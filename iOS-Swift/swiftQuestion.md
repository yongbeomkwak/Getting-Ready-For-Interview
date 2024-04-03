# 스위프트 100문 100답을 목표로!

<details>
<summary>1. 스위프트에서 Extension은 어떻게 사용되나요? (What are Extensions used for in Swift?) [3] </summary>

<ul>
  <li> Extension은 클래스, 구조체, 열거형 타입에 새로운 메서드, 프로퍼티 , 생성자를 추가적으로 정의해 사용하기위해 사용됩니다.</li>
    <li>이 때 저장 프로퍼티는 정의 불가, 연산 프로퍼티만 정의 가능</li>
      <li>convenience init만 정의</li>
</ul>

</details>

</br>

<details>
<summary>2. Swift의 upcasting과 downcasting의 차이에 대해서 설명해보세요. (What is the difference between Upcast and Downcast in Swift?) [2]</summary>

<ul>
  <li> 서로 상속 관계에서 자식 클래스를 부모 클래스로 타입캐스팅 하는 것이 업 캐스팅 as 를 사용 </li>
    <li>다운캐스팅도 as 를 사용하지만 다운 캐스팅은 실패할 수도 있기 때문에 as?나 as!를 사용합니다.</li>
</ul>

</details>

<br>


<details>
<summary>3. == 연산자와 === 연산자는 어떻게 다른가요? (What’s the difference between == and ===?) [1] </summary>

<ul>
  <li> == 연산자는 값을 비교하는데 사용되고, === 연산자는 참조 값을 비교하는데 사용됩니다.</li>
</ul>

</details>


</br>

<details>
<summary>4. Dispatch Queue의 Serial Queue에 대해서 설명해보세요. (What is a Serial Queue?) [1] </summary>

<ul>
  <li> 시리얼 큐는 스레드에 먼저 할당한 작업이 끝나야 대기 중인 작업을 스레드에 할당합니다.</li>
</ul>

</details>


</br>

<details>
<summary>5. let과 var의 차이는 무엇인가요? (What is the difference between let and var in Swift?) [1] </summary>

<ul>
  <li> let은  주소에 대한 포인터를 바꿀 수 없다는 의미, var는 값을 변경할 수 있는 변수를 선언하기 위한 명령어입니다.</li>
</ul>

</details>


</br>

<details>
<summary>6. function과 method의 차이를 말해보세요. (What are the differences between functions and methods in Swift?) [1]</summary>

<ul>
  <li> function은 재사용 가능한 코드 블럭, 메서드는 클래스, 구조체, 열거형 안에 정의된 function</li>
</ul>

</details>

</br>

<details>
<summary>7. mutaing 키워드의 의미를 설명해보세요. (What does the Swift mutating keyword mean?)[2] </summary>

<ul>
  <li> 스위프트에서 값 타입 프로퍼티들을 인스턴스 메서드에 의해 수정될 수 없습니다.</li>
   <li> mutating 키워드가 붙은 메서드를 실행하면 스위프트는 새로운 구조체를 생성해 변경된 프로퍼티의 값을 할당하고 반환해 현재 구조체를 대체합니다. 구조체의 불변성을 지키기 위해 이런 방법을 사용합니다.
</li>

</ul>

</details>


</br>

<details>
<summary>8. 프로토콜과 클래스의 차이를 설명해보세요. (What’s the difference between a protocol and a class in Swift?)
 </summary>

<ul>
  <li> 클래스는 인스턴스 메서드의 실제 구현체를 가지고 있지만 프로토콜은 메서드의 인터페이스만 가지고 있습니다. 프로토콜이 구현체를 가지게 하려면 프로토콜의 Extension을 만들어 구현체를 작성할 수 있습니다.</li>

</ul>

</details>


</br>

<details>
<summary>9. Class와 Struct의 공통점과 차이점을 설명해보세요. (What Classes and Structs have in common in Swift and what are their differences?)
 </summary>

