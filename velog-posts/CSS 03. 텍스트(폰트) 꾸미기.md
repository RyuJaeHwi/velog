<h2 id="텍스트-속성-정리">텍스트 속성 정리</h2>
<h3 id="font-family">font-family</h3>
<blockquote>
<p><strong>font-family란?</strong>
: 요소를 구성하는 텍스트의 글꼴을 정의하는 속성 (글꼴명 = 속성값)</p>
</blockquote>
<p>font-family는 여러 글꼴을 정의할 수 있는데, 이는 글꼴 사이의 우선순위를 지정하여 정의하는 것입니다.
<br /></p>
<p>ex)</p>
<pre><code>*{
  font-family: Times, monospace, serif;
}</code></pre><p style="color: gray; font-size: 16px;">
&nbsp;&nbsp;=> Times 글꼴이 1순위, 만약 이 글꼴이 없다면 후순위로 monospace 글꼴 사용
</p>

<br />

<p><em><strong>font-family 사용 예시</strong></em></p>
<pre><code>&lt;!doctype html&gt;
&lt;html lang=&quot;en&quot;&gt;
  &lt;head&gt;
    &lt;meta charset=&quot;UTF-8&quot; /&gt;
    &lt;meta name=&quot;viewport&quot; content=&quot;width=device-width, initial-scale=1.0&quot; /&gt;
    &lt;title&gt;텍스트 꾸미기&lt;/title&gt;
    &lt;style&gt;
      * {
        /* monospace 글꼴이 없는 경우엔 serif로 대체 */
        font-family: monospace, serif;
      }
    &lt;/style&gt;
  &lt;/head&gt;
  &lt;body&gt;
    &lt;h1&gt;h1 제목 테스트&lt;/h1&gt;
    &lt;p&gt;기본 p 태그 영역 테스트&lt;/p&gt;
  &lt;/body&gt;
&lt;/html&gt;</code></pre><img src="https://velog.velcdn.com/images/choco_dev/post/f736e910-4f12-4316-a812-cf7bc2b4bd81/image.png" width="60%" />

<p>monospace 글꼴인 경우
<br /></p>
<img src="https://velog.velcdn.com/images/choco_dev/post/1096936a-9632-42c9-a4aa-885bc30311bb/image.png" width="60%" />

<p>serif 글꼴인 경우</p>
<br />

<h3 id="font-size">font-size</h3>
<blockquote>
<p>css에서는 수치와 단위를 지정해 텍스트 크기를 정의할 수 있습니다.
&amp;nbsp&amp;nbsp=&gt; <strong>font-size</strong></p>
</blockquote>
<p>아래 표는 css의 font-size 단위입니다.
<br /></p>
<table>
<thead>
<tr>
<th>단위</th>
<th>의미</th>
</tr>
</thead>
<tbody><tr>
<td>&amp;nbsppx</td>
<td>모니터 상 화소 하나 크기에 대응하는 절대 단위</td>
</tr>
<tr>
<td>&amp;nbsprem</td>
<td>html 태그의 font-size에 대응하는 상대 단위</td>
</tr>
<tr>
<td>&amp;nbspem</td>
<td>부모 요소(태그)의 font-size를 기준으로 하는 상대 단위&amp;nbsp&amp;nbsp&amp;nbsp</td>
</tr>
<tr>
<td><br /></td>
<td></td>
</tr>
</tbody></table>
<p>ex)</p>
<pre><code>span{ font-size: 16px; }
span{ font-size: 2rem; }
span{ font-size: 1.5em; }</code></pre><br />

<p><em><strong>font-size 사용 예시</strong></em></p>
<pre><code>&lt;!doctype html&gt;
&lt;html lang=&quot;en&quot;&gt;
  &lt;head&gt;
    &lt;meta charset=&quot;UTF-8&quot; /&gt;
    &lt;meta name=&quot;viewport&quot; content=&quot;width=device-width, initial-scale=1.0&quot; /&gt;
    &lt;title&gt;텍스트 꾸미기&lt;/title&gt;
    &lt;style&gt;
      * {
        /* monospace 글꼴 없는 경우엔 serif로 대체하는 명령어 */
        font-family: monospace, serif;
      }
      /* html 태그는 루트 요소 */
      html {
        font-size: 18px;
      }
      /* rem : html이 18px이니, 2rem = 18 * 2, 1rem = 18 * 1 */
      h1 {
        font-size: 2rem;
      }
      p {
        font-size: 1rem;
      }
      span {
        font-size: 4em;
      }
    &lt;/style&gt;
  &lt;/head&gt;
  &lt;body&gt;
    &lt;h1&gt;h1 제목 테스트&lt;/h1&gt;
    &lt;p&gt;기본 p 태그 텍스트 &lt;span&gt;p 태그 인라인 영역 테스트&lt;/span&gt;&lt;/p&gt;
  &lt;/body&gt;
