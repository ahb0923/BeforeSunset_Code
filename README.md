## 📦 Project Overview
Firebase 기반의 게임 데이터 관리 및 유연한 타워 공격 로직 설계에 중점을 두고 개발하였습니다. 해당 리포지토리는 제가 직접 담당한 주요 코드들로 구성되어 있습니다.

## 🔧 Data System
✅ 데이터 흐름 구조
- Firebase Firestore에서 JSON 형태로 데이터를 받아옴

- 각 데이터는 대응하는 XXXDatabase.cs에 저장

- 공통 베이스 클래스인 BaseDataHandler를 상속받는 개별 데이터 핸들러를 제작

- 개발자는 이 핸들러를 통해 다양한 방식으로 데이터를 쉽게 조회 및 활용 가능

📁 예시
TowerDataHandler

- GetById(int id) : ID를 통해 특정 타워 데이터 조회

- GetPrefabByName(string name) : 이름을 통해 프리팹 조회

## 🏰 Tower System
✅ 구조 개요
- 모든 타워는 BaseTower를 상속

- 각 타워의 공격 방식은 전략 패턴(Strategy Pattern) 으로 분리하여 유연하게 확장 가능

⚔️ 공격 타입
1) 투사체 기반 타워 (Projectile Tower)

    - 타겟 선정 방식, 투사체 이동 방식 등을 전략 패턴으로 설계

    - 새로운 투사체 타입을 추가하거나 변경하기 쉬움

2) 범위 공격 타워 (AOE Tower)

    - 일정 반경 내 모든 적에게 피해

    - 범위 설정 및 이펙트 또한 전략적으로 분리 가능
 
## 🧠 설계 의도
1) 유지보수성 강화

    - 데이터 구조와 타워 시스템을 유연하게 구성하여 새로운 요구사항에도 빠르게 대응 가능

2) 확장성 보장

    - 새로운 타입의 데이터 또는 공격 로직 추가 시 최소한의 코드 수정으로 적용 가능

