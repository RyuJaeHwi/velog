<h2 id="인터페이스란">인터페이스란?</h2>
<blockquote>
<p>인터페이스란?
   컴퓨터 과학 = 상호 간에 정의한 약속 혹은 규칙
   타입스크립트 = 객체 타입을 정의할 때 사용하는 요소</p>
</blockquote>
<p>타입스크립트 내에서의 약속은 다음과 같은 범주가 있다.</p>
<ul>
<li>객체의 스펙 (속성과 속성의 타입)</li>
<li>함수의 파라미터</li>
<li>함수의 스펙 (파라미터, 반환 타입 등)</li>
<li>배열과 객체를 접근하는 방식</li>
<li>클래스</li>
</ul>
<br />
인터페이스는 "객체의 껍데기 또는 설계도"라고 생각하면 된다.

<p>즉, 프로그래밍에서 클래스 또는 함수의 '틀'을 정의하는 것처럼, <strong>타입의 '틀'</strong>로서 사용할 수 있는 것이 인터페이스인 것이다.</p>
<p>(인터페이스 = 타입의 &quot;틀&quot;)
<br /></p>
<p>인터페이스의 기본 구조는 다음과 같다.</p>
<pre><code>interface 인터페이스_이름 {
  속성: 타입;
}</code></pre><br />
인터페이스 내에서 필요한 속성만큼 더 추가해주는 식으로 사용하면 된다.
<br />
<br />

<p>기본 구조를 배웠으니, 실제 예제 코드를 통해 어떤 식으로 사용하는지 확인해보자.
<br /></p>
<p>ex)</p>
<pre><code>// 인터페이스명의 첫글자는 대문자!
interface Human {
  name: string; // name 키는 문자열
  age: number; // age 키는 숫자
  dear(): void; // dear() 함수(매서드) 키는 void, 반환값(return) X
}

// 인터페이스인 &quot;Human&quot; 자체를 타입으로 주며 객체 생성
const friend: Human = {
  name: &quot;Alice&quot;,
  age: 25,
  dear: () =&gt; console.log(&quot;she is my dear&quot;),
};

// 함수 mygirl의 매개변수에서 인터페이스를 타입으로 받아 작동
function mygirl(a: Human): void {
  console.log(`${a.name} is ${a.age} years old`);
};

// 아래 함수 mygirl()을 호출하는 순간, friend 객체 전체를 a에 넘김
// a = { name: &quot;Alice&quot;, age: 25, dear: ... }
// 즉 위 배열을 풀어 쓰면 a.name = &quot;Alice&quot;  a.age = 25
mygirl(friend); // &quot;Alice is 25 years old&quot;
friend.dear(); // &quot;she is my dear&quot;</code></pre><br />

<p>Human 이라는 이름의 인터페이스 안에 name, age, dear() 이라는 이름의 속성들을 추가하여 생성하였다.</p>
<p>그리고 friend 라는 객체를 Human 인터페이스를 타입으로 주어 생성하고, 각 속성 내용도 정의했다.</p>
<p>마지막으로 mygirl라는 함수를 만드는데, 여기서 매개변수(입력값)인 a는 Human 인터페이스에 정의된 속성들을 최소한 모두 포함하는 객체여야 한다.</p>
<br />

<h3 id="선택적-프로퍼티-">선택적 프로퍼티 (?:)</h3>
<p>인터페이스를 사용할 때 인터페이스에 정의되어 있는 속성을 반드시 모두 다 꼭 사용해야 한다면 코드의 유연성이 사라진다.
<br /></p>
<p>선택적 프로퍼티, 즉 옵션 속성의 기본 구조는 다음과 같다.</p>
<p>콜론(:) 앞에 물음표(?) 를 붙이면 된다.</p>
<pre><code>interface 인터페이스_이름 {
  속성?: 타입;
}</code></pre><br />
실제 예제 코드를 통해 알아보자.
<br />
<br />

<p>ex1)</p>
<pre><code>interface Friend {
  name: string;
  age?: number; // age 속성은 명시 자유 (옵션)
}

