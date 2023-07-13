# AIFFEL Campus Online 5th Code Peer Review
- 코더 : 박혜원
- 리뷰어 : 김민식


# PRT(PeerReviewTemplate)
각 항목을 스스로 확인하고 토의하여 작성한 코드에 적용합니다.

- [O] 코드가 정상적으로 동작하고 주어진 문제를 해결했나요?
  > 네. 노드에서 언급한 내용을 모두 수행하였습니다.
- [O] 주석을 보고 작성자의 코드가 이해되었나요?
  > opencv와 matplotlib, dlib 간의 채널 차이를 잘 설명해주셔서 BGR2RGB처리에 대한 과정이 이해됩니다.
  > 고양이수염을 코 위치에 적용시킬때 68 landmark 모델의 번호로 어느 위치에 적용하면 좋을지 잘 설명해주셨습니다.

- [O] 코드가 에러를 유발할 가능성이 없나요?
  > 네. 각각의 단게에서 작성자의 의도대로(ex: 코드 주석) 코드가 잘 수행되었습니다.
- [O] 코드 작성자가 코드를 제대로 이해하고 작성했나요?
  > 네. 얼굴 측면에서부터 스티커 이미지를 어떻게 적용할지에 대한 설명이 자세히 있었습니다.
- [O] 코드가 간결한가요?
  > 네. 얼굴 정면 | 얼굴 측면 | 다른 사진(어둡거나 서있는 사람) 에 대해 각각 코드로 실제 테스트를 해준 부분이 좋았습니다.

# 예시
- 개인적으로는 랜드마크 인덱스를 찍어서 사진에 표시할 생각을 하지 않았는데, 표시해 주신 부분이 좋았습니다.
- 이후 다른 모델로 랜드마크 테스트 할때도 이렇게 확인해보고 하는 것이 좋다는 생각이 들었습니다.
```python
# 코드 앞부분 생략
# landmark에 index 추가
for landmark in list_landmarks:
    for index, point in enumerate(landmark):
        cv2.putText(image_show_text, str(index), point, fontScale=0.35, color=(0, 255, 255), fontFace = cv2.FONT_HERSHEY_SCRIPT_SIMPLEX)

plt.subplot(1,3,3)
plt.imshow(image_show_text[top:top+(bottom-top),left:left+(right-left)])
plt.title('The Number of Landmarks')
plt.axis('off')

plt.show()
```

# 참고 링크 및 코드 개선
```python
# 코드 리뷰 시 참고한 링크가 있다면 링크와 간략한 설명을 첨부합니다.
# 코드 리뷰를 통해 개선한 코드가 있다면 코드와 간략한 설명을 첨부합니다.
```


