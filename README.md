#

## Table of Contents

* [Introduction](#introduction)
* [Data description](#data-description)
* [License](#license)
* [Version](#version)
* [Reference](#reference)
* [Citation](#citation)
* [Version](#version)

## Introduction

本オープンデータセット群は良品学習の評価を目的に利用されるもので、PCB1_DATASET、PCB4_DATASET、CHEWINGGUM_DATASET、TRANSISTOR_DATASET、BOTTLE_DATASET、METAL_NUT_DATASETの全6種が含まれています。

製造業の現場には、良品学習を用いて軽微な欠陥を持つ不良品と完全な良品を正確に区別したいという需要があります。

これらのデータセットは良品学習で検出が難しいとされる「軽微な欠陥を持つ不良品」や「良品に酷似した不良品」に対する異常検知性能を確認するため、[VisA](https://github.com/amazon-science/spot-diff/)、[MVTec AD](https://www.mvtec.com/company/research/datasets/mvtec-ad/)のデータセットを技術的に改変して作成され、既存のデータセットに対して独自の不良品画像を追加したものです。

利用用途は研究目的に限定してください。商用利用は不可です。

利用時は[CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/legalcode)及び[VisA](https://github.com/amazon-science/spot-diff/)、[MVTec AD](https://www.mvtec.com/company/research/datasets/mvtec-ad/)それぞれのライセンスに準拠してください。

## Data description

PCB1_DATASET、PCB4_DATASET、CHEWINGGUM_DATASETの3種は、VisAのデータセットをMVTec-AD形式に変換した後、同データセットから欠陥個所の大きい不良品画像を除去し、独自の不良種別「simulated_defect」を新たに付与したデータセットです。

TRANSISTOR_DATASET、BOTTLE_DATASET、METAL_NUT_DATASETの3種は、MVTec-ADのデータセットに独自の不良種別「simulated_defect」を新たに付与したデータセットです。

不良種別「simulated_defect」は、スマートフォンカメラ向けアクチュエーターの電子部品基盤に発生した不良品を白色照明下で撮影し、その不良品画像とデータセット元の良品画像群を用いて、欠陥画像を疑似的に生成した不良画像群から構成されます。

本データセットは全てMVTec-AD形式に準拠し、フォルダ構成の例は以下の通りです。

```shell
ALAP-DATASET/
└── pcb1_dataset/
    ├── ground_truth/
    │   ├── melt/
    │   ├── melt, scratch/
    │   ├── missing/
    │   ├── imitate/
    │   └── simulated_defect/
    │
    ├── test/
    │   ├── good/
    │   ├── melt/
    │   ├── melt, scratch/
    │   ├── missing/
    │   ├── imitate/
    │   └── simulated_defect/
    │
    └── train/
        └── good/
```

下記の各表はデータセットに含まれる良品・不良品画像の枚数と、不良種別毎の枚数を示します。

また、画像によって1枚で複数の不良種別を持つため、実際のフォルダ項目数と不良種別に差異が生じる場合があります。

### PCB1_DATASET

| Dataset      | Normal Samples(train) | Anomaly Samples(test) | Normal Samples(test) |
|--------------|-----------------------|-----------------------|----------------------|
| PCB1_DATASET | 804                   | 143                   | 100                  |

| Anomaly Classes : 5 | Count |
|---------------------|-------|
| melt                | 42    |
| melt, scratch       | 5     |
| missing             | 2     |
| scratch             | 14    |
| simulated_defect    | 80    |

### PCB4_DATASET

| Dataset      | Normal Samples(train) | Anomaly Samples(test) | Normal Samples(test) |
|--------------|-----------------------|-----------------------|----------------------|
| PCB4_DATASET | 805                   | 183                   | 100                  |

| Anomaly Classes : 8              |Count|
|----------------------------------|-----|
| burnt,dirt                       | 1   |
| damage                           | 7   |
| scratch,damage,extra             | 1   |
| burnt                            | 1   |
| damage,dirt                      | 2   |
| missing,dirt                     | 4   |
| scratch,damage                   | 1   |
| extra                            | 9   |
| burnt,extra                      | 1   |
| scratch,extra,dirt               | 1   |
| extra,dirt                       | 3   |
| missing                          | 11  |
| scratch,missing,dirt             | 1   |
| missing,damage                   | 2   |
| missing,damage,extra             | 1   |
| scratch,missing                  | 1   |
| scratch,dirt                     | 3   |
| scratch                          | 2   |
| wrong place,dirt                 | 8   |
| scratch,extra,wrong place        | 1   |
| wrong place                      | 2   |
| simulated_defect                 | 120 |

### CHEWINGGUM_DATASET

| Dataset            | Normal Samples(train) | Anomaly Samples(test) | Normal Samples(test) |
|--------------------|-----------------------|-----------------------|----------------------|
| CHEWINGGUM_DATASET | 303                   | 121                   | 100                  |

| Anomaly Classes : 4                                  | Count |
|------------------------------------------------------|-------|
| similar colour spot                                  | 10    |
| corner missing,similar colour spot,small cracks      | 1     |
| simulated_defect                                     | 110   |

### TRANSISTOR_DATASET

| Dataset      | Normal Samples(train) | Anomaly Samples(test) | Normal Samples(test) |
|--------------|-----------------------|-----------------------|----------------------|
| TRANSISTOR_DATASET | 213                   | 60                   | 55                  |

| Anomaly Classes : 5 | Count |
|---------------------|-------|
| bent_lead           | 10    |
| cut_lead            | 10    |
| damaged_case        | 10    |
| misplaced           | 10    |
| simulated_defect    | 20    |

### BOTTLE_DATASET

| Dataset        | Normal Samples(train) | Anomaly Samples(test) | Normal Samples(test) |
|----------------|-----------------------|-----------------------|----------------------|
| BOTTLE_DATASET | 204                   | 96                    | 20                   |

| Anomaly Classes : 4 | Count |
|---------------------|-------|
| broken_large        | 20    |
| broken_small        | 22    |
| contamination       | 21    |
| simulated_defect    | 33    |

### METAL_NUT_DATASET

| Dataset        | Normal Samples(train) | Anomaly Samples(test) | Normal Samples(test) |
|----------------|-----------------------|-----------------------|----------------------|
| METAL_NUT_DATASET | 215                   | 123                    | 22                   |

| Anomaly Classes : 5 | Count |
|---------------------|-------|
| bent                | 25    |
| color               | 22    |
| flip                | 23    |
| scratch             | 23    |
| simulated_defect    | 30    |


## License

The data is released under the CC BY 4.0 license.

本データセットは[VisA](https://github.com/amazon-science/spot-diff/)、[MVTec AD](https://www.mvtec.com/company/research/datasets/mvtec-ad/)を技術的に改変して作成されたものです。

商用利用は不可です。利用時は[CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/legalcode)及びそれぞれのライセンスに準拠してください。

## Version

ALAP-DATASETのバージョン情報はこちら：

[release_notes.md](release_notes.md)

## Citation

本データセット参照時は、下記の Bibtex を引用ください。

```bibtex
@inproceedings{morita2025anomdsproto,​
  author = {森田, 賢 and 洸之,川本 and 千葉,大輝 and 伊藤, 稀史 and 堀越, 智久 and 丹羽, 篤士},​
  booktitle = {2025年度画像符号化シンポジウム（PCSJ 2025）／2025年度映像メディア処理シンポジウム（IMPS 2025）},​
  keywords = {ALPSALPINE anomaly-detection dataset},​
  pages = {43-44},​
  title = {良品学習性能評価を目的とした画像検査データセットの構築と初期検討},​
  year = 2025,​
  month = Nov,​
  publisher = {電子情報通信学会画像工学研究専門委員会},​
  address = {静岡, 日本}​
}​
```

## Reference

本データセットは、下記のデータセットを参考に作成しました。

```bibtex
@article{zou2022spot,
  title={SPot-the-Difference Self-Supervised Pre-training for Anomaly Detection and Segmentation},
  author={Zou, Yang and Jeong, Jongheon and Pemula, Latha and Zhang, Dongqing and Dabeer, Onkar},
  journal={arXiv preprint arXiv:2207.14315},
  year={2022}
}
@inproceedings{8954181,
  added-at = {2024-12-11T15:52:21.000+0100},
  author = {Bergmann, Paul and Fauser, Michael and Sattlegger, David and Steger, Carsten},
  biburl = {https://www.bibsonomy.org/bibtex/20c11bf7d687f981e9145070f80c27590/andolab},
  booktitle = {2019 IEEE/CVF Conference on Computer Vision and Pattern Recognition (CVPR)},
  doi = {10.1109/CVPR.2019.00982},
  interhash = {0569b20d2c55b8156f0307a05b670a3a},
  intrahash = {0c11bf7d687f981e9145070f80c27590},
  keywords = {Anomaly-detection MVTec},
  pages = {9584-9592},
  timestamp = {2024-12-11T15:52:21.000+0100},
  title = {MVTec AD — A Comprehensive Real-World Dataset for Unsupervised Anomaly Detection},
  year = 2019
}

```
