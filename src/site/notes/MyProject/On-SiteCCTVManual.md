---
{"dg-publish":true,"permalink":"/my-project/on-site-cctv-manual/","dgPassFrontmatter":true,"created":"2023-12-15T13:27:57.542+09:00","updated":"2023-12-15T16:26:49.274+09:00"}
---


# 항목선정
목적
번호판 식별 가능한 환경 구성

화각 확인
화각 수정
조명 각도 확인
조명 각도 수정
세팅값 수정
	셔터
	게인
	3D DNR

실재 상황 사진 확인

노이즈 DNR, Sarpness 조절
번호판 확인

시속 120 이하 주행도로 기준  

|**환경**|조명 무|/*조명 유*/|밝은 시가지|
|---|---|---|---|
|3DNR|9|9|9|
|Sarpness|9|9|9|
|Shutter Time Max|500|500|500|
|Max AGC Gain|32|27|23|


속도
도로 주행 차량의 속도가 시속 120km 를 초과할 경우 Shutter Time Max 값을 높인다.
 - 도로주행 차량 속도와 Shutter Time Max 값은 정비례하다.

밝기
 - 카메라 영상의 밝기는 Shutter Time Max 값과 반비례한다.
Shutter Time Max 값 조절로 밝기가 낮아져 보정해야 할 때에 Max AGC Gain값을 높인다.
카메라 영상의 밝기와 Max AGC Gain 값은 정비례한다.

노이즈 / 흐림
 - 카메라 영상의 노이즈는 Max AGC Gain 값과 정비례한다
Max AGC Gain 값 조절로 노이즈가 심해 보정해야 할 때에 Sharpness값을 낮춘다.
 - 카메라 영상의 흐림은 Sharpness 값과 반비례한다
Sharpness 값이 조절로 흐림이 심해 보정해 할 때에 Sharpness 값조절을 멈춘다.
노이즈 보정을 위해 Sharpness 값 대신 3DNR 값을 높인다.
 - 3DNR 값은 고스트 현상 발생 빈도와 정비례한다. 
# 목차작성




