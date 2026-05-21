<h2 id="특성-선택자">특성 선택자</h2>
<h3 id="특성-선택자의-특징">특성 선택자의 특징</h3>
<p><strong>특성 선택자(속성 선택자)</strong>는 주어진 속성의 존재 여부나 그 값에 따라 요소를 선택합니다.
<br /></p>
<p>ex) 클래스 속성을 가진 요소 선택하기</p>
<pre><code>[class]{
  background-color: tomato;
}</code></pre><p>ex) 클래스가 &quot;item&quot;인 요소 선택하기</p>
<pre><code>[class=&quot;item&quot;]{
  background-color: tomato;
}</code></pre><br />

<h3 id="특성-선택자의-값-확인">특성 선택자의 값 확인</h3>
<p>특성 선택자는 <strong>기호를 추가</strong>하여 요소를 선택하는 방식을 다양하게 만들 수 있습니다.
<br /></p>
<p>ex) 클래스 값에 <strong>&quot;it&quot;가 포함</strong>되는 요소 선택</p>
<pre><code>[class *= &quot;it&quot;]{ color: white; }</code></pre><p>ex) 클래스 값이 <strong>&quot;it&quot;로 시작</strong>하는 요소 선택</p>
<pre><code>[class ^= &quot;it&quot;]{ color: white; }</code></pre><p>ex) 클래스 값이 <strong>&quot;it&quot;로 끝</strong>나는 요소 선택</p>
<pre><code>[class $= &quot;it&quot;]{ color: white; }</code></pre><br />

<p><em><strong>특성 선택자 사용 예시</strong></em></p>
<pre><code>&lt;!doctype html&gt;
&lt;html lang=&quot;en&quot;&gt;
  &lt;head&gt;
    &lt;meta charset=&quot;UTF-8&quot; /&gt;
    &lt;meta name=&quot;viewport&quot; content=&quot;width=device-width, initial-scale=1.0&quot; /&gt;
    &lt;title&gt;선택자&lt;/title&gt;
    &lt;style&gt;
      [class*=&quot;t&quot;] {
        color: green;
      }
      [id=&quot;unique&quot;] {
        color: blueviolet;
      }
      [class^=&quot;my&quot;] {
        color: pink;
      }
      [id$=&quot;sh&quot;] {
        color: red;
      }
    &lt;/style&gt;
  &lt;/head&gt;
  &lt;body&gt;
    &lt;h1&gt;선택자 연습&lt;/h1&gt;
    &lt;p&gt;1번 문단 - p 태그&lt;/p&gt;
    &lt;p class=&quot;item&quot;&gt;2번 문단 - 클래스가 있는 p 태그&lt;/p&gt;
    &lt;p id=&quot;unique&quot;&gt;3번 문단 - 아이디가 있는 p 태그&lt;/p&gt;
    &lt;p class=&quot;text&quot;&gt;4번 문단 - 클래스가 있는 p 태그&lt;/p&gt;
    &lt;p class=&quot;myclass&quot;&gt;5번 문단 - 클래스가 있는 p 태그&lt;/p&gt;
    &lt;p id=&quot;finish&quot;&gt;6번 문단 - 아이디가 있는 p 태그&lt;/p&gt;
  &lt;/body&gt;
&lt;/html&gt;</code></pre><img src="https://velog.velcdn.com/images/choco_dev/post/d07b2d8f-5129-42a1-a59f-c4f2c960fb12/image.png" width="70%" />

<p>[class*=&quot;t&quot;]는 &quot;t&quot; 문자가 포함되는 클래스를 가진 요소들의 색을 green으로 바꿉니다.</p>
<p>[id=&quot;unique&quot;]는 id가 &quot;unique&quot;인 요소의 색을 blueviolet로 바꿉니다.</p>
<p>[class^=&quot;my&quot;]는 &quot;my&quot; 문자로 시작하는 클래스를 가진 요소들의 색을 pink로 바꿉니다.</p>
<p>[id$=&quot;sh&quot;]는 &quot;sh&quot; 문자로 끝나는 id를 가진 요소들의 색을 red로 바꿉니다.</p>
<br />

<h2 id="결합-선택자">결합 선택자</h2>
<h3 id="결합-선택자의-특징">결합 선택자의 특징</h3>
<p>결합 선택자(결합자)는 두 개 이상의 선택자를 결합시키고, 결합된 조건을 만족하는 요소를 선택합니다.
<br /></p>
<p>이 결합 선택자의 종류는 두 개로 구분합니다.</p>
<ul>
<li><strong>자손 결합자</strong></li>
<li><strong>형제 결합자</strong></li>
</ul>
<br />

<h3 id="결합-선택자--자손-결합자">결합 선택자 : 자손 결합자</h3>
<p>두 개의 선택자 중, 첫 번째 선택자 요소의 자손을 선택할 수 있습니다.
<br /></p>
<p>ex) div 요소 안에 위치하는 모든 p 요소 선택</p>
<pre><code>div p{ color: white; }</code></pre><p>ex) div 요소의 <strong>바로 아래에 위치</strong>하는 모든 p 요소 선택</p>
<pre><code>div &gt; p{ color: white; }</code></pre><br />

