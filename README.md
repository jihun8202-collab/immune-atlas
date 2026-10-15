# 이뮨 아틀라스 · Immune Atlas 1.0 Beta 3

물리사전의 면역 실험실을 확장한 독립 Windows 앱 + 웹 앱입니다. `dist/`의 화면과 계산 코드를 두 제품이 그대로 공유합니다.

## 사용자 기능

- 건강 상태와 면역 방어력을 분리해서 표시. 시작 건강 상태·면역 강도·세포별 능력 조절.
- 장기·조직 18개, 면역세포 활동 12종, 조직 단면·미세혈관·백혈구 이동 WebGL 관찰.
- 9개 시나리오, 장기별 감염·건강·염증, 사이토카인·발열과 면역 기억.
- 점진적인 표적 개입 노출·감소, 개입 예약, 재노출, 조건별 그래프 비교.
- 단계 진행, 4가지 재생 속도, 일시정지, 큰 글씨, 절전 그래픽, 좁은 화면 지원.
- 실험 JSON 저장·복구, CSV 기록, 최대 6개 실험 보관, 자동 복구.
- GitHub 공개 저장소의 릴리스 업데이트 확인, 베타/정식 구분, SHA-256 검증 후 설치.

## 실행과 빌드

웹: Node.js 22 이상에서 `node server.mjs`, 표시된 localhost 주소 열기. 배포 파일은 `dist/`.

앱: Python 3.9 이상, Microsoft Edge WebView2 Runtime. `desktop/requirements.txt` 설치 후 `python desktop/main.py`. 모든 실험 기능은 오프라인으로 동작하며 업데이트 확인만 인터넷이 필요합니다.

설치 파일 빌드: Inno Setup 6 설치 후 `python desktop/build.py`. 결과는 `release/`의 Setup.exe, Update.zip, SHA256SUMS.txt입니다. 물리사전 앱과 다른 설치 경로·AppId를 사용합니다.

저장소 및 베타 다운로드: https://github.com/jihun8202-collab/immune-atlas/releases · 업데이트 확인은 이 공개 저장소의 GitHub Releases API를 사용하며, 베타/정식 채널을 구분하고 SHA-256을 검증합니다.
앱 실제 실행 검사: `ImmuneAtlas.exe --smoke-test <검증 결과 폴더>`.

## 모델 범위

89개 상태의 교육용 상대 지표 모델입니다. 실제 환자, 약물, 병원체 자료로 보정하지 않았습니다. 건강 상태·면역 방어력은 앱의 가상 지표이고, 모델 시간은 실제 질병 시간으로 환산되지 않습니다. 조직 단면은 실제 혈류역학을 풀어내는 세포 에이전트 모형이 아니라, 상대 부담·염증에 반응하는 개념 시각화입니다. 실제 고통·사망 시각·환자별 위험 예측을 제공하지 않습니다. 전체 방정식과 근거는 `dist/model.html`에 있습니다.

변경 내용은 `CHANGELOG.md`에서 확인할 수 있습니다.

## 데이터

웹 저장은 해당 브라우저에, 앱 저장은 `%LOCALAPPDATA%/ImmuneAtlas`에 보관합니다. 실험 데이터를 서버로 전송하지 않습니다. JSON으로 옮길 수 있습니다. Windows 앱 업데이트는 이뮨 아틀라스 전용 저장소 `jihun8202-collab/immune-atlas`의 `immune-atlas-v...` 릴리스만 사용합니다. 물리사전 앱과 업데이트 경로를 공유하지 않습니다.
