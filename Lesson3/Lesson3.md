# Lesson3

## ConstraintLayout

### ConstraintLayout이란?

* ConstraintLayout은 2016년 Google IO 행사에서 발표된 새로운 레이아웃 입니다.
* ConstraintLayout의 발표로 기존 안드로이드 스튜디오에서 기본으로 세팅되어있던 레이아웃인 RelativeLayout에서 ConstraintLayout으로 바뀌는 계기가 됩니다.
* ConstraintLayout은 앞서 소개했던 LinearLayout과 RelativeLayout을 합친 레이아웃 입니다.

### ConstraintLayout 기본상식

#### 위치지정

* 위치는 우리가 기존에 사용했던 방식을 그대로 사용합니다.
* 가로축은 Left,Right,Start,End를 주로 사용하고 세로축은 Top,Bottom,Baseline(문자열 시준선)을 주로 사용합니다.
* 또한 레이아웃 전체를 사용하여 위치를 지정하고 싶을떄는 속성에 parent를 추가해주면 됩니다.

```xml
<Button
    android:layout_width="wrap_content"
    android:layout_height="wrap_content" 
    android:text="first" 
    android:id="@+id/first"/>

    <Button
        android:id="@+id/button"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="second"
        app:layout_constraintLeft_toRightOf="@id/first" />

    <Button
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="center"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />
```

* second 버튼은 toRightOf 속성을 사용하여 first 버튼의 오른쪽에 배치합니다.
* 또한 center 버튼은 모든 속성을 parent에 맞추어 버튼을 정가운데에 배치합니다.

#### bias와 ratio

##### bias

* bias는 치우침을 조정할 수 있는 기능입니다.
* 치우침 기능을 이용하여 배치되어있는 버튼을 자유자재로 움직일 수 있습니다.
* bias는 vertical과 horizontal을 사용하여 조정합니다.

```xml
 <Button
        android:id="@+id/first"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginStart="8dp"
        android:layout_marginEnd="8dp"
        android:text="bias"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintHorizontal_bias="0.8"/>
```

* start와 end 부분을 parent 속성을 주어 중앙에 배치하고 bias 속성을 0.8로 두어 레이아웃의 가로방향으로 0.8 지점에 버튼을 배치합니다.

##### Ratio

* ratio는 뷰의 크키를 지정해줄때 사용하는 속성입니다.
* ratio를 사용하여 뷰의 비율을 지정해 줄 수 있습니다(linear의 weight와 비슷한 속성)

```xml
<View
      android:layout_width="match_parent"
      android:layout_height="0dp"
      android:background="@android:color/holo_red_dark"
      app:layout_constraintDimensionRatio="1:0.5"/>
```

* ratio 속성을 이용하여 뷰의 가로세로 길이의 비율을 지정해줍니다.(앞-가로,뒤-세로)
* ratio를 match로 주어 가로 전제길이의 절반이 세로길이가 되어 뷰의 크기가 지정됩니다.

### ConstraintLayout을 사용해보자!
![1](https://user-images.githubusercontent.com/26649912/48824381-7a2eaa00-eda7-11e8-8749-764e57bd32a2.PNG)

```xml
    <EditText
        android:inputType="text"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_marginTop="8dp"
        android:layout_marginBottom="8dp"
        android:hint="id"
        android:id="@+id/id"
        android:layout_margin="12dp"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintTop_toTopOf="parent"/>
    <EditText
        android:id="@+id/pw"
        android:inputType="textPassword"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="pw"
        android:layout_margin="12dp"
        app:layout_constraintTop_toBottomOf="@id/id"/>
    <Button
        android:layout_width="match_parent"
        android:layout_height="0dp"
        app:layout_constraintDimensionRatio="1:0.15"
        android:layout_margin="12dp"
        app:layout_constraintTop_toBottomOf="@id/pw"
        android:text="로그인"/>
```

* id edittext를 중앙에 배치후 bottom 속성을 활용해 pw와 로그인 버튼을 배치했습니다.
* 또한 Button의 사이즈를 ratio를 활용해 지정해주었습니다.

### ConstraintLayout 설명을 마치며

* 이번에 ContraintLayout을 설명하면서 Layout의 발전에 관한 설명을 마무리할까 합니다.

* 다음에는 Android 기초상식중 한가지인 Android 생명주기에 관해 이야기 할까 합니다.
* 세가지 레이아웃중 이거를 사용하라고 정해진 것은 아니지만 각자 자신에게 맞는 Layout으로 Android Application을 개발했으면 합니다.