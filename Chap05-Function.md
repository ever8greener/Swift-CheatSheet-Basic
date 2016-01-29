
### 함수에 대한 설명들

```swift

// 두개이상의 인자를 가지는 함수

func getAverage(X:Int...) -> Double {
    var total:Double = 0
    
    for num in X {  // 요런식으로 사용가능
        total = total + Double(num)
    }
    
    return (total / Double(X.count) )
}

getAverage(3,3,3,3) -> result: 3 ( 평균값이므로 )
getAverage(0,10) -> result : 5 ( 평균값이므로 )
```

### 내 외부 동일한 파라미터인자 사용하기
// 이전에 쓰던 # 문법 이제 없어짐.
// 참고: https://teamtreehouse.com/community/it-seems-that-swift-2-no-longer-uses-hash-shorthand-notation-for-external-names-of-parameters-of-functions


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
// ### in-out 파라미터 사용하면  return 하는 것 보다 편함.
```swift
func swapVal( inout a: Int , inout b:Int ){
    let tmp = a
    a = b
    b = tmp
 }

var a = 10 , b = 3

swapVal(&a, b: &b )
print("a = \(a) , b = \(b)") //==> "a = 3 , b = 10\n"
```
