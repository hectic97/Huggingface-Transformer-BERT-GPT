# Huggingface-Transformer-BERT-GPT
Fine-tuning Huggingface-Transformer pretrained multilingual BERT, GPT model using Korean Dataset<br>
### Reference
https://huggingface.co/transformers/index.html<br>
https://github.com/NLP-kr/tensorflow-ml-nlp-tf2

## BERT Sentiment Analysis
- Naver Movie Review Datasets
- data: 시간낭비 입니다. 보지 마세요.
- label: 0

## BERT Natural Language Inference
- KorNLU Dataset
- data1: 말을 탄 사람이 고장난 비행기 위로 뛰어오른다.
- data2: 사람은 야외에서 말을 타고 있다.	
- label: entailment

## BERT Named Entity Recognition
- KorNER Dataset
- data: 24회 최경운호의 좌익선상 28루타로 포문을 연 한화는
- label: NUM-B PER-B O NUM-B O O ORG-B

### F1 score

Label |     precision  |  recall | f1-score |  support |
---- | ---- | ---- | ---- | ---- |
AFW    |   0.42   |   0.50  |    0.45   |    393
ANM    |   0.64   |   0.73  |    0.68     |  699
CVL     |  0.71|      0.76|      0.73 |     5735
DAT      | 0.88 |     0.89 |     0.89  |    2510
EVT       |0.69  |    0.71  |    0.70   |   1093
FLD |      0.44   |   0.61   |   0.51    |   228
LOC  |     0.76    |  0.77    |  0.77  |    2124
MAT   |    0.00     | 0.00|      0.00   |     12
NUM    |   0.87      |0.90 |     0.89    |  5544
ORG     |  0.75|      0.81  |    0.78     | 4055
PER      | 0.81 |     0.82   |   0.81     | 4412
PLT  |     0.20  |    0.12    |  0.15      |  34
TIM   |    0.79   |   0.90     | 0.84     |  314
TRM    |   0.61    |  0.65   |   0.63     | 1950
micro avg  |     0.76 |     0.80 |     0.78 |    29103
macro avg   |    0.61  |    0.65  |    0.63  |   29103
weighted avg |      0.76|      0.80|      0.78 |    29103

## BERT Semantic Textual Similarity
- KorSTS Dataset
- data1: 파란색 교대복 차림의 여성이 음식을 잘게 썰었다.
- data2: 파란 드레스를 입은 여자가 케이크를 자른다.
- label: 3.8 ( low similarity 0 ~ 5 high similarity )

### Pearson correlation coefficient
dataset| Pearson Correlation | MSE
---- | ---- | ---- |
train | 0.7986 | 0.4523
dev | 0.8136 | 0.7116
test | 0.8104 | 0.9846

### inference
sentence1 | sentence2 | Pearson Coef 
----|----|----|
당신은 실험하고 당신이 좋아하는 것을 찾아야 할지도 모른다.  |당신은 당신에게 어떤 게 효과가 있는지 알아내야 한다. | 2.532
한 남자가 기타를 치고 있다. | 한 남자가 트럼펫을 연주하고 있다. | 1.910