function mygirl(beer: Friend) {
  console.log(beer.name);
}

let dear = { name: 'Merry' }; // age 속성은 명시 X
mygirl(dear); // &quot;Merry&quot;</code></pre><br />

<p>ex2)</p>
<pre><code>interface Student {
   name: string;
   age: number;
   gender?: string;
}

let girl: Student = {
   name: 'Lina',
   age: 17,
};

girl.age = 18;
girl.gender = &quot;female&quot;; // 옵션 속성에 의해 나중에 속성값 추가하는 것도 가능

girl.hobby = ''; // 아예 정의되지 않은 속성 추가는 불가능</code></pre><br />
선택적 프로퍼티의 원리를 정확히 알아보자.
<br /><br />

<p>아래 예제 코드에서 IPlayer, TPlayer 객체 둘 다 name 속성은 무조건 갖고 있다.</p>
<p>그러나 age는 옵션으로 두었는데, 이는 인터페이스에서 (?:)를 사용한 것과 Union 타입으로 number | undefiened; 로 선언한 것과 같은 뜻임을 알 수 있다.
<br /></p>
<p>ex)</p>
<pre><code>// 둘이 표현하고자 하는 타입 구조는 같음
interface IPlayer {
   name: string;
   age?: number; // 옵션 속성 사용
}

type TPlayer = {
   name: string;
   age: number | undefiened; // Union 타입 사용
}</code></pre><br />

<h3 id="읽기-전용-프로퍼티-readonly">읽기 전용 프로퍼티 (readonly)</h3>
<p><strong>읽기 전용 속성(readonly property)</strong>은 단어 그대로 인터페이스로 객체를 처음 생성할 때만 값을 할당하며 그 이후에는 해당 값을 변경할 수 없게 만드는 속성을 뜻한다.
<br /></p>
<p>readonly를 속성 이름 앞에 붙이면 적용된다.</p>
<pre><code>interface 인터페이스_이름 {
  readonly 속성: 타입;
}</code></pre><br />
읽기 전용 프로퍼티는 인터페이스를 통해 객체를 처음 선언하여 값을 대입할 땐 문제가 없다.

<p>그러나 그 후에 따로 접근하여 값을 수정하려고 하면 에러가 발생한다.
<br /></p>
<p>ex)</p>
<pre><code>interface Friend {
   name: string;
   age: number;
   gender?: string;
   readonly birthYear: number; // 읽기 전용 속성
}

let mygirl: Friend = {
   name: 'jeff',
   age: 30,
   birthYear: 2002, // 최초로 값을 초기화할 때만 할당 가능
};

mygirl.birthYear = 2010; // Error, 이후에는 수정 불가능</code></pre><br />
readonly로 설정된 속성 mygirl.birthYear 값을 처음에 2002 숫자로 선언했지만, 추후에 다시 접근하여 수정하려고 했기 때문에 에러가 발생하는 것을 알 수 있다.
<br />
<br />

<h4 id="readonly-키워드-vs-const-키워드">readonly 키워드 vs const 키워드</h4>
<p>readonly와 const는 둘 다 처음 초기화할 때만 값을 선언하고, 그후에는 해당 속성의 값을 수정하지 못한다는 점에서 유사하게 보인다.</p>
<p>그러나 이 두 키워드는 각각 사용하는 곳이 다르다.
<br /></p>
<ul>
<li>readonly 키워드 : 프로퍼티에서 사용</li>
<li>const 키워드 : 변수를 정의할 때 사용</li>
</ul>
<br />

<h4 id="readonly-활용">readonly 활용</h4>
<p>만약 모든 속성이 readonly일 경우, 일일히 프로퍼티마다 readonly를 써주는 것보다 더 간단한 방법이 있다.</p>
<p>바로 <strong>유틸리티(Utility)</strong>나 <strong>단언(Assertion)</strong> 타입을 활용하여 구현하는 것이다.
<br /></p>
<p>ex)</p>
<pre><code>// readonly 전부 사용 -&gt; 매우 귀찮은 방법
interface Player {
  readonly name: string,
  readonly age: number
}

