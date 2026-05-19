<h2 id="position">position</h2>
<blockquote>
<p><strong>position 이란?</strong>
: 요소의 위치 지정 방식을 설정하는 속성</p>
</blockquote>
<p>position이 요소의 위치를 어떻게 배치할 지 먼저 방법을 정합니다.</p>
<p>그리고 그 다음 top, bottom, right, left가 각각의 값을 통해 세부적으로 요소의 위치를 조절하여 결정합니다.
<br /></p>
<ul>
<li><strong>position</strong> : 요소의 배치 방식</li>
<li><strong>top</strong> : 위에서부터 얼만큼 떨어뜨릴지 값 지정</li>
<li><strong>right</strong> : 오른쪽에서부터 얼만큼 떨어뜨릴지 값 지정</li>
<li><strong>bottom</strong> : 아래에서부터 얼만큼 떨어뜨릴지 값 지정</li>
<li><strong>left</strong> : 왼쪽에서부터 얼만큼 떨어뜨릴지 값 지정</li>
</ul>
<br />

<p>position의 배치 방식에는 다음과 같은 키워드들이 있습니다.
<br /></p>


<table class="position-table">
  <thead>
    <tr>
      <th>속성값</th>
      <th>의미</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>static</td>
      <td>기본값, 요소를 일반적인 문서 흐름에 따라 배치</td>
    </tr>
    <tr>
      <td>relative</td>
      <td>일반적인 문서 흐름에 따라 배치하되, 상하좌우 위치 값에 따라 오프셋 적용</td>
    </tr>
    <tr>
      <td>absolute</td>
      <td>일반적인 문서 흐름에서 제거 후, 가장 가까운 position 지정 요소에 대한 상대적 오프셋 적용</td>
    </tr>
    <tr>
      <td>fixed</td>
      <td>일반적인 문서 흐름에서 제거 후, 지정한 위치에 <b>고정</b></td>
    </tr>
    <tr>
      <td>sticky</td>
      <td>일반적인 문서 흐름에서 제거 후, 스크롤 동작이 존재하는 가장 가까운 요소에 대한 오프셋 적용</td>
    </tr>
  </tbody>
</table>

<br />


<h3 id="position-static">position: static;</h3>
<p><strong>position: static</strong> 속성은 top, bottom, right, left 세부 값을 지정할 수 없는 정적인(static) 위치 지정 방식입니다.</p>
<p>위에서부터 일반적인 문서 흐름대로 배치됩니다.
<br /></p>
<p><em><strong>position: static 예시</strong></em></p>
<pre><code>&lt;!doctype html&gt;
&lt;html lang=&quot;en&quot;&gt;
  &lt;head&gt;
    &lt;meta charset=&quot;UTF-8&quot; /&gt;
    &lt;meta name=&quot;viewport&quot; content=&quot;width=device-width, initial-scale=1.0&quot; /&gt;
    &lt;title&gt;position&lt;/title&gt;
    &lt;style&gt;
      div {
        width: 100px;
        height: 100px;
        background-color: rosybrown;

        position: static;

        top: 100px;
        left: 200px;
      }
    &lt;/style&gt;
  &lt;/head&gt;
  &lt;body&gt;
    &lt;div&gt;&lt;/div&gt;
    &lt;p&gt;p태그p태그p태그p태그p태그p태그p태그p태그p태그p태그p태그&lt;/p&gt;
  &lt;/body&gt;
&lt;/html&gt;</code></pre><img src="https://velog.velcdn.com/images/choco_dev/post/cf64c655-38ec-43e7-9020-a98548796414/image.png" width="80%" />

<p>style로 top과 left 값을 지정했는데 적용되지 않습니다.</p>
<br />

<h3 id="position-relative">position: relative;</h3>
<p><strong>position: relative</strong> 속성은 요소를 일반적인 문서 흐름에 따라 배치하는 것은 static과 똑같습니다.</p>
<p>그러나 상하좌우 위치 값에 따라 <strong>오프셋</strong>을 적용한다는 차이점이 있습니다.</p>
<p style="color: gray; font-size: 16px;">
오프셋이란? 위치를 얼마만큼 이동시키는지 지정하는 값
</p>

