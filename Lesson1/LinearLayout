# Lesson1. LinearLayout

## LineaLayout이란?
+ LinearLayout은 레이아웃을 짤때 레이아웃의 비율을 나누어서 아이템을 넣는 레이아웃입니다.

+ LinearLayout은 화면전체를 1로 기준잡고 layout_weight를 이용하여 비율을 나눠 아이템을 배치하는 형식입니다.

+ LinearLayout과 같이 대중적으로 사용되는 RelativeLayout은 Lesson2에서 다루도록한다.

## 왜 LinearLayout을 사용하는가

+ LinearLayout은 화면 전체를 1로두고 아이템을 배치하는 형식으로 안드로이드 초보자들이 가장 쉽게 레이아웃을 접할 수 있는 형식입니다.
 
 + 하지만 현재 ConstraintLayout이 대중화 되고있는 추세로 Linear와 Relative의 사용률이 낮아지고 있습니다.

 + 현재 많이 사용되고 있는 ConstraintLayout은 Lesson3에서 다룰 예정입니다.

## LinearLayout 기초상식

* vertical과 horizontal의 차이
    * vertical과 horizontal의 차이는 비율을 지정해줄때 가로를 기준으로 비율을 지정해주는것과 세로를 기준으로 비율을 지정해주는것에 차이가 있다.
     
     * vertical은 세로의 길이 비율을 조절할때 사용하는 방식이다.
    
    * vertical을 사용하여 아이템 사이즈를 지정해줄때 width를 match_parent로 지정해주고 height를 0dp로 지정해주어 아이템의 크기를 바꿔준다.

    * 하지만 horizontal은 반대로 width를 0dp height를 match_parent로 지정해준 후 아이템의 사이즈를 조정한다.

    * 레이아웃 비율조정은 android:orientation 부분에서 지정해준다.

* weight_Sum
    
    * weight_Sum은 레이아웃의 전체크기를 지정해준 후 비율을 조정해줄때 사용하는 방식이다.
    
    * 만약 weight_Sum을 10으로 지정해주면 레이아웃의 전체크기는 10으로 지정되어 비율을 조정할 수 있다.

    * 아이템에서 weight를 지정해주는 것 보다는 결과를 조금 더 빨리 눈으로 볼 수 있다는 점이 있다.

## LinearLayout을 사용해보자
<pre><code>android:layout_width="match_parent"
android:layout_height="0dp"        android:layout_weight="0.25"
android:background="@android:color/darker_gray"/>
</code></pre>

* 여기서 가장 주목해서 보아야되는 코드는 layout_weight이다

* weight를 이용해 레이아웃 전체 비율의 크기를 정해준다. 

* 만약 똑같은 레이아웃 4개가 존재하면 저 View 부분은 전체 레이아웃 부분의 4분의 1을 차지하게 된다.

### 예시화면
![example](https://user-images.githubusercontent.com/26649912/45791907-968a6980-bcc6-11e8-8238-b751c329a717.PNG)

* layout_weight를 사용하여 View의 사이즈를 조정후 background_color를 다른 색으로 지정해주어서 뷰들을 4등분 시켰습니다.

## 마치며
 * 이번 Lesson1에서는 LinearLayout 간단 사용법을 정리해보았습니다.
 * Lesson2에서는 Linear와 함께 가장 대중적으로 사용됬던 RelativeLayout에 관해 정리하겠습니다..
