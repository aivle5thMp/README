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

## 👻작동 방식

LOCAL 환경 : 해당 Repo에 있는 파일 다운 후 Terminal에서 docker-compose up -d 입력 후 실행
Azure 배포 사이트: http://20.249.106.10:5173/

## 🙋‍♀️ 프로젝트 기능
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

---
### 작가 신청(User)
![image](https://github.com/user-attachments/assets/0f4538c2-450a-4e88-839f-3b1838b089ba)
![image](https://github.com/user-attachments/assets/841f1eda-f471-4e23-a4b1-fe3c95eb18b4)
![image](https://github.com/user-attachments/assets/16b54dd3-a9bc-48b4-965a-165b414ccac5)

---
### Admin 계정으로 로그인 (ID: admin@admin.com PW: admin1234) (Admin)

![image](https://github.com/user-attachments/assets/e8871408-8590-4129-9d3b-15ae57dc79f6)
![image](https://github.com/user-attachments/assets/596e66b1-5139-4931-8f37-d954c9308352)
![image](https://github.com/user-attachments/assets/f162412b-97b7-4463-bade-ce41886a75c3)
![image](https://github.com/user-attachments/assets/98015242-a29e-46a2-b966-1d057a009fa3)

---
### User 계정으로 다시 로그인 (User -> Author 승격)
![image](https://github.com/user-attachments/assets/88b9d45d-38b4-45f7-8b4e-bbbf66172fb8)


---
### 책 등록 Process(Author)
![image](https://github.com/user-attachments/assets/5a010bb8-aff1-4bda-870d-aa07324cffc4)
![image](https://github.com/user-attachments/assets/e2637854-a896-4233-8557-a79c80df5757)
![image](https://github.com/user-attachments/assets/77a84116-2246-4443-8525-ffaee881f3fb)
![image](https://github.com/user-attachments/assets/518f2924-d090-4ed1-9497-8f44f84955a3)
![image](https://github.com/user-attachments/assets/8826b067-3739-4469-aca3-618240b7aa0b)
![image](https://github.com/user-attachments/assets/beff736a-f392-44ea-8c01-ecee25e15ccf)

---
### AI 검토 및 생성 기능 작동 (FrontEnd에서는 보이지 않음) (AI)


---
### 출간 완료(Author)

![image](https://github.com/user-attachments/assets/51264fe5-0fb4-4ef4-8d8e-caf265d6d54d)
![image](https://github.com/user-attachments/assets/22995674-6d60-477f-8b05-38d290935672)

---
### 구독 신청

![image](https://github.com/user-attachments/assets/3b032480-794f-4c7a-97d2-14cf5b77d89e)
