<h2 id="input-태그">input 태그</h2>
<blockquote>
<p><strong>input 태그란?</strong>
: 사용자로부터 데이터를 입력받기 위한 대화형 컨트롤 콘텐츠를 만들 수 있는 단일 태그 (인라인 요소)</p>
</blockquote>
<p>type의 속성값이 무엇인지에 따라 입력 요소의 형태나 입력하는 데이터의 유형이 달라집니다.</p>
<p>type 외에도 여러 가지 속성을 통해 세부적인 조절이 가능합니다.
<br /></p>
<pre><code>&lt;input type=&quot;text&quot; name=&quot;nickname&quot; /&gt;
&lt;input type=&quot;text&quot; name=&quot;job&quot; /&gt;</code></pre><p>이 코드는</p>
<input name="nickname" type="text" />
<input name="job" type="text" />

<p>이런 식으로 input 입력칸을 만듭니다. 지정한 name 속성에 따라 알맞은 것들을 입력하면 됩니다.</p>
<p style="color: gray; font-size: 16px;">
ex) 왼쪽은 닉네임, 오른쪽은 직업...
</p>

<br />

<p>이제 직접 여러 입력 요소들을 코드를 통해 구현해보도록 하겠습니다!
<br />
<br /></p>
<p><strong><em>입력 요소 구현 예시</em></strong></p>
<pre><code>&lt;!doctype html&gt;
&lt;html lang=&quot;en&quot;&gt;
  &lt;head&gt;
    &lt;meta charset=&quot;UTF-8&quot; /&gt;
    &lt;meta name=&quot;viewport&quot; content=&quot;width=device-width, initial-scale=1.0&quot; /&gt;
    &lt;title&gt;여러 입력(input) 요소 만들기&lt;/title&gt;
  &lt;/head&gt;
  &lt;body&gt;
    &lt;input type=&quot;text&quot; placeholder=&quot;메시지 입력&quot; maxlength=&quot;5&quot; /&gt;
  &lt;/body&gt;
&lt;/html&gt;
</code></pre><img src="https://velog.velcdn.com/images/choco_dev/post/5df644bf-6fac-4928-8a9e-1fdcb3e71c42/image.png" width="60%" />

<p>여기서 input 내부의 속성들이 무엇인지 각각 알아보도록 하겠습니다.
<br /></p>
<p>먼저 <strong>type</strong>은 input이 어떤 컨트롤 기능을 갖고 있는지를 제공해주는 속성입니다. 해당 속성을 따로 지정하지 않으면 기본값으로 &quot;text&quot;가 지정됩니다.</p>
<p>이 <strong>type</strong>에는 정말 다양한 종류가 있으며, 이는 아래에 다른 예제로 더 알아보도록 하겠습니다!
<br /></p>
<p>그리고 <strong>placeholder</strong>는 값을 입력하기 전, 컨트롤 부분에 표시되는 연한 회색 안내 텍스트를 뜻합니다. 이를 통해 사용자는 어떤 내용을 적어야 하는지 도움을 받을 수 있습니다.
<br /></p>
<p><strong>maxlength</strong>는 사용자가 입력할 수 있는 최대 문자 수(Maximum length)를 제한하는 속성입니다. 위 예제에서는 5이니, 최대 5글자까지 입력 가능합니다.
<br />
<br /></p>
<p>가장 기본인 값을 입력하는 input에 대해 알아봤으니, 이제 다른 종류의input들도 예제를 통해 직접 구현해보겠습니다!
<br /></p>
<p><em><strong>입력 요소 구현 예시2</strong></em></p>
<pre><code>&lt;!doctype html&gt;
&lt;html lang=&quot;en&quot;&gt;
  &lt;head&gt;
    &lt;meta charset=&quot;UTF-8&quot; /&gt;
    &lt;meta name=&quot;viewport&quot; content=&quot;width=device-width, initial-scale=1.0&quot; /&gt;
    &lt;title&gt;여러 입력(input) 요소 만들기&lt;/title&gt;
  &lt;/head&gt;
  &lt;body&gt;
    &lt;input type=&quot;button&quot; value=&quot;PUSH&quot; /&gt;
    &lt;br /&gt;&lt;br /&gt;
    &lt;input type=&quot;color&quot; /&gt; &amp;nbsp;색상 선택 &lt;br /&gt;&lt;br /&gt;
    &lt;input type=&quot;range&quot; max=&quot;100&quot; min=&quot;0&quot; /&gt; &amp;nbsp;값 범위 선택 &lt;br /&gt;&lt;br /&gt;
    &lt;input type=&quot;date&quot; /&gt; &amp;nbsp;날짜 선택 &lt;br /&gt;&lt;br /&gt;
  &lt;/body&gt;
&lt;/html&gt;</code></pre><img src="https://velog.velcdn.com/images/choco_dev/post/8e60604f-02c5-42c7-be58-c334e5599ca9/image.png" width="60%" />
순서대로 클릭 버튼, 색상 선택, 값 범위 선택, 날짜 선택 input 입니다. 먼저 맨 위 push라 써져있는 것은 클릭 버튼으로, type="button" 지정 시 사용 가능합니다.<br />
<br />

<img src="https://velog.velcdn.com/images/choco_dev/post/5a4865a6-c668-4ebe-a6cc-c8ee7c42de38/image.png" width="60%" />
type="color"로 지정하면 해당 input은 색상을 선택하는 콘텐츠로 구현됩니다. 이미지처럼 버튼 클릭 시, 원하는 색상을 선택하도록 표가 나타납니다.
<br /><br />

<img src="https://velog.velcdn.com/images/choco_dev/post/5189d55f-f0f5-4f62-9c9a-156bc2695886/image.png" width="70%" />
type="range"는 값을 특정 범위 안에서 선택할 수 있는 input을 생성합니다.

<p>max와 min 속성을 추가하여 최대 ~ 최소 범위를 지정할 수 있습니다.
<br /></p>
<p>그리고 type=&quot;date&quot;는 원하는 날짜를 캘린더에서 직접 선택할 수 있는 input을 생성합니다.</p>