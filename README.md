# Large Thai Multi-domain Multi-environment
This repository contains the experimental setup described in the Speech-to-Text Cartography paper. We provide a list of 10 data sources used for Thai speech recognition, which are divided into three sets based on the original public datasets. Totally, the LTMM dataset contains 381.98 hours of speech in the final version (public+private), with 336.75 hours for the public dataset and 45.23 hours for the private dataset, as around 88.16% and 11.84%, respectively.

## List of dataset source
| Dataset | Description | Domain | Environment | Link |
| --- | --- | --- | --- | --- |
| `Common voice 12 (CV12)` | a crowd-sourced, open-licensed dataset where speakers record text from Wikipedia in various languages |  Wikipedia (General) | Open | [link](https://commonvoice.mozilla.org/th/datasets) |
| `Fleur` | a dataset with real noise recordings in 102 languages, it consists of a collection of audio recordings from various speakers, covering a wide range of speaking styles, topics, and environments | news broadcasts, interviews, podcasts, lectures, conversations, and more. | Open and Real-world | [link](https://huggingface.co/datasets/google/fleurs/viewer/th_th/train) |
| `Gowajee` | a recording input command voices spoken into a microphone for ordering smart devices. The recording environment varied over the years, with a uni-directional microphone used initially and uncontrolled microphones in later years, and the recording location is not fixed, introducing uncontrolled environmental factors. |  Smart-device | Semi-open | [link](https://github.com/ekapolc/gowajee_corpus) |
| `Thai Elderly Speech Command (TESC)` | a recording input command voices spoken into a microphone for ordering smart devices. | Smart-device | Close | [link](https://github.com/VISAI-DATAWOW/Thai-Elderly-Speech-dataset/releases/tag/v1.0.0) |
| `Thai Speech Emotion Dataset (ThaiSER)` | a recording speech converstation in each scenario on studio and virtual meeting environment. |  Conversation | Close (Studio and Virtual Meeting) | [link](https://github.com/vistec-AI/dataset-releases/releases/tag/v1) |
| `Thai News Speech Recognition corpus (LOTUS-BNv1)` | a Thai television broadcast news corpus. In addition to audio recordings and their transcription, this corpus also includes a detailed annotation of many interesting characteristics of broadcast news data such as acoustic condition, overlapping speech, news topic and named entity. |  Broadcast news | Close (Studio and Telephone) | [link](https://nectec.or.th/corpus/index.php) |
| `Thai News Speech Recognition corpus (LOTUS-BNv2)` | a Thai television broadcast news corpus. In addition to audio recordings and their transcription, this corpus also includes a detailed annotation of many interesting characteristics of broadcast news data such as acoustic condition, overlapping speech, news topic and named entity. |  Broadcast news | Close (Studio and Telephone) | [link](https://aiforthai.in.th/corpus.php) |
| `Thai Speech Recognition corpus from NECTEC (LOTUS)` | a Thai speech recognition corpus with accoustic detail such phonetic, which has the transcription distribution is also similar to the daily used context (ORCHID corpus in this case). | General | Close (Clean and Noise) | [link1](https://aiforthai.in.th/corpus.php) [link2](https://github.com/korakot/corpus/releases/download/v1.0/AIFORTHAI-LotusCorpus.zip) |


## Resample audio command
```
ffmpeg -i <audio_path_input> -ac 1 -ar 16000 -o <audio_path_output>
```

## Dataset splitting
In our experiment, we collected 10 datasets as part of LTMM. Each dataset provides a final version with successful validation, already divided into train, validate, and test sets. However, the CV12 dataset, although validated by humans, is relatively small compared to the full validation set. To address this, we utilized [TH_CV_script](https://github.com/ekapolc/Thai_commonvoice_split) to expand the size of the CV12 dataset and improve its performance with Thai native script. This script incorporates [TH_Re-validation](https://github.com/ekapolc/Thai_commonvoice_split/blob/main/clean_common_voice.ipynb) for re-validation and [spell_correction](https://github.com/ekapolc/Thai_commonvoice_split/blob/main/spell_correction.py) for Thai normalization in CV12.

For the other datasets, we only applied Thai normalization while following the original splitting provided by each dataset.

## The access of private dataset
Currently, the private datasets are not included in this version due to privacy concerns and legal regulations in Thailand. However, we have plans to develop new datasets following the same criteria as ProVoice and KCall in the future. For more information, please contact us at nlp@kbtg.tech.
