<h2 id="union-타입">Union 타입</h2>
<h3 id="union-타입-시작">Union 타입 시작</h3>
<blockquote>
<p><strong>유니온(Union) 타입</strong>이란?
 : 자바스크립트의 OR 연산자(||)와 같이 <strong>&quot;A이거나 B이다&quot;</strong>라는 의미의 타입</p>
</blockquote>
<pre><code>function logText(text: string | number) {
  // ...
}</code></pre><p>위 함수의 파라미터인 text에는 문자열 타입(string)이나 숫자 타입(number) 둘 다 올 수 있다.</p>
<p>이렇게 파이프 기호 (|) 연산자를 사용하여 타입을 여러 개 연결하는 방식을 <strong>유니온 타입</strong> 정의라고 한다.
<br /></p>
<p>ex)</p>
<pre><code>let union: string | number;

union = 'Hello World!';
union = 12345;
union = false; // Error</code></pre><p>위 예제 코드에서 마지막 union 변수는 선언되지 않은 boolean 타입으로 초기화하려고 했기 때문에 에러가 발생한다.</p>
<br />

<p>파이프 기호인 &quot;|&quot;를 통해 타입을 구분하고, 단일 타입인 경우엔 괄호를 사용하지 않아도 된다.</p>
<p>하지만 배열인 경우엔 괄호로 씌워주어야 한다.
<br /></p>
<p>여기서 단일 타입이랑 배열이 각각 무슨 뜻인지 헷갈릴 수 있다.</p>
<p>아래 예제 코드를 통해 직접 눈으로 확인하여 보자.
<br /></p>
<p>_&quot;문자열이나 숫자가 섞여 들어올 수 있는 배열&quot;_을 유니온 타입을 사용하여 정의하려고 한다.</p>
<p>어떻게 해야 할까?
<br /></p>
<p>ex)</p>
<pre><code>// 틀린 예시 : 아래는 단일 문자열 or 숫자 배열 중 택 1
let arr: string | number[];

arr = &quot;Hello&quot;; // 단일 문자열
arr = [1, 2, 3]; // 숫자 배열

arr = [1, &quot;Hello&quot;, 2]; // Error</code></pre><br />

<pre><code>// 옳은 예시 : 아래는 문자열과 숫자가 섞여 들어갈 수 있는 배열
let arr: (string | number)[];

arr = [1, &quot;Hello&quot;, 2, &quot;World&quot;];</code></pre><br />
또는 제네릭 방식으로도 표현 가능하다.


<pre><code>let arr: Array&lt;string | number&gt; = [1, &quot;Hello&quot;, 2, &quot;World&quot;];</code></pre><br />

<p>ex)</p>
<pre><code>function padLeft(value: string, padding: boolean | number) {
  // ...
}

let indentedString = padLeft(&quot;Hello world&quot;, true);</code></pre><p>두 번째 인자는 boolean 또는 number가 들어올 수 있는데, 이 중 boolean을 선택하여 true라는 값을 넣었다.</p>
<br />

<h3 id="union-타입의-장점">Union 타입의 장점</h3>
<p>아래 두 개의 코드를 비교하여 유니온 타입이 어떤 장점을 갖고 있는지 확인해보자.</p>
<pre><code>// 1) any를 사용하는 경우
function getAge(age: any) {
  // toFixed를 toFixe로 오타냄
  age.toFixed(); // Error, age의 타입이 any로 추론... -&gt; 숫자 관련된 API를 작성할 때 코드 자동 완성 X
  // 컴퓨터는 age가 숫자인지, 문자열인지, 배열인지 구분 불가능
  return age;
}</code></pre><br />

<pre><code>// 2) Union Type을 사용하는 경우
function getAge(age: number | string) {
  if (typeof age === 'number') {
    age.toFixed(); // 정상 동작, age의 타입이 `number`로 추론... -&gt; 숫자 관련된 API를 쉽게 자동완성 O
    return age;
  }
  if (typeof age === 'string') {
    return age;
  }
  return new TypeError('age must be number or string');
}</code></pre><p>any를 사용한다면 어떤 타입인지 제대로 알 수 없다.</p>
<p>그러나 Union Type을 사용한다면 특정 타입(age: number | string) 중 하나라는 것을 알 수 있다.
<br /></p>
<p>즉 타입을 제한하여 추론하기 좋고, 자동 완성도 훨씬 쉽게 가능하다는 장점이 있다.</p>
<br />

<h3 id="union-타입의-주의할-점">Union 타입의 주의할 점</h3>
<p>아래 코드를 먼저 확인해보자.</p>
<p>introduce() 함수의 파라미터 타입을 Person, Developer 타입으로 각각 선언하였는데, 이 둘을 유니온 타입으로 합친 모습이다.
<br /></p>
<p>ex)</p>
<pre><code>type Person = {
  name: string;
  age: number;
}

type Developer = {
  name: string;
  skill: string;
}

function introduce(someone: Person | Developer) {
  someone.name; // 정상 동작
  someone.age; // Error, 타입 에러
  someone.skill; // Error, 타입 에러
}</code></pre><br />
두 Person이랑 Developer 타입이 각각 가진 name, age, skill 속성들도 바로 사용할 수 있을 것이라고 착각하기 쉽다.

<p>그러나 타입스크립트 관점에서는 introduce() 함수를 호출하는 시점에 Person타입이 올지 Developer타입이 올지 알 수가 없기 때문에 에러를 발생시킨다.
<br /></p>
<p>어떤 타입이 들어와도 오류가 발생하지 않을 최선의 방향으로 타입을 추론한다.</p>
<p>그러니 Person과 Developer 두 타입에 공통적으로 들어있는 속성인 name만 접근할 수 있게 되는 것이다.</p>
<br />

<p>더 나아가면, 함수에서도 리턴값을 유니온으로 사용하게 되면 에러를 발생시킨다.</p>
<p>모든 경우의 수를 고려하여 x와 y 매개변수에 number와 string 둘 중 무엇이 들어오느냐에 따라 리턴값이 달라지니 유니온을 사용했지만, 컴파일러 입장에서는 이러한 방식이 틀린 것이다.
<br /></p>
<p>ex)</p>
<pre><code>function add(x: string | number, y: string | number): string | number {
   return x + y;
}

add(1, 2);
add('1', '2');
add(1, '2');</code></pre><img src="https://velog.velcdn.com/images/choco_dev/post/2396d897-4473-4fd3-b32d-609648c61ffe/image.png" width="80%" />

<br />
아래 코드처럼 result라는 변수를 만들고 거기에 함수의 결과값을 넣는 방법도 유니온 입장에선 옳은 방법 같지만, 이것도 에러가 발생한다.

<p>ex)</p>
<pre><code>function add(x: string | number, y: string | number): string | number {
   return x + y;
}

const result: string | number = add(1, 2);
result.charAt(1);</code></pre><img src="https://velog.velcdn.com/images/choco_dev/post/17817eda-9da0-483c-bee2-21ac38391a9b/image.png" width="80%" />

<br />
왜 에러가 발생할까?

<p>왜냐하면 컴파일러 입장에서는 result 변수가 string인지 number인지 확신이 안된다.</p>
<p>그래서 문자열 메소드인 charAt() 실행에 대해서 에러를 발생시키는 것이다.</p>
<br />
<br />