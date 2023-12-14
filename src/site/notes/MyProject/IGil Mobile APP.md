---
{"dg-publish":true,"permalink":"/my-project/i-gil-mobile-app/","dgPassFrontmatter":true,"created":"2023-12-13T17:50:08.562+09:00","updated":"2023-12-14T17:21:56.835+09:00"}
---


# Dev Env
## [[MyResource/Mobile App Framework\|Mobile App Framework]]
### [[MyResource/React-Native\|React-Native]]
## [[MyResource/Backend Framework\|Backend Framework]]
### [[MyResource/Express\|Express]]
# 요구사항
## 기능 흐름도
![Pasted image 20231017164044.png](/img/user/AttachedFile/Pasted%20image%2020231017164044.png)
## Screen 흐름도
![Pasted image 20231025155326.png](/img/user/AttachedFile/Pasted%20image%2020231025155326.png)
## Center APP
### [[MyResource/Login & Sign\|Login & Sign]]
- 서버 DB 연동 회원정보 생성, 로그인
### Center - Edge 연동 코드 생성
- Server에서 계정에 주어지는 랜덤 코드 수신
### [[MyResource/WebSocket\|WebSocket]]
- 디바이스 충격 감지 민감도, 송신
- 위치, 디바이스 연결, 디바이스 동작 수신
## Edge APP
### Center - Edge 연동 코드 입력
- 입력받은 연동코드를 Server 에 송신
### [[MyResource/WebSocket\|WebSocket]]
- 서버 DB와 연동
- 위치, 디바이스 연결, 디바이스 동작 송신
- 디바이스 충격 감지 민감도 수신
### MobileDeviceBlueTooth
- 디바이스 연결, 디바이스 동작 모니터
- 디바이스 충격 감지 민감도 제어
### MobileDevice 권한 접근
- 백그라운드 동작
- BlueTooth 연결
- 위치정보
- 기기 정보

## App



## Server DB
### 로그인, 회원가입 API 구현
### 외부 로그인 API 및 기존 계정 연동, 신규 아이디 생성 구현
### Center - Edge 연동 API 구현
### Center-Edge WebSocket 구현

![Pasted image 20231017173103.png](/img/user/AttachedFile/Pasted%20image%2020231017173103.png)

![Pasted image 20231025152601.png](/img/user/AttachedFile/Pasted%20image%2020231025152601.png)

