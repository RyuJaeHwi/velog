<h2 id="box-sizing">box-sizing</h2>
<blockquote>
<p><strong>box-sizing 이란?</strong>
: 해당 요소의 너비(width)와 높이(height)를 계산하는 방법을 지정하는 속성</p>
</blockquote>
<p>너비와 높이가 같더라도, box-sizing 속성값에 따라 크기가 달라질 수 있습니다.</p>
<p>아래는 해당 box-sizing 속성값을 정리한 표입니다.
<br /></p>
<table>
<thead>
<tr>
<th align="center">속성값</th>
<th>의미</th>
</tr>
</thead>
<tbody><tr>
<td align="center">content-box</td>
<td>기본값, 너비와 높이가 콘텐츠 영역만을 포함&amp;nbsp</td>
</tr>
<tr>
<td align="center">border-box</td>
<td>너비와 높이가 안쪽 여백과 테두리까지 포함</td>
</tr>
</tbody></table>
<br />
<br />
만약 200px * 20px의 너비와 높이 콘텐츠인 경우...

<ul>
<li><strong>content-box</strong> : 내부 콘텐츠 영역 크기만 200px * 20px</li>
<li><strong>border-box</strong> : border와 padding까지 합하여 200px * 20px</li>
</ul>
<p>이렇게 값이 계산되어 나타납니다.
<br /></p>
<p>아래 예시를 통해 어떤 식으로 값이 적용되는지 확인해보겠습니다.
<br /></p>
<p><em><strong>box-sizing 적용 예시</strong></em></p>
<pre><code>&lt;!doctype html&gt;
&lt;html lang=&quot;en&quot;&gt;
  &lt;head&gt;
    &lt;meta charset=&quot;UTF-8&quot; /&gt;
    &lt;meta name=&quot;viewport&quot; content=&quot;width=device-width, initial-scale=1.0&quot; /&gt;
    &lt;title&gt;box-sizing&lt;/title&gt;
    &lt;style&gt;
      div {
        width: 200px;
        padding: 20px;
        border: 10px solid black;
        margin-bottom: 20px;
      }
      .content-box {
        box-sizing: content-box;
      }
      .border-box {
        box-sizing: border-box;
      }
    &lt;/style&gt;
  &lt;/head&gt;
  &lt;body&gt;
    &lt;div class=&quot;content-box&quot;&gt;content-box&lt;/div&gt;
    &lt;div class=&quot;border-box&quot;&gt;border-box&lt;/div&gt;
  &lt;/body&gt;
&lt;/html&gt;</code></pre><img src="https://velog.velcdn.com/images/choco_dev/post/34138dbf-8025-424c-9d66-51c5b758ac06/image.png" width="80%" />
<img src="https://velog.velcdn.com/images/choco_dev/post/8b704d17-0a92-4330-8f9c-0445cfcbe560/image.png" width="80%" />

<p>결과를 보면 content-box 속성인 div 박스는 width: 200px가 내부 콘텐츠 영역의 너비로만 적용되었습니다.</p>
<p>그래서 padding 값과 border 값까지 합하여,
<strong>200px + 40px + 20px = 260px</strong> 이렇게 되었습니다.
<br /></p>
<p>반대로 border-box 속성인 div 박스는 padding 값과 border 값까지 다 합하여 width: 200px이 적용됩니다.</p>
<p>그래서 내부 콘텐츠 영역이 그 값들만큼 줄어든 것을 확인할 수 있습니다.</p>