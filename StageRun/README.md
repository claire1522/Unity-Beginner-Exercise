## Chapter 6: StageRun, 장애물 달리기 게임
### 1. 장애물
- 움직이는 상자: 리지드바디 O
- 움직이지 않는 상자: 리지드바디X, 물리적 동작 반영 안됨

### 2. 카메라 설정 
- MultipurposeCameraRig: 플레이어를 따라다니며 플레이어가 향한 방향이 정면이 되도록 회전하는 카메라

### 3. 목표 지점 설정
- Mesh Renderer >Rremove Component or 비활성화
- is Trigger 활성화

### 4. 타이머 기능
- public static float time;
- time += Time.deltaTime;

### 5. 최고 기록 시간
- PlayerPrefs: 유니티로 게임 데이터 저장

### 6. 추락시 다시 시작: 낙하 판정 처리
- Mesh Renderer >Rremove Component or 비활성화
- is Trigger 활성화: 충돌판정이 기능하지 않고 플레이어는 한없이 떨어짐.
그 영역에 오브젝트가 접촉했을 때의 처리를 스크립트로 직접 작성할 수 있음.
- 처음화면으로: SceneManager.LoadScene(SceneManager.GetActiveScene().name);

### 7. 오디오
- Audio Listener 컴포넌트: 소리를 듣는 귀의 역할, 소리를 담는 마이크 역할, 카메라에 기본적으로 Audio Listener 설정됨.
- Audio Source 컴포넌트: 소리의 발생원
- Spacial Blend: 3D설정으로 바뀌어 거리에 따라 음량이 달라짐

### 8. 처리 부담 줄이기
- Occlustion Culling:  카메라에 비치지 않는(게임 뷰에 표시되지 않는) 오브젝트 그리지 않기. 
- 오브젝트 선택> Static 체크 > Window-Rendering-Occlusion Culling-Visualisztion-Bake
