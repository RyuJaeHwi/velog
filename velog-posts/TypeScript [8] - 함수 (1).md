<h2 id="타입스크립트의-함수-소개">타입스크립트의 함수 소개</h2>
<h3 id="함수의-기본-정의">함수의 기본 정의</h3>
<p>함수는 자바스크립트로 된 모든 애플리케이션를 구성하는 기본 요소이다.</p>
<p>타입스크립트에는 클래스, 네임스페이스, 모듈이 있지만, 함수는 여전히 이 일을 어떻게 할 것인지를 설명하는 데 있어 핵심 역할을 수행한다.
<br /></p>
<p>타입스크립트에서의 함수는 기존의 자바스크립트 함수가 작업을 수월하게 할 수 있도록 몇 가지 새로운 기능이 추가된 상태이다.
<br /></p>
<p>먼저 간단한 자바스크립트 함수를 확인해보자.
<br /></p>
<p>ex)</p>
<pre><code>function sum(a, b) {
  return a + b;
}</code></pre><br />

<p>위 자바스크립트의 함수에 타입을 부여해보면 다음과 같이 된다.
<br /></p>
<p>ex)</p>
<pre><code>function sum(a: number, b: number): number {
  return a + b;
}</code></pre><br />

<p>즉 기존 자바스크립트 함수의 선언 방식에서 <strong>매개변수와 함수의 반환 값에 타입을 추가</strong>하게 되면, 그것이 타입스크립트의 함수 표현이 된다.</p>
<p style="color: gray; font-size: 16px;">
TIP: 함수의 반환 값에 타입을 정하지 않을 때는 void라도 사용하자!
</p>

<br />

<h3 id="함수의-여러가지-표현-방법">함수의 여러가지 표현 방법</h3>
<p>함수를 표현하는 방법에는 크게 3가지가 있다.
<br /></p>
<h4 id="표현1---함수-선언식">표현1 - 함수 선언식</h4>
<pre><code>// 함수 선언식
function myFunc1(x: number, y: number): number {
   return x + y;
}</code></pre><p>가장 기본적인 함수를 정의하는 방법이며, <strong>function</strong> 키워드를 사용하여 완전히 독립적으로 함수를 선언한다.</p>
<p><strong>호이스팅(Hoisting)</strong>이 발생하기 때문에 함수 선언 전에도 호출이 가능하다.
<br /></p>
<h4 id="표현2---함수-표현식">표현2 - 함수 표현식</h4>
<pre><code>// 함수 표현식
let myFunc2 = function (x: number, y: number): number {
   return x + y;
};</code></pre><p>함수를 <strong>특정 변수에 값으로 선언</strong>하여 정의하는 방법이다.</p>
<p>호이스팅(Hoisting)의 영향을 받지 않기 때문에, 반드시 선언한 이후에  호출해야 한다.
<br /></p>
<h4 id="표현3---화살표-함수-arrow-function">표현3 - 화살표 함수 (Arrow Function)</h4>
<pre><code>// 화살표 함수
let myFunc3 = (x: number, y: number): number =&gt; {
   return x + y;
};

// 중괄호 요약 시 - 표현식이 한 줄이면 {} 와 return 생략 가능
let myFunc3 = (x: number, y: number): number =&gt; x + y;</code></pre><p>함수 표현식을 더 간단히 표현하기 위해 사용한다.</p>
<br />

<h3 id="call-signature-함수-타입">Call Signature (함수 타입)</h3>
<blockquote>
<p><strong>Call Signature(함수 타입)</strong> 이란?
 : 함수를 표현하는 타입 (= 문자열의 string, 정수 배열의 number[] 등...)</p>
</blockquote>
<p>함수 타입을 미리 선언하고 뒤에 함수의 식을 붙여 넣으면, 함수 아규먼트에서 타입을 또 선언하지 않아도 된다는 특징이 있다.</p>
<p><em>아규먼트(argument) = 함수를 호출할 때 전달하는 값</em>
<br /></p>
<p>ex)</p>
<pre><code>// 변수에 미리 함수 타입 지정
let myFunc4: (arg1: number, arg2: number) =&gt; number;

myFunc4 = function (x, y) {
   return x + y;
}; // 미리 변수에 함수 타입을 지정함 -&gt; 대입하는 함수의 식에 타입을 쓰지 않아도 됨

