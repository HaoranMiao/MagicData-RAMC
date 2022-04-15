# MagicData-RAMC
This is the offical repository of the Rich Annotated Mandarin Conversational (RAMC) speech dataset. Please see our paper, *"Open Source MagicData-RAMC: A Rich Annotated Mandarin Conversational (RAMC) Speech Dataset"*, for more information on how we produced the dataset. [Preprint available on arxiv](https://arxiv.org/abs/2203.16844).

## Download
The open-source dataset can be downloaded [here](https://www.magicdatatech.com/datasets/mdt2021s003-1647827542).

## Data Description
MagicData-RAMC comprises dialog speech data, corresponding transcriptions, voice activity timestamps, and speakers’ demographic information. It contains 351 multi-turn Mandarin Chinese dialogs, which amount to about 180 hours. The speech data is carefully annotated and manually proofed.

### Speaker Information
MagicData-RAMC recorded the speaker information in SPKINFO.txt.

The format is like 
```
CHANNEL	SPEAKER_ID	GENDER	AGE	                        REGION,CITY	  DEVICE
C0	G00000016	M	Middle-aged and young people	Sichuan	          Mobile phone
...
```

### Dialog Information
MagicData-RAMC recorded the dialog information in UTTERANCEINFO.txt

The format is like
```
CHANNEL	UTTRANS_ID	                SPEAKER_ID-1	SPEAKER_ID-2	TOPIC	    VALID(min)	TOTAL(min)  Environment
C0	CTS-CN-F2F-2019-11-15-188.wav	G00000016	G00000015	职业发展	    27.63	31.1	    室内
...
```

### Annotations
The format of annotations for each audio is like
```
[1.319,6.691]	G00000140	女,普通话	爱数智慧语音采集二零一九年十一月六日
[8.106,12.713]	G00000140	女,普通话	最近最近那个新海诚的啊，那个
...
```

### Dataset Partition
The following is a summary of the partition in MagicData-RAMC. The gender and demographic distributions are roughly balanced.

| **Information**| **Training**     | **Development** |**Test**    |
|:---------------|:------------------:|:------------------:|:------------------:|
| Duration (h)    | 149.65 | 9.89 | 20.64 |
|#Sample | 289 | 19 | 43 |
|#Speaker | 556 | 38 | 86 |
|#Male | 307 | 23 | 49 |
|#Female | 249 | 15 | 37 |
|#Northern China | 271 | 20 | 52 |
|#Southern China | 285 | 18 | 34 |

### Categories
We classify the dialogs in MagicData-RAMC into 15 diversified domains. The diversity of topics and the consistency in one dialog are beneficial to the
development of open-domain spoken dialog systems.

| **Topic**| **#Sample**     | **Duration (h)** |
|:---------------|:------------------:|:------------------:|
|Humanities |22 |11.46|
|Entertainment |1 |0.52|
|Sports |32 |16.62|
|Military |4 |1.98|
|Finance & Economy |5 |2.49|
|Religion |1 |0.52|
|Family Life |6 |1.48|
|Politics & Law |4 |2.07|
|Education & Health |53 |27.30|
|Digital Devices |39| 20.14|
|Climate & Environment |13| 6.62|
|Science & Technology |11 |5.66|
|Professional Development |35 |18.26|
|Art |84 |43.87|
|Ordinary Life |41 |21.19|

## ASR Track
We held the [Magic Data ASR-SD Challenge](https://github.com/MagicHub-io/Magic-Data-ASR-SD-Challenge) in August 2021.
The released data includes the training and development datasets described above.
The first track focuses on dialog speech recognition accuracy, with detailed rules and preparation guidelines available in [Magic Data ASR-SD Challenge](https://github.com/MagicHub-io/Magic-Data-ASR-SD-Challenge).

### Baseline
| **Model**| **Train Data** |**Test CER**    |
|:---------------|:------------------|:------------------:|
| [LAS-Conformer](https://arxiv.org/abs/2203.16844) | [MagicData-RAMC](https://www.magicdatatech.com/datasets/mdt2021s003-1647827542) & [MagicData-READ](http://www.openslr.org/68) | 19.1 |

### Leaderboard
Here are the competition results for the top six teams.

| **Contributor**|**Test CER**    |
|:---------------|:------------------:|
| ASLP@NPU    | 12.7 |
| Xiaomi      | 13.7 |
| Royalflush  | 14.5 |
| LinkSure    | 17.3 |
| BUPT AI Lab | 17.8 |
| Vocust      | 18.3 |

We encourage more participants to hit the leaderboard!

## SD Track
The second track focuses on speaker diarization in dialog scenarios, with rules and data preparation the same as the ASR track.

### Baseline
| **Model**| **Train Data** |**Test DER (collar 0.25)**    |
|:---------------|:------------------|:------------------:|
| [VBx](https://arxiv.org/abs/2203.16844) | [MagicData-RAMC](https://www.magicdatatech.com/datasets/mdt2021s003-1647827542) & [MagicData-READ](http://www.openslr.org/68) & [VoxCeleb](http://www.openslr.org/49) & [CN-Celeb](http://www.openslr.org/82) | 7.96 |

### Leaderboard
The leaderboard is temporarily empty since the test set published in Magic Data ASR-SD Challenge is different from that of MagicData-RAMC.

We look forward to your participation！

## Citation
```bibtext
@article{yang2022open,
  title={Open Source MagicData-RAMC: A Rich Annotated Mandarin Conversational (RAMC) Speech Dataset},
  author={Yang, Zehui and Chen, Yifan and Luo, Lei and Yang, Runyan and Ye, Lingxuan and Cheng, Gaofeng and Xu, Ji and Jin, Yaohui and Zhang, Qingqing and Zhang, Pengyuan and others},
  journal={arXiv preprint arXiv:2203.16844},
  year={2022}
}
```


