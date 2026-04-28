# Geospatial Water Quality Prediction Challenge

This challenge focused on predicting three water-quality indicators from geospatial, environmental, hydrological, soil, land-cover, and remote-sensing features.

## Targets

- Dissolved Reactive Phosphorus
- Electrical Conductance
- Total Alkalinity

## Final Best Verified Result

- Best verified true leaderboard score: 0.4199
- Certificate threshold: 0.4
- Status: certificate threshold secured

## Main Modeling Setup

The main modeling approach was a target-wise tabular regression pipeline.

For each target, the pipeline used:

- ExtraTreesRegressor
- LightGBMRegressor
- Ridge meta-model trained on out-of-fold predictions

Validation used GroupKFold with cell_id as the grouping variable.

## General Pipeline Logic

1. Build target-specific feature sets.
2. Train ExtraTrees and LightGBM in grouped cross-validation.
3. Generate out-of-fold predictions for both base models.
4. Train a Ridge meta-model on the OOF predictions.
5. Retrain base models on the full training data.
6. Predict validation/test rows.
7. Save the final submission.

## Best Working Feature Addition

The strongest true leaderboard improvement came from adding a compact set of time-aligned Google Earth Engine features.

These features were extracted for a 1 km buffer around each sampling point and aligned to the sample date using the preceding 12-month window.

## Winning EE Feature Block

- buf1000_dry_days_12m
- buf1000_heavy_days_12m
- buf1000_lst_amp_12m
- buf1000_lst_anom_3m_12m
- buf1000_ndvi_amp_12m
- buf1000_ndvi_anom_3m_12m
- buf1000_ppt_max_daily_12m
- buf1000_ppt_p90_daily_12m
- buf1000_wet_days_12m

## Interpretation of the Winning Features

This feature block captured local, recent environmental conditions:

- dry-day frequency
- wet-day frequency
- heavy-rain frequency
- extreme daily precipitation
- vegetation seasonal amplitude
- vegetation anomaly
- land surface temperature amplitude
- land surface temperature anomaly

These features worked better than broad static basin summaries because they were local, time-aligned, event-oriented, and compact enough not to flood the model with noise.

## Best Submission Distribution

Dissolved Reactive Phosphorus:

- minimum: 9.9050
- mean: 31.0485
- maximum: 72.9918

Electrical Conductance:

- minimum: 168.8102
- mean: 405.7066
- maximum: 787.0541

Total Alkalinity:

- minimum: 22.6389
- mean: 101.7101
- maximum: 243.0561

## Experiment Summary Table

| Experiment | Change Tested | Result | Takeaway |
|---|---|---|---|
| Baseline target-wise stack | ExtraTrees plus LightGBM plus Ridge using selected environmental features | Passed early threshold range | Solid baseline, but limited hidden-LB generalization |
| Target-specific feature selection | Selected strong features per target from existing numeric features | Helpful | Target-wise feature maps were better than one shared feature set |
| DRP postprocessing | Piecewise stretching of DRP predictions | Mixed | Sometimes improved distribution, but not reliable after new features |
| kNN spatial context | Local neighbor-based spatial context features | Did not reliably help | Spatial proximity features improved intuition or CV but did not generalize well enough |
| BasinATLAS features | Joined HydroATLAS/BasinATLAS basin-level features | Hurt LB | Broad basin-level features created noise or hidden-split mismatch |
| Leakage-safe BasinATLAS filtering | Removed target-like, ID-like, topology-like, and risky basin columns | Still not useful | Even defensive BasinATLAS features did not provide robust signal |
| RiverATLAS nearest reach features | Nearest river reach and RiverATLAS-style features | Did not help | River proximity alone was not enough and was unstable under LB |
| Raw EE buffer means | NDVI, LST, precipitation, and other raster means in buffers | Hurt LB | Simple means were redundant or too smoothed |
| Date-aware EE extraction | Time-consistent 2011-2015 feature extraction instead of future data | Methodologically necessary | Correct temporal alignment was important, but raw means still did not boost |
| EE extremes and anomalies at 1 km | 9 local time-aligned event and anomaly features | Best improvement | Compact event-based features gave the best real LB signal |
| Larger or extra EE feature blocks | More radii, more buffer features, dry-spell and p99 add-ons | Did not improve | More features diluted the useful signal |
| Seasonality shape features | Month-of-maximum, month-of-minimum, and monthly variability | No improvement | Redundant with the winning anomaly and amplitude features |
| CatBoost main model | CatBoost as alternative primary model | Did not improve | Architecture change alone did not beat the stack |
| Harmful feature family dropping | Dropped feature families based on ablation tests | Hurt LB | Local ablation did not translate into hidden-LB improvement |

## What Worked

### Compact time-aligned event features

The best improvement came from features that described recent hydrological and vegetation conditions before the sample date.

The most useful signals were not broad averages, but event and anomaly features:

- extreme precipitation
- dry and wet day counts
- NDVI amplitude
- NDVI anomaly
- LST amplitude
- LST anomaly

### Target-wise modeling

Building separate feature maps and models for each target made sense because the three targets respond to different environmental processes.

- DRP: nutrient mobilization, runoff, agriculture, wet and dry events
- EC: concentration, hydrology, geology, groundwater, evaporation
- TA: geology, buffering capacity, hydrology, carbonate-related processes

### Careful true leaderboard testing

Several ideas looked reasonable but failed on the true leaderboard. The best progress came from treating LB feedback as a real generalization test rather than trusting local CV blindly.

## What Did Not Work

### Broad basin-level external data

BasinATLAS and related features seemed promising because they contain hydrological and environmental summaries. However, they consistently failed to improve the true leaderboard.

Likely reasons:

- wrong spatial support
- broad summaries not aligned with local sampling conditions
- hidden test distribution mismatch
- too many correlated or noisy columns

### More features without stronger signal

Adding more EE features did not automatically help. The strongest feature block was small and specific.

This suggested that the model was sensitive to feature dilution.

### Alternative model family alone

CatBoost did not improve over the existing stack. This suggested that the bottleneck was not only model architecture, but the available signal and its representation.

### Feature family ablation

Dropping entire feature families based on local tests hurt the leaderboard. This showed that local OOF improvements were not always aligned with hidden-LB behavior.

## Main Lessons Learned

1. More external data is not automatically better.
2. Temporal alignment matters for samples from 2011-2015.
3. Small, mechanistic features can beat large feature blocks.
4. Hidden leaderboard behavior can differ strongly from CV.
5. The best signal was local and event-based.

## Final Status

The challenge threshold was successfully passed.

Final best verified true leaderboard score: 0.4199

The most important contribution was the design and integration of time-aligned Google Earth Engine extreme and anomaly features into a target-wise tree-based regression stack.

## What I Would Do With More Time

1. Build upstream or catchment-connected features instead of simple local or basin features.
2. Improve validation using spatially blocked CV or basin-based CV.
3. Develop a more systematic ensemble of multiple feature representations.
4. Investigate target-specific calibration and error patterns.
5. Compare local buffer features against upstream hydrological summaries.
