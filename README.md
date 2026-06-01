# firmware-sec-p1-bare-metal-uart-aes
Bare-metal STM32F4 · AES-128 encrypted UART · no HAL · CVE analysis

## Overview
HAL 없이 레지스터를 직접 제어하는 Bare-metal 설계로 보안 통신을 구현한다.

## Dev Environment
MCU: STM32F4 Discovery
Language: C
IDE: STM32CubeIDE 2.1.1
Shell: PowerShell
Verification: Logic Analyzer, Serial Terminal

## Architecture

중간 산출물: 각 단계별 동작 확인 + 로직애널라이저 파형 캡처
최종 산출물: AES-128로 암호화된 UART 통신

## Key Engineering Decisions
### HAL은 사용하지 않음.
성능 및 보안 제어권 확보
### STM32F4를 사용하는 이유.
Cortex-M4 표준 아키텍처
ST-LINK 내장
### 대칭키(AES-128)를 사용하는 이유.
하드웨어 제약 내에서 표준적이고 검증된 대칭키 암호화
### 인터럽트 우선순위 설계
구현 중 실제 동작 기반으로 작성 예정

## Threat Model
예상 공격벡터 
UART 데이터 스니핑
키 관리 취약점
인터럽트 우선순위로 인한 DoS 가능성

## Troubleshooting & Learned
