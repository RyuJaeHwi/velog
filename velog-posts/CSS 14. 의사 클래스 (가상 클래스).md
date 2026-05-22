<h2 id="의사-클래스">의사 클래스</h2>
<blockquote>
<p><strong>의사 클래스(가상 클래스)</strong> 란?
: 선택자에 추가하는 키워드로, 요소가 어떤 특정한 상태일 때 해당 요소를  선택하겠다는 의미를 만들 때 사용</p>
</blockquote>
<p>의사 클래스의 코드 기본 구조입니다.</p>
<pre><code>선택자: 의사 클래스{
  속성명: 속성값;
}</code></pre><br />

<p>실제 저 구조를 적용하면 아래처럼 쓸 수 있습니다.</p>
<p><em>ex) h1 요소에 마우스 커서를 올리면 텍스트 색을 red로 변경</em></p>
<pre><code>h1:hover{
  color: red;
}</code></pre><br />

<p>아래 표는 의사 클래스 중 가장 많이 사용되는 것 일부를 정리한 것입니다.
<br /></p>
<table>
<thead>
<tr>
<th align="center">의사 클래스</th>
<th>의미</th>
</tr>
</thead>
<tbody><tr>
<td align="center">hover</td>
<td>마우스 포인터가 요소에 올라가 있는 경우</td>
</tr>
<tr>
<td align="center">active</td>
<td>사용자가 요소를 활성화한 경우 (마우스 클릭 등)&amp;nbsp&amp;nbsp</td>
</tr>
<tr>
<td align="center">focus</td>
<td>요소가 포커스를 받는 경우</td>
</tr>
<tr>
<td align="center">disabled</td>
<td>비활성 상태의 요소인 경우</td>
</tr>
<tr>
<td align="center">nth-child()</td>
<td>형제 사이에서의 순서에 따라 요소를 선택</td>
</tr>
</tbody></table>
<br />

<p>이 외에도 다양한 의사 클래스들이 있습니다.</p>
<br />

<p><em><strong>의사 클래스 예시1</strong></em></p>
<pre><code>&lt;!doctype html&gt;
&lt;html lang=&quot;en&quot;&gt;
  &lt;head&gt;
    &lt;meta charset=&quot;UTF-8&quot; /&gt;
    &lt;meta name=&quot;viewport&quot; content=&quot;width=device-width, initial-scale=1.0&quot; /&gt;
    &lt;title&gt;의사 클래스&lt;/title&gt;
    &lt;style&gt;
      /* 기본 스타일 */
      [type=&quot;button&quot;] {
        width: 100px;
        height: 30px;
        background-color: pink;
        color: white;
        border: none;
        border-radius: 8px;
      }
      /* hover = 커서를 가져다 두었을 때만 적용 (클릭X) */
      [type=&quot;button&quot;]:hover {
        background-color: gray;
      }
      /* active = 클릭 중일 때만 적용 */
      [type=&quot;button&quot;]:active {
        background-color: red;
      }
    &lt;/style&gt;
  &lt;/head&gt;
  &lt;body&gt;
    &lt;input type=&quot;button&quot; value=&quot;버튼&quot; /&gt;
  &lt;/body&gt;
&lt;/html&gt;</code></pre><img src="https://velog.velcdn.com/images/choco_dev/post/24df0e4b-d1cc-49ea-9bc6-0588ee055a10/image.png" width="60%" />

<img src="https://velog.velcdn.com/images/choco_dev/post/8bd4b224-c653-4437-a206-7a982052ac4f/image.png" width="60%" />

<img src="https://velog.velcdn.com/images/choco_dev/post/cba4e67f-c467-4b57-930d-0e061eb701e5/image.png" width="60%" />

<p>기본 색상은 pink이지만, 마우스 커서를 갖다 댄 hover 상태인 경우엔 버튼 색상을 gray로 바꿉니다.</p>
<p>그리고 마우스 클릭인 active인 경우에는 red로 색상을 바꿉니다.</p>
<br />

<p><em><strong>의사 클래스 예시2</strong></em></p>
<pre><code>&lt;!doctype html&gt;
&lt;html lang=&quot;en&quot;&gt;
  &lt;head&gt;
    &lt;meta charset=&quot;UTF-8&quot; /&gt;
    &lt;meta name=&quot;viewport&quot; content=&quot;width=device-width, initial-scale=1.0&quot; /&gt;
    &lt;title&gt;의사 클래스&lt;/title&gt;
    &lt;style&gt;
      input:focus {
        color: red;
        background-color: pink;
      }
    &lt;/style&gt;
  &lt;/head&gt;
  &lt;body&gt;
    &lt;input type=&quot;text&quot; placeholder=&quot;input 스타일 테스트&quot; /&gt;
  &lt;/body&gt;
