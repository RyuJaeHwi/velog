<h2 id="인터페이스-호환">인터페이스 호환</h2>
<p>같은 이름을 가진 인터페이스를 여러 개 선언할 수도 있다.</p>
<p>인터페이스는 서로 중복이 된 상태라면, 그 안에 선언된 속성(프로퍼티)들이 하나로 합쳐진다.</p>
<p>즉 <strong>기존에 만들어진 인터페이스에 내용을 추가</strong>하는 것이라고 이해하면 된다.
<br /></p>
<p>ex)</p>
<pre><code>interface FullName {
  firstName: string,
  lastName: string
}

interface FullName {
  middleName: string
}

const myfullName: FullName = {
  firstName: 'Alice',
  middleName: 'May',
  lastName: 'Diana'
};


function printFullName(a: FullName): void {
  const result = `${a.firstName} ${a.middleName} ${a.lastName}`;
  console.log(result);
}

printFullName(myfullName); // &quot;Alice May Diana&quot;</code></pre><br />

<h2 id="인터페이스-확장-extends">인터페이스 확장 (extends)</h2>
<p>클래스와 동일하게 인터페이스도 인터페이스끼리 확장하는 것이 가능하다.</p>
<p>자바스크립트의 클래스에서 상속을 할 때 <strong>extends</strong> 키워드를 사용하는데, 타입스크립트에서도 해당 키워드를 인터페이스에서 사용하면 확장이 된다.
<br /></p>
<p>ex)</p>
<pre><code>interface Person {
   name: string;
}

// 인터페이스 확장
interface Developer extends Person {
   skill: string;
}

let mygirl: Developer = { name: 'Lina', skill: 'TypeScript' };</code></pre><br />

<p>이러한 인터페이스 확장 기능을 타입 별칭을 사용하여 구현하려고 할 땐, <strong>인터렉션 타입(&amp;)</strong>을 이용하자.
<br /></p>
<p>ex)</p>
<pre><code>type Person = { name: string };

type Developer = Person &amp; { skill: string };

let mygirl: Developer = { name: 'Lina', skill: 'TypeScript' };</code></pre><br />

<p>또한 인터페이스는 한 번에 여러 개의 인터페이스를 받아서 확장할 수 있다는 특징을 갖고 있다.</p>
<p>(클래스는 한번에 하나만 extends 가능)
<br /></p>
<p>ex)</p>
<pre><code>interface Person {
   name: string;
   age: number;
}

interface Programmer {
   favoriteProgrammingLanguage: string;
}

interface Korean extends Person, Programmer { // 두개의 인터페이스를 받아 확장
   isLiveInSeoul: boolean;
}

const mygirl: Korean = {
   name: 'Merry',
   age: 25,
   favoriteProgrammingLanguage: 'eng',
   isLiveInSeoul: true,
};</code></pre><br />

<h2 id="인터페이스의-함수-타입">인터페이스의 함수 타입</h2>
<h3 id="호출-시그니처-call-signature">호출 시그니처 (Call Signature)</h3>
<p>인터페이스는 함수의 타입을 정의할 때도 사용 가능하다.</p>
<p>함수의 인자의 타입과 반환 값의 타입을 정의하는 역할을 수행한다.
<br /></p>
<p>ex)</p>
<pre><code>interface login {
  (username: string, password: string): boolean;
}

let loginUser: login;
loginUser = function(id: string, pw: string) {
  console.log('로그인 완료');
  return true;
}</code></pre><br />

<h2 id="인터페이스의-클래스-타입">인터페이스의 클래스 타입</h2>
<p>C#이나 자바처럼 타입스크립트에서도 클래스가 일정 조건을 만족하도록 타입 규칙을 정할 수 있다.</p>
<p>인터페이스로 클래스를 정의하는 경우, <strong>implements</strong> 키워드를 사용해 클래스 정의 옆에다 붙이면 된다.</p>
<br />

<p>ex)</p>
<pre><code>interface Friend {
  name: string;
  loveName(love: string): void; // 문자열을 받고 리턴하지 않는(void) 함수
}

// Friend 인터페이스 규칙을 토대로 클래스인 myGirls 구현 (= implements 사용)
// Friend 인터페이스를 implements -&gt; myGirls 클래스 구조는 반드시 Friend에 정의된 대로 따르기
class myGirls implements Friend {

  name: string = 'Alice';

  // loveName이라는 이름을 가진 함수(메서드)를 정의
  loveName(b: string) {
    // 실행할 때 괄호 안에 글자(문자열) 하나를 받아옴
    // 함수 내부에서는 그 받아온 글자를 b라는 임시 이름(매개변수)으로 부름
    this.name = b;
  }

  // 생성자 함수
  constructor() {}
}</code></pre><br />
만약 처음에 name이 'Alice'였는데, 누군가 loveName('Lina')이라고 함수를 실행하면, b 자리에 'Lina'가 들어간다.

<p>그러면 this.name = 'Lina'가 실행되면서 이 주인공의 이름이 'Lina'로 바뀌게 된다.</p>
<br />

<h2 id="하이브리드-타입">하이브리드 타입</h2>
<p>인터페이스도 여러 가지 타입을 조합하여 사용 가능하다.
<br /></p>
<p>예를 들어, 함수 타입이면서 객체 타입을 정의할 수 있는 인터페이스가 있다.</p>
<pre><code>interface Friend {
    // 함수처럼 실행할 때(dearPretty(...)), 괄호 안에 무조건 문자열 하나(dear)를 집어넣어서 호출
    // 함수를 실행하고 나면, 최종 결과물로 문자열(string) 하나를 리턴
    (dear: string): string; // 함수로 쓸 때의 규칙 (호출 시그니처)
    name: string; // 객체로 쓸 때의 변수 규칙
    love(): void; // 객체로 쓸 때의 메서드 규칙
}

function myGirl(): Friend {
    // dear라는 글자를 받는 평범한 함수를 하나 만든 후, my라는 이름의 상자에 보관
    let my = (function(dear: string) {}) as Friend;
    my.name = 'Alice';
    my.love = function() {}; // 또 다른 빈 함수를 채워 넣음
    return my;
}

let dearPretty = myGirl();
dearPretty('My Pretty dear'); // (dear: string): string 규칙인 부분을 출력
dearPretty.name = 'Luna';
dearPretty.love(); // love(): void 메서드를 찾아서 안에 저장되어 있던 함수를 실행</code></pre><br />
<br />