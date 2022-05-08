<p align="center">
    <img width="200px;" src="https://raw.githubusercontent.com/woowacourse/atdd-subway-admin-frontend/master/images/main_logo.png"/>
</p>
<p align="center">
  <img alt="npm" src="https://img.shields.io/badge/npm-%3E%3D%205.5.0-blue">
  <img alt="node" src="https://img.shields.io/badge/node-%3E%3D%209.3.0-blue">
  <a href="https://edu.nextstep.camp/c/R89PYi5H" alt="nextstep atdd">
    <img alt="Website" src="https://img.shields.io/website?url=https%3A%2F%2Fedu.nextstep.camp%2Fc%2FR89PYi5H">
  </a>
  <img alt="GitHub" src="https://img.shields.io/github/license/next-step/atdd-subway-service">
</p>

<br>

# 인프라공방 샘플 서비스 - 지하철 노선도

<br>

## 🚀 Getting Started

### Install
#### npm 설치
```
cd frontend
npm install
```
> `frontend` 디렉토리에서 수행해야 합니다.

### Usage
#### webpack server 구동
```
npm run dev
```
#### application 구동
```
./gradlew clean build
```
<br>


### 1단계 - 웹 성능 테스트
1. 웹 성능예산은 어느정도가 적당하다고 생각하시나요
   | 사이트          | FCP  |  TTI  |  SI  |  TBT  |   LCP  |   CLS   |   Score  |
   |----------------|------|------|------|--------|--------| ------- |  :-----: |
   | Infra-Subway   | 14.4s | 15s | 14.4s | 510ms |  15s  |   0.041   |    33    |
   | 서울교통공사     | 6.9s | 9.2s | 9.1s |  1150ms |  7.0s  |  0  |    28    |
   | 네이버맵        | 2.0s | 6.6s | 4.5s |  300ms  |  8.0s  |  0.03  |    61    |
   | 카카오맵        | 1.7s | 4.3s | 7.1s |  90ms  |  6.5s  |  0.005  |    68    |
   | 목표예산        |

webPageTest, PageSpeed 에서 테스트한 값을 바탕으로 경쟁사에 비해 성능이 떨어지는 것을 확인했습니다.
목표예산은 각 경쟁사 3사의 평균값으로 설정했습니다.


2. 웹 성능예산을 바탕으로 현재 지하철 노선도 서비스는 어떤 부분을 개선하면 좋을까요

텍스트 기반 리소스를 압축(gzip, deflate, brotli)
스크립트가 필요할 때까지 로딩을 지연시켜 네트워크 활동에 소비되는 바이트를 줄인다. (/js/vendors.js, /js/main.js)
정적 콘텐츠 캐싱

---

### 2단계 - 부하 테스트
1. 부하테스트 전제조건은 어느정도로 설정하셨나요

2. Smoke, Load, Stress 테스트 스크립트와 결과를 공유해주세요

---

### 3단계 - 로깅, 모니터링
1. 각 서버내 로깅 경로를 알려주세요

2. Cloudwatch 대시보드 URL을 알려주세요
