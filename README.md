# FastSpeech 2 English and Telugu Assignment

This repository contains the FastSpeech 2 reference implementation and the assignment work completed so far. It is a **partial submission**; the status below distinguishes completed work from items still outstanding.

## Current status

| Area | Current state |
|---|---|
| Reference implementation | FastSpeech 2 source, configs, and license are included under `English/`. |
| English | English training was run in Colab. Checkpoints 1,000–5,000 were present in the user's Google Drive during the Colab session; they are not included in this repository. |
| Telugu data | A 5-hour train / 1-hour validation selection was prepared in Colab from `SPRINGLab/IndicTTS_Telugu`: 1,045 clips, 5.0005 h train and 1.0001 h validation. The selected manifest and files were in Google Drive/Colab, not this local checkout. |
| Telugu preprocessing | Colab reported 1,045 processed utterances (873 train, 172 validation). The processed features are not present in this repository. |
| Telugu training | Colab logs reached step 500 / 5,000. Loss decreased from 11.5143 at step 100 to 2.8914 at step 500. No Telugu checkpoint was saved before the runtime reset, so this is not a resumable trained model. |
| Test audio, variance-adaptor plots, report | Not completed or included. |
| GitHub publication | Public repository: [mishraayushgit/FastSpeech2-Assignment](https://github.com/mishraayushgit/FastSpeech2-Assignment), branch `main`. |

See [`Telugu/PROGRESS.md`](Telugu/PROGRESS.md) for the recorded Telugu training log and limitations.

## Repository contents

- `English/` — reference FastSpeech 2 source and configuration files. The directory name reflects the assignment's English model area; the code is adapted from the upstream project and still needs assignment-specific review.
- `Telugu/PROGRESS.md` — factual record of the Telugu work done in Colab. Telugu training code/configs and feature arrays are not available in this local checkout.
- `FastSpeech2_Assignment_Starter.ipynb` — starter notebook, not the executed Colab training notebook.
- `upstream/` — local reference clone retained for comparison; it is excluded from the GitHub commit because it is a nested Git repository. The upstream source and license are already represented in `English/`.
- `Results/` and `Report/` — directories reserved for assignment outputs; required final outputs are not present yet.

## Data and checkpoint handling

Raw speech datasets, derived feature arrays, and model checkpoints are not committed. This avoids distributing audio or model weights without verifying their applicable terms and avoids GitHub's large-file limits. The Telugu dataset is available from [SPRINGLab/IndicTTS_Telugu](https://huggingface.co/datasets/SPRINGLab/IndicTTS_Telugu); review the dataset's original license and usage terms before downloading or redistributing it. The assignment also references [LJSpeech](https://keithito.com/LJ-Speech-Dataset/).

## Run the reference code

Use a compatible Linux/Colab GPU environment. Install a PyTorch build appropriate for the selected CUDA runtime, then install the Python dependencies:

```bash
pip install -r requirements.txt
```

The source is based on [ming024/FastSpeech2](https://github.com/ming024/FastSpeech2). Upstream configs are examples; point paths to your own dataset, preprocessing outputs, logs, and checkpoints before running preprocessing or training.

## Remaining assignment work

1. Restore the Colab dataset selection, processed features, and separate language configs from Drive; save Telugu checkpoints at regular intervals.
2. Finish Telugu training and preserve the checkpoint and logs.
3. Generate the five English and five Telugu test sentences from the assignment.
4. Save training/validation loss plots and per-sentence duration, F0, and energy plots.
5. Write the technical report with data split, preprocessing, training curves, speech observations, limitations, and reproducibility details.
6. Add the completed artifacts and push the updates to the public repository for evaluation.

## References

- Ren et al., [FastSpeech 2: Fast and High-Quality End-to-End Text to Speech](https://arxiv.org/abs/2006.04558).
- [FastSpeech 2 reference implementation](https://github.com/ming024/FastSpeech2).
