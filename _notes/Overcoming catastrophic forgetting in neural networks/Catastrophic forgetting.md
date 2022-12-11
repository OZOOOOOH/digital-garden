Pretrained model이 transfer learning을 할 때 pretrained dataset에 대한 기억을 잊어버린다.

## Example

1. A라는 모델이 MNIST Dataset에 대해서 학습했다.
2. SVHN Dataset에 대해서 다시 fine tuning 했다.
3. 모델 A의 MNIST Dataset에 대한 분류 성능은 보장되지 않는다.
4. 결국 모델 A는 MNIST Dataset에 대한 기억을 잊어버린 것이다.
