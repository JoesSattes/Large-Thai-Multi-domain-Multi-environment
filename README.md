# Large Thai Multi-domain Multi-environment
This repository contains the experimental setup described in the Speech-to-Text Cartography paper. We provide a list of 10 data sources used for Thai speech recognition, which are divided into three sets based on the original public datasets.

## Resample audio command
```
ffmpeg -i <audio_path_input> -ac 1 -ar 16000 -o <audio_path_output>
```

## List of dataset source
Table

## Dataset Splitting
For the public dataset, most datasets are already divided into train, validate, and test sets. We followed the original splitting provided by the dataset. In other cases, we performed the dataset splitting using the following command:
```
as
```

## The access of private dataset
Currently, the private datasets are not included in this version due to privacy concerns and legal regulations in Thailand. However, we have plans to develop new datasets following the same criteria as ProVoice and KCall in the future. For more information, please contact us at nlp@kbtg.tech.
