# 👋 어울림

![image](https://github.com/eomjimin/Eoullim/assets/68543910/31a97f46-7ca6-43c3-b8a6-74527ac4eb82)
##### 실시간 농인과 비장애인 간의 소통 지원 어플
###### 인원: 4명
###### 기간: 2024-02-26 ~ 2024-03-07

-----------------

## 👨‍💻 Process & Role
#### Overall Process
- 기획, 서버구현, 프론트구현, 모델학습, PPT제작, 발표, 데이터수집
#### 😺 My Role
- 기획
  - 아이디어 제시와 어플리케이션의 전체적인 방향성, 기능과 구현을 기획
- 논문 조사
  - 이전의 수어 모델 학습을 진행한 선례를 조사
  - YOLO 모델을 사용한 학습과 CNN 모델을 사용한 학습 두가지 방식을 제안
- 서버 구현
  -  Python Flask를 이용하여 서버 구현
  - 구현한 서버에서 리액트 네이티브로 데이터 전송
  - 프론트에서 전달받은 영상을 모델에 넣어 GPT API에 돌려 자연스럽게 문장 처리 후 프론트로 전달
- 프론트 구현
  - react native를 이용하여 어플리케이션의 메인화면, 카메라연동 작업 진행
  - 카메라를 연동하여 동영상 녹화 및 저장
  - 전달받은 문장을 음성으로 출력
- 모델 학습
  - CNN 방식
    - 기존 ResNet 모델을 커스텀하여 재학습
    - MediaPipe를 이용하여 각 프레임의 keypoint 추출 후 정규화
    - 정규화한 X, Y, 정확도를 색상 좌표로 변환하여 하나의 픽셀에 매핑
    - 생성된 이미지를 모델에 넣어 학습
  - YOLO 방식
    - 하나의 동영상의 각각의 프레임을 이미지화, 각 이미지의 손에 바운딩 박스 삽입 후 뜻 라벨링
    - 전처리한 이미지를 YOLO 모델에 넣어 학습
- PPT 제작
- 데이터 수집
  - AI Hub에서 데이터 다운로드 후 MediaPipe로 프레임 당 키포인트 추출
  - Keypoint와 동영상을 각각 Google Drive에 업로드

-----------------

## 💡 프로젝트 기획
농인과 청인의 의사소통을 편리하게 하기 위한 해결방안을 생각하다 하나의 단말기로 소통할 수 있다면 편리하게 이용할 수 있다고 생각함.
수어는 음성으로, 음성은 텍스트로 번역함으로서 하나의 단말기로 농인과 비장애인이 소통할 수 있도록 하고자 함.
이와 더불어 실시간 수어 번역을 통해 향후 수어를 학습하는 사람에게도 학습에 도움을 줄 수 있다는 확장성도 고려.


<img width="100%" alt="image" src="https://github.com/NVDIII/EoUlim/assets/124571378/17b3748a-604f-4dcd-b88e-6cae5177511a">

<hr>

# **두 가지 데이터로 학습**
영상 데이터와 키포인트 데이터를 각각 다른 방식으로 학습시킴.
- YOLO - 영상
- ResNet - 키포인트

<img width="100%" alt="image" src="https://github.com/NVDIII/EoUlim/assets/124571378/20bf4043-a559-485a-a5bf-787d9f13fa91">

## 🌏 Dataset & Model
#### Dataset
- [AIh-Hub]([https://github.com/moon-123/Matchuri-NLP-project/files/14344362/QADataset.xlsx](https://www.aihub.or.kr/aihubdata/data/view.do?currMenu=&topMenu=&aihubDataSe=data&dataSetSn=103))에서 수어 데이터를 다운로드
- Training : 총 단어 3000개, 각기 다른 사람 16명 분의 데이터가 존재
- Validation: 총 단어 3000개, 각기 다른 사람 2명 분의 데이터가 존재 

#### Model
- 영상 학습 모델 [YOLOv5](https://github.com/ultralytics/yolov5)
- 키포인트 학습 모델 [ResNet](https://wikidocs.net/137252)
- STT [GPT2 API](https://huggingface.co/docs/transformers/model_doc/gpt2)
-----------------
## 🚀 Result

### **발표ppt**
[어울림 ppt](Eoullim.pdf)


### **YOLOv5**
- 데이터 전처리
- 영상을 최대한 수어 뜻과 관련있는 부분만 따로 추려내어 프레임별로 쪼개어 이미지로 저장
- 수어 데이터를 뜻 별로 클래스로 구분하여 라벨데이터를 만듦.
- YOLOv5 모델에 학습시키기 위해 위 과정을 바탕으로 YAML 파일 생성
<img width="100%" alt="image" src="https://github.com/NVDIII/EoUlim/assets/124571378/b1837d3c-4f09-41bf-8d76-173b2ae93df7">

- 전처리한 데이터를 모델에 학습
<img width="100%" alt="image" src="https://github.com/NVDIII/EoUlim/assets/124571378/625aa3f6-29f6-4d45-a7ce-d000b72b3b31">

### **ResNet**
- 시공간지도사상기법을 통해 데이터를 학습
- Mediapipe를 이용하여 이미지 별 keypoint를 추출
- keypoint를 정규화 후 컬러이미지로 변환

<img width="100%" alt="image" src="https://github.com/NVDIII/EoUlim/assets/124571378/bd305744-a34e-4ebb-8d5c-bdc1f36d950e">
<img width="100%" alt="image" src="https://github.com/NVDIII/EoUlim/assets/124571378/ebbbe2dc-8e97-49c5-847d-8d8b5f5cc9b8">
<img width="100%" alt="image" src="https://github.com/NVDIII/EoUlim/assets/124571378/53927064-2fcb-44c4-bab3-e3be80dfb4a4">

- ResNetCustom Class객체를 만들어 학습

<img width="100%" alt="image" src="https://github.com/NVDIII/EoUlim/assets/124571378/600ce4de-735c-4e29-94d0-36f33117d346">

### **최종 선택 모델**
- 더 정확도가 높은 ResNet 모델(Keypoint)을 최종적으로 선택함.

<img width="100%" alt="image" src="https://github.com/NVDIII/EoUlim/assets/124571378/248519a2-f0e3-4bf2-9090-e9ac6c04b095">

### **모델로 뽑은 단어를 자연어 처리 모델에서 처리**
- GPT2 API를 활용하여 텍스트 처리 된 수어를 자연스럽게 처리
<img width="100%" alt="image" src="https://github.com/NVDIII/EoUlim/assets/124571378/0d25fb8e-923d-4061-b663-6103d3c64355">

-----------------
### ⚙️ Skills & Tools

<p>
  <img src="https://img.shields.io/badge/python-3776AB?style=flat-square&logo=python&logoColor=white"/>
  <img src="https://img.shields.io/badge/React-61DAFB?style=flat-square&logo=react&logoColor=white"/>
  <img src="https://img.shields.io/badge/openai-412991?style=flat&logo=openai&logoColor=white"/>&nbsp;&nbsp;
  <img src="https://img.shields.io/badge/opencv-5C3EE8?style=flat&logo=opencv&logoColor=white"/>&nbsp;&nbsp;
  <img src="https://img.shields.io/badge/CSS3-1572B6?style=flat&logo=css3&logoColor=white"/>&nbsp;&nbsp;
  <img src="https://img.shields.io/badge/JavaScript-gray?style=flat&logo=JavaScript&logoColor=F7DF1E"/>&nbsp;&nbsp;
  <img src="https://img.shields.io/badge/FastAPI-009688?style=flat&logo=fastapi&logoColor=4479A1"/>&nbsp;&nbsp;
</p>

<p>
  <img src="https://img.shields.io/badge/Colab-F37626?style=flat&logo=googlecolab&logoColor=white"/>&nbsp;&nbsp;
  <img src="https://img.shields.io/badge/VScode-007ACC?style=flat&logo=visualstudiocode&logoColor=white"/>&nbsp;&nbsp;
</p>
