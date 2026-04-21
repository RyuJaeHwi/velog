<h2 id="목록">목록</h2>
<blockquote>
<p><strong>목록이란?</strong>
: 서로 연관 있는 항목(item)들을 나열한 것을 의미</p>
</blockquote>
<p>.html 문서에서 목록은 &quot;순서 없는 목록&quot;과 &quot;순서 없는 목록&quot;으로 구분합니다.
<br /></p>
<p><strong>Unordered List</strong></p>
<ul>
<li>공부하기</li>
<li>운동하기</li>
<li>독서하기<br />

</li>
</ul>
<p><strong>Ordered List</strong></p>
<ol>
<li>HTML</li>
<li>CSS</li>
<li>JavaScript</li>
</ol>
<br />

<p>각 리스트 종류마다 사용하는 태그는 다음과 같습니다.</p>
<blockquote>
<ul>
<li>순서가 있는 목록 (Ordered List) : <strong>&lt;ol&gt; ~ &lt;/ol&gt;</strong></li>
</ul>
</blockquote>
<ul>
<li>순서가 없는 목록 (Unordered List) : <strong>&lt;ul&gt; ~ &lt;/ul&gt;</strong></li>
</ul>
<br />

<h4 id="각-항목을-나타내는-태그는">각 항목을 나타내는 태그는?</h4>
<p>리스트 내부의 각 항목들은 <strong>&lt;li&gt; ~ &lt;/li&gt;</strong> 태그를 사용합니다.</p>
<p>이 태그는 리스트의 종류에 상관없이 둘 다 공통으로 사용하는 태그입니다.
&lt;li&gt; ~ &lt;/li&gt; 태그를 감싸는 상위 태그가 무엇이냐에 따라 각 항목의 기호가 달라지는 원리입니다.
<br /></p>
<p><em><strong>목록 만들기 예시</strong></em></p>
<pre><code>&lt;!doctype html&gt;
&lt;html lang=&quot;en&quot;&gt;
  &lt;head&gt;
    &lt;meta charset=&quot;UTF-8&quot; /&gt;
    &lt;meta name=&quot;viewport&quot; content=&quot;width=device-width, initial-scale=1.0&quot; /&gt;
    &lt;title&gt;목록 만들기&lt;/title&gt;
  &lt;/head&gt;
  &lt;body&gt;
    &lt;h1&gt;오늘 할 일&lt;/h1&gt;
    &lt;ul&gt;
      &lt;li&gt;html 공부하기&lt;/li&gt;
      &lt;li&gt;&lt;strong&gt;pt 수업 들으러 가기&lt;/strong&gt;&lt;/li&gt;
      &lt;li&gt;낮잠자기&lt;/li&gt;
      &lt;li&gt;독서하기&lt;/li&gt;
    &lt;/ul&gt;
    &lt;hr /&gt;
    &lt;h1&gt;프론트엔드 공부 순서&lt;/h1&gt;
    &lt;ol&gt;
      &lt;li&gt;&lt;mark&gt;HTML&lt;/mark&gt;&lt;/li&gt;
      &lt;li&gt;CSS&lt;/li&gt;
      &lt;li&gt;JavaScript&lt;/li&gt;
      &lt;li&gt;React&lt;/li&gt;
    &lt;/ol&gt;
  &lt;/body&gt;
&lt;/html&gt;</code></pre><br />

<img src="https://velog.velcdn.com/images/choco_dev/post/13eafe55-41aa-418f-808e-30a03b9423dc/image.png" width="80%" />

<br />
여기서 리스트 영역이랑 항목 영역을 개발자 모드를 통해 확인하면, ol, ul, li 태그 셋 모두 블록 레벨 요소를 표시하는 태그란 걸 확인할 수 있습니다.

<img src="https://velog.velcdn.com/images/choco_dev/post/9f09940c-1222-4249-8347-22065ae23e00/image.png" width="70%" />
<img src="https://velog.velcdn.com/images/choco_dev/post/e896a6a3-32c4-48ca-a1d9-fc960473491b/image.png" width="70%" />