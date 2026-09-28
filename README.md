# Dynamic System Virtual Laboratory

ME341을 위한 브라우저 기반 동역학 실험실입니다. 메인 페이지에서 실험을 선택하고, 각 실험은 독립된 폴더에서 실행됩니다. 별도 설치, 빌드, 외부 라이브러리가 필요 없습니다.

## 현재 실험

**[Vertical Translational Mass–Spring–Damper System](./vertical-translational-mass-spring-damper/index.html)**

질량·감쇠·강성 및 힘 조절, Run/Pause, Reset, Pull & Release, 드래그 조작, 입력 선택(Free/Step/Pulse/Sine), 속도 및 주파수 선택, 물리/CAD 애니메이션, 시간응답, ODE/전달함수/상태공간, pole map, 감쇠·안정성 설명, 수치 대입 유도과정을 제공합니다.

기존 저장소의 시뮬레이터를 하위 폴더로 이동했습니다. 계산 JavaScript와 기존 CSS, responsive breakpoint를 유지했으며, 페이지 제목·실험 이름·All Labs 링크만 변경했습니다.

## 저장소 구조

```text
Dynamic-System-Virtual-Lab/
├── index.html                 # 전체 실험실 메인 페이지
├── README.md
├── LICENSE                    # 기존 MIT 라이선스 유지
└── vertical-translational-mass-spring-damper/
    └── index.html             # 독립 실행되는 기존 시뮬레이터
```

메인 페이지의 Rotational System, DC Motor, Pole-Zero Explorer, System Identification은 계획된 모듈입니다. 아직 구현되지 않았으므로 링크와 빈 실험 폴더를 만들지 않았습니다.

## 기존 GitHub 저장소에 업로드하기

1. 제공된 ZIP을 **먼저 압축 해제**합니다. ZIP 파일 자체를 업로드하면 사이트가 바뀌지 않습니다.
2. [저장소](https://github.com/janghyesoo/Dynamic-System-Virtual-Lab)를 열고 `main` 브랜치의 최상위 파일 목록으로 이동합니다.
3. **Add file → Upload files**를 선택합니다.
4. 압축을 푼 폴더 **안의 내용물**인 `index.html`, `README.md`, `LICENSE`, `vertical-translational-mass-spring-damper` 폴더를 함께 드래그합니다. 압축 해제된 바깥 폴더 자체를 올려 경로가 한 단계 더 생기지 않도록 주의하세요.
5. 업로드 목록에 `index.html`과 `vertical-translational-mass-spring-damper/index.html`이 각각 보이는지 확인합니다. 기존 root `index.html`과 `README.md`는 새 파일로 교체됩니다. `LICENSE`는 기존 내용과 같습니다.
6. Commit message에 `Organize virtual labs and add laboratory landing page`를 입력하고 `main`에 commit합니다.

## GitHub Pages 설정

저장소 **Settings → Pages → Build and deployment**에서 다음을 선택하고 **Save**합니다.

- Source: **Deploy from a branch**
- Branch: **main**
- Folder: **/(root)**

이미 이 설정이라면 다시 변경할 필요 없습니다. `main`에 변경사항을 올리면 Pages 배포가 실행됩니다. **Actions**에서 배포 성공을 확인한 뒤 **Settings → Pages**에 표시되는 사이트 링크를 여세요.

- 메인: https://janghyesoo.github.io/Dynamic-System-Virtual-Lab/
- 첫 실험: https://janghyesoo.github.io/Dynamic-System-Virtual-Lab/vertical-translational-mass-spring-damper/

기존 root 주소는 이제 메인 페이지를 엽니다. D2L에서 실험을 바로 열게 하려면 첫 실험 주소로 바꾸고, 전체 실험 목록을 제공하려면 메인 주소를 사용하세요.

[GitHub 공식 Pages 설정 가이드](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site)

## 새 실험 추가하기

1. 저장소 최상위에 `rotational-system`, `dc-motor`, `pole-zero-explorer`, `system-identification`처럼 영문 소문자와 하이픈으로 폴더를 만듭니다.
2. 해당 폴더 안에 새 실험의 `index.html`을 넣습니다. 해당 실험만 사용하는 이미지·CSS·JS는 같은 폴더 안에 두고 상대경로로 연결합니다.
3. root `index.html`의 `featured` 카드 구조를 복사하거나 해당 `planned` 카드를 실제 실험 카드로 교체합니다. 제목·설명·상태와 링크를 수정하고 이용 가능한 실험 수를 갱신합니다.
4. 링크는 `./dc-motor/index.html`처럼 작성합니다. `/dc-motor/`처럼 `/`로 시작하면 GitHub Pages의 저장소 경로를 벗어날 수 있습니다.
5. 새 실험에 `<a href="../index.html">← All Labs</a>`를 넣고 README의 실험 목록을 갱신합니다.
6. 폴더와 메인 페이지를 함께 commit합니다. 새로운 저장소나 Pages 설정은 필요 없습니다.

공통 디자인 파일이 필요해지면 최상위 `assets/` 폴더를 추가할 수 있습니다. 현재 시뮬레이터는 기존 스타일과 기능 간섭을 피하도록 독립적인 단일 HTML로 유지합니다.

## 로컬 확인 및 배포 후 점검

압축을 푼 뒤 root `index.html`을 브라우저에서 열어도 사용할 수 있습니다. 메인 → Open Lab → All Labs 이동을 확인하세요.

- 데스크톱·태블릿·휴대폰 화면에서 레이아웃 확인
- m/b/k 조절 시 수식·pole·감쇠 상태 갱신 확인
- Run/Pause, Reset, Pull & Release 및 질량 드래그 확인
- Free/Step/Pulse/Sine 입력, 속도·주파수 선택 확인
- 표현 탭 및 Derivations 펼치기 확인

## License

기존 [MIT License](./LICENSE)를 유지합니다.
