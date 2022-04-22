# 2주차 과제 - DDD설계

## 1. 도메인 모델 그리기
![이미지](https://aboutyhs1.notion.site/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2F93b20009-e35f-4b10-9019-15933b3e1ed6%2F%EB%8F%84%EB%A9%94%EC%9D%B8_%EB%8B%A4%EC%9D%B4%EC%96%B4%EA%B7%B8%EB%9E%A8.drawio.png?table=block&id=a007969b-3573-4fe5-824e-e43c6a2fba94&spaceId=2d170995-884c-45e9-8e7b-86359b2e2ef9&width=1400&userId=&cache=v2)

<br/>

## 2. MSA로 설계하기
#### a) 계획
- API Gateway→to 각 도메인별
- DB는 한 개, 스키마만 분리
- 한 도메인/서비스 당 스키마를 하나만 보게 최대한 분리
- 도메인 분리 기준은 유사 기능/같은 스키마를 볼 수 있는 기능끼리 
- 로그인은 oauth2 서버를 두고 JWT토큰 발급

![이미지](https://aboutyhs1.notion.site/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2Fee7e6e63-803f-4ed8-88fc-a97f1f9c7589%2Fs.drawio.png?table=block&id=d6c82853-290d-491f-a40d-e0ce700a288c&spaceId=2d170995-884c-45e9-8e7b-86359b2e2ef9&width=1120&userId=&cache=v2)

#### b) 도메인 분리
: 각 항목 당 하나의 도메인. 도메인 항목 하단은 각각 서비스

- 로그인 기능~>oauth2 인증 서버(로그인/토큰 발급)
- 회원 관련 기능
    - 가입
    - 계정 생성
    - 강사 생성
- 강의 관련 기능
    - 강의 개설
    - 강사 매칭
    - 강의 컨텐츠 업로드
    - 강의 노출 on/off
    - 강의 열람
    - 강의 별점 부여
    - 강의 별점 열람
    - 수강/업로드 한 강의 조회
    - 강의-시험 추가
    - 수강자 성적 추가
- 게시판 가능
    - 글 쓰기
    - 글 보기
    - 댓글 쓰기
    - 게시글/댓글 숨김

## 3. REST API 설계
: https://aboutyhs1.notion.site/327bb472f2ca40978e30caf62f132be8
