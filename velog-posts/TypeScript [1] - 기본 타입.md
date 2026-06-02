<h2 id="기본-타입이란">기본 타입이란?</h2>
<blockquote>
<p>변수나 함수를 정의할 때 사용하는 기본 타입들을 의미</p>
</blockquote>
<img src="https://velog.velcdn.com/images/choco_dev/post/a803f550-0575-4ebd-9e5d-db8bf19e0b54/image.png" width="90%" />

<br />

<h3 id="타입스크립트의-기본-코드-구조">타입스크립트의 기본 코드 구조</h3>
<p>개별 타입을 알아보기 전에, 타입스크립트에서 변수를 선언할 때 사용하는 기본적인 코드 구조를 알아보자.</p>
<pre><code>let [변수이름]: 타입 = 값;</code></pre><br />

<h3 id="타입---문자열string">타입 - 문자열(string)</h3>
<p>자바스크립트 변수의 타입이 문자열인 경우에 아래와 같이 <strong>string</strong>을 사용
<br /></p>
<pre><code>let str: string = 'hello';</code></pre><span style="font-size: 16px; color: gray;">
  <i>
    타입 표기(Type Annotation)이란?<br />
    &nbsp; : 콜론(':')을 사용하여 자바스크립트 코드에 타입을 정의하는 방식
  </i>
</span>


<br />
<br />


<p>ex)</p>
<pre><code>let mygirl1: string = 'Alice';

let mygirl2: string = &quot;Lina&quot;;
let myfriendAlice: string = 'My first friend is ' + mygirl1;

let myfriendLina: string = `My second friend is ${mygirl2}.`;

function strings(str1: string, str2: string): string {
    return str1 + str2;
}


console.log(mygirl1); // &quot;Alice&quot;
console.log(mygirl2); // &quot;Lina&quot;
console.log(myfriendAlice); // &quot;My second friend is Alice&quot;
console.log(myfriendLina); // &quot;My second friend is Lina.&quot;

let result = strings(&quot;Hello &quot;, &quot;World!&quot;);
console.log(result); // &quot;Hello World!&quot;</code></pre><br />

<h3 id="타입---number">타입 - number</h3>
<p>타입스크립트는 C언어나 JAVA가 갖고 있는 int, float, double 타입이 존재하지 않는다.</p>
<p>대신 자바스크립트의 number 자료형을 그대로 사용한다.
<br /></p>
<p>타입이 숫자이면 아래와 같이 <strong>number</strong> 사용
<br /></p>
<pre><code>let num: number = 10;</code></pre><br />

<p>ex)</p>
<pre><code>let num: number;
let integer: number = 6;
let float: number = 3.14;

function plus(num1: number, num2: number): number {
    return num1 + num2;
}

num = 10;

console.log(num); // 10
console.log(integer); // 6
console.log(float); // 3.14

let result = plus(integer, float);
console.log(result); // 9.14</code></pre><br />

<h3 id="타입---boolean">타입 - boolean</h3>
<p>타입이 진위 값(true/false)인 경우에는 아래와 같이 <strong>boolean</strong> 사용
<br /></p>
<pre><code>let isLoggedIn: boolean = false;</code></pre><br />

<p>ex)</p>
<pre><code>let isBoolean: boolean;
isBoolean = true;

let isDone: boolean = false;

console.log(isBoolean); // true
console.log(isDone); // false</code></pre><br />

<h3 id="타입---object">타입 - object</h3>
<p>자바스크립트에서 object는 객체뿐만 아니라 배열, 함수까지 포함한다.
<br /></p>
<p>타입스크립트에서의 object 타입은 typeof 연산자가 &quot;object&quot;를 반환하는 모든 타입을 의미한다.</p>
<p>여기서 말하는 object 타입이란, number, string, boolean, bigint, symbol, null, 또는 undefined가 아닌 나머지 비원시 타입(Non-primitive data type) 전체를 의미한다.</p>
<br />

<p>객체 타입인 경우에는 아래와 같이 <strong>object</strong> 사용
<br /></p>
<pre><code>let student: object = { name: &quot;Alice&quot;, age: 25 };</code></pre><span style="font-size: 16px; color: gray;">
  + 객체 타입은 위처럼 한 번에 정의하는 것보다, <br />
  &nbsp;&nbsp;&nbsp;인터페이스나 타입 별칭을 통해 정의하는 것이 더 좋은 방법
</span>

<br />
<br />

<p>ex)</p>
<pre><code>let obj: object = {};
let arr: object = [];
let func: object = function () {};
let nullValue: object = null;
let date: object = new Date();</code></pre><br />
object 타입은 타입스크립트에서 여러 타입의 상위 타입으로 인식된다.

