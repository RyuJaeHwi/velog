<h2 id="select-태그">select 태그</h2>
<blockquote>
<p><strong>&lt;select&gt; ~ &lt;/select&gt; 태그란?</strong>
: 여러 옵션(선택지)들을 제공해주는 컨트롤 생성 태그</p>
</blockquote>
<p>select 태그를 사용하면 여러 선택지 중 하나를 고를 수 있는 메뉴 형식의 콘텐츠가 만들어집니다. 간단히 말하면 <strong>&quot;드롭다운&quot;</strong>을 만들어줍니다.</p>
<p>이때 &lt;select&gt; ~ &lt;/select&gt; 태그 안의 각 선택지들은 option 태그를 사용합니다.
<br /></p>
<p>select 태그도 각 요소마다 name을 지정할 수 있습니다.</p>
<pre><code>&lt;select name=&quot;dessert&quot; multiple&gt;
  &lt;option value=&quot;jelly&quot;&gt;젤리&lt;/option&gt;
  &lt;option value=&quot;cookie&quot;&gt;쿠키&lt;/option&gt;
&lt;/select&gt;</code></pre><p>이 코드를 보면 select 태그 안에 name 속성을 넣어서 어떤 옵션들이 있는지 안내합니다.</p>
<p>또한 각각의 option마다 value 속성을 지정할 수 있습니다. 여기서 value는 실제로 처리될 값을 뜻합니다.
<br /></p>
<p>이제 직접 예시를 통해 알아보도록 하겠습니다.
<br /><br /></p>
<p><em><strong>select 태그 예시</strong></em></p>
<pre><code>&lt;!doctype html&gt;
&lt;html lang=&quot;en&quot;&gt;
  &lt;head&gt;
    &lt;meta charset=&quot;UTF-8&quot; /&gt;
    &lt;meta name=&quot;viewport&quot; content=&quot;width=device-width, initial-scale=1.0&quot; /&gt;
    &lt;title&gt;select ~ textarea&lt;/title&gt;
  &lt;/head&gt;
  &lt;body&gt;
    &lt;h1&gt;먹고 싶은 간식 선택&lt;/h1&gt;
    &lt;select name=&quot;dessert&quot;&gt;
      &lt;option value=&quot;candy&quot;&gt;사탕&lt;/option&gt;
      &lt;option value=&quot;chocolate&quot;&gt;초콜릿&lt;/option&gt;
      &lt;option value=&quot;jelly&quot;&gt;젤리&lt;/option&gt;
      &lt;option value=&quot;cookie&quot;&gt;쿠키&lt;/option&gt;
    &lt;/select&gt;
  &lt;/body&gt;
&lt;/html&gt;</code></pre><br />

<img src="https://velog.velcdn.com/images/choco_dev/post/2eae61b3-ab46-43cc-af0a-436fe3cd478e/image.png" width="60%" />
<img src="https://velog.velcdn.com/images/choco_dev/post/03311fdc-d82d-48b5-8fc5-b5381372e61e/image.png" width="60%" />

<p>결과를 보면 해당 드롭다운을 클릭해야 아래로 선택지들이 펼쳐지는 것을 확인할 수 있습니다.</p>
<p>그러면 이러한 것도 속성을 통해 조정하려면 어떻게 해야할까요?
<br /></p>
<img src="https://velog.velcdn.com/images/choco_dev/post/92d098ff-df40-41b2-bc34-37b5d81c02d5/image.png" width="60%" />

<p>select 태그에 <strong>&quot;multiple&quot;</strong> 속성을 넣으면 됩니다! 해당 속성은 드롭다운 클릭을 하지 않아도 처음부터 전체 선택지가 펼쳐지도록 해줍니다.
<br /><br /></p>
<img src="https://velog.velcdn.com/images/choco_dev/post/ff699fb8-5ccd-4457-a847-6ed05ff005ed/image.png" width="60%" />

<p>그리고 <strong>&quot;multiple&quot;</strong>속성이 있는 경우엔 Ctrl 키를 누르면서 클릭하면 다중 선택이 가능합니다.
<br /><br /></p>
<p>추가로 select 태그 안의 option 태그도 <strong>&quot;selected&quot;</strong>라는 속성이 있습니다. 이 속성은 이미 해당 option 태그의 값이 선택되어 있도록 해주는 속성입니다.
<br /></p>
<pre><code>&lt;option value=&quot;candy&quot;&gt;사탕&lt;/option&gt;
&lt;option value=&quot;chocolate&quot; selected&gt;초콜릿&lt;/option&gt;
&lt;option value=&quot;jelly&quot;&gt;젤리&lt;/option&gt;</code></pre><p>이렇게 특정 option 태그에 추가하면, 해당 option의 선택지는 이미 선택되어 있는 것으로 나타납니다.</p>
<img src="https://velog.velcdn.com/images/choco_dev/post/b0556fb7-bdfd-4b24-8d95-90aa4df0d6a3/image.png" width="60%" />

<p>결과를 보면 <strong>&quot;selected&quot;</strong> 속성이 있는 &quot;초콜릿&quot; 선택지만 먼저 선택되어 있는 것을 알 수 있습니다!</p>
<br />

<h2 id="textarea">textarea</h2>
<blockquote>
<p><strong>textarea란?</strong>
: 여러 줄의 텍스트를 입력할 수 있게 해주는 입력 요소 태그</p>
</blockquote>
<p>여기서 textarea랑 input의 입력이 무슨 차이인지 헷갈릴 수 있는데, input 태그는 한 줄밖에 쓸 수 없지만 textarea는 여러 줄의 텍스트를 입력할 수 있습니다.</p>
<p>그리고 textarea에서 초기값을 지정하려면 직접 해당 태그 안에 콘텐츠로 입력합니다.
<br /></p>
<p><em><strong>textarea 사용 예시</strong></em></p>
<pre><code>&lt;!doctype html&gt;
&lt;html lang=&quot;en&quot;&gt;
  &lt;head&gt;
    &lt;meta charset=&quot;UTF-8&quot; /&gt;
    &lt;meta name=&quot;viewport&quot; content=&quot;width=device-width, initial-scale=1.0&quot; /&gt;
    &lt;title&gt;select ~ textarea&lt;/title&gt;
  &lt;/head&gt;
  &lt;body&gt;
    &lt;h1&gt;textarea&lt;/h1&gt;
    &lt;textarea name=&quot;content&quot; rows=&quot;10&quot; cols=&quot;30&quot;&gt;기본적으로 쓰여 있는 텍스트&lt;/textarea&gt;
  &lt;/body&gt;
&lt;/html&gt;</code></pre><img src="https://velog.velcdn.com/images/choco_dev/post/e13ac8bf-e182-4dda-8473-2d1c12b446ac/image.png" width="70%" />

<p>여기서 textarea 또한 select와 똑같이 name 속성을 추가하여 구별할 수 있다는 걸 알 수 있습니다.
<br /><br /></p>
<img src="https://velog.velcdn.com/images/choco_dev/post/e0996d1a-c192-4d1f-92ea-eb98b0ec7bec/image.png" width="70%" />

<p><strong>rows</strong>와 <strong>cols</strong>들은 각각 입력창의 가로와 세로 크기를 지정할 수 있는 옵션들입니다.</p>
<p>위 예제에서 cols=&quot;30&quot;라고 했으니, 평균적인 글자 크기를 기준으로 약 30글자가 들어갈 정도의 너비로 만들어집니다.</p>
<p>그리고 rows=&quot;10&quot;이라고 했으니, 한 번에 10줄의 텍스트가 보일 정도의 높이로 만들어집니다.</p>