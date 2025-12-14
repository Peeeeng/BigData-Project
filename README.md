# Steam Game Genre Trend Analysis

Steam 게임 데이터를 기반으로 **연도별 인기 게임 장르의 변화와 그 배경 요인**을 분석하는 데이터 분석 프로젝트입니다.  
본 프로젝트는 특히 **데이터 수집 · 전처리 · 변환 과정의 설계와 구현**에 중점을 두었습니다.

###

## Project Overview

### Objective
- Steam 플랫폼에서 출시된 게임 데이터를 활용하여
- 연도별 인기 장르 트렌드를 분석하고
- 장르 변화가 발생한 원인을 데이터 기반으로 해석

### Key Focus
- 손상된 CSV 데이터 자동 복구
- 장르·카테고리 정규화
- 분석 가능한 구조로 데이터 변환



## 📂 Dataset

- **Source**: Kaggle – Steam Games Dataset  
- **Format**: CSV  
- **Size**: 약 80,000+ rows

### 주요 컬럼
- `name`, `release_date`
- `genres`, `categories`
- `price`
- `positive`, `negative`
- `estimated_owners`, `peak_ccu`



## 🛠 Data Processing Pipeline

### 1️) Data Acquisition
- Kaggle에서 원본 CSV 파일 다운로드
- 파일 인코딩 및 기본 구조 점검



### 2️) Data Cleaning
- CSV 파싱 오류로 인한 **열 밀림 현상 자동 탐지 및 복구**
- 특수문자 깨짐으로 인해 **게임명과 출시일이 합쳐진 행 수정**
- 원본 데이터 보존을 위해 중간 산출물 생성



### 3️) Data Transformation
- 문자열 형태의 리스트 컬럼(`genres`, `categories`) 정규화
- 대표 장르(`main_genre`) 추출
- 싱글/멀티플레이 여부 Boolean 컬럼 생성
- 리뷰 기반 파생 변수 생성 (`total_reviews`)
- 소유자 수 범위 문자열 → 수치형 변수 변환



### 4️) Validation
- 전처리 전·후 컬럼 수 및 행 수 비교
- 결측값 및 중복 데이터 제거
- 데이터 타입 및 샘플 행 검증



## 🧱 Final Dataset Structure

| Column | Description |
|------|------------|
| name | 게임 이름 |
| release_date | 출시일 |
| year | 출시 연도 |
| genres_clean | 정제된 장르 리스트 |
| main_genre | 대표 장르 |
| price | 가격 |
| is_multiplayer | 멀티플레이 여부 |
| is_singleplayer | 싱글플레이 여부 |
| positive | 긍정 리뷰 수 |
| negative | 부정 리뷰 수 |
| total_reviews | 총 리뷰 수 |
| owners_est | 추정 소유자 수 |
| peak_ccu | 최대 동시 접속자 수 |



## 📈 Analysis

- 연도별 인기 장르 트렌드 시각화
- 리뷰 수 기반 장르 인기 비교
- 무료/유료 게임 장르 분포 차이 분석
- 멀티플레이 여부에 따른 장르 변화 분석

<img width="905" height="5478" alt="0" src="https://github.com/user-attachments/assets/1414b473-a061-455a-8937-ba07a7eb729d" />

<img width="1008" height="5478" alt="1" src="https://github.com/user-attachments/assets/43d5fdb9-7dd8-46e1-90dc-383b8bf7c0b0" />

<img width="915" height="2859" alt="2" src="https://github.com/user-attachments/assets/92e54818-57c9-432f-98c5-eae2562a8ec9" />


## 💡 Expected Insights

- 장르 인기도는 단순 출시 수보다 **유저 반응(리뷰·동접자)**에 더 크게 좌우됨
- VR 등 일부 장르는 대중 장르보다 **매니아 장르** 성격이 강함
- 무료 게임과 멀티플레이 요소가 장르 트렌드에 중요한 영향을 미침



