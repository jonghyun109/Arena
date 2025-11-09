<div align="center">
 

# [<img width="60" height="60" alt="Youtube_logo" src="https://github.com/user-attachments/assets/8e31fdca-af1b-4ebc-b2c9-cdb9983454b4" />](https://www.youtube.com/watch?v=YOUR_VIDEO_ID)  Arena 모작

### 실시간 4인 대전! 롤 챔피언으로 즐기는 팀 배틀 AOS

<br>

<table>
  <tr>
    <td align="center" width="33%">
      <img src="https://github.com/user-attachments/assets/64c29cfb-82ad-4673-aa4f-a88311d303ac" alt="리그 오브 레전드 챔피언 전투" width="100%"/>
      <br/>
      <b>리그 오브 레전드 챔피언 전투</b>
    </td>
    <td align="center" width="33%">
      <img src="https://github.com/user-attachments/assets/0b5b7285-9e7d-4609-9c52-a9cff7c269ae" alt="로그인 화면" width="100%"/>
      <br/>
      <b>로그인 화면</b>
    </td>
    <td align="center" width="33%">
      <img src="https://github.com/user-attachments/assets/c1bce44f-ec46-40e1-92f8-93d5591878ac" alt="아레나 게임 플레이" width="100%"/>
      <br/>
      <b>아레나 게임 플레이</b>
    </td>
  </tr>
</table>



<br>
<br>

⭐ **4명의 독특한 리그 오브 레전드 챔피언으로 펼치는 전략 전투**

⭐ **유명게임인 리그오브레전드의 모드 아레나를 기반으로 모작**

</div>

<br>
<br>
<br>


---

</div>

<br>
<br>

## 📋 목차