&lt;/html&gt;</code></pre><img src="https://velog.velcdn.com/images/choco_dev/post/b3c40a26-5488-4dcd-b082-397e42d7206e/image.png" width="90%" />

<p>html 태그의 font-size는 18px, 이는 루트 요소니까 <strong>상대 단위인 rem, em의 기준</strong>이 됩니다.</p>
<p>h1 태그는 2rem이니 18 * 2 = 32px,</p>
<p>p 태그는 1rem이니 18 * 1 = 18px,
<br /></p>
<p>span 태그는 부모 요소가 p 태그이니 p 태그의 18px가 기준이 됩니다.</p>
<p>즉 4em = 4 * 18 = 72px 입니다.</p>
<br />

<h3 id="text-align">text-align</h3>
<blockquote>
<p>css에서는 블록 내에서 <strong>텍스트의 정렬 방식</strong>을 정의합니다.
(미리 정의된 키워드 값을 지정)</p>
</blockquote>
<p>아래 표는 정렬 방식의 종류입니다.
<br /></p>
<table>
<thead>
<tr>
<th>속성값</th>
<th>의미</th>
</tr>
</thead>
<tbody><tr>
<td>&amp;nbspleft / right</td>
<td>&amp;nbsp왼쪽, 또는 오른쪽 정렬</td>
</tr>
<tr>
<td>&amp;nbsp&amp;nbsp&amp;nbspcenter</td>
<td>&amp;nbsp가운데 정렬</td>
</tr>
<tr>
<td>&amp;nbsp&amp;nbsp&amp;nbspjustify</td>
<td>&amp;nbsp양 끝 정렬 (마지막 줄 제외)&amp;nbsp&amp;nbsp&amp;nbsp</td>
</tr>
<tr>
<td><br /></td>
<td></td>
</tr>
</tbody></table>
<p>ex)</p>
<pre><code>p{ text-align: right; }</code></pre><br />

<p><em><strong>text-align 사용 예시</strong></em></p>
<pre><code>&lt;!doctype html&gt;
&lt;html lang=&quot;en&quot;&gt;
  &lt;head&gt;
    &lt;meta charset=&quot;UTF-8&quot; /&gt;
    &lt;meta name=&quot;viewport&quot; content=&quot;width=device-width, initial-scale=1.0&quot; /&gt;
    &lt;title&gt;텍스트 꾸미기&lt;/title&gt;
    &lt;style&gt;
      .left {
        text-align: left;
      }
      .right {
        text-align: right;
      }
      .center {
        text-align: center;
      }
      .justify {
        text-align: justify;
      }

      /* p 태그 스타일 지정 */
      p {
        background-color: gainsboro;
        height: 25px;
      }
      /* span 태그 스타일 지정 */
      span {
        font-size: 36px;
        color: red;
      }
    &lt;/style&gt;
  &lt;/head&gt;
  &lt;body&gt;
    &lt;p class=&quot;left&quot;&gt;왼쪽 정렬 (기본값)&lt;/p&gt;

    &lt;p class=&quot;right&quot;&gt;오른쪽 정렬&lt;/p&gt;

    &lt;p class=&quot;center&quot;&gt;가운데 정렬&lt;/p&gt;

    &lt;p class=&quot;justify&quot;&gt;
      양 끝 정렬 Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor
      incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud
      exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in
      reprehenderit in voluptate &lt;span&gt;velit esse cillum dolore&lt;/span&gt; eu fugiat nulla pariatur.
      Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim
      id est laborum.
    &lt;/p&gt;
  &lt;/body&gt;
&lt;/html&gt;</code></pre><img src="https://velog.velcdn.com/images/choco_dev/post/88fb0465-408e-4dae-8d7f-ad0de1296244/image.png" width="100%" />

<p>여기서 <strong>justify</strong>는 텍스트가 양 끝에 딱 맞게 정렬되는 것을 볼 수 있습니다.</p>
<br />

<h3 id="color">color</h3>
<br />

<table>
<thead>
<tr>
<th>속성값</th>
<th>의미</th>
</tr>
</thead>
<tbody><tr>
<td>&amp;nbsp키워드</td>
<td>&amp;nbsp미리 정의된 색상 키워드 사용 ex) red, green ...</td>
</tr>
<tr>
<td>&amp;nbspRGB 색상 코드</td>
<td>&amp;nbsp# + 여섯 자리 16진수 형태로 색상 지정</td>
</tr>
<tr>
<td>&amp;nbspRGB 함수</td>
<td>&amp;nbspRed, Green, Blue의 값을 각각 정의해 색상 지정 (%값)&amp;nbsp&amp;nbsp</td>
</tr>
<tr>
<td><br /></td>
<td></td>
</tr>
</tbody></table>
<p>ex)</p>
<pre><code>span{ color: red; }
span{ color: #FF0000; }
span{ color: rgb(100%, 0%, 30%); }</code></pre><br />