<p><em><strong>자손 결합자 예시</strong></em></p>
<pre><code>&lt;!doctype html&gt;
&lt;html lang=&quot;en&quot;&gt;
  &lt;head&gt;
    &lt;meta charset=&quot;UTF-8&quot; /&gt;
    &lt;meta name=&quot;viewport&quot; content=&quot;width=device-width, initial-scale=1.0&quot; /&gt;
    &lt;title&gt;선택자&lt;/title&gt;
    &lt;style&gt;
      body h1 {
        color: brown;
      }
      p &gt; span {
        color: red;
        font-size: 24px;
      }
    &lt;/style&gt;
  &lt;/head&gt;
  &lt;body&gt;
    &lt;h1&gt;선택자 연습&lt;/h1&gt;
    &lt;p&gt;1번 문단 - p 태그&lt;/p&gt;
    &lt;p class=&quot;item&quot;&gt;2번 문단 - 클래스가 있는 p 태그&lt;/p&gt;
    &lt;p id=&quot;unique&quot;&gt;3번 문단 - 아이디가 있는 p 태그&lt;/p&gt;
    &lt;p class=&quot;text&quot;&gt;4번 문단 - 클래스가 있는 p 태그&lt;/p&gt;
    &lt;p class=&quot;myclass&quot;&gt;5번 문단 - 클래스가 있는 p 태그&lt;/p&gt;
    &lt;p id=&quot;finish&quot;&gt;6번 문단 - 아이디가 있는 p 태그&lt;/p&gt;
    &lt;p&gt;7번 문단 - &lt;span&gt;span 태그가 있는&lt;/span&gt;p 태그&lt;/p&gt;
    &lt;h3&gt;마지막 문단&lt;/h3&gt;
  &lt;/body&gt;
&lt;/html&gt;</code></pre><img src="https://velog.velcdn.com/images/choco_dev/post/e52fe8e0-ad70-43d5-8ccd-c505fa3a3784/image.png" width="60%" />

<p>body 안의 모든 h1 요소들의 색을 brown으로, p 태그 안의 span 요소의 텍스트색과 크기를 조절하였습니다.</p>
<p>여기서 span 태그 요소는 상위 요소가 p 태그인데, 자손 결합자는 자신의 바로 아래에 있는 자식 요소만 선택 가능합니다.</p>
<p>즉 body &gt; span { ... } 이런 형태는 불가능하며 바로 위, 아래 관계여야 합니다.</p>
<br />

<h3 id="결합-선택자--형제-결합자">결합 선택자 : 형제 결합자</h3>
<p>두 개의 선택자 중, 첫 번째 선택자 요소의 형제를 선택할 수 있습니다.
<br /></p>
<p>ex) h1 요소의 뒤에 오는 형제 중, 모든 p 요소 선택</p>
<pre><code>h1 ~ p{ color: red; }</code></pre><p>ex) h1 요소의 바로 뒤에 오는 형제 p 요소 선택</p>
<pre><code>h1 + p{ color: red; }</code></pre><pre><code>&lt;!doctype html&gt;
&lt;html lang=&quot;en&quot;&gt;
  &lt;head&gt;
    &lt;meta charset=&quot;UTF-8&quot; /&gt;
    &lt;meta name=&quot;viewport&quot; content=&quot;width=device-width, initial-scale=1.0&quot; /&gt;
    &lt;title&gt;선택자&lt;/title&gt;
    &lt;style&gt;
      /* h1 안의 모든 p 태그 선택 (span 태그 제외됨) */
      h1 ~ p {
        color: rebeccapurple;
      }
      /* 클래스가 text인 요소 바로 아래 p 태그만 선택 */
      .text + p {
        color: green;
      }
      /* 클래스가 myclass인 요소 바로 아래 p 태그만 선택 */
      .myclass + p {
        color: red;
      }
    &lt;/style&gt;
  &lt;/head&gt;
  &lt;body&gt;
    &lt;h1&gt;선택자 연습&lt;/h1&gt;
    &lt;p&gt;1번 문단 - p 태그&lt;/p&gt;
    &lt;p class=&quot;item&quot;&gt;2번 문단 - 클래스가 있는 p 태그&lt;/p&gt;
    &lt;p id=&quot;unique&quot;&gt;3번 문단 - 아이디가 있는 p 태그&lt;/p&gt;
    &lt;p class=&quot;text&quot;&gt;4번 문단 - 클래스가 있는 p 태그&lt;/p&gt;
    &lt;p class=&quot;myclass&quot;&gt;5번 문단 - 클래스가 있는 p 태그&lt;/p&gt;
    &lt;p id=&quot;finish&quot;&gt;6번 문단 - 아이디가 있는 p 태그&lt;/p&gt;
    &lt;p&gt;7번 문단 - &lt;span&gt;span 태그가 있는&lt;/span&gt;p 태그&lt;/p&gt;
    &lt;h3&gt;마지막 문단&lt;/h3&gt;
  &lt;/body&gt;
&lt;/html&gt;</code></pre><img src="https://velog.velcdn.com/images/choco_dev/post/de470c09-cb03-4521-b6d9-b2ffad6d99eb/image.png" width="60%" />

<p>h1 태그 다음에 나오는 모든 p 태그 요소들을 rebeccapurple 색상으로 바꿉니다.</p>
<p>그리고 class=&quot;text&quot;인 요소 뒤에 나오는 p 태그 요소의 텍스트 색은 green으로,</p>
<p>class=&quot;myclass&quot;인 요소 뒤에 나오는 p 태그 요소의 텍스트 색은 red로 바꿉니다.</p>