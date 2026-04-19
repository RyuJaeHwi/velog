<h2 id="태그의-구분">태그의 구분</h2>
<h3 id="블록-요소-vs-인라인-요소">블록 요소 vs 인라인 요소</h3>
<blockquote>
<p><strong>블록 레벨 요소</strong>
: 자신이 속한 영역의 너비를 모두 차지하여 블록 형성 <br />
<strong>인라인 요소</strong>
: 자신에게 필요한 만큼, 즉 실제로 사용하는 공간만 차지</p>
</blockquote>
<br />

<p><em><strong>블록 요소 &amp; 인라인 요소 영역 구분 예시</strong></em></p>
<pre><code>&lt;!doctype html&gt;
&lt;html lang=&quot;en&quot;&gt;
  &lt;head&gt;
    &lt;meta charset=&quot;UTF-8&quot; /&gt;
    &lt;meta name=&quot;viewport&quot; content=&quot;width=device-width, initial-scale=1.0&quot; /&gt;
    &lt;title&gt;태그의 구분&lt;/title&gt;
  &lt;/head&gt;
  &lt;body&gt;
    &lt;h2&gt;블록 요소&lt;/h2&gt;
    &lt;br /&gt;
    &lt;p&gt;블록 요소가 차지하는 영역의 크기를 테스트 중입니다.&lt;/p&gt;

    &lt;br /&gt;
    &lt;hr /&gt;
    &lt;br /&gt;

    &lt;h2&gt;인라인 요소&lt;/h2&gt;
    &lt;br /&gt;
    &lt;p&gt;인라인 요소가 차지하는 &lt;span&gt;영역의 크기&lt;/span&gt;를 테스트 중입니다.&lt;/p&gt;
  &lt;/body&gt;
&lt;/html&gt;</code></pre><p>이 코드를 실행하고 개발자 모드(F12)를 통해 각 요소의 영역을 확인해봅시다.</p>
<img src="https://velog.velcdn.com/images/choco_dev/post/01c4f532-7888-4b8a-929d-2cf1264e7648/image.png" width="80%" />
블록 요소인 p 태그는 문장이 끝났어도 해당 영역 전체를 차지합니다.
<br />
<br />

<img src="https://velog.velcdn.com/images/choco_dev/post/7482b412-5e3e-4170-a6e8-ba7f523d9378/image.png" width="80%" />
인라인 요소인 span 태그는 해당하는 텍스트의 영역만 차지합니다.

<p>span 태그는 해당 태그 자체로는 의미가 없습니다. 특정 영역에만 속성값을 추가하려 할 때 사용하는 인라인 태그라고 알고 있으시면 됩니다.
<br /></p>
<h3 id="인라인-요소에-여러-텍스트-효과-넣기">인라인 요소에 여러 텍스트 효과 넣기</h3>
<blockquote>
<p><strong>&lt;strong&gt; 태그</strong> : 텍스트의 두께를 굵게 바꿔주는 태그
<strong>&lt;em&gt; 태그</strong> : 텍스트를 기울어진 이탤릭체로 바꿔주는 태그
<strong>&lt;mark&gt; 태그</strong> : 텍스트에 형관펜 밑줄 효과를 추가하는 태그</p>
</blockquote>
<br />

<p><em><strong>텍스트 효과 예시</strong></em></p>
<pre><code>&lt;!doctype html&gt;
&lt;html lang=&quot;en&quot;&gt;
  &lt;head&gt;
    &lt;meta charset=&quot;UTF-8&quot; /&gt;
    &lt;meta name=&quot;viewport&quot; content=&quot;width=device-width, initial-scale=1.0&quot; /&gt;
    &lt;title&gt;태그의 구분&lt;/title&gt;
  &lt;/head&gt;
  &lt;body&gt;
    &lt;h2&gt;인라인 요소를 통해 여러 속성 적용하기&lt;/h2&gt;
    &lt;p&gt;인라인 요소를 사용하여 텍스트의 특정 부분에만 효과를 넣어보겠습니다.&lt;/p&gt;

    &lt;br /&gt;

    &lt;p&gt;텍스트의 특정 부분에만 &lt;strong&gt;굵은 텍스트 효과&lt;/strong&gt; 넣기&lt;/p&gt;
    &lt;p&gt;텍스트의 특정 부분에만 &lt;em&gt;기울어진 텍스트 효과&lt;/em&gt; 넣기&lt;/p&gt;
    &lt;p&gt;텍스트의 특정 부분에만 &lt;mark&gt;형광펜 밑줄 효과&lt;/mark&gt; 넣기&lt;/p&gt;
  &lt;/body&gt;
&lt;/html&gt;</code></pre><br />
아래 개발자 모드를 통해 보면, strong, em, mark 태그로 지정한 인라인 영역에만 텍스트 효과가 들어간 것을 확인할 수 있습니다.

<img src="https://velog.velcdn.com/images/choco_dev/post/fbb00be3-73d7-4655-a771-9049fa89adfb/image.png" width="80%" />