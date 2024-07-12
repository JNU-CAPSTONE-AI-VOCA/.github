# 생성형 AI기반 PDF 인식 단어장 애플리케이션 VOCAI

## 프로젝트 개요
본 프로젝트는 2024 전남대학교 소프트웨어공학과 캡스톤 프로젝트로 진행 하였으며 안드로이드 환경에서 PDF 및 이미지 파일에서 단어를 추출하고, 단어장 관리 및 학습 기능을 제공하는 것을 목표로 한다.

**프로젝트 대상자**
1. 영어 본문을 번역기에 의존하지 않고 원문 그대로 이해하고자 하는 사용자
2. 논문, 소설, 기사 등 영어 원문을 그대로 읽고자 하는 사용자
3. 개인적으로 선택한 글을 학습하려는 사용자

## 프로젝트 아키텍처 설계

#### 유스케이스 다이어그램
<img src="/img/image10.jpg" style="zoom:67%;" />

###


## 팀구성 및 역할

#### 신수민
- 역할: [Flutter] 사용자 인터페이스 설계 및 애플리케이션 개발
- 담당 작업: 로그인 기능 구현, 단어장 리스트 UI 구현, 단어 추가 및 삭제 기능 구현 등
#### 최진서
- 역할: [Flutter] 사용자 인터페이스 설계 및 애플리케이션 개발
- 담당 작업: 파일 탐색 및 업로드 기능 구현, 직접 촬영 및 업로드 기능 구현 등
#### 허란
- 역할: [Flutter] 사용자 인터페이스 설계 및 애플리케이션 개발
- 담당 작업: 단어 추출 및 저장 기능 구현, 예문 해석 및 초기화 기능 구현 등
#### 박하민
- 역할: [SpringBoot] ChatGPT API 통신 및 REST API 서버 개발
- 담당 작업: 프롬프트 엔지니어링, 파일 업로드 구현, PDF 및 이미지 단어 추출 구현 등
#### 송대철
- 역할: [SpringBoot] ChatGPT API 통신 및 REST API 서버 개발
- 담당 작업: 예문 생성 구현, 보기 단어 생성 구현, 서버 배포 및 유지보수 등

### 프로젝트 일정 간트차트

```mermaid
gantt
    title 프로젝트 추진 일정 및 현황
    dateFormat  YYYY-MM-DD
    section 주제 선정 및 계획서 작성 역할 분담
    전체 팀      :active, a1, 2024-03-01, 2024-03-31

    section 기능명세 및 사용자 인터페이스 화면 설계
    전체 팀      :active, a2, 2024-03-15, 2024-04-15

    section 프로젝트 개발 환경 구축
    전체 팀      :active, a3, 2024-03-15, 2024-04-15

    section 로그인 기능 및 UI 구현
    프론트엔드  :active, a4, 2024-04-01, 2024-04-15

    section 단어장 리스트 UI 구현
    프론트엔드  :active, a5, 2024-04-15, 2024-04-30

    section 단어장 추가 및 삭제 기능 구현
    프론트엔드  :active, a6, 2024-04-15, 2024-04-30

    section 단어 리스트 UI 구현
    프론트엔드  :active, a7, 2024-05-01, 2024-05-15

    section 단어 추가 기능 및 UI 구현
    프론트엔드  :active, a8, 2024-05-15, 2024-05-30

    section PDF IMG 업로드 기능 및 UI 구현
    프론트엔드  :active, a9, 2024-05-01, 2024-05-15

    section PDF 추출 결과 UI 구현
    프론트엔드  :active, a10, 2024-05-15, 2024-05-30

    section 카메라 촬영 기능 구현
    프론트엔드  :active, a11, 2024-05-15, 2024-05-30

    section 스트림 통신 위젯 구현
    프론트엔드  :active, a12, 2024-06-01, 2024-06-15

    section 단어 삭제 복사 이동 기능 구현
    프론트엔드  :active, a13, 2024-06-01, 2024-06-15

    section 예문 해석 및 초기화 기능 구현
    프론트엔드  :active, a14, 2024-06-01, 2024-06-15

    section 단어 학습 UI 구현
    프론트엔드  :active, a15, 2024-06-15, 2024-06-30

    section 프롬프트 엔지니어링
    백엔드      :active, a16, 2024-04-01, 2024-04-30

    section 파일 업로드 구현
    백엔드      :active, a17, 2024-04-15, 2024-05-15

    section PDF 단어 추출 구현
    백엔드      :active, a18, 2024-05-01, 2024-05-30

    section 예문 생성 구현
    백엔드      :active, a19, 2024-05-15, 2024-06-15

    section 보기 단어 생성 구현
    백엔드      :active, a20, 2024-06-01, 2024-06-30

    section 이미지 단어 추출 구현
    백엔드      :active, a21, 2024-06-01, 2024-06-30

    section AWS 서버 배포 및 유지보수
    백엔드      :active, a22, 2024-06-15, 2024-06-30

    section 어플리케이션 테스트 및 검증
    전체 팀      :active, a23, 2024-06-15, 2024-06-30

    section 디버깅
    전체 팀      :active, a24, 2024-06-15, 2024-06-30
```


### 프로젝트 기능 구현


**로그인 기능**

| 로그인 화면 | ID 입력 | PWD 입력 | 입력 오류 알림 |
|------|------|------|------|
| <img src="/img/image26.png" style="zoom:63%;" /> | <img src="/img/image27.png" style="zoom:67%;" /> | <img src="/img/image27.png" style="zoom:67%;" /> | <img src="/img/image28.png" style="zoom:67%;" /> |

---

**단어장 추가 및 삭제 기능**

