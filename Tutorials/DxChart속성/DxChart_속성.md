
> **DXChart 개발자 튜토리얼**
>
> **(Nexacro용)**
---

**\[목 차\]**
각각의 목차를 클릭시 해당 페이지로 이동합니다




 [**2.** **DxChart 속성**](#DxChart-속성)
   - [Margin (옵션 - margin 그룹)](#margin-옵션---margin-그룹)
   - [X축 (옵션 - xaxis 그룹)](#text-property-예제)
   - [Y축 (옵션 - yaxis 그룹)](#y축-옵션-yaxis-그룹)
   - [배경 (옵션 - background 그룹)](#\_Toc162962562)
   - [제목 (옵션 - title 그룹)](#제목-옵션-title-그룹)
   - [범례](#_Toc162962564)
   - [툴팁](#_Toc162962565)
   - [라벨 (옵션 - labels 그룹)](#\_Toc162962566)
   - [그외](#_Toc162962570)






# **DxChart 속성**

## 차트 주요 Properties

### Margin (옵션 - margin 그룹)

![Margin](../../assets/img/image23.png)

![Margin2](../../assets/img/image24.png)

  <table>
    <tr>
      <th style="text-align: center;">Sub property</th>
      <th style="text-align: center;">설명</th>
      <th style="text-align: center;">타입</th>
      <th style="text-align: center;">기본값</th>
    </tr>
    <tr>
      <td style="text-align: center;">Bottom</td>
      <td style="text-align: center;">차트의 아래쪽 여백을 설정합니다.</td>
      <td style="text-align: center;">number</td>
      <td style="text-align: center;">35</td>
    </tr>
    <tr>
      <td style="text-align: center;">Inner</td>
      <td style="text-align: center;">차트의 내부 여백을 설정합니다.</td>
      <td style="text-align: center;">number</td>
      <td style="text-align: center;">5</td>
    </tr>
    <tr>
      <td style="text-align: center;">InnerGrouped</td>
      <td style="text-align: center;">그룹화된 차트에서 동일한 그룹에 있는 요소 사이의 여백입니다.</td>
      <td style="text-align: center;">number</td>
      <td style="text-align: center;">1</td>
    </tr>
    <tr>
      <td style="text-align: center;">Left</td>
      <td style="text-align: center;">차트의 왼쪽 여백을 설정합니다.</td>
      <td style="text-align: center;">number</td>
      <td style="text-align: center;">35</td>
    </tr>
    <tr>
      <td style="text-align: center;">Right</td>
      <td style="text-align: center;">차트의 오른쪽 여백을 설정합니다.</td>
      <td style="text-align: center;">number</td>
      <td style="text-align: center;">35</td>
    </tr>
    <tr>
      <td style="text-align: center;">Top</td>
      <td style="text-align: center;">차트의 위쪽 여백을 설정합니다.</td>
      <td style="text-align: center;">number</td>
      <td style="text-align: center;">35</td>
    </tr>
  </table>



#### Margin 사용 예제

아래는 차트의 Margin Properties 설정하기 튜토리얼 입니다.


![Margin3](../../assets/img/image25.png)

```javascript
      var bar = new DxChartBar({
        id: cvs,
        elem : canvas,
        binddataset : this.Dataset00,
        data:["bind:total","bind:man","bind:woman"],
        options: {
            margin: { 
            Left: 100,    // 차트의 왼쪽 여백 값을 설정할수 있습니다.
            Right: 100,  // 차트의 오른쪽 여백 값을 설정할수 있습니다.
            Top: 50,     // 차트의 위쪽 여백 값을 설정할수 있습니다.
            Bottom: 50,  // 차트의 아래쪽 여백 값을 설정할수 있습니다.
            Inner : 20,  // 차트의 내부의 여백 값을 설정할수 있습니다.
            InnerGroupued : 20  // 차트의 그룹 사이 여백 값을 설정할수 있습니다.
      },
        }.
      }).draw();


```
#### Text Property 예제

차트 내부에 렌더링 되는 모든 Text 값들의 색상, Font Style을 지정할 수
있습니다. title, X축라벨, Y축라벨 등 모든 텍스트 값들을 제어할 수
있습니다.

![Text](../../assets/img/image26.png)

```javascript

var bar = new DxChartBar({

id: cvs,
elem : canvas,
binddataset : this.Dataset00,
data:["bind:total","bind:man","bind:woman"],
options: {
    text: {
    Color:'Blue', // text 색상을 설정할수 있습니다. 위의 예제에선 Y축 라벨색상입니다.
    FontStyle: '20px bold Pretendard' // Text FontStyle을 설정할 수 있습니다.
    }
}
}).draw();
```

### 제목 (옵션- title 그룹)

![Title](../../assets/img/image27.png)

<style>
    table {
        border-collapse: collapse;
        width: 80%;
        margin: auto; /* 테이블을 가운데 정렬 */
    }
    th, td {
        border: 1px solid black;
        text-align: center; /* 텍스트를 가운데 정렬 */
        padding: 10px;
    }
    th {
        background-color: #f2f2f2;
    }
</style>

<table>
    <tr>
        <th>Sub property</th>
        <th>설명</th>
        <th>타입</th>
        <th>기본값</th>
    </tr>
    <tr>
        <td>Color</td>
        <td>제목의 색을 지정합니다.</td>
        <td>object</td>
        <td>null</td>
    </tr>
    <tr>
        <td>FontStyle</td>
        <td>제목의 글꼴 스타일을 지정합니다.</td>
        <td>string</td>
        <td>null</td>
    </tr>
    <tr>
        <td>Halign</td>
        <td>제목의 가로 정렬을 지정합니다. left, right, center를 사용할 수 있습니다.</td>
        <td>object</td>
        <td>null</td>
    </tr>
    <tr>
        <td>OffsetX</td>
        <td>제목의 가로 오프셋을 지정합니다.</td>
        <td>number</td>
        <td>0</td>
    </tr>
    <tr>
        <td>OffsetY</td>
        <td>제목의 세로 오프셋을 지정합니다.</td>
        <td>number</td>
        <td>0</td>
    </tr>
    <tr>
        <td>Subtitle</td>
        <td>차트의 부제목을 지정합니다. 제목 바로 아래에 생기기 때문에 마진을 주지 않으면 제목이 제대로 보이지 않을 수 있습니다.</td>
        <td>string</td>
        <td></td>
    </tr>
    <tr>
        <td>SubtitleColor</td>
        <td>부제목의 색을 지정합니다.</td>
        <td>string</td>
        <td>#aaa</td>
    </tr>
    <tr>
        <td>SubtitleFontStyle</td>
        <td>부제목의 글꼴 스타일을 지정합니다.</td>
        <td>string</td>
        <td>null</td>
    </tr>
    <tr>
        <td>SubtitleOffsetX</td>
        <td>부제목의 가로 오프셋을 지정합니다.</td>
        <td>number</td>
        <td>0</td>
    </tr>
    <tr>
        <td>SubtitleOffsetY</td>
        <td>부제목의 세로 오프셋을 지정합니다.</td>
        <td>number</td>
        <td>0</td>
    </tr>
    <tr>
        <td>Text</td>
        <td>중앙 상단의 제목을 지정합니다.</td>
        <td>string</td>
        <td></td>
    </tr>
    <tr>
        <td>Valign</td>
        <td>제목의 세로 정렬을 지정합니다. top, bottom, center를 사용할 수 있습니다.</td>
        <td>object</td>
        <td>null</td>
    </tr>
    <tr>
        <td>X</td>
        <td>제목의 가로 좌표를 지정합니다.</td>
        <td>object</td>
        <td>null</td>
    </tr>
    <tr>
        <td>Y</td>
        <td>제목의 세로 좌표를 지정합니다.</td>
        <td>object</td>
        <td>null</td>
    </tr>
</table>



#### Title Property 예제
![Title](../../assets/img/image28.png)

```javascript
    var bar = new DxChartBar({
    id: cvs,
    elem : canvas,
    binddataset : this.Dataset00,
    data:["bind:total","bind:man","bind:woman"],
    options: {
    title: { 
      Text : 'DxChart 튜토리얼', // 차트의 title Text값을설정합니다.
      FontStyle: '32px bold Pretendard', // title FontStyle을 설정할 수 있습니다.
      Y :73, // 차트 내 title의 Y 위치값을 설정 할수 있습니다.
      X: 450 // 차트 내 title의 X 위치값을 설정 할수 있습니다.
      },
    }
    }).draw();
```

### 제목(옵션 -Subtitle)

DxChart는 Main Title 외에 차트의 부제목 또한 설정할 수 있습니다. 같은
title Properties내에 Subtitle

옵션값으로 설정 할 수 있습니다.

<table text-align="center"  cellpadding="5" cellspacing="0">
  <tr>
    <th>Sub property</th>
    <th>설명</th>
    <th>타입</th>
    <th>기본값</th>
  </tr>
  <tr>
    <td>Subtitle</td>
    <td>차트의 부제목을 지정합니다.<br>제목 바로 아래에 생기기 때문에 마진을 주지 않으면 제목이 제대로 보이지 않을 수 있습니다.</td>
    <td>string</td>
    <td></td>
  </tr>
  <tr>
    <td>SubtitleColor</td>
    <td>부제목의 색을 지정합니다.</td>
    <td>string</td>
    <td>#aaa</td>
  </tr>
  <tr>
    <td>SubtitleFontStyle</td>
    <td>부제목의 글꼴 스타일을 지정합니다.</td>
    <td>string</td>
    <td>null</td>
  </tr>
  <tr>
    <td>SubtitleOffsetX</td>
    <td>부제목의 가로 오프셋을 지정합니다.</td>
    <td>number</td>
    <td>0</td>
  </tr>
  <tr>
    <td>SubtitleOffsetY</td>
    <td>부제목의 세로 오프셋을 지정합니다.</td>
    <td>number</td>
    <td>0</td>
  </tr>
</table>

#### SubTitle Property 예제 

![Subtitle](../../assets/img/image29.png)

```javascript
var bar = new DxChartBar({
id: cvs,
elem : canvas,
binddataset : this.Dataset00,
data:["bind:total","bind:man","bind:woman"],
options: {
      title: {
         Text : 'DxChart 튜토리얼', // 차트의 title Text값을설정합니다.
        Subtitle: '차트 제목 만들기', // 차트의 부제목을 설정할 수있습니다.
         SubtitleFontStyle : '24px Pretendard' // 차트 부제목의 폰트스타일을 설정 할 수 있습니다.
        // SubtitleOffsetY: 103 // 차트 부제목의 Offset Y 좌표 위치를 설정 할 수있습니다. X 좌표 위치값 변경도 가능합니다.
      },
}
}).draw();
```

### X축 (옵션 - xaxis 그룹)

차트의 X축에 대한 설정을 하는 Property입니다.

![Xaixs](../../assets/img/image30.png)

![Xaixs2](../../assets/img/image31.png)

<table text-align="center"  border="1" cellpadding="5" cellspacing="0">
  <tr>
    <th>Sub property</th>
    <th>설명</th>
    <th>타입</th>
    <th>기본값</th>
  </tr>
  <tr>
    <td>AddLineSize</td>
    <td>x축 선의 길이를 지정합니다.<br>양수이면 원점에서 왼쪽으로 x축 길이가 늘어나며 음수이면 원점에서 오른쪽으로 x축 길이가 줄어듭니다.</td>
    <td>number</td>
    <td>0</td>
  </tr>
  <tr>
    <td>Color</td>
    <td>x축 선의 색을 지정합니다.</td>
    <td>string</td>
    <td>black</td>
  </tr>
  <tr>
    <td>Labels</td>
    <td>x축에서 사용할 라벨을 지정합니다.<br>라벨은 html 태그 형식 또는 배열 형태로 사용할 수 있습니다.</td>
    <td>object</td>
    <td>null</td>
  </tr>
  <tr>
    <td>LabelsAngle</td>
    <td>x축 라벨의 각도를 지정합니다.<br>양수일 때 지정한 각도만큼 왼쪽으로 회전하며 음수일 때 오른쪽으로 회전합니다.</td>
    <td>number</td>
    <td>0</td>
  </tr>
  <tr>
    <td>LabelsColor</td>
    <td>x축 라벨의 색을 지정합니다.</td>
    <td>object</td>
    <td>null</td>
  </tr>
  <tr>
    <td>LabelsFontStyle</td>
    <td>x축 라벨의 글꼴 스타일을 지정합니다.</td>
    <td>string</td>
    <td>null</td>
  </tr>
  <tr>
    <td>LabelsFormattedDecimals</td>
    <td>x축에서 %{value_formatted}처럼 형식이 지정된 라벨에서 지정한 값만큼의 소수점을 표시합니다.</td>
    <td>number</td>
    <td>0</td>
  </tr>
  <tr>
    <td>LabelsFormattedPoint</td>
    <td>x축에서 %{value_formatted}처럼 형식이 지정된 라벨에서 소수점 표시 방식을 지정합니다.</td>
    <td>string</td>
    <td>.</td>
  </tr>
  <tr>
    <td>LabelsFormattedThousand</td>
    <td>x축에서 %{value_formatted}처럼 형식이 지정된 라벨에서 천 단위 구분 기호를 지정합니다.</td>
    <td>string</td>
    <td>,</td>
  </tr>
  <tr>
    <td>LabelsFormattedUnitsPost</td>
    <td>x축에서 %{value_formatted}처럼 형식이 지정된 라벨에서 뒤에 표시할 문자를 지정합니다.</td>
    <td>string</td>
    <td></td>
  </tr>
  <tr>
    <td>LabelsFormattedUnitsPre</td>
    <td>x축에서 %{value_formatted}처럼 형식이 지정된 라벨에서 앞에 표시할 문자를 지정합니다.</td>
    <td>string</td>
    <td></td>
  </tr>
  <tr>
    <td>LabelsHalign</td>
    <td>x축 라벨의 가로 정렬을 지정합니다. left, right, center를 사용할 수 있습니다.</td>
    <td>object</td>
    <td>null</td>
  </tr>
  <tr>
    <td>LabelsOffsetX</td>
    <td>x축 라벨의 가로 오프셋을 지정합니다.</td>
    <td>number</td>
    <td>0</td>
  </tr>
  <tr>
    <td>LabelsOffsetY</td>
    <td>x축 라벨의 세로 오프셋을 지정합니다.</td>
    <td>number</td>
    <td>0</td>
  </tr>
  <tr>
    <td>LabelsPosition</td>
    <td>x축 라벨의 포지션을 지정합니다. section, edge를 사용할 수 있습니다. section은 영역쪽에 라벨이 위치하고 edge는 데이터 포인트 점에 라벨이 위치합니다.</td>
    <td>string</td>
    <td>section</td>
  </tr>
  <tr>
    <td>LabelsValign</td>
    <td>라벨의 세로 정렬을 지정합니다. top, bottom, center를 사용할 수 있습니다.</td>
    <td>object</td>
    <td>null</td>
  </tr>
  <tr>
    <td>Linewidth</td>
    <td>x축의 두께를 지정합니다.</td>
    <td>number</td>
    <td>1</td>
  </tr>
  <tr>
    <td>Position</td>
    <td>x축의 위치를 지정합니다. top, bottom, center를 사용할 수 있습니다.</td>
    <td>string</td>
    <td>bottom</td>
  </tr>
  <tr>
    <td>Tickmarks</td>
    <td>x축 라벨에 눈금을 표시할 지 여부입니다.</td>
    <td>boolean</td>
    <td>true</td>
  </tr>
  <tr>
    <td>TickmarksCount</td>
    <td>x축 라벨의 눈금 개수를 지정합니다.</td>
    <td>object</td>
    <td>null</td>
  </tr>
  <tr>
    <td>TickmarksLastLeft</td>
    <td>x축 라벨의 가장 왼쪽 마크를 표시할 지 여부입니다.</td>
    <td>object</td>
    <td>null</td>
  </tr>
  <tr>
    <td>TickmarksLastRight</td>
    <td>x축 라벨의 가장 오른쪽 마크를 표시할 지 여부입니다.</td>
    <td>object</td>
    <td>null</td>
  </tr>
  <tr>
    <td>TickmarksLength</td>
    <td>x축 라벨의 데이터마다 위치한 마크값의 길이를 지정합니다.</td>
    <td>number</td>
    <td></td>
  </tr>
  <tr>
    <td>Title</td>
    <td>x축의 제목을 지정합니다.</td>
    <td>string</td>
    <td></td>
  </tr>
  <tr>
    <td>TitleColor</td>
    <td>x축 제목의 색상을 지정합니다.</td>
    <td>object</td>
    <td>null</td>
  </tr>
  <tr>
    <td>TitleFontStyle</td>
    <td>x축 제목의 글꼴 스타일을 지정합니다.</td>
    <td>string</td>
    <td>null</td>
  </tr>
  <tr>
    <td>TitleHalign</td>
    <td>x축 제목의 가로 정렬을 지정합니다. 'left', 'right', 'center'를 사용할 수 있습니다.</td>
    <td>string</td>
    <td>center</td>
  </tr>
  <tr>
    <td>TitleOffsetX</td>
    <td>x축 제목의 가로 오프셋을 지정합니다.</td>
    <td>number</td>
    <td>0</td>
  </tr>
  <tr>
    <td>TitleOffsetY</td>
    <td>x축 제목의 세로 오프셋을 지정합니다.</td>
    <td>number</td>
    <td>0</td>
  </tr>
  <tr>
    <td>TitlePos</td>
    <td>x축 제목의 위치를 지정합니다. 양수일 때 아래로 내려가고 음수일 때 위로 올라갑니다.</td>
    <td>object</td>
    <td>null</td>
  </tr>
  <tr>
    <td>TitleValign</td>
    <td>x축 제목의 수직 정렬을 지정합니다. top, bottom, center를 사용할 수 있습니다.</td>
    <td>string</td>
    <td>top</td>
  </tr>
  <tr>
    <td>TitleX</td>
    <td>x축 제목의 가로 좌표를 지정합니다.</td>
    <td>object</td>
    <td>null</td>
  </tr>
  <tr>
    <td>TitleY</td>
    <td>x축 제목의 세로 좌표를 지정합니다.</td>
    <td>object</td>
    <td>null</td>
  </tr>
  <tr>
    <td>Use</td>
    <td>x축을 사용할 지 여부입니다.</td>
    <td>boolean</td>
    <td>true</td>
  </tr>
</table>


#### X축 Property 기본 예제

![Xaxis](../../assets/img/image32.png)


```javascript
var bar = new DxChartBar({

    id: cvs,
    elem : canvas,
    binddataset : this.Dataset00,
    data:["bind:total","bind:man","bind:woman"],
    options: {
        xaxis: {
          Use : false, // 차트의 X축을 Draw 할지 설정할 수 있습니다.
          Labels: ["bind:indecators"], // X축 라벨의 데이터 값을 설 정할 수있습니다. 주로 Nexacro 내 Dataset 바인딩을 통해 데이터 값을 설정 합니다. Nexacro가 아닌 다른 프레임워크나 실행환경에선 배열값으로 설정할수있습니다.
     //   ex) Lables :\['1','2','3','4','5'\]
          AddLineSize : 10, // X축 선의 길이 값을 설정 할 수 있습니다. }
          Color : 'red', // X축의 색상을 설정 할 수 있습니다.
          Position: 'bottom' // X축의 위치를 설정 할 수 있습니다. 기본값은bottom이며,top, bottom 두가지 값으로 설정 할 수 있습니다.X축의 Position을 top으로 설정 할 시 차트가 상하반전이 되어 렌더링됩니다.        
      }
    }
  }).draw();
  ```

#### ![스크린샷, 텍스트, 직사각형, 사각형이(가) 표시된 사진 자동 생성된 설명](media/image33.png){width="7.579166666666667in" height="3.392361111111111in"}X축 Labels 기본 예제

var bar = new DxChartBar({

id: cvs,

elem : canvas,

binddataset : this.Dataset00,

data:\[\"bind:total\",\"bind:man\",\"bind:woman\"\],

options: {

names: DxChart.convertDataset(this.Dataset00,\[\'bind:year\'\]),

// Labels formatted 사용을 위해 names프로퍼티 선언후, 데이터셋바인딩을
해줍니다.

// 프로퍼티 이름은 자유롭게 사용이 가능합니다.

xaxis: { Use : true,

Labels: \'%{property:names\[%{index}\]} (%{value_formatted})\',

// 현재 예제에서는 Labels formatted 기능을 사용하기위해 글로벌 내장 함수
사용을 합니다.

// Labels formatted 기능을 제외할시, 기존과 동일하게 dataset바인딩이나,
배열 데이터로 선언합니다.

LineWidth : 5, // 차트의 X축 Line의 두께 값을 설정 할 수 있습니다..

LabelsAngle : 5, // 차트의 X축 Labels의 각도를 설정 할 수 있습니다. 양수
음수 모두 가능합니다.

LabelsColor: \'blue\', // 차트의 X축 Labels의 색상을 설정할 수 있습니다.

LabelsOffsetY:15, // 차트의 X축 OffsetY 좌표 값을 설정 할 수 있습니다.

LabelsFontStyle: \'24px bold Pretendard\', // X축 Labels의 FonstStyle을
설정할수 있습니다.

LabelsFormattedDecimals : 1, // X축 Labels의 표시되는 소수점 수를 설정
할 수 있습니다.

LabelsFormattedPoint:\".\", // X축 Labels의 표시되는 소수점 문자를
설정할 수 있습니다.

LabelsFormattedThousand:\",\", //X축 Labels의 표시되는 천단위 구분점을
설정할 수 있습니다.

LabelsFormattedUnitsPost:\" μg/m³\", //X축 Labels 뒤에오는 구분문자를
설정할 수 있습니다.

LabelsFormattedUnitsPre:\"\$\", //X축 Labels 앞에오는 구분문자를 설정할
수 있습니다.

LabelsHalign : \'center\', //X축 Labels의 가로정렬 방향을 설정할수
있습니다. (left,right,center).

LabelsOffsetX : 0, //X축 Labels의 OffsetX 위치값을 설정할 수 있습니다.

LabelsOffsetY : 0, //X축 Labels의 OffsetY 위치값을 설정할 수 있습니다.

LabelsPosition :\'section\', //X축 Labels의 Position값을 설정할 수
있습니다. (section, edge)

#### 추가 예제 xaxisLabelsFormatter

LabelsFormatter Properties는 차트의 데이터 값이나 라벨 데이터의 명확성을
제시할 수 있습니다. 기존 데이터에 추가적인 String값이나 특정 값을 붙여
줌으로써 해당 데이터의 명료성을 더해 줄 수 있습니다.

xaxisLabelsFormatter를 만들 때 사용할 수 있는 매크로는 다음과 같습니다.

### 인덱스 매크로

> %{index}

-   이 매크로는 레이블의 인덱스를 표시합니다. 자바스크립트 배열과 같이
    0부터 시작하는 점을 유의해야 합니다.

### 속성 매크로

%{property:myProperties\[%{index}\]}

-   이 매크로는 템플릿 문자열에서 객체의 속성을 참조할 수 있게 해줍니다.
    예를 들어, 위의 이름 속성을 설정하고 템플릿 문자열에서 참조할 수
    있습니다. 속성 매크로 사용시, 해당 속성에 사용될 변수를 반드시
    할당하고 사용해야 합니다.

### 값 매크로

%{value}, %{value_formatted}

-   인덱스와 속성 매크로가 라벨에 명시될 값을 선언한다면, 값 매크로는
    명시될 값 뒤에 Formate value를 설정할수 있습니다. 따라서
    FormattedPost, FormattedPre 프로퍼티와 항상 함께 사용해야합니다.

> Ex) xaxis : {
>
> Labels: %{index} %{value_formatted} //인덱스매크로

Labels: %{property:myProperties\[%{index}\]} %{value_formatted} // 속성
매크로

> //속성 매크로 사용시 항상 프로터피 오브젝트를 생성해주어야합니다.
>
> myProperties : \['1','2,'3','4,',,, \] ,
>
> myProperties : DxChart.convertDataset(this.Dataset, \['bind:data'\])
>
> }

### 전역변수 매크로

> %{global:myVariable} %{global:myVariable\[%{index}\]}

-   이 매크로는 템플릿 문자열에서 전역 변수를 참조할 수 있게 합니다.
    이를 통해 차트 객체의 속성으로 데이터를 설정하는 것보다 쉽게
    데이터를 참조할 수 있습니다.

### 함수 호출 매크로

> %{function:myFunction()} %{function:myFunction(%{index})}

-   이 매크로는 함수를 호출하여 반환 값을 레이블 텍스트로 사용할 수 있게
    합니다. 인수를 전달하지 않고 함수를 호출할 수도 있으며, 인덱스를
    인수로 전달할 수도 있습니다.

> Ex)
>
> this.fnDraw = function()
>
> {
>
> var chart = this.ChartJS00;
>
> var canvas = chart.getCanvas();
>
> var cvs = canvas.id;
>
> DxChart.reset(canvas);
>
> //전역변수를 선언해줍니다.
>
> myVariable = \[..........\]
>
> var bar = new DxChartBar({
>
> id: cvs,
>
> elem : canvas,
>
> binddataset : this.Dataset00,
>
> data:\[\"bind:val\"\],
>
> options: {
>
> xaxis:{
>
> Labels: '%{global:myVariable\[%{index}\]} (%{value_formatted})',
>
> LabelsFormattedUnitsPost: \'μg/m³\', //(%{value_formatted}) 값 뒤에
> 붙을 Format입니다
>
> LabelsFormattedDecimals: 1,
>
> LabelsFormattedPoint: \',\',
>
> LabelsFormattedThousand: \',,\',
>
> LabelsFormattedUnitsPre:
>
> },

#### X축 Property 기본 예제( Tickmarks, Title 관련)

![스크린샷, 라인, 도표, 직사각형이(가) 표시된 사진 자동 생성된
설명](media/image34.png){width="7.579166666666667in"
height="3.1958333333333333in"}

var bar = new DxChartBar({

id: cvs,

elem : canvas,

binddataset : this.Dataset00,

data:\[\"bind:total\",\"bind:man\",\"bind:woman\"\],

options: {

xaxis: { Use : true,

Labels: \[\'bind:indecators\'\],

Tickmarks:true, // X축 Labels에 눈금 사용 여부를 설정 할 수 있습니다.
기본값은 true입니다.

TickmarksCount:15, // X축 Labels에 눈금 갯수를 설정 할 수 있습니다.

TickmarksLastLeft:null, // X축 Labels에 눈금 사용 여부를 설정 할 수
있습니다. 기본값은 true입니다.

TickmarksLastRight:null, // X축 Labels에 눈금 사용 여부를 설정 할 수
있습니다. 기본값은 true입니다.

TickmarksLength:10, // X축 Labels에 눈금의 길이를 설정할 수 있습니다..

Title:\'DxChart 튜토리얼\', // X축 Labels의 제목을 설정할 수 있습니다.

TitleColor: \'red\', // X축 Labels 제목의 색상값을 설정 할 수 있습니다.

TitleFontStyle:\'15px bold Pretendard\', // X축 Labels 제목의 폰트
스타일을 설정할 수 있습니다.

TitleHalign: \'cetner\', // X축 Labels에 제목의 가로정렬 값을 설정 할수
있습니다. (left,right,center)

TitleOffsetX: 5, // X축 Labels에 제목의 OffsetX 값을 설정 할수 있습니다.

TitleOffsetY:5, // X축 Labels에 제목의 OffsetY 값을 설정 할수 있습니다.

TitlePos:10, // X축 Labels에 제목의 위치를 지정합니다. 양수일 때 아래로
내려가고 음수일 때 위로 올 라갑니다..

TitleValign:\'center\', // X축 Labels에 제목의 세로정렬 값을 설정 할수
있습니다. (top, bottom, center)

TitleX: 850, // X축 Labels에 제목의 X좌표 값을 설정 할수 있습니다. 양수,
음수 모두 설정 가능합니다

TitleY:790 // X축 Labels에 제목의 Y좌표 값을 설정 할수 있습니다. 양수,
음수 모두 설정 가능합니다

},

}

}).draw();

### Y축 (옵션 -- yaxis 그룹)

![텍스트, 스크린샷, 도표, 그래프이(가) 표시된 사진 자동 생성된
설명](media/image35.png){width="6.298968722659668in"
height="2.9763888888888888in"}

![텍스트, 스크린샷, 폰트, 도표이(가) 표시된 사진 자동 생성된
설명](media/image36.png){width="2.783505030621172in"
height="2.264818460192476in"}

  --------------------------------------------------------------------------
  Sub property          설명                              타입      기본값
  --------------------- --------------------------------- --------- --------
  AddLineSize           y축 선의 길이를 지정합니다.       number    0
                        양수이면 원점에서 왼쪽으로 y축              
                        길이가 늘어나며 음수이면 원점에서           
                        오른쪽으로 y축 길이가 줄어듭니다.           

  Color                 y축 선의 색을 지정합니다.         string    black

  LabelsColor           y축 라벨의 색을 지정합니다.       object    null

  LabelsCount           y축 라벨의 개수를 지정합니다.     number    5
                        라벨이 많아도 넘어도 지정한                 
                        만큼의 개수만 보여집니다.                   

  LabelsFontStyle       y축 라벨의 글꼴 스타일을          string    null
                        지정합니다.                                 

  LabelsHalign          y축 라벨의 가로 정렬을            object    null
                        지정합니다. left, right, center를           
                        사용할 수 있습니다.                         

  LabelsOffsetX         y축 라벨의 가로 오프셋을          number    0
                        지정합니다.                                 

  LabelsOffsetY         y축 라벨의 세로 오프셋을          number    0
                        지정합니다.                                 

  LabelsPosition        y축 라벨의 포지션을 지정합니다.   string    edge
                        section, edge가 차트 유형별로               
                        적용되어 있으며 수정이 불가능한             
                        차트도 있습니다.                            

  LabelsSpecific        y축 라벨 값을 특정한 값으로       object    null
                        지정합니다.                                 

  LabelsValign          라벨의 세로 정렬을 지정합니다.    object    null
                        top, bottom, center를 사용할 수             
                        있습니다.                                   

  LineWidth             y축의 두께를 지정합니다.          number    1

  Position              y축의 위치를 지정합니다. top,     string    left
                        bottom, center를 사용할 수                  
                        있습니다.                                   

  Scale                 y축 라벨의 규모를 보여줄 지       boolean   true
                        여부입니다. true면 데이터 값에              
                        따라 y축에 라벨이 표현됩니다.               

  ScaleDecimals         y축 라벨의 규모를 보여줄 때,      number    0
                        지정한 값만큼의 소수점을                    
                        표시합니다.                                 

  ScaleFormatter        y축 라벨 규모의 데이터를 특정한   object    null
                        형식으로 변환하거나 서식을                  
                        적용합니다.                                 

  ScaleInvert           y축 라벨 규모를 반전시킬 지       boolean   false
                        여부입니다.                                 

  ScaleMax              y축 라벨의 규모를 보여줄 때,      object    null
                        라벨의 최대값을 지정합니다.                 

  ScaleMin              y축 라벨의 규모를 보여줄 때,      number    0
                        라벨의 최소값을 지정합니다.                 

  ScalePoint            y축 라벨의 규모를 보여줄 때,      string    .
                        소수점 표시 방식을 지정합니다.              

  ScaleRound            y축 라벨의 규모를 반올림할 지     boolean   false
                        여부입니다.                                 

  ScaleThousand         y축 라벨의 규모를 보여줄 때, 천   string    ,
                        단위 구분 기호를 지정합니다.                

  ScaleUnitsPost        y축 라벨의 규모를 보여줄 때, 뒤에 string    
                        표시할 문자를 지정합니다.                   

  ScaleUnitsPre         y축 라벨의 규모를 보여줄 때, 앞에 string    
                        표시할 문자를 지정합니다.                   

  Tickmarks             y축 라벨에 눈금을 표시할 지       boolean   true
                        여부입니다.                                 

  TickmarksCount        y축 라벨의 눈금 개수를            object    null
                        지정합니다.                                 

  TickmarksLastBottom   y축 라벨의 가장 아래쪽 마크를     object    null
                        표시할 지 여부입니다.                       

  TickmarksLastTop      y축 라벨의 가장 위쪽 마크를       object    null
                        표시할 지 여부입니다.                       

  TickmarksLength       y축 라벨의 데이터마다 위치한      number    3
                        마크값의 길이를 지정합니다.                 

  Title                 y축의 제목을 지정합니다.          string    

  TitleColor            y축 제목의 색상을 지정합니다.     object    null

  TitleFontStyle        y축 제목의 글꼴 스타일을          string    null
                        지정합니다.                                 

  TitleHalign           y축 제목의 가로 정렬을            object    null
                        지정합니다.                                 
                        \'left\',\'right\',\'center\'를             
                        사용할 수 있습니다.                         

  TitleOffsetX          y축 제목의 가로 오프셋을          number    0
                        지정합니다.                                 

  TitleOffsetY          y축 제목의 세로 오프셋을          number    0
                        지정합니다.                                 

  TitlePos              y축 제목의 위치를 지정합니다.     object    null
                        양수일 때 아래로 내려가고 음수일            
                        때 위로 올라갑니다.                         

  TitleValign           y축 제목의 수직 정렬을            object    null
                        지정합니다. top, bottom, center를           
                        사용할 수 있습니다.                         

  TitleX                y축 제목의 가로 좌표를            object    null
                        지정합니다.                                 

  TitleY                y축 제목의 세로 좌표를            object    null
                        지정합니다.                                 

  Use                   y축을 사용할 지 여부입니다.       boolean   true
  --------------------------------------------------------------------------

#### Y축 Property 기본 예제

![스크린샷, 텍스트, 그래프, 도표이(가) 표시된 사진 자동 생성된
설명](media/image37.png){width="7.772916666666666in"
height="3.607638888888889in"} 다음 예제는 Basic한 차트의 Y축 생성
예제입니다.

var bar = new DxChartBar({

id: cvs,

elem : canvas,

binddataset : this.Dataset00,

data:\[\"bind:total\",\"bind:man\",\"bind:woman\"\],

options: {

yaxis: {

Use : true, // 차트의 Y축을 Draw 할지 설정할 수 있는 옵션입니다. 디폴트
값은 true입니다.

ScaleMax: 100, // 차트 Y축 라벨 데이터값의 MAX값을 설정할 수 있습니다.

Tickmarks:false, // 차트 Y축의 눈금선 사용 여부를 설정할 수 있습니다.
디퐅트값은 true입니다.

TickmarksCount: 5, // 차트 Y축의 눈금선 개수 를 설정 할 수 있습니다.

Color:\"#E2E2E2\", // 차트 Y축 라인의 색상을 설정 할 수 있습니다.

LabelsOffsetX:-15, //차트의 Y축과 라벨 사이 OffsetX값을 설정할 수
있습니다 양수 음수 둘다 가능합니다..

}

}

}).draw();

#### Y축 Property 기본 예제 (Labels 관련 예제)

![텍스트, 스크린샷, 라인, 그래프이(가) 표시된 사진 자동 생성된
설명](media/image38.png){width="7.793055555555555in"
height="3.4944444444444445in"} 다음은 차트의 Y축 라벨에 관련된 기본 예제
입니다.

var bar = new DxChartBar({

id: cvs,

elem : canvas,

binddataset : this.Dataset00,

data:\[\"bind:total\",\"bind:man\",\"bind:woman\"\],

options: {

yaxis: {

Use : true, // 차트의 Y축을 Draw 할지 설정할 수 있는 옵션입니다. 디폴트
값은 true입니다.

Tickmarks:true, // 차트 Y축의 눈금선 사용 여부를 설정할 수 있습니다.
디퐅트값은 true입니다.

TickmarksCount: 3, // 차트 Y축의 눈금선 개수 를 설정 할 수 있습니다.

Color:\"#E2E2E2\", // 차트 Y축 라인의 색상을 설정 할 수 있습니다.

LabelsCount: 3, // 차트 Y축 라벨 데이터 의 개수를 설정할 수 있습니다.
기본적으로 바인딩된 데이터 값들의 평균값이 라벨로 설정 됩니다.

LabelsFontStyle:\'20px bold Pretendard\', // 차트 Y축 라벨 데이터의 폰트
스타일을 설정할 수 있습니다.

LabelsHalign: \'center\', // 차트 Y축 라벨 데이터의 가로정렬을 설정할 수
있습니다.

LabelsOffsetX:-35, //차트의 Y축과 라벨 사이 OffsetX값을 설정할 수
있습니다 양수 음수 둘다 가능합니다..

LabelsOffsetY: -15, //차트의 Y축과 라벨 사이 OffsetY값을 설정할 수
있습니다 양수 음수 둘다 가능합니다..

LabelsPosition: \'edge\', //차트의 Y축 라벨 데이터의 포지션을 설정할 수
있습니다. 'section', 'edge'로 설정 가능합니다.

LabelsSpecific:\[\'High\',\'Medium\',\'Low\'\], // 차트의 Y축 라벨
데이터를 바인딩된 데이터의 평균값이 아닌

특정한 값으로 설정할 수있습니다. Array 형식으로 설정이 가능합니다.

LabelsValign:\'left\', //차트의 Y축 라벨데이터의 세로정렬 값을 설정할
수있습니다.

LineWidth:3, // 차트의 Y축 색상을 설정 할 수 있습니다.

Position:\'left\' // 차트의 Y축 포지션을 설정할 수 있습니다.

LabelsColor:\'red\', //차트 Y축 라벨 데이터의 색상을 설정 할 수
있습니다.

}

}

}).draw();

#### Y축 Property 기본 예제 (Scale 관련 예제)

![스크린샷, 텍스트, 그래프, 도표이(가) 표시된 사진 자동 생성된
설명](media/image39.png){width="7.782638888888889in"
height="4.061111111111111in"}다음은 Y축 Scale에 관련된 기본 예제 입니다.
Scale Properties는 기본적으로 Y축 라벨데이터와 연관되어 있습니다. Scale
설정에 따라서 차트의 데이터 값 표현이 달라질 수 있습니다.

var bar = new DxChartBar({

id: cvs,

elem : canvas,

binddataset : this.Dataset00,

data:\[\"bind:total\",\"bind:man\",\"bind:woman\"\],

options: {

yaxis: {

Use : true,

Color:\"#E2E2E2\",

LabelsOffsetX:-15, //y축과 label 사이 15px 설정

Scale: true, //차트의 Y축 Scale값 표시 여부를 설정할 수 있습니다.

ScaleRound: true, //차트의 Y축 Scale값을 반올림 표현을 할지 설정할 수
있습니다.\
예를들어 Scale의 최대값을 59로설정할시, 100으로 반올림하여 표현합니다.

ScaleMax: 59, //차트의 Y축 Scale의 최대값을 설정할 수 있습니다. 설정값에
따라 차트의 데이터 표현형태가 달라지므로, 차트의 형태도 달라질수
있습니다.

ScaleMin:10, , //차트의 Y축 Scale의 최솟값을 설정할 수 있습니다.
설정값에 따라 차트의 데이터 표현형태가 달라지므로, 차트의 형태도
달라질수 있습니다.

ScaleUnitsPost: \'%\', //차트의 Y축 Scale 값 뒤에 문자를 설정 할 수
있습니다.

ScaleUnitsPre:\'\$\', //차트의 Y축 Scale 값 앞에 문자를 설정 할 수
있습니다.

ScaleDecimals: 2, //차트의 Y축 Scale 소수점 자릿 수를 설정 할 수
있습니다..

ScaleInvert:false, //차트의 Y축 Scale의 최대값과 최소값을 Invert하여
표시할 수 있습니다.

ScalePoint: \',,\', //차트의 Y축 Scale 값 소수점 구분점을 설정할 수
있습니다.

ScaleThousand:\'..\' //차트의 Y축 Scale 값 천단위 구분점을 설정할 수
있습니다.

}

}

}).draw();

#### Y축 Property ScaleFormatter예제 (Scale 관련 예제)

![텍스트, 스크린샷, 도표, 그래프이(가) 표시된 사진 자동 생성된
설명](media/image40.png){width="7.579166666666667in"
height="6.047916666666667in"}ScaleFormatter는 Y축 Sclae 데이터 값을
바인딩된 데이터값과 다르게 표현할수 있는 Properties 입니다.\
옵션 객체 안에서 함수형태로 선언하여 사용할 수 있습니다.

앞선 예제의 Y축 Scale값입니다. ScaleFormatter 프로퍼티를 통해서 해당
값을 다른값으로 표현할수 있습니다.

var bar = new DxChartBar({

id: cvs,

elem : canvas,

binddataset : this.Dataset00,

data:\[\"bind:total\",\"bind:man\",\"bind:woman\"\],

options: {

//기본적으로 ScaleFormatter는 yaxis에 관련된 프로퍼티이기 때문에 yaxis
객체안에 선언합니다.

yaxis: {

ScaleFormatter : function (e)

{

//yaxis의 Scale값은 바인딩된 데이터 값이기 때문에, 기본적으로
Number형식을 따릅니다

var num = Number(e.number) \* 6; //매개변수 e는 바인딩된 데이터값이
넘어오게되며, 설정하고 싶은 값을 변수에 담아줍니다.

return String(num) //설정된 값을 String으로 변환해 반환합니다.,

}

}

}

}).draw();

기존![텍스트, 스크린샷, 도표, 그래프이(가) 표시된 사진 자동 생성된
설명](media/image41.png){width="7.579166666666667in"
height="6.101388888888889in"} Sclae값에 \*6을 한 데이터를 반환한
결과입니다. SclaeFormmater를 설정하게되면, 기존에 설정했던 Scale 구분점
값이나, Post, Pre값들은 초기화 되게 됩니다.

이와 같이 Scale 데이터 값을 특정 값으로 표현할 수 있습니다.

#### ![스크린샷, 라인, 도표, 그래프이(가) 표시된 사진 자동 생성된 설명](media/image42.png){width="7.772916666666666in" height="3.6180555555555554in"}Y축 Property 기본 예제 (Tickmarks 관련 예제)

var bar = new DxChartBar({

id: cvs,

elem : canvas,

binddataset : this.Dataset00,

data:\[\"bind:total\",\"bind:man\",\"bind:woman\"\],

options: {

yaxis: { //기본적인 설정은 Basic예제와 동일합니다

Tickmarks: true, //차트 Y축의 눈금선 표시여부를 설정할 수 있습니다.

TickmarksCount: 5, //차트 Y축의 눈금선 표시여부를 설정할 수 있습니다.

TickmarksLastBottom:false, //차트 Y축의 눈금선 표시여부를 설정할 수
있습니다.

TickmarksLastTop:false, //차트 Y축의 눈금선 표시여부를 설정할 수
있습니다.

TickmarksLength: 10, //차트 Y축의 눈금선 표시여부를 설정할 수 있습니다.

LabelsFontStyle: \'20px bold Pretendard\'

}

}

}

}).draw();

#### Y축 Property 기본 예제 (title 관련 예제)

다음은 Y축 title에 관한 기본 예제입니다.

![텍스트, 스크린샷, 도표, 폰트이(가) 표시된 사진 자동 생성된
설명](media/image43.png){width="7.4430555555555555in"
height="4.547916666666667in"}![스크린샷, 텍스트, 그래프, 도표이(가)
표시된 사진 자동 생성된
설명](media/image44.png){width="7.3805555555555555in"
height="3.685416666666667in"}

var bar = new DxChartBar({

id: cvs,

elem : canvas,

binddataset : this.Dataset00,

data:\[\"bind:total\",\"bind:man\",\"bind:woman\"\],

options: {

yaxis: { //기본적인 설정은 Basic예제와 동일합니다

Use : true,

Color:\"#E2E2E2\",

LabelsOffsetX:-15, //y축과 label 사이 15px 설정

Title:\'DxChart 튜토리얼\', //차트 Y축 타이틀을 설정할 수 있습니다.

TitleColor:\'red\', //차트 Y축 타이틀을 색상을 설정할 수 있습니다.

TitleFontStyle:\'18px bold Pretendard\', //차트 Y축 타이틀 폰트 스타일을
설정할 수 있습니다.

TitleHalign:\'center\', //차트 Y축 타이틀 가로정렬을 설정할수 있습니다.
'left','right','cetner'.

TitleOffsetX:80, //차트 Y축 타이틀 OffsetX 값을 설정할 수 있습니다.

TitleOffsetY:-20, //차트 Y축 타이틀 OffsetY 값을 설정할 수 있습니다.

TitlePos:-20, //차트 Y축 타이틀을 설정할 수 있습니다.

TitleValign:\'cetner\', //차트 Y축 타이틀 세로정렬 값 을 설정할 수
있습니다.

TitleX:50, //차트 Y축 타이틀 X좌표값 을 설정할 수 있습니다.

TitleY:400 //차트 Y축 타이틀 Y좌표값 을 설정할 수 있습니다.

}

}

}

}).draw();

###  {#section-1 .unnumbered}

###  {#section-2 .unnumbered}