<br />

<p><em><strong>position: relative 예시</strong></em></p>
<pre><code>&lt;!doctype html&gt;
&lt;html lang=&quot;en&quot;&gt;
  &lt;head&gt;
    &lt;meta charset=&quot;UTF-8&quot; /&gt;
    &lt;meta name=&quot;viewport&quot; content=&quot;width=device-width, initial-scale=1.0&quot; /&gt;
    &lt;title&gt;position&lt;/title&gt;
    &lt;style&gt;
      div {
        width: 100px;
        height: 100px;
        background-color: rosybrown;

        position: relative;

        top: 100px;
        left: 200px;
      }
    &lt;/style&gt;
  &lt;/head&gt;
  &lt;body&gt;
    &lt;div&gt;&lt;/div&gt;
    &lt;p&gt;p태그p태그p태그p태그p태그p태그p태그p태그p태그p태그p태그&lt;/p&gt;
  &lt;/body&gt;
&lt;/html&gt;</code></pre><img src="https://velog.velcdn.com/images/choco_dev/post/fd56af85-f2d0-465e-80d6-76c8165978cb/image.png" width="80%" />
<img src="https://velog.velcdn.com/images/choco_dev/post/4e4df146-c0a8-4547-b6fa-320df1af28d5/image.png" width="60%" />

<p>위에서부터 100px, 왼쪽에서부터 200px 떨어뜨린 위치에 배치된 것을 볼 수 있습니다.</p>
<br />

<h3 id="position-absolute">position: absolute;</h3>
<p><strong>position: absolute</strong> 속성은 요소를 일반적인 문서 흐름에서 제거 후,상위 요소 중 가장 가까운 position 지정 요소에 대해 상대적인 오프셋을 적용합니다.</p>
<p style="color: gray; font-size: 16px;">
position 지정 요소란? position 속성에 속성값이 정의되어 있는 요소!
</p>

<br />

<p><em><strong>position: absolute 예시</strong></em></p>
<pre><code>&lt;!doctype html&gt;
&lt;html lang=&quot;en&quot;&gt;
  &lt;head&gt;
    &lt;meta charset=&quot;UTF-8&quot; /&gt;
    &lt;meta name=&quot;viewport&quot; content=&quot;width=device-width, initial-scale=1.0&quot; /&gt;
    &lt;title&gt;position&lt;/title&gt;
    &lt;style&gt;
      div {
        width: 200px;
        height: 200px;
        background-color: blanchedalmond;
        position: relative;
        border: 2px solid black;
      }
      .absolute {
        width: 100px;
        height: 100px;
        background-color: red;
        position: absolute;
        top: 50px;
        left: 150px;
      }
    &lt;/style&gt;
  &lt;/head&gt;
  &lt;body&gt;
    &lt;div&gt;&lt;/div&gt;
    &lt;div&gt;
      &lt;div class=&quot;absolute&quot;&gt;&lt;/div&gt;
      &lt;p&gt;p태그p태그p태그&lt;/p&gt;
    &lt;/div&gt;
    &lt;p&gt;p태그p태그p태그p태그p태그p태그p태그p태그p태그p태그p태그&lt;/p&gt;
  &lt;/body&gt;
&lt;/html&gt;</code></pre><img src="https://velog.velcdn.com/images/choco_dev/post/b05ff567-5e6f-40a0-99b7-b99467f70ecb/image.png" width="80%" />

