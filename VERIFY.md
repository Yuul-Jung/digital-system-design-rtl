# 코드 검증 기록

rule_md `common/code-style-rules.md` 13절 판정 기준(통과·실패·미검증·해당 없음)에 따른 기록입니다.

- 도구: Icarus Verilog 12.0 (`iverilog -g2005`), 컴파일·정교화(elaboration)만 수행
- 대상: `module … endmodule`을 모두 갖춘 코드. 하위 모듈은 같은 장의 코드에서 찾아 함께 컴파일
- 시뮬레이션 파형 비교, Vivado 합성, 보드 동작은 수행하지 않았습니다 → **미검증**
- 문법 형식·부분 코드·시뮬레이션 출력은 컴파일 대상이 아니므로 **미검증**으로 표시합니다

## 장별 결과

| 장 | 코드 박스 | 컴파일 대상 | 통과 | 미통과 | 포트 선언 수정 |
|---|---:|---:|---:|---:|---:|
| 01 Verilog HDL 기초 | 27 | 10 | 6 | 4 | 0 |
| 02 자료형과 연산자 | 33 | 7 | 5 | 2 | 0 |
| 03 게이트 수준 모델링 | 11 | 7 | 5 | 2 | 0 |
| 04 할당문 | 16 | 7 | 4 | 3 | 0 |
| 05 행위수준 모델링 | 53 | 24 | 7 | 17 | 0 |
| 06 구조적 모델링 | 42 | 33 | 17 | 16 | 0 |
| 07 함수와 태스크 | 10 | 4 | 3 | 1 | 0 |
| 08 컴파일러 지시어 | 13 | 5 | 4 | 1 | 0 |
| 09 시스템 태스크와 시스템 함수 | 8 | 6 | 4 | 2 | 0 |
| 10 조합회로 모델링 | 49 | 48 | 16 | 32 | 0 |
| 11 순차회로 모델링 | 39 | 29 | 10 | 19 | 0 |
| 12 순차회로의 FPGA 구현 실습 | 44 | 39 | 38 | 1 | 0 |
| **합계** | 345 | 219 | 119 | 100 | 0 |

## 컴파일 미통과 코드 (원본 유지)