<p>그래서 object 자체를 타입으로 쓰기엔 좋지 않다.
<br /></p>
<p>심지어  다음과 같이 object 타입에 객체값을 주고 실제로 조회해 보면 에러가 발생하는 것을 확인할 수 있다.
<br /></p>
<p>ex)</p>
<pre><code>const player: object = { name: 'merry' };
player.name; // Error, Property 'name' does not exist on type 'object'.</code></pre><br />

<p>정말 객체에 타입을 지정해주고 싶다면, 다음과 같이 객체 속성(Properties)들에 대한 타입을 개별적으로 지정하자.
<br /></p>
<p>ex)</p>
<pre><code>let myGirl1: { name: string, age: number };
myGirl1 = {
  name: 'Alice',
  age: 25
};

let myGirl2: { name: string, age: number };
myGirl2 = {
  name: 'Lina',
  age: false, // Error
  email: 'lina@naver.com' // Error
};</code></pre><br />

<p>그런데 이 코드도 가독성이 좋지 않다.</p>
<p>이러한 가독성 문제를 해결하기 위해 타입스크립트는 <strong>alias</strong> 기능과 <strong>interface</strong> 라는 문법을 사용한다.
<br /></p>
<p>지금은 어떤 식으로 코드를 간결히 작성할 수 있는지 확인만 해보자.
<br /></p>
<p>ex1)</p>
<pre><code>// type alias
type Girls = {
    name: string,
    age: number
}

let myGirl1: Girls = {
    name: 'Alice',
    age: 25
};

let myGirl2: Girls = {
    name: 'Lina',
    age: false, // Error
    email: 'lina@naver.com' // Error
};</code></pre><br />

<p>ex2)</p>
<pre><code>// interface
interface Girls {
  name: string,
  age: number
}

let myGirl1: Girls = {
  name: 'Alice',
  age: 25
};

let myGirl2: Girls = {
  name: 'Lina',
  age: false, // Error
  email: 'lina@naver.com' // Error
};</code></pre><br />

<h3 id="타입---array">타입 - array</h3>
<p>배열 타입은 두 가지 방법으로 선언할 수 있다.</p>
<ol>
<li>첫 번째 방법은 배열 요소들을 나타내는 타입 뒤에 <strong>[]</strong> 사용</li>
<li>두 번째 방법은 <strong>Array&lt;&gt; 배열 타입</strong> 사용 -&gt; <strong>제네릭(Generics)</strong> 사용<br />

</li>
</ol>
<pre><code>// 방법1 : 타입 뒤에 [] 사용
let arr1: string[] = ['cookie', 'cake', 'candy'];

// 방법2 : Array&lt;&gt; 배열 타입 사용
let arr2: Array&lt;string&gt; = ['apple', 'tomato', 'banana'];</code></pre><br />

<p>Array&lt;타입&gt; 형식을 통해, 타입을 파라미터(매개변수)로 받아와서 지정하는 방법을 제네릭이라고 한다.</p>
<p>즉 미리 타입을 선언하지 않고 사용할 때 넘겨받는 방식이다.</p>
<br />

<p>ex)</p>
<pre><code>// number 타입만 허용
let nums:number[] = [100, 101, 102];

// string 타입만 허용
let strs:string[] = ['apple', 'banana', 'melon'];

// boolean 타입만 허용
let boos:boolean[] = [true, false, true];

// 모든 데이터 타입 허용 (any 타입, 아래에서 배움)
let someArr: any[] = [0, 1, {}, [], 'str', false];

// 특정 데이터 타입만 아이템으로 허용 (union 타입, 아래에서 배움)
let selects:(number | string)[] = [102, 'apple'];</code></pre><br />

<p>나머지 매개변수 기능도 배열과 관련이 있다.</p>
<blockquote>
<p><strong>나머지 매개변수(Rest Parameters)</strong>란,
 : 함수를 정의할 때 매개변수 앞에 점 3개(...)를 붙여서 &quot;여기에 들어오는 인자(값)들을 전부 모아서 하나의 배열로 만들겠다&quot;라고 선언하는 문법</p>
</blockquote>
<p>아래 예제 코드를 보면 getArr 함수의 매개변수인 <strong>&quot;...args&quot;</strong>이 나머지 매개변수로 정의되었다.</p>
<p>즉 매개변수의 개수를 따로 정하지 않고, 받는 만큼 전부 하나의 배열로 정리하여 반환하는 것이다.
<br /></p>
<p>ex)</p>
<pre><code>// 나머지 매개변수(스프레드 연산자)를 이용한 배열 반환 함수
function getArr(...args: number[]): number[] {
   return args;
}

