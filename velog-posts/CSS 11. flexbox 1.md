<h2 id="flexbox">flexbox</h2>
<blockquote>
<p><strong>flexbox 란?</strong>
박스 내 요소 간의 공간 배분과 정렬 기능을 제공하기 위한 1차원 레이아웃 모델</p>
</blockquote>
<p>여기서 flexbox를 1차원 모델이라 부르는 이유는, 레이아웃을 다룰 때 한 번에 하나의 차원만 다루기 때문입니다.</p>
<p>즉 한 번에 행, 또는 열 하나만 다룹니다. (동시에 X)
<br /></p>
<p align="center">
<img src="https://velog.velcdn.com/images/choco_dev/post/b0b3ae60-9527-48da-83da-7202f1fbf48c/image.png" width="80%" />
</p>

<br />

<h3 id="flexbox-만들기">flexbox 만들기</h3>
<p>flexbox는 flex 컨테이너라고도 불립니다. (= 요소들을 포함)</p>
<p>flexbox를 만들기 위해선, 컨테이너가 되는 요소에 <strong>display: flex;</strong>를 적용하면 됩니다.
<br /></p>
<p>ex)
flexbox 적용 전...</p>
<div style="display: flex;">
  <div style="width: 50%;">
    <pre><code>
&lt;div&gt;
  &lt;div class="item"&gt;요소1&lt;/div&gt;
  &lt;div class="item"&gt;요소2&lt;/div&gt;
  &lt;div class="item"&gt;요소3&lt;/div&gt;
&lt;/div&gt;
    </code></pre>
  </div>
  <div style="width: 50%;">
    <img src="https://velog.velcdn.com/images/choco_dev/post/0241dced-b086-445f-9c92-0159e2b6c841/image.png" width="100%" />
  </div>
</div>

<br />
flexbox 적용 후
<div style="display: flex;">
  <div style="width: 50%;">
    <pre><code>
&lt;div style="display: flex"&gt;
  &lt;div class="item"&gt;요소1&lt;/div&gt;
  &lt;div class="item"&gt;요소2&lt;/div&gt;
  &lt;div class="item"&gt;요소3&lt;/div&gt;
&lt;/div&gt;
    </code></pre>
  </div>
  <div style="width: 50%;">
    <img src="https://velog.velcdn.com/images/choco_dev/post/484f4607-66d7-400f-8723-d7232ed8c63c/image.png" width="100%" />
  </div>
</div>

<p>각 요소가 개별로 취급되어 위에서부터 하나씩 쌓이던 것을 display: flex; 속성을 추가하여 하나의 컨테이너로 취급되고 나란히 배치되게 하였습니다.</p>
<br />

<h2 id="flex-direction">flex-direction</h2>
<p>flexbox에는 <strong>&quot;주축(main-axis)&quot;</strong>과 <strong>&quot;교차축(cross-axis)&quot;</strong>이 있습니다.</p>
<p align="center">
<img src="https://velog.velcdn.com/images/choco_dev/post/d97df509-8d51-401a-9915-7cbaf2b41f80/image.png" width="80%" />
</p>

<blockquote>
<p><strong>flex-direction 이란?</strong>
: flexbox 내 요소를 배치할 때 사용할 주축과 방향(정방향, 역방향)을 지정하는 속성</p>
</blockquote>
<table>
<thead>
<tr>
<th align="center">속성값</th>
<th>의미</th>
</tr>
</thead>
<tbody><tr>
<td align="center">row</td>
<td>기본값, 주축은 행이고 방향은 콘텐츠의 방향과 동일&amp;nbsp&amp;nbsp</td>
</tr>
<tr>
<td align="center">row-reverse</td>
<td>주축은 행이고 방향은 콘텐츠의 방향과 반대</td>
</tr>
<tr>
<td align="center">column</td>
<td>주축은 열이고 방향은 콘텐츠의 방향과 동일</td>
</tr>
<tr>
<td align="center">column-reverse</td>
<td>주축은 열이고 방향은 콘텐츠의 방향과 반대</td>
</tr>
</tbody></table>
<p><br /><br /></p>
<p><em><strong>flex-direction 예시</strong></em></p>
<pre><code>&lt;!doctype html&gt;
&lt;html lang=&quot;en&quot;&gt;
  &lt;head&gt;
    &lt;meta charset=&quot;UTF-8&quot; /&gt;
    &lt;meta name=&quot;viewport&quot; content=&quot;width=device-width, initial-scale=1.0&quot; /&gt;
    &lt;title&gt;flexbox&lt;/title&gt;
    &lt;style&gt;
      .container {
        display: flex;
        /* row = 행, column = 열 */
        flex-direction: row;
      }
      .item {
        width: 80px;
        height: 80px;
        background-color: pink;
      }
    &lt;/style&gt;
  &lt;/head&gt;
  &lt;body&gt;
    &lt;div class=&quot;container&quot;&gt;
      &lt;div class=&quot;item&quot;&gt;1&lt;/div&gt;
      &lt;div class=&quot;item&quot;&gt;2&lt;/div&gt;
      &lt;div class=&quot;item&quot;&gt;3&lt;/div&gt;
    &lt;/div&gt;
  &lt;/body&gt;
&lt;/html&gt;</code></pre><img src="https://velog.velcdn.com/images/choco_dev/post/5b159dd0-689d-4160-a586-51ceb7a5e216/image.png" width="60%" />

<p>기본값인 <strong>flex-direction: row;</strong> 속성일 때의 결과입니다.
<br /></p>
<p>이제 flex-direction 속성을 다른 것들로 하나씩 바꿔보도록 하겠습니다.
<br /></p>
<pre><code>.container {
  display: flex;
  /* row = 행, column = 열 */
  flex-direction: row-reverse;
}</code></pre><img src="https://velog.velcdn.com/images/choco_dev/post/592fecf2-f410-47e1-a377-856d4d76306f/image.png" width="80%" />

<p><strong>flex-direction: row-reverse</strong> 속성으로 바꿨더니, 요소가 오른쪽부터 반대 방향으로 나열됩니다.
<br /></p>
<pre><code>.container {
  display: flex;
  /* row = 행, column = 열 */
  flex-direction: column;
}</code></pre><img src="https://velog.velcdn.com/images/choco_dev/post/c3ec5a31-58ae-4637-a063-8e891a1d2b28/image.png" width="60%" />

<p><strong>flex-direction: column</strong> 속성은 교차축 방향으로 요소들이 나열됩니다.
<br /></p>
<pre><code>.container {
  display: flex;
  /* row = 행, column = 열 */
  flex-direction: column-reverse;
}</code></pre><img src="https://velog.velcdn.com/images/choco_dev/post/655fc1d6-81a7-4ba1-acd4-422f07aa60cf/image.png" width="60%" />

<p><strong>flex-direction: column-reverse</strong> 속성으로 바꾸니, 기존의 요소들이 거꾸로 나열되는 것을 확인할 수 있습니다.</p>