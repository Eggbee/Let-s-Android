# Lesson2.RelativeLayout

## RelativeLayout이란?

* RelativeLayout이란 부모 레이아웃과 자식 레이아웃이라는 개념을 가지고 아이템의 위치를 이동시킬 수 있는 레이아웃 방식입니다.

* RelativeLayout은 layout_ailgnParent<속성>을 이용하여 레이아웃의 왼쪽 오른쪽 바닥 중앙 부분에 배치를 할 수 있습니다.

* RelativeLayout은 LinearLayout과 같이 가장 대중적으로 사용되었던 레이아웃입니다.

* 하지만 현재 ConstraintLayout의 등장으로 현재 사용룰이 줄고 있습니다.

## RelativeLayout은 언제 활용될까?

*  RelativeLayout은 아이템을 자신이 원하는 위치에 아이템을 배치할 때 빠르게 배치할 수 있는 레이아웃입니다.

* ailParent 성질 뿐만이 아니라 <속성>of 라는 속성을 이용하여서 다른 아이템 근처에 빠른 배치가 가능합니다.

* 그래서 RelativeLayout은 프래그먼트를 활용한 메인화면이나 간단한 ui작업에 주로 사용됩니다.

## RelativeLayout 기본상식

### layout_ailgnParent<속성>

* layout_ailgnParent<속성>은 부모 레이아웃에서 아이템을 배치할 때 사용되는 속성입니다.

* 속성부분에는 top,bottom,left,right,center,center_horizontal,center_vertical이 들어가며 아이템에 layout_ailginParent를 사용하면 속성에 맞는 위치에 아이템이 배치됩니다.

### layout_<속성>of

* layout_<속성>of는 자신이 선택한 아이템을 기준으로 아이템을 배치하는 것을 말한다.

* 만약 속성 부분에 left를 적어 사용하면 기준으로 잡은 아이템의 왼쪽에 아이템이 배치된다.

* 위에 있는 ailgnParent와 of 속성을 이용해서 RelativeLayout을 짠다.

## RelativeLayout을 짜보자.

<pre><code> android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="center"
        android:layout_centerInParent="true"</code></pre>

* RelativeLayout에서 layout_centerInParent로 center 라는 텍스트를 중앙으로 옮겼다

* 굳이 center를 사용하지 않아도 right나 다른 속성을 이용하면 아이템의 빠른 배치가 가능하다.

<pre><code> android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="right|leftof" 
        android:layout_centerInParent="true"
        android:layout_toLeftOf="@id/center"</code></pre>

* 이번에는 toLeftOf라는 속성을 이용하여 center라는 텍스트 왼쪽에 LeftOf 속성을 이용하여 텍스트를 왼쪽으로 옮겼습니다.

* 이 속성을 이용하면 아이템을 원하는 위치에 빠르게 옮길 수 있습니다.

#### RelativeLayout의 특징을 가장 잘 보여주는 예시
![111](https://user-images.githubusercontent.com/26649912/45927964-df684980-bf76-11e8-96b2-e380a13a4d09.PNG)

* xml코드는 따로 첨부하겠습니다.

## Lesson2를 마무리 하면서

* 이번에는 Linear와 함께 가장 널리 사용되었던 안드로이드 레이아웃이였던 RelativeLayout에 대해 알아봤습니다.

* 다음에는 현재 가장 유용하게 사용되고있는 ConstraintLayout에 대해 알아보겠습니다.
