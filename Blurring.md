## Blurring(블러링)

> **Blurring**

- 초점이 맞지 않는 사진처럼 영상을 부드럽게 만듦
<br>

> **평균값 필터**

- 평균값 필터 : 행렬의 전체 원소 개수로 각 행렬 원소 값을 나눔 
  
  - 마스크의 크기가 커질수록 부드러운 느낌 증가 but 연산량 증가 가능성 존재 

- **cv2.blur(입력 영상, (블러링 커널 크기, 블러링 커널 크기))** : 평균값 필터링 수행

- **cv2.putText(창 이름, 문자열, 문자열 위치, 글자 폰트 지정, 폰트 사이즈, 글자 색, 글자 굵기, cv2.LINE_AA)** : 창에 글자 띄우기

>
    import cv2
    src = cv2.imread('bears.jpg', cv2.IMREAD_GRAYSCALE)

    for ksize in (3,5,7):
        dst = cv2.blur(src, (ksize, ksize))
        txt = 'Mean : (%d x %d)' % (ksize, ksize)
        cv2.putText(dst, txt, (10,30), cv2.FONT_HERSHEY_SIMPLEX, 1.0, 255,1,cv2.LINE_AA)
        cv2.imshow('dst', dst)
        cv2.waitKey()

    cv2.destroyAllWindows()
<br>

|ksize=3|ksize=5|ksize=7|
|:---:|:---:|:---:|
|<img src="https://user-images.githubusercontent.com/105197496/213210540-5a1263ee-67db-4896-b1ed-a698ed0e3b9c.png" width=282px height=269px>|<img src="https://user-images.githubusercontent.com/105197496/213210944-63237fb4-66d3-40bc-a826-73182cee3253.png" width=282px height=269px>|<img src="https://user-images.githubusercontent.com/105197496/213211412-76d0ec5a-082f-4cad-a081-e032f8020bc9.png" width=282px height=269px>|


