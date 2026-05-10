<h2 id="박스-모델-box-model-이란">박스 모델 (Box-Model) 이란?</h2>
<p>브라우저가 요소를 렌더링할 때, 각각의 요소는 보통 사각형 형태로 영역을 차지합니다. 이 영역을 <strong>&quot;박스&quot;</strong>라고 합니다.</p>
<p>CSS는 이러한 박스들의 크기, 위치, 속성(색, 배경, 테두리 등)을 결정합니다.
<br /></p>
<p>아래는 박스가 가지는 영역 4가지와, 해당 영역의 크기를 정의하는 속성입니다.</p>
<ul>
<li>콘텐츠 영역 : <strong>width, height</strong></li>
<li>안쪽 여백 : <strong>padding</strong></li>
<li>경계선 (테두리) : <strong>border-width</strong></li>
<li>바깥쪽 여백 : <strong>margin</strong></li>
</ul>
<br />

<p>이미지로 정리하면 다음과 같습니다.</p>
<p align="center">
<img src="https://velog.velcdn.com/images/choco_dev/post/1fd04325-803d-4341-9e71-1248df0eee28/image.png" width="80%" />
</p>
<br />

<p><strong><em>box-model 요소 확인 예시</em></strong></p>
<pre><code>&lt;!doctype html&gt;
&lt;html lang=&quot;en&quot;&gt;
  &lt;head&gt;
    &lt;meta charset=&quot;UTF-8&quot; /&gt;
    &lt;meta name=&quot;viewport&quot; content=&quot;width=device-width, initial-scale=1.0&quot; /&gt;
    &lt;title&gt;box model&lt;/title&gt;
    &lt;style&gt;
      div {
        border: 5px solid blueviolet;
        padding: 20px;
        margin: 20px;
        width: 150px;
        height: 50px;
      }
    &lt;/style&gt;
  &lt;/head&gt;
  &lt;body&gt;
    &lt;div&gt;요소의 콘텐츠 - box&lt;/div&gt;
  &lt;/body&gt;
&lt;/html&gt;</code></pre><img src="https://velog.velcdn.com/images/choco_dev/post/3c5b87fb-8c62-4686-95b5-711dd6986b23/image.png" width="60%" />

<p>하나씩 살펴보도록 하겠습니다.
<br /></p>
<p>우선 border입니다. 저번 글에서 배웠던 것인데, 5px 두께의 실선 테두리를 추가하였습니다.</p>
<p>이 border를 기준으로 안쪽 여백, 바깥쪽 여백을 구분할 수 있습니다.
<br /></p>
<img src="https://velog.velcdn.com/images/choco_dev/post/bd8124a8-8cec-410b-9523-2fe342eae4a6/image.png" width="60%" />

<p>위 이미지에서 초록 부분이 안쪽 여백인 padding, 주황색 부분이 바깥쪽 여백인 margin입니다. 그 사이 보라색이 border이고 이것으로 구분합니다.</p>
<p>가장 내부 파란 부분은 콘텐츠 영역이에요.</p>
<p>코드에서 준 값인 padding=20px, margin=20px이 잘 적용되었고 콘텐츠 영역도 150px * 50px 크기로 이루어진 것을 볼 수 있습니다.
<br /></p>
<p>다른 것도 확인해보도록 하겠습니다.
<br />
<br /></p>
<p><strong><em>box-model 요소 확인 예시2</em></strong></p>
<pre><code>&lt;!doctype html&gt;
&lt;html lang=&quot;en&quot;&gt;
  &lt;head&gt;
    &lt;meta charset=&quot;UTF-8&quot; /&gt;
    &lt;meta name=&quot;viewport&quot; content=&quot;width=device-width, initial-scale=1.0&quot; /&gt;
    &lt;title&gt;box model&lt;/title&gt;
    &lt;style&gt;
      span {
        width: 100px;
        height: 60px;
      }
    &lt;/style&gt;
  &lt;/head&gt;
  &lt;body&gt;
    &lt;span&gt;영역 check&lt;/span&gt;
  &lt;/body&gt;
&lt;/html&gt;
</code></pre><img src="https://velog.velcdn.com/images/choco_dev/post/6424c515-e6d7-4474-9627-d89e4e3a7f04/image.png" width="60%" />

<p>style 태그로 span 영역에 width와 height를 넣었는데 적용이 안 됩니다. 왜 그럴까요?
<br /></p>
<p>span 같은 인라인 요소는 width와 height 값 지정이 안됩니다. 이미 해당 요소가 사용하는 만큼의 영역만 차지하기 때문인데, 그럼 어떻게 지정할 수 있을까요?</p>
<p>저번에 공부했던 display의 inline-block 옵션을 추가하면 됩니다!
<br />
<br /></p>
<p><strong><em>box-model 요소 확인 예시3</em></strong></p>
<pre><code>&lt;!doctype html&gt;
&lt;html lang=&quot;en&quot;&gt;
  &lt;head&gt;
    &lt;meta charset=&quot;UTF-8&quot; /&gt;
    &lt;meta name=&quot;viewport&quot; content=&quot;width=device-width, initial-scale=1.0&quot; /&gt;
    &lt;title&gt;box model&lt;/title&gt;
    &lt;style&gt;
      span {
        display: inline-block;
        width: 100px;
        height: 60px;
      }
    &lt;/style&gt;
  &lt;/head&gt;
  &lt;body&gt;
    &lt;span&gt;영역 check&lt;/span&gt;
  &lt;/body&gt;
&lt;/html&gt;
</code></pre><img src="https://velog.velcdn.com/images/choco_dev/post/c737fa56-c1de-46e1-a1c5-5c6bd380bd0a/image.png" width="60%" />

<p>inline-block을 추가하였더니 span에도 width랑 height 값이 적용되는 것을 확인할 수 있습니다.</p>