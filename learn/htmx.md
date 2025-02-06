#### 개요
	- HTML을 사용하여 page를 rendering 할 수 있도록 하는 js library이다.
	- 서버에서 data(json)을 받아서 rendering하는게 아니고 html를 받아서 rendering함
#### 특징
#### 단점
#### 사용법
##### hx-{httpMethod}
- GET, POST등의 httpmethod를 사용할수 있으며 요청할 URL을 넣어준다
##### hx-trigger
- URL을 요청할 trigger를 작성
	- click
	- load
	- submit
##### hx-target
- 서버로 부터 받은 page를 넣을 위치를 정의
##### hx-swap
- 서버로 부터 받은 page를 어떻게 교체할 것인지 정의