<ul>
  <li> Class 와 Struct 모두 프로퍼티를 정의해 데이터를 저장하고 인스턴스를 만들어 객체의 형태로 사용할 수 있습니다. [6]</li>

</ul>

</details>


</br>

## 16. 강한 참조는 무엇이고 왜 필요한가요? (What’s a strong reference, and why do we need it?)

</br>

## 17. strong, weak, unowned reference는 각각 언제 사용할까요? (When to use strong, weak and unowned references?)

</br>

## 18. Array, Set, Dictionary의 차이점이 뭘까요? (What's the main difference between the Array, Set and Dictionary collection type?)

</br>

## 19. required 키워드에 대해서 설명해보세요. (What does the required keyword in Swift mean?)

</br>

## 20. Self와 self의 차이가 뭘까요? (What's the difference between Self vs self?)

</br>

## 21. Array보다 Set을 사용하는게 더 좋을 때는 언제일까요? (When to use a set rather than an array in Swift?)

</br>

## 22. Trailing Closure에 대해서 설명해보세요. (What is trailing closure syntax?)

</br>

## 23. @objc는 언제 사용하나요? (When to use @objc attribute?)

</br>

## 25. DispatchQueue.main.async 와 DispatchQueue.main.sync 의 차이를 설명해보세요. (Explain the difference between DispatchQueue.main.async and DispatchQueue.main.sync?)

</br>

## 26. Defer에 대해 설명해보세요. (Explain the defer usage in Swift)


</br>

## 27. open과 public 키워드의 차이를 설명해보세요. (What is the difference between open and public keywords in Swift?)

</br>

## 28. fileprivate을 설명하고 언제 사용하면 좋을지 이야기해보세요. (When to use fileprivate access modifier in Swift?)


</br>

## 29. fileprivate과 private의 차이를 설명해보세요. (What is the difference between fileprivate and private?)


</br>

## 30. static func 와 class func의 차이를 설명해보세요. (What is the difference between static func and class func in Swift?)


</br>

## 31. Function과 Closure의 차이를 설명해보세요. (What is the difference between functions and closures?)


</br>

## 32. 스위프트에서 추상 클래스를 만들려면 어떻게 해야할까요? (Is there a way to create an abstract class in Swift?)

</br>

## 33. Any와 AnyObject의 차이를 설명해보세요. (What’s the difference between Any and AnyObject?)


</br>

## 34. 언제 클래스 대신 구조체를 사용하면 좋을까요? (When should you use Structs over Classes?)

</br>

## 35. 언제 구조체 대신 클래스를 선택해야할까요? (When should you use Classes over Structs?)


</br>

## 36. weak과 unowned 의 차이를 설명하고 예를 들어주세요. (Explain the difference between weak and unowned references. Provide an example.)

 
</br>

## 37. unowned는 언제 사용하는 것이 안전할까요? (When is it safe to use an unowned reference?)


</br>

## 38. Swift의 Copy-on-Write에 대해서 설명해보세요. (What is Copy on Write (Cow) in Swift?)


</br>

## 39. staic 변수와 class 변수에 대해 설명해보세요. (What’s the difference between a static variable and a class variable?)


</br>

## 40. ARC와 GC는 어떤 차이점이 있나요? (What is the difference between ARC (automatic reference counting) and GC (garbage collection)?)


</br>

## 41. autoclosure attribute에 대해서 설명해보세요. (What is the autoclosure attribute and when to use it?)



</br>

## 42. GCD의 QoS에 대해서 설명해보세요. (What is QoS (Quality of Service) in GCD?)

</br>

## 43. Hashable 프로토콜에 대해서 설명해보세요. (What is the use of Hashable protocol?)

<br>

## 44. Hashable 프로토콜을 채택하는 커스텀 타입이 Equtable도 채택해야하는 이유가 무엇인가요?

<br/>

## 45. 열거형도 Hashable을 채택했을 때 자동으로 Hashable하게 만들 수 있나요?

<br/>

