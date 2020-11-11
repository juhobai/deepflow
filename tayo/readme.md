<h2>주차관제 시스템 구축 프로젝트 입니다.</h2>
0. 학습 매뉴얼 참조 할것 (링크)

```
https://software.intel.com/content/www/us/en/develop/download/license-plate-recognition-using-lprnet-model.html
https://software.intel.com/content/dam/develop/public/us/en/documents/license-plate-recognition-using-training-toolbox-0.pdf
```
-버전이 달라졌을수도 있음-
0-1 번호판 사진의 좌 하단의 번호판 부분만 크롭해서 파일이름을 번호판 이름으로 작성하여 데이터셋을 구성할것.

입력 사이즈는 

>> input_shape = (24, 94, 3) 픽셀 24x94 RGB 로 할것.

A. 해당 코드에서 아웃풋 부분의 문자에 한글 번호판의 글자 내용을 적어주거나 한국어 번호판 파일을 새로 만들어서 컨피겨에 한글을 넣음 됨.

```
https://github.com/openvinotoolkit/training_extensions/tree/develop/tensorflow_toolkit/lpr/chinese_lp
```

-- 해당 폴더내의 파일 config.py config_test.py 2개 에서 아래 부분이 패턴 분류입니다.
```
# Licens plate patterns
lpr_patterns = [
  '^<[^>]*>[A-Z][0-9A-Z]{5}$',
  '^<[^>]*>[A-Z][0-9A-Z][0-9]{3}<police>$',
  '^<[^>]*>[A-Z][0-9A-Z]{4}<[^>]*>$',  # <Guangdong>, <Hebei>
  '^WJ<[^>]*>[0-9]{4}[0-9A-Z]$',
]
```

B. 학습 설명 매뉴얼(그대로 따라하면됨, 버전은 16.x로 되어있는데 18.x도 돌아갔음) 

```
https://github.com/openvinotoolkit/training_extensions/tree/develop/tensorflow_toolkit/lpr
```


아래는 장치 셋팅 방법 : 씨퓨로만 해도 되고 라즈베리에 GPUstick을 써도 됨.(성능상 큰차이 없음) 


1. 우분투 18.04 버전 설치 , 상위 버전 설치시 2번 항 제대로 설치 안됨
2. openvino 설치
```
https://docs.openvinotoolkit.org/latest/_docs_install_guides_installing_openvino_linux.html
```
3. cmake 설치
4. 기타 요구사항 설치후 데모 테스트
```
https://docs.openvinotoolkit.org/2018_R5/_samples_security_barrier_camera_demo_README.html
````
5. 카메라 드라이버 설치
```
https://www.christitus.com/logitech-c920-linux-driver/
``` 

   > 카메라 장치 경로 확인
```
https://askubuntu.com/questions/348838/how-to-check-available-webcams-from-the-command-line
```
6. 아나콘다 설치
7. 콘다 환경 셋팅
```
conda create --name tayo tensorflow-gpu
``` 
8. opencv 설치
```
conda install -c conda-forge opencv
```
9. 깃 셋팅
```
https://github.com/PINTO0309/OpenVINO-YoloV3
```

