# AIFFEL Campus Online 5th Code Peer Review
- 코더 : 박혜원
- 리뷰어 : 조대호


# PRT(PeerReviewTemplate)
각 항목을 스스로 확인하고 토의하여 작성한 코드에 적용합니다.

- [O] 코드가 정상적으로 동작하고 주어진 문제를 해결했나요?

- [O] 주석을 보고 작성자의 코드가 이해되었나요?
  > 헷갈리는 부분은 혜원님에게 물어봐서 해결하였습니다.
- [O] 코드가 에러를 유발할 가능성이 없나요?
  > 실행 해본 결과 모두 오류없이 작동하는것을 확인했습니다
- [O] 코드 작성자가 코드를 제대로 이해하고 작성했나요?
  > 제가 헷갈리는 부분을 질문을 드렸을 때 설명을 잘해주셨습니다.
- [O] 코드가 간결한가요?
  > 네. 거기다 시각화를 잘해주셔서 이해하는데 더 도움이 되었습니다.

# 예시
1. 코드의 작동 방식을 주석으로 기록합니다.
2. 코드의 작동 방식에 대한 개선 방법을 주석으로 기록합니다.
3. 참고한 링크 및 ChatGPT 프롬프트 명령어가 있다면 주석으로 남겨주세요.
Quest01_1 주석문을 몇줄 추가했습니다
```python
for learning_rate in LEARNING_RATES:
    W = np.random.randn(10)
    b = np.random.randn()
    losses = [] #각 learning rate 마다 마지막 로스값을 저장하는 리스트

    for i in range(1, 10001):
        dW, db = gradient(X_train, W, b, y_train)
        W -= learning_rate * dW
        b -= learning_rate * db
        L = loss(X_train, W, b, y_train)
        losses.append(L)
        if i % 10 == 0:
            print('Iteration %d : Loss %0.4f' % (i, L))

    if losses[-1] < best_loss: #for문에서 결과로 나온 마지막 값과 저장된 가장 낮은 로스값 비교
        best_loss = losses[-1]
        best_learning_rate = learning_rate
        best_W = W
        best_b = b
```

# 참고 링크 및 코드 개선
```python
# 코드 리뷰 시 참고한 링크가 있다면 링크와 간략한 설명을 첨부합니다.
# 코드 리뷰를 통해 개선한 코드가 있다면 코드와 간략한 설명을 첨부합니다.
```


