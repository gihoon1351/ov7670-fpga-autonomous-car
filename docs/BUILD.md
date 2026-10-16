# 빌드 및 검증 안내

## 영상처리 보드

Vivado 2020.2에서 Basys3용 프로젝트를 만들고 `fpga/` 소스와 XDC를 추가합니다. `fpga/intergration/top_isp.v`의 포트·인스턴스를 기준으로 카메라, 영상처리, UART 경로를 연결합니다. 같은 이름의 모듈을 중복 추가하지 않도록 파일별 용도를 확인합니다.

SCCB 초기화 메모리 `fpga/sccb/ov7670_setup.mem`을 프로젝트의 메모리 초기화 파일로 추가합니다. 카메라 배선과 보드 핀은 포함된 XDC와 실제 연결에 맞춰 확인합니다.

## 모터 제어 보드

`microblaze/`에는 커스텀 IP 패키지와 BD, `microblaze_cu_design_wrapper.xsa`가 있습니다. Vivado IP Repository에 커스텀 IP를 등록하고 BD의 의존 IP를 확인합니다. Vitis에서 XSA 기반 플랫폼과 standalone 앱을 만든 뒤 `firmware/vitis_code/`를 추가합니다. XSA는 제출 당시 자료이며 현재 툴의 재생성 결과로 대체하지 않았습니다.

## Sobel 단독 검증

`sobel_filter_uvm_verification/README.md`와 `sim/Makefile`의 지시를 따릅니다. 이 환경은 차량 전체가 아닌 Sobel 모듈의 블록 단위 비교입니다. 입력/기대값 파일을 같은 상대경로에 두어야 합니다.

## 확인 순서

카메라 입력 → 차선/적색 검출 → UART 좌표/정지 명령 → MicroBlaze 처리 → 모터 레지스터 순서로 확인합니다. 0xFF 정지 명령은 좌표 평균 계산에서 구분합니다. 보드 통합과 VCS 검증은 이번 정리에서 재실행하지 않았습니다.
