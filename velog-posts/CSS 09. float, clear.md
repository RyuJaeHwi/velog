<h2 id="float">float</h2>
<blockquote>
<p><strong>float 란?</strong>
: 요소가 문서의 일반적인 흐름에서 벗어나게 <strong>띄워(float)</strong>주고, 자신을 포함하고 있는 컨테이너의 왼쪽 혹은 오른쪽에 배치되게 하는 속성</p>
</blockquote>
<p>float은 해당 속성을 가진 요소가 문서의 흐름에서 제외되는 속성이지만, 필요한 만큼의 공간은 차지합니다.
<br /></p>
<table>
<thead>
<tr>
<th align="center">속성값</th>
<th>의미</th>
</tr>
</thead>
<tbody><tr>
<td align="center">none</td>
<td>기본값, 원래 상태</td>
</tr>
<tr>
<td align="center">left</td>
<td>자신을 포함하고 있는 컨테이너의 왼쪽에 떠있음</td>
</tr>
<tr>
<td align="center">right</td>
<td>자신을 포함하고 있는 컨테이너의 오른쪽에 떠있음&amp;nbsp&amp;nbsp</td>
</tr>
</tbody></table>
<br />
<br />

<p><em><strong>float 예시</strong></em></p>
<pre><code>&lt;!doctype html&gt;
&lt;html lang=&quot;en&quot;&gt;
  &lt;head&gt;
    &lt;meta charset=&quot;UTF-8&quot; /&gt;
    &lt;meta name=&quot;viewport&quot; content=&quot;width=device-width, initial-scale=1.0&quot; /&gt;
    &lt;title&gt;float, clear&lt;/title&gt;
    &lt;style&gt;
      #a {
        width: 100px;
        height: 50px;
        background-color: orange;
      }
      #b {
        width: 100px;
        height: 100px;
        background-color: royalblue;
      }
    &lt;/style&gt;
  &lt;/head&gt;
  &lt;body&gt;
    &lt;div id=&quot;a&quot;&gt;&lt;/div&gt;
    &lt;div id=&quot;b&quot;&gt;&lt;/div&gt;
    &lt;p&gt;첫 번째 태그 p&lt;/p&gt;
    &lt;p&gt;두 번째 태그 p&lt;/p&gt;
    &lt;p&gt;세 번째 태그 p&lt;/p&gt;
    &lt;p&gt;네 번째 태그 p&lt;/p&gt;
    &lt;p&gt;다섯 번째 태그 p&lt;/p&gt;
  &lt;/body&gt;
&lt;/html&gt;</code></pre><img src="https://velog.velcdn.com/images/choco_dev/post/fb526cce-8170-4e61-a5c6-d1c7df130d0e/image.png" width="70%" />

<p>float 옵션 추가 전입니다.</p>
<p>각 div와 p 태그가 위에서부터 순서대로 배치된 형태입니다.
<br /></p>
<p>여기에 float을 하나씩 추가해보도록 하겠습니다.
<br /></p>
<pre><code>&lt;!doctype html&gt;
&lt;html lang=&quot;en&quot;&gt;
  &lt;head&gt;
    &lt;meta charset=&quot;UTF-8&quot; /&gt;
    &lt;meta name=&quot;viewport&quot; content=&quot;width=device-width, initial-scale=1.0&quot; /&gt;
    &lt;title&gt;float, clear&lt;/title&gt;
    &lt;style&gt;
      #a {
        width: 100px;
        height: 50px;
        background-color: orange;
        float: right;
      }
      #b {
        width: 100px;
        height: 100px;
        background-color: royalblue;
      }
    &lt;/style&gt;
  &lt;/head&gt;
  &lt;body&gt;
    &lt;div id=&quot;a&quot;&gt;&lt;/div&gt;
    &lt;div id=&quot;b&quot;&gt;&lt;/div&gt;
    &lt;p&gt;첫 번째 태그 p&lt;/p&gt;
    &lt;p&gt;두 번째 태그 p&lt;/p&gt;
    &lt;p&gt;세 번째 태그 p&lt;/p&gt;
    &lt;p&gt;네 번째 태그 p&lt;/p&gt;
    &lt;p&gt;다섯 번째 태그 p&lt;/p&gt;
  &lt;/body&gt;
&lt;/html&gt;
</code></pre><img src="https://velog.velcdn.com/images/choco_dev/post/6c84f512-9654-42c9-88a8-3d5c62364df8/image.png" width="80%" />

