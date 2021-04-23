# Statement

- 반복문
	- for~in 문
		~~~
		for 변수명 in 반복범위 or 반복대상 {
			code
		}
		~~~
		- 반복 대상은 순번을 가지는 자료형이나 범위 데이터 등이 사용됨
		- 반복 대상의 길이나 포함되어 있는 데이터의 수만큼 반복
			~~~
			var a = "Swift"
			for i in a.characters{ // a 문자열의 크기만큼 반복되며, i 는 a 문자열의 각 문자를 받아들임
				print(i)
			}
			
			for _ in 0...5{ // 변수값 사용 없이 단순 반복으로 사용할 때
				code 
			}
			~~~ 
			
	- while 문
		- 조건을 만족하는 동안 계속 실행
		- 실행 횟수가 명확하지 않을 때 사용
			~~~
			while <조건> { // 조건식이 결과가 true 인 동안 실행됨
				code
			}
			~~~

	- repeat~while 구문
		- while 문이랑 비슷하지만 code를 최소한 한번은 수행함
		~~~
		repeat{
			code
		}
		while <조건식>
		~~~

- 조건문
	- if 구문
		~~~
		if <조건식> {  // 조건식이 참인 경우에만 code 수행
			code
		}

		if <조건식>{ // 조건식이 거짓일 경우 else 구문의 code  수행
			code
		}
		else{ 
			code
		}
		
		if <조건식>{  // 조건이 여러 개일 경우 사용, else if 의 횟수는 제한이 없음
			code
		}
		else if <조건식2>{
			code
		}
		else{
			code
		}
		~~~

	-	guard 구문
		~~~
		guard <조건문> else { // 조건문의 결과가 거짓일 경우 code 수행
			code
		}
		~~~

	- #available 구문
		- 특정 API 를 사용할 때 사용 가능한 os 버전과 기기를 체크해야 함
			~~~
			if #available( ~~ ) {
				<해당 버전에서 사용할 수 있는 API 구문>
			} else{
				<API 를 사용할 수 없는 환경에 대한 처리>
			}
			~~~
	- switch 구문
		~~~
		switch <비교 대상>{
			case <비교 패턴1> :
				code // 비교 패턴 1에 해당되는 경우 수행
			case <비교 패턴2> :
				code // 비교 패턴 2에 해당되는 경우 수행
				...
			default :
				code // 위 패턴 중 아무것도 일치하지 않을 경우 수행
		}
		~~~ 
		- 여러 case 중 해당되는 경우 그 code 를 수행하고 switch 구문을 종료함
		- 모든 case 가 해당되지 않으면 default code 를 수행
		
 - 제어 전달문
	 - break
		 - 구문의 실행 흐름이나 반복 실행 중인 루프를 즉각적으로 종료하는 데에 사용됨
			 ~~~
			 switch a {
				 case A :
						code
				 case B :
						break  // case B 에 해당될 경우 switch 구문 종료
				 default :
						code
			}

			for i in 0...5 {
				if 조건식 {
					break // 조건식이 참일 경우, 더 이상 반복하지 않고  for in 구문 종료
				}
			}
			 ~~~

	- continue
		- continue 뒤에 올 코드를 수행하지 않고 다음 반복을 시작함
		~~~
		for i in 0...5{
			if i<2{  // 이 조건문을 만족하는 경우 아래의 코드는 수행되지 않음
				continue
			}
			print(i)
		}
		~~~
	- 구문 레이블
		- 흐름 제어문 앞에 구문 레이블을 사용하여 원하는 흐름 제어문을 제어할 수 있음
		~~~
		A : for i in 1...9{
			B : for j in 1...9{
				if j==4 {  // 해당 조건문 만족 시 A 반복문을 종료 시킴
					break A
				}
				print(i,j)
			}
		}
		~~~
	
		
			
