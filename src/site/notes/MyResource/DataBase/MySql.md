---
{"dg-publish":true,"permalink":"/my-resource/data-base/my-sql/","dgPassFrontmatter":true,"created":"2023-12-13T17:50:08.588+09:00","updated":"2023-12-14T17:37:39.258+09:00"}
---


# WorkBench
## CreateSchema 
- DATABASE 생성
### How To use CreateSchema
-  SCHEMAS에서 마우스 오른쪽 클릭
- Create Schema 클릭
- Charset/Collation: utf8mb4 utf8mb4_bin
- Algorithm: Defalt Lock Type: Default

## ReverseEngineer
- ERD Diagram 생성
### How To use ReveseEngineer
- 상단탭에서 Database 클릭
- Reverse Engineer... 클릭
- Select Schema to Reverse Engineer에서 이용할 Schema 선택
### What is ERD Diagram

# Relationship

## OnUpdate/Delete
### RESTRICT 
 - 개체를 변경/삭제할 때, 참조개체를 변경/삭제 취소(제한)
### CASCADE
 - 개체를 변경/삭제할 때, 참조개체를 변경/삭제
### NO ACTION
- MYSQL에서는 RESTRICT와 동일합니다.
### SET NULL
- 개체를 변경/삭제할 때, 참조개체의 값을 NULL로 세팅

## Fori