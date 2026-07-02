# Deep Learning

## Experiment discipline
- Treat model changes as experiments: state the hypothesis, the expected metric movement, and the comparison baseline before changing training code.
- Keep data preprocessing, model architecture, loss functions, optimizer settings, and evaluation metrics explicit and reproducible.
- Do not change random seeds, dataset splits, precision settings, or augmentation policy while also changing model logic unless the user asks for a broad experiment.
- Preserve checkpoint compatibility unless the task explicitly requires a breaking architecture or state-dict change.

## Training and evaluation
- Prefer small, fast smoke runs before long training jobs.
- Report the exact command, config, dataset split, seed, hardware assumptions, and key metrics for any training or evaluation run.
- Watch for silent failures: constant loss, NaNs/Infs, degenerate predictions, empty batches, train/eval mode mistakes, and metric leakage.
- For performance work, distinguish data-loading bottlenecks, host/device transfer overhead, compilation time, and model compute time.

## Data and metrics
- Avoid inspecting or using test labels during development.
- Keep train, validation, and test metrics separate in code, logs, and summaries.
- When changing metrics, preserve the old metric path long enough to compare before and after behavior.
- Document any class weighting, masking, padding, truncation, or sample filtering that affects reported results.