// 위의 과정을 한줄로 표현
let myFunc5: (arg1: number, arg2: number) =&gt; number = (x, y) =&gt; {
   return x + y;
};</code></pre><p>함수 타입 부분을 화살표 함수와 헷갈리지 않도록 주의하자.
<br /></p>
<p>type 별칭 및 인터페이스 역시 개별적으로 함수타입을 선언하여 사용될 수 있다.
<br /></p>
<p>ex)</p>
<pre><code>// type 리터럴로 함수 타입 지정
type Add1 = (x: number, y: number) =&gt; number;
let myFunc6: Add1 = (x, y) =&gt; {
   return x + y;
};</code></pre><pre><code>// 인터페이스로 함수 타입을 지정
interface Add2 {
   (x: number, y: number): number;
}
let myFunc7: Add2 = (x, y) =&gt; {
   return x + y;
};</code></pre><br />

<h2 id="타입스크립트의-매개변수-표현">타입스크립트의 매개변수 표현</h2>
<p>타입스크립트에서는 함수의 인자를 모두 필수 값으로 간주한다.</p>
<p>함수의 매개변수를 설정하면 <strong>undefined</strong>나 <strong>null</strong>이라도 인자로 넘겨주어야 하며, 컴파일러에서는 정의된 매개변수 값이 넘어왔는지 확인한다.</p>
<p>즉 정의된 매개변수 값만 받을 수 있고, 추가로 인자를 받을 수는 없다는 의미가 된다.
<br /></p>
<p>ex)</p>
<pre><code>function sum(a: number, b: number): number {
  return a + b;
}
sum(10, 20); // 30
sum(10, 20, 30); // Error, Expected 2 arguments, but got 3. (인자 개수 초과)
sum(10); // Error, Expected 2 arguments, but got 1. (인자 개수 부족)</code></pre><br />

<h3 id="선택적-매개변수---사용">선택적 매개변수 : (?) 사용</h3>
<p>만약 자바스크립트처럼 좀 더 유연하게 표현하고 싶다면, <strong>(?) 키워드</strong>를 사용하여 정의하면 된다.</p>
<p>인자에 <strong>옵션 속성</strong>을 부여하여 넣어도 되고, 안넣어도 되도록 선택 사항으로 만드는 것이다.
<br /></p>
<p>아래 예제 코드는 인자인 &quot;b&quot;에 <strong>(?) 키워드</strong>를 사용하여 선택적 매개변수로 지정한 모습이다.</p>
<p>그래서 b가 받을 인수가 없어도 에러가 발생하지 않는다.
<br /></p>
<p>ex)</p>
<pre><code>function sum(a: number, b?: number): number {
  return a + b;
}
sum(10, 20); // 30
sum(10, 20, 30); // Error, Expected 2 arguments, but got 3. (인자 개수 초과)
sum(10);</code></pre><br />

<p>위 예제는 유니온 타입 <strong>&quot;| undefined&quot;</strong>를 사용한 것과 같은 뜻이다.</p>
<p>(둘 중 하나 선택)
<br /></p>
<p>ex)</p>
<pre><code>function sum(a: number, b: number | undefined): number {
  return a + b;
}
sum(10, 20); // 30
sum(10);</code></pre><br />

<p><strong>Null 병합 연산자( ?? )</strong>와 함께 응용하여 사용해보자.</p>
<p>선택적 매개변수인 b와 c에 값이 있다면 그대로 사용하여 리턴하고, 없다면 0을 각각의 인자에 부여하여 계산한다.
<br /></p>
<p>ex)</p>
<pre><code>function add(a: number, b?: number, c?: number): number {
   return a + (b ?? 0) + (c ?? 0);
}

add(1, 2, 3); // 6
add(1, 2); // 3
add(1); // 1</code></pre><br />

<p>이러한 선택적 매개변수를 사용할 때도 주의할 점이 있다.
<br /></p>
<p>선택적 매개변수가 이외의 함수 인자 앞으로 위치하면 안된다.</p>
<p>(= 선택적 매개변수는 무조건 뒤에 위치)
<br /></p>
<p>ex)</p>
<pre><code>function sum(b?: number, a: number): number {
   return a + (b ?? 0);
}</code></pre><img src="https://velog.velcdn.com/images/choco_dev/post/d7b89a6f-fe91-43cc-af57-6716bdad02d7/image.png" width="80%" />

<br />

