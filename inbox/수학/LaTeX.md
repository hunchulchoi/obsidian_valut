---
created: 2025-01-27 17:01
last_modified: 2025-01-27 17:01
tags:
---
LaTeX 기본 문법은 다음과 같습니다.

1. **문서 구조**

   - `\documentclass{}` : 문서 클래스 선언
   - `\begin{document}` : 문서 시작
   - `\end{document}` : 문서 끝

2. **텍스트**

   - `\text{}` : 텍스트 입력
   - `\emph{}` : 강조
   - `\itshape` : 이탤릭체
   - `\bfseries` : 볼드체

3. **수식**

   - `$` : 수식 시작
   - `\$` : 수식 끝
   - `\frac{}{}` : 분수
   - `\sqrt{}` : 제곱근
   - `\overline{}` : 오버라인
   - `\underline{}` : 언더라인

4. **수학 기호**

   - `\cdot` : 점
	   - $$\cdot$$
   - `\ldots` 줄임표 ellpsis
	   - $$\ldots$$
   - `^`, `+` , `-` , `*`,`\times` , `/`, `\div` : 기본 연산자
   - `\leq` , `\geq` : 이등호
	   - $$\leq \geq$$
   - `<` , `>` : 부등호
   - `\neq`
	   - $$\neq$$
   - `\appotox`  근사치 approximately equal to
	   - $$\approx$$
   - `\pm`
	   - $$\pm$$
   - `\mp`
	   - $$\mp$$
1. 화살표
	- `\rightarrow`, `to`
	- `\leftarrow`, `\gets`
	- `\uparrow`
	- `\downarrow`
2. **배열** 

   - `\begin{array}{}` : 배열 시작
   - `\end{array}` : 배열 끝
   - `l` , `c` , `r` : 배열 정렬 (왼쪽, 가운데, 오른쪽)

2. **수식 환경** 

   - `\begin{equation*}` : 수식 환경 시작
   - `\end{equation*}` : 수식 환경 끝

3. **참조**

   - `\label{}` : 참조 레이블 지정
   - `\ref{}` : 참조

이러한 기본 문법을 사용하여 LaTeX 문서를 작성할 수 있습니다.