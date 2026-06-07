<h2 id="intersection-타입">Intersection 타입</h2>
<blockquote>
<p><strong>인터섹션(Intersection) 타입</strong>이란?
 : 여러 타입을 모두 만족하는 하나의 타입</p>
</blockquote>
<p>&amp;(ampersand)를 사용해 2개 이상의 타입을 조합하는 경우, 이를 인터섹션 타입이라고 부른다.</p>
<p>이전에 배운 유니온 타입이 <strong>&quot;OR&quot;</strong>이라는 의미라면, 인터섹션 타입은 <strong>&quot;AND&quot;</strong>라고 이해하면 된다.
<br /></p>
<img src="https://velog.velcdn.com/images/choco_dev/post/cca7c2f1-6bc3-4a12-939d-2938eda3afa1/image.png" width="70%" />

<br />

<p>ex)</p>
<pre><code>interface Person {
  name: string;
  age: number;
}

interface Developer {
  name: string;
  skill: number;
}

type Capt = Person &amp; Developer;</code></pre><br />

<p>위 예제 코드는 Person 인터페이스의 타입 정의와 Developer 인터페이스의 타입 정의를 <strong>&quot;&amp;&quot; 연산자</strong>를 통해 합쳤다. 그리고 Capt 이라는 새로운 타입에 할당하였다.</p>
<p>이런 방식으로 만들어진 Capt 타입은 아래와 같이 정의된다.
<br /></p>
<pre><code>{
  name: string;
  age: number;
  skill: string;
}</code></pre><p>이렇게 <strong>&quot;&amp;&quot; 연산자</strong>를 사용하여 여러 개의 타입 정의를 하나로 합치는 방식을 인터섹션 타입 정의라고 한다.</p>
<br />
<br />