<p>id=&quot;a&quot;인 오렌지색 div 박스가 오른쪽으로 이동했습니다.</p>
<p>그러나 블록 레벨 요소인 div가 영역 전체를 차지하지 않고 오른쪽으로만 이동했으며, 그 다음 파란 div 박스는 왼쪽 맨 위로 이동했습니다.
<br /></p>
<p>이제 id=&quot;b&quot;인 파란 div 박스에도 float을 적용해보도록 하겠습니다.</p>
<pre><code>&lt;!doctype html&gt;
&lt;html lang=&quot;en&quot;&gt;
  &lt;head&gt;
    &lt;meta charset=&quot;UTF-8&quot; /&gt;
    &lt;meta name=&quot;viewport&quot; content=&quot;width=device-width, initial-scale=1.0&quot; /&gt;
    &lt;title&gt;float, clear&lt;/title&gt;
    &lt;style&gt;
      #a {
        width: 100px;
        height: 50px;
        background-color: orange;
        float: right;
      }
      #b {
        width: 100px;
        height: 100px;
        background-color: royalblue;
        float: left;
      }
    &lt;/style&gt;
  &lt;/head&gt;
  &lt;body&gt;
    &lt;div id=&quot;a&quot;&gt;&lt;/div&gt;
    &lt;div id=&quot;b&quot;&gt;&lt;/div&gt;
    &lt;p&gt;첫 번째 태그 p&lt;/p&gt;
    &lt;p&gt;두 번째 태그 p&lt;/p&gt;
    &lt;p&gt;세 번째 태그 p&lt;/p&gt;
    &lt;p&gt;네 번째 태그 p&lt;/p&gt;
    &lt;p&gt;다섯 번째 태그 p&lt;/p&gt;
  &lt;/body&gt;
&lt;/html&gt;</code></pre><img src="https://velog.velcdn.com/images/choco_dev/post/fc89f19a-496d-41fb-beaf-2eb08c9bfb32/image.png" width="80%" />

<p>파란 div 박스도 float 속성에 맞게 왼쪽에 띄워집니다.</p>
<p>아래 p 태그들 또한 원래 div 바로 아래에 배치되었지만, float 옵션인 div의 바로 옆으로 이동하여 배치되는 것을 알 수 있습니다.</p>
<br />

<h2 id="clear">clear</h2>
<blockquote>
<p><strong>clear 란?</strong>
: float 요소 이후에 표시되는 요소가 이전에 있는 float 요소 옆에 배치되지 않도록 <strong>해제(clear)</strong>해주는 속성</p>
</blockquote>
<p>clear 속성은 블록 레벨 요소에 적용할 수 있습니다.</p>
<p>이전에 있는 float 요소의 다음에 있는 요소에만 적용 가능하며, 그 이후에 있는 float 요소에는 영향이 없습니다.
<br /></p>
<table>
<thead>
<tr>
<th align="center">속성값</th>
<th>의미</th>
</tr>
</thead>
<tbody><tr>
<td align="center">none</td>
<td>기본값, 아래로 이동되지 않음을 나타내는 키워드&amp;nbsp&amp;nbsp</td>
</tr>
<tr>
<td align="center">left</td>
<td>float이 left인 요소의 아래로 이동</td>
</tr>
<tr>
<td align="center">right</td>
<td>float이 right인 요소의 아래로 이동</td>
</tr>
<tr>
<td align="center">both</td>
<td>float이 left 및 right인 요소의 아래로 이동</td>
</tr>
</tbody></table>
<br />
<br />

<p><em><strong>clear 예시</strong></em></p>
<pre><code>&lt;!doctype html&gt;
&lt;html lang=&quot;en&quot;&gt;
  &lt;head&gt;
    &lt;meta charset=&quot;UTF-8&quot; /&gt;
    &lt;meta name=&quot;viewport&quot; content=&quot;width=device-width, initial-scale=1.0&quot; /&gt;
    &lt;title&gt;float, clear&lt;/title&gt;
    &lt;style&gt;
      #a {
        width: 100px;
        height: 250px;
        background-color: orange;
        float: right;
      }
      #b {
        width: 100px;
        height: 100px;
        background-color: royalblue;
        float: left;
      }
      p {
        clear: left;
      }
    &lt;/style&gt;
  &lt;/head&gt;
  &lt;body&gt;
    &lt;div id=&quot;a&quot;&gt;&lt;/div&gt;
    &lt;div id=&quot;b&quot;&gt;&lt;/div&gt;
    &lt;p&gt;첫 번째 태그 p&lt;/p&gt;
    &lt;p&gt;두 번째 태그 p&lt;/p&gt;
    &lt;p&gt;세 번째 태그 p&lt;/p&gt;
    &lt;p&gt;네 번째 태그 p&lt;/p&gt;
    &lt;p&gt;다섯 번째 태그 p&lt;/p&gt;
  &lt;/body&gt;
