# 서울 일정 계획 웹 사이트 제작기
---
# 프로젝트 소개
### 직접 가본곳 위주로 지도에 정리하여 일정짜기 쉽게 하기위하여 만들어보았습니다.
---
# 환경
<img src="https://img.shields.io/badge/Python 3.8-3776AB?style=for-the-badge&logo=Python&logoColor=white" width="80" height="25"> <img src="https://img.shields.io/badge/Linux-FCC624?style=flat&logo=Linux&logoColor=white" width="80" height="25"/> <img src="https://img.shields.io/badge/ubuntu 20.04-E95420?style=for-the-badge&logo=ubuntu&logoColor=white" width="80" height="25"> <img src="https://img.shields.io/badge/Django-092E20?style=flat&logo=Django&logocolor=white" width="80" height="25"> <img src="https://img.shields.io/badge/PostgreSQL-4169E1?style=flat&logo=PostgreSQL&logocolor=white" width="80" height="25">


<details>
  <summary>과정</summary>
    <div markdown="1">
        django 설치후
        templates 폴더를 생성해주었다 이 폴더에 들어있는 html 파일이 웹 화면에 출력된다 (아마도)<br>그리고 이 생성된 폴더의 html 파일을 활용하기위해서는 se_pro/setting.py 파일의 코드를 수정해주어야한다
        <pre>
<code>
TEMPLATES = [
    {
        'BACKEND': 'django.template.backends.django.DjangoTemplates',
        'DIRS': [],
        'APP_DIRS': True,
        'OPTIONS': {
            'context_processors': [
                'django.template.context_processors.debug',
                'django.template.context_processors.request',
                'django.contrib.auth.context_processors.auth',
                'django.contrib.messages.context_processors.messages',
            ],
        },
    },
]
# 위와 같은 코드를 아래와 같이 바꿔준다
TEMPLATES = [
    {
        'BACKEND': 'django.template.backends.django.DjangoTemplates',
        'DIRS': [os.path.join(BASE_DIR,'templates')],
        'APP_DIRS': True,
        'OPTIONS': {
            'context_processors': [
                'django.template.context_processors.debug',
                'django.template.context_processors.request',
                'django.contrib.auth.context_processors.auth',
                'django.contrib.messages.context_processors.messages',
            ],
        },
    },
]
</code>
        </pre>
        생성된 templates 폴더의 kakaomap.html 파일에는 카카오맵 api 활용 가이드라인을 따라한 아래와 같은 코드를 입력해주었다.
	      <pre>
		          <code>
          <html>
<head>
	<meta charset="utf-8"/>
	<title>Kakao 지도 시작하기</title>
</head>
<body>
	<div id="map" style="width:500px;height:400px;"></div>
	<script type="text/javascript" src="//dapi.kakao.com/v2/maps/sdk.js?appkey=ab5ad010c7de341a97fc2148f6164f40"></script>
	<script>
		var container = document.getElementById('map');
		var options = {
			center: new kakao.maps.LatLng(33.450701, 126.570667),
			level: 3
		};

		var map = new kakao.maps.Map(container, options);
	</script>
</body>
</html>
        </code>    
	      </pre>
  </div>
</details>
