# Global Batch Normalization

- SimCLR은 positive pair가 같은 device에서 계산됨
- 모델은 표현력을 높이는 것 없이 accuracy를 높이기 위해서 local 정보 leakage를 사용 가능
- 학습하는 동안 모든 device간에 BN mean, variance를 합함
