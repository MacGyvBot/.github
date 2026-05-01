# 🧰 MacGyvBot

MacGyvBot은 **음성 명령 기반 공구 서랍 관리 로봇팔 어시스턴트**를 개발하는 Organization입니다.

사용자가 음성으로 특정 공구를 요청하면, 시스템은 공구를 인식하고 위치를 추정한 뒤 로봇팔과 그리퍼로 공구를 집어 사용자 앞 전달 위치 또는 사용자 손 방향으로 안전하게 전달합니다. 이후 사용자가 반납한 공구를 다시 원래 위치로 정리하는 기능도 목표로 합니다.

## 🎯 목표

- 음성 명령으로 필요한 공구를 요청합니다.
- 카메라와 비전 모델로 공구 종류와 위치를 추정합니다.
- ROS 2 기반 로봇팔이 서랍 또는 보관 위치로 이동합니다.
- 그리퍼가 공구를 파지하고 사용자에게 안전하게 전달합니다.
- 반납된 공구를 원래 위치로 정리합니다.
- 실패 상황을 감지하고 안전하게 복구합니다.

## 📦 주요 레포지토리

| 레포지토리 | 역할 |
| --- | --- |
| [`macgyvbot-assistant`](https://github.com/MacGyvBot/macgyvbot-assistant) | ROS 2 메인 시스템, 작업 상태 관리, 로봇팔/그리퍼/서랍 제어 |
| [`macgyvbot-perception`](https://github.com/MacGyvBot/macgyvbot-perception) | 공구 인식, 위치 추정, 모델 학습/추론 |
| [`macgyvbot-datasets`](https://github.com/MacGyvBot/macgyvbot-datasets) | 데이터 수집, 라벨링, 메타데이터 관리 |
| [`macgyvbot-docs`](https://github.com/MacGyvBot/macgyvbot-docs) | 기획서, 요구사항 명세서, 발표자료, 다이어그램 |
| [`macgyvbot-vla`](https://github.com/MacGyvBot/macgyvbot-vla) | OpenVLA 기반 조작 skill 실험 및 파인튜닝 |
| [`macgyvbot-simulation`](https://github.com/MacGyvBot/macgyvbot-simulation) | Isaac Sim, Gazebo, RViz 기반 시뮬레이션 |

## 🧩 핵심 구성 요소

- 🤖 ROS 2 기반 로봇팔 제어
- 👁️ 공구 인식 및 위치 추정
- 🎙️ 음성 명령 처리
- 🗂️ 공구 선택 및 작업 상태 관리
- 🧰 서랍 개폐 제어
- ✋ 그리퍼 파지 제어
- 🚚 사용자 손 또는 전달 트레이 방향 안전 전달
- 🧪 데이터 수집, 라벨링, 모델 학습
- 🧠 YOLO, GroundingDINO, SAM, OpenVLA 실험
- 🕹️ 시뮬레이션 및 실제 로봇 테스트
- 🚨 안전 제어, 실패 복구, 로깅

## 🚨 안전 원칙

로봇팔과 사용자 손이 가까운 거리에서 상호작용하는 프로젝트이므로 안전을 최우선으로 다룹니다.

- 실제 로봇 실행 전 dry-run 또는 시뮬레이션을 권장합니다.
- 로봇 작업 공간과 속도 제한을 명확히 설정합니다.
- 비상정지 동작을 먼저 확인합니다.
- 사용자 손과 로봇팔/공구 사이의 최소 거리를 유지합니다.
- 안전 관련 변경은 `safety`, `urgent` 라벨로 우선 검토합니다.

## 🤝 기여

조직 프로필과 공통 기여 가이드는 이 `.github` 레포지토리에서 관리합니다.
새 레포지토리 생성용 이슈/PR 템플릿은 [`macgyvbot-template`](https://github.com/MacGyvBot/macgyvbot-template)에서 관리합니다.

- 이슈를 만들 때는 버그, 기능 제안, 일반 작업, 실험, 안전 이슈 중 알맞은 템플릿을 선택해주세요.
- PR은 가능한 한 하나의 목적만 포함하고, 테스트 결과와 리뷰 포인트를 명확히 작성해주세요.
- 자세한 규칙은 [`CONTRIBUTING.md`](https://github.com/MacGyvBot/.github/blob/main/CONTRIBUTING.md)를 참고해주세요.