let answer = getArr(1, 2, 3, 4, 5)

console.log(answer) // [1, 2, 3, 4, 5]</code></pre><br />

<h3 id="타입---tuple">타입 - tuple</h3>
<p>배열의 길이와 각 요소의 타입이 지정되어 있는 배열 형식을 <strong>튜플(tuple)</strong>이라고 한다. (= 배열의 크기와 타입 고정)</p>
<p><strong>&quot;튜플 = 배열의 서브타입&quot;</strong>이라고 생각하자.
<br /></p>
<pre><code>let arr: [string, number] = ['hello', 10];</code></pre><br />

<p>항상 정해진 갯수의 요소를 가져와야 하는 배열을 지정해서 응용할 때 사용한다.
<br /></p>
<p>ex1)</p>
<pre><code>let x: [string, number]; // 튜플 타입

x = [&quot;hello&quot;, 10]; // 성공
x = [10, &quot;hello&quot;]; // Error, 원소 타입 불일치
x = [&quot;hello&quot;, 10, 99]; // Error, 원소 개수 불일치</code></pre><br />

<p>ex2)</p>
<pre><code>let user: [number, string, boolean] = [1234, 'Alice', true];
console.log(user[0]); // 1234
console.log(user[1]); // 'Alice'
console.log(user[2]); // true</code></pre><br />

<p>ex3)</p>
<pre><code>// 2차원 튜플 타입 방법1
let users1: [number, string, boolean][];

users1 = [[1, 'Alice', true], [2, 'Lina', false], [3, 'Merry', true]];
console.log(users1)

// 2차원 튜플 타입 방법2

let users2: Array&lt;[number, string, boolean]&gt;;

users2 = [[1, 'Diana', true], [2, 'Luna', false], [3, 'Selly', false]];
console.log(users2)</code></pre><br />
타입뿐만 아니라 값 자체를 고정시키는 것도 가능하다.

<p>아래 예제 코드를 통해 확인해보자.</p>
<p>ex)</p>
<pre><code>// 값 자체 고정
// 값 개수는 2개 + 첫 번째 자리는 숫자 &quot;1&quot; 고정, 두 번째 자리는 number 타입
let tuple: [1, number];

tuple = [1, 2];
tuple = [1, 3];

// 첫 번째 자리가 숫자 &quot;1&quot;이 아님 -&gt; Error
tuple = [2, 3]; // Error - TS2322: Type '2' is not assignable to type '1'.</code></pre><br />

<p style="color: red; font-size: 18px; font-weight: bold;">
주의)
</p>
<p style="color: red; font-size: 16px; font-weight: bold;">
튜플은 정해진 타입의 고정된 길이 배열을 표현하지만, 이는 할당(Assign)에만 한정됨
</p>

<br />
즉 .push() 나 .splice() 등을 통해 값을 넣는 행위는 막을 수 없다는 뜻이다.

<p>ex)</p>
<pre><code>let tuple: [string, number];
tuple = ['a', 1];
tuple = ['b', 2];

tuple.push(3);
console.log(tuple); // ['b', 2, 3];

tuple.push(true); // Error
// push() 함수를 사용하여 요소를 추가할 때, 처음 할당된 값의 타입과 정확히 일치해야 함</code></pre><br />

<p>튜플의 에러는 어떤 식으로 발생할까?</p>
<p>정의해두지 않은 타입이나 인덱스로 접근할 경우엔 에러가 발생한다.
<br /></p>
<p>ex)</p>
<pre><code>let arr: [string, number] = ['hello', 10];

arr[1].concat('!'); // Error
arr[5] = &quot;hellomyfriend'; // Error</code></pre><br />

<p>위 두 접근 모두 에러가 발생한다.
<br /></p>
<p>먼저 arr[1]이 가리키는 값은 10이다. (인덱스는 0, 1, 2, ... 순서)</p>
<p>즉 숫자인데, 숫자 뒤에 문자열인 '!'를 붙이려고 했기 때문에 에러가 발생한 것이다.</p>
<span style="font-size: 16px; color: gray;">
  (concat은 글자나 배열에만 쓸 수 있는 기능)
</span>

<br />
<br />

<p>현재 선언한 튜플은 arr[0], arr[1] 딱 두 개 이다.</p>
<p>그런데 두 번째 arr[5]은 존재하지 않는 여섯 번째 배열의 위치 값을 요구하니 에러가 발생한다.</p>
<br />

