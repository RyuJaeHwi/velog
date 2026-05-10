<h2 id="블록-레벨-요소-vs-인라인-요소">블록 레벨 요소 vs 인라인 요소</h2>
<blockquote>
<p><strong>블록 레벨 요소</strong> : 자신이 속한 영역의 너비를 모두 차지하여 블록 형성
ex) div, p, h1 등...</p>
</blockquote>
<blockquote>
<p><strong>인라인 요소</strong> : 자신에게 필요한 만큼의 공간만 차지
ex) span, a 등...</p>
</blockquote>
<br />

<p>블록 레벨 요소 vs 인라인 요소 비교 예시</p>
<pre><code>&lt;!doctype html&gt;
&lt;html lang=&quot;en&quot;&gt;
  &lt;head&gt;
    &lt;meta charset=&quot;UTF-8&quot; /&gt;
    &lt;meta name=&quot;viewport&quot; content=&quot;width=device-width, initial-scale=1.0&quot; /&gt;
    &lt;title&gt;텍스트 꾸미기&lt;/title&gt;
  &lt;/head&gt;
  &lt;body&gt;
    &lt;h1&gt;블록 레벨 요소 영역&lt;/h1&gt;
    &lt;h2&gt;&lt;span&gt;인라인&lt;/span&gt; 요소 영역&lt;/h2&gt;
  &lt;/body&gt;
&lt;/html&gt;
</code></pre><img src="https://velog.velcdn.com/images/choco_dev/post/7067984c-c75a-4037-9c3d-b4fab7c591b3/image.png" width="70%" />

<p>블록 레벨 요소인 h1은 텍스트가 끝나도 해당 영역 전체를 차지합니다.
<br /></p>
<img src="https://velog.velcdn.com/images/choco_dev/post/e5dd2a64-3d58-42c4-89ff-04f1b0c5c429/image.png" width="70%" />

<p>인라인 요소인 span은 h2 중 일부를 나타내고, 직접 확인해보면 해당 span이 차지하는 &quot;인라인&quot; 텍스트 영역만 차지합니다.
<br /></p>
<h2 id="display-속성">display 속성</h2>
<blockquote>
<p><strong>display 속성이란?</strong>
: 요소를 블록과 인라인 요소 중 어느 쪽으로 처리할지 정의하는 속성</p>
</blockquote>
<p>✔️ 블록 레벨 요소인 div를 <strong>인라인으로 처리</strong>할 때 (블록 -&gt; 인라인)</p>
<pre><code>div{ display: inline; }</code></pre><p>✔️ 인라인 레벨 요소인 a를 <strong>블록 레벨로 처리</strong>할 때 (인라인 -&gt; 블록)</p>
<pre><code>a{ display: block; }</code></pre><br />
<p style="color: black; font-size: 20px; font-weight: bold;">
display의 속성값 정리
</p>

<table>
<thead>
<tr>
<th align="center">단위</th>
<th>의미</th>
</tr>
</thead>
<tbody><tr>
<td align="center">inline</td>
<td>인라인으로 처리</td>
</tr>
<tr>
<td align="center">block</td>
<td>블록 레벨로 처리</td>
</tr>
<tr>
<td align="center">&amp;nbspinline-block&amp;nbsp</td>
<td>인라인으로 배치하되, 블록 레벨 요소의 속성을 추가할 수 있도록 처리 &amp;nbsp&amp;nbsp</td>
</tr>
<tr>
<td align="center">none</td>
<td>표시하지 않도록 처리</td>
</tr>
</tbody></table>
<br />

<p>가장 대표적으로 많이 사용되는 display의 속성값들입니다.
<br /></p>
<p>display 영역 예시</p>
<pre><code>&lt;!doctype html&gt;
&lt;html lang=&quot;en&quot;&gt;
  &lt;head&gt;
    &lt;meta charset=&quot;UTF-8&quot; /&gt;
    &lt;meta name=&quot;viewport&quot; content=&quot;width=device-width, initial-scale=1.0&quot; /&gt;
    &lt;title&gt;display 속성&lt;/title&gt;
  &lt;/head&gt;
  &lt;body&gt;
    &lt;div&gt;블록 레벨 영역&lt;/div&gt;
    &lt;br /&gt;
    &lt;span&gt;인라인 레벨 영역&lt;/span&gt;
  &lt;/body&gt;
