---
{"dg-publish":true,"permalink":"/my-project/on-site-cctv-manual/","dgPassFrontmatter":true,"created":"2023-12-15T13:27:57.542+09:00","updated":"2023-12-15T17:18:13.875+09:00"}
---

# 항목선정
목적
번호판 인식 가능한 환경 구성

1 화각 확인
2 화각 수정

3 조명 각도 확인
4 조명 각도 수정

5 세팅값 초기화
시속 120 이하 주행도로 기준  

|**환경**|조명 무|/*조명 유*/|밝은 시가지|
|---|---|---|---|
|3DNR|9|9|9|
|Sarpness|9|9|9|
|Shutter Time Max|500|500|500|
|Max AGC Gain|32|27|23|

6 실재 상황 사진 확인

7 세팅값 수정
속도
도로 주행 차량의 속도가 시속 120km 를 초과하여 끌림현상이 발생할 경우 Shutter Time Max 값을 높인다.
 - 도로주행 차량 속도와 Shutter Time Max 값은 정비례하다.

밝기
 - 카메라 영상의 밝기는 Shutter Time Max 값과 반비례한다.
Shutter Time Max 값 조절로 등의 이유로 밝기를 보정해야 할 때에 Max AGC Gain값을 높인다.
카메라 영상의 밝기와 Max AGC Gain 값은 정비례한다.

노이즈 / 흐림
 - 카메라 영상의 노이즈는 Max AGC Gain 값과 정비례한다
Max AGC Gain 값 조절 등의 이유로 노이즈를 보정해야 할 때에 Sharpness값을 낮춘다.
 - 카메라 영상의 흐림은 Sharpness 값과 반비례한다
Sharpness 값이 조절로 흐림이 심해 보정해 할 때에 Sharpness 값조절을 멈춘다.
노이즈 보정을 위해 Sharpness 값 대신 3DNR 값을 높인다.
 - 3DNR 값은 고스트 현상 발생 빈도와 정비례한다. 
# 목차작성
목차
개요
	매뉴얼 목적
현장 설정 절차
	설정 값 초기화
	카메라 화각 수정
		차량 영상 확인
		카메라 화각 조정 가이드
	조명 각도 수정
		카메라 영상 확인
		조명 각도 조정 가이드
	카메라 설정 값 수정
		차량 영상 확인
		상황별 설정 값 수정 가이드
			속도
			밝기
			노이즈 / 흐림
		
	
	
	
	
	