&lt;/html&gt;</code></pre><img src="https://velog.velcdn.com/images/choco_dev/post/0ea7c572-3cf7-4879-a0d0-03d0b51fd394/image.png" width="60%" />

<img src="https://velog.velcdn.com/images/choco_dev/post/e56c2d49-f909-43f0-be6a-86c4342fe305/image.png" width="60%" />

<p>input 창을 커서로 클릭하여 focus 상태로 만든다면, 배경색은 pink가 되고 내부 깜빡이는 타이핑 바 색은 red가 됩니다.</p>
<p>두 번째 이미지를 보시면 확인하실 수 있습니다.
<br /></p>
<p>여기에 <strong>disabled</strong> 속성을 추가해보겠습니다.</p>
<p><strong>disabled</strong>는 해당 기능을 '사용 불가'로 변경하는 속성입니다.</p>
<pre><code>&lt;!doctype html&gt;
&lt;html lang=&quot;en&quot;&gt;
  &lt;head&gt;
    &lt;meta charset=&quot;UTF-8&quot; /&gt;
    &lt;meta name=&quot;viewport&quot; content=&quot;width=device-width, initial-scale=1.0&quot; /&gt;
    &lt;title&gt;의사 클래스&lt;/title&gt;
    &lt;style&gt;
      input:focus {
        color: red;
        background-color: pink;
      }
      input:disabled {
        height: 100px;
      }
    &lt;/style&gt;
  &lt;/head&gt;
  &lt;body&gt;
    &lt;input type=&quot;text&quot; placeholder=&quot;input 스타일 테스트&quot; disabled /&gt;
  &lt;/body&gt;
&lt;/html&gt;</code></pre><img src="https://velog.velcdn.com/images/choco_dev/post/6a48dbe4-7cfb-43ac-a226-9f116f969ea9/image.png" width="60%" />

<p>input창에 disabled 속성을 추가한 후,</p>
<p>이 input이 disabled된 경우에 높이를 100px로 바뀌도록 관련 의사 클래스를 추가했습니다.</p>
<br />

<p><em><strong>의사 클래스 예시3</strong></em></p>
<pre><code>&lt;!doctype html&gt;
&lt;html lang=&quot;en&quot;&gt;
  &lt;head&gt;
    &lt;meta charset=&quot;UTF-8&quot; /&gt;
    &lt;meta name=&quot;viewport&quot; content=&quot;width=device-width, initial-scale=1.0&quot; /&gt;
    &lt;title&gt;의사 클래스&lt;/title&gt;
    &lt;style&gt;
      body {
        display: flex;
        justify-content: space-around;
      }
      .box {
        width: 50px;
        height: 50px;
        background-color: blue;
        color: aliceblue;
      }
      .box:nth-child(3) {
        background-color: burlywood;
      }
    &lt;/style&gt;
  &lt;/head&gt;
  &lt;body&gt;
    &lt;div class=&quot;box&quot;&gt;1번&lt;/div&gt;
    &lt;div class=&quot;box&quot;&gt;2번&lt;/div&gt;
    &lt;div class=&quot;box&quot;&gt;3번&lt;/div&gt;
    &lt;div class=&quot;box&quot;&gt;4번&lt;/div&gt;
    &lt;div class=&quot;box&quot;&gt;5번&lt;/div&gt;
  &lt;/body&gt;
&lt;/html&gt;</code></pre><img src="https://velog.velcdn.com/images/choco_dev/post/450bef09-98ca-4b4b-8a32-dbf67a100824/image.png" width="70%" />

<p>각 div 박스마다 blue 색상을 지정하였는데, box:nth-child(3){ ... } 의사 클래스로 3번째 div 박스만 burlywood 색상이 되도록 지정하였습니다.
<br /></p>
<pre><code>.box:nth-child(2n) {
  background-color: burlywood;
}</code></pre><img src="https://velog.velcdn.com/images/choco_dev/post/adcaea2d-4a79-432e-a5a9-fe9f6c5dd39a/image.png" width="70%" />

<p>여기서 3을 2n으로 바꾸면, 2 * 1 = 2, 2 * 2 = 4, ...즉 짝수 번째 요소들만 해당 의사 클래스의 영향을 받게 됩니다.</p>
<p>홀수 번째 요소들을 변경하려면 2n - 1로 값을 넣으면 됩니다.
<br /></p>
<pre><code>.box:nth-child(n) {
  background-color: burlywood;
}</code></pre><img src="https://velog.velcdn.com/images/choco_dev/post/76691167-72d8-48b5-8650-c4f501642c64/image.png" width="70%" />

<p>그냥 n을 넣는다면 해당하는 모든 요소의 순서에 대한 숫자를 대입합니다.</p>
<p>즉 해당하는 모든 요소에 의사 클래스를 적용합니다.</p>