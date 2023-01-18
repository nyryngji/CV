## Contract(명암비) 조절하기 

> **Contract** 

- 명암비 : 영상 내 밝은 영역과 어두운 영역 사이에 드러나는 밝기 차이의 강도 

  - 명암비가 높으면 영상이 선명해보임 
  - 밝은 영역과 어두운 영역이 섞여있으면 명암비가 높다고 말함 
  
- 명암비 조절 수식 : **dst(x,y) = saturate(src(x,y) + (src(x,y)-128) * alpha)**

  - alpha에 의해 기울기가 변경 
  - 0 <= a <= 1 : 명암비를 감소 
  - 0 < a : 명암비 증가

- **np.clip(배열, 최솟값, 최댓값)** : saturate(포화 연산 수행) 
- **astype()** : 데이터프레임 타입 변경 

  - uint8(unsigned integer) : 0이상의 양수로 표현 

>
    import cv2
    import numpy as np

    src = cv2.imread('lenna.bmp', cv2.IMREAD_GRAYSCALE)
    
    alpha = 0.5
    dst = np.clip(src + (src-128.)*alpha, 0, 255).astype(np.uint8)

    cv2.imshow('source', src)
    cv2.imshow('destination', dst)
    cv2.waitKey()
    cv2.destroyAllWindows()
    
|Before|After(명암비 증가)|
|:---:|:---:|
|<img src="https://user-images.githubusercontent.com/105197496/213227144-f774e776-cb21-4a3b-9447-ee186ba802c9.png" width=256px height=256px>|<img src="https://user-images.githubusercontent.com/105197496/213227184-1b8dbaee-87c8-4314-bd50-0fd9eb2cfd03.png" width=256px height=256px>|