| 장 | 모듈 | 원인 |
|---|---|---|
| 01 | `mux2b_if` | error: 'out' has already been declared in this scope. |
| 01 | `D_ff` | error: 'q' has already been declared in this scope. |
| 01 | `test_fix` | error: Unknown module type: Mod_A |
| 01 | `tb_dff_sr` | error: Unknown module type: dff_sr |
| 02 | `dff` | error: 'qout' has already been declared in this scope. |
| 02 | `mux21_if` | error: 'out' has already been declared in this scope. |
| 03 | `invalid_array_example` | error: 'I_nand' has already been declared in this scope. |
| 03 | `tri_latch` | error: 'qout' has already been declared in this scope. |
| 04 | `select_bus` | error: 'bus_out' has already been declared in this scope. |
| 04 | `proc_assignment` | error: 'out' has already been declared in this scope. |
| 04 | `dff_pca` | error: 'q' has already been declared in this scope. |
| 05 | `or2` | error: 'out' has already been declared in this scope. |
| 05 | `dff` | error: 'qout' has already been declared in this scope. |
| 05 | `mux21_omit_sel` | error: 'out' has already been declared in this scope. |
| 05 | `mux21_if` | error: 'out' has already been declared in this scope. |
| 05 | `dff_async_sr` | error: 'q' has already been declared in this scope. |
| 05 | `mux21_case` | error: 'out' has already been declared in this scope. |
| 05 | `pri_enc_casex` | error: 'enc' has already been declared in this scope. |
| 05 | `pri_enc_case` | error: 'enc' has already been declared in this scope. |
| 05 | `multiplier_8b` | error: 'result' has already been declared in this scope. |
| 05 | `count_ones` | error: 'count' has already been declared in this scope. |
| 05 | `count_ones_syn` | error: 'count' has already been declared in this scope. |
| 05 | `pri_enc_for` | error: 'enc_out' has already been declared in this scope. |
| 05 | `tb_dff` | error: 'qout' has already been declared in this scope. |
| 05 | `dff` | error: 'qout' has already been declared in this scope. |
| 05 | `dff_event` | error: 'qout' has already been declared in this scope. |
| 05 | `intra_assign_delay` | error: 'out' has already been declared in this scope. |
| 05 | `intra_assign_delay_eq` | error: 'out' has already been declared in this scope. |
| 06 | `module_name` | error: Port port_list (1) of module module_name is not declared within module. |
| 06 | `port_example` | syntax error |
| 06 | `port_example` | syntax error |
| 06 | `complex_ports` | error: Port c (1) of module complex_ports is not declared within module. |
| 06 | `dff` | error: 'q' has already been declared in this scope. |
| 06 | `reg_5b` | error: 'q' has already been declared in this scope. |
| 06 | `tb_full_adder` | error: Unknown module type: half_adder |
| 06 | `bus_driver` | error: 'net_r' has already been declared in this scope. |
| 06 | `bus_driver` | error: 'net_r' has already been declared in this scope. |
| 06 | `driver` | error: 'net_r' has already been declared in this scope. |
| 06 | `receiver` | error: 'net_r' has already been declared in this scope. |
| 06 | `mod_param` | error: Port a (1) of module mod_param is not declared within module. |
| 06 | `mod_defparam` | error: Port a (1) of module mod_param is not declared within module. |
| 06 | `MxN_register` | error: Unknown module type: DFF |
| 06 | `gray2bin2` | error: 'bin' has already been declared in this scope. |
| 06 | `multiplier` | error: Unknown module type: WALLACE_mul |
| 07 | `bit_counter` | error: 'bit_count' has already been declared in this scope. |
| 08 | `bcd_cnt_fnd` | Include file bcd_to_fnd.v not found |
| 09 | `tb_ring_counter` | error: Unknown module type: ring_counter |
| 09 | `driver` | error: 'net_r' has already been declared in this scope. |
| 10 | `nor3_if` | error: 'out_nor3' has already been declared in this scope. |
| 10 | `xor4b_for` | error: 'xor4b' has already been declared in this scope. |
| 10 | `bin2gray` | error: 'gray' has already been declared in this scope. |
| 10 | `tb_bin2gray` | error: 'gray' has already been declared in this scope. |
| 10 | `mux4to1_if` | error: 'mux_out' has already been declared in this scope. |
| 10 | `mux4to1_case` | error: 'mux_out' has already been declared in this scope. |
| 10 | `tb_mux41` | error: 'mux_out' has already been declared in this scope. |
| 10 | `enc_4to2_case` | error: 'enc_out' has already been declared in this scope. |
| 10 | `enc_4to2_if` | error: 'enc_out' has already been declared in this scope. |
| 10 | `enc_4to2_for` | error: 'enc_out' has already been declared in this scope. |
| 10 | `tb_enc_4to2` | error: 'enc_out' has already been declared in this scope. |
| 10 | `pri_enc_4to2_if` | error: 'valid' has already been declared in this scope. |
| 10 | `pri_enc_4to2_case` | error: 'valid' has already been declared in this scope. |
| 10 | `pri_enc_4to2_for` | error: 'valid' has already been declared in this scope. |
| 10 | `tb_pri_enc_4to2` | error: 'valid' has already been declared in this scope. |
| 10 | `dec_2to4_case` | error: 'dec_out' has already been declared in this scope. |
| 10 | `dec_2to4_if` | error: 'dec_out' has already been declared in this scope. |
| 10 | `dec_2to4_for` | error: 'dec_out' has already been declared in this scope. |
| 10 | `tb_dec_2to4` | error: 'dec_out' has already been declared in this scope. |
| 10 | `dec_param` | error: 'dec_out' has already been declared in this scope. |
| 10 | `dec_3to6_param` | error: 'dec_out' has already been declared in this scope. |
| 10 | `comp_if` | error: 'aeqb' has already been declared in this scope. |
| 10 | `comp_for` | error: 'aeqb' has already been declared in this scope. |
| 10 | `case_latch` | error: 'out' has already been declared in this scope. |
| 10 | `if_latch` | error: 'out' has already been declared in this scope. |
| 10 | `case_no_latch` | error: 'out' has already been declared in this scope. |
| 10 | `case_latch_attr` | error: 'out' has already been declared in this scope. |
| 10 | `case_init` | error: 'out' has already been declared in this scope. |
| 10 | `if_init` | error: 'out' has already been declared in this scope. |
| 10 | `if_latch2` | error: 'out1' has already been declared in this scope. |
| 10 | `if_if` | error: 'dout' has already been declared in this scope. |
| 10 | `if_else_if` | error: 'dout' has already been declared in this scope. |
| 11 | `dlatch_pos` | error: 'qout' has already been declared in this scope. |
| 11 | `tb_dlatch` | error: 'qout' has already been declared in this scope. |
| 11 | `dlatch_pos_AHrst` | error: 'qout' has already been declared in this scope. |
| 11 | `tb_dlatch_rst` | error: 'qout' has already been declared in this scope. |
| 11 | `dff_pos` | error: 'qout' has already been declared in this scope. |
| 11 | `tb_dff` | error: 'qout' has already been declared in this scope. |
| 11 | `dff_Bad1` | error: 'qout' has already been declared in this scope. |
| 11 | `dff_Bad2` | error: 'qout' has already been declared in this scope. |
| 11 | `dff_Good` | error: 'qout' has already been declared in this scope. |
| 11 | `dff_sync_ALrst` | error: 'qout' has already been declared in this scope. |
| 11 | `dff_async_ALrst` | error: 'qout' has already been declared in this scope. |
| 11 | `dlatch_blocking` | error: 'y_out' has already been declared in this scope. |
| 11 | `dlatch_Nonblocking` | error: 'y_out' has already been declared in this scope. |
| 11 | `seq_blocking` | error: 'yout' has already been declared in this scope. |
| 11 | `seq_Nonblocking` | error: 'yout' has already been declared in this scope. |
| 11 | `Not_recommend_3` | error: 'qout' has already been declared in this scope. |
| 11 | `counter_up` | error: 'cnt_out' has already been declared in this scope. |
| 11 | `tb_counter` | error: 'cnt_out' has already been declared in this scope. |
| 11 | `freq_div10` | error: 'clk_div' has already been declared in this scope. |
| 12 | `motor_turn_fnd_beep` | error: Unknown module type: motor_drive_core |

원인 유형: 다른 장·외부 파일에 정의된 하위 모듈 참조, 의도적인 오류 예제, 비ANSI 문법 형식 예시, net(`wire`/`tri`) 재선언.
이들 코드는 교재 설명 목적상 원본을 유지하고 코드 박스에 **미검증**으로 표시했습니다.
