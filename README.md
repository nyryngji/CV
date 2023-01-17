## 영상을 화면에 출력하기

- **cv2.imread(사진이름)** : 사진 및 영상 파일 불러오기
- **cv2.imshow(창 이름, 출력할 이미지 데이터)** : 사진 및 영상을 화면에 띄우기
- **cv2.waitKey()** : 사용자로부터 키보드 키 입력 받기 
- **cv2.destroyAllWindows()** : 프로그램 동작 중 창을 닫고 싶을 때 사용

>
    img = cv2.imread('lenna.bmp')
    cv2.namedWindow('image') 
    cv2.imshow('image',img) 
    cv2.waitKey() 
    cv2.destroyAllWindows()


<img src="https://user-images.githubusercontent.com/105197496/212924366-241c0c7b-e2ac-4790-9184-72f6283205a7.png" width=385px height=410px>
