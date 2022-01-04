# 

## CNN

![image](https://user-images.githubusercontent.com/37800546/148029367-009d312b-f76e-4ebb-a0d0-02b3c55a9d24.png)

- Pooling layer는 학습하는 parameter가 없음 (값만 뽑는 것이므로) + noize 제거 효과


- output size 계산: (이미지 크기 - 필터 크기) / stride + 1

<details>
<summary> 3x3 필터 3개를 중첩하는 것과 7x7 필터 하나를 사용하는 것 중 더 좋은 것은? </summary>

    3x3 필터 여러개를 쓰는 것이 더 좋다

    필터 중간 단계에 있는 non-linearity를 더 많이 활용할 수 있음

    연산량 또한 적어짐

    3x3 필터 3개를 사용하면, 3*3*3 = 27개의 weight을 학습

    7x7 필터 1개를 사용하면, 7*7 = 49개의 weight을 학습

![image](https://user-images.githubusercontent.com/37800546/148028008-e22ee20b-bd1c-4c69-84cb-5b2c253db6a4.png)  
</details>

<details>
<summary> Stride 1에 pooling을 적용하는 방식과 stride를 크게 하는 방식의 차이는? </summary>
    
    Stride를 1로 설정하는 경우에는, pooling을 통해 값을 선택적으로 고를 수 있지만
  
    stride를 크게하는 경우에는 픽셀을 크게 건너뛰게 되면서 값을 선택할 기회가 사라짐
  
    -> 통상적으로 stride는 1로, pooling을 통해 sub sampling하는 것이 더 좋은 결과를 보여줌
  
    * 크기가 큰 영상의 경우 연산량을 줄이기 위해 입력 영상을 처리하는 첫번째 covolutional layer에서 stride 값을 1이 아닌 값으로 적용하기도 함
    
</details>

<details>
<summary> Zero padding을 하는 이유 </summary>
     
    - 입력 데이터와 동일하게 크기 유지 가능
  
      e.g) 32x32의 입력 데이터, zero padding 2 픽셀, 5x5 필터
  
      보정된 입력 데이터: (2+32+2)x(2+32+2) = 36x36
  
      출력 데이터: (36 - 5 +1)x(36 - 5 +1) = 32x32
    
      * Padding 사이즈 = (Filter 사이즈 - 1) / 2 로 설정하면 크기를 동일하게 유지 가능
  
    - 경계면의 정보 살릴 수 있음
    
</details>


