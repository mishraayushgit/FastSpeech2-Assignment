# Telugu progress record

This is a partial-work record from the Colab session. The notebook outputs and Google Drive files were not copied into this local checkout, so the figures below are transcribed from the Colab output observed during that session.

## Dataset selection and preprocessing

- Dataset source: `SPRINGLab/IndicTTS_Telugu` on Hugging Face.
- Selected in Colab: 1,045 audio clips, approximately 5.0005 hours for training and 1.0001 hours for validation.
- Preprocessing output reported: 1,045 utterances; 873 training items and 172 validation items.
- The audio, selected manifest, and extracted features are not included here. Review the original dataset license and usage terms before reusing or redistributing any data.

## Telugu training log

| Step | Total loss | Mel | Mel postnet | Pitch | Energy | Duration |
|---:|---:|---:|---:|---:|---:|---:|
| 100 | 11.5143 | 5.2397 | 5.2416 | 0.2895 | 0.4329 | 0.3106 |
| 200 | 8.9120 | 4.2411 | 4.1975 | 0.0847 | 0.2447 | 0.1441 |
| 300 | 6.1552 | 3.0051 | 2.8629 | 0.0455 | 0.1385 | 0.1031 |
| 400 | 3.9739 | 1.9440 | 1.7766 | 0.0328 | 0.1474 | 0.0730 |
| 500 | 2.8914 | 1.2880 | 1.4253 | 0.0269 | 0.0996 | 0.0516 |

The configured run targeted 5,000 steps and saved checkpoints every 1,000 steps. The runtime reset before the first checkpoint was written. These logs document an incomplete run; they do not constitute a usable Telugu checkpoint or a finished model.

## Still required

- Restore the Colab corpus and processed features, then resume training from a valid saved checkpoint or restart and save checkpoints regularly.
- Produce validation and training loss plots, test-sentence audio, and duration/F0/energy plots.
- Include the completed Telugu preprocessing/training/inference scripts and configuration files in this repository.