| 단어장 목록 화면 | 단어장 생성 | 단어장 삭제(슬라이드) | 단어장 삭제(확인) |
|------|------|------|------|
| <img src="/img/image29.png" style="zoom:67%;" /> | <img src="/img/image30.png" style="zoom:67%;" /> | <img src="/img/image31.png" style="zoom:56%;" /> | <img src="/img/image32.png" style="zoom:70%;" /> |

---

**파일 탐색 및 업로드 기능**

| 업로드 화면 | 파일 탐색 | PDF 선택 시 화면 | IMG 선택 시 화면 |
|------|------|------|------|
| <img src="/img/image33.png" style="zoom:67%;" /> | <img src="/img/image34.png" style="zoom:67%;" /> | <img src="/img/image35.png" style="zoom:67%;" /> | <img src="/img/image36.png" style="zoom:67%;" /> |

---

**직접 촬영 및 업로드 기능**

| 업로드 화면(카메라 버튼) | 카메라 열기 | 카메라 촬영 | 촬영 이미지 적재 |
|------|------|------|------|
| <img src="/img/image37.png" style="zoom:67%;" /> | <img src="/img/image38.png" style="zoom:67%;" /> | <img src="/img/image39.png" style="zoom:67%;" /> | <img src="/img/image40.png" style="zoom:67%;" /> |

---

**단어 추출 및 저장 기능**

| 추출 결과 화면 | 단어 선택 | 단어장 선택 | 저장 확인 |
|------|------|------|------|
| <img src="/img/image41.png" style="zoom:80%;" /> | <img src="/img/image42.png" style="zoom:77%;" /> | <img src="/img/image43.png" style="zoom:67%;" /> | <img src="/img/image44.png" style="zoom:77%;" /> |

---

**예문 해석 및 초기화 기능**

| 예문 보기 화면 | 예문 해석 | 예문 초기화 | 새로운 예문 해석 |
|------|------|------|------|
| <img src="/img/image45.png" style="zoom:75%;" /> | <img src="/img/image46.png" style="zoom:75%;" /> | <img src="/img/image47.png" style="zoom:67%;" /> | <img src="/img/image48.png" style="zoom:67%;" /> |

---

**단어 삭제 복사 이동 기능**

| 단어 목록 화면 | 단어 삭제 | 단어 복사 | 단어 이동 |
|------|------|------|------|
| <img src="/img/image49.png" style="zoom:67%;" /> | <img src="/img/image50.png" style="zoom:67%;" /> | <img src="/img/image51.png" style="zoom:67%;" /> | <img src="/img/image52.png" style="zoom:67%;" /> |

---

**단어 직접 추가 기능**

| 단어 추가 화면 | 단어 뜻 입력 | 예문 입력 | 저장 확인 |
|------|------|------|------|
| <img src="/img/image53.png" style="zoom:67%;" /> | <img src="/img/image54.png" style="zoom:67%;" /> | <img src="/img/image55.png" style="zoom:67%;" /> | <img src="/img/image56.png" style="zoom:67%;" /> |

---

**단어 학습 기능 (1)**

| 학습 페이지 도입부 화면 | 문제 예시 보기 | 단어장 선택 | 단어장 적재 확인 |
|------|------|------|------|
| <img src="/img/image57.png" style="zoom:67%;" /> | <img src="/img/image58.png" style="zoom:79%;" /> | <img src="/img/image59.png" style="zoom:67%;" /> | <img src="/img/image60.png" style="zoom:67%;" /> |

---

**단어 학습 기능 (2)**

| 단어 학습 화면 | 보기 선택 (1개 제한) | 정답 및 뜻 확인 | 다음 단어 학습(슬라이드) |
|------|------|------|------|
| <img src="/img/image61.png" style="zoom:67%;" /> | <img src="/img/image62.png" style="zoom:67%;" /> | <img src="/img/image63.png" style="zoom:67%;" /> | <img src="/img/image64.png" style="zoom:43%;" /> |


## 시연 영상
<img src="/img/demo_video.gif" style="zoom:100%;" />

## 향후 과제
**AI 답변에 검증기능 추가**
현재 앱의 답변은 ai의 실수가 고려되어 있지 않으므로 pdf로부터 단어 추출 후, 영어사전을 검색하고 주려고 했던 문맥상 의미와 가장 가까운 뜻을 제공하는 기능을 추가할 수 있다. 이와 같은 방법으로 사용자에게 정확한 정보의 전달을 기대할 수 있을 것이다.

**다양한 언어로의 확장**
다른 대규모 언어 모델 (LLM) 기반의 서비스를 제공하며 자연어처리를 하기 때문에 추후 영어가 아닌 다른 언어로의 유연한 확장성을 기대할 수 있을 것이다.

**예문 생성 기능의 확장**
PDF 텍스트 추출 및 단어와 예문 제공 기능 외에도, 사용자가 제공하는 다양한 상황이 반영된 예문 생성 기능을 추가하여 여러 문맥에서 단어의 사용방법을 학습할 수 있을 것이다.

**수준별 학습 기능 추가**
학습 페이지에서 문장구조의 수준과 학습 단어의 난이도를 고려하며, 유럽 언어 표준등급(CEFR)을 기반으로 예문과 선지를 구성하도록 지원할 예정이다.

**결제 및 구독 서비스 추가**
또한, 결제 및 구독 기능을 추가하여 계정 별 온라인 저장 서비스를 지원하고, 서비스를 구독제로 판매할 예정이다.

**학습 기반 사용자 수준 진단**
사용자가 학습한 단어정보를 기반으로 사용자가 CEFR 기준으로 어느 수준까지 학습했는지에 대한 통계 데이터를 시각적으로 제공할 예정이다.
