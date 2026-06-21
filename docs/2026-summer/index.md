---
hide:
  - navigation
  - toc
---

<div class="hydroai-hero" markdown>

<span class="eyebrow">HydroAI Lab · GIST · Summer 2026</span>

# The Future of the Water Cycle,<br>powered by <span class="accent">AI & Satellites</span>.

<p class="lede">
Welcome to the kickoff page for our <strong>G-SURF 2026</strong> interns —
<strong>Changik Park</strong> and <strong>Dowon Lee</strong>.
(Four more interns will join later this summer through the
<strong>GIST Summer Internship</strong> program on rolling start dates.)
Below is what to prepare <strong>before our first meeting on Wednesday afternoon</strong>.
</p>

<div class="tag-row">
  <span class="hydroai-tag">Deep Learning</span>
  <span class="hydroai-tag">SMAP · CYGNSS · ASCAT</span>
  <span class="hydroai-tag">GNSS-R</span>
  <span class="hydroai-tag">Land–Atmosphere</span>
  <span class="hydroai-tag">Water Cycle</span>
</div>

</div>

## :material-calendar-clock: 이번 주 일정

| 요일 | 할 일 |
|------|------|
| **월 · 화** | 아래 "월/화 할 일" 체크리스트 진행 |
| **수 오후** | **첫 미팅** — 그동안 정리한 내용 공유, 연구 방향 합 맞추기 |
| **금** | 첫 주간 로그 마감 (Google Doc) |

---

## :material-check-circle-outline: 월/화 할 일 — 수요일 미팅 전까지

수요일 미팅에서 **여러분이 미팅을 주도**합니다. 아래 세 가지만 준비해 오세요.
완성도보다 **고민의 흔적**이 중요해요.

### :material-numeric-1-circle-outline: 연구 주제 이해하기 (반나절)

각자에게 배정된 주제의 **배경 논문 3–5편**을 빠르게 훑어 읽기.
다 이해할 필요 없음 — "이 분야에서 뭐가 알려져 있고 뭐가 모르는지"만 잡으면 됨.

!!! tip "선배에게 먼저 물어보기"
    어떤 논문부터 보면 좋은지, 어떤 자료/툴을 쓰면 좋은지
    **연구실 선배들에게 꼭 먼저 의논**해 보세요. 같은 영역을 다뤄본 선배의
    한 마디가 논문 5편 읽는 것보다 빠를 때가 많습니다.

=== ":material-weather-pouring: 박창익 — Brown Ocean Effect"

    **주제 한 줄 요약**
    : 열대저기압(태풍·허리케인)이 육지에 상륙한 후에도 약해지지 않거나
      오히려 강해지는 현상. 젖은 토양이 마치 바다처럼 수증기를 공급해서
      발생한다고 알려져 있음.

    **읽어볼 출발점**

    - Andersen & Shepherd (2014), *Sustained convection in tropical cyclones over land* — Brown Ocean의 고전
    - Kishtawal et al. (2012) — TC 상륙 후 강도 변화 분석
    - 최근 SMAP 데이터를 활용한 연구 (Google Scholar에서 "brown ocean effect SMAP" 검색)
    - 연구실 폴더 `2026_summer/brown_ocean_effect/brown_ocean_pipeline.md` — 교수님이 미리 정리해둔 파이프라인 스케치 (공유 드라이브에서 열어보기)

=== ":material-satellite-variant: 이도원 — GNSS-R 기반 토양수분 (CYGNSS)"

    **주제 한 줄 요약**
    : 기존 마이크로파 위성(SMAP, ASCAT, AMSR2)의 토양수분 산출을
      **GNSS-R 기반 위성(CYGNSS)**이 대체할 수 있을까?
      성능·공간해상도·시간해상도·관측 가능 지역 측면에서 비교.

    **읽어볼 출발점**

    - Chew & Small (2018, 2020) — CYGNSS 토양수분 산출 알고리즘 (대표 논문)
    - Kim & Lakshmi (2018) — CYGNSS와 SMAP 비교
    - Eroglu et al. (2019) — Machine learning 기반 CYGNSS 토양수분
    - NASA CYGNSS 미션 페이지 — <https://www.nasa.gov/cygnss/>
    - SMAP, ASCAT, AMSR2 토양수분 산출 원리 정리 자료 (Petropoulos et al. 리뷰)
    - Google Scholar 검색어: `"CYGNSS soil moisture"`, `"GNSS-R soil moisture SMAP"`

