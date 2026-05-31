<p><em>(해당 시리즈의 글들은 캡틴판교님의 타입스크립트 핸드북을 통해 공부한 것을 개인적으로 정리한 것입니다.)</em></p>
<br />
<br />

<h2 id="타입스크립트란">타입스크립트란?</h2>
<blockquote>
<p>JavaScript에 타입을 부여한 언어 (= JavaScript에서 확장된 언어)</p>
</blockquote>
<p>이러한 타입스크립트는 브라우저에서 실행하려면 파일을 한 번 변환해주는 작업이 필요한데, 이 변환 과정을 <strong>컴파일(compile)</strong>이라고 한다.</p>
<br />

<h3 id="타입스크립트를-사용하는-이유">타입스크립트를 사용하는 이유?</h3>
<h4 id="에러-사전-방지">에러 사전 방지</h4>
<p>타입스크립트는 에러를 사전에 예방할 수 있다는 장점을 가진다.</p>
<pre><code>// math.ts
function sum(a, b){
    return a + b;   
}</code></pre><pre><code>// math.ts
function sum(a: number, b: number){
    return a + b;
}</code></pre><p>이 두 코드는 전부 두 숫자 a, b의 합을 구하는 함수 코드이다.</p>
<p>하나는 자바스크립트, 하나는 타입스크립트인데 두 함수를 가지고 실제 작동하는 코드를 테스트해보려고 한다.</p>
<br />

<pre><code>sum(10, 20) // 30</code></pre><p>sum 함수를 이렇게 쓰면 10 + 20으로 인식하니 30이 출력된다.</p>
<br />

<pre><code>sum('10', '20'); // 1020</code></pre><p>그러나 이렇게 따옴표로 숫자들을 감싼 경우엔, 문자열로 인식하기 때문에 1020이라고 결과가 나타난다.</p>
<br />

<p>우리는 이러한 자바스크립트의 예기치 않은 동작을 예방하기 위해 타입스크립트를 사용하게 된 것이다.</p>
<br />

<pre><code>// math.ts
function sum(a: number, b: number){
    return a + b;
}

sum('10', '20'); // Error: '10'은 number에 할당 불가</code></pre><p>VScode에서도 똑같은 에러가 나타날 것이다.</p>
<br />


<h4 id="코드-자동-완성--가이드">코드 자동 완성 &amp; 가이드</h4>
<p>타입스크립트는 개발 툴 기능을 최대한으로 활용 가능하다.</p>
<p>자바스크립트 코드와 비교하여 어떤 활용이 가능한지 확인해보도록 하자.
<br /></p>
<pre><code>// math.ts
function sum(a, b){
    return a + b;
}

var total = sum(10, 20);
total.toLocaleString();</code></pre><p>sum() 함수를 통해 얻은 합을 toLocaleString()을 적용한 코드이다.</p>
<span style="font-size: 16px; color: gray;">
  <i>
toLocaleString()이란?
특정 언어의 표현 방식에 맞게 숫자를 표기하는 API
  </i>
</span>

<br />
<br />

<p>위 코드에서는 자바스크립트가 total이라는 변수의 타입이 number라는 것을 인식하지 못하고 있다는 문제가 있다.
<br /></p>
<p>얼핏 보면 타입만 문제라 별 것 아닌 것처럼 느껴질 수 있지만, 이는 개발자가 스스로 sum() 함수의 결과를 예상하고 타입이 무엇인지 가정해야 한다는 번거로움이 있다.</p>
<p>자바스크립트가 제공하는 API인 toLocaleString()을 하나하나 작성해야하고, 오타라도 난 경우엔 브라우저에서 실행했을 때에만 에러가 발생한 것을 확인할 수 있다는 문제도 존재한다.</p>
<br />

<p>이를 타입스크립트로 고치면 어떻게 될까?
<br /></p>
<pre><code>// math.ts
function sum(a:number, b:number): number {
    return a + b;
}

var total = sum(10, 20);
total.toLocaleString();</code></pre><p>total의 변수가 무슨 타입인지 이미 지정이 되어있으니 VSCode에서 해당 타입에 대해 사용 가능한 API를 미리보기로 확인할 수 있다.</p>
<p>즉 하나하나 찾는 것이 아니라, tab 키 등으로 빠르게 바로 자동완성을 할 수 있는 것이다.</p>
<br />
<br />
<br />

<p>지금까지 타입스크립트와 자바스크립트를 비교하며 왜 타입스크립트가 점점강세가 되어가고 있는지를 공부해보았다.</p>
<br />

<p>다음부터는 타입스크립트의 기본 타입부터 차근차근 공부해볼 것이다.</p>
<br />