## 46. init?()과 init()은 어떤 차이가 있나요? (What’s the difference between init?() and init()?)


</br>

## 47. Never 반환 타입에 대해 설명해보세요. (What is the Never return type? When to use it over Void?)


</br>

## 48. weak만 사용하지 않고 unowned도 사용하는 이유가 무엇을까요? (Why can not we just use weak everywhere and forget about unowned?)


</br>

## 49. ARC가 메모리해제를 할 수 없는 상황에 대해 설명해보세요. GC는 해결할 수 있을까요? (Explain the use case when ARC won't help you to release memory (but GC will)?)


</br>

## 50. DispatchGroup에 대해서 설명해보세요. (Explain what is DispatchGroup?)

<br>

## 51. DispatchWorkItem의 장점이 무엇인가요? (What are the benefits of using DispatchWorkItem in Swift?)


</br>

## 52. Concurrent와 Serial Queue가 async, sync와 함께 사용되는 상황에 대해서 설명해보세요. (Explain usage of Concurrent vs Serial Queues with async and sync blocks)


</br>

## 53. @escaping에 대해서 설명해보세요.



</br>

## 54. @objc와 dynamic의 차이에 대해서 설명해보세요. (What's the difference between marking a method as @objc vs dynamic, when would you do one vs the other?)

</br>

## 55. Extension은 메서드를 Override 할 수 있을까요?

</br>

## 56. RunLoop에 대해서 설명해보세요.

</br>

## 57. autoreleasepool에 대해서 설명해보세요.



</br>

## 58. OperationQueue에 대해서 설명해보세요. DispatchQueue와는 어떤 것이 다른가요?

</br>

## 59. final 키워드를 클래스 앞에 붙이면 어떤 효과가 있을까요?


</br>

## 60. vtable에 대해서 설명해보세요.



</br>

## 61. 프로퍼티 옵저버에 대해 설명해보세요.

</br>

## 61. Property Wrapper에 대해 설명해보세요.

</br>

## 62. 고차함수 중 flatMap과 compactMap의 차이를 설명해보세요.


</br>

## 63. High Order Function에 대해서 설명해보세요.



</br>

## 64. 함수형 프로그래밍은 무엇인가요? Swift는 함수형 프로그래밍 언어인가요?



</br>

## 65. 순수함수가 무엇인가요?

</br>

## 66. 그럼 사이드 이펙트는 무엇인가요?


  </br>

## 67. 순수 함수가 왜 필요하다고 생각하나요?


</br>

## 68. 1급 객체(혹은 1급 시민)에 대해서 설명해보세요. Swift에는 어떤 1급 객체들이 있나요?

</br>

## 69. Optional은 내부적으로 어떻게 구현되어 있나요?

</br>

## 70. Swift에서 참조 타입을 말해보세요.


</br>

## 71. String은 왜 subscript로 접근할 수 없을까요?


</br>

## 72. Result 타입에 대해서 설명해보세요.



</br>

## 73. some 키워드에 대해서 설명해보세요.


</br>

## 74. KVC에 대해서 설명해보세요.


</br>

## 75. KVO에 대해서 설명해보세요.


</br>

## 76. typealias 가 무엇인지 말해주세요.


</br>

## 77. associatedType이 무엇인지 설명해주세요.



</br>

## 78. Generic이 무엇이고 어떻게 동작하는지 설명해주세요.


</br>

## 79. GCD의 Barrier에 대해 설명해주세요.


</br>

## 80. DispatchSemaphore를 사용하는 상황을 설명해주세요.


</br>

## 81. DispatchGroup은 언제 어떻게 사용할까요?

</br>

## 82. Codable에 대해서 설명해주세요.

</br>

## 83. 그럼 Codable과 NSCodong의 차이는?


</br>

## 84. COW를 직접 구현한다면 어떻게 구현할 것인지?


</br>

## 85. @Main에 대해서 설명해주세요.

</br>

## 86. Subscription에 대해서 설명해주세요.

## Questions Source
