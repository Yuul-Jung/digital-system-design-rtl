# Digital System Design · RTL · Verilog

Verilog HDL 문법에서 조합·순차회로 모델링, FPGA 구현 실습까지 12개 장으로 구성한 GitHub Pages 교재입니다.

## 파일 구성

| 파일 | 내용 |
|---|---|
| `index.html` | 과정 개요 · 전체 학습 테크트리 · 장별 목차 · 학습·검증 원칙 |
| `ch01_verilog_basics_v01.html` | 제01장 Verilog HDL 기초 |
| `ch02_datatypes_operators_v01.html` | 제02장 자료형과 연산자 |
| `ch03_gate_level_modeling_v01.html` | 제03장 게이트 수준 모델링 |
| `ch04_assignments_v01.html` | 제04장 할당문 |
| `ch05_behavioral_modeling_v01.html` | 제05장 행위수준 모델링 |
| `ch06_structural_modeling_v01.html` | 제06장 구조적 모델링 |
| `ch07_functions_tasks_v01.html` | 제07장 함수와 태스크 |
| `ch08_compiler_directives_v01.html` | 제08장 컴파일러 지시어 |
| `ch09_system_tasks_functions_v01.html` | 제09장 시스템 태스크와 시스템 함수 |
| `ch10_combinational_modeling_v01.html` | 제10장 조합회로 모델링 |
| `ch11_sequential_modeling_v01.html` | 제11장 순차회로 모델링 |
| `ch12_sequential_fpga_lab_v01.html` | 제12장 순차회로의 FPGA 구현 실습 |
| `VERIFY.md` | 코드 컴파일 검증 기록 |

## 📘 교육용 HTML 공통 제작 규칙

이 저장소의 교육자료(웹페이지·강의 HTML)는 [Yuul-Jung 교육용 HTML 공통 표준](https://github.com/Yuul-Jung/rule_md/tree/main/web/education-html)을 적용합니다.

- [제작 규칙](https://github.com/Yuul-Jung/rule_md/blob/main/web/education-html/STANDARD.md)
- [다른 저장소 적용 안내](https://github.com/Yuul-Jung/rule_md/blob/main/web/education-html/INTEGRATION.md)
- [공통 코드 규칙](https://github.com/Yuul-Jung/rule_md/blob/main/common/code-style-rules.md) · [FPGA/SoC RTL 규칙](https://github.com/Yuul-Jung/rule_md/blob/main/fpga-soc/MBV_SOC_rules.md)
- [기준 디자인 사례](https://github.com/Yuul-Jung/ai-agent-engineering)

공통 책장 이미지, 컴팩트한 상단 배너, 좌측 전체 장/절 탐색, 모바일 메뉴, 파일 버전 및 검증 기준을 따릅니다.
**색상만 예외**로 표준 기본색(보라·회색) 대신 따뜻한 팔레트(테라코타 강조 `#B4532A`, 바탕 `#F6F1E8`)를 사용합니다.

적용 기준: rule_md 커밋 `d1b8278`

## 검증 상태

코드 박스 상단에 상태를 표시합니다. **iverilog 컴파일 통과**는 컴파일·정교화만 확인한 것이며, 시뮬레이션 파형·합성·보드 동작은 **미검증**입니다. 세부 결과는 [`VERIFY.md`](VERIFY.md)를 참고합니다.
