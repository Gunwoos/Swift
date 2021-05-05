# Collection

- 종류
	- 배열(Array) : 순서에 따라 정렬된 자료형
	- 집합(Set) : 중복되지 않는 데이터들의 자료형
	- 튜플(Tuple) : 종류에 상관없이 데이터들을 모은 자료형
	- 딕셔너리(Dictionary) : 키 값을 사용하여 순서 없이 모인 자료형

- 배열 ( Array )
	- 선언
	~~~
	var array1 = [ 1, 2, 3, 4 ]
	var array2 : [String] = [ "A", "B", "C", "D" ]
	~~~
	- 배열 탐색 방법
		~~~
		// 1. 배열의 길이를 구해 for 문으로 반복하여 탐색
		var array1 = [ 1, 2, 3, 4]
		array1.count // 4
		for i in 0..<array1.count{
			print(array1[i])
		}

		// 2. 이터레이터를 이용
		for i in array1 {
			print(i)
			let index = array1.index(of : i) // 해당 아이템이 몇번째 인덱스인지 알 수 있음
		}

		// 1,2 실행 결과 : 1 2 3 4
		~~~

	- 배열의 동적 선언과 초기화
		~~~
		var abc = Array<String>() // String 타입 배열 선언과 빈 배열 초기화
		
		var abc2 : Array<String> // String 타입 배열 선언
		abc2 = Array() // 빈 배열 초기화
		
		var abc3 = [String]()

		var abc4 : [String]
		abc4 = [String]()
		abc4 = []
		~~~
	- 배열 아이템의 동적 추가
		~~~
		var nums = [Int]() // []
 		nums.append(2) // [2]
		nums.append(3) // [2,3]
		nums.insert(4), at:0) // [4,2,3]
		nums.append(contentsOf : [5,6]) // [4,2,3,5,6]
		~~~

- 집합 ( Set )
	~~~
	var abc : Set = [ "A", "B", "C" ] 
	// 타입 명시를 하지 않으면 문자열 배열로 선언됨
	var abc2 = Set<String>() // 집합 선언 및 빈 집합 초기화
	var abc3 : Set<String> = [ "A", "B", "C" ] // 집합 선언 및 초기화
	~~~

	- 집합 탐색
		~~~
		var abc : Set = [ "A", "b", "'F" ]
		for i in abc{
			print(i)
		} 
		~~~
		
	-	 집합의 동적 추가와 삭제
			~~~
			var num : Set = [ 1, 2, 3, 5]
			num.insert(1) // 집합에 1이 있으므로 추가되지 않음
			num.insert(4) // 집합에 추가됨
			
			num.remove(4) // 집합에 해당 아이템이 있으면 삭제하고, 없으면 nil 반환 
			num.removeAll // 집합의 모든 아이템을 삭제
			~~~

	- 집합 연산
		~~~
		var oddNum : Set = [1,3,5,7,9]
		var evenNum : Set = [2,4,6,8,10]
		var primeNum : Set = [2,3,5,7]

		var set1 = oddNum.intersection(primeNum) // 교집합, 겹치는 아이템을 새로운 집합으로 만듬
		// [3,5,7]
		var set2 = oddNum.symmetricDifference(primeNum // 두 집합 중 어느 한 쪽에만 있는 아이템을 선택하여 새 집합을 만듬)
		// [1,2,9]
		var set3 = oddNum.union(evenNum) // 합집합, 모든 아이템을 합친 집합으로 만듬
		// [1,2,3,4,5,6,7,8,9,10]
		var set4 = oddNum.subtract(primeNum) // 차집합, 기존 아이템 중 겹치지 않는 아이템들로 집합을 만듬
		// [1,9]

		oddNum.isSubset(of : i) //  oddNum이 i 의 부분 집합인지 참, 거짓 반환
		oddNum.isSuperset(of : i ) // oddNum이 i 를 포함하는지 참, 거짓 반환
		oddNum.isStrictSubsetk(of : i ) // isSubset 과 비슷하지만 두 집합이 같은 경우에는 거짓을 반환
		oddNum.isStrictSuperset(of : i ) // isSuperset 과 비슷하지만 두 집합이 같은 경우 거짓을 반환
		oddNUm.isDisjoint(with : i ) // 두 집합 사이에 공통 값이 없으면 true, 하나라도 있으면 false
		~~~

- 튜플 ( Tuple )
	- 여러가지 타입의 아이템을 저장할 수 있음
	-	선언되고 나면 상수적 성격을 가져 값의 추가나 수정이 불가함
		~~~
		let tuple1 = ( "a", 1, 1.5, false )
		~~~

- 딕셔너리 ( Dictionary )
	- 하나의 키는 하나의 데이터에만 연결되어야 함
	- 키는 중복될 수 없음
	- 하나의 딕셔너리에 저장하는 데이터 타입은 일치해야 함
	- 키값을 통해 for ~ in 구문을 이용한 탐색 가능
	
	- 선언과 초기화
		~~~
		var dic1 = Dictionary<String, String>()
		var dic2 = [ String : String ]()
		var dic3 : Dictionary<String, String>
		dic3 = [String : String]()
		// 딕셔너리 타입이 명시되어 있지 않다면 초기화 시 타입을 생략할 수 없음
		~~~

	- 딕셔너리 동적 추가 및 삭제
		~~~
		var item : Dictionary<String, Int>
		item = [ String, Int ]()

		item.updateValue(3, forKey : "book") // 기존 딕셔너리에 해당 키가 있다면 아이템을 수정하고, 없다면 키와 아이템을 새로 추가함
		item.updateValue(5, forKey : "code")

		item["book"] = nil // nil 값을 주어 삭제
		item.removeValue(forKey = "code") //딕셔너리에 해당 키값이 있으면 삭제
		~~~

