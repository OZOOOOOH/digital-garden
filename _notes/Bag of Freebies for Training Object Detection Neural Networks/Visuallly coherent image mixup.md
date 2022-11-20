Object Detection 을 위해서 Mixup 적용
- 베타 분포에 맞는 $\alpha, \beta$ 비율을 Mixup에 적용했을 때 효과적
모델 일반화 능력 키우고 오버피팅 문제 줄여줌

"Elephant in the room" 실험 진행

Vanilla 모델은 heavy occlusion & lack of context로 인해 elephant를 잘 찾지 못함
Mixup 적용 모델
- elephant를 찾는 것에 robust
- elephant detect시 평균적으로 가구 object에 대해 confidence가 낮음
- 전례없는 상황이나 객체들이 모여있는 경우 상당히 효과적임