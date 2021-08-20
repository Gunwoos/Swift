# Optional

- 잠재적 오류를 다루기 위해 사용하는 개념
- 잘못된 입력값 또는 이미 삭제된 반환값을 오류처리 하지 않고 nil 이라는 것으로 반환하여 값이 없다는 것을 알림

- 옵셔널 타입 선언과 정의
	~~~
	var optionalInt : Int?
	var optinalArray : [String]?
	var optionalDictionary : Ditcionary<String, String>?
	var optionalClass : AnyObject?
	~~~
	- 옵셔널 타입으로 선언하면 자동으로 nil 로 초기화됨
	~~~
	var optionalInt : Int? = 3
	var optionalArray : [String]? : [ "A", "B", "3" ]
	var optionalDictionary : Dictionary<String, String>? = ["A":"a", "B":"b"]
	~~~
	- 일반 변수처럼 값을 할당하면 됨

- 옵셔널 해제
	- 명시적 해제 ( Forced Unwrapping ) : nil 여부와 관계없이 옵셔널 해제
		- 강제적인 해제
		- 비강제적인 해제
	- 묵시적 해제
		- 컴파일러에 의한 자동 해제
		- 연산자를 사용한 자동 해제

	- 명시적 해제
		~~~
		var optionalInt: Int? = 3
		print(optionalInt!)  // 3
		print(optionalInt) // Optional(3)
	
		Int("123")! + 30 // 153
		~~~
		- 단 ! 사용 시 옵셔널 변수를 unwrapping 했을 때 값이 nil 이 아니라는 확신이 이어야 함, 그래서 ! 사용하기 전에 옵셔널 값이 nil 인지 점검해야함
			~~~
			var str = "123"
			var optionalInt = Int(str)

			if optionalInt != nil {
				print(optionalInt!)
			}else {
				print(optionalInt)
			}
			~~~
	- Optional Binding
		- 비강제적 해제
		- 옵셔널 변수에 값이 있는지 확인하여, 값이 있다면 옵셔널에서 추출된 값을 상수나 변수로 할당해서 사용
		- 단, 옵셔널 변수가 절대 nil 값이 들어가지 않을 것이라는 보장이 있을 경우에는 ! 사용하는 것이 효율적임
			~~~
			//if 문 Binding
			var str = "ABC"
			if let str2 = Int(str){
				print(str2)
			}else{
				print("It is nil")
			 }

			// guard 문 Binding : 실행 흐름상 옵셔널 값이 해제되지 않으면 더 이상 진행이 불가능할 정도의 경우에 사용하는 것이 좋음
			func doBinding( str : String ){
				guard let str = str else {
					return
				}
				print(str)
			}
			doBinding(str:nil)
			~~~ 
	- Implictily Unwrapped Optionals ( 묵시적 해제 )
		- 옵셔널 타입이지만 별도의 해제 없이 연산 및 사용이 가능함
		- 단 변수가 nil 이 아니라는 확신이 있을 때 사용
			~~~
			var str : String! = "ABC"
			print(str) // ABC
			~~~		
