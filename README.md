# Hustar_ML_contest
## 구성원 : 강나현, 권헌진, 김민호, 오승환
### 5.25(수)
- 승환 추가 제출 (public accuracy 0.930006)
> - early_stopping_patience=5로 늘리고 적용시켰더니 점수가 조금 더 올랐음. 예상대로 기존의 방식은 학습이 너무 빨리 종료됨
> - patience를 20으로 해보고 학습 시켜볼 예정
- 민호 첫 제출 (public accuracy 0.89497)
> - positive, negative pairs의 dataset 크기를 약 60만개로 줄임
> - RoBertaForSequenceClassification 대신 AutoModelForSequenceClassification 사용
> - MAX_LEN = 256, train_batch_size=32, eval_batch_size=32, early_stopping_patience = 5로 설정
>   - MAX_LEN이 작아서 256 이상 코드에 대한 학습이 저조하여 score가 낮게 나온 것으로 예상
>   - early_stopping_patience가 커지면 모델을 저장하는 크기도 그만큼 커져야 최적의 모델을 저장할 수 있을 듯

### 5.24(화)
- 나현 첫 제출 (public accuracy 0.49929)
> - 모델을 전혀 학습시키지 않고 바로 predicting
> - 이 경우에는 결과가 별로 좋지 않았음
> - 최소한의 학습은 있어야 할 것으로 보임
- 승환 첫 제출 (public accuracy 0.92825)
- 생각한 내용
> - 학습환경은 2080 두개. batch size를 작게 쓸 수 밖에 없었음 (model이 너무 크다...)
> - 그래서 hyperparameter가 max_len=512, train_batch=4, eval_batch_size=16, patience=2, eval_steps=500으로 설정됨
> - 이에따라 early stopping이 3000 step에서 진행됐는데, 너무 일찍 되지 않았나 하는 우려가 있음
- 할 일
> - max_len을 256으로 줄이고 해본다면 오히려 어떨까?
> - max_len을 512로 유지하되 dataset의 크기를 줄이고 batch_size를 키울 수 있다면 더 좋을것 같은데
> - distillation, quantization, pruning, weight sharing 등 경량화 기법을 사용해서 모델 자체를 가볍게 하는게 좋을수도?
> - early_stopping_patience=2는 너무 작긴함. 좀 더 키우고 학습시켜보자

### 05.23(월)
- Tokenize에 시간이 상당히 소요됨
- max_len 512로 tokenize해서 두개의 문제를 cross-encording하는 기법을 사용하기로 함

### 05.22(일)
- 코드 유사성 판단 AI 경진대회 참가 (Link : https://dacon.io/competitions/official/235900/overview/description)
- EDA 개시
- graphCodeBert 사용하기로 결정

### 05.02(월)
- Git repository 생성
- 프로젝트 목표 설정
