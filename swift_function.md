# Function
- 독립적으로 실행 가능한 코드
- 동일 코드가 재사용 될 경우가 많을 경우 사용됨
- 가독성과 유지보수에 용이

- 함수의 정의
	- 입력값은 하나도 없을 수 있고, 하나 이상일 수 있음
	- 리턴값은 값이 없거나 특정 값을 반환하는데 반환 값은 일반적으로 하나, 만약 둘 이상의 값을 반환해야 할 필요가 있다면 집단 자료형으로 묶어 반환해야 함
	- Input, Output 이 모두 있음 ( Function )
		~~~
		func getNum(num1 : Int) -> Int{
			var a = num1
			return a + a
		}
		~~~
	- Output 만 있음 ( Generator )
		~~~
		func getNum() -> Int{
			return 0
		}
		~~~
	- Intput 만 있음 ( Consumer )
		~~~
		func getNum(num1 : Int){
		}
		~~~
	- Intput, Output 모두 없음
		~~~
		func getNum(){
		}
		~~~
- 함수의 호출
	~~~
	func sumNum(num1 : Int, num2 : Int) -> Int{
		return num1 + num2
	}
	
	var memverA = 12
	var memverB = 24
	
	sumNum(num1 : memverA, num2 : memverB) // 36
	~~~
	
- 함수의 반환값과 튜플
	- 2개 이상의 값을 반환해야 하는 경우
	- 배열, 딕셔너리, 튜플, 구조체, 클래스 등을 사용
	~~~
	func getData(name : String, age : Int ) -> (String,Int){
		var name = name
		var age = age

		return ( name, age )
	}
	~~~