<p>만약 해당 선택적 매개변수를 앞에 작성해야 한다면, 같은 기능으로 작동하는 <strong>유니온(Union) 타입</strong>으로 대신 작성하면 된다.
<br /></p>
<p>ex)</p>
<pre><code>function sum(b: number | undefined, a: number): number {
   return a + (b ?? 0);
}

sum(20, 11); // 31
sum(undefined, 11); // 11</code></pre><br />

<h3 id="매개변수-초기화">매개변수 초기화</h3>
<p>매개변수의 초기화는 ES6+ 문법과 동일하다.</p>
<p>기본값을 할당한 매개변수의 함수 타입을 보면 선택적 매개변수가 적용된 걸 확인할 수 있다.</p>
<p>(매개변수에 기본값 존재 =&gt; 값을 할당하지 않아도 됨)
<br /></p>
<p>그리고 매개변수에 기본값이 있다면 인자의 타입을 선언하지 않아도 된다는 특징이 있다. (= <strong>타입 추론</strong>)
<br /></p>
<p>ex)</p>
<pre><code>// 매개변수에 기본값이 존재 -&gt; 인자의 타입을 선언하지 않아도 됨 (= 타입 추론)
// b 인자의 기본값은 100
function sum(a: number, b = 100): number {
   return a + b;
 }
 sum(10, undefined); // 110
 sum(10); // 110
 sum(10, 10) // 20</code></pre><p>위 코드의 b 인자에는 기본값이 있는데, 이는 <strong>b?: number</strong> 라고 선언한 것과 같은 의미가 된다.</p>
<br />

<h3 id="나머지rest-매개변수">나머지(rest) 매개변수</h3>
<p>ES6에서 사용되는 문법 중 하나인 <strong>스프레드 매개변수</strong>도 타입을 잘 지정해준다면, 타입스크립트에서 사용 가능하다.</p>
<span style="font-size: 16px;">
REST 문법이란?
매개변수 이름 앞에 점 3개(...)를 붙여서 정의한 매개변수,<br />
이렇게 전달된 인수들은 배열로 전달됨
</span>

<p>ex)</p>
<pre><code>myArray(1, 2, 3, 4, 5);

function myArray(...rest) {
    console.log(rest) // 1, 2, 3, 4, 5
}</code></pre><br />

<p>이 REST 문법을 적용해보면 다음과 같다.</p>
<pre><code>function sum(a:number, ...nums: number[]):number {

    const totalOfNums = 0;

    for(let key in nums) {
        totalOfNums += nums[key];
    }

    return a + totalOfNums;
}</code></pre><p>만약 sum(10, 1, 2, 3);로 호출했다고 가정하면, <strong>a</strong>에는 가장 첫 번째 값인 10이 들어간다.</p>
<p>그리고 나머지 값들은 숫자 배열 타입을 가진 인자인 <strong>...nums</strong> 안에 하나의 배열로 묶여서 저장된다.</p>
<p>즉 <strong>nums = [1, 2, 3]</strong> 의 형태가 되는 것이다.
<br /></p>
<p>그 아래 for문에서는 nums의 내부 요소들이 하나씩 더해지니 1 + 2 + 3 = 6 이고,</p>
<p>마지막에 a + totalOfNums이니 10 + 6 = 16 이 된다.
<br /></p>
<h4 id="나머지-매개변수-사용-시-주의할-점">나머지 매개변수 사용 시 주의할 점</h4>
<p>타입스크립트에서는 strict 모드를 true로 설정하여 사용한다.</p>
<p>즉 자바스크립트의 arguments 예약어 기능을 사용하지 못하니 이를 주의하여 나머지 매개변수를 사용하자.</p>
<span style="font-size: 16px;">
arguments 예약어란?<br />
자바스크립트에서 매개변수를 따로 선언을 하지 않아도,<br /> 함수에 넘긴 값들을 자동으로 담아주는 특별한 객체
</span>

<br />
<br />

<p>ex)</p>
<pre><code>function aa() {
    console.log([...arguments]); // 전달된 인수들을 배열로 출력
}

aa(1, 2, 3, 4, 5); // Error</code></pre><br />
위 오류를 수정하면 아래와 같다.
<br />
<br />

<pre><code>// 매개변수를 명시적으로 선언 (arguments 예약어 사용 불가)
function aa2(...args: number[]): number[] {
    return args;
}

aa2(1, 2, 3, 4, 5); // [1, 2, 3, 4, 5]</code></pre><br />
<br />