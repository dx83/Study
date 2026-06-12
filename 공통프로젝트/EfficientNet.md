# EfficientNet-B0

### 2019년에 처음 소개, 추론에 필요한 FLOPS가 가장 적은 효율적인 모델 중 하나
### ImageNet 벤치마크와 다양한 전이학습 기반 이미지 분류 문제에서 당시 최고 수준(SOTA)의 정확도를 달성한 CNN 모델
`FLOPS` : Floating Point Operations Per Second, 초당 부동소수점 연산 횟수

## keras
- 이 모델은 (height, width, channel) 형태의 입력 이미지를 사용하며, 입력 데이터(3개의 channel)는 [0, 255] 범위의 값을 가져야 한다. 정규화(Normalization)는 모델 내부에서 자동으로 이루어집니다.
- B0부터 B7까지의 기본 모델들은 서로 다른 입력 이미지 크기를 사용한다. 아래는 각 모델이 요구하는 입력 이미지 크기 목록이다.

| Base model | resolution|
|----------------|-----|
| EfficientNetB0 | 224 |
| EfficientNetB1 | 240 |
| EfficientNetB2 | 260 |
| EfficientNetB3 | 300 |
| EfficientNetB4 | 380 |
| EfficientNetB5 | 456 |
| EfficientNetB6 | 528 |
| EfficientNetB7 | 600 |