<p>class=&quot;absolute&quot;의 빨간 div 박스는 absolute입니다. 즉 position 속성을 가진 가장 가까운 상위 요소에 맞춰서 위치가 지정됩니다.</p>
<p>class=&quot;absolute&quot; div의 상위 요소는 div로, 두 번째 위치의 베이지색 div 박스입니다.</p>
<p>이 div 박스를 기준으로 세부 위치를 지정합니다.</p>
<p>위로 50px, 왼쪽으로 150px 떨어진 곳에 배치하도록 설정해서 저렇게 나타났습니다.
<br /></p>
<p>top과 left 값을 바꾸어보면 어떻게 될까요?</p>
<img src="https://velog.velcdn.com/images/choco_dev/post/6b672ad4-909f-47d6-836d-d8fe6f1c8927/image.png" width="80%" />

<p>top: 10px, left: 80px 으로 설정하니 이런 식으로 배치되었습니다.</p>
<p>즉 absolute는 자신보다 상위 요소 중 position 속성을 가진 가장 가까운 요소를 기준으로 세부적인 배치 값을 적용한다는 것을 알 수 있습니다.
<br /></p>
<h3 id="position-fixed">position: fixed;</h3>
<p><strong>position: fixed</strong> 속성은 문서 흐름을 무시하고 브라우저 화면을 기준으로 요소를 배치합니다.</p>
<br />

<p><em><strong>position: fixed 예시</strong></em></p>
<pre><code>&lt;!doctype html&gt;
&lt;html lang=&quot;en&quot;&gt;
  &lt;head&gt;
    &lt;meta charset=&quot;UTF-8&quot; /&gt;
    &lt;meta name=&quot;viewport&quot; content=&quot;width=device-width, initial-scale=1.0&quot; /&gt;
    &lt;title&gt;position&lt;/title&gt;
    &lt;style&gt;
      .fixed {
        width: 200px;
        height: 200px;
        background: tomato;
        position: fixed;
        top: 50px;
        left: 150px;
      }
    &lt;/style&gt;
  &lt;/head&gt;
  &lt;body&gt;
    &lt;div&gt;
      첫번째&lt;br /&gt;첫번째&lt;br /&gt;첫번째&lt;br /&gt;첫번째&lt;br /&gt;
      첫번째&lt;br /&gt;첫번째&lt;br /&gt;첫번째&lt;br /&gt;첫번째&lt;br /&gt;
      첫번째&lt;br /&gt;첫번째&lt;br /&gt;첫번째&lt;br /&gt;첫번째&lt;br /&gt;
      첫번째&lt;br /&gt;첫번째&lt;br /&gt;첫번째&lt;br /&gt;첫번째&lt;br /&gt;
      첫번째&lt;br /&gt;첫번째&lt;br /&gt;첫번째&lt;br /&gt;첫번째&lt;br /&gt;
      첫번째&lt;br /&gt;첫번째&lt;br /&gt;첫번째&lt;br /&gt;첫번째&lt;br /&gt;
    &lt;/div&gt;
    &lt;div class=&quot;fixed&quot;&gt;&lt;/div&gt;
    &lt;div&gt;
      두번째&lt;br /&gt;두번째&lt;br /&gt;두번째&lt;br /&gt;두번째&lt;br /&gt;
      두번째&lt;br /&gt;두번째&lt;br /&gt;두번째&lt;br /&gt;두번째&lt;br /&gt;
      두번째&lt;br /&gt;두번째&lt;br /&gt;두번째&lt;br /&gt;두번째&lt;br /&gt;
      두번째&lt;br /&gt;두번째&lt;br /&gt;두번째&lt;br /&gt;두번째&lt;br /&gt;
      두번째&lt;br /&gt;두번째&lt;br /&gt;두번째&lt;br /&gt;두번째&lt;br /&gt;
      두번째&lt;br /&gt;두번째&lt;br /&gt;두번째&lt;br /&gt;두번째&lt;br /&gt;
    &lt;/div&gt;
  &lt;/body&gt;
&lt;/html&gt;</code></pre><img src="https://velog.velcdn.com/images/choco_dev/post/b6dd67c2-31f2-42fc-aa30-b104d57a4309/image.png" width="80%" />
<img src="https://velog.velcdn.com/images/choco_dev/post/1350882c-642b-477e-9e82-d4d6a3a95de1/image.png" width="80%" />

