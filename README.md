# OV7670 카메라 기반 FPGA 자율주행 차량 시스템

영상처리 결과인 차선 좌표와 적색 정지 명령을 UART로 전달하고 MicroBlaze가 모터 구동으로 연결하는 프로젝트입니다.

| 항목 | 내용 |
|---|---|
| 작성자 | 최기훈 |
| 수행 기간 | 2026.08.31 ~ 2026.09.08 |
| 프로젝트 형태 | 팀 프로젝트 |
| 담당 범위 | AXI4-Lite 스텝모터 IP, Red Detection 1차 통합, 차선 기반 제어와 시스템 연동 |
| 주요 기술 | Verilog · C · AXI4-Lite · MicroBlaze · UART · OV7670 |

## 저장소 구성

| 경로 | 내용 |
|---|---|
| `fpga/` | 카메라·Sobel·적색 검출·UART 중재 |
| `firmware/` | MicroBlaze C 애플리케이션 및 드라이버 |
| `microblaze/` | 커스텀 IP, BD, XSA |
| `sobel_filter_uvm_verification/` | 제출본에 동봉된 Sobel 단독 검증 자료 |
| `docs/` | 구조·실행 안내와 원본 대응표 |

## 자료 범위와 확인 상태

이 저장소는 프로젝트 원본에서 RTL, 펌웨어, 테스트벤치와 필요한 설정 자료를 추려 정리한 소스 배포본입니다. 생성 캐시, 실행 바이너리, 과거 백업과 중복 BSP는 제외했습니다. 원본 소스의 로직은 변경하지 않았습니다.

정리 과정에서는 파일 구성과 참조 경로를 점검했습니다. 이번 정리에서 Vivado 합성·구현, VCS 시뮬레이션, 보드 동작을 새로 실행한 것은 아닙니다. 프로젝트 수행 당시 결과와 현재 소스의 재실행 결과는 구분합니다.

- [실행 및 검증 안내](docs/BUILD.md)
- [파일 구성과 원본 대응](docs/SOURCE_MAP.csv)
- [구조 및 주요 동작](docs/ARCHITECTURE.md)
- [포함된 제3자 코드 안내](THIRD_PARTY.md)

## 프로젝트 자료

- [제출 당시 완료보고서](docs/completion-report.docx)

- [프로젝트 발표자료 PPT](docs/presentation.pptx)
