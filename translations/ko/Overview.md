# 개요

Klipper 문서에 오신 것을 환영합니다. Klipper를 처음 사용하시는 경우,
[기능](Features.md) 및 [설치](Installation.md) 문서부터 시작하세요.

## 개요 정보

- [기능](Features.md): Klipper의 주요 기능 목록입니다.
- [FAQ](FAQ.md): 자주 묻는 질문입니다.
- [릴리스](Releases.md): Klipper 릴리스 이력입니다.
- [설정 변경사항](Config_Changes.md): 사용자가 프린터 설정 파일을
업데이트해야 할 수 있는 최근 소프트웨어 변경사항입니다.
- [연락처](Contact.md): 버그 보고 및 Klipper 개발자와의 일반적인
소통에 대한 정보입니다.

## 설치 및 구성

- [설치](Installation.md): Klipper 설치 가이드입니다.
  - [Octoprint](OctoPrint.md): Klipper와 함께 Octoprint를 설치하는 가이드입니다.
- [설정 참조](Config_Reference.md): 설정 매개변수에 대한 설명입니다.
  - [회전 거리](Rotation_Distance.md): rotation_distance 스테퍼 매개변수
    계산하기.
- [설정 확인](Config_checks.md): 설정 파일의 기본 핀 설정을 확인합니다.
- [베드 레벨링](Bed_Level.md): Klipper의 "베드 레벨링"에 대한 정보입니다.
  - [델타 캘리브레이션](Delta_Calibrate.md): 델타
    키네마틱스 캘리브레이션.
  - [프로브 캘리브레이션](Probe_Calibrate.md): 자동 Z
    프로브 캘리브레이션.
  - [BL-Touch](BLTouch.md): "BL-Touch" Z 프로브 구성하기.
  - [수동 레벨링](Manual_Level.md): Z 엔드스톱 캘리브레이션 (및
    유사 항목).
  - [베드 메쉬](Bed_Mesh.md): XY
    위치에 따른 베드 높이 보정.
  - [엔드스톱 위상](Endstop_Phase.md): 스테퍼 보조 Z 엔드스톱
    위치 조정.
  - [축 비틀림 보상](Axis_Twist_Compensation.md): X 갠트리의 비틀림으로 인한
    부정확한 프로브 측정값을 보정하는 도구입니다.
- [공진 보상](Resonance_Compensation.md): 프린트에서
  링잉을 줄이는 도구입니다.
  - [공진 측정](Measuring_Resonances.md): 공진을 측정하기 위해
    adxl345 가속도계 하드웨어를 사용하는 정보입니다.
- [압력 전진](Pressure_Advance.md): 익스트루더
  압력을 캘리브레이션합니다.
- [G-Code](G-Codes.md): Klipper가 지원하는 명령에 대한 정보입니다.
- [명령 템플릿](Command_Templates.md): G-Code 매크로 및
  조건부 평가.
  - [상태 참조](Status_Reference.md):
    매크로 (및 유사 항목)에서 사용 가능한 정보입니다.
- [TMC 드라이버](TMC_Drivers.md): Klipper와 함께 Trinamic 스테퍼 모터 드라이버
  사용하기.
- [다중 MCU 호밍](Multi_MCU_Homing.md): 여러 마이크로컨트롤러를 사용한 호밍 및 프로빙.
- [슬라이서](Slicers.md): Klipper용 "슬라이서" 소프트웨어 구성하기.
- [스큐 보정](Skew_Correction.md): 완벽하게 직각이 아닌
  축에 대한 조정.
- [PWM 도구](Using_PWM_Tools.md): 레이저 또는 스핀들과 같은 PWM 제어
  도구 사용 방법 가이드.
- [객체 제외](Exclude_Object.md): 객체 제외
  구현 가이드.

## 개발자 문서

- [코드 개요](Code_Overview.md): 개발자는 이것을
  먼저 읽어야 합니다.
- [키네마틱스](Kinematics.md): Klipper가
  모션을 구현하는 방법에 대한 기술적 세부사항.
- [프로토콜](Protocol.md): 호스트와 마이크로컨트롤러 간
  저수준 메시징 프로토콜에 대한 정보.
- [API 서버](API_Server.md): Klipper의 명령 및
  제어 API에 대한 정보.
- [MCU 명령](MCU_Commands.md): 마이크로컨트롤러 소프트웨어에
  구현된 저수준 명령에 대한 설명.
- [CAN 버스 프로토콜](CANBUS_protocol.md): Klipper CAN 버스 메시지
  형식.
- [디버깅](Debugging.md): Klipper를 테스트하고 디버그하는
  방법에 대한 정보.
- [벤치마크](Benchmarks.md): Klipper 벤치마크
  방법에 대한 정보.
- [기여하기](CONTRIBUTING.md): Klipper에
  개선사항을 제출하는 방법에 대한 정보.
- [패키징](Packaging.md): OS 패키지 빌드에 대한 정보.

## 장치별 문서

- [예제 설정](Example_Configs.md): Klipper에
  예제 설정 파일을 추가하는 정보.
- [SD카드 업데이트](SDCard_Updates.md): 마이크로컨트롤러의 SD카드에
  바이너리를 복사하여 마이크로컨트롤러를 플래시합니다.
- [마이크로컨트롤러로서의 Raspberry Pi](RPi_microcontroller.md): Raspberry Pi의
  GPIO 핀에 연결된 장치를 제어하는 세부사항.
- [Beaglebone](Beaglebone.md): Beaglebone PRU에서
  Klipper를 실행하는 세부사항.
- [부트로더](Bootloaders.md):
  마이크로컨트롤러 플래싱에 대한 개발자 정보.
- [부트로더 진입](Bootloader_Entry.md): 부트로더 요청하기.
- [CAN 버스](CANBUS.md): Klipper와 함께 CAN 버스 사용에 대한 정보.
  - [CAN 버스 문제 해결](CANBUS_Troubleshooting.md): CAN 버스
    문제 해결 팁.
- [TSL1401CL 필라멘트 폭 센서](TSL1401CL_Filament_Width_Sensor.md)
- [홀 필라멘트 폭 센서](Hall_Filament_Width_Sensor.md)
- [와전류 유도 프로브](Eddy_Probe.md)
- [로드셀](Load_Cell.md)
