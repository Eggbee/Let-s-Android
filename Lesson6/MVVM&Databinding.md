# MVVM Pattern과 Databinding을 사용해보기

## MVVM이란?

* mvvm은 Design Patter중 한가지로 Model,View,ViewModel로 이루어져 있다.
* mvvm pattern을 사용하면 조금 더 효율적인 어플리케이션을 개발할 수 있습니다.

## MVVM 파헤쳐보기

### View

* 화면에 보여지는 레이아웃 부분.
* UI와 관련된 로직을 수행하는 부분이다.

### ViewModel

* View에 연결할 데이터과 명령으로 구성되어 있다.
* 변경상태를 View에 전달합니다.
* UI의 상태를 변경할건지는 View에서 관리합니다.

![download](https://user-images.githubusercontent.com/26649912/53961671-86f3c580-412c-11e9-8490-b2aa70e39c02.png)

## MVVM 적용해보기

### 기초 세팅

* Databinding 세팅을 위해 gradle에 기초 세팅을 해야합니다.(Andrid studio 3.3.1 기준)

``` groove
apply plugin : "kotlin-kapt"

android{
    dataBinding {
        enabled = true
    }
}
```

### layout 설정 바꿔주기

* Databinding을 설정해주기 위해서는 layout 태그를 사용해주어야 합니다.
* 또한 data를 xml코드 상에서 받아와 읽고 쓰는 처리를 해주어야 합니다.

```xml
<layout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto">

    <data>
        <import type="android.view.View" />
        <variable
            name="info"
            type="com.example.databindingexample.MainViewModle" />
    </data>

    <android.support.constraint.ConstraintLayout
        android:layout_width="match_parent"
        android:layout_height="match_parent"/>
</layout>
```

* 또한 데이터를 읽고 쓰는 처리를 하기 위해 xml 코드 상에서 작성을 해주어야 합니다.

```xml
        <EditText
            android:id="@+id/editText"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:hint="@string/string_writing"
            android:text="@={info.text}"
            app:layout_constraintStart_toStartOf="parent"
            app:layout_constraintTop_toTopOf="parent" />

        <EditText
            android:id="@+id/editText2"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:layout_marginBottom="8dp"
            android:hint="@string/string_writing"
            android:text="@={info.text2}"
            app:layout_constraintBottom_toBottomOf="parent"
            app:layout_constraintStart_toStartOf="parent"
            app:layout_constraintTop_toTopOf="parent" />
```

### MainViewModel 코드 작성

* 이제 본격적으로 데이터를 수정하거나 이벤트를 처리해주어야 합니다.
* ViewModle에서 데이터를 처리해주기 위해 먼저 선언을 처리해야 합니다.

```kotlin
val text=ObservableField<String>("")
```

* 또한 이벤트 처리를 위해 함수생성후 이벤트 처리를 진행해주어야 합니다.

```kotlin
fun minus(view:View){
            result.set((("${text.get()}".toInt()-"${text2.get()}".toInt()).toString()))
    }
```

### MainActivity에 Databinding 세팅하기

* 마지막으로 MainActivity에 Databinding 설정을 세팅해주면 작업이 완료됩니다.

```kotlin
val binding = DataBindingUtil.setContentView<ActivityMainBinding>(this, R.layout.activity_main)
        binding.info = MainViewModle()
```

* DatabindingUtil을 이용하여 layout을 불러오고 binding을 이용해 xml에서 세팅했던 데이터의 이름인 info를 불러와주면 자동적으로 세팅이 완료됩니다~!

## 끝마치며

* 이번에는 현재 가장 많이 사용되고 있는 디자인 패턴인 MVVM에 대해 공부해보았습니다.
* 다음에는 AAC를 이용하여 생명주기를 관리하여 어플리케이션을 제작해 보도록 하겠습니다.