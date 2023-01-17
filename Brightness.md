## 사진의 밝기 조절 

> **saturate(포화 연산)**

- 행렬의 원소 값을 설정할 때 최솟값, 최댓값의 범위를 넘어가지 않게 원소 값 설정 
- **ex)** 사진 픽셀의 범위는 0-255, 밝기를 더하거나 뺄 때 0~255의 범위를 벗어나지 않게 함 
- cv2.add, cv2.subtract에는 해당 연산 기능 내포
<br>

- cv2.add(사진 데이터, 밝기 정도) : 사진 데이터 + 밝기 정도
- cv2.subtract(사진 데이터, 밝기 정도) : 사진 데이터 - 밝기 정도 

>
    import cv2

    src = cv2.imread('lenna.bmp', cv2.IMREAD_GRAYSCALE)
    dst1 = cv2.add(src, 100) 
    dst2 = cv2.subtract(src, 100) 

    cv2.imshow('source', src)
    cv2.imshow('add', dst1)
    cv2.imshow('subtract', dst2)
    cv2.waitKey()
    cv2.destroyAllWindows()

|Original|+100|-100|
|:--------:|:--------:|:--------:|
|<img src="https://user-images.githubusercontent.com/105197496/212934548-fb556567-1051-4a90-bb2c-147cdf82d896.png" width=256px height=256px>|<img src="https://user-images.githubusercontent.com/105197496/212936212-b2d06197-a399-438a-ba1a-3924f14cdb2f.png" width=256px height=256px>|<img src="https://user-images.githubusercontent.com/105197496/212936252-e1f5fba8-0449-489d-ad07-11d17de968c8.png" width=256px height=256px>|



