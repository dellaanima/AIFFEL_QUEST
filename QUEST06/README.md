# AIFFEL Campus Online 5th Code Peer Review Templete
- 코더 : 박혜원
- 리뷰어 : 이효겸


# PRT(PeerReviewTemplate) 
각 항목을 스스로 확인하고 토의하여 작성한 코드에 적용합니다.

- [X] 코드가 정상적으로 동작하고 주어진 문제를 해결했나요?
  
- [X] 주석을 보고 작성자의 코드가 이해되었나요?
  > 주석이 잘 작성되어 있어 코드가 잘 이해 되었습니다.
- [X] 코드가 에러를 유발할 가능성이 없나요?
  > 에러가 발생할 가능성은 없어 보입니다.
- [X] 코드 작성자가 코드를 제대로 이해하고 작성했나요?
  > 코드가 단계별로 잘 정리되고 단락이 잘 되어서 제대로 이해하고 작성된걸로 확인이 됩니다.
- [X] 코드가 간결한가요?
  > 코드가 복잡할 곳이 없었기도 하였지만 아래와 같이 변수 선언 후 사용한 부분이 깔끔하였습니다.
```python
threshold = 8
total_cnt = len(src_tokenizer.word_index) # 단어의 수
rare_cnt = 0 # 등장 빈도수가 threshold보다 작은 단어의 개수를 카운트
total_freq = 0 # 훈련 데이터의 전체 단어 빈도수 총 합
rare_freq = 0 # 등장 빈도수가 threshold보다 작은 단어의 등장 빈도수의 총 합
```

# 예시
1. 코드의 작동 방식을 주석으로 기록합니다.
2. 코드의 작동 방식에 대한 개선 방법을 주석으로 기록합니다.
3. 참고한 링크 및 ChatGPT 프롬프트 명령어가 있다면 주석으로 남겨주세요.

# 참고 링크 및 코드 개선
```python
코드 작성부터 주석, 리뷰까지 잘 정리되어 있습니다.
```