# 앱 개발 할땐하더라도 코틀린 한번정돈 괜찮잖아

## Kotlin 기초 문법

### 출력해보기

```kotlin
println("hello_world!")
```

* hello_world 출력을 할 수 있다!

```kotlin
val a=10 // Int Type 추론
val b:Int=15 // Int Type
val c: Int// 만약 초기화를 해주지 않으면 타입이 필요하다.
```

* 코틀린은 val을 사용하여 입력을 하고 타입을 추론할 수 있다.
* 만약 초기화를 해주지 않으면 타입을 선언해 주어야 한다.

### Kotlin 타입 정리

* Double
* Float
* Int
* Short
* Char
* String
* Boolean

### Kotlin 삽입하기

``` kotlin
val i = 10
val s = "i = $i"
```

* s의 값에 10이 들어감!

### 배열

``` kotlin
val arr=arrayof(1,2,3,4)
arr.inetator().forEach{println(it)} // 배열 출력
println(arr[2]) // 3 출력
```

### null 처리

* kotlin에서는 ?로 null 처리를 할 수 있다.

```koltin
    val text: String?=null
```

* 또한 null을 안전하게 처리해주기 위해서 ?.을 사용한다.

```kotlin
val text: String? = s?.toUpperCase()
println(text)
```

* ?.은 우항이 null이 아닐때 오른쪽의 함수를 실행시키는 것을 말한다.
* java는 if/else구문을 사용해주어야 하지만 kotlin에서는 더 간단한게 처리해줄 수 있다.

* 또한 ?:을 사용하여 간단하게 if/else를 만들어 줄 수 있습니다.

```kotlin
val name = str ?: "???"// if(name != null) str else "???"와 같은 코드
```

* 마지막으로 !!을 사용하여 강제로 not null 처리를 해줄 수 있습니다.

```kotlin
fun none(t: String?) {
    val text: String = t!!
    println(text.length)
}

fun main(args: Array<String>) {
    none(null)
}
```

* !!을 사용하여 강제 not null 처리를 해주었지만 null 값이 들어와서 NullPointerException이 난다.

### when(swicth)

* when은 java의 swicth 역할이다.

``` kotlin
val v = 11
    when(v) {
        1, 2 -> println("1 or 2")
        // 조건을 콤마로 묶을 수 있음
        in 3..13 -> println("between 3 and 13")
        // in, !in, 범위, 컬렉션을 사용해서 값 검사
        is Int -> println("int")
        // is, !is로 타입 여부 확인
        else -> println("else")
    }
```

### 함수

* kotlin에서는 함수를 생성하여 기능을 수행할 수 있다.

```kotlin
fun plus(a:Int=2,b:Int):Int{
    return a+b
}
fun main(args:Array<String>){
    fun print(){
        println("print!")
    }
    println(plus(5,5))//10 출력
    println(plus(b=5)) //5 출력
    print()
}
```

* 함수를 구현하여 기능을 사용할 수 있습니다.

### 클래스

* 코틀린에서도 클래스를 사용할 수 있습니다!

```kotlin
class None // 빈 클래스

class Print(name: String){
    init //클래스에 들어오면 바로 실행
    {
        println("&name")
    }
}
fun main(args:Array<String>){
    val print=Print("GramDefined")
}
```

* 클래스를 활용하여 기능들을 구현할 수 있습니다!

### 더 다양한 내용

* [JoMingyu- Awesome_Kotlin](https://github.com/JoMingyu/--Awesome-Kotlin--)
* [[Kotlin] 코틀린 null 처리 - ? ?. ?: !!, let, lateinit, 제너릭, 플랫폼 타입](https://tourspace.tistory.com/114)

## Android에서 Kotlin 적용해보기

* tool: Android Studio
* 코틀린을 사용하기 위해서 처음시작시 kotlin 모드로 설정해주어야 한다.

```kotlin
override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)
        val text = findViewById<TextView>(R.id.text)
        text.setOnClickListener { text.text = "터치함" }
    }
```

* val로 텍스트를 정의해주고 .setOnClickListener를 사용하여 Toast 기능을 사용해준다.