<h3 id="타입---enum">타입 - enum</h3>
<p><strong>특정 값(상수)들의 집합</strong>을 의미하는 타입을 뜻한다. (C, Java 등에서도 사용)</p>
<p>튜플 타입이 특정 타입이나 값을 고정하는 배열이라면, Enum은 특정 값을 고정하는 또다른 독립된 자료형이라고 생각하면 된다.</p>
<br />

<p>ex)</p>
<pre><code>enum Friends {
    Alice,
    Lina,
    Merry
}

let girls1: Friends = Friends.Lina;
console.log(girls1); // 1

// enum은 인덱스 번호를 통해서도 접근 가능
let girls2: Friends = Friends[2];
console.log(girls2); // &quot;Merry&quot;</code></pre><br />

<p>또는 enum 인덱스 자체를 자체적으로 변경하여 사용하는 것도 가능하다.</p>
<p>이런 경우엔 자체적으로 조정한 인덱스의 다음 숫자부터 인덱스 순서가 계속 진행된다.
<br /></p>
<p>ex)</p>
<pre><code>enum Friends {
    Alice = 2,
    Lina, // 인덱스 3
    Merry // 인덱스 4
}

let girls1: Friends = Friends[2]; // &quot;Alice&quot;
console.log(girls1);

let girls2: Friends = Friends[4]; // &quot;Merry&quot;
console.log(girls2);</code></pre><br />

<p>enum 타입은 나중에 추가로 더 공부해보도록 하자.</p>
<br />

<h3 id="타입---any">타입 - any</h3>
<p>모든 타입에 사용 가능한 범용성을 가진 타입이다.</p>
<p>특정 타입을 잘 모르거나, 자바스크립트로 된 프로젝트에 타입스크립트를 조금 사용해야 하는 경우에 적용하면 좋은 타입이다.
<br /></p>
<p>예를 들어 사용자로부터 받은 데이터와 같은 동적 컨텐츠에서 변수나 함수를 다룰 때 사용할 수 있다.</p>
<br />

<p>ex1)</p>
<pre><code>let str: any = 'hello';
let num: any = 10;
let arr: any = ['a', 2, true];

let list: any[] = [1, true, &quot;free&quot;];
list[1] = 100;

console.log(list[2]) // &quot;free&quot;</code></pre><br />

<p>ex2)</p>
<pre><code>// 명시적 any 타입 지정 : any 타입 선언
let product_id1: any = 124981;

product_id1 = 'p9023412'; // any 타입 설정 -&gt; 어떤 유형도 값으로 할당 가능
console.log(product_id1); // &quot;p9023412&quot;

// 암시적 any 타입 지정 : any 타입 X, 변수 이름만 입력...
let product_id2;

product_id2 = 124981;
console.log(product_id2); // 124981

product_id2 = 'p9023412';
console.log(product_id2); // &quot;p9023412&quot;</code></pre><br />
하지만 이 any 타입은 되도록이면 사용하지 않는 것이 좋다.

<p>타입을 확실히 구분하는 것이 타입스크립트의 장점인데, any 타입을 많이 사용할수록 이러한 타입스크립트의 장점이 퇴색될 수 있다.
<br /></p>
<p>거기에 타입스크립트 컴파일의 보호를 받지 못하게 될 수 있다.</p>
<p>아래 예제 코드처럼 잘못된 연산이어도 컴파일이 경고를 안해주게 된다.
(= 자바스크립트의 단점)
<br /></p>
<p>ex)</p>
<pre><code>const a: any[] = [1, 2, 3, 4]; // array
const b: any = true; // boolean

a + b; // 배열과 불리언을 더했는데 컴파일이 허용 -&gt; 문제!</code></pre><br />

<h3 id="타입---void">타입 - void</h3>
<p>반환 값이 없는 함수의 반환 타입을 void라고 한다.</p>
<p>return이 없거나, return 이 있더라도 반환하는 값이 없는 경우에 사용하면 된다.
<br /></p>
<p>즉 어떤 타입도 존재할 수 없음을 나타내는 것이니, any 타입의 반대라고 이해하면 된다.</p>
<p>그래서 void는 보통 함수에서 return 값이 없을 때의 반환 타입을 표현하기 위해 사용하는 편이다.
<br /></p>
<p>ex)</p>
<pre><code>function printSomething(): void {
    console.log('hello'); // return X
}

function returnNothing(): void {
    return;
}</code></pre><br />

<h3 id="타입---null--undefined">타입 - Null &amp; Undefined</h3>
<p>TypeScript는 undefined 과 null 둘 다 각각 자신의 타입 이름으로 undefined , null로 사용한다.</p>
<p>(void처럼 그 자체로 유용한 경우는 거의 없음)
<br /></p>
<p>ex)</p>
<pre><code>// 이 밖에 이 변수들에 할당할 수 있는 값이 없음
let u: undefined = undefined;
let n: null = null;</code></pre><br />

