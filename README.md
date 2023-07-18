# Large Thai Multi-domain Multi-environment
This repository contains the experimental setup described in the Speech-to-Text Cartography paper. We provide a list of 10 data sources used for Thai speech recognition, which are divided into three sets based on the original public datasets. Totally, the LTMM dataset contains 381.98 hours of speech in the final version (public+private), with 336.75 hours for the public dataset and 45.23 hours for the private dataset, as around 88.16% and 11.84%, respectively.

## List of dataset source
| Dataset | Description | Domain | Environment | Link |
| --- | --- | --- | --- | --- |
| `Common voice 12 (CV12)` | a crowd-sourced, open-licensed dataset where speakers record text from Wikipedia in various languages |  Wikipedia (General) | Open | [link](https://commonvoice.mozilla.org/th/datasets) |
| `Fleur` | a dataset with real noise recordings in 102 languages, it consists of a collection of audio recordings from various speakers, covering a wide range of speaking styles, topics, and environments | news broadcasts, interviews, podcasts, lectures, conversations, and more | Open and Real-world | [link](https://huggingface.co/datasets/google/fleurs/viewer/th_th/train) |

## Resample audio command
```
ffmpeg -i <audio_path_input> -ac 1 -ar 16000 -o <audio_path_output>
```

## Dataset splitting
In our experiment, we collected 10 datasets as part of LTMM. Each dataset provides a final version with successful validation, already divided into train, validate, and test sets. However, the CV12 dataset, although validated by humans, is relatively small compared to the full validation set. To address this, we utilized [TH_CV_script](https://github.com/ekapolc/Thai_commonvoice_split) to expand the size of the CV12 dataset and improve its performance with Thai native script. This script incorporates [TH_Re-validation](https://github.com/ekapolc/Thai_commonvoice_split/blob/main/clean_common_voice.ipynb) for re-validation and [spell_correction](https://github.com/ekapolc/Thai_commonvoice_split/blob/main/spell_correction.py) for Thai normalization in CV12.

For the other datasets, we only applied Thai normalization while following the original splitting provided by each dataset.

## The access of private dataset
Currently, the private datasets are not included in this version due to privacy concerns and legal regulations in Thailand. However, we have plans to develop new datasets following the same criteria as ProVoice and KCall in the future. For more information, please contact us at nlp@kbtg.tech.
