<h2 id="padding-과-margin">padding 과 margin</h2>
<p>padding과 margin이 정확히 어떤 영역의 공백을 뜻하는지는 아래 이미지를 보면 쉽게 이해할 수 있습니다.</p>
<p align="center">
<img src="https://velog.velcdn.com/images/choco_dev/post/1d42fbf3-2c19-4b53-8a3d-7782b23b2745/image.png" width="60%" />
</p>

<p>테두리 선인 border를 기준으로 안쪽에 있는 여백을 <strong>padding</strong>, 바깥쪽에 있는 여백을 <strong>margin</strong>이라고 합니다.
<br /></p>
<p>이러한 여백은 둘 padding과 margin 둘 다 상하좌우 네 개의 면에 전부 존재하는 영역입니다.</p>
<p>그런데 이 여백을 어느 부분에는 적용하고, 어디는 아예 없애고 싶은데 어떻게 할 수 있을까요?
<br /></p>
<p>아래 두 개의 방법을 사용하면 각각 여백을 주는 것이 가능합니다.
<br /></p>
<ul>
<li>하위 속성 정의</li>
<li>여러 값을 한 번에 정의</li>
</ul>
<br />

<h3 id="하위-속성-정의">하위 속성 정의</h3>
<p>padding과 margin 모두 상하좌우 여백을 정의할 수 있는 개별 속성이 있습니다.</p>
<p>각 속성 옆에 top, bottom, left, right를 붙이면 해당하는 방향에만 여백을 주는 것이 가능합니다.</p>
<p align="center">
<img src="https://velog.velcdn.com/images/choco_dev/post/9c2ddb3b-f8c1-4e4d-92be-6971c09673ca/image.png" width="60%" />
</p>

<p>아래 예시를 통해 직접 보도록 하겠습니다.
<br /></p>
<p><strong><em>상하좌우 여백값 예시</em></strong></p>
<pre><code>&lt;!doctype html&gt;
&lt;html lang=&quot;en&quot;&gt;
  &lt;head&gt;
    &lt;meta charset=&quot;UTF-8&quot; /&gt;
    &lt;meta name=&quot;viewport&quot; content=&quot;width=device-width, initial-scale=1.0&quot; /&gt;
    &lt;title&gt;box model&lt;/title&gt;
    &lt;style&gt;
      div {
        width: 100px;
        height: 100px;
        border: 5px solid darkmagenta;
        /* 상하좌우 padding 값 각각 설정 가능 */
        padding-top: 10px;
        padding-right: 40px;
        padding-bottom: 10px;
        padding-left: 20px;
        /* 상하좌우 margin 값 각각 설정 가능 */
        margin-top: 20px;
        margin-right: 10px;
        margin-bottom: 30px;
        margin-left: 40px;
      }
    &lt;/style&gt;
  &lt;/head&gt;
  &lt;body&gt;
    &lt;div&gt;&lt;/div&gt;
  &lt;/body&gt;
&lt;/html&gt;</code></pre><img src="https://velog.velcdn.com/images/choco_dev/post/5def3ec5-aaec-4a00-97c7-b04f3dc5af98/image.png" width="60%" />

<p>안쪽 초록 부분이 padding 값이고, border의 바깥 주황 부분이 margin 값 입니다.</p>
<p>상하좌우 각 부분마다 padding과 margin 값이 각각 지정된 것을 확인할 수 있습니다.</p>
<br />


<h3 id="여러-값을-한-번에-정의">여러 값을 한 번에 정의</h3>
<p>padding과 margin은 위처럼 각각 접미사를 붙여 여백을 부여할 수도 있지만, 더 간편하게 하는 방법이 있습니다.</p>
<p>네 면의 여백에 대한 <strong>단축 속성</strong>으로 작성하면 매우 짧은 코드로 여백을 부여할 수 있습니다.
<br /></p>
<p>ex)</p>
<pre><code>span{
  margin: 10px 20px 30px 40px;
}</code></pre><p>이 예시 코드에서 왼쪽부터 순서대로 <em><strong>top, right, bottom, left</strong></em> 입니다.
<br /></p>
<p>아래 예시를 통해 직접 보도록 하겠습니다.
<br /></p>
<p><strong><em>상하좌우 여백값 예시2</em></strong></p>
<pre><code>&lt;!doctype html&gt;
&lt;html lang=&quot;en&quot;&gt;
  &lt;head&gt;
    &lt;meta charset=&quot;UTF-8&quot; /&gt;
    &lt;meta name=&quot;viewport&quot; content=&quot;width=device-width, initial-scale=1.0&quot; /&gt;
    &lt;title&gt;box model&lt;/title&gt;
    &lt;style&gt;
      div {
        width: 100px;
        height: 100px;
        border: 5px solid darkmagenta;
        /* 한 번에 상하좌우 padding 값 설정 가능 */
        padding: 10px 10px 20px 30px;
        /* 한 번에 상하좌우 margin 값 설정 가능 */
        margin: 50px 30px 10px 40px;
      }
    &lt;/style&gt;
  &lt;/head&gt;
  &lt;body&gt;
    &lt;div&gt;&lt;/div&gt;
  &lt;/body&gt;
&lt;/html&gt;</code></pre><img src="https://velog.velcdn.com/images/choco_dev/post/9abbda94-a674-4974-9824-c33ba0b2e00d/image.png" width="60%" />

<p>padding과 margin 둘 다 한 번에 값을 설정했습니다.</p>
<p>둘 다 순서대로 top, right, bottom, left 입니다.
<br /></p>
<p>그런데 한 번에 값을 줄 때, 저것보다 더 축약할 수도 있습니다.
<br /></p>
<p><strong><em>상하좌우 여백값 예시3</em></strong></p>
<pre><code>&lt;!doctype html&gt;
&lt;html lang=&quot;en&quot;&gt;
  &lt;head&gt;
    &lt;meta charset=&quot;UTF-8&quot; /&gt;
    &lt;meta name=&quot;viewport&quot; content=&quot;width=device-width, initial-scale=1.0&quot; /&gt;
    &lt;title&gt;box model&lt;/title&gt;
    &lt;style&gt;
      div {
        width: 100px;
        height: 100px;
        border: 5px solid darkmagenta;

        /* 아래와 같은 경우는 상 좌우 하 */
        padding: 10px 60px 40px;
        margin: 20px 40px 20px;
      }
    &lt;/style&gt;
  &lt;/head&gt;
  &lt;body&gt;
    &lt;div&gt;&lt;/div&gt;
  &lt;/body&gt;
&lt;/html&gt;</code></pre><img src="https://velog.velcdn.com/images/choco_dev/post/5e43a9d0-8c3d-4472-8193-5dcd560ca32c/image.png" width="60%" />

<p>위처럼 딱 세 개의 값만 적용한 경우엔 순서대로 <strong>top, left &amp; right, bottom</strong> 순서로 여백이 적용됩니다.</p>
<p>더 줄일 수도 있습니다. 아래 예시처럼 입력하면 <strong>top &amp; bottom, left &amp; right</strong> 순서로 여백이 적용됩니다.
<br /></p>
<p>ex)</p>
<pre><code>/* 아래와 같은 경우는 상하 좌우 */
margin: 60px 20px;</code></pre><br />

<p>이렇게 개발자 마음대로 편리하게 단축하여 값을 넣을 수 있습니다!</p>