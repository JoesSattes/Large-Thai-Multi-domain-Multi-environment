# Large-Thai-Multi-domain-Multi-environment
This repository contains the experimental setup in Speech-to-Text Cartography paper. We show the list of 10 data sources for Thai speech recognition, which divide into three sets based on the original public datasets.

## Resample audio command
```
ffmpeg -i <audio_path_input> -ac 1 -ar 16000 -o <audio_path_output>
```

## List of dataset source
Table

## Dataset Splitting
For the public dataset, most dataset are currently divided into train, validate, and test sets. We follow on the original splitting. Also, in other case, we splitting set with below command;
```
as
```

## The access of private dataset
Currently, the private datasets are not provided in this version because of the privacy data and law in Thailand. But, in the future, we have a plane to develop the new dataset with same criterion in ProVoice and Kcall. For more information, please contact in `nlp@kbtg.tech`. 
