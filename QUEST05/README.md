# AIFFEL Campus Online 5th 수Code Peer Review Templete
- 코더 : 박혜원
- 리뷰어 : 조대호


# PRT(PeerReviewTemplate) 
각 항목을 스스로 확인하고 토의하여 작성한 코드에 적용합니다.

- [Δ] 코드가 정상적으로 동작하고 주어진 문제를 해결했나요?
  > 평가 문항 3가지 중 1번인 배경 이미지 변경 문제는 해결하였지만, 나머지2,3번에 대한 문제는 해결하지 못했습니다.
- [O] 주석을 보고 작성자의 코드가 이해되었나요?
  > 필요한 부분에 주석을 작성해주셔서 이해하는데 도움이 되었습니다.
- [O] 코드가 에러를 유발할 가능성이 없나요?
  >코드를 실행해본 결과 에러가 발생하지 않아 유발할 가능성은 없어 보입니다.
- [O] 코드 작성자가 코드를 제대로 이해하고 작성했나요?
  > 필요한 부분에 주석을 달아주셔서 코드를 이해하고 있다고 생각합니다.
- [O] 코드가 간결한가요?
  > 아래 예시에 나오는 배경 이미지 변경하는 코드를 함수화 하여 작성하였습니다.

# 예시
1. 코드의 작동 방식을 주석으로 기록합니다.
2. 코드의 작동 방식에 대한 개선 방법을 주석으로 기록합니다.
3. 참고한 링크 및 ChatGPT 프롬프트 명령어가 있다면 주석으로 남겨주세요.
```python
#배경 이미지 변경에 대한 함
def shallow_focus_chromakey(img, deepLab_label, background):
    img_path = os.getenv('HOME') + f'/aiffel/human_segmentation/images/{img}'
    img_orig = cv2.imread(img_path) 
    
    # Semantic segmentation DeepLab
    
    # 준비한 이미지를 네트워크에 입력
    model = semantic_segmentation()
odel_file)
    model.load_pascalvoc_model(m    segvalues, output = model.segmentAsPascalvoc(img_path)
    
    # 라벨 이름
    LABEL_NAMES = [
    'background', 'aeroplane', 'bicycle', 'bird', 'boat', 'bottle', 'bus',
    'car', 'cat', 'chair', 'cow', 'diningtable', 'dog', 'horse', 'motorbike',
    'person', 'pottedplant', 'sheep', 'sofa', 'train', 'tv'
    ]
    # 삭제예정
    plt.figure(figsize=(15,20))
    
    plt.subplot(2,3,1)
    plt.imshow(output)
    plt.title('Extracting labeled object areas')
    
    # 라벨 조회
    label = LABEL_NAMES.index(deepLab_label)
    
    # 색상코드 BGR -> RGB 목적
    colormap = np.zeros((256, 3), dtype = int)
    ind = np.arange(256, dtype=int)

    for shift in reversed(range(8)):
        for channel in range(3):
            colormap[:, channel] |= ((ind >> channel) & 1) << shift
        ind >>= 3

    seg_color = tuple(colormap[label][::-1])
    
    
    # output의 픽셀 별로 색상이 seg_color와 같다면 1(True), 다르다면 0(False)이 됩니다
    seg_map = np.all(output==seg_color, axis=-1)
    ...


shallow_focus_chromakey('img1.jpg', 'person', 'stars.jpg')
```

# 참고 링크 및 코드 개선
```python
# 코드 리뷰 시 참고한 링크가 있다면 링크와 간략한 설명을 첨부합니다.
# 코드 리뷰를 통해 개선한 코드가 있다면 코드와 간략한 설명을 첨부합니다.

#잘못 블러 처리된 부분 동그라미로 표시하기
#step2에서 인물사진을 비교하고 잘못된 부분을 찾아서 표시하는 문제에서 잘못된 부분의 위치를 정하고
# 그 부분에 원을 그려 표시하는 코드입니다.
circle = plt.Circle((780, 470), radius=30, edgecolor='red', facecolor='none',linewidth=3)
plt.gca().add_patch(circle)
circle = plt.Circle((620, 530), radius=30, edgecolor='yellow', facecolor='none',linewidth=3)
plt.gca().add_patch(circle)
plt.show()
```
