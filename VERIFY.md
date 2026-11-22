# 코드 검증 기록

rule_md `common/code-style-rules.md` 13절 판정 기준(통과·실패·미검증·해당 없음)에 따른 기록입니다.

- 도구: Icarus Verilog 12.0 (`iverilog -g2005`), 컴파일·정교화(elaboration)만 수행
- 대상: `module … endmodule`을 모두 갖춘 코드. 하위 모듈은 같은 장의 코드에서 찾아 함께 컴파일
- 시뮬레이션 파형 비교, Vivado 합성, 보드 동작은 수행하지 않았습니다 → **미검증**
- 문법 형식·부분 코드·시뮬레이션 출력은 컴파일 대상이 아닙니다
- 검증 상태는 페이지(코드 박스)에 표시하지 않고 이 문서에만 기록합니다

## 장별 결과

| 장 | 코드 박스 | 컴파일 대상 | 통과 | 미통과 | 포트 선언 수정 |
|---|---:|---:|---:|---:|---:|
| 01 Verilog HDL 기초 | 27 | 10 | 8 | 2 | 2 |
| 02 자료형과 연산자 | 33 | 7 | 7 | 0 | 2 |
| 03 게이트 수준 모델링 | 11 | 7 | 5 | 2 | 0 |
| 04 할당문 | 16 | 7 | 6 | 1 | 2 |
| 05 행위수준 모델링 | 53 | 24 | 24 | 0 | 16 |
| 06 구조적 모델링 | 42 | 33 | 20 | 13 | 2 |
| 07 함수와 태스크 | 10 | 4 | 4 | 0 | 1 |
| 08 컴파일러 지시어 | 13 | 5 | 4 | 1 | 0 |
| 09 시스템 태스크와 시스템 함수 | 8 | 6 | 4 | 2 | 0 |
| 10 조합회로 모델링 | 49 | 48 | 48 | 0 | 26 |
| 11 순차회로 모델링 | 39 | 29 | 29 | 0 | 15 |
| 12 순차회로의 FPGA 구현 실습 | 44 | 39 | 38 | 1 | 0 |
| **합계** | 345 | 219 | 197 | 22 | 66 |

## 포트 선언 수정 (필수 수정)

ANSI 포트 목록에서 `output`으로 선언한 신호를 본문에서 `reg`로 다시 선언하면 Verilog-2001 규칙상 컴파일 오류입니다.
동작은 바꾸지 않고 `output reg`로 합쳤습니다.

수정 모듈: 01장 `mux2b_if`, 01장 `D_ff`, 02장 `dff`, 02장 `mux21_if`, 04장 `proc_assignment`, 04장 `dff_pca`, 05장 `or2`, 05장 `dff`, 05장 `mux21_omit_sel`, 05장 `mux21_if`, 05장 `dff_async_sr`, 05장 `mux21_case`, 05장 `pri_enc_casex`, 05장 `pri_enc_case`, 05장 `multiplier_8b`, 05장 `count_ones`, 05장 `count_ones_syn`, 05장 `pri_enc_for`, 05장 `dff`, 05장 `dff_event`, 05장 `intra_assign_delay`, 05장 `intra_assign_delay_eq`, 06장 `dff`, 06장 `gray2bin2`, 07장 `bit_counter`, 10장 `nor3_if`, 10장 `xor4b_for`, 10장 `bin2gray`, 10장 `mux4to1_if`, 10장 `mux4to1_case`, 10장 `enc_4to2_case`, 10장 `enc_4to2_if`, 10장 `enc_4to2_for`, 10장 `pri_enc_4to2_if`, 10장 `pri_enc_4to2_case`, 10장 `pri_enc_4to2_for`, 10장 `dec_2to4_case`, 10장 `dec_2to4_if`, 10장 `dec_2to4_for`, 10장 `dec_param`, 10장 `comp_if`, 10장 `comp_for`, 10장 `case_latch`, 10장 `if_latch`, 10장 `case_no_latch`, 10장 `case_latch_attr`, 10장 `case_init`, 10장 `if_init`, 10장 `if_latch2`, 10장 `if_if`, 10장 `if_else_if`, 11장 `dlatch_pos`, 11장 `dlatch_pos_AHrst`, 11장 `dff_pos`, 11장 `dff_Bad1`, 11장 `dff_Bad2`, 11장 `dff_Good`, 11장 `dff_sync_ALrst`, 11장 `dff_async_ALrst`, 11장 `dlatch_blocking`, 11장 `dlatch_Nonblocking`, 11장 `seq_blocking`, 11장 `seq_Nonblocking`, 11장 `Not_recommend_3`, 11장 `counter_up`, 11장 `freq_div10`

## 컴파일 미통과 코드 (원본 유지)

| 장 | 모듈 | 원인 |
|---|---|---|
| 01 | `test_fix` | error: Unknown module type: Mod_A |
| 01 | `tb_dff_sr` | error: Unknown module type: dff_sr |
| 03 | `invalid_array_example` | error: 'I_nand' has already been declared in this scope. |
| 03 | `tri_latch` | error: 'qout' has already been declared in this scope. |
| 04 | `select_bus` | error: 'bus_out' has already been declared in this scope. |
| 06 | `module_name` | error: Port port_list (1) of module module_name is not declared within module. |
| 06 | `port_example` | syntax error |
| 06 | `port_example` | syntax error |
| 06 | `complex_ports` | error: Port c (1) of module complex_ports is not declared within module. |
| 06 | `tb_full_adder` | error: Unknown module type: half_adder |
| 06 | `bus_driver` | error: 'net_r' has already been declared in this scope. |
| 06 | `bus_driver` | error: 'net_r' has already been declared in this scope. |
| 06 | `driver` | error: 'net_r' has already been declared in this scope. |
| 06 | `receiver` | error: 'net_r' has already been declared in this scope. |
| 06 | `mod_param` | error: Port a (1) of module mod_param is not declared within module. |
| 06 | `mod_defparam` | error: Port a (1) of module mod_param is not declared within module. |
| 06 | `MxN_register` | error: Unknown module type: DFF |
| 06 | `multiplier` | error: Unknown module type: WALLACE_mul |
| 08 | `bcd_cnt_fnd` | Include file bcd_to_fnd.v not found |
| 09 | `tb_ring_counter` | error: Unknown module type: ring_counter |
| 09 | `driver` | error: 'net_r' has already been declared in this scope. |
| 12 | `motor_turn_fnd_beep` | error: Unknown module type: motor_drive_core |

원인 유형: 다른 장·외부 파일에 정의된 하위 모듈 참조, 의도적인 오류 예제, 비ANSI 문법 형식 예시, net(`wire`/`tri`) 재선언.
이들 코드는 설명 목적상 원본을 유지합니다.
