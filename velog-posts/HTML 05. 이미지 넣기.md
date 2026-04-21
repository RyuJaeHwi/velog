<h2 id="img-태그">img 태그</h2>
<blockquote>
<p><strong>img 태그란?</strong>
: .html 문서에서 이미지를 표시할 때 사용하는 단일 태그</p>
</blockquote>
<p>.html 문서에서는 이미지를 넣을 때도 태그를 사용합니다.</p>
<p>img 태그는 단일 태그로 콘텐츠를 적지 않는 대신, 해당 태그의 속성에 삽입하려는 이미지에 대한 정보를 주어야 합니다.
<br />
img 태그의 기본 형태는 다음과 같습니다.</p>
<pre><code>&lt;img src=&quot;삽입할 이미지 URL&quot; alt=&quot;이미지 설명&quot; /&gt;</code></pre><p><br />여기에 추가로 width, height 등의 너비와 높이 옵션도 추가하여 이미지의 크기와 높낮이를 조절할 수 있습니다.</p>
<pre><code>&lt;img src=&quot;삽입할 이미지 URL&quot; alt=&quot;이미지 설명&quot; width=&quot;너비값 height=&quot;높이값&quot; /&gt;</code></pre><p>여기서, 너비와 높이는 각각 픽셀(px) 단위입니다!</p>
<br />

<p><em><strong>이미지 넣기 예시</strong></em></p>
<pre><code>&lt;!doctype html&gt;
&lt;html lang=&quot;en&quot;&gt;
  &lt;head&gt;
    &lt;meta charset=&quot;UTF-8&quot; /&gt;
    &lt;meta name=&quot;viewport&quot; content=&quot;width=device-width, initial-scale=1.0&quot; /&gt;
    &lt;title&gt;이미지 표시&lt;/title&gt;
  &lt;/head&gt;
  &lt;body&gt;
    &lt;h2&gt;웹 브라우저에 이미지 표시하기&lt;/h2&gt;
    &lt;p&gt;width = 너비, height = 높이&lt;/p&gt;
    &lt;br /&gt;
    &lt;img src=&quot;test.png&quot; alt=&quot;인트로&quot; width=&quot;450&quot; height=&quot;150&quot; /&gt;
  &lt;/body&gt;
&lt;/html&gt;</code></pre><br />
img 태그에 지정한 크기대로 이미지가 나타나는 것을 알 수 있습니다.

<img src="https://velog.velcdn.com/images/choco_dev/post/94e16e7e-ddd1-4237-91e0-4c3097d41247/image.png" width="80%" />

<br />
<p style="color: gray; font-size: 18px; font-style: italic;">
+ alt 속성은 왜 쓸까?
</p>
<p style="color: gray; font-size: 16px; font-style: italic;">
alt는 alternative의 약자로, 대체 텍스트 역할을 합니다. 
이미지가 로딩되기 전이나 로딩이 실패한 경우, 이미지 대신에 보여줄 텍스트가 alt 속성입니다.<br />
alt를 사용하면 이미지를 볼 수 없는 시각장애인에게 웹페이지 서비스 소개 시 대비가 가능합니다. (음성인식기가 이미지 대신 alt 설명 활용)
</p>
<br />