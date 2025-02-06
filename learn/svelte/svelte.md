### state 상태값 
- markup 영역에서 { 이름 } 으로 표현
![[Pasted image 20240330161211.png|300]]
### reactivity 반응성
- $:
- 변화를 즉시 반영
- 변수, 블록, 조건을 사용할 수 있음
![[Pasted image 20240330161447.png|400]]
### component
```svelte
<script>
	// 컴포넌트 불러오기
	import Header from './header'
</script>

// markup 배치
<Header />
```
### props
- 컴토넌트간 통신방법
- 상위 컴포넌트 -> 하위 컴포넌트 단방향
- ![[Pasted image 20240330162633.png|600]]
- 하위 콤포넌트에서 전달 받은 값을 변경해도 상위컴포넌트의 상태는 변경되지 않음
### store
- 전역으로 사용가능한 상태값 저장
- 
### html dom제어
- 논리 블록
	- ![[Pasted image 20240330163441.png|300]]
- 반복블록
	- ![[Pasted image 20240330163702.png|300]]
