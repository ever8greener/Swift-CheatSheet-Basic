
## Fuction (함수)

### 두개이상의 인자를 가지는 함수

```swift
func getAverage(X:Int...) -> Double {
    var total:Double = 0
    
    for num in X {  // 요런식으로 사용가능
        total = total + Double(num)
    }
    
    return (total / Double(X.count) )
}

getAverage(3,3,3,3) //결과: 3 ( 평균값이므로 )
getAverage(0,10)    //결과: 5 ( 평균값이므로 )
```

### 내 외부 동일한 파라미터인자 사용하기

 이전에 쓰던 `# 문법`은 이제 없어짐.

 참고: https://teamtreehouse.com/community/it-seems-that-swift-2-no-longer-uses-hash-shorthand-notation-for-external-names-of-parameters-of-functions


아래 문법은 더이상 사용하지 않는다.
```swift
func combineStr2 ( #stringa:String, stringb:String) -> String { // deprecated.
```
아래는 바뀐 문법은 동일한 이름을 두번 써주는 방식이다.

```swift
func combineStr2 ( stringa stringa:String, stringb:String) -> String {  
    return stringa + " " + stringb
}

combineStr2(stringa: "동일한", stringb: "파라미터사용했어요")

```
### in-out 파라미터 사용
inout 키워드를 사용하면  parameter 로 받은 값을 함수내에서 직접 변경할 수 있다 ( 즉 외부값을 변경할 수 있다!). return 값을 처리하는 일반적인 방식보다 편할 수 있다.(다만 in-out 키워드가 상용코드에 많이 쓰이는지는 확인한 적 없음)

```swift
func swapVal( inout a: Int , inout b:Int ){
    let tmp = a
    a = b
    b = tmp
 }

var a = 10 , b = 3

swapVal(&a, b: &b )
print("a = \(a) , b = \(b)")  // 결과: "a = 3 , b = 10\n"
```
