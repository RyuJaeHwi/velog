<h2 id="문단paragraph-태그">문단(paragraph) 태그</h2>
<blockquote>
<p><strong>p 태그</strong> : 문단 요소를 나타내는 태그로, 가장 많이 쓰이는 텍스트 태그</p>
</blockquote>
<p>하나의 p 태그는 하나의 문단을 표현하고, 문단 사이에는 공백이 있습니다.
<br /></p>
<p><em><strong>문단 태그 사용 예시</strong></em></p>
<pre><code>&lt;!doctype html&gt;
&lt;html lang=&quot;en&quot;&gt;
  &lt;head&gt;
    &lt;meta charset=&quot;UTF-8&quot; /&gt;
    &lt;meta name=&quot;viewport&quot; content=&quot;width=device-width, initial-scale=1.0&quot; /&gt;
    &lt;title&gt;텍스트 태그 연습&lt;/title&gt;
  &lt;/head&gt;
  &lt;body&gt;
    &lt;p&gt;텍스트를 표시하고 있습니다.&lt;/p&gt;
    &lt;p&gt;
      Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut
      labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco
      laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in
      voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat
      non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
    &lt;/p&gt;
  &lt;/body&gt;
&lt;/html&gt;</code></pre><p>이 테스트 코드의 결과는 다음과 같습니다.</p>
<img src="https://velog.velcdn.com/images/choco_dev/post/d9c87ec8-cc7d-45dc-a976-1defc80ca237/image.png" width="80%" />

<p>개발자 모드로 확인하면 각 p 태그가 서로 다른 문단으로 되어있는 것을 확인할 수 있습니다.</p>
<img src="https://velog.velcdn.com/images/choco_dev/post/5df2fa88-279e-443c-867a-0bef1fc35e8d/image.png" width="80%" />

<br />

<h2 id="제목headline-태그">제목(headline) 태그</h2>
<blockquote>
<p><strong>h 태그</strong> : 제목(표제) 요소를 나타내는 태그, 숫자와 함께 사용</p>
</blockquote>
<p>h 태그는 숫자와 함께 쓰이는데, h1 ~ h6로 총 6종류입니다.</p>
<p>h1이 가장 큰 크기의 제목 텍스트이고 h6으로 숫자가 커질수록 제목 텍스트의 크기는 작아집니다.
<br /></p>
<p><em><strong>제목 태그 사용 예시</strong></em></p>
<pre><code>&lt;!doctype html&gt;
&lt;html lang=&quot;en&quot;&gt;
  &lt;head&gt;
    &lt;meta charset=&quot;UTF-8&quot; /&gt;
    &lt;meta name=&quot;viewport&quot; content=&quot;width=device-width, initial-scale=1.0&quot; /&gt;
    &lt;title&gt;텍스트 태그 연습&lt;/title&gt;
  &lt;/head&gt;
  &lt;body&gt;
    &lt;h1&gt;텍스트 태그 연습 h1&lt;/h1&gt;
    &lt;h2&gt;텍스트 태그 연습 h2&lt;/h2&gt;
    &lt;h3&gt;텍스트 태그 연습 h3&lt;/h3&gt;
    &lt;h4&gt;텍스트 태그 연습 h4&lt;/h4&gt;
    &lt;h5&gt;텍스트 태그 연습 h5&lt;/h5&gt;
    &lt;h6&gt;텍스트 태그 연습 h6&lt;/h6&gt;
  &lt;/body&gt;
&lt;/html&gt;
</code></pre><p>이 테스트 코드의 결과는 다음과 같습니다.</p>
<img src="https://velog.velcdn.com/images/choco_dev/post/c72cbee6-f904-47ba-a8e9-e8fdbbed84cd/image.png" width="70%" />

<br />

<h2 id="구분선">구분선</h2>
<blockquote>
<p><strong>hr 태그</strong> : 구분선을 표시하는 태그 (주제 또느 내용 구분 시 사용)</p>
</blockquote>
<p>hr 태그는 콘텐츠 사이에 넣는 구분선을 표시합니다. 단일 태그로 사용합니다.</p>
<p><em><strong>구분선 태그 사용 예시</strong></em></p>
<pre><code>&lt;!doctype html&gt;
&lt;html lang=&quot;en&quot;&gt;
  &lt;head&gt;
    &lt;meta charset=&quot;UTF-8&quot; /&gt;
    &lt;meta name=&quot;viewport&quot; content=&quot;width=device-width, initial-scale=1.0&quot; /&gt;
    &lt;title&gt;텍스트 태그 연습&lt;/title&gt;
  &lt;/head&gt;
  &lt;body&gt;
    &lt;h1&gt;텍스트 태그 연습 h1&lt;/h1&gt;
    &lt;p&gt;구분선 위 텍스트 문단&lt;/p&gt;
    &lt;hr /&gt;
    &lt;p&gt;구분선 아래 텍스트 문단&lt;/p&gt;
  &lt;/body&gt;