- [게임 소개](#-게임-소개)
- [프로젝트 개요](#-프로젝트-개요)
- [주요 스크립트](#-주요-스크립트)
  - [인증 및 회원가입](#-인증-및-회원가입)
  - [로비 및 매칭 시스템](#-로비-및-매칭-시스템)
  - [인게임 관리](#-인게임-관리)
  - [체력바 시스템](#-체력바-시스템)
  - [전장의 안개 시스템](#-전장의-안개-시스템)
  - [Vayne 캐릭터 시스템](#-vayne-캐릭터-시스템)
- [기술 스택](#-주요-기술-스택)
- [참고사항](#-참고사항)
- [개발자](#-개발자)

<br>
<br>

---

<br>
<br>

## 🎯 게임 소개

**ArenaJjap**은 유명게임 리그 오브 레전드의 아레나 모드를 기반으로 모작한 **실시간 4인 대전 팀 배틀 AOS 게임**입니다.  
Ryze, Sion, Tryndamere, Vayne 등 **4명의 독특한 리그 오브 레전드 챔피언**으로 펼치는 전략 전투를 즐길 수 있습니다.  
Photon PUN2를 활용한 실시간 매칭 시스템, 상태 패턴 기반의 정교한 캐릭터 제어, 전장의 안개 시스템, Firebase 인증 연동으로 완성도 높은 멀티플레이어 경험을 제공합니다.

<br>
<br>

---

<br>
<br>

## 📌 프로젝트 개요

| 항목     | 내용                          |
|----------|-------------------------------|
| 유형     | 네트워크 팀 프로젝트           |
| 기간     | 2025.03.17 ~ 2025.04.03 (14일) |
| 인원     | 개발자 4명                     |
| 도구     | Unity, Photon PUN2, Firebase  |

<br>
<br>

---

<br>
<br>

# 📁 YJH Scripts

> ArenaJjap 프로젝트의 YJH 폴더 스크립트 모음입니다.

<br>
<br>

---

## 💻 주요 스크립트

<br>

## 🔐 인증 및 회원가입

<br>

### [`AuthManager.cs`](https://github.com/jonghyun109/ArenaJjap/blob/main/Assets/Scripts/YJH/IntroSceneScript/AuthManager.cs)

**💡 기능**: Firebase 인증 및 Photon 네트워크 연동 관리

**📌 주요 기능**:
- Firebase 이메일/비밀번호 기반 회원가입 및 로그인
- 닉네임 설정 및 Firebase DisplayName 저장
- 로그인 성공 시 Photon 서버 자동 연결
- 로딩 패널 및 에러 메시지 처리

**📌 주요 메서드**:
- `Login()`: 로그인 코루틴 시작
- `Register()`: 회원가입 코루틴 시작
- `SaveNickName()`: 닉네임 Firebase에 저장
- `OnConnectedToMaster()`: Photon 연결 후 로비 씬 이동

**✨ 특징**: 
- Enter 키 입력으로 로그인 가능
- 로딩 스피너 회전 애니메이션
- Firebase 에러 코드별 한글 메시지 처리

<br>

### [`RegisterManager.cs`](https://github.com/jonghyun109/ArenaJjap/blob/main/Assets/Scripts/YJH/IntroSceneScript/RegisterManager.cs)

**💡 기능**: 회원가입 UI 및 약관 동의 처리

**📌 주요 기능**:
- 약관 동의 3개 체크박스 검증
- 모든 약관 동의 시 다음 버튼 활성화
- 회원가입 패널 표시 및 닫기

**✨ 특징**: Toggle 3개 모두 체크 시에만 계정 생성 가능

<br>

### [`VideoManager.cs`](https://github.com/jonghyun109/ArenaJjap/blob/main/Assets/Scripts/YJH/IntroSceneScript/VideoManager.cs)

**💡 기능**: 로그인 화면 배경 비디오 제어

**📌 주요 기능**:
- 비디오 음소거 토글
- 비디오 애니메이션 정지 (정적 이미지로 전환)

**✨ 특징**: 사용자가 배경 영상의 재생과 음소거를 제어 가능

<br>
<br>

---

<br>
<br>

## 🏠 로비 및 매칭 시스템

<br>

### [`LobbyManager.cs`](https://github.com/jonghyun109/ArenaJjap/blob/main/Assets/Scripts/YJH/LobbyManager.cs)

**💡 기능**: 로비 UI 관리 및 Photon 매칭 시스템

**📌 주요 기능**:
- 4인 랜덤 매칭 시스템
- 매칭 타이머 (분:초 형식)
- 매칭 완료 시 수락 패널 활성화
- 15초 수락 타이머 (이미지 FillAmount로 시각화)
- 모든 플레이어 수락 시 게임 시작
- 매칭 취소 및 방 나가기

**📌 주요 메서드**:
- `StartMatchmaking()`: 랜덤 방 참가 시도
- `OnJoinRandomFailed()`: 방 없으면 새로 생성
- `OnJoinedRoom()`: 4명 모이면 수락 버튼 활성화
- `AcceptMatch()`: 플레이어 수락 RPC 전송
- `PlayerAccepted()`: 4명 모두 수락 시 게임 시작
- `CancelMatch()`: 매칭 취소 및 방 나가기

**✨ 특징**: 
- Photon RPC를 통한 실시간 동기화
- 타이머 이미지로 직관적인 UI
- 닉네임 표시

<br>

### [`MatchManager.cs`](https://github.com/jonghyun109/ArenaJjap/blob/main/Assets/Scripts/YJH/MatchManager.cs)

**💡 기능**: 캐릭터 선택 및 팀 구성 시스템

**📌 주요 기능**:
- 4명의 플레이어를 블루팀/레드팀으로 자동 분배
- 캐릭터 선택 (Ryze, Sion, Tryn, Vayne)
- 랜덤 캐릭터 선택 (팀원이 선택하지 않은 챔피언 중)
- 선택한 캐릭터 프로필 이미지 동기화
- Ready 시스템 및 게임 시작
- 선택된 캐릭터는 다른 팀원이 선택 불가

**📌 주요 메서드**:
- `AssignTeams()`: 마스터 클라이언트가 팀 분배
- `SyncTeams()`: RPC로 모든 클라이언트에 팀 정보 동기화
- `OnChampionClick(int index)`: 캐릭터 선택 및 동기화
- `OnRandomChampionClick()`: 랜덤 캐릭터 선택
- `OnReadyClick()`: 준비 완료 및 커스텀 프로퍼티 저장
- `PlayerReady()`: 4명 모두 준비되면 게임 시작

**✨ 특징**: 
- ActorNumber 기반 팀 배정
- myChampionIndex를 static 변수로 저장하여 인게임에서 사용
- 캐릭터 선택 시 배경 이미지 변경
- GameManager에 팀 정보 전달

<br>
<br>

---

<br>
<br>

## 🎮 인게임 관리

<br>

### [`InGameManager.cs`](https://github.com/jonghyun109/ArenaJjap/blob/main/Assets/Scripts/YJH/InGameManager.cs)

**💡 기능**: 인게임 캐릭터 생성 및 체력바 설정

**📌 주요 기능**:
- MatchManager에서 저장한 myChampionIndex로 캐릭터 생성
- ActorNumber에 따라 스폰 위치 지정
- 블루팀/레드팀 태그 설정 (RPC 동기화)
- 모든 플레이어에게 체력바 생성
- 캐릭터별 UI Canvas 활성화

**📌 주요 메서드**:
- `SpawnMyChampion()`: 선택한 캐릭터를 지정된 위치에 생성
- `SetupAllHealthBars()`: 1초 후 모든 플레이어의 체력바 생성

**✨ 특징**: 
- championNames 배열로 프리팹 이름 관리
- PhotonNetwork.Instantiate로 네트워크 오브젝트 생성
- 체력바의 useLocalData를 IsMine 여부로 설정

<br>

### [`RoundCheck.cs`](https://github.com/jonghyun109/ArenaJjap/blob/main/Assets/Scripts/YJH/RoundCheck.cs)

**💡 기능**: 라운드 정보 UI 동기화

**📌 주요 메서드**:
- `Init()`: PhotonView와 라운드 번호 초기화
- `RoundChecking()`: 라운드 UI 업데이트 RPC 전송
- `ShowRound()`: 모든 클라이언트에서 라운드 텍스트 표시

**✨ 특징**: 마스터 클라이언트만 GameManager.RC에 저장

<br>

### [`init.cs (AutoConnectSolo)`](https://github.com/jonghyun109/ArenaJjap/blob/main/Assets/Scripts/YJH/init.cs)

**💡 기능**: 솔로 테스트용 자동 Photon 연결

**📌 주요 기능**:
- Photon 서버 자동 연결
- 1인 전용 비공개 방 생성 (SoloRoom)

**✨ 특징**: 
- AutomaticallySyncScene = false (씬 동기화 비활성화)
- 테스트 목적의 스크립트

<br>
<br>

---

<br>
<br>

## ❤️ 체력바 시스템

<br>

### [`HealthBar.cs`](https://github.com/jonghyun109/ArenaJjap/blob/main/Assets/Scripts/YJH/HealthBar.cs)

**💡 기능**: 플레이어 머리 위 체력바 UI

**📌 주요 기능**:
- 타겟 플레이어의 HP를 실시간으로 fillAmount에 반영
- 체력바를 카메라 방향으로 회전 (빌보드)
- offset으로 플레이어 위치에서의 상대 위치 조정
- useLocalData: 로컬 플레이어는 직접 데이터 참조, 원격 플레이어는 네트워크 데이터 사용

**📌 주요 메서드**:
- `Update()`: 매 프레임 HP 비율 계산 및 위치/회전 업데이트
- `UpdateFromNetwork()`: 네트워크로 받은 HP 데이터로 업데이트

**✨ 특징**: 
- 로컬/원격 플레이어 구분하여 최적화
- Mathf.Clamp01로 0~1 범위 보장

<br>

### [`HealthBarNetworkSync.cs`](https://github.com/jonghyun109/ArenaJjap/blob/main/Assets/Scripts/YJH/HealthBarNetworkSync.cs)

**💡 기능**: 체력바 네트워크 동기화

**📌 주요 기능**:
- 로컬 플레이어의 HP를 다른 플레이어들에게 RPC 전송
- FixedUpdate에서 주기적으로 동기화
- isReady 플래그로 character가 준비될 때까지 대기

**📌 주요 메서드**:
- `FixedUpdate()`: IsMine일 경우 HP 데이터를 RPC로 전송
- `UpdateHPBar()`: RPC로 받은 HP 데이터를 체력바에 반영

**✨ 특징**: 
- PhotonView.IsMine 체크로 중복 전송 방지
- RpcTarget.Others로 자신 제외하고 전송

<br>
<br>

---

<br>
<br>

## 🌫️ 전장의 안개 시스템

<br>

### [`FieldOfView.cs`](https://github.com/jonghyun109/ArenaJjap/blob/main/Assets/Scripts/YJH/FogofWar/FieldOfView.cs)

**💡 기능**: 시야 범위 감지 및 메시 생성

**📌 주요 기능**:
- 시야 범위(viewRadius) 및 시야 각도(viewAngle) 설정
- 시야 내의 타겟 감지 (Physics.OverlapSphere)
- 장애물에 가려진 타겟 제외 (Raycast 체크)
- 시야 영역 메시 동적 생성

**📌 주요 메서드**:
- `FindVisibleTargets()`: 0.2초마다 시야 내 타겟 탐색
- `DrawFieldOfView()`: 시야 범위를 메시로 그리기
- `ViewCast()`: 특정 각도에서 장애물까지의 거리 계산
- `DirFromAngle()`: 각도를 3D 방향 벡터로 변환

**✨ 특징**: 
- targetMask: 감지할 대상 레이어
- obstacleMask: 시야를 가리는 장애물 레이어
- meshResolution: 메시 정밀도 조절

<br>

### [`FogProjector.cs`](https://github.com/jonghyun109/ArenaJjap/blob/main/Assets/Scripts/YJH/FogofWar/FogProjector.cs)

**💡 기능**: 전장의 안개 텍스처 블렌딩 및 프로젝션

**📌 주요 기능**:
- 렌더 텍스처 2개를 사용한 전장의 안개 잔상 효과
- 블러 셰이더로 자연스러운 안개 연출
- 프로젝터를 통해 지형에 안개 텍스처 투영
- 블렌드 애니메이션으로 부드러운 전환

**📌 주요 메서드**:
- `OnEnable()`: 렌더 텍스처 및 머터리얼 초기화
- `UpdateFog()`: 텍스처 블러 처리 및 블렌딩 시작
- `Blend()`: 코루틴으로 텍스처 블렌드 값을 0→1로 증가

**✨ 특징**: 
- upsample: 텍스처 해상도 배율
- blendSpeed: 블렌딩 속도 조절
- _FogTex, _OldFogTex 셰이더 프로퍼티 사용

<br>

### [`Solidify.cs`](https://github.com/jonghyun109/ArenaJjap/blob/main/Assets/Scripts/YJH/FogofWar/Solidify.cs)

**💡 기능**: 카메라 렌더링 셰이더 교체

**📌 주요 기능**:
- flatShader로 카메라의 렌더링 셰이더 교체
- ExecuteInEditMode: 에디터에서도 실행

**✨ 특징**: SetReplacementShader로 모든 오브젝트를 특정 셰이더로 렌더링

<br>
<br>

---

<br>
<br>

## 🏹 Vayne 캐릭터 시스템

<br>

### [`VayneState.cs`](https://github.com/jonghyun109/ArenaJjap/blob/main/Assets/Scripts/YJH/VayneState/VayneState.cs)

**💡 기능**: Vayne 캐릭터의 상태 패턴 기반 컨트롤러

**📌 주요 기능**:
- IVayneState 인터페이스 기반 상태 전환
- Q 스킬: 구르기 (Tumble) - 일반/궁극기 버전
- E 스킬: 밀쳐내기 (Condemn) - 벽에 박으면 기절 및 추가 피해
- R 스킬: 최후의 시간 (Final Hour) - 이동속도 및 공격력 증가
- W 패시브: 3타 시 적 최대 HP의 10% 고정 피해

**📌 주요 메서드**:
- `ChangeState(IVayneState newState)`: 상태 전환 (Exit → Enter)
- `SkillQ()`: 구르기 스킬 (궁 여부에 따라 다른 상태)
- `SkillE()`: 밀쳐내기 스킬 (넉백 + 벽 충돌 체크)
- `SkillR()`: 궁극기 (UltState로 전환)
- `AutoAttack()`: 기본 공격 + W 패시브 적용
- `VayneWSkill()`: 3타 적중 시 추가 피해
- `WallCheck()`: 넉백 중 벽 충돌 시 스턴 및 추가 피해

**✨ 특징**: 
- OnAutoAttackGlobal 이벤트로 상태 전환 트리거
- 마지막 공격 대상 추적 (lastAttackedTarget)
- 이펙트 관리 (firstHit, secondHit)

<br>

### [`DefaultState.cs`](https://github.com/jonghyun109/ArenaJjap/blob/main/Assets/Scripts/YJH/VayneState/DefaultState.cs)

**💡 기능**: Vayne의 기본 상태

**✨ 특징**: 
- 이동 속도를 애니메이션 파라미터로 전달
- Walk 애니메이션 적용
- TumbleWalk을 0으로 초기화

<br>

### [`TumbleState.cs`](https://github.com/jonghyun109/ArenaJjap/blob/main/Assets/Scripts/YJH/VayneState/TumbleState.cs)

**💡 기능**: Vayne Q 스킬 (일반 구르기) 상태

**📌 주요 기능**:
- targetLocation 방향으로 4f 거리 이동
- 구르기 애니메이션 재생
- 평타 시 또는 3초 후 DefaultState로 복귀
- 공격력 증가 (+115.14)

**✨ 특징**: 
- OnAutoAttackGlobal 이벤트 구독/해제
- TumbleWalk 애니메이션 파라미터 사용

<br>

### [`UltState.cs`](https://github.com/jonghyun109/ArenaJjap/blob/main/Assets/Scripts/YJH/VayneState/UltState.cs)

**💡 기능**: Vayne R 스킬 (궁극기) 상태

**📌 주요 기능**:
- 이동속도 +90
- 공격력 +65
- Q 쿨타임 1초로 감소
- 16초 지속

**✨ 특징**: 
- IsUlt 플래그 true로 설정
- IsUlt 애니메이션 Bool 파라미터
- 시간 종료 시 DefaultState로 복귀 및 스탯 원복

<br>

### [`UltTumbleState.cs`](https://github.com/jonghyun109/ArenaJjap/blob/main/Assets/Scripts/YJH/VayneState/UltTumbleState.cs)

**💡 기능**: Vayne 궁극기 중 Q 스킬 (은신 구르기) 상태

**📌 주요 기능**:
- 궁극기 활성화 중 Q 사용 시 진입
- UltTumbleIdle 애니메이션
- 3초 후 UltState로 복귀

**✨ 특징**: 
- 일반 TumbleState와 달리 UltState로 돌아감
- UltTumbleWalk 애니메이션 파라미터 사용

<br>
<br>

<br>
<br>

---

<br>
<br>

## 🔧 주요 기술 스택

<br>

- 🌐 **Photon PUN2**: 멀티플레이어 네트워킹 (매칭, RPC, 동기화)
- 🔥 **Firebase**: 인증(Authentication) 및 실시간 데이터베이스
- 🎯 **Unity 2022.3 (URP)**: 게임 엔진
- 🎨 **Amplify Shader Editor**: 전장의 안개 셰이더 제작
- 📝 **TextMeshPro**: UI 텍스트

<br>
<br>

---

<br>
<br>

## 📝 참고사항

<br>

💡 **네트워크 아키텍처**
- Photon PUN2의 RPC와 CustomProperties를 활용한 실시간 동기화
- 마스터 클라이언트 기반 팀 분배 및 스폰 관리

💡 **상태 패턴**
- IVayneState 인터페이스로 캐릭터 상태 분리
- EnterState, UpdateState, ExitState로 상태별 로직 관리
- 확장 가능한 구조로 다른 챔피언 추가 용이

💡 **전장의 안개**
- 메시 기반 시야 시스템과 셰이더 블렌딩 조합
- 렌더 텍스처 2개를 활용한 잔상 효과
- 프로젝터로 지형에 안개 투영

💡 **Firebase 연동**
- 이메일/비밀번호 인증 및 DisplayName 저장
- 에러 코드별 한글 메시지 처리
- Photon NickName과 Firebase DisplayName 연동

<br>
<br>

---

<br>
<br>

<div align="center">

## 👨‍💻 개발자

<br>

**YJH (윤종현)**

<br>
<br>

[![GitHub](https://img.shields.io/badge/GitHub-jonghyun109-181717?style=for-the-badge&logo=github)](https://github.com/jonghyun109/ArenaJjap)

<br>

**📌 모든 스크립트 링크는 위의 GitHub 저장소에서 확인할 수 있습니다.**

</div>

<br>
<br>
