<h2 id="선택자-기본-개념">선택자 기본 개념</h2>
<blockquote>
<p><strong>선택자란?</strong>
: 어떤 요소에 스타일을 적용할 것인지에 대한 정보를 나타내는 요소</p>
</blockquote>
<pre><code>선택자{
  속성명: 속성값;
}</code></pre><p>선택자에는 아래와 같은 종류들이 있습니다.</p>
<ul>
<li><strong>기본 선택자</strong></li>
<li><strong>그룹 선택자</strong></li>
<li>특성 선택자</li>
<li>결합 선택자</li>
<li>의사 클래스</li>
<li>의사 요소</li>
</ul>
<br />

<p>이번 글에서는 위 종류들 중에서 가장 기초라고 할 수 있는 <strong>기본 선택자</strong>와 <strong>그룹 선택자</strong>부터 공부해보려고 합니다!
<br /></p>
<h2 id="기본-선택자">기본 선택자</h2>
<h3 id="전체-선택자">전체 선택자</h3>
<blockquote>
<p><strong>전체 선택자</strong>란, <strong>문서 내 모든 요소를 선택</strong>할 때 사용하는 선택자입니다.</p>
</blockquote>
<p>ex)</p>
<pre><code>*{
  color: blue;
}</code></pre><p><strong>*(애스타리스크)</strong>란, <strong>'문서 내의 모든 요소'</strong>를 의미하는 기호입니다.</p>
<p>즉 위 예시 코드는, 문서 내 모든 요소의 텍스트 색을 파란 색으로 지정한다는 뜻입니다.</p>
<br />

<h3 id="태그-선택자">태그 선택자</h3>
<blockquote>
<p><strong>태그 선택자</strong>란, 해당 이름을 가진 요소만 선택할 때 사용하는 선택자입니다. (= 유형 선택자)</p>
</blockquote>
<p>만약 해당 이름을 가진 요소가 문서 내 여러 개인 경우, 해당 요소들을 모두 선택합니다.</p>
<p>ex)</p>
<pre><code>p{
  color: pink;
}</code></pre><p>위 예시 코드는, 문서 내 모든 p 태그 요소의 텍스트 색을 분홍으로 지정한다는 뜻입니다.</p>
<br />


<h3 id="클래스-선택자">클래스 선택자</h3>
<blockquote>
<p><strong>클래스 선택자</strong>란, 주어진 class 속성값을 가진 요소만을 선택할 때 사용하는 선택자입니다.</p>
</blockquote>
<p>만약 해당 class 속성값을 가진 요소가 문서 내 여러 개인 경우, 해당 요소들을 모두 선택합니다.</p>
<p>ex)</p>
<pre><code>.text{
  color: blue;
}</code></pre><p>위 예시 코드는, 문서 내 class가 &quot;text&quot;인 모든 요소의 텍스트 색을 파란 색으로 지정한다는 뜻입니다.</p>
<br />

<h3 id="아이디-선택자">아이디 선택자</h3>
<blockquote>
<p><strong>아이디 산택자</strong>란, 주어진 id 속성값을 가진 요소를 선택할 때 사용하는 선택자입니다.</p>
</blockquote>
<p>여기서 id는 고유한 식별자 역할을 하는 전역 속성입니다.
(참고 링크 추가)</p>
<p>ex)</p>
<pre><code>#topic{
  color: blue;
}</code></pre><p>위 예시 코드는, 문서 내id가 &quot;topic&quot;인 요소의 텍스트 색을 파란 색으로 지정한다는 뜻입니다.
<br /></p>
<h2 id="그룹-선택자">그룹 선택자</h2>
<blockquote>
<p><strong>그룹 선택자</strong>란, 다양한 유형의 요소를 한꺼번에 선택하고자 할 때 사용하는 선택자입니다.
<strong>쉼표( , )</strong>를 이용해 선택자를 그룹화합니다.</p>
</blockquote>
<p>ex)</p>
<pre><code>h1, p, div{
  color: green;
}</code></pre><p>위 예시 코드는, 문서 내 모든 h1, p, div 태그 요소의 텍스트 색을 초록색으로 지정한다는 뜻입니다.
<br /></p>
<p style="color: black; font-size: 22px; font-weight: bold;">
선택자가 겹치는 경우?
</p>

<p>만약 위 선택자들이 고른 요소들이 서로 겹치는 경우엔 어떻게 될까요?
<br /></p>
<p><strong>1) 선택자가 겹치는 경우</strong></p>
<p> =&gt; 기본적으로 나중에 작성된 스타일이 적용됩니다. (아래에 적힌 것들)
<br /></p>
<p><strong>2) 선택자가 다르지만 요소가 겹치는 경우</strong></p>
<p>=&gt; &quot;선택자 우선순위&quot;에 의해 적용될 스타일이 결정됩니다.</p>
<br />

<blockquote>
<p style="color: black; font-size: 21px; font-weight: bold;">
"선택자 우선순위"
</blockquote>
</p>

<p><em>아이디 선택자 &gt; 클래스 선택자 &gt; 태그 선택자</em></p>
<br />


