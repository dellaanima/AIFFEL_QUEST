# AIFFEL Campus Online 5th Code Peer Review Templete
- 코더 : 코더 1인의 이름을 작성하세요.
- 리뷰어 : 본인의 이름을 작성하세요.
- 코더 : 박혜원 (양주영, 조대호)
- 리뷰어 : 맹선재


# PRT(PeerReviewTemplate) 
각 항목을 스스로 확인하고 토의하여 작성한 코드에 적용합니다.

- [O] 코드가 정상적으로 동작하고 주어진 문제를 해결했나요?
  > 동작에 이상 없음, 다양한 조건에 따라 결과가 변화하는 부분도 보여주어 루브릭에서 요구한 내용 이상으로 상세한 결과를 보여주었음
- [O] 주석을 보고 작성자의 코드가 이해되었나요?
  > 블럭 별 어떤 과정을 수행하는지와, 블럭 내의 코드에 달린 주석을 통해 과정을 상세히 설명하였음
- [O] 코드가 에러를 유발할 가능성이 없나요?
  > 시행 상으로는 문제 없었음
- [O] 코드 작성자가 코드를 제대로 이해하고 작성했나요?
  > 조건을 다양하게 주도록 노드 학습 내용에서 변주를 주고, Max length 관련하여 해당 데이터셋 외의 경우에도 적용이 가능토록 한 점을 보아 코드에 대한 이해도가 높다고 생각됨
- [O] 코드가 간결한가요?
  > 불필요한 코드 없음
- [O] 주석을 보고 작성자의 코드가 이해되었나요?

# 예시
Max length 조건 설정
```python
# 정수 인코딩, 최대 길이를 초과하는 샘플 제거, 패딩
def tokenize_and_filter(inputs, outputs):
    tokenized_inputs, tokenized_outputs = [], []
    for (sentence1, sentence2) in zip(inputs, outputs):
        # 정수 인코딩 과정에서 시작 토큰과 종료 토큰을 추가
        sentence1 = START_TOKEN + tokenizer.encode(sentence1) + END_TOKEN
        sentence2 = START_TOKEN + tokenizer.encode(sentence2) + END_TOKEN

        # 최대 길이 40 이하인 경우에만 데이터셋으로 허용
        if len(sentence1) <= MAX_LENGTH and len(sentence2) <= MAX_LENGTH:
            tokenized_inputs.append(sentence1)
            tokenized_outputs.append(sentence2)

    # 최대 길이 40으로 모든 데이터셋을 패딩
    tokenized_inputs = tf.keras.preprocessing.sequence.pad_sequences(
    tokenized_inputs, maxlen=MAX_LENGTH, padding='pre')
    tokenized_outputs = tf.keras.preprocessing.sequence.pad_sequences(
    tokenized_outputs, maxlen=MAX_LENGTH, padding='pre')

    return tokenized_inputs, tokenized_outputs
print("슝=3")
```



# 참고 링크 및 코드 개선
```
# 코드 리뷰 시 참고한 링크가 있다면 링크와 간략한 설명을 첨부합니다.
# 코드 리뷰를 통해 개선한 코드가 있다면 코드와 간략한 설명을 첨부합니다.
```

```python

```