### :material-numeric-2-circle-outline: 한 페이지 정리 (1~2시간)

읽은 내용을 바탕으로 **Google Doc 한 페이지**에 다음을 적어 오기.
양식 자유, 분량 짧게.

- :material-target: **연구 질문(가설)** — "나는 이 여름에 \_\_\_\_을(를) 알아내고 싶다."
- :material-database: **필요한 데이터** — 어떤 자료가 있어야 답할 수 있나
- :material-tools: **분석 방법(아이디어)** — 어떻게 답할 생각인지 (3줄 이내)
- :material-help-circle: **모르는 것 / 막힐 것 같은 부분** — 교수님께 물어볼 것

!!! tip "Doc 만드는 법"
    - Google Drive에서 새 Doc 만들기
    - 파일명: `(본인 이름) — Summer 2026 Weekly Log`
    - 공유: 교수님(hyunglok@) **편집자** 권한으로
    - 첫 페이지에 위 네 항목 작성
    - 미팅 1시간 전까지 Doc 링크를 교수님께 메일/Slack으로 전송

### :material-numeric-3-circle-outline: 환경 점검 (30분)

- 본인 노트북에 **Python 3 + Jupyter** 설치돼 있는지 확인
- **Google Earth Engine** 계정 만들기 — <https://earthengine.google.com/> (승인에 며칠 걸릴 수 있음, **오늘 신청**)
- **연구실 Slack 가입** — 박창익: 교수님께 초대 요청 / 이도원: 이미 가입 완료

---

## :material-calendar-star: 9주 큰 그림

| 주차 | 기간 | 주제 |
|------|------|------|
| **1** | 6/22 – 6/26 | 문헌 탐색 + 금요일 주제 발표 (10분) |
| 2 | 6/29 – 7/03 | 데이터 수집 |
| 3 | 7/06 – 7/10 | 분석 파이프라인 v1 |
| **4** | 7/13 – 7/17 | 중간 점검 발표 (10분) |
| 5 | 7/20 – 7/24 | 결과 다듬기 |
| 6 | 7/27 – 7/31 | 검증 / 강건성 테스트 |
| 7 | 8/03 – 8/07 | 발표 자료 초안 |
| 8 | 8/10 – 8/14 | 리허설 |
| **9** | 8/17 – 8/21 | **최종 발표 15분 (8/21 금)** |

!!! info "여름휴가 1주 (날짜 미정)"
    이 기간 중 **1주일 여름휴가**가 있습니다. 정확한 날짜는 첫 미팅에서
    함께 정할 예정이며, 그에 맞춰 위 일정도 1주씩 밀려 조정됩니다.

---

## :material-message-question: 미팅 전에 막히면

- 슬랙/메신저로 교수님께 바로 물어보기
- "이거 맞나요?" 보다 "**이렇게 해봤는데 이 부분이 막힙니다**" 가 좋음
- 같은 인턴끼리도 자유롭게 의논 — 둘 다 토양수분/원격탐사 다루니까 겹치는 부분 많음

!!! abstract "수요일 미팅에서 다룰 것"
    1. 각자 정리해온 한 페이지 발표 (5분씩)
    2. 연구 질문 다듬기 — 교수님과 함께
    3. 금요일 주제 발표(10분) 준비 방향 잡기
    4. 데이터 접근 권한, 컴퓨팅 자원 안내

---

<div style="text-align:center; margin-top:3rem; opacity:0.6; font-size:0.85rem;">
HydroAI Lab · GIST · Summer 2026
</div>
