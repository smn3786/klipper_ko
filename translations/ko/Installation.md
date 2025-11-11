# 설치

이 지침은 소프트웨어가 Klipper 호환 프론트엔드를 실행하는
Linux 기반 호스트에서 실행될 것으로 가정합니다. Raspberry Pi 또는
Debian 기반 Linux 장치와 같은 SBC(Small Board Computer)를 호스트 머신으로
사용하는 것이 권장됩니다(기타 옵션은
[FAQ](FAQ.md#can-i-run-klipper-on-something-other-than-a-raspberry-pi-3)
참조).

이 지침에서 host는 Linux 장치를 의미하고
mcu는 프린터 보드를 의미합니다. SBC는 Raspberry Pi와 같은
Small Board Computer를 의미합니다.

## Klipper 설정 파일 얻기

대부분의 Klipper 설정은 호스트에 저장될 "프린터 설정 파일"
printer.cfg에 의해 결정됩니다. 적절한 설정 파일은
종종 대상 프린터에 해당하는 "printer-" 접두사로 시작하는
파일을 Klipper [config 디렉토리](../config/)에서 찾아볼 수 있습니다.
Klipper 설정 파일에는 설치 중에 필요한
프린터에 대한 기술 정보가 포함되어 있습니다.

Klipper config 디렉토리에 적절한 프린터 설정 파일이 없는 경우
프린터 제조업체의 웹사이트를 검색하여 적절한 Klipper 설정 파일이
있는지 확인해 보세요.

프린터용 설정 파일을 찾을 수 없지만 프린터
제어 보드 유형을 알고 있는 경우, "generic-" 접두사로 시작하는
적절한 [설정 파일](../config/)을 찾아보세요. 이러한
예제 프린터 보드 파일은 초기 설치를 성공적으로 완료할 수 있도록
하지만, 전체 프린터 기능을 얻으려면 일부
사용자 정의가 필요합니다.

처음부터 새 프린터 설정을 정의하는 것도 가능합니다.
그러나 이를 위해서는 프린터와 그 전자 장치에 대한
상당한 기술 지식이 필요합니다. 대부분의 사용자는
적절한 설정 파일로 시작하는 것이 권장됩니다. 새로운 맞춤형
프린터 설정 파일을 생성하는 경우, 가장 가까운 예제
[설정 파일](../config/)로 시작하고 추가 정보는 Klipper
[설정 참조](Config_Reference.md)를 사용하세요.

## Klipper와 상호작용하기

Klipper는 3D 프린터 펌웨어이므로 사용자가
상호작용할 수 있는 방법이 필요합니다.

현재 가장 좋은 선택은 [Moonraker web API](https://moonraker.readthedocs.io/)를
통해 정보를 검색하는 프론트엔드이며, Klipper를 제어하기 위해
[Octoprint](https://octoprint.org/)를 사용하는 옵션도 있습니다.

사용자가 무엇을 사용할지는 선택의 문제이지만, 모든 경우에
기본 Klipper는 동일합니다. 사용 가능한 옵션을 연구하고
정보에 입각한 결정을 내리시기 바랍니다.

## SBC용 OS 이미지 얻기

SBC 사용을 위한 Klipper OS 이미지를 얻는 방법은 여러 가지가 있으며,
대부분 사용하려는 프론트엔드에 따라 다릅니다. 일부 SBC 보드 제조업체는
자체적으로 Klipper 중심 이미지도 제공합니다.

두 가지 주요 Moonraker 기반 프론트엔드는 [Fluidd](https://docs.fluidd.xyz/)
및 [Mainsail](https://docs.mainsail.xyz/)이며, 후자는 미리 만들어진 설치
이미지 ["MainsailOS"](https://docs-os.mainsail.xyz/)를 제공하며, Raspberry Pi
및 일부 OrangePi 변형을 위한 옵션이 있습니다.

Fluidd는 KIAUH(Klipper Install And Update Helper)를 통해 설치할 수 있으며,
이는 아래에서 설명하고 모든 Klipper 관련 항목을 위한 타사 설치 프로그램입니다.

OctoPrint는 인기 있는 OctoPi 이미지 또는 KIAUH를 통해 설치할 수 있으며,
이 프로세스는 [OctoPrint.md](OctoPrint.md)에서 설명합니다.

## KIAUH를 통한 설치

일반적으로 SBC용 기본 이미지(예: RPiOS Lite)로 시작하거나
x86 Linux 장치의 경우 Ubuntu Server로 시작합니다. Desktop
변형은 일부 Klipper 기능의 작동을 중지하고 심지어 일부
프린터 보드에 대한 액세스를 마스킹할 수 있는 특정 헬퍼 프로그램으로 인해
권장되지 않습니다.

KIAUH는 Debian 형식을 실행하는 다양한
Linux 기반 시스템에 Klipper와 관련 프로그램을 설치하는 데 사용할 수 있습니다.
자세한 정보는 https://github.com/dw-0/kiauh에서 확인할 수 있습니다.

## 마이크로컨트롤러 빌드 및 플래싱

마이크로컨트롤러 코드를 컴파일하려면 호스트 장치에서 다음
명령을 실행하여 시작하세요:

```
cd ~/klipper/
make menuconfig
```

[프린터 설정 파일](#obtain-a-klipper-configuration-file) 상단의
주석은 "make menuconfig" 중에 설정해야 하는
설정을 설명해야 합니다. 웹 브라우저 또는 텍스트 편집기에서
파일을 열고 파일 상단 근처에서 이러한 지침을 찾으세요.
적절한 "menuconfig" 설정이 구성되면 "Q"를 눌러 종료한 다음
"Y"를 눌러 저장합니다. 그런 다음 실행:

```
make
```

[프린터 설정 파일](#obtain-a-klipper-configuration-file) 상단의
주석이 최종 이미지를 프린터
제어 보드에 "플래싱"하기 위한 사용자 정의 단계를 설명하는 경우,
해당 단계를 따른 다음
[OctoPrint 구성](#configuring-octoprint-to-use-klipper)으로 진행하세요.

그렇지 않으면 다음 단계가 프린터 제어 보드를 "플래시"하는 데
자주 사용됩니다. 먼저 마이크로컨트롤러에 연결된 시리얼 포트를
결정해야 합니다. 다음을 실행:

```
ls /dev/serial/by-id/*
```

다음과 유사한 내용이 보고되어야 합니다:

```
/dev/serial/by-id/usb-1a86_USB2.0-Serial-if00-port0
```

각 프린터는 고유한 시리얼 포트 이름을 갖는 것이 일반적입니다.
이 고유한 이름은 마이크로컨트롤러를 플래싱할 때 사용됩니다.
위의 출력에 여러 줄이 있을 수 있습니다 - 그렇다면
마이크로컨트롤러에 해당하는 줄을 선택하세요. 많은
항목이 나열되고 선택이 모호한 경우, 보드의 플러그를 뽑고
명령을 다시 실행하면 누락된 항목이 프린트 보드입니다(자세한 내용은
[FAQ](FAQ.md#wheres-my-serial-port) 참조).

STM32 또는 클론 칩, LPC 칩 및
기타를 사용하는 일반적인 마이크로컨트롤러의 경우, SD 카드를 통한
초기 Klipper 플래시가 필요한 것이 일반적입니다.

이 방법으로 플래싱할 때, 일부 보드가
보드에 전원을 다시 공급하여 플래시가
발생하지 않도록 할 수 있으므로, 프린트 보드가 호스트에
USB로 연결되어 있지 않은지 확인하는 것이 중요합니다.

SD 카드를 사용하여 플래시하는 대부분의 프린트 보드는
SD 카드가 제자리에 남아 있을 때를 위한 일종의 플래시 루프 보호를
구현한다는 점에 유의하세요. 두 가지 일반적인 방법이 있습니다:

파일 이름 변경 필요(일반적으로 "순정" 프린트 보드):

이러한 보드는 플래시할 때마다 펌웨어 파일이 다른 이름을 가져야 합니다
(예: firmware1.bin, firmware2.bin 등).
동일한 파일 이름을 재사용하면 보드가 무시하고 업데이트하지 않을 수 있습니다.

자동 파일 이름 변경(일반적으로 애프터마켓 프린트 보드):

다른 보드는 일반적으로 firmware.bin이라는 동일한 파일 이름을 사용할 수 있지만,
플래싱 후 보드가 파일 이름을 firmware.cur로 변경합니다.
이는 펌웨어가 성공적으로 플래시되었음을 나타내고 다음 시작 시
다시 플래시되는 것을 방지하는 데 도움이 됩니다.

플래싱하기 전에 보드가 어떤 동작을 따르는지 확인하세요.

예를 들어 2560과 같은 Atmega 칩을 사용하는 일반적인 마이크로컨트롤러의 경우,
다음과 유사한 명령으로 코드를 플래시할 수 있습니다:

```
sudo service klipper stop
make flash FLASH_DEVICE=/dev/serial/by-id/usb-1a86_USB2.0-Serial-if00-port0
sudo service klipper start
```

프린터의 고유한 시리얼
포트 이름으로 FLASH_DEVICE를 업데이트해야 합니다.

RP2040 칩을 사용하는 일반적인 마이크로컨트롤러의 경우, 다음과
유사한 명령으로 코드를 플래시할 수 있습니다:

```
sudo service klipper stop
make flash FLASH_DEVICE=first
sudo service klipper start
```

이 작업 전에 RP2040 칩을 부팅 모드로
전환해야 할 수 있다는 점에 유의해야 합니다.


## Klipper 구성

다음 단계는 [프린터 설정 파일](#obtain-a-klipper-configuration-file)을
호스트에 복사하는 것입니다.

Klipper 설정 파일을 설정하는 가장 쉬운 방법은 Mainsail 또는
Fluidd의 내장 편집기를 사용하는 것입니다. 이를 통해 사용자는
설정 예제를 열고 printer.cfg로 저장할 수 있습니다.

또 다른 옵션은 "scp" 및/또는 "sftp" 프로토콜을 통해 파일 편집을
지원하는 데스크톱 편집기를 사용하는 것입니다. 이를 지원하는 무료
도구가 있습니다(예: Notepad++, WinSCP 및 Cyberduck).
편집기에서 프린터 설정 파일을 로드한 다음 pi 사용자의
홈 디렉토리에 "printer.cfg"라는 이름으로 파일을 저장합니다
(즉, /home/pi/printer.cfg).

또는 SSH를 통해 호스트에서 파일을 직접 복사하고 편집할 수도
있습니다. 다음과 유사하게 보일 수 있습니다(적절한 프린터
설정 파일 이름을 사용하도록 명령을 업데이트해야 합니다):

```
cp ~/klipper/config/example-cartesian.cfg ~/printer.cfg
nano ~/printer.cfg
```

각 프린터는 마이크로컨트롤러의 고유한 이름을 갖는 것이 일반적입니다.
이름은 Klipper를 플래싱한 후 변경될 수 있으므로, 플래싱할 때
이미 수행한 경우에도 이러한 단계를 다시 실행하세요. 실행:

```
ls /dev/serial/by-id/*
```

다음과 유사한 내용이 보고되어야 합니다:

```
/dev/serial/by-id/usb-1a86_USB2.0-Serial-if00-port0
```

그런 다음 고유한 이름으로 설정 파일을 업데이트합니다. 예를 들어,
`[mcu]` 섹션을 다음과 유사하게 업데이트합니다:

```
[mcu]
serial: /dev/serial/by-id/usb-1a86_USB2.0-Serial-if00-port0
```

파일을 생성하고 편집한 후, 설정을 로드하기 위해 명령 콘솔에서
"restart" 명령을 실행해야 합니다.
Klipper 설정 파일이 성공적으로 읽히고 마이크로컨트롤러가
성공적으로 발견되어 구성된 경우 "status" 명령은 프린터가 준비되었음을
보고합니다.

프린터 설정 파일을 사용자 정의할 때 Klipper가
설정 오류를 보고하는 것은 드문 일이 아닙니다. 오류가 발생하면
프린터 설정 파일에 필요한 수정을 하고 "status"가 프린터가
준비되었다고 보고할 때까지 "restart"를 실행합니다.

Klipper는 명령 콘솔 및 Fluidd 및 Mainsail의 팝업을 통해
오류 메시지를 보고합니다. "status" 명령을 사용하여 오류
메시지를 다시 보고할 수 있습니다. 로그는 사용 가능하며 일반적으로
`~/printer_data/logs/klippy.log`에 있습니다.

Klipper가 프린터가 준비되었다고 보고한 후,
설정 파일의 정의에 대한 기본 검사를 수행하려면
[설정 검사 문서](Config_checks.md)로 진행하세요. 기타 정보는
주요 [문서 참조](Overview.md)를 참조하세요.
