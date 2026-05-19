<h2 id="background">background</h2>
<p><strong>배경(background)</strong>은 콘텐츠의 배경을 정의합니다.</p>
<p>단축 속성이며 색상, 이미지, 반복 등 다양한 하위 속성을 추가할 수 있습니다.
아래 표는 배경의 하위 속성 중 일부입니다.
<br /></p>
<table>
<thead>
<tr>
<th align="center">하위 속성</th>
<th>역할</th>
</tr>
</thead>
<tbody><tr>
<td align="center">background-color</td>
<td>배경 색상 정의</td>
</tr>
<tr>
<td align="center">background-image</td>
<td>배경 이미지 정의</td>
</tr>
<tr>
<td align="center">background-position</td>
<td>배경 이미지의 초기 위치 정의</td>
</tr>
<tr>
<td align="center">background-size</td>
<td>배경 이미지의 크기 정의</td>
</tr>
<tr>
<td align="center">background-repeat</td>
<td>배경 이미지의 반복 방법 정의&amp;nbsp&amp;nbsp&amp;nbsp</td>
</tr>
</tbody></table>
<br />
<br />

<p><em><strong>background 사용 예시</strong></em></p>
<pre><code>&lt;!doctype html&gt;
&lt;html lang=&quot;en&quot;&gt;
  &lt;head&gt;
    &lt;meta charset=&quot;UTF-8&quot; /&gt;
    &lt;meta name=&quot;viewport&quot; content=&quot;width=device-width, initial-scale=1.0&quot; /&gt;
    &lt;title&gt;background&lt;/title&gt;
    &lt;style&gt;
      div {
        box-sizing: border-box;
        width: 400px;
        height: 300px;
        border: 2px solid maroon;
      }
      .github {
        background-color: blanchedalmond;
        background-image: url(../githublogo.png);
      }
    &lt;/style&gt;
  &lt;/head&gt;
  &lt;body&gt;
    &lt;div class=&quot;github&quot;&gt;깃허브&lt;/div&gt;
  &lt;/body&gt;
&lt;/html&gt;</code></pre><img src="https://velog.velcdn.com/images/choco_dev/post/0c3bbddd-7a92-4b67-b63c-14760ad4669f/image.png" width="70%" />

<p>깃허브 아이콘을 이미지로 해서 400px * 300px 크기의 div안에 넣었습니다.</p>
<p>그러나 이미지의 기본 크기가 매우 커서 div 안에 다 담기지 않는 모습입니다. 이는 어떻게 해결해야 할까요?
<br /></p>
<p>속성으로 <strong>background-size: cover;</strong>을 추가했습니다. 이 속성은 이미지가 찌그러지지 않는 내에서 최대 사이즈로 들어갈 수 있도록 자동으로 맞춰줍니다.
<br /></p>
<pre><code>.github {
  background-color: blanchedalmond;
  background-image: url(../githublogo.png);
  background-size: cover;
}</code></pre><img src="https://velog.velcdn.com/images/choco_dev/post/b3c53e74-8cf9-4f0b-a555-8892dcfe9bcb/image.png" width="70%" />

<p>이미지가 조금 짤렸지만, 위에서 설정한 400px * 300px 크기에 최대한 맞도록 이미지가 들어간 것을 알 수 있습니다.</p>
<p>cover는 이렇게 짤리는 것을 감안하고 빈 공간 없이 이미지를 채웁니다.
<br /><br /></p>
<p>cover와는 다른 속성도 있습니다. contain인데, 이는 이미지가 잘리지 않고 원본 그대로 나올 수 있는 최대 크기를 맞춰서 보여줍니다.
<br /></p>
<pre><code>.github {
  background-color: blanchedalmond;
  background-image: url(../githublogo.png);
  background-size: contain;
}</code></pre><img src="https://velog.velcdn.com/images/choco_dev/post/3367b7d6-f52f-4509-9887-5a9ceeb0af2f/image.png" width="70%" />

<br />

<p>그런데 같은 이미지가 반복되어 들어가다가 잘리니 조금 지저분한 것처럼 보일 수 있습니다.</p>
<p>이러한 이미지의 반복을 없애려면 어떻게 해야할까요?
<br /></p>
<p><strong>background-repeat: no-repeat;</strong> 속성을 추가하면 됩니다.</p>
<p>기본적으로 반복을 하는 repeat가 기본값이며, no-repeat을 넣으면 이미지가 반복되지 않습니다.
<br /></p>
<pre><code>.github {
  background-color: blanchedalmond;
  background-image: url(../githublogo.png);
  background-size: contain;
  background-repeat: no-repeat;
}</code></pre><img src="https://velog.velcdn.com/images/choco_dev/post/6c5004bf-9b0b-481b-bb23-540fc8f6d532/image.png" width="70%" />

<p>이미지가 반복되지 않고 한 번만 들어가며, 나머진 여백으로 처리되는 것을 확인할 수 있습니다.
<br /></p>
<p>이제 이미지 사이즈와 위치를 마음대로 커스텀하도록 하겠습니다.</p>
<p>각각 background-size와 background-position을 사용하면 됩니다.
<br /></p>
<pre><code>.github {
  background-color: blanchedalmond;
  background-image: url(../githublogo.png);
  background-size: 200px 100px;
  background-position: right bottom;
  background-repeat: no-repeat;
}</code></pre><img src="https://velog.velcdn.com/images/choco_dev/post/56ad5336-d63c-4956-9325-9fe174545253/image.png" width="70%" />

<p>200px * 100px 크기로 이미지가 맞춰져서 찌그러진 채로 들어갑니다.</p>
<p>위치도 오른쪽 아래로 알맞게 배치된 것을 알 수 있습니다.</p>