<p>결과를 보면 스크롤을 위아래로 계속 바꾸어도 div 박스의 위치는 고정되어 있습니다.</p>
<p>이처럼 fixed는 문서 흐름과는 상관없이 지정된 위치에 고정시킵니다.</p>
<br />

<h3 id="position-sticky">position: sticky;</h3>
<p><strong>position: sticky</strong> 속성은 스크롤 기능에 따라 position이 지정됩니다.</p>
<p>스크롤을 하다가 브라우저에서 설정한 위치가 되면 해당 요소의 배치가 결정됩니다.</p>
<br />

<p><em><strong>position: sticky 예시</strong></em></p>
<pre><code>&lt;!doctype html&gt;
&lt;html lang=&quot;en&quot;&gt;
  &lt;head&gt;
    &lt;meta charset=&quot;UTF-8&quot; /&gt;
    &lt;meta name=&quot;viewport&quot; content=&quot;width=device-width, initial-scale=1.0&quot; /&gt;
    &lt;title&gt;position&lt;/title&gt;
    &lt;style&gt;
      .sticky {
        width: 200px;
        height: 200px;
        background: tomato;
        position: sticky;
        top: 50px;
        left: 150px;
      }
    &lt;/style&gt;
  &lt;/head&gt;
  &lt;body&gt;
    &lt;div&gt;
      첫번째&lt;br /&gt;첫번째&lt;br /&gt;첫번째&lt;br /&gt;첫번째&lt;br /&gt;
      첫번째&lt;br /&gt;첫번째&lt;br /&gt;첫번째&lt;br /&gt;첫번째&lt;br /&gt;
      첫번째&lt;br /&gt;첫번째&lt;br /&gt;첫번째&lt;br /&gt;첫번째&lt;br /&gt;
      첫번째&lt;br /&gt;첫번째&lt;br /&gt;첫번째&lt;br /&gt;첫번째&lt;br /&gt;
      첫번째&lt;br /&gt;첫번째&lt;br /&gt;첫번째&lt;br /&gt;첫번째&lt;br /&gt;
      첫번째&lt;br /&gt;첫번째&lt;br /&gt;첫번째&lt;br /&gt;첫번째&lt;br /&gt;
    &lt;/div&gt;
    &lt;div class=&quot;sticky&quot;&gt;&lt;/div&gt;
    &lt;div&gt;
      두번째&lt;br /&gt;두번째&lt;br /&gt;두번째&lt;br /&gt;두번째&lt;br /&gt;
      두번째&lt;br /&gt;두번째&lt;br /&gt;두번째&lt;br /&gt;두번째&lt;br /&gt;
      두번째&lt;br /&gt;두번째&lt;br /&gt;두번째&lt;br /&gt;두번째&lt;br /&gt;
      두번째&lt;br /&gt;두번째&lt;br /&gt;두번째&lt;br /&gt;두번째&lt;br /&gt;
      두번째&lt;br /&gt;두번째&lt;br /&gt;두번째&lt;br /&gt;두번째&lt;br /&gt;
      두번째&lt;br /&gt;두번째&lt;br /&gt;두번째&lt;br /&gt;두번째&lt;br /&gt;
    &lt;/div&gt;
  &lt;/body&gt;
&lt;/html&gt;</code></pre><img src="https://velog.velcdn.com/images/choco_dev/post/7d06b877-06da-4060-80cb-efb14d1810b4/image.png" width="80%" />
<img src="https://velog.velcdn.com/images/choco_dev/post/a868ebdc-86bb-4e80-8170-bd1361f3f9ac/image.png" width="80%" />

<p>처음에는 아래에 있었지만, 스크롤을 하다가 top: 50px, left: 150px인 위치가 되는 순간 해당 위치에 고정되어 멈춥니다.</p>
<p>이는 위로 다시 스크롤을 하면 처음처럼 아래로 돌아갑니다.</p>