<h2 id="상속ingeritance">상속(Ingeritance)</h2>
<blockquote>
<p><strong>상속(Ingeritance) 이란?</strong>
: 하위 요소가 상위 요소의 스타일 속성값을 물려받는 것</p>
</blockquote>
<p>이 상속 기능이 이루어지는 속성과, 영향을 받지 않는 속성이 따로 있습니다.</p>
<p>아래 표는 이러한 속성들을 구분한 것입니다.</p>
<table>
<thead>
<tr>
<th align="center">상속 여부</th>
<th>상속 O</th>
<th>상속 X</th>
</tr>
</thead>
<tbody><tr>
<td align="center">속성</td>
<td>&amp;nbsp&amp;nbsp&amp;nbspcolor, font-family, font-size, font-&amp;nbsp&amp;nbsp&amp;nbspweight, text-align, cursor 등</td>
<td>&amp;nbsp&amp;nbsp&amp;nbspbackground-color, background-image, &amp;nbsp&amp;nbsp&amp;nbspbackground-repeat, border, display 등</td>
</tr>
</tbody></table>
<br />

<p><em><strong>상속(Ingeritance) 사용 예시</strong></em></p>
<pre><code>&lt;!doctype html&gt;
&lt;html lang=&quot;en&quot;&gt;
  &lt;head&gt;
    &lt;meta charset=&quot;UTF-8&quot; /&gt;
    &lt;meta name=&quot;viewport&quot; content=&quot;width=device-width, initial-scale=1.0&quot; /&gt;
    &lt;title&gt;의사 요소&lt;/title&gt;
    &lt;style&gt;
      div {
        display: flex;
        justify-content: center;
        align-items: center;
        width: 300px;
        height: 300px;

        /* p 태그의 텍스트는 아래 tomato 색을 상속받음
        (따로 p 태그 스타일이 있으면 해당 스타일 적용) */
        color: tomato;
        font-size: 24px;
        border: 3px dashed violet;
      }
      p {
        border: 1px solid blue;
      }
    &lt;/style&gt;
  &lt;/head&gt;
  &lt;body&gt;
    &lt;div&gt;
      &lt;p&gt;가운데 p 태그&lt;/p&gt;
    &lt;/div&gt;
  &lt;/body&gt;
&lt;/html&gt;
</code></pre><img src="https://velog.velcdn.com/images/choco_dev/post/2e46f5f6-f10f-4612-bb6c-c817c5709b89/image.png" width="60%" />

<p>p 태그 요소에는 텍스트 색을 따로 지정하지 않았지만 div 태그 요소가 가진 color: tomato; 색상이 그대로 상속되었습니다.</p>
<br />

<pre><code>p {
  color: teal;
  border: 1px solid blue;
}</code></pre><img src="https://velog.velcdn.com/images/choco_dev/post/065628c2-2343-47fa-b1c7-2986013d3706/image.png" width="60%" />

<p>p 태그 요소에 따로 색상 속성을 추가하면, 해당 속성을 우선적으로 적용합니다.</p>
<br />

<h2 id="공용-키워드">공용 키워드</h2>
<blockquote>
<p><strong>공용 키워드란?</strong>
: 모든 CSS 속성에 사용 가능한 키워드, &quot;전역 값&quot;이라고도 표현</p>
</blockquote>
<p>아래는 공용 키워드의 종류를 정리한 것입니다.</p>
<table>
<thead>
<tr>
<th align="center">키워드</th>
<th>의미</th>
</tr>
</thead>
<tbody><tr>
<td align="center">inherit</td>
<td>상위 요소로부터 해당 속성의 값을 받아 사용</td>
</tr>
<tr>
<td align="center">initial</td>
<td>(브라우저에 지정되어 있는) 해당 속성의 기본값을 요소에 적용</td>
</tr>
<tr>
<td align="center">unset</td>
<td>상속 속성에 대해서는 inherit처럼, 상속되지 않는 속성에 대해서는 initial처럼 적용&amp;nbsp&amp;nbsp</td>
</tr>
</tbody></table>
<br />
<br />

<p><em><strong>공용 키워드 사용 예시1</strong></em></p>
<pre><code>&lt;!doctype html&gt;
&lt;html lang=&quot;en&quot;&gt;
  &lt;head&gt;
    &lt;meta charset=&quot;UTF-8&quot; /&gt;
    &lt;meta name=&quot;viewport&quot; content=&quot;width=device-width, initial-scale=1.0&quot; /&gt;
    &lt;title&gt;의사 요소&lt;/title&gt;
    &lt;style&gt;
      div {
        display: flex;
        justify-content: center;
        align-items: center;
        width: 300px;
        height: 300px;
        color: tomato;
        font-size: 36px;
        border: 3px dashed violet;
      }
      p {
        color: initial;
        font-size: inherit;
        border: inherit;
      }
    &lt;/style&gt;
  &lt;/head&gt;
  &lt;body&gt;
    &lt;div&gt;
      &lt;p&gt;가운데 p 태그&lt;/p&gt;
    &lt;/div&gt;
  &lt;/body&gt;
&lt;/html&gt;</code></pre><img src="https://velog.velcdn.com/images/choco_dev/post/a71a1deb-21c0-4754-b252-b16717492b5a/image.png" width="60%" />

<p>color는 상속받지 않는 기본값인 initial로 하였기 때문에 검은색으로 됩니다.</p>
<p>font-size는 p태그 상위 요소인 div의 크기를 상속받으니 36px입니다.</p>
<p>여기서 border도 inherit으로 상속받는데, 만약 initial로 바꾸면 어떻게 될까요?
<br /></p>
<pre><code>p {
  color: initial;
  font-size: inherit;
  border: initial;
}</code></pre><img src="https://velog.velcdn.com/images/choco_dev/post/4b3a40c8-f0a0-4481-a353-49fd5ce59a14/image.png" width="60%" />

<p>border는 기본값이 없으니 initial을 사용할 수 없습니다.</p>
<p>따라서 border: initial;라고 한 경우엔 테두리가 아예 없어지게 됩니다.
<br /></p>
<p>border: unset;이라고 한 경우엔 상속받는 값이면 inherit을, 그렇지 못하는 값이면 initial을 적용합니다.</p>
<pre><code>p {
  color: initial;
  font-size: inherit;
  border: unset;
}</code></pre><img src="https://velog.velcdn.com/images/choco_dev/post/479a5710-b78a-4224-a6c2-3046d13e7c91/image.png" width="60%" />

<p>즉 똑같이 p 태그 요소의 테두리 선이 없어집니다.</p>