# speech2translate_jeju

## Development Setting
- OS: Linux Ubuntu 20.4 LTS
- Python: 3.9.x
- Docker container: nvidia/cuda:11.8.0-devel-ubuntu20.04

## Installed Libraries
```bash
docker pull nvidia/cuda:11.8.0-devel-ubuntu20.04
pip install -r requirements.txt
```

## How to use
1. Download the dataset [LINK](https://www.aihub.or.kr/aihubdata/data/view.do?currMenu=115&topMenu=100&aihubDataSe=data&dataSetSn=71558)
2. '재주도'에 해당하는 데이터 및 따라 말하기 데이터만을 다운 받아서 압축을 해제합니다. <br> 이 때, train set 폴더 명을 circum_01로 하면 다른 수정 과정을 거치지 않아도 무방합니다.
3. EDA_dataset.ipynb 파일부터 실행하여 train, test split 된 파일을 생성합니다. <br> 이후, 각 셀을 실행시키면서 train, validation csv를 저장합니다.
4. jeju_kobart.ipynb를 실행합니다. <br> 해당 셀을 그대로 실행할 경우 문제가 없지만, 만약 custom dataset을 이용하려는 경우 dictionary 형태를 잘 지켜주세요. <br> ex. {'kr': "한국어", 'en':"English"}
5. jeju_kobart.ipynb는 한 파일에 fine tuning과 evaluation을 모두 진행합니다. 참고하여 실행하여 주세요. (trainer.push_to_hub() 이후는 evaluation process)

## Evaluation Result
| Model Name | BLEU Score | CER Score | Human Voting Score |
|:-----:	|:----------:	|:-----------: |:-----------:|
| JejuBART(ours) | 0.7187 | 0.0984 | 2.00  |

More results and cleansing codes would be published as soon as possible.