<p>이제 직접 테스트를 해보며 선택자에 대해 공부해봅시다.
<br /></p>
<p><em><strong>선택자 사용 예시 - 전체 선택자</strong></em></p>
<pre><code>&lt;!doctype html&gt;
&lt;html lang=&quot;en&quot;&gt;
  &lt;head&gt;
    &lt;meta charset=&quot;UTF-8&quot; /&gt;
    &lt;meta name=&quot;viewport&quot; content=&quot;width=device-width, initial-scale=1.0&quot; /&gt;
    &lt;title&gt;선택자 테스트&lt;/title&gt;
    &lt;style&gt;
      /* 전체 선택자 스타일 */
      * {
        color: green;
      }
    &lt;/style&gt;
  &lt;/head&gt;
  &lt;body&gt;
    &lt;h1&gt;제목&lt;/h1&gt;
    &lt;p&gt;문단 테스트1&lt;/p&gt;
    &lt;p&gt;문단 테스트2&lt;/p&gt;
    &lt;p&gt;문단 테스트3&lt;/p&gt;
  &lt;/body&gt;
&lt;/html&gt;
</code></pre><img src="https://velog.velcdn.com/images/choco_dev/post/7db473d6-5293-4b11-8713-0ab6ebc9873f/image.png" width="60%" />

<p>먼저 전체 요소들을 선택하는 <strong>&quot;*&quot; 선택자</strong>입니다. 이를 사용하니&lt;body&gt; 태그 안 모든 요소들의 텍스트 색이 green으로 바뀌었습니다.
<br /><br /></p>
<p><em><strong>선택자 사용 예시 - 태그, 클래스, 아이디 선택자</strong></em></p>
<pre><code>&lt;!doctype html&gt;
&lt;html lang=&quot;en&quot;&gt;
  &lt;head&gt;
    &lt;meta charset=&quot;UTF-8&quot; /&gt;
    &lt;meta name=&quot;viewport&quot; content=&quot;width=device-width, initial-scale=1.0&quot; /&gt;
    &lt;title&gt;선택자 테스트&lt;/title&gt;
    &lt;style&gt;
      /* 태그 선택자 스타일 */
      p {
        color: green;
      }
      /* 클래스 선택자 스타일 */
      .text {
        color: blue;
        font-size: 32px;
      }
      /* 아이디 선택자 스타일 */
      #number {
        color: orange;
      }
    &lt;/style&gt;
  &lt;/head&gt;
  &lt;body&gt;
    &lt;h1 class=&quot;text&quot;&gt;제목&lt;/h1&gt;
    &lt;p id=&quot;number&quot;&gt;문단 테스트1&lt;/p&gt;
    &lt;p class=&quot;text&quot;&gt;문단 테스트2&lt;/p&gt;
    &lt;p&gt;문단 테스트3&lt;/p&gt;
  &lt;/body&gt;
&lt;/html&gt;
</code></pre><img src="https://velog.velcdn.com/images/choco_dev/post/f646485f-ed84-44c2-b62c-cc3924736cd4/image.png" width="60%" />

<p>결과를 보면 p 태그 요소들의 텍스트 색은 green입니다.</p>
<p>그런데 아래 클래스 선택자와 아이디 선택자가 나와서 이 스타일이 덮어씌어집니다. <strong>(선택자 우선순위)</strong></p>
<p><br /><br /></p>
<p><em><strong>선택자 사용 예시 - 그룹 선택자</strong></em></p>
<pre><code>&lt;!doctype html&gt;
&lt;html lang=&quot;en&quot;&gt;
  &lt;head&gt;
    &lt;meta charset=&quot;UTF-8&quot; /&gt;
    &lt;meta name=&quot;viewport&quot; content=&quot;width=device-width, initial-scale=1.0&quot; /&gt;
    &lt;title&gt;선택자 테스트&lt;/title&gt;
    &lt;style&gt;
      /* 그룹 선택자 스타일 */
      h1,
      p {
        color: purple;
      }
      /* 우선순위는 클래스 선택자 &gt; 태그 선택자 */
      .text {
        color: red;
      }
      h1 {
        color: blue;
      }
    &lt;/style&gt;
  &lt;/head&gt;
  &lt;body&gt;
    &lt;h1 class=&quot;text&quot;&gt;제목&lt;/h1&gt;
    &lt;p id=&quot;number&quot;&gt;문단 테스트1&lt;/p&gt;
    &lt;p class=&quot;text&quot;&gt;문단 테스트2&lt;/p&gt;
    &lt;p&gt;문단 테스트3&lt;/p&gt;
  &lt;/body&gt;
&lt;/html&gt;</code></pre><img src="https://velog.velcdn.com/images/choco_dev/post/1bdbfcdc-1e81-4e5a-a4c8-dca62f7c9fbd/image.png" width="60%" />

<p>선택자 사이의 우선 순위는 <em>클래스 선택자 &gt; 태그 선택자</em> 입니다.</p>
<p>즉 위 예시 코드에서는 마지막에 h1{...} 태그 선택자가 나와서 제목 텍스트 색으로 파란 색상을 지정했지만, 우선 순위로는 클래스 선택자가 먼저이므로 .text {...} 의 red 컬러가 적용된 것입니다.</p>