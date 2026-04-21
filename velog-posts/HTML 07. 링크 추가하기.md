<h2 id="링크">링크</h2>
<h3 id="링크의-개념">링크의 개념</h3>
<blockquote>
<p><strong>링크(Link)란?</strong>
: 현재 문서에서 다른 문서로 이동할 수 있는 수단</p>
</blockquote>
<p style="color: gray; font-size: 18px; font-style: italic;">
  ex) 외부 링크 클릭 시 해당 페이지로 이동...
</p>
<br />

<h3 id="링크--anchor-a-태그">링크 = anchor (a 태그)</h3>
<blockquote>
<p><strong>&lt;a&gt; ~ &lt;/a&gt; 태그란?</strong>
: href 속성으로 특정 URL을 지정하여 하이퍼링크를 만들 수 있는 태그</p>
</blockquote>
<p>해당 a 태그는 인라인 요소입니다. 내부 콘텐츠(텍스트나 이미지...)를 클릭하면 지정된 URL로 이동하게 됩니다.
<br /></p>
<p>&lt;a&gt; 태그의 기본 구조는 다음과 같습니다.</p>
<pre><code>&lt;a href=&quot;지정할 URL&quot;&gt; 콘텐츠 (텍스트 또는 이미지...) &lt;/a&gt;</code></pre><ul>
<li>href=&quot;URL&quot; : 하이퍼링크가 될 URL</li>
<li>콘텐츠 : 사용자가 클릭하는 콘텐츠</li>
</ul>
<br />

<h4 id="어떤-탭에서-열까">어떤 탭에서 열까?</h4>
<p>링크 클릭 시, 기존 탭에서 이동하거나 아예 새로운 탭을 통해 이동하는 방법 2가지가 있습니다.</p>
<p>이는 <strong>target 속성</strong>을 통해 지정 가능합니다. 기본값은 현재 탭에서 이동입니다.</p>
<pre><code>&lt;a href=&quot;https://www.naver.com/&quot; target=&quot;_self&quot;&gt;
  네이버 이동 (현재 탭에서 열기, 기본값)
&lt;/a&gt;

&lt;a href=&quot;https://www.google.com/&quot; target=&quot;_blank&quot;&gt;
  구글로 이동 (새 탭에서 열기)
&lt;/a&gt;</code></pre><br />

<p>이제 실제로 만들어진 링크들이 어떻게 나타나는지 직접 테스트를 하려고 합니다.
<br /></p>
<p><em><strong>링크 만들기 예시</strong></em></p>
<pre><code>&lt;!doctype html&gt;
&lt;html lang=&quot;en&quot;&gt;
  &lt;head&gt;
    &lt;meta charset=&quot;UTF-8&quot; /&gt;
    &lt;meta name=&quot;viewport&quot; content=&quot;width=device-width, initial-scale=1.0&quot; /&gt;
    &lt;title&gt;링크 제작&lt;/title&gt;
  &lt;/head&gt;
  &lt;body&gt;
    &lt;a href=&quot;https://www.naver.com/&quot; target=&quot;_self&quot;&gt;네이버 이동 (현재 탭, 기본값)&lt;/a&gt;
    &lt;br /&gt;
    &lt;a href=&quot;https://www.google.com/&quot; target=&quot;_blank&quot;&gt;구글로 이동 (새 탭)&lt;/a&gt;
    &lt;br /&gt;
    &lt;a href=&quot;https://www.daum.net/&quot; target=&quot;_blank&quot;&gt;
      &lt;img src=&quot;../daum-logo.png&quot; alt=&quot;다음 로고&quot; width=&quot;150&quot; height=&quot;70&quot; /&gt;
    &lt;/a&gt;
  &lt;/body&gt;
&lt;/html&gt;</code></pre><br />
target 속성을 "_self"로 하면 기존 탭에서 열고, "_blank"로 하면 새로운 탭에서 엽니다.

<img src="https://velog.velcdn.com/images/choco_dev/post/c3279f19-3167-41c6-a850-d01b63b4a1e0/image.png" width="80%" />

<br />

<h4 id="전화-걸기-이메일-보내기">전화 걸기, 이메일 보내기</h4>
<p>a 태그를 통해 전화번호와 이메일 주소를 적어서 지정할 수도 있습니다.</p>
<pre><code>&lt;a href=&quot;tel:010-1234-5678&quot;&gt;010-1234-5678&lt;/a&gt;
&lt;a href=&quot;mailto:beansdrawer@naver.com&quot;&gt;beansdrawer@naver.com&lt;/a&gt;</code></pre><p>이렇게 하면 전화 걸기, 이메일 보내기 등의 기능을 구현할 수 있습니다.</p>
<img src="https://velog.velcdn.com/images/choco_dev/post/8fa10932-c094-4a9f-9fd9-03e91b42ad03/image.png" width="80%" />