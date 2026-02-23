# NN_Project — Next-Region Prediction (Optimization Study)

This project studies how optimizer choice and learning rate affect convergence and stability when training a small MLP on a hospital location tracking dataset. The task is next-region prediction: for each person (`ownerId`), predict the region at time `t+1` from features at time `t`.
## Author 
Remy Frederick

## Objective
Compare optimizer behavior and learning-rate sensitivity while keeping:
- Dataset and preprocessing fixed
- Model architecture fixed
- Train/val/test split fixed (by `ownerId`)

## Dataset
CSV: `Space_Utilization.csv`

Columns:
- trackingType, ownerCreated, regionName, dateString, ownerId, long, ownerDistance,
  enddate, ownerAccountType, regionId, ownerDuration, lat, timestamp

## Optimizers
- Gradient Descent (GD)
- GD + Momentum
- Adam

## Notes
- The CSV has a non-header first line (“Space Utilization”); skip it when reading.
- Keep architecture fixed for all optimizer/lr comparisons.
