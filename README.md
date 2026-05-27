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
### STM32F4를 사용하는 이유.
### 대칭키(AES-128)를 사용하는 이유.
### 인터럽트 우선순위 설계
구현 중 실제 동작 기반으로 작성 예정 — 이론과 실제가 다를 수 있음

## Threat Model
구현하면서 취약 지점을 발견하는 순서대로 추가

## Troubleshooting & Learned
