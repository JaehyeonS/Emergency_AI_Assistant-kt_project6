# 🚨 응급상황 자동 인식 및 응급실 연계 서비스

## 📌 프로젝트 개요

이 프로젝트는 응급전화 음성 데이터를 기반으로,  
AI가 실시간으로 **상황을 인식**하고 **응급 등급을 분류**한 후  
가장 적절한 **근처 응급실을 추천**하는 3단계 구조의 인공지능 서비스입니다.

---

## 🧠 시스템 구성

### 1단계: 음성 인식 및 요약
- Whisper API를 통해 음성 → 텍스트 변환
- GPT 모델을 통해 요약 및 키워드 추출

### 2단계: 응급 등급 분류
- BERT 모델을 파인튜닝하여 응급 상황 등급 분류

### 3단계: 응급실 추천 및 연계
- 응급 등급 결과 기반으로, Naver Map API + 응급실 DB 활용
- 가까운 응급실 3곳 추천 및 안내

---

## 🎯 주요 기능

- 응급전화 수신 시 음성 자동 인식 (Whisper)
- GPT를 활용한 응급내용 요약 및 핵심 키워드 추출
- BERT 모델 기반 응급 등급 자동 분류
- Naver Map API를 활용한 병원 위치 연계
- 교통 상황, 응급실 상태 등을 고려한 병원 추천 로직 포함

---

## 🛠️ 적용 기술

| 항목       | 내용 |
|------------|------|
| Language   | Python |
| OpenAPI    | OpenAI Whisper, GPT, BERT, Naver Map |
| Framework  | PyTorch, Transformers |
| IDE/환경   | Google Colab, VS Code |
| 기타       | 응급실 DB, 지도 연계 시스템 |

---

## 🖼️ 전체 흐름도

[응급전화 수신]<br>
↓<br>
[Whisper] → 음성 → 텍스트<br>
↓<br>
[GPT] → 텍스트 요약, 키워드 추출<br>
↓<br>
[BERT] → 응급 등급 분류<br>
↓<br>
[Naver Map API + DB] → 최적 응급실 3곳 추천<br>

yaml
복사
편집

---

## ▶️ 실행 예시

```bash
# Whisper로 음성 인식
python whisper_transcribe.py --input emergency_call.wav

# GPT로 요약
python summarize_with_gpt.py --input transcribed_text.txt

# BERT로 등급 분류
python classify_emergency.py --input summary.txt

# 응급실 추천
python recommend_hospitals.py --level 1
