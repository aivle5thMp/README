# AIVLE_5차_자동_출간_및_구독_플랫폼 – " KT 걷다가서재 "

![image](https://github.com/user-attachments/assets/ef7335cb-ef3e-4848-bfd7-a2f04a9979f6)


AIVLE에서 주관하는 5차 미니프로젝트 12조에서 사용한 코드입니다. 
**Spring boot, React, Kubernates** 를 활용하여 REST API를 설계 및 'AI를 활용한 북커버 만들기' 웹사이트를 구현했습니다.

👨‍🏫 **프로젝트 개요**
---
**Spring boot, React, Kubernates** 를 활용하여 REST API를 설계 및 'AI를 활용한 북커버 만들기' 웹사이트를 구현했습니다.
또한 OpenAI 통합을 통해 **내용 검토, 도서 표지 자동 생성, 요약 생성, 가격 및 카테고리 선정, 오디오북 생성**하는 기능을 포함한
풀스택 웹 애플리케이션을 성공적으로 개발했습니다.

- **목표**:  
  1. 작가 신청 → 심사(Admin) → AI 지원 출간 → 구독/결제 → 알림까지  
  2. 구독 서비스를 결제할 경웅 오디오 북 접근 가능
  3. 상위 5개 도서 **베스트셀러**에 등재

## 🏗 서비스 구성

| No. | 서비스명           | 기본 포트 | 역할                                                         |
|:--:|:------------------|:--------:|:------------------------------------------------------------|
| 1  | authentication    | 8080     | 회원가입/로그인, 권한(Role)/구독 여부 관리                             |
| 2  | authors           | 8081     | 작가 신청·심사, Kafka 이벤트 발행 → authentication, notifications 연동 |
| 3  | manuscripts       | 8082     | 원고 작성·조회·수정·삭제·출간 신청                                     |
| 4  | ai                | 8083     | GPT+이미지 API로 요약·카테고리·가격·커버 이미지·오디오 메타데이터 생성     |
| 5  | books             | 8084     | 완결된 도서 관리, 전체/상세 조회, 유료/무료 접근 제어                     |
| 6  | mybook            | 8085     | 구매/열람 기록 관리                                          |
| 7  | payments          | 8086     | 결제 처리                                                   |
| 8  | points            | 8087     | 포인트 트랜잭션 관리                                          |
| 9  | notifications     | 8088     | 사용자 알림 발송                                              |

## 🔧 아키텍처

![image](https://github.com/user-attachments/assets/77c1d6d9-a816-4a1a-91e8-201eac21d844)

## 🤖 API 설계 목록

https://www.notion.so/temp-2227119fc6918083b5c3cc4a054e3a67

🙋‍♀️ 프로젝트 기능
---
### 회원 가입(User)

![image](https://github.com/user-attachments/assets/095eb810-c421-4a1e-a0e6-8ec40029250d)
![image](https://github.com/user-attachments/assets/30e337d9-96cc-4405-b608-033ca007170a)

---
### 로그인(User)

![image](https://github.com/user-attachments/assets/5169f936-37b7-4a46-8fef-ca2980c63b19)

---
### 가입 1000포인트 확인(User)

![image](https://github.com/user-attachments/assets/91611973-ab47-4952-abee-0aab40dbb5fc)
![image](https://github.com/user-attachments/assets/218a2dfc-5191-4549-a658-cc578b8e9a27)

---
### 포인트 구매(User 및 Author)

![image](https://github.com/user-attachments/assets/deb58919-014e-47b9-b471-584d98fe6ca4)
![image](https://github.com/user-attachments/assets/e1e7024a-b41b-4930-bbdc-5cf2882e7969)


