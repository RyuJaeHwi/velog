<h2 id="type-alias-타입-별칭">Type Alias (타입 별칭)</h2>
<h3 id="타입-별칭-시작">타입 별칭 시작</h3>
<blockquote>
<p><strong>타입 별칭(Type Alias)</strong>이란?
 : type 키워드를 사용해서 사용자가 직접 타입 변수를 정의하는 것</p>
</blockquote>
<p>선언 기본 구조는 다음과 같다.</p>
<p>그리고 이 별칭은 대문자로 시작하여 일반 변수와 차이를 두는 것이 관습이다.
<br /></p>
<pre><code>type 별칭 = 타입;</code></pre><br />

<p>왜 굳이 또다른 별칭을 지어서 타입을 표현하는 것일까?</p>
<p>아래 예제 코드들을 통해 직접 이유를 확인해보자.
<br /></p>
<p>ex)</p>
<pre><code>let Dom: {version:string, el:(selector:string)=&gt;void, css:(prop:string)=&gt;void} = {
  version: '0.0.1',
  el(){},
  css(){}
};</code></pre><br />

<p>위 선언된 Dom 타입은 매우 길고 복잡하게 정의되어 있다.</p>
<p>한두번 사용하는 것도 아니고 매번 이런 식으로 길고 복잡하게 작성해야 한다면 개발자 입장에서 매우 어려운 일이다.
<br /></p>
<p>이러한 불편함을 해소하기 위해 우리는 <strong>타입 별칭</strong>을 사용하는 것이다.</p>
<br />

<p>ex)</p>
<pre><code>type Operation = {
    version: string, 
    el: (selector:string) =&gt; void, 
    css: (prop:string) =&gt; void
}

let Dom: Operation = {
  version: '0.0.1',
  el(){},
  css(){}
};</code></pre><br />

<p>Operation 이라는 별칭으로 version, el, css 속성들을 따로 묶어서 저장한 후, Dom 타입이 이를 호출하여 그대로 사용하는 코드로 바꾸었다.</p>
<p>이렇게 바꾸니 해당 타입에 어떤 속성들이 있는지 더 쉽게 확인할 수 있어 매우 편리해졌다.
<br /></p>
<p>만약 해당 타입 별칭 안에 어떤 속성들이 있는지 확인하려면, 에디터에서 별칭에 커서를 갖다 대어 확인하면 된다.
<br /></p>
<img src="https://velog.velcdn.com/images/choco_dev/post/4e3a7d06-0974-4ea7-89f8-20236450a94c/image.png" width="70%" />

<br />

<p>C언어나 JAVA에서 했던 것처럼 앞에 <strong>자료형</strong>을 선언하고 그 뒤에 해당 자료형에 알맞은 <strong>값</strong>을 대입했던 것처럼, 타입도 <strong>&quot;type&quot;</strong>이라는 자료형 선언 후 뒤에 해당하는 타입 값을 넣으면 된다.
<br /></p>
<p>ex)</p>
<pre><code>// type 변수명 = 타입;
type Name = string;
type Age = number;

let name: Name = 'Tom';
let age: Age = 20;</code></pre><br />

<p>타입 별칭을 사용할 때 주의할 점은, 타입 별칭은 확장이 불가능하다.</p>
<p>즉 extends 키워드를 통해 타입 안에 속성을 추가하는 것이 불가능하다는 뜻이다.
<br /></p>
<p>ex)</p>
<pre><code>type Animal = {
  name: string;
};

// Error, 타입 별칭은 extends 사용 불가능 (확장 X)
type Bear extends Animal = { 
  honey: boolean;
};

// Error, 중복 선언 불가능
type Animal = {
  age: number;
};</code></pre><br />
<br />