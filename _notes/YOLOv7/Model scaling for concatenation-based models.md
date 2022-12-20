
<img src="Pasted image 20221127193122.png" width="50%">

- (a)에서 (b)로 depth scaling을 하면 computational 블럭의 출력 width도 증가하게 됨
- 이는 transition layer의 input channel도 증가하게 되는 것을 의미
- 이렇게 되면 그 다음 transition layer의 input channel도 증가하여 반복적으로 발생하게 되기 때문에
scaling factor에 대한 분석이 불가능해짐

<img src="Pasted image 20221127193317.png" width="50%">

위 문제를 해결하고자 (c) 방법 제안함
- Computational block에만 depth scaling 적용 -> Computational block output channel 증가 -> Transition layer에 width scaling 적용
- Partial 부분도 width scaling 적용

(c)를 통해 초기 디자인에서 모델이 가졌던 특징과 최적의 구조를 유지할 수 있음