<p>기본적으로 null 과 undefined는 다른 모든 타입의 하위 타입으로 취급된다.
&amp;nbsp&amp;nbsp = null과 undefined를 아무 여러 타입에 할당할 수 있다는 뜻!
<br /></p>
<p>그러나 <strong>--strictNullChecks</strong>를 사용하면, null과 undefined는 오직 any와 각자 자신들 타입에만 할당 가능하게 바뀐다.
(예외적으로 undefined는 void에 할당 가능)</p>
<p>이러한 --strictNullChecks는 많은 일반적인 에러를 방지하기 위해 사용한다.
<br /></p>
<p style="color: gray; font-size: 16px;">
&nbsp; + 가능한 --strictNullChecks를 사용하자!
</p>

<br />

<h3 id="타입---unknown">타입 - unknown</h3>
<p>unknown 타입은 쉽게 생각하면 any 타입과 같은 것이라고 보면 된다.</p>
<p>unknown 타입은 이름 그대로 알 수 없는 타입을 뜻하며, any 타입처럼 모든 데이터 타입을 받을 수 있다.
<br /></p>
<p>ex)</p>
<pre><code>let a: any = 123;
let u: unknown = 123;</code></pre><br />

<p>그러면 왜 unknown과 any 타입을 구분하는 것일까?</p>
<ul>
<li>any 타입은 어떤 것이어도 타입을 다 허용</li>
<li>unknown 타입은 해당 데이터를 &quot;모른다&quot;라는 의미가 더 강함<br />

</li>
</ul>
<p>&quot;엄격한 정도&quot;가 이 두 타입을 구분하는 차이점이다.
<br /></p>
<p>아래 예제 코드를 통해 예를 들어 확인하자.</p>
<p>any 타입은 number 타입의 데이터를 넣고 string 타입의 메소드인 length를 사용했을 때, 에러를 발생시키지 않고 그냥 undefined를 반환한다.
<br /></p>
<p>ex)</p>
<pre><code>let value : any = 10;
console.log(value.length); // undefined</code></pre><br />
하지만 unknown 타입은 모든 값을 허용하는 것 자체는 any 타입과 동일하지만, 할당된 해당 데이터가 어떤 타입인지는 모르기 때문에 함부로 연산을 하지 못한다는 특징을 갖고 있다.

<p>그래서 아래 코드처럼 에디터 자체에서 에러를 발생시킨다.
<br /></p>
<p>ex)</p>
<pre><code>let valueNum: unknown = 10;
let valueStr: unknown = 'Test';

console.log(valueNum.length); // Error, 'valueNum' is of type 'unknown'.
console.log(valueStr.length); // Error, 'valueStr' is of type 'unknown'.</code></pre><br />
이러한 경우엔 자바스크립트의 **typeof** 연산자를 사용하여 타입을 검사하며 해결하자.


<p>ex)</p>
<pre><code>let valueStr: unknown = &quot;hello&quot;;

if (typeof valueStr === &quot;string&quot;) { // typeof로 타입 검사
  console.log(valueStr.length); // 5
}</code></pre><br />

<p>이렇게 any 대신 unknown 타입을 사용하면 체크를 해야 되는 코드는 많아질 것이다.</p>
<p>그렇지만 그만큼 사전에 문제가 되는 부분을 방지할 수 있으니, any 타입에 비해 안정적인 애플리케이션을 개발할 수 있다.</p>
<br />

<h3 id="타입---never">타입 - never</h3>
<p>절대 발생하지 않을 값을 의미할 때 never 타입을 사용한다.</p>
<p>잘못된 것을 알려줄 때 사용하는 것이니, never 타입은 number나 string 처럼 어떠한 자료형 값을 담기 위한 타입이 아니다.
<br /></p>
<p>함수가 반복문이나 에러 핸들링으로 인해 함수의 끝에 절대 도달하지 않는 경우, never 타입을 사용하면 된다.
<br /></p>
<p>ex)</p>
<pre><code>// 함수의 끝까지 실행 X
function loopForever(): never {
    while(true){
        // ...
    }
}

function neverEnd(): never {
    throw new Error('unexpected');
}</code></pre><br />

<p>never 타입은 null &amp; undefiened 처럼 모든 타입에 할당을 할 수 있는 하위 타입이다.</p>
<p>하지만 반대로 어떤 타입도 never에 할당할 수 없기도 하다.
(never 자신은 제외)</p>
<br />
<br />