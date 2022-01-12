- **Update History**
  - v0.9.8.9 : 2022.01.11 (HOTFIX-1)
    - HOTFIX
	  - [Client] UE5.0EA에서 로비/로그인/캐릭터 생성 UI의 Text 출력이 비정상적으로 보이던 문제 수정 (#918)
	  - [Action Editor] '프리뷰 씬으로 이동' 아이콘이 출력되지 않던 문제 수정 (#906)
    - New feature or Enhancement
	  - Editor
	    - [Quest Flow] GraphNode Thumbnail 크기 제한(최대 140x130) 및 정렬, 레이아웃, 컬러 조정 (#909)
	    - [Quest Flow] GraphNode의 Thumbnail 알림 표시 이미지 세분화 (NoImage, Exclamation, Question) (#906)
		  - NoImage(Verbose), Exclamation(Warning), Question(Error) 대응
		  - Exclamation는 현재 Reward를 설정하지 않았을 경우 출력
	    - [Quest Flow] Quest 중, Mission, Dialogue, Action, Branch 하위 노드 진행 조건 판단 로직 변경 (#881)
		  - Service Condition 류에서 Decorator Condition 류로 기능 전환
		- [Quest Flow] ActionMovePath에서 WaypointName을 Quest Action Type 형으로만 제한 (#898)
		- [Entity Editor] Entity에서 사용하는 에셋의 출처를 남길 수 있는 'Marketplace' 탭 추가 (Zone Entity 제외) (#915)
	  - Common
		- [Client/Editor] Widet영상 출력 기능 지원-2DMedia (#870)
	- Bugfix
	  - Client or Server
	    - [Content Editor] SpawnObject Rename 시 간헐적으로 이전 모델이 출력되던 문제 수정 (#916)
	    - [Quest Flow] Spawn Object - Event Trigger - NPC 선택으로 이벤트 발현이 안 되는 문제 수정 (#876)
		- [Quest Flow] ChainQuest 기능이 동작하는 않는 문제 수정 (#897)
		- [Quest Flow] AcionMovePath Node 반응 속도가 늦어지는 문제 수정 (#882)
		- [Quest Flow] Portrait Name의 Animation이 지정되어 있다면 Animation 연출이 되도록 기능 수정 (#735)
		- [Quest Flow] Dialogue ReturnType과 별개로 UseLookat이라면 카메라 전환 (#735)
		   - UseLookat 이더라도 화자 전환이 없으면 카메라 전환 안 됨
        - [Quest Flow] Quest Abort가 되었을 때, Quest Start, Finish UI가 출력되는 문제 수정 (#884)
		- [Entity Editor] Character Fullbody Skin, Override Material Item 선택 시 편집 불가 문제 수정 (#912)
	  - Editor
	    - [Quest Flow] MissionPlay Node의 MissionObjectFilter 선택 시 GUID Droplist 미출력 문제 수정 (#892)
	    - [Entity Editor] Costume Entity의 AttachParts AttachMeshType::Groom 변경 시 Manipulator가 남아있던 문제 수정 (#902)
	    - [Entity Editor] MaterialOverride에 Material 설정 시 전체 DetailView가 Refresh 되던 문제 수정 (#905)
  - v0.9.8.8 : 2022.01.09
    - New feature or Enhancement
	  - Client or Server
		- [Client] Skeleton 본 구조가 다른 캐릭터의 Partial Blending/Aim/FootIK를 사용할 수 있도록 기능 개선 (#885)
		  - 기본 AnimBP가 일괄 업데이트 되었고, T4Framework 전용 AnimGraphNode가 추가되었음. 타 프로젝트에서 사용 불가
		  - Entity Editor, Animation 탭 내 AnimNode Setup 프로퍼티의 BoneName을 선택해 동작하도록 변경 됨
	  - Editor
	    - [Quest Flow] SpawnObject Guid Candidates DropList Item 표시를 'ID {Guid}'로 표시하도록 개선 (#890)
	    - [Quest Flow] GraphNode의 설정 오류 (물음표) / 썸네일 미설정 시 별도의 Thumbnail 표시 추가 (#906)
		- [Action Editor] Animation Action 내 'bDisablePartialBlending' 옵션 추가 (#888)
		  - Movement Action이 이동으로 간주 상하체 블랜딩이 동작하는데, 풀바디 애니메이션을 사용하고 싶을 경우 해당 옵션 사용
		- [Entity Editor] Costume AttachParts로 GroomType 선택 시는 RelativeTransform 설정없이 Attach되도록 개선 (Hetahuman) (#908)
		  - Groom Target Parts Name으로 어떤 Modular Parts에 붙일지 옵션이 추가됨 (Metahuman의 경우 "Head" 사용)
		  - GroomType 선택 시는 RelativeTransform 설정이 없음으로 Manipulator도 출력되지 않음에 유의
	    - [Editor Common] 에디터 툴바 아이콘 교체 (UE4 & UE5) (#906)
	  - Common
	    - [Client/Server] AttachType Dash 사용 시 타겟이 없을 경우 픽킹 위치로 캐릭터 회전이 동작하지 않던 문제 수정 (#888)
		  - AttackType Launch 기능은 삭제 (캐릭터가 발사체로 동작하는 걸 가정한 기능인데, 다른 기능으로 대체 가능해 삭제함)
	- Bugfix
	  - Client or Server
	    - [Server] AoE 스킬 효과로 Area => Hit를 사용할 경우 데미지가 정상적으로 적용되지 않던 문제 수정 (#900)
	    - [Server] 스킬 시전 시 Weapon의 ItemStatDB가 적용되지 않던 문제 수정 (#891)
	  - Editor
	    - [Quest Flow] MissionPlay Node의 MissionObjectFilter 프로퍼티 미출력 문제 수정 (#892)
	    - [Quest Flow] Mission Node의 MissionObjectFilter의 World GameDB 바로가기 버튼이 동작하지 않던 문제 수정 (#893)
	    - [Quest Flow] 한 퀘스트 내에 Dialogue 조건이 Auto와 Interaction이 공존하면, 퀘스트 수행시 크래시 나는 문제 수정 (#879, #867)
		- [Entity Editor] Costume AttachParts의 Groom 설정 시 GroomAsset만 설정할 경우 CostumeMesh가 사라지던 문제 수정 (#903)
		- [Entity Editor] Costume AttachParts의 Item Manipuator 편집 오류 및 초기 선택이 정상적으로 동작하지 않던 문제 수정 (#902)
		- [Entity Editor] Costume AttachParts Details에서 RelativeTransform 수정이 반영되지 않던 문제 수정 (#902)
		- [Entity Editor] Costume Entity에서 AttachParts Manipulator의 Rotation/Scale 변경이 되지 않던 문제 수정 (#901)
		  - 뷰포트의 R키가 캐릭터 스탠스 변경과 겹쳐 EditMode가 켜질 경우 무기/스탠스 교체가 되지 않도록 수정
		- [Entity Editor] Costume Entity의 AttachParts 삭제 시 캐릭터의 파츠 모델이 삭제되지 않는 문제 수정 (#904)
	    - [Entity Editor] Character Entity의 Test Weapon 착용 시 간헐적 크래시 수정 (#886)
	    - [Editor Common] Entity/Action Editor등의 테스트용 ProjectID 설정에 ServiceEnabled 프로젝트만 노출되던 문제 수정 (#888)
	    - [Editor Common] GameProject 전체 경로 이동 시 GameMasterTable을 읽지 못하던 문제 수정 (#894)
  - v0.9.8.7 : 2022.01.04
    - New feature or Enhancement
	  - Client or Server
	    - [Server] Quest 중단을 처리할 수 있는 QuestAbort Task 기능 추가 (#878)
	  - Editor
	    - [Content Editor] Skill/Effect DB의 Attack/EffectType ShapeData 설정을 DetailGroup Header Title로 노출 (#877)
	    - [Content Editor] SpawnLayer Rename 시 마지막 편집 카메라 위치를 유지하도록 개선 (#863)
		- [Quest Flow] Quest 완료 조건을 개별 객체별로 지정하여 모든 조건이 완료됨을 검사하는 Spawn Target 형 Mission Rule 구현 (#839)
		- [Entity Editor] 캐릭터 AnimSet StateLayer에 걷기용 AimSequence와 MoveSpeed Parameter 추가 (#742)
		- [Entity Editor] 상당 툴바에 편집 중인 플레이어 캐릭터로 카메라 포커스를 이동하는 "플레이어 포커스" 버튼 추가 (#875)
		- [Entity Editor] Prop Entity, ModularParts ListView의 Item 더블클릭으로 카메라 포커스 이동 기능 추가 (#875)
	- Bugfix
	  - Client or Server
	    - [Server] 인벤토리에서 무기 교체 시 기존 아이템 탈착이 되지 않던 문제 수정 (#869)
		- [Server] QuestSample1 프로젝트, Quest1 DB 수행 도중 발생하는 크래쉬 수정 (#867)
	  - Editor
	    - [Quest Flow] Action Composite에 첫 번째 등록한 Guid값이 ActionMovePath, ActionStagePlay에서 선택될 수 없는 상황 개선 (#866)
	  - Common
	    - [Common] Skill/Effect DB의 AttackType Air, EffectType Knockback/Airborne 옵션 사용 시 간헐적 크래시 수정 (#877)
  - v0.9.8.6 : 2022.01.02
    - New feature or Enhancement
	  - Editor
	    - [Content Editor] ItemPackDB에 등록된 모든 ItemPackageData의 타 프로젝트로 Migration 지원 (#859)
	    - [Entity Editor] Weapon Entity, 선택한 Attach/Mount 포인트가 모델에 없을 경우에 대한 메시지 추가 (#853)
		  - EquipMesh/ExchangeMesh Tab의 Attach/MountPoint Droplist에 존재하는 액션포인트 표시 추가
	  - Common
	    - [Common] Game/UI/Editor MessageTable에 영문 번역이 없을 경우 "(MsgID)한글"로 화면에 출력되도록 수정 (#853)
		  - 단, 위 기능은 Shpping 빌드와 에디터 상수 테이블은 제외
	- Bugfix
	  - Editor
	    - [Content Editor] OtherPC의 장착 무기/코스튬이 보이지 않던 문제 수정 (#607)
	    - [Action Editor] 테스트용 Project의 Weapon/CostumeDB 장착 및 해제가 되지 않던 문제 수정 (#852, #607)
	    - [Entity Editor] 플레이어 캐릭터를 "ALT + R-Click"으로 삭제할 경우 마지막 카메라 위치 보존 처리 (#847)