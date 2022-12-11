Cosine warmup scheduler를 통해서 적절하게 학습하면 Step scheduler보다 좋은 성능을 냄

- lr이 연속적으로 조정되기 때문에 Step decay의 plateau 현상을 덜 겪는다.

### Step decay의 plateau 현상

- step decay: lr을 특정 step마다 줄이는 방법
- plateau: 평지
- validation 성능이 lr이 줄어들기 전까지 진전이 없는 현상을 말함
