---
{"dg-publish":true,"permalink":"/my-resource/python/alpr-program/","dgPassFrontmatter":true,"created":"2023-12-13T17:50:08.571+09:00","updated":"2023-12-19T15:40:03.672+09:00"}
---

# ALPR Program Structure
## 통합 관리 
- 각 프로그램 실행, 인식된 이미지의 이름에 따라 문자열을 만들어주는 프로그램
## 모션 디텍션
- 감지되는 객체의 범위가 기준 이상일 때에 영상을 이미지로 저장하는 기능
## 번호판 영역 추출
- 감지된 객체 이미지의 번호판 영역을 식별하여 저장하는 기능
## 문자 인식
- 식별된 번호판 영역의 문자를 개별 인식하여 번호판 이미지의 이름으로 저장하는 기능

# 프로그램 분석
## DETECT_1.PY

```Python
expe = 0
expe_f = 0
check_image = ""

sellect = 0

def main(opt):
	data_count = 0
    del_file = ".\\data\\images\\*.jpg"
    check_requirements(exclude=('tensorboard', 'thop'))
    while True:
        try:
            e = run(**vars(opt)) # 에러메세지 리턴
            if expe == 1: # 에러 플래그 True
                ee = str(e) # 에러 메세지 스트링
                eee = ee.split() # 에러 스트링 분할
                
                for del_image in glob.glob(del_file):# 저장경로상 모든 파일
                    if del_image == eee[3]:
  # 저장경로 상 이미지 이름이 에러메세지 3번째 글자와 일치할 때에
                        os.remove(del_image) # 해당이미지를 삭제하고
                        expe = 0 # 에러플레그를 False로 치환한다.
                        continue

            elif expe_f == 1:
                ee = str(e)
                eee = ee.split()
                eeee = eee[7]
                eeeee = eeee.split("+")
                eeeeee = eeeee[0]

                for del_image in glob.glob(del_file):
                    if del_image == eee[7]:
                        os.remove(del_image)
                        expe_f = 0
                        continue

                    elif del_image == eeeeee:
                        os.remove(del_image)
                        expe_f = 0
                        continue

            else:
                print("dddd")

        except Exception as e:
            print("예외내용=", e)
```
