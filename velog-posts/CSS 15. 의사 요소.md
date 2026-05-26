<h2 id="의사-요소">의사 요소</h2>
<blockquote>
<p><strong>의사 요소(pseudo-elements) 란?</strong>
: 선택자에 추가하는 키워드로, 선택한 요소의 특정 부분에 대한 스타일을 정의할 수 있음</p>
</blockquote>
<p>의사 요소의 코드 기본 구조입니다.</p>
<pre><code>선택자::의사 요소{
  속성명: 속성값;
}</code></pre><p>실제 저 구조를 적용하면 아래처럼 쓸 수 있습니다.
<br /></p>
<p>ex) li 요소의 첫 번째 글자만 크기를 20px로 변경 (기본값 = 16px)</p>
<pre><code>li::first-letter{
  font-size: 20px;
}</code></pre><br />

<p>아래 표는 의사 요소 중 가장 많이 사용되는 것 일부를 정리한 것입니다.
<br /></p>
<table>
<thead>
<tr>
<th align="center">의사 요소</th>
<th>의미</th>
</tr>
</thead>
<tbody><tr>
<td align="center">after</td>
<td>요소의 앞에 의사 요소를 생성 및 추가</td>
</tr>
<tr>
<td align="center">before</td>
<td>요소의 뒤에 의사 요소를 생성 및 추가</td>
</tr>
<tr>
<td align="center">first-line</td>
<td>블록 레벨 요소의 첫 번째 선에 스타일 적용&amp;nbsp&amp;nbsp</td>
</tr>
<tr>
<td align="center">maker</td>
<td>목록 기호의 스타일 적용</td>
</tr>
<tr>
<td align="center">placeholder</td>
<td>입력 요소의 자리표시자 스타일 적용</td>
</tr>
</tbody></table>
<br />

<p><em><strong>의사 요소 예시1</strong></em></p>
<pre><code>&lt;!doctype html&gt;
&lt;html lang=&quot;en&quot;&gt;
  &lt;head&gt;
    &lt;meta charset=&quot;UTF-8&quot; /&gt;
    &lt;meta name=&quot;viewport&quot; content=&quot;width=device-width, initial-scale=1.0&quot; /&gt;
    &lt;title&gt;의사 요소&lt;/title&gt;
    &lt;style&gt;
      p::first-line {
        color: red;
      }
      p::first-letter {
        font-size: 24px;
      }
    &lt;/style&gt;
  &lt;/head&gt;
  &lt;body&gt;
    &lt;p&gt;
      퍼스트 라인 &amp; 레터 테스트
      &lt;br /&gt;
      퍼스트 라인 &amp; 레터 테스트
      &lt;br /&gt;
      퍼스트 라인 &amp; 레터 테스트
      &lt;br /&gt;
      퍼스트 라인 &amp; 레터 테스트
    &lt;/p&gt;
  &lt;/body&gt;
&lt;/html&gt;</code></pre><img src="https://velog.velcdn.com/images/choco_dev/post/d976268c-1087-42b5-a2e2-ea5592190815/image.png" width="60%" />

<p>의사 요소를 통해 첫 번째 p 태그의 전체 한 줄 색을 red로, 그 첫 번째 줄의 첫 번째 텍스트 크기만 24px로 바꾸었습니다.</p>
<br />

<p><em><strong>의사 요소 예시2</strong></em></p>
<pre><code>&lt;!doctype html&gt;
&lt;html lang=&quot;en&quot;&gt;
  &lt;head&gt;
    &lt;meta charset=&quot;UTF-8&quot; /&gt;
    &lt;meta name=&quot;viewport&quot; content=&quot;width=device-width, initial-scale=1.0&quot; /&gt;
    &lt;title&gt;의사 요소&lt;/title&gt;
    &lt;style&gt;
      li::marker {
        color: darkcyan;
        font-size: 50px;
      }
      input::placeholder {
        font-size: 28px;
        color: plum;
      }
    &lt;/style&gt;
  &lt;/head&gt;
  &lt;body&gt;
    &lt;ul&gt;
      &lt;li&gt;사탕&lt;/li&gt;
      &lt;li&gt;초콜릿&lt;/li&gt;
      &lt;li&gt;젤리&lt;/li&gt;
      &lt;li&gt;쿠키&lt;/li&gt;
    &lt;/ul&gt;
    &lt;input type=&quot;text&quot; placeholder=&quot;아무거나 작성하기&quot; /&gt;
  &lt;/body&gt;
&lt;/html&gt;</code></pre><img src="https://velog.velcdn.com/images/choco_dev/post/ee83ee94-12de-4fbb-a804-3b65f604c7cd/image.png" width="70%" />

<p>li::marker { ... } 의사 요소를 통해 목록 표시의 색상과 크기를 바꾸었습니다.</p>
<p>또한 input 내부 placehoder 텍스트의 크기와 색상도 변경하였습니다.
<br /></p>
<p><em><strong>의사 요소 예시3</strong></em></p>
<pre><code>&lt;!doctype html&gt;
&lt;html lang=&quot;en&quot;&gt;
  &lt;head&gt;
    &lt;meta charset=&quot;UTF-8&quot; /&gt;
    &lt;meta name=&quot;viewport&quot; content=&quot;width=device-width, initial-scale=1.0&quot; /&gt;
    &lt;title&gt;의사 요소&lt;/title&gt;
    &lt;style&gt;
      h2::before {
        content: &quot;h2 앞에 before 옵션으로 추가한 텍스트&quot;;
        font-size: 12px;
        font-weight: 900;
        color: brown;
      }
      h2::after {
        content: &quot;h2 뒤에 after 옵션으로 추가한 텍스트&quot;;
        font-size: 12px;
        font-weight: 400;
        color: darkgoldenrod;
      }
    &lt;/style&gt;
  &lt;/head&gt;
  &lt;body&gt;
    &lt;h2&gt;원래 작성된 내용&lt;/h2&gt;
  &lt;/body&gt;
&lt;/html&gt;</code></pre><img src="https://velog.velcdn.com/images/choco_dev/post/520a2e24-f4de-4e13-bc58-56edefa8fbfb/image.png" width="70%" />

<p>before과 after 의사 요소를 통해 기존 h2 요소 앞 뒤에 각각 텍스트를 추가하였습니다.</p>