&lt;/html&gt;</code></pre><img src="https://velog.velcdn.com/images/choco_dev/post/77b93d7a-6f1c-4d99-8b41-c14351682633/image.png" width="80%" />

<p>태그 p들은 clear: left; 속성을 갖고 있습니다.</p>
<p>즉 이전 float 요소의 하단으로 이동하는 것이며, 파란 div 박스의 바로 아래로 이동하게 됩니다.
<br /></p>
<p>다른 속성값들은 어떻게 될까요?</p>
<pre><code>&lt;!doctype html&gt;
&lt;html lang=&quot;en&quot;&gt;
  &lt;head&gt;
    &lt;meta charset=&quot;UTF-8&quot; /&gt;
    &lt;meta name=&quot;viewport&quot; content=&quot;width=device-width, initial-scale=1.0&quot; /&gt;
    &lt;title&gt;float, clear&lt;/title&gt;
    &lt;style&gt;
      #a {
        width: 100px;
        height: 50px;
        background-color: orange;
        float: right;
      }
      #b {
        width: 100px;
        height: 100px;
        background-color: royalblue;
        float: left;
      }
      p {
        clear: right;
      }
    &lt;/style&gt;
  &lt;/head&gt;
  &lt;body&gt;
    &lt;div id=&quot;a&quot;&gt;&lt;/div&gt;
    &lt;div id=&quot;b&quot;&gt;&lt;/div&gt;
    &lt;p&gt;첫 번째 태그 p&lt;/p&gt;
    &lt;p&gt;두 번째 태그 p&lt;/p&gt;
    &lt;p&gt;세 번째 태그 p&lt;/p&gt;
    &lt;p&gt;네 번째 태그 p&lt;/p&gt;
    &lt;p&gt;다섯 번째 태그 p&lt;/p&gt;
  &lt;/body&gt;
&lt;/html&gt;</code></pre><img src="https://velog.velcdn.com/images/choco_dev/post/c2873ea4-240c-4819-927b-5ff294995065/image.png" width="80%" />

<p>clear: right;로 속성값을 바꾸었더니, float이 오른쪽인 첫 번째 오렌지색 div 박스의 바로 아래에 p 태그들이 배치됩니다.</p>
<p>오렌지색 div 박스의 높이를 낮추니 해당 높이 바로 아래부터 배치되는 것을 확인할 수 있습니다.
<br /></p>
<p>이제 both 속성값을 확인해보도록 하겠습니다.
<br /></p>
<pre><code>&lt;!doctype html&gt;
&lt;html lang=&quot;en&quot;&gt;
  &lt;head&gt;
    &lt;meta charset=&quot;UTF-8&quot; /&gt;
    &lt;meta name=&quot;viewport&quot; content=&quot;width=device-width, initial-scale=1.0&quot; /&gt;
    &lt;title&gt;float, clear&lt;/title&gt;
    &lt;style&gt;
      #a {
        width: 100px;
        height: 250px;
        background-color: orange;
        float: right;
      }
      #b {
        width: 100px;
        height: 100px;
        background-color: royalblue;
        float: left;
      }
      p {
        clear: both;
      }
    &lt;/style&gt;
  &lt;/head&gt;
  &lt;body&gt;
    &lt;div id=&quot;a&quot;&gt;&lt;/div&gt;
    &lt;div id=&quot;b&quot;&gt;&lt;/div&gt;
    &lt;p&gt;첫 번째 태그 p&lt;/p&gt;
    &lt;p&gt;두 번째 태그 p&lt;/p&gt;
    &lt;p&gt;세 번째 태그 p&lt;/p&gt;
    &lt;p&gt;네 번째 태그 p&lt;/p&gt;
    &lt;p&gt;다섯 번째 태그 p&lt;/p&gt;
  &lt;/body&gt;
&lt;/html&gt;</code></pre><img src="https://velog.velcdn.com/images/choco_dev/post/b8c1eb85-17da-455b-aa72-cce675669c9a/image.png" width="80%" />

<p>left, right 둘 중 더 아래에 있는 요소 하단으로 이동하는 것을 볼 수 있습니다.</p>