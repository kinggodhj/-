# 

## CNN

<details>
<summary> 3x3 필터 3개를 중첩하는 것과 7x7 필터 하나를 사용하는 것 중 더 좋은 것은? </summary>

  3x3 필터 여러개를 쓰는 것이 더 좋다

  필터 중간 단계에 있는 non-linearity를 더 많이 활용할 수 있음
  
  연산량 또한 적어짐
  
  3x3 필터 3개를 사용하면, 3*3*3 = 27개의 weight을 학습
  
  7x7 필터 1개를 사용하면, 7*7 = 49개의 weight을 학습
  
  ![image](https://user-images.githubusercontent.com/37800546/148028008-e22ee20b-bd1c-4c69-84cb-5b2c253db6a4.png)
  
</details>

- ㄹㄹ