&lt;/html&gt;</code></pre><p>이 테스트 코드의 결과는 다음과 같습니다.</p>
<img src="https://velog.velcdn.com/images/choco_dev/post/f5cf1ec4-b530-49b8-8096-81dc4991c949/image.png" width="70%" />

<br />


<h2 id="줄바꿈-태그">줄바꿈 태그</h2>
<blockquote>
<p><strong>br 태그</strong> : 텍스트에서 줄바꿈(line <strong>br</strong>eak)을 나타내는 태그</p>
</blockquote>
<p>br 태그는 특정 태그 밖이나 안에서 사용 가능합니다.</p>
<p>텍스트를 끊어 줄바꿈을 하고 싶은 부분에 사용하면 됩니다.
<br /></p>
<p><strong><em>줄바꿈 태그 사용 예시</em></strong></p>
<pre><code>&lt;!doctype html&gt;
&lt;html lang=&quot;en&quot;&gt;
  &lt;head&gt;
    &lt;meta charset=&quot;UTF-8&quot; /&gt;
    &lt;meta name=&quot;viewport&quot; content=&quot;width=device-width, initial-scale=1.0&quot; /&gt;
    &lt;title&gt;텍스트 태그 연습&lt;/title&gt;
  &lt;/head&gt;
  &lt;body&gt;
    &lt;p&gt;줄바꿈 하기 전 텍스트 문단&lt;/p&gt;
    &lt;br /&gt;
    &lt;p&gt;줄바꿈 한 후 텍스트 문단&lt;/p&gt;
    &lt;br /&gt;
    &lt;br /&gt;
    &lt;p&gt;
      p 태그 내부에서도 br 태그로 줄바꿈이 가능합니다.
      &lt;br /&gt;
      줄바꿈을 넣고 싶은 부분에 &lt;br /&gt;바로 넣으면 됩니다.
    &lt;/p&gt;
  &lt;/body&gt;
&lt;/html&gt;</code></pre><p>이 테스트 코드의 결과는 다음과 같습니다.</p>
<img src="https://velog.velcdn.com/images/choco_dev/post/71872f2c-6d4f-40cf-8f9b-e892d4203515/image.png" width="80%" />

<br />

<h2 id="공백-표기">공백 표기</h2>
<blockquote>
<p><strong>&amp;nbsp;</strong>란? 공백을 표시하는 문자</p>
</blockquote>
<p>.html 문서에서는 space바를 사용해 띄어쓰기를 아무리 많이 해도 딱 한 번만 한 것으로 인식됩니다.</p>
<p>ex)</p>
<pre><code>&lt;p&gt;띄어쓰기 테스트 중인          텍스트 문단&lt;/p&gt;</code></pre><p>이렇게 많이 공백을 넣어도 결과는 딱 한번 공백을 넣은 것으로 처리됩니다.</p>
<img src="https://velog.velcdn.com/images/choco_dev/post/28253386-fe37-493a-a91d-0f1bef8adcd6/image.png" width="70%" />

<br />

<p>.html 문서에서는 공백을 두 번 이상 넣으려면 <strong>&amp;nbsp;</strong>을 사용해야 합니다.</p>
<p><strong><em>&amp;nbsp; 공백 문자 사용 예시</em></strong></p>
<pre><code>&lt;!doctype html&gt;
&lt;html lang=&quot;en&quot;&gt;
  &lt;head&gt;
    &lt;meta charset=&quot;UTF-8&quot; /&gt;
    &lt;meta name=&quot;viewport&quot; content=&quot;width=device-width, initial-scale=1.0&quot; /&gt;
    &lt;title&gt;텍스트 태그 연습&lt;/title&gt;
  &lt;/head&gt;
  &lt;body&gt;
    &lt;p&gt;띄어쓰기&amp;nbsp;를 테스트 중인 &amp;nbsp;&amp;nbsp;&amp;nbsp;텍스트 &amp;nbsp;&amp;nbsp;문단&lt;/p&gt;
  &lt;/body&gt;
&lt;/html&gt;</code></pre><p>이 테스트 코드의 결과는 다음과 같습니다.</p>
<img src="https://velog.velcdn.com/images/choco_dev/post/6f58c844-0965-4034-bc96-fd885cfa5e76/image.png" width="70%" />