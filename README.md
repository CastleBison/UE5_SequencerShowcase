# UE5_SequencerShowcase

Unreal Engine 5 Sequencer(시퀀서) 학습 및 컷신/카메라 연출 연습 내용을 정리하는 프로젝트입니다.

- 목표: 시퀀서 기본기 + 컷신 구성 + 카메라 연출 반복 연습
- 결과물: 레벨(맵) + 레벨 시퀀스(Level Sequence) + 렌더 출력(선택)

---

## Engine / Requirements

- Unreal Engine: 5.7
- 플랫폼: Windows 권장
- (선택) Git LFS: 대용량 uasset/영상 출력물을 버전관리하려면 권장

---

## 프로젝트 열기

1) 레포 클론
git clone https://github.com/CastleBison/UE5_SequencerShowcase.git

2) 프로젝트 실행
- SequencerShowcase.uproject 더블 클릭
- 처음 열면 셰이더 컴파일이 오래 걸릴 수 있음

---

## 빠른 실행(재생) 방법

방법 A) 레벨 시퀀스를 에디터에서 바로 재생
1. Content Browser에서 Level Sequence 에셋 선택
2. 더블 클릭해서 Sequencer 창 오픈
3. Space(재생) 또는 상단 Play 버튼

방법 B) 레벨에서 시네마틱처럼 자동 재생
- 레벨에 Level Sequence Actor 배치
- 해당 Actor에 Sequence 지정
- Auto Play 또는 블루프린트로 BeginPlay에 Play 호출

---

## 렌더(영상 뽑기) 방법

추천: Movie Render Queue 사용
1. Sequencer 창에서 Render(또는 Movie Render Queue) 실행
2. Output 해상도/프레임/코덱/저장 경로 설정
3. Render Local

권장 프리셋(예시)
- 1080p / 30fps 또는 60fps
- Anti-aliasing: Temporal Sample 적당히
- Output: PNG Sequence 또는 ProRes(가능하면)

---

## 연습 주제 체크리스트(아이디어)

- 컷 분할: Shot Track / Camera Cut Track
- 카메라 기본: Focal Length, Aperture, Focus Distance
- 키프레임: 위치/회전, Ease In/Out, 속도감
- 타이밍: 음악/효과음 기준으로 컷 타이밍 맞추기
- 레이어: 캐릭터/프랍/라이트 애니메이션 분리
- 룩: Post Process + 노출 고정 + 컬러 무드 테스트
- 마스터 구성: 여러 샷을 Master Sequence로 묶어 관리

---

## 트러블슈팅(자주 겪는 것)

- 재생하면 카메라가 안 바뀜
  - Camera Cut Track이 있는지 확인
  - 레벨에서 플레이할 때는 해당 시퀀스가 실제로 Play 되고 있는지 확인

- 오토포커스가 튀어서 화면이 불안정함
  - Focus Method를 Manual로 고정하거나, Tracking 대상/거리 값을 명확히 지정

- 렌더 결과가 에디터 뷰와 다름
  - 노출(Exposure) 고정, Post Process Volume 적용 범위(무한/Bounded) 확인
  - Movie Render Queue의 렌더 설정(AA/샘플링/톤매핑) 차이 확인

---