&lt;/html&gt;</code></pre><img src="https://velog.velcdn.com/images/choco_dev/post/285923a7-aa14-4039-b130-9cf88c8a2465/image.png" width="70%" />

<p>해당 영역별로 어떻게 너비가 정해지는지 확인해보도록 하겠습니다.
<br /></p>
<img src="https://velog.velcdn.com/images/choco_dev/post/f92b20a3-a554-448e-8b9e-9c2425f1f5ae/image.png" width="70%" />
<img src="https://velog.velcdn.com/images/choco_dev/post/8e827819-e861-482a-9ccd-23a8d1dce1a4/image.png" width="70%" />

<p>개발자 모드를 통해 각 요소의 영역을 살펴보았습니다.</p>
<p>block 영역은 내부 요소가 끝났어도 해당 영역 전체를 차지하지만 inline 영역은 내부 요소 크기만큼의 영역을 차지하는 것을 직접 볼 수 있습니다.</p>
<br />


<h2 id="border-속성">border 속성</h2>
<blockquote>
<p><strong>border 속성이란?</strong>
: 해당 요소가 차지하고 있는 영역에 테두리를 추가하는 속성</p>
</blockquote>
<p>border 속성을 통해 너비, 스타일, 색상을 지정해서 해당 영역에 테두리를 추가할 수 있습니다.</p>
<p>또한 border는 속성값으로 테두리의 두께, 모양, 크리 등을 단축해서 한꺼번에 지정하는 특징이 있는데, 이를 <strong>&quot;단축 속성(shorthand property)&quot;</strong>이라고 합니다.
<br /></p>
<p><strong>border의 속성 요소</strong></p>
<ul>
<li>border-width</li>
<li>border-style</li>
<li>border-color</li>
</ul>
<br />
표로 정리해보면 다음과 같습니다.
<br />
<br />

<p style="color: black; font-size: 20px; font-weight: bold;">
border의 속성값 정리
</p>

<table>
<thead>
<tr>
<th align="center">단위</th>
<th>의미</th>
</tr>
</thead>
<tbody><tr>
<td align="center">border-width</td>
<td>none(기본값), solid(직선), dotted(점선), dashed(긴 점선) 등&nbsp;&nbsp;</td>
</tr>
<tr>
<td align="center">border-style</td>
<td>thin, medium, thick 등의 키워드 / px, em, rem 등의 단위</td>
</tr>
<tr>
<td align="center">border-color</td>
<td>color 정의 방식과 동일</td>
</tr>
</tbody></table>
<br />
<br />

<p><strong>단축 속성</strong>이라는 특징을 사용하면 아래처럼 표현 가능합니다!</p>
<p>ex)</p>
<pre><code>span{ border: 2px solid green }</code></pre><img src="https://velog.velcdn.com/images/choco_dev/post/106908fa-157b-4c14-808a-2cd646c7e917/image.png" width="60%" />

<p>위 예시 코드는, &quot;두께가 2px인 직선 모양(solid)의 초록색 테두리 제작&quot;이라는 뜻입니다.
<br /></p>
<p>예시를 통해 직접 만들어보도록 하겠습니다!
<br /></p>
<p>ex)
<em><strong>border 속성 예시</strong></em></p>
<pre><code>&lt;!doctype html&gt;
&lt;html lang=&quot;en&quot;&gt;
  &lt;head&gt;
    &lt;meta charset=&quot;UTF-8&quot; /&gt;
    &lt;meta name=&quot;viewport&quot; content=&quot;width=device-width, initial-scale=1.0&quot; /&gt;
    &lt;title&gt;border 속성&lt;/title&gt;
    &lt;style&gt;
      div {
        border: 2px solid red;
      }
      span {
        border-width: 5px;
        border-style: dashed;
        border-color: orange;
      }
      /* span {
        border: 5px dashed orange;
      } */
    &lt;/style&gt;
  &lt;/head&gt;
  &lt;body&gt;
    &lt;div&gt;블록 레벨 영역&lt;/div&gt;
    &lt;br /&gt;
    &lt;span&gt;인라인 레벨 영역&lt;/span&gt;
  &lt;/body&gt;
&lt;/html&gt;</code></pre><img src="https://velog.velcdn.com/images/choco_dev/post/4d38e422-defc-45ed-887f-b578c520083b/image.png" width="60%" />