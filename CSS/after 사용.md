# after 사용
> after사용하면서 어려웠던 부분을 정리함

### 아무것도 보이지 않는 문제
content 속성을 적용해주지 않아서 이러한 문제가 발생함
* 해결
아무것도 쓰지 않더라도 content: ""; 를 써주어야 함

### ::after로 화면 전체를 가리고 싶을 때
<img width="1429" alt="after가 전체를 가리지 않을 때" src="https://user-images.githubusercontent.com/68562176/110833316-246cbd00-8251-11eb-990a-bb425b9fa7ea.png">

* 코드    
body태그에 아래와 같이 가상요소를 적용함
<pre><code>
body.login-tab::after {
  content: "";
  position: absolute;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  background-color: rgb(0, 0, 0, 0.8);
}
</code></pre>

* 해결
position이 absolute일 때는 일반적인 문서 흐름에서 벗어나 가장 가까운 위치 지정 부모 요소로부터 상대적인 위치를 정하게 된다.    
그런데 위치 지정 부모 요소가 아무것도 없어서 위와 같은 문제가 발생했다. 따라서 원하는 부모 요소에 position을 지정해주어야한다.
<pre><code>
body {
  position: relative;
  margin: 0;
}
</code></pre>
<pre><code>
body.login-tab::after {
  content: "";
  position: absolute;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  background-color: rgb(0, 0, 0, 0.8);
}
</code></pre>


