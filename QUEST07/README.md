# AIFFEL Campus Online 5th Code Peer Review Templete
- 코더 : 코더 1인의 이름을 작성하세요.
- 리뷰어 : 본인의 이름을 작성하세요.
- 코더 : 양주영 (박혜원, 조대호)
- 리뷰어 : 맹선재


# PRT(PeerReviewTemplate) 
각 항목을 스스로 확인하고 토의하여 작성한 코드에 적용합니다.

- [O] 코드가 정상적으로 동작하고 주어진 문제를 해결했나요?
  > 동작에 이상 없음, Epoch 10회 이상 돌리는 루브릭 부분은 충족하지 못하였으나, 다른 조건을 만족시키기 위해 수정하는 과정에서 시간이 부족하다고 회고에 명시되어 있으므로 시간만 더 주어졌다면 해당 사항도 문제 없었을 것으로 생각됨
- [O] 주석을 보고 작성자의 코드가 이해되었나요?
  > 루브릭 기준에 따라 코드 블럭들을 나누고, 코드마다 주석이 상세하게 달려 이해에 문제가 없었음
- [O] 코드가 에러를 유발할 가능성이 없나요?
  > 시행 상으로는 문제 없었음
- [O] 코드 작성자가 코드를 제대로 이해하고 작성했나요?
  > 주석과 더불어 코드를 간결하게 하는 작업 (class Discriminator(Model) 부분)이 있는 것으로 보아 이해에 문제 없었다고 생각됨
- [O] 코드가 간결한가요?
  > 필요한 코드 외의 코드가 없고, 긴 코드도 더 간단하게 압축하였음
- [O] 주석을 보고 작성자의 코드가 이해되었나요?

# 예시
코드 간략화 작업을 시행한 부분 (class Discriminator(Model))
```python
class Discriminator(Model):
    def __init__(self):
        super(Discriminator, self).__init__()

        '''
        self.block1 = layers.Concatenate()
        self.block2 = DiscBlock(n_filters=64, stride=2, custom_pad=False, use_bn=False, act=True)
        self.block3 = DiscBlock(n_filters=128, stride=2, custom_pad=False, use_bn=True, act=True)
        self.block4 = DiscBlock(n_filters=256, stride=2, custom_pad=False, use_bn=True, act=True)
        self.block5 = DiscBlock(n_filters=512, stride=1, custom_pad=True, use_bn=True, act=True)
        self.block6 = DiscBlock(n_filters=1, stride=1, custom_pad=True, use_bn=False, act=False)
        self.sigmoid = layers.Activation("sigmoid")
        '''
        filters = [64,128,256,512,1]
        self.blocks = [] #layers.Concatenate()은 def call 부분에서 concat으로 결합하였다.


        # For문을 활용해서 DiscBlock을 쌓아주세요.
        # 조건 1 : 3번째까지 stride는 2로 주되 이후에는 1로 주세요
        # 조건 2 : 3번째까지 custom padding을 주지 않아도 되는데 이후에는 주세요.
        # 조건 3: 1번째와 5번째에서는 Batch Normalization을 사용하지 마세요.
        # 조건 4 : 1번째부터 4번째까지 LeakyReLU를 적용하고 마지막에는 sigmoid를 적용하세요. (sigmoid의 경우 따로 정의해야 합니다)
        for i, f in enumerate(filters):
            if i < 3:
                if i == 0:
                    self.blocks.append(DiscBlock(f, stride=2, custom_pad=False, use_bn=False, act=True))
                else:
                    self.blocks.append(DiscBlock(f, stride=2, custom_pad=False, use_bn=True,act=True))
            elif i == 3:
                  self.blocks.append(DiscBlock(f, stride=1, custom_pad=True, use_bn=True, act=True))
            else:
                  self.blocks.append(DiscBlock(f, stride=1, custom_pad=True, use_bn=False,act=False))
        self.sigmoid = layers.Activation("sigmoid")

    def call(self, x, y):
        '''
        out = self.block1([x, y])
        out = self.block2(out)
        out = self.block3(out)
        out = self.block4(out)
        out = self.block5(out)
        out = self.block6(out)
        return self.sigmoid(out)
        '''

    def call(self, x, y):
        out = tf.concat([x, y], axis=-1)  # 입력 데이터를 합칩니다.
        for block in self.blocks:
            out = block(out)
        return self.sigmoid(out)


    def get_summary(self, x_shape=(256,256,3), y_shape=(256,256,3)):
        x, y = Input(x_shape), Input(y_shape)
        return Model((x, y), self.call(x, y)).summary()

print("✅")
```



# 참고 링크 및 코드 개선
```
# 코드 리뷰 시 참고한 링크가 있다면 링크와 간략한 설명을 첨부합니다.
# 코드 리뷰를 통해 개선한 코드가 있다면 코드와 간략한 설명을 첨부합니다.
```

```python

```