let user: Player = {
  name: 'Alice',
  age: 25
};

user.age = 18; // Error
user.name = 'Merry'; // Error</code></pre><p>위와 같은 코드를 Readonly 유틸리티(Utility)를 활용하면 다음과 같이 더 간단하게 작성할 수 있다.
<br /></p>
<p>ex)</p>
<pre><code>// Readonly 유틸리티(Utility) 활용
interface Player {
  name: string,
  age: number
}

// Array와 비슷하게 Readonly 라는 자료형이 있다고 생각하기
let user: Readonly&lt;Player&gt; = {
  name: 'Alice',
  age: 25
};

user.age = 18; // Error
user.name = 'Merry'; // Error</code></pre><br />
또는 따로 인터페이스를 이용하지 않을 땐, 객체 데이터 자체에 **"as const"**를 붙이면 된다.

<p>해당 데이터 자체가 리터럴 타입이 된다.
<br /></p>
<p>ex)</p>
<pre><code>// Type assertion 사용
let user = {
  name: 'Alice',
  age: 25
} as const;

user.age = 18; // Error
user.name = 'Merry'; // Error</code></pre><br />

<h4 id="읽기-전용-배열">읽기 전용 배열</h4>
<p>배열을 선언할 때에도 바로 위에서 설명한 ReadonlyArray 유틸리티 타입을 사용하자. 그러면 읽기 전용 배열을 생성할 수 있다.</p>
<p>선언하는 시점에만 값을 정의할 수 있고, 후에 배열의 내용을 변경할 수 없다.
<br /></p>
<p>ex)</p>
<pre><code>let arr: ReadonlyArray&lt;number&gt; = [1,2,3]; // 읽기 전용 배열

arr.splice(0,1); // Error
arr.push(4); // Error
arr[0] = 100; // Error</code></pre><br />

<h3 id="인터페이스-vs-type-alias타입-별칭">인터페이스 vs type alias(타입 별칭)</h3>
<p>객체의 구조 타입을 선언해서 사용한다고 가정할때, 이는 인터페이스와 타입 별칭 둘 다 구현이 가능하다.
<br /></p>
<p>다음은 똑같은 객체 구조 타입을 각각 순서대로 리터럴, 타입 별칭, 인터페이스를 사용하여 구현한 예제 코드이다.
<br /></p>
<p>ex)</p>
<pre><code>// 리터럴 사용 객체 타입
const a1: {
   name: string;
   age: number;
   talk: () =&gt; void;
} = {
   name: 'Alice',
   age: 25,
   talk() {},
};


// type alias 사용 객체 타입
type Ty = {
   name: string;
   age: number;
   talk: () =&gt; void;
};
const a2: Ty = {
   name: 'Alice',
   age: 25,
   talk() {},
};


// 인터페이스 사용 객체 타입
interface In {
   name: string;
   age: number;
   talk: () =&gt; void;
}
const a3: In = {
   name: 'Alice',
   age: 25,
   talk() {},
};</code></pre><br />
셋 중 어떤 것을 사용하는 것이 좋을지 헷갈릴 수 있다고 생각한다.
<br />

<p>겉보기엔 딱히 차이점이 없어 보이지만, 그래도 현시점 가장 추천되는 것은 <strong>&quot;인터페이스&quot;</strong>를 사용하는 것이다.
<br /></p>
<p>타입 별칭은 불가능한 확장을, 인터페이스에서는 사용이 가능하다.</p>
<p>인터페이스는 <strong>extends</strong>나 <strong>implement</strong> 키워드 등을 사용하여 단순 객체 타입 표현을 넘어 다양하게 활용이 가능하다.</p>
<p>여러 라이브러리도 인터페이스로 타입을 선언하니, 가능하면 인터페이스를 사용하는 것이 더 좋다고 볼 수 있다.</p>
<br />
<br />