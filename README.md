# 마크업 가이드

- 이 문서는 개인 프로젝트를 진행할 때 기본적인 규칙을 정해놓은 문서입니다.
- 이 문서는 추가, 수정, 삭제가 될 수 있습니다.
- 이 문서를 통해 얻고자 하는 것은 일관성 있는 코드 작성 방법입니다.<br />
  작업을 진행하다 보면 어떤 방식으로 코드를 작성했는지 작성 방법을 잊어버리는 경우가 있습니다.<br />
  그렇기 때문에 기본적인 규칙을 정해놓은 문서가 필요하다고 생각되어 만들었습니다.
- 이 문서의 내용을 바탕으로 코드를 일관성 있게 작성하는 데 도움이 되길 기대하고 있습니다.

## 목차

[1. HTML](#HTML)<br />
[1-1. 레이아웃](#레이아웃)<br />
[1-2. 주석](#주석)<br />
[1-2-1. 수정 작업 시 주석 처리 방법](#수정-작업-시-주석-처리-방법)<br />
[1-2-2. 개발자에게 전달하는 주석 처리 방법](#개발자에게-전달하는-주석-처리-방법)<br />
[1-3. 들여쓰기](#들여쓰기)<br />
[1-4. HTML 속성 작성 순서](#HTML-속성-작성-순서)<br />
[1-5. 기타 참고사항](#기타-참고사항)<br />
[2. CSS](#CSS)<br />
[2-1. z-index 값 할당 가이드](#z-index-값-할당-가이드)<br />
[2-2. 아이콘 링크, 아이콘 버튼 영역 가이드](#아이콘-링크,-아이콘-버튼-영역-가이드)<br />
[2-3. CSS 주석 규칙](#CSS-주석-규칙)<br />
[2-4. CSS 속성 선언 순서](#CSS-속성-선언-순서)<br />
[2-4-1. font 속성 선언 시 주의할 점](#font-속성-선언-시-주의할-점)<br />
[2-4-2. color 속성 값 선언 시 주의할 점](#color-속성-값-선언-시-주의할-점)<br />
[2-4-3. background-position 속성값 선언 시 주의할-점](#background-position-속성값-선언-시-주의할-점)<br />
[2-4-4. !important 사용 시 주의할-점](#!important-사용-시-주의할-점)<br />
[2-5. CSS Cascading](#CSS-Cascading)<br />
[3. Naming](#Naming)<br />
[3-1. 네이밍 규칙](#네이밍-규칙)<br />
[3-1-1. id/class 규칙](#id/class-규칙)<br />
[3-1-2. folder/file 규칙](#folder/file-규칙)<br />
[3-1-3. images 규칙](#images-규칙)<br />
[3-2. prefix/subfix/suffix 정의](#prefix/subfix/suffix-정의)<br />
[3-2-1. prefix 예약어 및 설명](#prefix-예약어-및-설명)<br />
[3-2-2. subfix 예약어 및 설명](#subfix-예약어-및-설명)<br />
[3-2-3. suffix 예약어 및 설명](#suffix-예약어-및-설명)<br />
[4. Image](#Image)<br />
[4-1. 이미지 스프라이트 가이드 및 이미지 압축](#이미지-스프라이트-가이드-및-이미지-압축)

## 레이아웃

레이아웃은 전체를 class="wrapper"로 감싸고 class="header", class="container" class="footer"로 나눕니다. 이 내용은 모바일에서도 적용하는 것을 권장합니다.

class="wrapper"에 CSS Style position: relative를 줌으로써 상단 유틸리티 메뉴를 문서 흐름과 디자인에 맞게 위로 올리는 디자인 대응이 가능하도록 할 수 있습니다.

<strong>주의사항</strong>

- 자사 서비스의 경우 자사의 이름을 prefix로 해서 id="prefixWrap", id="prefixHead", id="prefixContainer" id="prefixFoot"으로 적용하는 것을 권장합니다. (자사의 이름을 prefix로 해서 자사의 HTML 문서임을 알 수 있도록 하는 것을 권장합니다.)
- 웹 접근성용 바로 가기 메뉴는 가장 상단에 위치하도록 하는 것을 권장합니다.
- 바로 가기 메뉴는 자사의 이름을 prefix로 해서 id="prefixContainer"로 했을 경우, 잊지 말고 href="#prefixContainer"로 수정해 주세요.
- &lt;h<em>n</em>&gt; 태그의 경우 아래 표와 같이 각 영역을 대표하는 제목을 작성할 때 사용하도록 하는 것을 권장합니다.

<table>
  <thead>
    <tr>
      <th>&lt;h<em>n</em>&gt;</th>
      <th>설명</th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>&lt;h1&gt;</td>
      <td>이 서비스의 이름을 작성할 때 사용할 것을 권장합니다.</td>
    </tr>
    <tr>
      <td>&lt;h2&gt;</td>
      <td>
          특정 영역을 대표하는 제목을 작성할 때 사용할 것을 권장합니다.<br />
          예를 들어, 주메뉴, 본문, 하단 회사 정보 및 이용약관 등
      </td>
    </tr>
    <tr>
      <td>&lt;h3&gt;</td>
      <td>콘텐츠 영역을 대표하는 제목을 작성할 때 사용할 것을 권장합니다.</td>
    </tr>
    <tr>
      <td>&lt;h4&gt;, &lt;h5&gt;, &lt;h6&gt;</td>
      <td>상황에 따라 콘텐츠 제목을 작성할 때 사용할 것을 권장합니다.</td>
    </tr>
  </tbody>
</table>

<strong>주의사항</strong>

- 페이지 내 레이어 팝업의 경우 &lt;strong&gt; 태그를 사용해서 제목을 작성할 것을 권장합니다. 레이어 팝업 마크업이 다른 곳에서 사용될 수 있기 때문에 &lt;h<em>n</em>&gt; 태그를 사용해서 레이어 팝업 제목을 작성한다면 &lt;h<em>n</em>&gt; 태그 순서가 맞지 않을 가능성이 있습니다.
- &lt;section&gt; 태그에는 &lt;h<em>n</em>&gt; 태그를 사용해서 콘텐츠 영역을 구분하는 것을 권장합니다.
- &lt;article&gt; 태그는 해당 콘텐츠가 단독으로 노출 가능한 콘텐츠일 때 사용하는 것을 권장합니다.
- &lt;article&gt; 태그 안에 &lt;section&gt; 태그를 사용할 수 있습니다.

## 주석

주석을 일관성 있게 작성함으로써 개발자와 협업 시 원활한 소통을 기대할 수 있습니다.

### 수정 작업 시 주석 처리 방법

마크업 수정 시 수정 부분을 표시하는 주석은 아래와 같이 날짜와 수정 내용을 간단하게 작성해서 처리하는 것을 권장합니다.

```
<!-- 2021-03-02 이미지 수정 시작 -->
  ...
<!-- // 2021-03-02 이미지 수정 끝 -->
```

### 개발자에게 전달하는 주석 처리 방법

```
<!-- [D]
  현재 메뉴가 활성화되었을 경우 class="link_gnb"에 current를 추가해 주세요.
-->
```

<strong>주의사항</strong>

- <! 와 > 사이에 공백 문자가 있어서는 안됩니다. 예를 들어, &lt;! -- // 주석 내용 -- &gt;
- 두 개 이상의 하이픈을 사용해서는 안 됩니다. 예를 들어, &lt;!--- // 주석 내용 ---&gt;

## 들여쓰기

코드의 가독성을 높이기 위해서 들여쓰기 크기는 2로 설정하는 것을 권장합니다.

## HTML 속성 작성 순서

<table>
  <thead>
    <tr>
      <th>순서</th>
      <th>속성</th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>1</td>
      <td>rel</td>
    </tr>
    <tr>
      <td>2</td>
      <td>type</td>
    </tr>
    <tr>
      <td>3</td>
      <td>href, src</td>
    </tr>
    <tr>
      <td>4</td>
      <td>id</td>
    </tr>
    <tr>
      <td>5</td>
      <td>class</td>
    </tr>
    <tr>
      <td>6</td>
      <td>name</td>
    </tr>
    <tr>
      <td>7</td>
      <td>alt, title</td>
    </tr>
    <tr>
      <td>8</td>
      <td>width, height</td>
    </tr>
    <tr>
      <td>9</td>
      <td>target</td>
    </tr>
    <tr>
      <td>10</td>
      <td>style</td>
    </tr>
    <tr>
      <td>11</td>
      <td>기타</td>
    </tr>
  </tbody>
</table>

```
<a href="#" id="linkLocal" class="link_local" target="_blank" style="display: inline-block">링크 바로 가기</a>

<img src="/images/20210101.jpg" id="imgLocal" class="img_local" alt="이미지 내용" width="12" height="12" />

<input type="text" id="tfLocal" class="tf_local" name="start" title="시작일" style="width: 12px" maxlength="8" />
```

<strong>주의사항</strong>

- HTML 속성의 값은 반드시 큰따옴표"로 묶어서 사용하는 것을 권장합니다.
- 에디터 플러그인을 통해 자동으로 속성이 정렬될 경우 플러그인의 설정을 따라가는 것을 권장합니다.

## 기타 참고사항

### &lt;table&gt; 태그

&lt;table&gt; 태그를 사용해서 마크업을 작성할 때 아래 내용을 확인하고 작성하는 것을 권장합니다.

<table>
  <thead>
    <tr>
      <th>속성 또는 태그</th>
      <th>설명</th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>scope</td>
      <td>scope는 화면 낭독기를 통해 테이블이 읽어야 하는 방향을 알려줍니다. scope="col"은 세로(column)로 읽고, row는 가로(row)로 읽습니다.</td>
    </tr>
    <tr>
      <td>id, headers</td>
      <td>복잡도가 높은 table에서 접근성을 고려한 마크업 시 사용하는 것을 권장합니다.</td>
    </tr>
    <tr>
      <td>&lt;thead&gt;, &lt;tbody&gt;, &lt;tfoot&gt;</td>
      <td>table에서 &lt;table&gt 태그 안에 &lt;thead&gt;만 있으면 <a href="https://validator.w3.org/" target="_blank">HTML validation</a>에서 에러가 발생합니다. &lt;tfoot&gt;는 마크업의 흐름상 &lt;thead&gt;, &lt;tfoot&gt;, &lt;tbody&gt; 순서로 작성해야 합니다.</td>
    </tr>
    <tr>
      <td>&lt;colgroup&gt;</td>
      <td>&lt;colgroup&gt; 태그는 세로 열 전체를 그룹화할 때 사용하는 것을 권장합니다.</td>
    </tr>
    <tr>
      <td>&lt;col /&gt;</td>
      <td>&lt;col /&gt; 태그를 사용 시 &lt;col style="width: 33.33%" /&gt;와 같이 style 속성을 사용해서 작성하는 것을 권장합니다.</td>
    </tr>
  </tbody>
</table>

### summary, caption 작성 방법

<strong>[잘못된 경우]</strong>

```
<table>
  <caption>
    <strong>table의 제목</strong>
    <p>th의 제목, th의 제목, th의 제목, ...</p>
  </caption>

  ...
</table>

<table>
  <caption>
    table의 제목
  </caption>

  ...
</table>
```

<strong>[권장]</strong>

```
<table>
  <caption>
    table의 제목에 대한 th의 제목, th의 제목, th의 제목에 대한 정보를 확인할 수 있습니다.
  </caption>

  ...
</table>
```

&lt;dl&gt; 태그 내부에서 여러 개의 &lt;dt&gt;, &lt;dd&gt;를 사용할 수 있습니다.

&lt;label&gt; 태그를 사용하기 애매한 구조의 &lt;input /&gt; 태그에서 title 속성을 사용할 수 있습니다.

HTML 속성 값은 속성을 같이 작성해 주세요.

```
<option value="a" selected> ... </option> // X
<option value="a" selected="selected"> ... </option> // O

<input type="checkbox" value=" ... " checkbox /> // X
<input type="checkbox" value=" ... " checkbox="checkbox" /> // O
```

HTML 속성 값은 큰따옴표"로 묶어서 작성하는 것을 권장합니다.

```
<img src=/images/20210101.jpg alt=" ... " /> // X
<img src="/images/20210101.jpg" alt=" ... " /> // O
```

- 에디터 플러그인을 통해 자동으로 제어될 경우 플러그인의 설정을 따라가는 것을 권장합니다.

HTML 요소는 반드시 닫아야 합니다.

```
<input type="checkbox" value=" ... " checkbox="checkbox"> // X
<input type="checkbox" value=" ... " checkbox="checkbox" /> // O

<img src="/images/20210101.jpg" alt=" ... "> // X
<img src="/images/20210101.jpg" alt=" ... " /> // O

<br> // X
<br /> // O

<hr> // X
<hr /> // O
```

- 에디터 플러그인을 통해 자동으로 제어될 경우 플러그인의 설정을 따라가는 것을 권장합니다.

text나 url, script에 포함된 특수 문자는 HTML escape 처리를 해주세요.

<table>
  <thead>
    <tr>
      <th>특수 문자 이스케이프 처리 이전</th>
      <th>특수문자 이스케이프 처리 이후</th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>&lt;</td>
      <td>& l t ;</td>
    </tr>
    <tr>
      <td>&gt;</td>
      <td>& g t ;</td>
    </tr>
    <tr>
      <td>&amp;</td>
      <td>& a m p ;</td>
    </tr>
  </tbody>
</table>

## CSS

CSS는 초기화에 사용되는 base.css와 콘텐츠 부분에 사용되는 custom.css로 나누어 작업하는 것을 권장합니다.<br />
<br />
CSS 선택자는 HTML Class로 제어하는 것을 권장합니다. 태그로 제어하는 것은 전역 태그들을 오염시킬 수 있기 때문에 지양합니다.<br />
<br />
하지만 태그 안에 특정 태그 외 다른 태그가 들어올 수 없는 dl, ol, ul 그리고 사용빈도가 높은 h1, th, td의 경우 예외적으로 사용할 수 있습니다.

```
h2 {
  font-size: 16px;
  color: #ff0000;
} // X

.tit_local {
  font-size: 16px;
  color: #ff0000;
} // O

ul {
  margin-top: 24px;
} // X

ul li {
  margin-top: 12px;
} // X

.list_local {
  margin-top: 24px;
} // O

.list_local li {
  margin-top: 12px;
} // O

p {
  font-size: 12px;
  color: #008000;
} // X

span {
  font-size: 12px;
  color: #0000ff;
} // X

.txt_local {
  font-size: 12px;
  color: #ff0000;
} // O

p.txt_local {
  font-size: 12px;
  color: #008000;
} // O

span.txt_local {
  font-size: 12px;
  color: #0000ff;
} // O
```

CSS 작성 시 3 Depth를 초과하지 않도록 작성하는 것을 권장합니다. 또한 크로스 브라우징을 위해 CSS hack 사용은 지양합니다.<br />
<br />
CSS 단위 사용은 PC 홈페이지와 같이 고정된 디자인을 사용했을 경우 px 단위를 사용하는 것을 권장하고, Mobile 홈페이지 또는 하이브리드 앱 작업 시 rem, %를 사용하는 것을 권장합니다.<br />
<br />
속성 값 할당에 작은따옴표' 사용은 지양합니다. 하지만 사용이 필요한 경우 작음 따옴표' 사용으로 통일하는 것을 권장합니다.

```
body {
  font-family: '돋움', Dotum;
}
```

- 에디터 플러그인을 통해 자동으로 제어될 경우 플러그인의 설정을 따라가는 것을 권장합니다.

## z-index 값 할당 가이드

규칙 없는 z-index 사용은 추후 운영에 큰 문제를 발생시킬 수 있습니다. (다중 레이어 팝업 같은 경우..) 그렇기 때문에 z-index 값은 10단위로 사용할 것을 권장합니다.<br />
<br />
하지만 10단위를 어떤 요소에 적용하기에 너무 큰 값인 것 같다 생각이 들 경우 z-index 값은 1단위를 고정 값으로 사용하는 것을 권장합니다.

```
.lab_local {
  ...
  z-index: 1;
  ...
}
```

만약 음수 값을 할당해야 한다면 -1단위를 고정 값으로 사용합니다. 그리고 레이어 팝업에서 z-index를 사용할 경우 할당 값은 1000부터 시작하고 증가 값은 10단위로 할당하는 것을 권장합니다.

```
.layer_local1 {
  ...
  z-index: 1000;
  ...
}

.layer_local2 {
  ...
  z-index: 1010;
  ...
}

.layer_local3 {
  ...
  z-index: 1020;
  ...
}

...
```

## 아이콘 링크, 아이콘 버튼 영역 가이드

PC 홈페이지와 Mobile 홈페이지 또는 하이브리드 앱에서 너무 작은 영역의 아이콘 링크나 아이콘 버튼 같은 경우 사용자가 조작하기 불편한 경우가 많습니다.<br />
<br />
이러한 부분을 최소화하고자 아이콘 링크, 아이콘 버튼 영역은 아래와 같이 최소한의 가로, 세로 값을 지정하는 것을 권장합니다.

- 상황에 따라 사용할 것을 권장합니다.

## CSS 주석 규칙

주석은 아래와 같이 주석을 사용한 년-월-일 주석 내용 추가, 수정, 삭제 여부를 추가해서 작성할 것을 권장합니다.

```
body { ... } /* 2020-03-03 수정 */

body { ... } /* 2020-03-03 주석 내용 */

/* 2020-03-03 주석 내용 시작 */
html { ... }
body { ... }
/* 2020-03-03 주석 내용 끝 */
```

- 내용이 기존과 크게 바뀌지 않은 경우 주석 내용을 제외하고 년-월-일 추가, 수정, 삭제 여부만 추가해서 작성하는 것을 권장합니다.
- 만약 두 줄 이상 주석을 추가해야 하는 경우 시작과 끝을 추가해서 작성하는 것을 권장합니다.

## CSS 속성 선언 순서

<table>
  <thead>
    <tr>
      <th>순서</th>
      <th>속성</th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>1</td>
      <td>display</td>
    </tr>
    <tr>
      <td>2</td>
      <td>overflow</td>
    </tr>
    <tr>
      <td>3</td>
      <td>float</td>
    </tr>
    <tr>
      <td>4</td>
      <td>position</td>
    </tr>
    <tr>
      <td>5</td>
      <td>top</td>
    </tr>
    <tr>
      <td>6</td>
      <td>right</td>
    </tr>
    <tr>
      <td>7</td>
      <td>bottom</td>
    </tr>
    <tr>
      <td>8</td>
      <td>left</td>
    </tr>
    <tr>
      <td>9</td>
      <td>z-index</td>
    </tr>
    <tr>
      <td>10</td>
      <td>width</td>
    </tr>
    <tr>
      <td>11</td>
      <td>height</td>
    </tr>
    <tr>
      <td>12</td>
      <td>margin</td>
    </tr>
    <tr>
      <td>13</td>
      <td>padding</td>
    </tr>
    <tr>
      <td>14</td>
      <td>border</td>
    </tr>
    <tr>
      <td>15</td>
      <td>font-style</td>
    </tr>
    <tr>
      <td>16</td>
      <td>font-weight</td>
    </tr>
    <tr>
      <td>17</td>
      <td>font-size</td>
    </tr>
    <tr>
      <td>18</td>
      <td>font-family</td>
    </tr>
    <tr>
      <td>19</td>
      <td>line-height</td>
    </tr>
    <tr>
      <td>20</td>
      <td>color</td>
    </tr>
    <tr>
      <td>21</td>
      <td>background-color</td>
    </tr>
    <tr>
      <td>22</td>
      <td>background-image</td>
    </tr>
    <tr>
      <td>23</td>
      <td>background-position</td>
    </tr>
    <tr>
      <td>24</td>
      <td>background-repeat</td>
    </tr>
    <tr>
      <td>25</td>
      <td>background-attachment</td>
    </tr>
    <tr>
      <td>26</td>
      <td>background-size</td>
    </tr>
    <tr>
      <td>27</td>
      <td>기타</td>
    </tr>
  </tbody>
</table>

- font의 선언 순서는 https://www.w3schools.com/cssref/pr_font_font.asp Definition and Usage를 일부 참고하였습니다.
- background의 선언 순서는 https://www.w3schools.com/cssref/css3_pr_background.asp Definition and Usage를 일부 참고하였습니다.

### font 속성 선언 시 주의할 점

font 속성의 값 작성 시 축약형을 가급적 사용하지 않는 것을 권장합니다.<br />
<br />
font 속성 선언 순서는 아래와 같습니다.

<table>
  <thead>
    <tr>
      <th>순서</th>
      <th>속성</th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>1</td>
      <td>font-style</td>
    </tr>
    <tr>
      <td>2</td>
      <td>font-weight</td>
    </tr>
    <tr>
      <td>3</td>
      <td>font-size</td>
    </tr>
    <tr>
      <td>4</td>
      <td>font-family</td>
    </tr>
    <tr>
      <td>5</td>
      <td>line-height</td>
    </tr>
    <tr>
      <td>6</td>
      <td>color</td>
    </tr>
  </tbody>
</table>

### background-position 속성값 선언 시 주의할 점

background-position 속성의 값은 숫자로 작성하는 것을 권장합니다.

```
background-position: center center; // X

background-position: 50% 50%; // O
```

### color 속성 값 선언 시 주의할 점

color 속성 값의 경우 축약이 가능하다면 축약형으로 작성하는 것을 권장합니다.

```
color: #ffffff; // X

color: #fff; // O
```

### !important 사용 시 주의할 점

!important는 가급적 사용을 지양합니다. 하지만 카페24, 그누보드, 워드프레스와 같이 특수한 상황에서는 유연하게 대체해 주세요.

## CSS Cascading

두 개 이상의 속성의 값이 동일한 요소에 적용됐을 때, 우선순위에 따라 값이 적용됩니다. 각 선택자에 따른 우선순위 값은 아래 표와 같으며, 높은 값일수록 우선적으로 적용됩니다.

<table>
  <thead>
    <tr>
      <th>선택자</th>
      <th>값</th>
      <th>예를 들어</th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>inline style</td>
      <td>1000</td>
      <td>style="margin-left: 12px"</td>
    </tr>
    <tr>
      <td>id</td>
      <td>100</td>
      <td>#header { ... }</td>
    </tr>
    <tr>
      <td>class</td>
      <td>10</td>
      <td>.footer { ... }</td>
    </tr>
    <tr>
      <td>element</td>
      <td>1</td>
      <td> div { ... }</td>
    </tr>
  </tbody>
</table>

- 속성 선언 뒤 !important를 사용할 경우 우선순위에 상관없이 적용됩니다.

## Naming

작업을 진행하다 보면 어떤 방식으로 코드를 작성했는지 작성 방법을 잊어버리는 경우가 있습니다.<br />
<br />
그렇기 때문에 기본적인 규칙을 정해서 작성하는 것을 권장합니다.<br />
<br />
이 문서에서는 네이밍 규칙과 Prefix/Subfix/Suffix 부분으로 나뉩니다. 먼저 네이밍 규칙에서는 HTML, CSS, 폴더, 파일의 공통된 네이밍 규칙에 대해 정리합니다.<br />
<br />
그리고 Prefix/Subfix/Suffix에서는 마크업 작업에 대비한 예약어를 소개하면서 이를 조합하는 방식에 대해 설명합니다.

### 네이밍 규칙

네이밍은 형태\_의미 상태 순서로 작성하는 것을 권장합니다.<br />

```
class="grp_local open"

class="btn_local active"
```

- 형태\_의미가 너무 많이 추가되지 않도록 작성하는 것을 권장합니다.

### id/class 규칙

### folder/file 규칙

페이지의 성격에 따라 폴더를 생성하고 해당 폴더 안에 HTML 파일을 생성하는 것을 권장합니다.<br />
<br />
생성되는 HTML의 파일명은 의미\_상태 순서로 작성하는 것을 권장합니다.

```
/gallery/gallery_list.html
```

- 상태는 필요에 따라 작성하는 것을 권장합니다.

### images 규칙

images 폴더를 생성하고 해당 폴더 내부에 이미지 성격에 맞는 폴더를 생성하는 것을 권장합니다.

## Prefix/Subfix/Suffix

prefix는 접두사를 의미하는 것으로 앞부분에 사용하며, 형태를 나타내는 데 사용하는 것을 권장합니다.<br />
<br />
subfix가 필요한 부분은 \_를 사용해서 조합하는 것을 권장합니다.<br />
<br />
prefix 목록에 존재하는 예약어를 가지고 subfix, suffix를 조합해서 작성하는 것을 권장합니다.<br />
<br />

- 이외 네이밍은 의미 전달 가능하도록 작성하는 것을 권장합니다.<br />
  <br />
  prefix를 2개 이상 중복으로 사용해야 할 경우, 기능적인 prefix가 앞부분에 위치할 수 있도록 작성하는 것을 권장합니다.<br />
  <br />
  단독 클래스 사용은 지양하며, prefix를 조합한 형태로 작성하는 것을 권장합니다.<br />
  <br />
  fst, lst, on, hide의 경우 suffix로 적용해서 사용하는 것을 권장합니다.

### prefix 예약어 및 설명

<table>
  <thead>
    <tr>
      <th>유형</th>
      <th>prefix</th>
      <th>설명</th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>제목</td>
      <td>tit_, title_</td>
      <td>&lt;h<em>n</em>&gt; 또는 &lt;strong&gt; 태그에서 사용하는 것을 권장합니다.</td>
    </tr>
    <tr>
      <td rowspan="6">영역</td>
      <td>wrap_, wrapper_</td>
      <td>&lt;body&gt; 태그 바로 아래에 &lt;header&gt;, &lt;container&gt;, &lt;footer&gt; 태그를 묶는데 사용하는 것을 권장합니다.</td>
    </tr>
    <tr>
      <td>inner_</td>
      <td>각 prefix 내부에서 사용합니다. _ 뒤의 subfix는 prefix를 따라갑니다.<br />이 prefix는 wrap_, wrapper_을 감쌀 수 없습니다.</td>
    </tr>
    <tr>
      <td>sec_, section_</td>
      <td>&lt;h<em>n</em>&gt; 태그가 존재하는 영역에서 사용하는 것을 권장합니다. (선택적으로 사용합니다.)<br />이 prefix는 wrap_, wrapper_을 감쌀 수 없습니다.</td>
    </tr>
    <tr>
      <td>grp_, group_</td>
      <td>컴포넌트 단위로 마크업을 작성할 때 사용하는 것을 권장합니다.<br />이 prefix는 wrap_, wrapper_, sec_, section_을 감쌀 수 없습니다.</td>
    </tr>
    <tr>
      <td>box_</td>
      <td>grp_, group_ 보다 작은 단위로 마크업을 작성할 때 사용하는 것을 권장합니다.<br />이 prefix는 wrap_, wrapper_, sec_, section_을 감쌀 수 없습니다.<br />이 prefix는 grp_, group_ 감쌀 수 있습니다.</td>
    </tr>
    <tr>
      <td colspan="2">wrap_, wrapper_ &gt; inner_ == sec_, section_ &gt; inner_ == grp_, group_ == box_</td>
    </tr>
    <tr>
      <td rowspan="3">메뉴 영역</td>
      <td>gnb_</td>
      <td>주메뉴 영역을 마크업 할 때 사용하는 것을 권장합니다.</td>
    </tr>
    <tr>
      <td>lnb_</td>
      <td>주메뉴 내부의 지역 메뉴를 마크업 할 때 사용하는 것을 권장합니다.</td>
    </tr>
    <tr>
      <td>snb_</td>
      <td>왼쪽, 오른쪽 사이드 메뉴를 마크업 할 때 사용하는 것을 권장합니다.</td>
    </tr>
    <tr>
      <td>탭 메뉴 영역</td>
      <td>tab_</td>
      <td>탭 메뉴 영역을 마크업 할 때 사용하는 것을 권장합니다.<br />만약, &lt;ul&gt; 이 tab 메뉴라면 class="list_tab"으로 작성하는 것을 권장합니다.</td>
    </tr>
    <tr>
      <td>테이블</td>
      <td>tbl_</td>
      <td>&lt;table&gt; 태그에서 사용하는 것을 권장합니다.</td>
    </tr>
    <tr>
      <td>목록</td>
      <td>list_</td>
      <td>&lt;ol&gt;, &lt;ul&gt;, &lt;dl&gt; 태그에서 사용하는 것을 권장합니다.</td>
    </tr>
    <tr>
      <td rowspan="5">입력 양식 영역</td>
      <td>textfield_, tf_</td>
      <td>&lt;input type="text, password" /&gt; 처럼 text field 일 때 사용하는 것을 권장합니다.</td>
    </tr>
    <tr>
      <td>inp_</td>
      <td>&lt;input type="checkbox, radio" /&gt; 처럼 checkbox, radio 일 때 사용하는 것을 권장합니다.</td>
    </tr>
    <tr>
      <td>slct_, opt_</td>
      <td>&lt;select&gt; 태그에서 사용하는 것을 권장합니다.</td>
    </tr>
    <tr>
      <td>label_, lab_</td>
      <td>&lt;label&gt; 태그에서 사용하는 것을 권장합니다.</td>
    </tr>
    <tr>
      <td>fldst_, fld_</td>
      <td>&lt;fieldset&gt; 태그에서 사용하는 것을 권장합니다.</td>
    </tr>
    <tr>
      <td>버튼</td>
      <td>btn_</td>
      <td>&lt;button&gt; 태그에서 사용하는 것을 권장합니다.</td>
    </tr>
    <tr>
      <td>링크</td>
      <td>link_</td>
      <td>&lt;a&gt; 태그에서 사용하는 것을 권장합니다.</td>
    </tr>
    <tr>
      <td>아이콘</td>
      <td>ico_</td>
      <td>배경으로 아이콘 이미지가 들어가는 태그에서 사용하는 것을 권장합니다.<br />예를 들어 &lt;span class="ico_local"&gt;</td>
    </tr>
    <tr>
      <td>배경</td>
      <td>bg_</td>
      <td>배경 이미지로 들어가는 태그에서 사용하는 것을 권장합니다.<br />예를 들어, &lt;span class="bg_local"&gt;</td>
    </tr>
    <tr>
      <td>섬네일 이미지 영역</td>
      <td>thumb_</td>
      <td>&lt;img /&gt; 태그를 감싸는 영역 마크업을 작성할 때 사용하는 것을 권장합니다.</td>
    </tr>
    <tr>
      <td>페이징</td>
      <td>paging_</td>
      <td>게시판 하단 페이징 마크업을 할 때 사용하는 것을 권장합니다.</td>
    </tr>
    <tr>
      <td>텍스트</td>
      <td>txt_</td>
      <td>문자를 감싸는 마크업을 작성할 때 사용하는 것을 권장합니다.</td>
    </tr>
    <tr>
      <td>번호</td>
      <td>num_</td>
      <td>숫자를 감싸는 마크업을 작성할 때 사용하는 것을 권장합니다.<br />하지만 숫자 아이콘이 들어갈 경우 num_, number_ prefix를 사용하지 않고 ico_ prefix를 사용하는 것을 권장합니다.</td>
    </tr>
    <tr>
      <td>카피라이터</td>
      <td>copyright_, copy_</td>
      <td></td>
    </tr>
    <tr>
      <td>시간</td>
      <td>time_</td>
      <td>날짜 및 시간을 감싸는 마크업을 작성할 때 사용하는 것을 권장합니다.<br />하지만 txt_, text_로 대체하는 것을 권장합니다.</td>
    </tr>
    <tr>
      <td>강조</td>
      <td>emph_</td>
      <td>emphasis (강조)의 축약형으로 강조가 필요한 텍스트를 감쌀 때 &lt;em&gt; 태그에서 사용하는 것을 권장합니다.</td>
    </tr>
    <tr>
      <td rowspan="2">순서</td>
      <td>fst</td>
      <td></td>
    </tr>
    <tr>
      <td>lst</td>
      <td></td>
    </tr>
    <tr>
      <td>팝업</td>
      <td>popup_</td>
      <td>팝업 전체를 감싸는 마크업을 작성할 때 사용하는 것을 권장합니다.</td>
    </tr>
    <tr>
      <td>레이어</td>
      <td>layer_, ly_</td>
      <td>레이어 팝업 전체를 감싸는 마크업을 작성할 때 사용하는 것을 권장합니다.</td>
    </tr>
    <tr>
      <td>광고 영역</td>
      <td>ad_</td>
      <td>광고 영역을 감싸는 마크업을 작성할 때 사용하는 것을 권장합니다.<br />※ 광고 차단 프로그램이 활성화되어있을 경우 해당 영역이 노출되지 않으니 상황에 맞게 고려해서 사용해 주세요.</td>
    </tr>
    <tr>
      <td>설명</td>
      <td>desc_</td>
      <td>상세 설명이 필요한 영역에서 사용하는 것을 권장합니다.<br />&lt;span class="desc_"&gt;, &lt;dl class="desc_"&gt;</td>
    </tr>
    <tr>
      <td>댓글</td>
      <td>comment_, cmt_</td>
      <td>댓글 관련 마크업을 작성할 때 사용하는 것을 권장합니다.</td>
    </tr>
  </tbody>
</table>

### subfix 예약어 및 설명

<table>
  <thead>
    <tr>
      <th>유형</th>
      <th>subfix</th>
      <th>설명</th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>공통</td>
      <td>_comm</td>
      <td>공통적으로 사용하는 영역에서 사용하는 것을 권장합니다.</td>
    </tr>
    <tr>
      <td>위치</td>
      <td>_top, _right, _bot, _left, _mid</td>
      <td></td>
    </tr>
    <tr>
      <td>순서</td>
      <td>_fst, _lst</td>
      <td></td>
    </tr>
    <tr>
      <td>화살표</td>
      <td>_arr, _arrow</td>
      <td>화살표 아이콘에서 주로 사용하는 것을 권장합니다. 항목의 위치와 함께 사용할 수 있습니다.</td>
    </tr>
    <tr>
      <td rowspan="2">버튼 상태</td>
      <td>_nor, _normal</td>
      <td rowspan="2">버튼의 상태가 기본 값일 경우 사용하는 것을 권장합니다.</td>
    </tr>
    <tr>
      <td>_default</td>
    </tr>
    <tr>
      <td>방향</td>
      <td>_hori, _vert</td>
      <td></td>
    </tr>
    <tr>
      <td>카테고리</td>
      <td>_category, _cate</td>
      <td></td>
    </tr>
    <tr>
      <td>순위</td>
      <td>_ranking, _rank</td>
      <td></td>
    </tr>
    <tr>
      <td>상단 고정형 탭 메뉴</td>
      <td>_sticky</td>
      <td>스크롤 했을 때 상단에 고정되는 유형의 탭 메뉴를 마크업 할 때 사용하는 것을 권장합니다.</td>
    </tr>
    <tr>
      <td>페이징</td>
      <td>_paging</td>
      <td>게시판 하단 페이징 마크업을 할 때 사용하는 것을 권장합니다.</td>
    </tr>
    <tr>
      <td>페이지 번호</td>
      <td>_page</td>
      <td>게시판 하단 페이지 번호 마크업을 할 때 사용하는 것을 권장합니다.</td>
    </tr>
    <tr>
      <td>페이지</td>
      <td>_prev, _previous, _next</td>
      <td>게시판 하단 페이지 이전, 다음 마크업을 할 때 사용하는 것을 권장합니다.</td>
    </tr>
    <tr>
      <td>카피라이터</td>
      <td>_copyright, _copy</td>
      <td></td>
    </tr>
    <tr>
      <td>광고 영역</td>
      <td>_ad</td>
      <td>광고 영역을 감싸는 마크업을 작성할 때 사용하는 것을 권장합니다.<br />※ 광고 차단 프로그램이 활성화되어있을 경우 해당 영역이 노출되지 않으니 상황에 맞게 고려해서 사용해 주세요.</td>
    </tr>
    <tr>
      <td>댓글</td>
      <td>_comment, _cmt</td>
      <td>댓글 관련 마크업을 작성할 때 사용하는 것을 권장합니다.</td>
    </tr>
  </tbody>
</table>

### suffix 예약어 및 설명

<table>
  <thead>
    <tr>
      <th>유형</th>
      <th>suffix</th>
      <th>설명</th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>상태</td>
      <td>on, off, over, focus, current, active</td>
      <td></td>
    </tr>
    <tr>
      <td>위치</td>
      <td>top, right, bot, left, mid</td>
      <td></td>
    </tr>
    <tr>
      <td>순서</td>
      <td>fst, lst</td>
      <td></td>
    </tr>
    <tr>
      <td>이전, 다음</td>
      <td>prev, previous, next</td>
      <td></td>
    </tr>
  </tbody>
</table>

- 상태를 나타내는 데 사용하는 것을 권장합니다.

## Image

### 이미지 스프라이트 가이드 및 이미지 압축

운영 성격의 이미지가 아닌 아이콘 위주의 이미지 요소들을 한곳에 모아 이미지 스프라이트 기법을 사용해 관리한다면 파일 호출에 대한 자원 낭비 최소화와 실무자 간의 이미지 파일명 중복 문제 해결을 기대할 수 있습니다.<br />
<br />
가로형, 세로형 이미지 스프라이트의 경우 이미지가 계속 추가됐을 때 필요 공간도 같이 늘어나 바둑판 형태의 이미지 스프라이트로 작성하는 것을 권장합니다.<br />
<br />
각 스프라이트 이미지는 프로젝트 규모가 클 경우 주메뉴, 타이틀, 텍스트, 숫자, 아이콘, 버튼 등으로 나누어 사용하는 것을 권장합니다.<br />
<br />
각 이미지 배치 시 이미지의 간격은 10px 단위로 하는 것을 권장합니다.<br />
<br />
on, off 이미지의 경우 비활성화된 이미지가 위, 활성화된 버튼의 이미지가 아래에 위치하도록 배치하는 것을 권장합니다.<br />
<br />
이미지 압축은 아래 사이트를 이용할 것을 권장합니다.<br />
<br />
https://tinypng.com/
