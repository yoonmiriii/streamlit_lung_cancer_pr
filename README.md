![waving](https://capsule-render.vercel.app/api?type=waving&height=200&text=Predict_Lung_cancer&fontAlign=50&fontAlignY=40&color=gradient)

# 파일이름 : lung_cancer_pr
> ## 국내 암 사망율 1위인 폐암 가능성을 예측해 보자.

 ### :warning: 폐암의 원인과 전조증상에 따른 암 발생 데이터를 기반으로 나의 현재상태로는 암 발생 가능성이 있는지 예측해보자.

 ### :ambulance: 머신러닝을 통해 인공지능을 개발하여 암 가능성을 예측하고, Streamlit으로 웹 대시보드를 만들었습니다.

 기사 출처 

 :smoking:현재 국내 암사망율 1위는 폐암이라고 한다. 이전에 폐암은 흡연자만 걸린다고 알고 있었지만, 요즘 들어 비흡연자들도 폐암으로 사망하는 경우가 많은 것을 볼 수 있다. 폐암은 초기 증상이 없어서 발견하기가 더욱 힘든데, 내 몸에 나타나는 여러 증상들을 통해 폐암 가능성이 있는지 예측해 보자.



:pencil: 작업순서<br>
    데이터 주제 선정 ➡︎ 데이터 가공(주피터노트북) ➡︎ Streamlit 프레임워크 웹 대시보드 개발 ➡︎ AWS EC2 배포


:pencil: 데이터 가공<br>
    - 데이터 파일(.csv)을 판다스 라이브러리를 이용하여 읽인 후 데이터분석을 했습니다.<br> 
    - str 데이터를 skleran 라이브러리의 LabelEncoder를 이용하여 컴퓨터가 읽을 수 있는 int 데이터로 변경함.<br>
    - 머신러닝 학습을 위해 데이터를 train과 test로 나누고, test 사이즈는 20%로 할당함.<br>
    - 머신러닝 논리회귀인 LogisticRegression으로 학습함.<br>
    - os 모듈로 새 디렉토리 생성 및 joblib 라이브러리로 예측데이터(.pkl) 생성함.<br>
    - mse = 0.027, accuracy_score = 0.87 의 비교적 정확성이 높은 머신러닝 구축함.<br>
    - histogram으로 연령별 폐암 환자수를 나타냄. <br>
    - 증상별 폐암 환자 분포도를 matplotlib의 pie차트로 나타냄.<br>    


:pencil: 스트림릿 웹 대시보드 개발<br>
    APP<br>
    - 사이드바를 통해서 웹 대시보드의 카테고리를 표시함.<br>
    - 사이드바 streamlit_option_menu 로 업그레이드함.<br>
    - streamlit_option_menu는 파이썬에 기본 라이브러리가 아니여서, cmd에서 pip install streamlit_option_menu로 설치함.<br>
    HOME <br>
    - 프로젝트 계기가 된 기사 출처 표시.<br>
    - 사용한 데이터 출처 표시.<br>
    - 프로젝트 내용 게시함.<br>
    REASON<br>
    - 스트림릿 라이브러리 데이터를 데이터프레임으로 노출함.<br>
    - 버튼 함수를 사용하여 연령별 폐암 환자수 그래프를 볼 수 있도록 함.<br>
    - 셀렉트박스 함수로 확인하고 싶은 데이터 컬럼을 선택할 수 있도록 함.<br>
    - 증상별 폐암 환자 분포는 matplotlib의 pie 차트로 나타냄.<br>
    ML<br>
    - 예측자의 성별 및 증상이 있는지 여부는 라디오 함수로 선택할 수 있도록 함.<br>
    - 나이는 넘버인풋 함수로 기재할 수 있도록 함.<br>
    - 선택한 데이터를 바탕으로 폐암 가능성이 있으면 warning 메시지로 표시함.<br>
    - 선택한 데이터를 바탕으로 폐암 가능성이 없다면 info 메시지로 표시함.<br>


:pencil: 배포<br>
    - AWS EC2 프리티어를 사용했습니다.


