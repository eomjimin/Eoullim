# 👶 챗쪽이
##### 나와 배우자의 성격을 기반으로 생성되는 AI 챗봇
###### 인원: 5명
###### 기간: 2024-01-12 ~ 2024-02-20
-----------------
## 💡 프로젝트 기획
한 가정에 한 아이만 낳는 시대에, 그 하나뿐인 아이에 대한, 부모님들의 기대와 관심은, 더욱 높아지고 있습니다. 
이런 관심들을 자극하는 아이의 미래 얼굴을 예측 서비스나, 미래 기질을 예상해주는 상품들도 굉장히 많은 인기를 끌고 있습니다.
저희 팀은 이런 사실을 이용하여 부모로서, 미래의 자녀에 대한 상상을 충족하고 궁금증을 해소할 수 있는 앱을 구현해보았습니다.



<hr>

## 👪 Process & Role
#### Overall Process
###### - 기획, 데이터 작성, 모델학습, 프론트구현, 서버구현, 서버배포, PPT제작, 발표
#### 😺 My Role
###### - 기획, 데이터 작성, 모델학습, PPT제작, 발표

## 🌏 Dataset & Model
#### Dataset
- 일상 질문900개에 성격별로 각 다른 대답 작성
- 성격은 5개의 카테고리로 총 10개.
- 느긋/급함, 내향/외향, 낙천/불안, 고집/우유부단, 이성적/감성적
- 총 9000개의 질문-대답 형식의 데이터셋 작성
  
  ![image](https://github.com/junyealim/chatbot/assets/149549323/86e44e68-d011-4d66-9e17-e7a44106057a)


#### Model 🚀
- 문장 학습 모델
- GPT2LMHeadModel.from_pretrained(skt/kogpt2-base-v2)
- GPT2LMHeadModel 클래스에서 사전 훈련된 'skt/kogpt2-base-버전2' 모델을 불러옴

  ![image](https://github.com/junyealim/chatbot/assets/149549323/08f00f2b-d7a1-4d32-b6ad-d3d9f6a84762)


<br>
<br>

-----------------  
# **앱설명 🎨**
![image](https://github.com/junyealim/chatbot/assets/149549323/2a3785ff-9eee-4bb2-af0c-7340e9bac549)

![image](https://github.com/junyealim/chatbot/assets/149549323/76f95223-ea5d-45db-9a27-ac39be2eac87)

![image](https://github.com/junyealim/chatbot/assets/149549323/faea03f6-ef1a-461c-b778-c3261e05af25)

![image](https://github.com/junyealim/chatbot/assets/149549323/3ac50e36-1635-497a-a628-16f778036415)


-----------------
## 🌈 Result

![image](https://github.com/junyealim/chatbot/assets/149549323/d40691aa-a602-43fc-8b17-1bd1f8db6755)

- 성격별로 다른 대답이 생성됨.
- 반반으로 골고루 선택된 성격은 가중치를 줄이고 한쪽으로 선택이 쏠린 성격의 출력 가중치를 높히는 알고리즘을 생성.
- 사용자가 선택한 성격이 적절히 섞여서 대답이 출력됨.

-----------------
### ⚙️ Skills & Tools

<p>
  <img src="https://img.shields.io/badge/PyTorch-EE4C2C?style=flat&logo=pytorch&logoColor=white"/>&nbsp;&nbsp;
  <img src="https://img.shields.io/badge/HTML5-E34F26?style=flat&logo=html5&logoColor=white"/>&nbsp;&nbsp;
  <img src="https://img.shields.io/badge/CSS3-1572B6?style=flat&logo=css3&logoColor=white"/>&nbsp;&nbsp;
  <img src="https://img.shields.io/badge/JavaScript-gray?style=flat&logo=JavaScript&logoColor=F7DF1E"/>&nbsp;&nbsp;
  <img src="https://img.shields.io/badge/FastAPI-009688?style=flat&logo=fastapi&logoColor=4479A1"/>&nbsp;&nbsp;
</p>

<p>
  <img src="https://img.shields.io/badge/Colab-F37626?style=flat&logo=googlecolab&logoColor=white"/>&nbsp;&nbsp;
  <img src="https://img.shields.io/badge/VScode-007ACC?style=flat&logo=visualstudiocode&logoColor=white"/>&nbsp;&nbsp;
  <img src="https://img.shields.io/badge/Discord-5865F2?style=flat&logo=Discord&logoColor=white"/>&nbsp;&nbsp;
  <img src="https://img.shields.io/badge/AWSEC2-FF9900?style=flat&logo=amazonec2&logoColor=white"/>&nbsp;&nbsp;
  <img src="https://img.shields.io/badge/AWSS3-569A31?style=flat&logo=amazons3&logoColor=white"/>&nbsp;&nbsp;

  
</p>
