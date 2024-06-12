> **DXChart 개발자 튜토리얼**
>
> **(Nexacro용)**
---

**\[목 차\]**

1. [처음 시작하기](#처음-시작하기)
   - [Nexacro Project 만들기](#nexacro-project-만들기)
   - [차트모듈 설치하기](#차트모듈-설치하기)
   - [샘플화면 만들기](#샘플화면-만들기)
   - [차트함수 만들기](#차트함수-만들기)

2. [차트 구성요소](#차트-구성요소)
   - [구성요소 용어 설명](#구성요소-용어-설명)
   - [데이터 형식](#데이터-형식)
     - [data Property](#data-property)
     - [binddataset Property](#binddataset-property)
     - [Margin (옵션 - margin 그룹)](#margin-옵션---margin-그룹)
     - [X축 (옵션 - xaxis 그룹)](#text-property-예제)
     - [Y축 (옵션 - yaxis 그룹)](#y축-옵션-yaxis-그룹)
     - [배경 (옵션 - background 그룹)](#\_Toc162962562)
     - [제목 (옵션 - title 그룹)](#제목-옵션-title-그룹)
     - [범례](#_Toc162962564)
     - [툴팁](#_Toc162962565)
     - [라벨 (옵션 - labels 그룹)](#\_Toc162962566)
     - [십자선(옵션 - crosshairs 그룹)](#\_Toc162962567)
     - [에러바 (옵션 - errorbars 그룹)](#\_Toc162962568)
     - [주석 (옵션 - annotation 그룹)](#\_Toc162962569)
     - [그외](#_Toc162962570)

[**3.** **차트의 주요 메소드**](#차트의-주요-메소드)

- [DxChart 오브젝트](#dxchart-오브젝트)
  - [appendAxis](#appendaxis)
  - [redraw](#redraw)
  - [reset](#reset)
  - [convertDataset](#convertdataset)
  - [clear](#clear)
  - [\...\* (이하 생략)\*](#shadecolor-clear)

- [(2) Effect 종류](#effect-종류)
  - [draw](#draw)
  - [drawAni](#drawani)
  - [wave](#wave)
  - [\...\* (이하 생략)\*](#roundrobinsequential-explode)

- [(3) 차트별 메소드](#차트별-메소드)
  - [get](#get)
  - [set](#set)
  - [getValue](#getvalue)
  - [on](#on)
  - [\...\* (이하 생략)\*](#ontooltip)
  
- [(4) 이벤트 종류](#이벤트-종류)
  - [onadjustbegin](#onadjustbegin)
  - [onadjust](#onadjust)
  - [\...\* (이하 생략)\*](#ontooltip-onmouseout)


[**4.** **차트 종류**](#차트-종류)

- [막대차트 (bar)](#막대차트bar)
- [라인차트 (line)](#라인차트line)
- [activity 차트 (activity)](#activity-차트activity)
- [양극성 차트 (bipolar)](#양극성-차트bipolar)
- [연료 차트 (fuel)](#연료-차트fuel)
- [Funnel 차트 (funnel)](#funnel-차트funnel)
- [간트 차트 (gantt)](#간트-차트gantt)
- [게이지 차트 (gauge)](#게이지-차트gauge)
- [가로 막대 차트 (hbar)](#가로-막대-차트hbar)
- [히트맵 차트 (heatmap)](#히트맵-차트heatmap)
- [말발굽 차트 (horseshoe)](#말발굽-차트horseshoe)
- [수평 진행 차트 (hprogress)](#수평-진행-차트hprogress)
- [미터 차트 (meter)](#미터-차트meter)
- [계기판 차트 (odo)](#계기판-차트odo)
- [조직구조 차트 (org)](#조직구조-차트org)
- [파이 차트 (pie)](#파이-차트pie)
- [피라미드 차트 (pyramid)](#피라미드-차트pyramid)
- [레이더 차트 (radar)](#레이더-차트radar)
- [로즈 차트 (rose)](#로즈-차트rose)
- [산점도 차트 (rscatter)](#산점도-차트rscatter)
- [분산형 차트 (scatter)](#분산형-차트scatter)
- [세그먼트 차트 (segment)](#세그먼트-차트segment)
- [반원형 진행 차트 (semicircularprogress)](#반원형-진행-차트semicircularprogress)
- [온도계 차트 (thermometer)](#온도계-차트thermometer)
- [트리 차트 (tree)](#트리-차트tree)
- [수직 진행 차트 (vprogress)](#수직-진행-차트vprogress)
- [워터폴 차트 (waterfall)](#워터폴-차트waterfall)

[**5.** **관련사이트**](#관련사이트)


# **처음 시작하기**

## Nexacro Project 만들기

차트를 사용하기 위한 테스트 프로젝트를 생성합니다.

넥사크로스튜디오가 설치되지 않은 경우에는 설치를 먼저 진행해야 합니다.

(<http://support.tobesoft.com>에서 다운로드 받아 설치할 수 있습니다.)

1)  NexacroStudio를 기동합니다.

2)  새로운 프로젝트를 생성합니다.

    ![생성하기](생성하기.png)

3)  새로운 창이 열리면 Project Name 항목에 프로젝트 이름을 입력하고
    [Next] 버튼을 클릭합니다.

    ![다음버튼](다음버튼.png)

4)  Screen 설정값은 기본값으로 놔두고 [Next] 버튼을 클릭합니다.

    ![다음버튼2](다음버튼2.png)

5)  Frame 설정값도 기본값으로 놔두고 [Finish] 버튼을 클릭합니다.

    ![프레임설정](프레임설정.png)

6)  Project Explorer 영역에 앞에서 입력한 프로젝트명으로 프로젝트가
    생성된 것을 확인합니다.

    ![완성](프로젝트완성.png)

## 차트모듈 설치하기

1)  Nexacro Studio에서 [File]-[install module]을 선택합니다.

2)  [Module Package(.xmodule)]을 선택하고 [Next]를 클릭합니다.

    ![모듈설치](모듈설치.png)

3)  준비된 DxChart.xmodule파일을 선택하고 [Next]를 클릭합니다.

    ![모듈설치2](모듈설치2.png)

4)  [Install]버튼을 클릭합니다.

    ![인스톨](인스톨.png)

5)  [Finish]버튼을 클릭합니다.

    ![완료](완료.png)

6)  설치가 끝나면 프로젝트 파일을 Reload할지를 묻는 Confirm메시지가
    표시됩니다.

    [Yes]를 클릭합니다.

    ![컨펌](컨펌.png)

7)  DXChart가 설치된 것을 확인합니다.

-   [Project Explorer]-[TypeDefinition]-[Objects]를 선택하면
    [TypeDefinition-Objects]팝업이 표시됩니다.

-   [Modlues] 에 "extlib::DxChart.json"이 추가된 것을 확인합니다.

-   [Objects]에 "ChartJS"가 추가되어 있는 것을 확인합니다.

    ![종료](종료.png)

## 샘플화면 만들기

1)  작성할 화면을 오픈합니다. (FrameBase::Frame_Work.xfdl)

    ![샘플화면](샘플화면.png)

2)  Chart 컴포넌트를 추가합니다.

    컴포넌트의 아이디는 변경을 하지 않으면 기본적으로 "ChartJS00"으로
    생성됩니다.

    ![샘플화면2](image-1.png)

3)  버튼을 추가합니다.

    컴포넌트의 아이디는 변경을 하지 않으면 기본적으로 "Button00"으로
    생성됩니다.

    ![버튼](image-2.png)

4)  데이터 생성하기

    표시할 데이터를 생성합니다. (데이터셋 사용)

    컴포넌트의 아이디는 변경을 하지 않으면 기본적으로 "Dataset00"으로
    생성됩니다.

    ![데이터](image-3.png)

5)  Dataset을 추가한 후 데이터셋을 더블클릭하면, [Dataset Editor]창이
    표시됩니다.

    ![데이터2](image-4.png)

6)  [Dataset Editor]창 하단의 [Source]탭을 클릭합니다.

    ![데이터3](image-5.png)

7)  [Dataset Source Editor]팝업이 표시됩니다.

    ![스크린샷, 디스플레이, 컴퓨터, 화면이(가) 표시된 사진 자동 생성된
    설명](media/image18.png)

8)  아래의 내용을 창에 입력 후 [OK]를 클릭합니다.

    ![텍스트, 디스플레이, 스크린샷, 소프트웨어이(가) 표시된 사진 자동
    생성된 설명](media/image19.png)

```html 
    [데이터셋 내용]
    <ColumnInfo>
      <Column id="indecators" type="STRING" size="256"/>
      <Column id="total" type="BIGDECIMAL" size="256"/>
      <Column id="man" type="BIGDECIMAL" size="256"/>
      <Column id="woman" type="BIGDECIMAL" size="256"/>
    </ColumnInfo>
    <Rows>
      <Row>
        <Col id="indecators">2015</Col>
        <Col id="total">5203440</Col>
        <Col id="woman">2610477</Col>
        <Col id="man">2592963</Col>
      </Row>
      <Row>
        <Col id="indecators">2016</Col>
        <Col id="total">5397615</Col>
        <Col id="woman">2721754</Col>
        <Col id="man">2675861</Col>
      </Row>
      <Row>
        <Col id="indecators">2017</Col>
        <Col id="total">5618677</Col>
        <Col id="woman">2826828</Col>
        <Col id="man">2791849</Col>
      </Row>
      <Row>
        <Col id="indecators">2018</Col>
        <Col id="total">5848594</Col>
        <Col id="woman">2942274</Col>
        <Col id="man">2906320</Col>
      </Row>
      <Row>
        <Col id="indecators">2019</Col>
        <Col id="total">6147516</Col>
        <Col id="woman">3093783</Col>
        <Col id="man">3053733</Col>
      </Row>
      <Row>
        <Col id="indecators">2020</Col>
        <Col id="total">6643354</Col>
        <Col id="woman">3338956</Col>
        <Col id="man">3304398</Col>
      </Row>
      <Row>
        <Col id="indecators">2021</Col>
        <Col id="total">7165788</Col>
        <Col id="woman">3582018</Col>
        <Col id="man">3583770</Col>
      </Row>
    </Rows>
  ```

  ##  **차트함수 만들기**

1) 생성한 버튼을 더블클릭하고 스크립트를 작성합니다.

    ![텍스트, 스크린샷, 폰트, 번호이(가) 표시된 사진 자동 생성된
    설명](media/image20.png){width="3.3650524934383204in"
    height="1.718989501312336in"}

2) [버튼 처리 내용]

    
    
  ```javascript
   this.Button00_onclick = function(obj:nexacro.Button,e:nexacro.ClickEventInfo)
      {
      var chart = this.ChartJS00;
      var canvas = chart.getCanvas();
      var cvs = canvas.id;
      DxChart.reset(canvas);
      var labels = DxChart.convertDataset(this.Dataset00, ["bind:indecators"])
      var line = new DxChartBar({
        id: cvs,
        elem : canvas,
        binddataset : this.Dataset00,
        data:["bind:total","bind:man","bind:woman"],
        options: {
              colors: ['#FF6A8E','#42B0FF','#5DCA63'],
              title: { Text : '1인 가구 수', FontStyle: 'bold 12px Tahoma' },
                    xaxis: { Use : true, Labels: labels },
            yaxis: { Use : true,
                    LabelsCount: 5,
              ScaleMax: 10000000,
              TickmarksCount: 10,
              },
            margin: { Left: 100, Bottom: 50, Inner : 20 },
            tooltips: {
              Data : '%{key}',
              FormattedUnitsPost: '명',
              Effect : 'fade',
              Pointer : true,
              Css: {
                fontSize: '14pt'
              },
              FormattedKeyLabels: ['종합','남자','여자'],
            }
          }
        }).wave();
      }
```
  
3) 테스트해보기
 
    Quick View를 실행합니다.(Browser는 Chrome 또는 Microsoft Edge을
    선택합니다.)

    ![텍스트, 스크린샷, 폰트, 소프트웨어이(가) 표시된 사진 자동 생성된
    설명](media/image21.png){width="4.162982283464567in"
    height="0.9509350393700787in"}

    \[실행 결과\]


4)  버튼을 클릭합니다.


5)  결과를 확인합니다.

    ![텍스트, 도표, 그래프, 스크린샷이(가) 표시된 사진 자동 생성된
    설명](media/image22.png){width="4.297011154855643in"
    height="2.2946587926509188in"}




# **차트 구성요소**

## 구성요소 용어 설명

차트의 호출형식은 아래와 같이 구성되어 있습니다.

  ```javascript
        var chart = this.chart; 
        var canvas = chart.getCanvas(); 
        var cvs = canvas.id;
        DxChart.reset(canvas);
        var bar = new DxChartBar({
          id: cvs,
          elem : canvas,
          binddataset : this.Dataset00,
          data:["bind:total","bind:man","bind:woman"],
          options: {
              colors: ['#FF6A8E','#42B0FF','#5DCA63'],
              title: { Text : '1인 가구 수' },
                xaxis: { Use : true, Labels: labels },
                  yaxis: { Use : true,
                    LabelsCount: 5,
              ScaleMax: 10000000,
              TickmarksCount: 10,
              },
              margin: { Left: 100, Bottom: 50, Inner : 20 },
          }
        }).wave();




        1)  차트를 그리기 전에 차트영역을 reset해줍니다.

            var chart = this.chart; // Chart Object를 지정합니다.

            var canvas = chart.getCanvas(); // canvas를 가져옵니다.

            var cvs = canvas.id; // cavas의 아이디

            DxChart.reset(canvas); // 차트영역(canvas)을 reset합니다.

        2)  차트의 종류(오브젝트)를 지정합니다.

            var bar = New DxChartBar(config);

            //config : 차트를 그리기 위한 정보(config)

```
---

  1) 지정가능한 차트의 종류는 아래와 같습니다.




      <table>
        <thead>
          <tr>
            <th style="text-align: center;">차트 종류</th>
            <th style="text-align: center;">오브젝트명</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td style="text-align: center;">activity 차트</td>
            <td style="text-align: center;">DxChartActivity</td>
          </tr>
          <tr>
            <td style="text-align: center;">막대 차트</td>
            <td style="text-align: center;">DxChartBar</td>
          </tr>
          <tr>
            <td style="text-align: center;">양극성 차트</td>
            <td style="text-align: center;">DxChartBipolar</td>
          </tr>
          <tr>
            <td style="text-align: center;">연료 차트</td>
            <td style="text-align: center;">DxChartFuel</td>
          </tr>
          <tr>
            <td style="text-align: center;">Funnel 차트</td>
            <td style="text-align: center;">DxChartFunnel</td>
          </tr>
          <tr>
            <td style="text-align: center;">간트 차트</td>
            <td style="text-align: center;">DxChartGantt</td>
          </tr>
          <tr>
            <td style="text-align: center;">게이지 차트</td>
            <td style="text-align: center;">DxChartGauge</td>
          </tr>
          <tr>
            <td style="text-align: center;">가로 막대 차트</td>
            <td style="text-align: center;">DxChartHbar</td>
          </tr>
          <tr>
            <td style="text-align: center;">히트맵 차트</td>
            <td style="text-align: center;">DxChartHeatmap</td>
          </tr>
          <tr>
            <td style="text-align: center;">말발굽 차트</td>
            <td style="text-align: center;">DxChartHorseshoe</td>
          </tr>
          <tr>
            <td style="text-align: center;">수평 진행 차트</td>
            <td style="text-align: center;">DxChartHProgress</td>
          </tr>
          <tr>
            <td style="text-align: center;">선 차트</td>
            <td style="text-align: center;">DxChartLine</td>
          </tr>
          <tr>
            <td style="text-align: center;">미터 차트</td>
            <td style="text-align: center;">DxChartMeter</td>
          </tr>
          <tr>
            <td style="text-align: center;">계기판 차트</td>
            <td style="text-align: center;">DxChartOdo</td>
          </tr>
          <tr>
            <td style="text-align: center;">조직구조 차트</td>
            <td style="text-align: center;">DxChartOrg</td>
          </tr>
          <tr>
            <td style="text-align: center;">파이 차트</td>
            <td style="text-align: center;">DxChartPie</td>
          </tr>
          <tr>
            <td style="text-align: center;">피라미드 차트</td>
            <td style="text-align: center;">DxChartPyramid</td>
          </tr>
          <tr>
            <td style="text-align: center;">레이더 차트</td>
            <td style="text-align: center;">DxChartRadar</td>
          </tr>
          <tr>
            <td style="text-align: center;">로즈 차트</td>
            <td style="text-align: center;">DxChartRose</td>
          </tr>
          <tr>
            <td style="text-align: center;">산점도 차트</td>
            <td style="text-align: center;">DxChartRscatter</td>
          </tr>
          <tr>
            <td style="text-align: center;">분산형 차트</td>
            <td style="text-align: center;">DxChartScatter</td>
          </tr>
          <tr>
            <td style="text-align: center;">세그먼트 차트</td>
            <td style="text-align: center;">DxChartSegment</td>
          </tr>
          <tr>
            <td style="text-align: center;">반원형 진행 차트</td>
            <td style="text-align: center;">DxChartSemiCircle</td>
          </tr>
          <tr>
            <td style="text-align: center;">온도계 차트</td>
            <td style="text-align: center;">DxChartThermometer</td>
          </tr>
          <tr>
            <td style="text-align: center;">트리 차트</td>
            <td style="text-align: center;">DxChartTree</td>
          </tr>
          <tr>
            <td style="text-align: center;">수직 진행 차트</td>
            <td style="text-align: center;">DxChartVProgress</td>
          </tr>
          <tr>
            <td style="text-align: center;">워터폴 차트</td>
            <td style="text-align: center;">DxChartWaterfall</td>
          </tr>
        </tbody>
      </table>


---


1)  config를 정의합니다.

-   Config는 JSON형식으로 구성이 되어 있습니다.

-   Config는 아래의 구성요소로 되어 있습니다.

<table>
  <thead>
    <tr>
      <th style="text-align: center;">구성요소명</th>
      <th style="text-align: center;">설명</th>
      <th style="text-align: center;">사용예</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align: center;">id</td>
      <td style="text-align: center;">차트 canvas의 아이디</td>
      <td style="text-align: center;">Id : canvas.id</td>
    </tr>
    <tr>
      <td style="text-align: center;">elem</td>
      <td style="text-align: center;">차트 canvas 오브젝트</td>
      <td style="text-align: center;">elem: this.chart00.getCanvas()</td>
    </tr>
    <tr>
      <td style="text-align: center;">binddataset</td>
      <td style="text-align: center;">Nexacro의 데이터셋 오브젝트</td>
      <td style="text-align: center;">Binddataset:</td>
    </tr>
    <tr>
      <td style="text-align: center;">datachangeevent</td>
      <td style="text-align: center;">Bind된 데이터셋의 데이터가 변경되면 차트를 다시 그릴지를 확인합니다.<br>Use: 사용 여부(true/false(default))<br>Effect: 다시 그릴 때 사용할 effect함수명(String)</td>
      <td style="text-align: center;">datachangeevent: {Use: true, Effect: "wave"}</td>
    </tr>
    <tr>
      <td style="text-align: center;">data</td>
      <td style="text-align: center;">차트에 표시할 데이터 리스트(배열)<br>Binddataset이 세팅된 경우는 "bind" + 컬럼명을 지정하면 해당 컬럼의 데이터값이 배열로 세팅됩니다.</td>
      <td style="text-align: center;">- ["bind:Col0", "bind:Col1"]<br>- [[10,20,30], [20,30,40]]</td>
    </tr>
    <tr>
      <td style="text-align: center;">option</td>
      <td style="text-align: center;">차트에 대한 옵션값을 세팅합니다.<br>- background, key, xaxis, yaxis, tooltip 등</td>
      <td style="text-align: center;">{<br>xaxis: {...},<br>yaxis: {...},<br>key: {...},<br>...</td>
    </tr>
  </tbody>
</table>



## 데이터 형식

차트에 사용되는 데이터의 형식은 2차원 배열을 사용합니다.

### data Property
---

차트에 사용될 데이터를 지정합니다. 데이터의 지정방식을

bind컬럼지정/CSV배영/2차원배열등로 표현되어 지정 가능합니다.

형식: data : \[ \[첫번째 차트 데이터\] , \[두번째 차트 데이터\] ,
\[세번째 차트 데이터\]\]

사용 예 : data : \["bind:Column0","bind:Column1"\] (binddataset을
지정한경우)

data: \["123,123,123,123","123,123,123,1234"\] (CSV데이터의 배열)

data: \[\[123,123,123,123\],\[123,123,123,1234\]\] (2차원 배열)

---
### binddataset Property
---
데이터셋의 오브젝트를 지정합니다.

이 Property를 사용하는 경우, 일부 Property에서는 "bind: 컬럼명"형태로

데이터의 리스트(배열)을 지정할 수 있습니다.

(Nexacro 전용 프로퍼티)

사용 예 : binddataset : this.dsList

---

## 차트 주요 Properties

### Margin (옵션 - margin 그룹)

![텍스트, 스크린샷, 그래프, 도표이(가) 표시된 사진 자동 생성된
설명](media/image23.png){width="5.708333333333333in"
height="2.860313867016623in"}

![텍스트, 스크린샷, 도표, 라인이(가) 표시된 사진 자동 생성된
설명](media/image24.png){width="2.6770833333333335in"
height="2.5411187664041996in"}

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


![스크린샷, 그래프, 라인, 도표이(가) 표시된 사진 자동 생성된
 설명](media/image25.png)

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

![일렉트릭 블루, 스크린샷, 다채로움, 블루이(가) 표시된 사진 자동 생성된
설명](media/image26.png){width="6.929166666666666in"
height="3.5569444444444445in"}

var bar = new DxChartBar({

id: cvs,

elem : canvas,

binddataset : this.Dataset00,

data:\[\"bind:total\",\"bind:man\",\"bind:woman\"\],

options: {

text: {

Color:\'Blue\', // text 색상을 설정할수 있습니다. 위의 예제에선 Y축 라벨
색상입니다.

FontStyle: \'20px bold Pretendard\' // Text FontStyle을 설정할 수
있습니다.

}

}

}).draw();

### 제목 (옵션 -- title 그룹)

![텍스트, 도표, 그래프, 스크린샷이(가) 표시된 사진 자동 생성된
설명](media/image27.png){width="6.309278215223097in"
height="2.9430555555555555in"}

  -----------------------------------------------------------------------
  Sub property        설명                           타입      기본값
  ------------------- ------------------------------ --------- ----------
  Color               제목의 색을 지정합니다.        object    null

  FontStyle           제목의 글꼴 스타일을           string    null
                      지정합니다.                              

  Halign              제목의 가로 정렬을 지정합니다. object    null
                      left, right, center 를 사용할            
                      수 있습니다.                             

  OffsetX             제목의 가로 오프셋을           number    0
                      지정합니다.                              

  OffsetY             제목의 세로 오프셋을           number    0
                      지정합니다.                              

  Subtitle            차트의 부제목을 지정합니다.    string    
                      제목 바로 아래에 생기기 때문에           
                      마진을 주지 않으면 제목이                
                      제대로 보이지 않을 수                    
                      있습니다.                                

  SubtitleColor       부제목의 색을 지정합니다.      string    #aaa

  SubtitleFontStyle   부제목의 글꼴 스타일을         string    null
                      지정합니다.                              

  SubtitleOffsetX     부제목의 가로 오프셋을         number    0
                      지정합니다.                              

  SubtitleOffsetY     부제목의 세로 오프셋을         number    0
                      지정합니다.                              

  Text                중앙 상단의 제목을 지정합니다. string    

  Valign              제목의 세로 정렬을 지정합니다. object    null
                      top, bottom, center를 사용할             
                      수 있습니다.                             

  X                   제목의 가로 좌표를 지정합니다. object    null

  Y                   제목의 세로 좌표를 지정합니다. object    null
  -----------------------------------------------------------------------

#### Title Property 예제![라인, 도표, 스크린샷, 그래프이(가) 표시된 사진 자동 생성된 설명](media/image28.png){width="7.579166666666667in" height="3.651388888888889in"}

var bar = new DxChartBar({

id: cvs,

elem : canvas,

binddataset : this.Dataset00,

data:\[\"bind:total\",\"bind:man\",\"bind:woman\"\],

options: {

title: { Text : \'DxChart 튜토리얼\', // 차트의 title Text값을
설정합니다.

FontStyle: \'32px bold Pretendard\', // title FontStyle을 설정할 수
있습니다.

Y :73 // 차트 내 title의 Y 위치값을 설정 할수 있습니다.

X: 450 // 차트 내 title의 X 위치값을 설정 할수 있습니다.

},

}

}).draw();

### 제목(옵션 -Subtitle)

DxChart는 Main Title 외에 차트의 부제목 또한 설정할 수 있습니다. 같은
title Properties내에 Subtitle

옵션값으로 설정 할 수 있습니다.

  -----------------------------------------------------------------------
  Sub property        설명                           타입      기본값
  ------------------- ------------------------------ --------- ----------
  Subtitle            차트의 부제목을 지정합니다.    string    
                      제목 바로 아래에 생기기 때문에           
                      마진을 주지 않으면 제목이                
                      제대로 보이지 않을 수                    
                      있습니다.                                

  SubtitleColor       부제목의 색을 지정합니다.      string    #aaa

  SubtitleFontStyle   부제목의 글꼴 스타일을         string    null
                      지정합니다.                              

  SubtitleOffsetX     부제목의 가로 오프셋을         number    0
                      지정합니다.                              

  SubtitleOffsetY     부제목의 세로 오프셋을         number    0
                      지정합니다.                              
  -----------------------------------------------------------------------

#### SubTitle Property 예제 ![라인, 도표, 그래프, 스크린샷이(가) 표시된 사진 자동 생성된 설명](media/image29.png){width="7.579166666666667in" height="3.5965277777777778in"}

var bar = new DxChartBar({

id: cvs,

elem : canvas,

binddataset : this.Dataset00,

data:\[\"bind:total\",\"bind:man\",\"bind:woman\"\],

options: {

title: { Text : \'DxChart 튜토리얼\', // 차트의 title Text값을
설정합니다.

Subtitle: \'차트 제목 만들기\', // 차트의 부제목을 설정할 수있습니다.

SubtitleFontStyle : \'24px Pretendard\' // 차트 부제목의 폰트 스타일을
설정 할 수 있습니다.

// SubtitleOffsetY: 103 // 차트 부제목의 Offset Y 좌표 위치를 설정 할 수
있습니다. X 좌표 위치값 변

경도 가능합니다.

},

}

}).draw();

### X축 (옵션 - xaxis 그룹)

차트의 X축에 대한 설정을 하는 Property입니다.

![](media/image30.png){width="6.04123687664042in"
height="2.6972222222222224in"}

![텍스트, 스크린샷, 폰트, 라인이(가) 표시된 사진 자동 생성된
설명](media/image31.png){width="5.577319553805775in"
height="1.1930555555555555in"}

  --------------------------------------------------------------------------------
  Sub property               설명                              타입      기본값
  -------------------------- --------------------------------- --------- ---------
  AddLineSize                x축 선의 길이를 지정합니다.       number    0
                             양수이면 원점에서 왼쪽으로 x축              
                             길이가 늘어나며 음수이면 원점에서           
                             오른쪽으로 x축 길이가 줄어듭니다.           

  Color                      x축 선의 색을 지정합니다.         string    black

  Labels                     x축에서 사용할 라벨을 지정합니다. object    null
                             라벨은 html 태그 형식 또는 배열             
                             형태로 사용할 수 있습니다.                  

  LabelsAngle                x축 라벨의 각도를 지정합니다.     number    0
                             양수일 때 지정한 각도만큼                   
                             왼쪽으로 회전하며 음수일 때                 
                             오른쪽으로 회전합니다.                      

  LabelsColor                x축 라벨의 색을 지정합니다.       object    null

  LabelsFontStyle            x축 라벨의 글꼴 스타일을          string    null
                             지정합니다.                                 

  LabelsFormattedDecimals    x축에서 %{value_formatted}처럼    number    0
                             형식이 지정된 라벨에서 지정한               
                             값만큼의 소수점을 표시합니다.               

  LabelsFormattedPoint       x축에서 %{value_formatted}처럼    string    .
                             형식이 지정된 라벨에서 소수점               
                             표시 방식을 지정합니다.                     

  LabelsFormattedThousand    x축에서 %{value_formatted}처럼    string    ,
                             형식이 지정된 라벨에서 천 단위              
                             구분 기호를 지정합니다.                     

  LabelsFormattedUnitsPost   x축에서 %{value_formatted}처럼    string    
                             형식이 지정된 라벨에서 뒤에                 
                             표시할 문자를 지정합니다.                   

  LabelsFormattedUnitsPre    x축에서 %{value_formatted}처럼    string    
                             형식이 지정된 라벨에서 앞에                 
                             표시할 문자를 지정합니다.                   

  LabelsHalign               x축 라벨의 가로 정렬을            object    null
                             지정합니다. left, right, center를           
                             사용할 수 있습니다.                         

  LabelsOffsetX              x축 라벨의 가로 오프셋을          number    0
                             지정합니다.                                 

  LabelsOffsetY              x축 라벨의 세로 오프셋을          number    0
                             지정합니다.                                 

  LabelsPosition             x축 라벨의 포지션을 지정합니다.   string    section
                             section, edge를 사용할 수                   
                             있습니다. section은 영역쪽에                
                             라벨이 위치하고 edge는 데이터               
                             포인트 점에 라벨이 위치합니다.              

  LabelsValign               라벨의 세로 정렬을 지정합니다.    object    null
                             top, bottom, center를 사용할 수             
                             있습니다.                                   

  Linewidth                  x축의 두께를 지정합니다.          number    1

  Position                   x축의 위치를 지정합니다. top,     string    bottom
                             bottom, center를 사용할 수                  
                             있습니다.                                   

  Tickmarks                  x축 라벨에 눈금을 표시할 지       boolean   true
                             여부입니다.                                 

  TickmarksCount             x축 라벨의 눈금 개수를            object    null
                             지정합니다.                                 

  TickmarksLastLeft          x축 라벨의 가장 왼쪽 마크를       object    null
                             표시할 지 여부입니다.                       

  TickmarksLastRight         x축 라벨의 가장 오른쪽 마크를     object    null
                             표시할 지 여부입니다.                       

  TickmarksLength            x축 라벨의 데이터마다 위치한      number    
                             마크값의 길이를 지정합니다.                 

  Title                      x축의 제목을 지정합니다.          string    

  TitleColor                 x축 제목의 색상을 지정합니다.     object    null

  TitleFontStyle             x축 제목의 글꼴 스타일을          string    null
                             지정합니다.                                 

  TitleHalign                x축 제목의 가로 정렬을            string    center
                             지정합니다.                                 
                             \'left\',\'right\',\'center\'를             
                             사용할 수 있습니다.                         

  TitleOffsetX               x축 제목의 가로 오프셋을          number    0
                             지정합니다.                                 

  TitleOffsetY               x축 제목의 세로 오프셋을          number    0
                             지정합니다.                                 

  TitlePos                   x축 제목의 위치를 지정합니다.     object    null
                             양수일 때 아래로 내려가고 음수일            
                             때 위로 올라갑니다.                         

  TitleValign                x축 제목의 수직 정렬을            string    top
                             지정합니다. top, bottom, center를           
                             사용할 수 있습니다.                         

  TitleX                     x축 제목의 가로 좌표를            object    null
                             지정합니다.                                 

  TitleY                     x축 제목의 세로 좌표를            object    null
                             지정합니다.                                 

  Use                        x축을 사용할 지 여부입니다.       boolean   true
  --------------------------------------------------------------------------------

#### ![스크린샷, 직사각형, 라인, 다채로움이(가) 표시된 사진 자동 생성된 설명](media/image32.png){width="7.579166666666667in" height="3.8965277777777776in"}X축 Property 기본 예제

var bar = new DxChartBar({

id: cvs,

elem : canvas,

binddataset : this.Dataset00,

data:\[\"bind:total\",\"bind:man\",\"bind:woman\"\],

options: {

xaxis: {

Use : false, // 차트의 X축을 Draw 할지 설정할 수 있습니다.

Labels: \[\"bind:indecators\"\], // X축 라벨의 데이터 값을 설 정할 수
있습니다.

주로 Nexacro 내 Dataset 바인딩을 통해 데이터 값을 설정 합니다.

Nexacro가 아닌 다른 프레임워크나 실행환경에선 배열값으로 설정할수
있습니다.\
ex) Lables :\['1','2','3','4','5'\]

AddLineSize : 10, // X축 선의 길이 값을 설정 할 수 있습니다. }

Color : \'red\', // X축의 색상을 설정 할 수 있습니다.

Position: \'bottom\' // X축의 위치를 설정 할 수 있습니다. 기본값은
bottom이며,\
top, bottom 두가지 값으로 설정 할 수 있습니다.

X축의 Position을 top으로 설정 할 시 차트가 상하반전이 되어 렌더링됩니다.

}

}

}).draw();

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

# **차트의 주요 메소드**

## DxChart 오브젝트

### appendAxis

기존의 차트에 X/Y축을 추가합니다.

+----------+-----------+---------+-----------------------------------+
| 파라미터 | objChart  | Object  | 대상이 되는 차트 오브젝트         |
+==========+===========+=========+===================================+
|          | objProp   | Object  | 추가할 X/Y축의 옵션 (JSON)        |
+----------+-----------+---------+-----------------------------------+
| 리턴값   | \-        | 없음    |                                   |
+----------+-----------+---------+-----------------------------------+
| 상세     | X/Y축을   |         |                                   |
| 설명     | 추        |         |                                   |
|          | 가합니다. |         |                                   |
|          |           |         |                                   |
|          | 추가한    |         |                                   |
|          | X/Y축은   |         |                                   |
|          | 기존의    |         |                                   |
|          | 축과      |         |                                   |
|          | 겹치지    |         |                                   |
|          | 않게      |         |                                   |
|          | 세팅을    |         |                                   |
|          | 합니다.   |         |                                   |
+----------+-----------+---------+-----------------------------------+
| 사용예   |           |         |                                   |
+----------+-----------+---------+-----------------------------------+

### redraw

등록된 모든 객체를 다시 그립니다.

+----------+-----------+---------+-----------------------------------+
| 파라미터 | color     | String  | (옵션) Clear할 때 배경으로 사용할 |
|          |           |         | 색상                              |
+==========+===========+=========+===================================+
|          | cvs       | Object  | (옵션) canvas object              |
+----------+-----------+---------+-----------------------------------+
| 리턴값   | \-        | 없음    |                                   |
+----------+-----------+---------+-----------------------------------+
| 상세     | 차트를    |         |                                   |
| 설명     | 다시      |         |                                   |
|          | 그립니다. |         |                                   |
+----------+-----------+---------+-----------------------------------+
| 사용예   | DxChart.  |         |                                   |
|          | redraw(); |         |                                   |
|          |           |         |                                   |
|          | Dx        |         |                                   |
|          | Chart.red |         |                                   |
|          | raw("blue |         |                                   |
|          | ",cavas); |         |                                   |
+----------+-----------+---------+-----------------------------------+

### reset

+----------+-----------+---------+-----------------------------------+
| 파라미터 | canvas    | Object  | canvas object                     |
+==========+===========+=========+===================================+
| 리턴값   | \-        | 없음    |                                   |
+----------+-----------+---------+-----------------------------------+
| 상세     | 캔버스를  |         |                                   |
| 설명     | 초기      |         |                                   |
|          | 화합니다. |         |                                   |
|          | 적용할 수 |         |                                   |
|          | 있는      |         |                                   |
|          | 개체의    |         |                                   |
|          | Object R  |         |                                   |
|          | egistry를 |         |                                   |
|          | 지웁니다  |         |                                   |
|          |           |         |                                   |
|          | 또한,     |         |                                   |
|          | Anti      |         |                                   |
|          | -aliasing |         |                                   |
|          | Translate |         |                                   |
|          | Fix,      |         |                                   |
|          | canvas를  |         |                                   |
|          | 지웁니다  |         |                                   |
+----------+-----------+---------+-----------------------------------+
| 사용예   | DxCh      |         |                                   |
|          | art.reset |         |                                   |
|          | (canvas); |         |                                   |
+----------+-----------+---------+-----------------------------------+

### convertDataset

+----------+-----------+---------+-----------------------------------+
| 파라미터 | dataset   | Object  | Dataset object                    |
+==========+===========+=========+===================================+
|          | arrCol    | Array   | 변환할 데이터셋 컬럼 명           |
+----------+-----------+---------+-----------------------------------+
|          | nDiv      | Number  | (옵션) 반복 행 설정               |
+----------+-----------+---------+-----------------------------------+
|          | Option    | String  | (옵션) "linear" 설정 시 컬럼 별   |
|          |           |         | 데이터 생성                       |
+----------+-----------+---------+-----------------------------------+
| 리턴값   | arrData   | Data    |                                   |
|          |           | set에서 |                                   |
|          |           | 배열로  |                                   |
|          |           | 반환된  |                                   |
|          |           | 데이터  |                                   |
+----------+-----------+---------+-----------------------------------+
| 상세     | DataSet을 |         |                                   |
| 설명     | 배열로    |         |                                   |
|          | 반환하는  |         |                                   |
|          | 메서      |         |                                   |
|          | 드입니다. |         |                                   |
|          |           |         |                                   |
|          | \[예시\]  |         |                                   |
|          |           |         |                                   |
|          | ![        |         |                                   |
|          | 스크린샷, |         |                                   |
|          | 번호,     |         |                                   |
|          | 라인,     |         |                                   |
|          | 텍스      |         |                                   |
|          | 트이(가)  |         |                                   |
|          | 표시된    |         |                                   |
|          | 사진 자동 |         |                                   |
|          | 생성된    |         |                                   |
|          | 설명]     |         |                                   |
|          | (me%20dia |         |                                   |
|          | /image%20 |         |                                   |
|          | 45.png){w |         |                                   |
|          | idth="2.1 |         |                                   |
|          | 145833333 |         |                                   |
|          | 333335in" |         |                                   |
|          | hei       |         |                                   |
|          | ght="0.69 |         |                                   |
|          | 888779527 |         |                                   |
|          | 55905in"} |         |                                   |
|          |           |         |                                   |
|          | -linear   |         |                                   |
|          | 사용 시   |         |                                   |
|          |           |         |                                   |
|          | arr       |         |                                   |
|          | =\[\[가,  |         |                                   |
|          | 나,다\],\ |         |                                   |
|          | \         |         |                                   |
|          | [라,마,바 |         |                                   |
|          | \],\[사,  |         |                                   |
|          | 아,자\]\] |         |                                   |
|          |           |         |                                   |
|          | -미설정   |         |                                   |
|          | 시        |         |                                   |
|          |           |         |                                   |
|          | arr       |         |                                   |
|          | =\[\[가,  |         |                                   |
|          | 라,사\],\ |         |                                   |
|          | \         |         |                                   |
|          | [나,마,아 |         |                                   |
|          | \],\[다,  |         |                                   |
|          | 바,자\]\] |         |                                   |
+----------+-----------+---------+-----------------------------------+
| 사용예   | DxCha     |         |                                   |
|          | rt.conver |         |                                   |
|          | tDataset( |         |                                   |
|          | this.data |         |                                   |
|          | set00,\[\ |         |                                   |
|          | "bind:Col |         |                                   |
|          | umn0\",\" |         |                                   |
|          | bind:Colu |         |                                   |
|          | mn1\"\]); |         |                                   |
|          | DxC       |         |                                   |
|          | hart.conv |         |                                   |
|          | ertDatase |         |                                   |
|          | t(this.da |         |                                   |
|          | taset00,\ |         |                                   |
|          | \         |         |                                   |
|          | [\"bind:C |         |                                   |
|          | olumn0\", |         |                                   |
|          | \"bind:Co |         |                                   |
|          | lumn1\"\] |         |                                   |
|          | ,null,\"l |         |                                   |
|          | inear\"); |         |                                   |
+----------+-----------+---------+-----------------------------------+

### clear

+----------+-----------+---------+-----------------------------------+
| 파라미터 | canvas    | Object  | canvas object                     |
+==========+===========+=========+===================================+
|          | color     | String  | (옵션) 컬러 값                    |
+----------+-----------+---------+-----------------------------------+
| 리턴값   | \-        | 없음    |                                   |
+----------+-----------+---------+-----------------------------------+
| 상세     | 캔버스    |         |                                   |
| 설명     | 위에 직   |         |                                   |
|          | 사각형을  |         |                                   |
|          | 그려      |         |                                   |
|          | 캔버스를  |         |                                   |
|          | 지웁니다. |         |                                   |
|          | 색상과    |         |                                   |
|          | 차트를 명 |         |                                   |
|          | 시적으로  |         |                                   |
|          | 지정하지  |         |                                   |
|          | 않으면    |         |                                   |
|          | 마지막    |         |                                   |
|          | 차트를    |         |                                   |
|          | 지우며,   |         |                                   |
|          | clearto   |         |                                   |
|          | 옵션으로  |         |                                   |
|          | 지우는    |         |                                   |
|          | 동작에    |         |                                   |
|          | 사용할    |         |                                   |
|          | 색상을    |         |                                   |
|          | 지정할 수 |         |                                   |
|          | 있습니다. |         |                                   |
+----------+-----------+---------+-----------------------------------+
| 사용예   | DxCh      |         |                                   |
|          | art.clear |         |                                   |
|          | (canvas); |         |                                   |
|          |           |         |                                   |
|          | DxC       |         |                                   |
|          | hart.clea |         |                                   |
|          | r(canvas, |         |                                   |
|          | \'red\'); |         |                                   |
+----------+-----------+---------+-----------------------------------+

### \_shadeColor

  ------------------------------------------------------------------------------------
  파라미터   hueIn                                 String   hex color
  ---------- ------------------------------------- -------- --------------------------
             pcIn                                  Number   퍼센트 값

  리턴값     String                                밝기     
                                                   계산된   
                                                   hex      
                                                   color 값 

  상세 설명  퍼센트 값을 기반으로 색상을 어둡게             
             또는 밝게 조절합니다. 입력된 퍼센트            
             값에 따라서 해당 색상을 더 어둡게              
             또는 더 밝게 만들어서 반환합니다.              

  사용예     DxChart.\_shadeColor("#FF6A8E",30);            
  ------------------------------------------------------------------------------------

### arrayClone

  -------------------------------------------------------------------------------
  파라미터   object                          Array    복제할 arrary
  ---------- ------------------------------- -------- ---------------------------
  리턴값     Array                           복제한   
                                             array    

  상세 설명  Array를 복제합니다.                      

  사용예     DxChart.arrayClone(arryData);            
  -------------------------------------------------------------------------------

### clipTo.start

+----------+----------+----------+-----------------------------------+
| 파라미터 | object   | Object   | canvas object                     |
+==========+==========+==========+===================================+
|          | di       | Object,  | 자르기 위한 설정 값               |
|          | mensions |          |                                   |
|          |          | Array,   |                                   |
|          |          |          |                                   |
|          |          | String   |                                   |
+----------+----------+----------+-----------------------------------+
| 리턴값   | \-       | 없음     |                                   |
+----------+----------+----------+-----------------------------------+
| 상세     | 캔버스를 |          |                                   |
| 설명     | 클리     |          |                                   |
|          | 핑하는데 |          |                                   |
|          | 사용     |          |                                   |
|          | 합니다.\ |          |                                   |
|          | "tophalf |          |                                   |
|          | / bo     |          |                                   |
|          | ttomhalf |          |                                   |
|          | /        |          |                                   |
|          | lefthalf |          |                                   |
|          | / rig    |          |                                   |
|          | hthalf\" |          |                                   |
|          | 옵션들은 |          |                                   |
|          | 캔버스를 |          |                                   |
|          | 각각     |          |                                   |
|          | 상단 반, |          |                                   |
|          | 하단 반, |          |                                   |
|          | 왼쪽 반, |          |                                   |
|          | 오른쪽   |          |                                   |
|          | 반으로   |          |                                   |
|          | 자르는데 |          |                                   |
|          | 사용     |          |                                   |
|          | 됩니다.  |          |                                   |
|          | 만약     |          |                                   |
|          | margin이 |          |                                   |
|          | 다       |          |                                   |
|          | 르다면,\ |          |                                   |
|          | "tophalf |          |                                   |
|          | .margins |          |                                   |
|          | / bo     |          |                                   |
|          | ttomhalf |          |                                   |
|          | .margins |          |                                   |
|          | /        |          |                                   |
|          | lefthalf |          |                                   |
|          | .margins |          |                                   |
|          | / rig    |          |                                   |
|          | hthalf.m |          |                                   |
|          | argins\" |          |                                   |
|          | 옵션들을 |          |                                   |
|          | 사용해야 |          |                                   |
|          | 합니다.  |          |                                   |
+----------+----------+----------+-----------------------------------+
| 사용예   | D        |          |                                   |
|          | xChart.c |          |                                   |
|          | lipTo.st |          |                                   |
|          | art(obj, |          |                                   |
|          | \'top    |          |                                   |
|          | half\'); |          |                                   |
|          |          |          |                                   |
|          | D        |          |                                   |
|          | xChart.c |          |                                   |
|          | lipTo.st |          |                                   |
|          | art(obj, |          |                                   |
|          | \'b a    |          |                                   |
|          | 250 150  |          |                                   |
|          | 150 0    |          |                                   |
|          | 6.29     |          |                                   |
|          | false s  |          |                                   |
|          | #aaa\'); |          |                                   |
+----------+----------+----------+-----------------------------------+

### clipTo.end

  ---------------------------------------------------------------------------
  파라미터   \-                       \-       없음
  ---------- ------------------------ -------- ------------------------------
  리턴값     \-                       없음     

  상세 설명  DxChart.clipTo.start()            
             함수 에 의해 시작된               
             클리핑을 종료합니다               

  사용예     DxChart.clipTo.end();             
  ---------------------------------------------------------------------------

### arraySum

  ----------------------------------------------------------------------------------
  파라미터   Array                                Array   합을 구할 배열
  ---------- ------------------------------------ ------- --------------------------
  리턴값     String                               합계 값 

  상세 설명  배열의 원소 합을 구합니다.                   

  사용예     DxChart.arraySum(obj.orgData\[0\])           
  ----------------------------------------------------------------------------------

### arrayPad

  ---------------------------------------------------------------------------
  파라미터   Array                   Array     패딩 할 대상 배열
  ---------- ----------------------- --------- ------------------------------
             Length                  Number    패딩 배열의 길이

             value                   String    패딩에 사용할 값

  리턴값     Array                   패딩이    
                                     완료된    
                                     배열      

  상세 설명  주어진 배열을 특정                
             길이로 패딩하는                   
             것입니다. 배열의 길이를           
             지정된 길이로 늘리고,             
             필요한 경우 지정된                
             값으로 채우는 것을                
             의미합니다                        

  사용예     DxChart.arrayPad(\[1,             
             2, 3\], 5, "value");              
  ---------------------------------------------------------------------------

### clearAnnotations

  ----------------------------------------------------------------------------------
  파라미터   canvas                             Object   Dataset object
  ---------- ---------------------------------- -------- ---------------------------
  리턴값     \-                                 없음     

  상세 설명  localStorage에서 주석 data를                
             지웁니다.                                   

  사용예     DxChart.clearAnnotations(canvas)            
  ----------------------------------------------------------------------------------

### arrayLinearizeString

  --------------------------------------------------------------------------------------------------------------
  파라미터   arguments                                                             String,   선형화 할 데이터
                                                                                   Object    
  ---------- --------------------------------------------------------------------- --------- -------------------
  리턴값     arr                                                                   선형화 된 
                                                                                   배열      

  상세 설명  주어진 인자들을 문자열 형태로 선형화하여 배열로 반환하는 역할을                 
             합니다                                                                          

  사용예     DxChart.arrayLinearizeString(DxChart.convertDataset(this.Dataset00,             
             \[\"bind:KOSPI\",\"bind:KOSDAQ\"\], null, \"linear\"))                          
  --------------------------------------------------------------------------------------------------------------

### arrayRandom

+----------+-----------+----------+----------------------------------+
| 파라미터 | count     | Number   | 배열의 길이                      |
+==========+===========+==========+==================================+
|          | min       | Number   | Min 값                           |
+----------+-----------+----------+----------------------------------+
|          | max       | Number   | Max 값                           |
+----------+-----------+----------+----------------------------------+
|          | decimals  | Number   | 소수점 설정                      |
+----------+-----------+----------+----------------------------------+
| 리턴값   | Array     | 랜덤     |                                  |
|          |           | 값이     |                                  |
|          |           | 담긴     |                                  |
|          |           | 배열     |                                  |
+----------+-----------+----------+----------------------------------+
| 상세     | 선언한    |          |                                  |
| 설명     | 배열의    |          |                                  |
|          | 길이만큼  |          |                                  |
|          | 랜덤 한   |          |                                  |
|          | 배열를    |          |                                  |
|          | 만듭니다. |          |                                  |
+----------+-----------+----------+----------------------------------+
| 사용예   | DxCh      |          |                                  |
|          | art.array |          |                                  |
|          | Random(7, |          |                                  |
|          | 0, 10);   |          |                                  |
|          |           |          |                                  |
|          | DxCh      |          |                                  |
|          | art.array |          |                                  |
|          | Random(7, |          |                                  |
|          | 0, 10,    |          |                                  |
|          | 2);       |          |                                  |
|          | //소수점  |          |                                  |
|          | 2자리까지 |          |                                  |
+----------+-----------+----------+----------------------------------+

### colorSet, setColorList

  -------------------------------------------------------------------------------------
  파라미터   categoryName                             String   카테고리 이름
  ---------- ---------------------------------------- -------- ------------------------
  리턴값     \-                                       없음     

  상세 설명  Chart의 default 컬러를 설정합니다.                
             사용자가 정의한 카테고리에서 색상을               
             가져와서 이를 기본 색상 값으로                    
             설정합니다.                                       

  사용예     DxChart.colorSet(\"ChartColorBasic\");            
  -------------------------------------------------------------------------------------

### random

  -------------------------------------------------------------------------------
  파라미터   min                       Number        최소값
  ---------- ------------------------- ------------- ----------------------------
             max                       Number        최대값

             decimals                  Number        (옵션)소수점 이하 자릿수를
                                                     설정하는 값

  리턴값     Number                    함수 내       
                                       toFixed()를   
                                       사용하여      
                                       소수점 이하   
                                       자릿수를      
                                       조절하고,     
                                       Number를      
                                       사용하여      
                                       결과를 숫자로 
                                       변환한 후     
                                       반환합니다.   

  상세 설명  주어진 최솟값(min)과                    
             최댓값(max) 사이의 난수를               
             생성하는 기능을                         
             제공합니다.\                            
             다양한 범위와 소수점 이하               
             자릿수를 갖는 난수를                    
             생성할 수 있습니다.                     

  사용예     DxChart.random(min,max)                 
  -------------------------------------------------------------------------------

### redrawCanvas

  --------------------------------------------------------------------------------------------
  파라미터   canvas                                         Object    Redraw할 canvas 객체
  ---------- ---------------------------------------------- --------- ------------------------
             clear                                          Boolean   (옵션)Canvas를 지울지
                                                                      여부를 결정하는
                                                                      플래값(True,false)

             color                                          String    (옵션) redraw할 시
                                                                      차트의 배경색을 설정

  리턴값     \- 없음                                                  

  상세 설명  주어진 캔버스(canvas)에 등록된 모든 객체를               
             다시 그리도록 하는 기능을 제공합니다. 만약               
             clear 값이 주어지지 않거나, boolean 타입이면서           
             false가 아닌 경우에는 캔버스를 지우도록                  
             합니다.                                                  

  사용예     DxChart.redrawCanvas(this.canvas,true,'red')             
  --------------------------------------------------------------------------------------------

### REG.getFirstObjectByType

+----------+-----------+---------+-----------------------------------+
| 파라미터 | type      | String  | 객체의 유형을 나타내는            |
|          |           |         | 문자열(type)을 받습니다.          |
+==========+===========+=========+===================================+
| 리턴값   | -Object   | 객체의  |                                   |
|          |           | 유형이  |                                   |
|          |           | 입력된  |                                   |
|          |           | 유형과  |                                   |
|          |           | 일      |                                   |
|          |           | 치하는  |                                   |
|          |           | 경우    |                                   |
|          |           | 해당    |                                   |
|          |           | 객체를  |                                   |
|          |           | 반환    |                                   |
|          |           | 합니다. |                                   |
|          |           |         |                                   |
|          |           | 만약 일 |                                   |
|          |           | 치하는  |                                   |
|          |           | 객체가  |                                   |
|          |           | 없으면  |                                   |
|          |           | null을  |                                   |
|          |           | 반환    |                                   |
|          |           | 합니다. |                                   |
+----------+-----------+---------+-----------------------------------+
| 상세     | 주어진    |         |                                   |
| 설명     | 유형      |         |                                   |
|          | (type)과  |         |                                   |
|          | 일치하는  |         |                                   |
|          | 첫 번째   |         |                                   |
|          | 객체를    |         |                                   |
|          | 찾아      |         |                                   |
|          | 반환하는  |         |                                   |
|          | 기능을 제 |         |                                   |
|          | 공합니다. |         |                                   |
+----------+-----------+---------+-----------------------------------+
| 사용예   | DxC       |         |                                   |
|          | hart.REG. |         |                                   |
|          | getFirstO |         |                                   |
|          | bjectByTy |         |                                   |
|          | pe('bar') |         |                                   |
+----------+-----------+---------+-----------------------------------+

### text

+----------+-----------+---------+-----------------------------------+
| 파라미터 | args      | Object  | 차트의 텍스트와 관련된 설정을     |
|          |           |         | 나타내는 객체                     |
+==========+===========+=========+===================================+
| 리턴값   | 없음      |         |                                   |
+----------+-----------+---------+-----------------------------------+
| 상세     | 주어진    |         |                                   |
| 설명     | 설정에    |         |                                   |
|          | 따라      |         |                                   |
|          | 차트의    |         |                                   |
|          | 텍스트를  |         |                                   |
|          | 처리하고, |         |                                   |
|          | 설정이    |         |                                   |
|          | 주어지지  |         |                                   |
|          | 않은 경우 |         |                                   |
|          | 기본값을  |         |                                   |
|          | 적용하여  |         |                                   |
|          | 텍스트    |         |                                   |
|          | 객체를    |         |                                   |
|          | 생성하고  |         |                                   |
|          | 반        |         |                                   |
|          | 환합니다. |         |                                   |
+----------+-----------+---------+-----------------------------------+
| 사용예   | DxCha     |         |                                   |
|          | rt.text({ |         |                                   |
|          |           |         |                                   |
|          | object:   |         |                                   |
|          | pie,      |         |                                   |
|          |           |         |                                   |
|          | font: \'  |         |                                   |
|          | Tahoma\', |         |                                   |
|          |           |         |                                   |
|          | size: 9,  |         |                                   |
|          |           |         |                                   |
|          | color:\   |         |                                   |
|          | 'white\', |         |                                   |
|          |           |         |                                   |
|          | bold:     |         |                                   |
|          | false     |         |                                   |
|          |           |         |                                   |
|          | });       |         |                                   |
+----------+-----------+---------+-----------------------------------+

### Registry.get

  ------------------------------------------------------------------------------------
  파라미터   name                             String        가져올 객체의 이름
  ---------- -------------------------------- ------------- --------------------------
  리턴값     Object                           해당 이름에   
                                              해당하는      
                                              객체를 찾아   
                                              반환합니다.   

  상세 설명  DxChart 레지스트리에서 특정                    
             이름에 해당하는 객체를 쉽게                    
             가져올 수 있습니다. 주로 객체의                
             이름을 통해 레지스트리에서 해당                
             객체를 검색하는 데 사용됩니다.                 

  사용예     DxChart.Registry.get(\'name\')                 
  ------------------------------------------------------------------------------------

### parseRadialGradientInfo

  -----------------------------------------------------------------------------------------
  파라미터   obj                                    Object        그라데이션을 생성하는 데
                                                                  사용되는 캔버스
                                                                  컨텍스트나 그라데이션을
                                                                  적용할 객체
  ---------- -------------------------------------- ------------- -------------------------
             val                                    String        그라데이션에 대한 문자열
                                                                  값

             centerX1                               Number        그라데이션의 시작 지점

             centerY1                               Number        그라데이션의 시작 지점

             radius1                                Number        시작 반지름

             centerX2                               Number        그라데이션의 끝 지점

             centerY2                               Number        그라데이션의 끝 지점

             radius2                                Number        끝 반지름

  리턴값     Object                                 최종적으로    
                                                    생성된        
                                                    그라데이션    
                                                    객체를        
                                                    반환합니다.   

  상세 설명  주어진 값(**val**)을 기반으로 원형                   
             그라데이션(radial gradient)을 처리하고               
             해당 그라데이션을 생성하여 반환합니다.               

  사용예     DxChart.parseRadialGradientInfo(obj,                 
             "val", centerX1, centerY1, radius1,                  
             centerX2, centerY2, radius2)                         
  -----------------------------------------------------------------------------------------

### getMaskString

  -------------------------------------------------------------------------------------
  파라미터   type                              String        마스킹을 적용할 데이터
                                                             타입
  ---------- --------------------------------- ------------- --------------------------
             mask                              String        마스크 문자열,

             value                                           적용할 값

  리턴값                                       마스크가      
                                               적용된 값이   
                                               변수에        
                                               할당됩니다.   

  상세 설명  주어진 타입(type), 마스크(mask),                
             및 값(value)에 대해 마스킹 처리를               
             수행하여 변환된 값을 반환하는                   
             기능을 제공합니다.                              

  사용예     DxChart.getMaskString(\'date\',                 
             \'yyyy-MM\', value)                             
  -------------------------------------------------------------------------------------

### hideTooltip

  ----------------------------------------------------------------------------
  파라미터   obj                        Object   툴팁을 숨길 대상 객체
  ---------- -------------------------- -------- -----------------------------
  리턴값     없음                                

  상세 설명  현재 표시된 툴팁을 숨기는           
             역할을 합니다.                      

  사용예     DxChart.hideTooltip(obj)            
  ----------------------------------------------------------------------------

### HTML.Key

+----------+-----------+---------+-----------------------------------+
| 파라미터 | id        | String  | HTML에서 생성되는 Key 테이블의    |
|          |           |         | 부모 엘리먼트                     |
+==========+===========+=========+===================================+
|          | p         | Object  | 생성되는 HTML Key 테이블과 관련된 |
|          | roperties |         | 속성들을 가지는 객체              |
+----------+-----------+---------+-----------------------------------+
| 리턴값   |           | 반      |                                   |
|          |           | 환값은  |                                   |
|          |           | HTML    |                                   |
|          |           | Key 테  |                                   |
|          |           | 이블에  |                                   |
|          |           | 대한    |                                   |
|          |           | DOM     |                                   |
|          |           | 엘리먼  |                                   |
|          |           | 트이며, |                                   |
|          |           | 해당    |                                   |
|          |           | 엘리    |                                   |
|          |           | 먼트는  |                                   |
|          |           | 주어진  |                                   |
|          |           | id에 기 |                                   |
|          |           | 반하여  |                                   |
|          |           | 유일한  |                                   |
|          |           | 식      |                                   |
|          |           | 별자로  |                                   |
|          |           | 생성    |                                   |
|          |           | 되었습  |                                   |
|          |           | 니다.\" |                                   |
+----------+-----------+---------+-----------------------------------+
| 상세     | HTML      |         |                                   |
| 설명     | 기반의    |         |                                   |
|          | 키(Key)를 |         |                                   |
|          | 생성하고  |         |                                   |
|          | 스타일을  |         |                                   |
|          | 적용한    |         |                                   |
|          | 후, 해당  |         |                                   |
|          | 키를      |         |                                   |
|          | 나타내는  |         |                                   |
|          | 테이블을  |         |                                   |
|          | 반        |         |                                   |
|          | 환합니다. |         |                                   |
|          | 반환된    |         |                                   |
|          | 테이블은  |         |                                   |
|          | 호출한    |         |                                   |
|          | 측에서    |         |                                   |
|          | 적절히    |         |                                   |
|          | 사용할 수 |         |                                   |
|          | 있습니다. |         |                                   |
+----------+-----------+---------+-----------------------------------+
| 사용예   | var key = |         |                                   |
|          | DxCh      |         |                                   |
|          | art.HTML. |         |                                   |
|          | Key(\'con |         |                                   |
|          | tainer\', |         |                                   |
|          |           |         |                                   |
|          | {         |         |                                   |
|          |           |         |                                   |
|          | colors:   |         |                                   |
|          | colors,   |         |                                   |
|          |           |         |                                   |
|          | la        |         |                                   |
|          | bels:\[\' |         |                                   |
|          | Louise\', |         |                                   |
|          | \'Fred\', |         |                                   |
|          | \'C       |         |                                   |
|          | harley\', |         |                                   |
|          | \'L       |         |                                   |
|          | ucy\',\'K |         |                                   |
|          | evin\',\' |         |                                   |
|          | Luis\',\' |         |                                   |
|          | Pete\',\' |         |                                   |
|          | Jake\'\], |         |                                   |
|          |           |         |                                   |
|          | tableCss: |         |                                   |
|          | {         |         |                                   |
|          |           |         |                                   |
|          | position: |         |                                   |
|          | \'ab      |         |                                   |
|          | solute\', |         |                                   |
|          |           |         |                                   |
|          | top:      |         |                                   |
|          | \'50%\',  |         |                                   |
|          |           |         |                                   |
|          | right:\   |         |                                   |
|          | '-70px\', |         |                                   |
|          |           |         |                                   |
|          | t         |         |                                   |
|          | ransform: |         |                                   |
|          | \'        |         |                                   |
|          | translate |         |                                   |
|          | Y(-50%)\' |         |                                   |
|          |           |         |                                   |
|          | }         |         |                                   |
|          |           |         |                                   |
|          | })        |         |                                   |
+----------+-----------+---------+-----------------------------------+

### isArray

  -----------------------------------------------------------------------------
  파라미터   obj                    Object        배열인지 판별할 객체
  ---------- ---------------------- ------------- -----------------------------
  리턴값     Boolean                판별하고자    
                                    하는 객체가   
                                    배열이면      
                                    True, 아니면  
                                    False를       
                                    반환합니다.   

  상세 설명  주어진 변수가 배열인지               
             아닌지를 판별하는                    
             역할을 합니다.                       

  사용예     DxChart.isArray(obj)                 
  -----------------------------------------------------------------------------

### linearGradient

+----------+-----------+---------+-----------------------------------+
| 파라미터 | obj       | Object  | 그라데이션을 생성할 객체를        |
|          |           |         | 매개변수로 받습니다.              |
+==========+===========+=========+===================================+
| 리턴값   | Object    | gradien |                                   |
|          |           | t객체를 |                                   |
|          |           | 반환    |                                   |
|          |           | 합니다. |                                   |
+----------+-----------+---------+-----------------------------------+
| 상세     | 주어진 매 |         |                                   |
| 설명     | 개변수를  |         |                                   |
|          | 사용하여  |         |                                   |
|          | 선 그라   |         |                                   |
|          | 데이션을  |         |                                   |
|          | 생성하고, |         |                                   |
|          | gradient  |         |                                   |
|          | 객체를 반 |         |                                   |
|          | 환합니다. |         |                                   |
|          | 이후      |         |                                   |
|          | 반환된 그 |         |                                   |
|          | 라데이션  |         |                                   |
|          | 객체를    |         |                                   |
|          | 사용하여  |         |                                   |
|          | 캔버스에  |         |                                   |
|          | 선 그라   |         |                                   |
|          | 데이션을  |         |                                   |
|          | 적용할 수 |         |                                   |
|          | 있습니다. |         |                                   |
+----------+-----------+---------+-----------------------------------+
| 사용예   | DxChar    |         |                                   |
|          | t.linearG |         |                                   |
|          | radient({ |         |                                   |
|          |           |         |                                   |
|          | object:   |         |                                   |
|          | obj,      |         |                                   |
|          |           |         |                                   |
|          | x1: 0,    |         |                                   |
|          | y1: 0,    |         |                                   |
|          | x2: 0,    |         |                                   |
|          | y2: 250,  |         |                                   |
|          |           |         |                                   |
|          | colors:   |         |                                   |
|          | \[\'rgba( |         |                                   |
|          | 255,255,2 |         |                                   |
|          | 55,0.75)\ |         |                                   |
|          | ',\'rgba( |         |                                   |
|          | 255,255,2 |         |                                   |
|          | 55,0)\'\] |         |                                   |
|          |           |         |                                   |
|          | })        |         |                                   |
+----------+-----------+---------+-----------------------------------+

### log

  -------------------------------------------------------------------------
  파라미터   n                Number       로그 값으로 변환될 값
  ---------- ---------------- ------------ --------------------------------
             base             Number       로그 값의 base(밑)값이 될 값

  리턴값     Number           반환 값은    
                              주어진       
                              밑(base)에   
                              대한 로그 값 

  상세 설명  주어진 수에 대한              
             로그 값을                     
             계산하는 역할을               
             합니다.                       

  사용예     DxChart.log(n,                
             10)                           
  -------------------------------------------------------------------------

### setColorList

+----------+-----------+---------+-----------------------------------+
| 파라미터 | cat       | String  | 컬러 카테고리의 이름              |
|          | egoryName |         |                                   |
+==========+===========+=========+===================================+
| 리턴값   | 없음      |         |                                   |
+----------+-----------+---------+-----------------------------------+
| 상세     | 주어진    |         |                                   |
| 설명     | cat       |         |                                   |
|          | egoryName |         |                                   |
|          | 기반으로  |         |                                   |
|          | 해당하는  |         |                                   |
|          | 컬러      |         |                                   |
|          | 설정을    |         |                                   |
|          | DxChar    |         |                                   |
|          | t.selectC |         |                                   |
|          | olorSet에 |         |                                   |
|          | 할당하여  |         |                                   |
|          | 차트에서  |         |                                   |
|          | 사용할    |         |                                   |
|          | 기본      |         |                                   |
|          | 컬러셋을  |         |                                   |
|          | 설정하는  |         |                                   |
|          | 역할을    |         |                                   |
|          | 합니다.   |         |                                   |
|          |           |         |                                   |
|          | cat       |         |                                   |
|          | egortName |         |                                   |
|          | 으로는    |         |                                   |
|          |           |         |                                   |
|          | (1) \"    |         |                                   |
|          |           |         |                                   |
|          | ChartColo |         |                                   |
|          |           |         |                                   |
|          | rBasic\", |         |                                   |
|          |           |         |                                   |
|          | <!-- -->  |         |                                   |
|          |           |         |                                   |
|          | (4)       |         |                                   |
|          | \"ChartCo |         |                                   |
|          |           |         |                                   |
|          | lorful\", |         |                                   |
|          |           |         |                                   |
|          | (5) \     |         |                                   |
|          |           |         |                                   |
|          | "ChartCol |         |                                   |
|          |           |         |                                   |
|          | orBlue\", |         |                                   |
|          |           |         |                                   |
|          | (6) \"C   |         |                                   |
|          |           |         |                                   |
|          | hartColor |         |                                   |
|          |           |         |                                   |
|          | Google\", |         |                                   |
|          |           |         |                                   |
|          | (7) \"C   |         |                                   |
|          |           |         |                                   |
|          | hartColor |         |                                   |
|          |           |         |                                   |
|          | Purple\", |         |                                   |
|          |           |         |                                   |
|          | (8) \"    |         |                                   |
|          |           |         |                                   |
|          | ChartColo |         |                                   |
|          |           |         |                                   |
|          | rGreen\", |         |                                   |
|          |           |         |                                   |
|          | (9)       |         |                                   |
|          | \"ChartCo |         |                                   |
|          |           |         |                                   |
|          | lorRed\", |         |                                   |
|          |           |         |                                   |
|          | (10) \    |         |                                   |
|          |           |         |                                   |
|          | "ChartCol |         |                                   |
|          |           |         |                                   |
|          | orDual\", |         |                                   |
|          |           |         |                                   |
|          | (11) \    |         |                                   |
|          |           |         |                                   |
|          | "ChartCol |         |                                   |
|          |           |         |                                   |
|          | orGray\", |         |                                   |
|          |           |         |                                   |
|          | (12) \    |         |                                   |
|          |           |         |                                   |
|          | "ChartCol |         |                                   |
|          |           |         |                                   |
|          | orWhite\" |         |                                   |
|          |           |         |                                   |
|          |      등이 |         |                                   |
|          |           |         |                                   |
|          | 설정되어  |         |                                   |
|          |           |         |                                   |
|          | 있습니다. |         |                                   |
+----------+-----------+---------+-----------------------------------+
| 사용예   | Dx        |         |                                   |
|          | Chart.set |         |                                   |
|          | ColorList |         |                                   |
|          | (\"catego |         |                                   |
|          | tyName\") |         |                                   |
+----------+-----------+---------+-----------------------------------+

### colorSet

+----------+-----------+---------+-----------------------------------+
| 파라미터 | cat       | String  | 컬러 카테고리의 이름              |
|          | egoryName |         |                                   |
+==========+===========+=========+===================================+
| 리턴값   | 없음      |         |                                   |
+----------+-----------+---------+-----------------------------------+
| 상세     | 주어진    |         |                                   |
| 설명     | cat       |         |                                   |
|          | egoryName |         |                                   |
|          | 기반으로  |         |                                   |
|          | 해당하는  |         |                                   |
|          | 컬러      |         |                                   |
|          | 설정을    |         |                                   |
|          | DxChar    |         |                                   |
|          | t.selectC |         |                                   |
|          | olorSet에 |         |                                   |
|          | 할당하여  |         |                                   |
|          | 차트에서  |         |                                   |
|          | 사용할    |         |                                   |
|          | 기본      |         |                                   |
|          | 컬러셋을  |         |                                   |
|          | 설정하는  |         |                                   |
|          | 역할을    |         |                                   |
|          | 합니다.   |         |                                   |
|          |           |         |                                   |
|          | cat       |         |                                   |
|          | egortName |         |                                   |
|          | 으로는    |         |                                   |
|          |           |         |                                   |
|          | (2) \"    |         |                                   |
|          |           |         |                                   |
|          | ChartColo |         |                                   |
|          |           |         |                                   |
|          | rBasic\", |         |                                   |
|          |           |         |                                   |
|          | <!-- -->  |         |                                   |
|          |           |         |                                   |
|          | (13)      |         |                                   |
|          | \"ChartCo |         |                                   |
|          |           |         |                                   |
|          | lorful\", |         |                                   |
|          |           |         |                                   |
|          | (14) \    |         |                                   |
|          |           |         |                                   |
|          | "ChartCol |         |                                   |
|          |           |         |                                   |
|          | orBlue\", |         |                                   |
|          |           |         |                                   |
|          | (15) \"C  |         |                                   |
|          |           |         |                                   |
|          | hartColor |         |                                   |
|          |           |         |                                   |
|          | Google\", |         |                                   |
|          |           |         |                                   |
|          | (16) \"C  |         |                                   |
|          |           |         |                                   |
|          | hartColor |         |                                   |
|          |           |         |                                   |
|          | Purple\", |         |                                   |
|          |           |         |                                   |
|          | (17) \"   |         |                                   |
|          |           |         |                                   |
|          | ChartColo |         |                                   |
|          |           |         |                                   |
|          | rGreen\", |         |                                   |
|          |           |         |                                   |
|          | (18)      |         |                                   |
|          | \"ChartCo |         |                                   |
|          |           |         |                                   |
|          | lorRed\", |         |                                   |
|          |           |         |                                   |
|          | (19) \    |         |                                   |
|          |           |         |                                   |
|          | "ChartCol |         |                                   |
|          |           |         |                                   |
|          | orDual\", |         |                                   |
|          |           |         |                                   |
|          | (20) \    |         |                                   |
|          |           |         |                                   |
|          | "ChartCol |         |                                   |
|          |           |         |                                   |
|          | orGray\", |         |                                   |
|          |           |         |                                   |
|          | (21) \    |         |                                   |
|          |           |         |                                   |
|          | "ChartCol |         |                                   |
|          |           |         |                                   |
|          | orWhite\" |         |                                   |
|          |           |         |                                   |
|          |      등이 |         |                                   |
|          |           |         |                                   |
|          | 설정되어  |         |                                   |
|          |           |         |                                   |
|          | 있습니다. |         |                                   |
+----------+-----------+---------+-----------------------------------+
| 사용예   | DxChart.  |         |                                   |
|          | setColorL |         |                                   |
|          | ist(\"cat |         |                                   |
|          | egotyName |         |                                   |
|          | \")       |         |                                   |
+----------+-----------+---------+-----------------------------------+

### numberFormat

+----------+-----------+---------+-----------------------------------+
| 파라미터 | args      | Object  | 포맷팅할 숫자의 객체              |
+==========+===========+=========+===================================+
| 리턴값   | String    | 포      |                                   |
|          |           | 맷팅된  |                                   |
|          |           | 숫자를  |                                   |
|          |           | 나      |                                   |
|          |           | 타내는  |                                   |
|          |           | 문자열  |                                   |
+----------+-----------+---------+-----------------------------------+
| 상세     | 숫자를 천 |         |                                   |
| 설명     | 단위로    |         |                                   |
|          | 구분하여  |         |                                   |
|          | 읽기 쉽게 |         |                                   |
|          | 포        |         |                                   |
|          | 맷팅하는  |         |                                   |
|          | 기능을 수 |         |                                   |
|          | 행합니다. |         |                                   |
|          | 반환값은  |         |                                   |
|          | 포맷팅된  |         |                                   |
|          | 천        |         |                                   |
|          | 단위로,   |         |                                   |
|          | **,**로   |         |                                   |
|          | 구        |         |                                   |
|          | 분되어진  |         |                                   |
|          | 문자      |         |                                   |
|          | 열입니다. |         |                                   |
+----------+-----------+---------+-----------------------------------+
| 사용예   | DxCh      |         |                                   |
|          | art.numbe |         |                                   |
|          | rFormat({ |         |                                   |
|          |           |         |                                   |
|          | object:   |         |                                   |
|          | this,     |         |                                   |
|          |           |         |                                   |
|          | number:   |         |                                   |
|          | Strin     |         |                                   |
|          | g(value.t |         |                                   |
|          | oFixed(de |         |                                   |
|          | cimals)), |         |                                   |
|          |           |         |                                   |
|          | unitspre: |         |                                   |
|          | unitsPre, |         |                                   |
|          |           |         |                                   |
|          | u         |         |                                   |
|          | nitspost: |         |                                   |
|          | u         |         |                                   |
|          | nitsPost, |         |                                   |
|          |           |         |                                   |
|          | point:    |         |                                   |
|          | point,    |         |                                   |
|          |           |         |                                   |
|          | thousand: |         |                                   |
|          | thousand  |         |                                   |
|          |           |         |                                   |
|          | })        |         |                                   |
+----------+-----------+---------+-----------------------------------+

### REG.clear

  ----------------------------------------------------------------------------------
  파라미터   args                               Object   함수의 매개변수는 객체일
                                                         수도 있고, 문자열일 수도
                                                         있으며, 캔버스 객체일 수도
                                                         있습니다.
  ---------- ---------------------------------- -------- ---------------------------
             args                               String   

  리턴값     없음                                        

  상세 설명  DxChart.REG 저장된 객체에서                 
             객체들을 제거하는데 사용되며,               
             필요에 따라 특정 캔버스에 속한              
             객체들만 제거하거나 전체 REG를              
             초기화할 수 있습니다.                       

  사용예     DxChart.REG.clear() ,                       
             DxChart.REG.clear('this.canvas')            
  ----------------------------------------------------------------------------------

### setToolTipBackColor

  ----------------------------------------------------------------------------------
  파라미터   obj                                Object   DxChart 객체
  ---------- ---------------------------------- -------- ---------------------------
             arr                                Arrary   (옵션)배경색을 지정하는
                                                         배열로, 각 데이터셋에 대한
                                                         색상 값을 포함합니다. 이
                                                         배열은 데이터셋의 인덱스에
                                                         해당하는 요소를 포함하고
                                                         있어야 합니다. 만약 해당
                                                         인덱스에 대한 값이 없다면
                                                         기본적으로 데이터셋의
                                                         색상이 사용됩니다.

  리턴값     없음                                        

  상세 설명  툴팁의 배경 색상을 설정하는 데              
             사용됩니다. 매개변수를 받아와서             
             툴팁 및 포인터의 배경 색상을                
             설정합니다.                                 

  사용예     DxChart.setToolTipBackColor(obj)            
  ----------------------------------------------------------------------------------

## Effect 종류

차트를 그릴 때 애니메이션의 종류를 지정합니다.

### draw

애니메이션을 하지 않고, 차트를 그립니다.

### drawAni

애니메이션을 지정합니다. 첫번째 인수는 애니메이션의 종류를 나타내고
두번째 인수 이후는 해당 애니메이션의 인수를 지정합니다.

사용 예) wave 애니메이션 : chart.drawAni("wave");

### wave

왼쪽에서 오른쪽으로 아래쪽에서 위쪽으로 애니메이션이 동시에 일어납니다.

기본적인 애니메이션 초당 Frame은 90입니다.

### grow

아래쪽 또는 위쪽으로 애니메이션이 일어납니다.

기본적인 애니메이션 초당 Frame은 60입니다.

### trace

왼쪽에서 오른쪽으로 애니메이션이 일어납니다.

적용 대상 차트 : line , scatter , rader

### unfold (toBottom)

아래쪽으로 애니메이션이 일어납니다.

적용 대상 차트 : line

### Unfoldfromcentertrace (fromCenter)

![라인, 영수증, 스크린샷, 텍스트이(가) 표시된 사진 자동 생성된
설명](media/image48.png){width="2.8661417322834644in"
height="0.8944455380577427in"}![라인, 그래프, 스크린샷이(가) 표시된 사진
자동 생성된 설명](media/image49.png){width="2.8661417322834644in"
height="0.9338735783027121in"}

차트의 중앙에서부터 원래의 값으로 이동하는 애니메이션이 일어납니다.

적용 대상 차트 : line

### foldtocenter (toCenter)

![라인, 그래프, 스크린샷이(가) 표시된 사진 자동 생성된
설명](media/image49.png){width="2.8661417322834644in"
height="0.9338735783027121in"}![라인, 영수증, 스크린샷, 텍스트이(가)
표시된 사진 자동 생성된
설명](media/image48.png){width="2.8661417322834644in"
height="0.8944455380577427in"}

차트의 원래의 값에서부터 중앙으로 이동하는 애니메이션이 일어납니다.

적용 대상 차트 : line

### roundrobin

시계방향으로 돌아가면서 차트를 그리는 애니메이션이 일어납니다.

-   roundRobinSequential 과의 차이점

    roundRobin은 각각의 값이 조금씩 늘어나면서 파이의 각도가 점점
    늘어나지만, roundRobinSequential은 하나의 값이 점점 늘어나면서
    하나의 값이 전부 그려지면 다음 값이 늘어나면서 파이의 각도를
    증가합니다.

    적용 대상 차트 : pie , pieSegment, rose

### roundRobinSequential 

시계방향으로 돌아가면서 차트를 그리는 애니메이션이 일어납니다.

-   roundRobin 과의 차이점

    roundRobin은 각각의 값이 조금씩 늘어나면서 파이의 각도가 점점
    늘어나지만, roundRobinSequential은 하나의 값이 점점 늘어나면서
    하나의 값이 전부 그려지면 다음 값이 늘어나면서 파이의 각도를
    증가합니다.

    적용 대상 차트 : pie , pieSegment, rose

### implode

파이의 각 부분이 바깥으로부터 중심으로 모여 드는 애니메이션이
일어납니다.

적용 대상 차트 : pie , pieSegment, rose

### explode 

파이의 각 부분이 중심으로부터 바깥으로 퍼져 나가는 애니메이션이
일어납니다.

적용 대상 차트 : pie , pieSegment, rose , scatter

## 차트별 메소드

### get

  -----------------------------------------------------------------------------
  파라미터   name                     String     차트에서 정의된 가져올 속성
                                                 명입니다.
  ---------- ------------------------ ---------- ------------------------------
  리턴 값    String                   차트의     
                                      특정       
                                      속성에     
                                      대한 값을  
                                      리턴       
                                      합니다..   

  상세 설명  Properties에 있는 값을              
             가져온다. Properties는              
             JSON의 Option에 있는                
             Property로 구성되어                 
             있습니다.                           

  사용 예    var sMarginLeft =                   
             bar.get("marginLeft");              
  -----------------------------------------------------------------------------

### set

  ------------------------------------------------------------------------------
  파라미터   name                        String    차트에서 정의된 가져올 속성
                                                   명입니다.
  ---------- --------------------------- --------- -----------------------------
             value                       Variant   세팅할 속성값입니다.

  리턴 값                                없음      

  상세 설명  Properties에 값을                     
             세팅합니다. Properties는              
             JSON의 Option에 있는                  
             Property로 구성되어                   
             있습니다.                             

  사용예     bar.set("marginLeft",30);             
  ------------------------------------------------------------------------------

### getValue

+----------+-----------+---------+-----------------------------------+
| 파라미터 | event     | Object  | 전달받은 Event Object입니다.      |
+==========+===========+=========+===================================+
| 리턴 값  | Number    | Even    |                                   |
|          |           | t로부터 |                                   |
|          |           | 취득한  |                                   |
|          |           | Value   |                                   |
|          |           | 정보    |                                   |
|          |           | 입니다. |                                   |
+----------+-----------+---------+-----------------------------------+
| 상세     | event로   |         |                                   |
| 설명     | 부터 값을 |         |                                   |
|          | 취        |         |                                   |
|          | 득합니다. |         |                                   |
+----------+-----------+---------+-----------------------------------+
| 사용 예  | this.     |         |                                   |
|          | c         |         |                                   |
|          | hanging\_ |         |                                   |
|          | mousemove |         |                                   |
|          | = fu      |         |                                   |
|          | nction(e) |         |                                   |
|          |           |         |                                   |
|          | {         |         |                                   |
|          |           |         |                                   |
|          | #         |         |                                   |
|          | var value |         |                                   |
|          |           |         |                                   |
|          | this.get  |         |                                   |
|          | Value(e); |         |                                   |
|          |           |         |                                   |
|          | ...       |         |                                   |
|          |           |         |                                   |
|          | }         |         |                                   |
+----------+-----------+---------+-----------------------------------+

### on

  ---------------------------------------------------------------------------
  파라미터   event                   String    차트의 Event를 생성할 때
                                               생성할 이벤트 명입니다.
                                               이벤트명은 지정된 값만 사용
                                               가능합니다. 예): onenddraw
  ---------- ----------------------- --------- ------------------------------
             function                Object    차트의 Event를 생성할 때
                                               이벤트 발생시 수행되는
                                               함수입니다.

  리턴 값                            없음      

  상세 설명  차트의 이벤트 핸들러를            
             정의한다.(onenddraw 등)           

  사용 예    pie.on(\"onenddraw\",             
             function() { ... });              
  ---------------------------------------------------------------------------

### getShape

+----------+-----------+---------+-----------------------------------+
| 파라미터 | event     | Object  | 전달받은 Event Object입니다.      |
+==========+===========+=========+===================================+
| 리턴 값  | Object    | 해당    |                                   |
|          |           | Shape의 |                                   |
|          |           | 정보 오 |                                   |
|          |           | 브젝트  |                                   |
|          |           | (JSON)  |                                   |
|          |           |         |                                   |
|          |           | ## ---- |                                   |
|          |           | --- {#s |                                   |
|          |           | ection} |                                   |
|          |           |         |                                   |
|          |           | ##      |                                   |
|          |           | ------- |                                   |
|          |           |         |                                   |
|          |           |   -     |                                   |
|          |           | ------- |                                   |
|          |           |         |                                   |
|          |           | obje ct |                                   |
|          |           |         |                                   |
|          |           |         |                                   |
|          |           | 차트 오 |                                   |
|          |           |         |                                   |
|          |           |  브젝트 |                                   |
|          |           |   -     |                                   |
|          |           | ------- |                                   |
|          |           |         |                                   |
|          |           | -----   |                                   |
|          |           |         |                                   |
|          |           | ##      |                                   |
|          |           | --- --- |                                   |
|          |           |         |                                   |
|          |           |   --    |                                   |
|          |           | ------- |                                   |
|          |           |       x |                                   |
|          |           |         |                                   |
|          |           |         |                                   |
|          |           | x좌표값 |                                   |
|          |           |         |                                   |
|          |           |       y |                                   |
|          |           |         |                                   |
|          |           |         |                                   |
|          |           | y좌표값 |                                   |
|          |           |         |                                   |
|          |           |   d     |                                   |
|          |           | at aset |                                   |
|          |           |         |                                   |
|          |           |   d     |                                   |
|          |           | atase t |                                   |
|          |           |         |                                   |
|          |           |   index |                                   |
|          |           |         |                                   |
|          |           |         |                                   |
|          |           |  inde x |                                   |
|          |           |         |                                   |
|          |           |         |                                   |
|          |           | point의 |                                   |
|          |           |         |                                   |
|          |           |   index |                                   |
|          |           |         |                                   |
|          |           |         |                                   |
|          |           |    sequ |                                   |
|          |           |         |                                   |
|          |           | entialI |                                   |
|          |           |         |                                   |
|          |           |    ndex |                                   |
|          |           |         |                                   |
|          |           | Point의 |                                   |
|          |           |         |                                   |
|          |           |   s     |                                   |
|          |           | equenti |                                   |
|          |           |         |                                   |
|          |           | alIndex |                                   |
|          |           |         |                                   |
|          |           |   T     |                                   |
|          |           | o oltip |                                   |
|          |           |         |                                   |
|          |           |   T     |                                   |
|          |           | oolt ip |                                   |
|          |           |         |                                   |
|          |           |    text |                                   |
|          |           |         |                                   |
|          |           |         |                                   |
|          |           |   width |                                   |
|          |           |         |                                   |
|          |           |   S     |                                   |
|          |           | ha pe의 |                                   |
|          |           |      폭 |                                   |
|          |           |         |                                   |
|          |           |         |                                   |
|          |           | he ight |                                   |
|          |           |         |                                   |
|          |           |   S     |                                   |
|          |           | hape 의 |                                   |
|          |           |         |                                   |
|          |           |    높이 |                                   |
|          |           |   --    |                                   |
|          |           | ------- |                                   |
|          |           |         |                                   |
|          |           | ##      |                                   |
|          |           | ------- |                                   |
|          |           |         |                                   |
|          |           | ##      |                                   |
|          |           | ------- |                                   |
+----------+-----------+---------+-----------------------------------+
| 상세     | 해당하는  |         |                                   |
| 설명     | 이벤트가  |         |                                   |
|          | 발생한 오 |         |                                   |
|          | 브젝트를  |         |                                   |
|          | 가        |         |                                   |
|          | 져옵니다. |         |                                   |
|          |           |         |                                   |
|          | oncli     |         |                                   |
|          | k이벤트나 |         |                                   |
|          | mous      |         |                                   |
|          | eup이벤트 |         |                                   |
|          | 등에서    |         |                                   |
|          | 전달받은  |         |                                   |
|          | 이벤      |         |                                   |
|          | 트정보를  |         |                                   |
|          | 사        |         |                                   |
|          | 용합니다. |         |                                   |
+----------+-----------+---------+-----------------------------------+
| 사용 예  | var obj   |         |                                   |
|          | ShapeInfo |         |                                   |
|          | = pie.ge  |         |                                   |
|          | tShape(e) |         |                                   |
|          |           |         |                                   |
|          | var nX =  |         |                                   |
|          | objSha    |         |                                   |
|          | peInfo.x; |         |                                   |
|          |           |         |                                   |
|          | var nY =  |         |                                   |
|          | objSha    |         |                                   |
|          | peInfo.y; |         |                                   |
|          |           |         |                                   |
|          | var       |         |                                   |
|          | nValue =  |         |                                   |
|          | thi       |         |                                   |
|          | s.data(ob |         |                                   |
|          | jShapeInf |         |                                   |
|          | o.dataset |         |                                   |
|          | ,o        |         |                                   |
|          | bjShapeIn |         |                                   |
|          | fo.index) |         |                                   |
+----------+-----------+---------+-----------------------------------+

### getShapeByX

+----------+-----------+---------+-----------------------------------+
| 파라미터 | event     | Object  | 전달받은 Event Object입니다.      |
+==========+===========+=========+===================================+
| 리턴 값  | Object    | 해당    |                                   |
|          |           | Shape의 |                                   |
|          |           | 정보 오 |                                   |
|          |           | 브젝트  |                                   |
|          |           | (JSON)  |                                   |
|          |           |         |                                   |
|          |           | ##      |                                   |
|          |           | ------- |                                   |
|          |           |         |                                   |
|          |           | ##      |                                   |
|          |           | ------- |                                   |
|          |           |         |                                   |
|          |           |   -     |                                   |
|          |           | ------- |                                   |
|          |           |         |                                   |
|          |           | obje ct |                                   |
|          |           |         |                                   |
|          |           |         |                                   |
|          |           | 차트 오 |                                   |
|          |           |         |                                   |
|          |           |  브젝트 |                                   |
|          |           |   -     |                                   |
|          |           | ------- |                                   |
|          |           |         |                                   |
|          |           | -----   |                                   |
|          |           |         |                                   |
|          |           | ##      |                                   |
|          |           | --- --- |                                   |
|          |           |         |                                   |
|          |           |   --    |                                   |
|          |           | ------- |                                   |
|          |           |       x |                                   |
|          |           |         |                                   |
|          |           |         |                                   |
|          |           | x좌표값 |                                   |
|          |           |         |                                   |
|          |           |       y |                                   |
|          |           |         |                                   |
|          |           |         |                                   |
|          |           | y좌표값 |                                   |
|          |           |         |                                   |
|          |           |   d     |                                   |
|          |           | at aset |                                   |
|          |           |         |                                   |
|          |           |   d     |                                   |
|          |           | atase t |                                   |
|          |           |         |                                   |
|          |           |   index |                                   |
|          |           |         |                                   |
|          |           |         |                                   |
|          |           |  inde x |                                   |
|          |           |         |                                   |
|          |           |         |                                   |
|          |           | point의 |                                   |
|          |           |         |                                   |
|          |           |   index |                                   |
|          |           |         |                                   |
|          |           |         |                                   |
|          |           |    sequ |                                   |
|          |           |         |                                   |
|          |           | entialI |                                   |
|          |           |         |                                   |
|          |           |    ndex |                                   |
|          |           |         |                                   |
|          |           | Point의 |                                   |
|          |           |         |                                   |
|          |           |   s     |                                   |
|          |           | equenti |                                   |
|          |           |         |                                   |
|          |           | alIndex |                                   |
|          |           |         |                                   |
|          |           |   t     |                                   |
|          |           | o oltip |                                   |
|          |           |         |                                   |
|          |           |   T     |                                   |
|          |           | oolt ip |                                   |
|          |           |         |                                   |
|          |           |    text |                                   |
|          |           |         |                                   |
|          |           |         |                                   |
|          |           |   width |                                   |
|          |           |         |                                   |
|          |           |   S     |                                   |
|          |           | ha pe의 |                                   |
|          |           |      폭 |                                   |
|          |           |         |                                   |
|          |           |         |                                   |
|          |           | he ight |                                   |
|          |           |         |                                   |
|          |           |   S     |                                   |
|          |           | hape 의 |                                   |
|          |           |         |                                   |
|          |           |    높이 |                                   |
|          |           |   --    |                                   |
|          |           | ------- |                                   |
|          |           |         |                                   |
|          |           | ##      |                                   |
|          |           | ------- |                                   |
|          |           |         |                                   |
|          |           | ##      |                                   |
|          |           | ------- |                                   |
+----------+-----------+---------+-----------------------------------+
| 상세     | 해당하는  |         |                                   |
| 설명     | 이벤트가  |         |                                   |
|          | 발생한 오 |         |                                   |
|          | 브젝트를  |         |                                   |
|          | 가        |         |                                   |
|          | 져옵니다. |         |                                   |
|          |           |         |                                   |
|          | oncli     |         |                                   |
|          | k이벤트나 |         |                                   |
|          | mous      |         |                                   |
|          | eup이벤트 |         |                                   |
|          | 등에서    |         |                                   |
|          | 전달받은  |         |                                   |
|          | 이벤      |         |                                   |
|          | 트정보를  |         |                                   |
|          | 사        |         |                                   |
|          | 용합니다. |         |                                   |
|          |           |         |                                   |
|          | \* getSh  |         |                                   |
|          | ape()와의 |         |                                   |
|          | 차이점    |         |                                   |
|          |           |         |                                   |
|          | get       |         |                                   |
|          | Shape()는 |         |                                   |
|          | X좌표     |         |                                   |
|          | /Y좌표를  |         |                                   |
|          | 체크하여  |         |                                   |
|          | 해당      |         |                                   |
|          | Shape를   |         |                                   |
|          | 자        |         |                                   |
|          | 겨오지만, |         |                                   |
|          | getSha    |         |                                   |
|          | peByX()는 |         |                                   |
|          | X축의     |         |                                   |
|          | 정보만을  |         |                                   |
|          | 가지고    |         |                                   |
|          | Shape를   |         |                                   |
|          | 가        |         |                                   |
|          | 져옵니다. |         |                                   |
+----------+-----------+---------+-----------------------------------+
| 사용 예  | var obj   |         |                                   |
|          | ShapeInfo |         |                                   |
|          | =         |         |                                   |
|          | pie.getSh |         |                                   |
|          | apeByX(e) |         |                                   |
|          |           |         |                                   |
|          | var nX =  |         |                                   |
|          | objSha    |         |                                   |
|          | peInfo.x; |         |                                   |
|          |           |         |                                   |
|          | var nY =  |         |                                   |
|          | objSha    |         |                                   |
|          | peInfo.y; |         |                                   |
|          |           |         |                                   |
|          | var       |         |                                   |
|          | nValue =  |         |                                   |
|          | thi       |         |                                   |
|          | s.data(ob |         |                                   |
|          | jShapeInf |         |                                   |
|          | o.dataset |         |                                   |
|          | ,o        |         |                                   |
|          | bjShapeIn |         |                                   |
|          | fo.index) |         |                                   |
+----------+-----------+---------+-----------------------------------+

### getXCoord

+----------+-----------+---------+-----------------------------------+
| 파라미터 | value     | Number  | 구하고 싶은 value값               |
+==========+===========+=========+===================================+
| 리턴 값  | Number    | 값에 해 |                                   |
|          |           | 당하는  |                                   |
|          |           | X좌표의 |                                   |
|          |           | 값(좌   |                                   |
|          |           | 로부터  |                                   |
|          |           | 0이     |                                   |
|          |           | 시작)   |                                   |
+----------+-----------+---------+-----------------------------------+
| 상세     | 주어진    |         |                                   |
| 설명     | 값에      |         |                                   |
|          | 해당하는  |         |                                   |
|          | X좌표의   |         |                                   |
|          | 위치 값을 |         |                                   |
|          | 구합니다. |         |                                   |
|          |           |         |                                   |
|          | 범위를    |         |                                   |
|          | 넘어가는  |         |                                   |
|          | 경우는    |         |                                   |
|          | null을 반 |         |                                   |
|          | 환합니다. |         |                                   |
+----------+-----------+---------+-----------------------------------+
| 사용 예  | hp        |         |                                   |
|          | .drawAni( |         |                                   |
|          | \"grow\", |         |                                   |
|          | null, f   |         |                                   |
|          | unction() |         |                                   |
|          | {         |         |                                   |
|          |           |         |                                   |
|          | var x =   |         |                                   |
|          | hp.getX   |         |                                   |
|          | Coord(hp. |         |                                   |
|          | value+1); |         |                                   |
|          |           |         |                                   |
|          | var rect2 |         |                                   |
|          | = new     |         |                                   |
|          | DxCh      |         |                                   |
|          | artRect({ |         |                                   |
|          |           |         |                                   |
|          | id: cvs,  |         |                                   |
|          |           |         |                                   |
|          | elem :    |         |                                   |
|          | canvas,   |         |                                   |
|          |           |         |                                   |
|          | x: x,     |         |                                   |
|          |           |         |                                   |
|          | y: hp.ma  |         |                                   |
|          | rginTop + |         |                                   |
|          | 5,        |         |                                   |
|          |           |         |                                   |
|          | width: 6, |         |                                   |
|          |           |         |                                   |
|          | height:   |         |                                   |
|          | hp        |         |                                   |
|          | .height - |         |                                   |
|          | 10,       |         |                                   |
|          |           |         |                                   |
|          | options:  |         |                                   |
|          | {         |         |                                   |
|          |           |         |                                   |
|          | co        |         |                                   |
|          | lorsFill: |         |                                   |
|          | \'#       |         |                                   |
|          | FF6A8E\', |         |                                   |
|          |           |         |                                   |
|          | highlig   |         |                                   |
|          | htStroke: |         |                                   |
|          | \'        |         |                                   |
|          | rgba(0,0, |         |                                   |
|          | 0,0.5)\', |         |                                   |
|          |           |         |                                   |
|          | highl     |         |                                   |
|          | ightFill: |         |                                   |
|          | \'        |         |                                   |
|          | rgba(0,0, |         |                                   |
|          | 0,0.5)\', |         |                                   |
|          |           |         |                                   |
|          | }         |         |                                   |
|          |           |         |                                   |
|          | }         |         |                                   |
|          | ).draw(); |         |                                   |
|          |           |         |                                   |
|          | });       |         |                                   |
+----------+-----------+---------+-----------------------------------+

### getYCoord

+----------+-----------+---------+-----------------------------------+
| 파라미터 | value     | Number  | 구하고 싶은 value값               |
+==========+===========+=========+===================================+
| 리턴 값  | Number    | 값에 해 |                                   |
|          |           | 당하는  |                                   |
|          |           | Y좌표의 |                                   |
|          |           | 값(위   |                                   |
|          |           | 로부터  |                                   |
|          |           | 0이     |                                   |
|          |           | 시작)   |                                   |
+----------+-----------+---------+-----------------------------------+
| 상세     | 주어진    |         |                                   |
| 설명     | 값에      |         |                                   |
|          | 해당하는  |         |                                   |
|          | Y좌표의   |         |                                   |
|          | 위치 값을 |         |                                   |
|          | 구합니다. |         |                                   |
|          |           |         |                                   |
|          | 범위를    |         |                                   |
|          | 넘어가는  |         |                                   |
|          | 경우는    |         |                                   |
|          | null을 반 |         |                                   |
|          | 환합니다. |         |                                   |
+----------+-----------+---------+-----------------------------------+

사용예 \| thesholdY \| \| \| \| \| = \| \| \| \| \| l \| \| \| \| \|
ine.getYC \| \| \| \| \| oord(52); \| \| \|
+----------+-----------+---------+-----------------------------------+

### getAngle

  ---------------------------------------------------------------------------
  파라미터   numitems            Number       총 데이터 항목의 수
  ---------- ------------------- ------------ -------------------------------
             Index               Number       데이터 항목의 특정 인덱스 값

  리턴 값    angle               데이터항목   
                                 수가         
                                 인덱스로     
                                 계산한 각도  
                                 값           

  상세 설명  각 항목에 대한                   
             각도를 계산하는 데               
             사용될 수 있으며,                
             일반적으로 차트나                
             그래픽 요소의                    
             배치나 시각적인                  
             표현을 위해 사용될               
             수 있습니다.                     

  사용예     var angleRadar =                 
             obj.getAngle(8,3)                
  ---------------------------------------------------------------------------

### explode

  ---------------------------------------------------------------------------
  파라미터   index                     확산시킬 인덱스
  ---------- ------------------------- --------------------------------------
             size                      확산 시킬 크기

  리턴 값    angle                     데이터항목 수가 인덱스로 계산한 각도
                                       값

  상세 설명  pie, segement 차트 등     
             원형 차트를 시각적으로    
             확산 시키는 메서드        
             입니다. 일반적으로 해당   
             차트의 배치나 시각적인    
             표현을 위해 사용될 수     
             있습니다.                 

  사용예     var angleRadar =          
             obj.explode(index,size)   
  ---------------------------------------------------------------------------

### closest

+----------+-----------+---------+-----------------------------------+
| 파라미터 | opt       | Object  | coords, mousex, tolerance로       |
|          |           |         | 구성된 객체입니다.                |
|          |           |         |                                   |
|          |           |         | -   coords: 점의 좌표를 포함하는  |
|          |           |         |     배열입니다.                   |
|          |           |         |                                   |
|          |           |         | -   mousex: 마우스 X 좌표입니다.  |
|          |           |         |                                   |
|          |           |         | -   tolerance: 허용되는 픽셀      |
|          |           |         |     범위입니다. 기본값은          |
|          |           |         |     10입니다.                     |
+==========+===========+=========+===================================+
| 리턴 값  | Object    | 가장    |                                   |
|          |           | 가까운  |                                   |
|          |           | 점의    |                                   |
|          |           | 정보를  |                                   |
|          |           | 담은    |                                   |
|          |           | 객체를  |                                   |
|          |           | 반환    |                                   |
|          |           | 합니다. |                                   |
|          |           | 이      |                                   |
|          |           | 객체는  |                                   |
|          |           | d       |                                   |
|          |           | ataset, |                                   |
|          |           | index,  |                                   |
|          |           | dis     |                                   |
|          |           | tance로 |                                   |
|          |           | 구      |                                   |
|          |           | 성되어  |                                   |
|          |           | 있      |                                   |
|          |           | 습니다. |                                   |
+----------+-----------+---------+-----------------------------------+
| 상세     | 주어진    |         |                                   |
| 설명     | 마우스 X  |         |                                   |
|          | 좌표에    |         |                                   |
|          | 가장      |         |                                   |
|          | 가까운    |         |                                   |
|          | 점을 찾는 |         |                                   |
|          | 함        |         |                                   |
|          | 수입니다. |         |                                   |
|          | 이 함수는 |         |                                   |
|          | 일련의    |         |                                   |
|          | 점들의    |         |                                   |
|          | 좌표와    |         |                                   |
|          | 마우스    |         |                                   |
|          | 이벤트    |         |                                   |
|          | 객체,     |         |                                   |
|          | 그리고    |         |                                   |
|          | 허용      |         |                                   |
|          | 오차를    |         |                                   |
|          | 인자로    |         |                                   |
|          | 받아와서  |         |                                   |
|          | 가장      |         |                                   |
|          | 가까운    |         |                                   |
|          | 점을      |         |                                   |
|          | 찾습니다. |         |                                   |
+----------+-----------+---------+-----------------------------------+
| 사용예   | var       |         |                                   |
|          | indexes = |         |                                   |
|          | line.cl   |         |                                   |
|          | osest({ev |         |                                   |
|          | ent:e,xon |         |                                   |
|          | ly:true,t |         |                                   |
|          | olerance: |         |                                   |
|          | 50});     |         |                                   |
+----------+-----------+---------+-----------------------------------+

### growPoint

+----------+-----------+---------+-----------------------------------+
| 파라미터 | dataset   | 옵션    | 점의 데이터셋을 나타냅니다.       |
|          |           |         | 기본값은 0입니다.                 |
+==========+===========+=========+===================================+
|          | Index     | Index   | 점의 인덱스를 나타냅니다.         |
+----------+-----------+---------+-----------------------------------+
|          | value     | Value   | 점의 크기를 성장시킬 새로운 값을  |
|          |           |         | 나타냅니다.                       |
+----------+-----------+---------+-----------------------------------+
|          | frames    | 옵션    | 애니메이션에 사용할 프레임        |
|          |           |         | 수입니다. 기본값은 15입니다.      |
+----------+-----------+---------+-----------------------------------+
| 리턴 값  |           |         |                                   |
+----------+-----------+---------+-----------------------------------+
| 상세     | 점을 새   |         |                                   |
| 설명     | 위치로 성 |         |                                   |
|          | 장시키는  |         |                                   |
|          | 애니      |         |                                   |
|          | 메이션을  |         |                                   |
|          | 처        |         |                                   |
|          | 리합니다. |         |                                   |
|          | 주어진    |         |                                   |
|          | 인덱스와  |         |                                   |
|          | 새 값,    |         |                                   |
|          | 그리고 선 |         |                                   |
|          | 택적으로  |         |                                   |
|          | 데        |         |                                   |
|          | 이터셋을  |         |                                   |
|          | 받아서    |         |                                   |
|          | 점의      |         |                                   |
|          | 크기를    |         |                                   |
|          | 성장      |         |                                   |
|          | 시킵니다. |         |                                   |
+----------+-----------+---------+-----------------------------------+
| 사용예   | line.     |         |                                   |
|          | growPoint |         |                                   |
|          |           |         |                                   |
|          | ({        |         |                                   |
|          |           |         |                                   |
|          | index:    |         |                                   |
|          | index     |         |                                   |
|          | es.index, |         |                                   |
|          |           |         |                                   |
|          | value:    |         |                                   |
|          | value,    |         |                                   |
|          |           |         |                                   |
|          | dataset:  |         |                                   |
|          | 0, // O   |         |                                   |
|          | ptional - |         |                                   |
|          | defaults  |         |                                   |
|          | to 0      |         |                                   |
|          |           |         |                                   |
|          | frames:   |         |                                   |
|          | 15 // O   |         |                                   |
|          | ptional - |         |                                   |
|          | defaults  |         |                                   |
|          | to 15     |         |                                   |
|          |           |         |                                   |
|          | });       |         |                                   |
+----------+-----------+---------+-----------------------------------+

### hide

  -----------------------------------------------------------------------------
  파라미터   \[index\]              Array(옵션)   Line Index의 배열. 파라미터
                                                  값을 넘기지 않을 시 모든 선이
                                                  숨김 처리됩니다.
  ---------- ---------------------- ------------- -----------------------------
  리턴 값    this                   함수는 this를 
                                    반환하여      
                                    체이닝을      
                                    가능하게      
                                    합니다        

  상세 설명  주어진 인덱스 또는                   
             배열에 따라 단일 또는                
             여러 선을 숨기는                     
             기능을 제공합니다.                   
             데이터 시각화에서 특정               
             선을 숨기거나 숨겨진                 
             선을 표시하는 데                     
             사용될 수 있습니다.                  

  사용예     Line.hide(\[1,3,5\])                 
  -----------------------------------------------------------------------------

### show

  -----------------------------------------------------------------------------
  파라미터   \[index\]              Array(옵션)   Line Index의 배열.
                                                  파라미터값을 넘기지 않을 시
                                                  모든 선이 보이게 됩니다.
  ---------- ---------------------- ------------- -----------------------------
  리턴값     this                   함수는        
                                    **this**를    
                                    반환하여      
                                    체이닝을      
                                    가능하게      
                                    합니다        

  상세 설명  주어진 인덱스 또는                   
             배열에 따라 단일 또는                
             여러 선을 표시하는                   
             기능을 제공합니다.                   
             데이터 시각화에서                    
             숨겨진 선을 표시하거나               
             특정 선을 강조하는 데                
             사용될 수 있습니다.                  

  사용예     Line.show(\[1,3,5\])                 
  -----------------------------------------------------------------------------

### hidden

  -----------------------------------------------------------------------------
  파라미터   index                 Number        확인할 선의 인덱스 값 입니다.
  ---------- --------------------- ------------- ------------------------------
  리턴값     Boolean               True 또는     
                                   False 값을    
                                   반환합니다.   

  상세 설명  주어진 선의 인덱스를                
             통해 해당 선이 숨겨져               
             있는지 여부를                       
             확인하는 데 사용될 수               
             있습니다. 데이터                    
             시각화에서 특정 선의                
             가시성을 확인하고                   
             필요한 경우 조건부로                
             다양한 작업을                       
             수행하는 데                         
             유용합니다.                         

  사용예     this.hidden(index);                 
  -----------------------------------------------------------------------------

### overChartArea

  -------------------------------------------------------------------------------
  파라미터   e                        Event         매개변수 이벤트
  ---------- ------------------------ ------------- -----------------------------
  리턴값     Boolean                  True 또는     
                                      False 값을    
                                      반환합니다.   

  상세 설명  주어진 이벤트(e)의                     
             좌표를 기반으로 차트                   
             영역 위에 커서가 있는지                
             여부를 판단합니다.                     
             주어진 이벤트의 마우스                 
             좌표를 추출하고, 해당                  
             좌표가 차트의 영역 안에                
             있는지를 확인하여 true                 
             또는 false 값을                        
             반환합니다.                            

  사용예     this.overChartArea(e);                 
  -------------------------------------------------------------------------------

### highlightDataset

  --------------------------------------------------------------------------------
  파라미터   dataset                          Number   데이터셋의 인덱스를
                                                       나타내며, 일반적으로 0부터
                                                       시작하여 데이터셋의 개수에
                                                       따라 증가하는 값을
                                                       가집니다.
  ---------- -------------------------------- -------- ---------------------------
  리턴값                                               

  상세 설명  차트에서 특정 데이터셋을                  
             강조하여 시각적으로 돋보이게              
             하는 데 사용될 수 있습니다.               
             데이터 시각화에서 특정                    
             데이터셋을 강조하여 사용자의              
             주의를 끌거나 중요한 정보를               
             강조하는 데 유용합니다.                   

  사용예     this.highlightDataset(dataset)            
  --------------------------------------------------------------------------------

### exec

  -----------------------------------------------------------------------------
  파라미터   func              Object             실행할 함수를 나타내는
                                                  매개변수입니다. 이 함수는
                                                  객체를 인자로 받을 수
                                                  있습니다.
  ---------- ----------------- ------------------ -----------------------------
  리턴값     this              현재               
                               객체(**this**)를   
                               반환하여 함수      
                               체이닝을 가능하게  
                               합니다.            

  상세 설명  다른 함수를                          
             실행할 때 현재                       
             객체를 해당 함수                     
             내에서 사용할 수                     
             있도록                               
             전달해줍니다.                        
             이것은 함수                          
             실행과 함께                          
             객체의 상태나                        
             속성을 변경하거나                    
             조작하는 데                          
             유용합니다. 또한                     
             함수 체이닝을                        
             통해 여러                            
             메서드를 연결하여                    
             사용할 수 있도록                     
             합니다.                              

  사용예     this.exec(func)                      
  -----------------------------------------------------------------------------

### responsive

+----------+-----------+---------+-----------------------------------+
| 파라미터 | conf      | Object  | 반응형 구성을 설정하는 데         |
|          |           |         | 사용되는 구성 객체입니다.         |
+==========+===========+=========+===================================+
| 리턴값   | this      | 현재 객 |                                   |
|          |           | 체(**th |                                   |
|          |           | is**)를 |                                   |
|          |           | 반      |                                   |
|          |           | 환하여  |                                   |
|          |           | 함수 체 |                                   |
|          |           | 이닝을  |                                   |
|          |           | 가      |                                   |
|          |           | 능하게  |                                   |
|          |           | 합니다  |                                   |
+----------+-----------+---------+-----------------------------------+
| 상세     | 차트에    |         |                                   |
| 설명     | 반응형    |         |                                   |
|          | 구성을    |         |                                   |
|          | 쉽게      |         |                                   |
|          | 추가할 수 |         |                                   |
|          | 있습니다. |         |                                   |
|          | 주로      |         |                                   |
|          | 차트의    |         |                                   |
|          | 전경 및   |         |                                   |
|          | 배경과    |         |                                   |
|          | 관련된    |         |                                   |
|          | 구성      |         |                                   |
|          | 요소에    |         |                                   |
|          | 대해      |         |                                   |
|          | 반응형    |         |                                   |
|          | 동작을    |         |                                   |
|          | 설정하는  |         |                                   |
|          | 데 사용될 |         |                                   |
|          | 수        |         |                                   |
|          | 있습니다. |         |                                   |
|          | 이를 통해 |         |                                   |
|          | 차트가    |         |                                   |
|          | 다양한    |         |                                   |
|          | 디바이스  |         |                                   |
|          | 크기와    |         |                                   |
|          | 환경에    |         |                                   |
|          | 대응할 수 |         |                                   |
|          | 있도록 할 |         |                                   |
|          | 수        |         |                                   |
|          | 있습니다. |         |                                   |
+----------+-----------+---------+-----------------------------------+
| 사용예   | wave.re   |         |                                   |
|          | sponsive: |         |                                   |
|          | (\[       |         |                                   |
|          |           |         |                                   |
|          | {         |         |                                   |
|          | maxWidth: |         |                                   |
|          | null,     |         |                                   |
|          | width:    |         |                                   |
|          | 700,      |         |                                   |
|          | height:   |         |                                   |
|          | 275,      |         |                                   |
|          | options:  |         |                                   |
|          | {t        |         |                                   |
|          | itleSize: |         |                                   |
|          | 18        |         |                                   |
|          | ,xaxisLab |         |                                   |
|          | elsAngle: |         |                                   |
|          | 0,        |         |                                   |
|          | textSize: |         |                                   |
|          | 14,x      |         |                                   |
|          | axisLabel |         |                                   |
|          | sOffsety: |         |                                   |
|          | 0,marg    |         |                                   |
|          | inBottom: |         |                                   |
|          | 5,mar     |         |                                   |
|          | ginInner: |         |                                   |
|          | 25}       |         |                                   |
|          |           |         |                                   |
|          | },        |         |                                   |
|          |           |         |                                   |
|          | \])       |         |                                   |
+----------+-----------+---------+-----------------------------------+

## 이벤트 종류

### onadjustbegin

이 이벤트는 조정(adjust)이 시작될 때 발생합니다.

callback함수 parameter :

  ----------------------------------
  obj 차트 object 입니다.\\
  Event 발생시 수행됩니다.\\
  on 메소드를 사용하여 수행합니다.
  ----------------------------------

------------------------------------------------------------------------

### onadjust

이 이벤트는 조정(adjust) 중에 (반복적으로) 발생합니다.

callback함수 parameter :

  ----------------------------------
  obj 차트 object 입니다.\\
  Event 발생시 수행됩니다.\\
  on 메소드를 사용하여 수행합니다.
  ----------------------------------

------------------------------------------------------------------------

### onadjustend

이 이벤트는 조정(adjust)이 끝나면 시작됩니다

callback함수 parameter :

  ----------------------------------
  obj 차트 object 입니다.\\
  Event 발생시 수행됩니다.\\
  on 메소드를 사용하여 수행합니다.
  ----------------------------------

------------------------------------------------------------------------

### onafterinteractivekey

이 이벤트는 대화형 키를 사용하는 경우 키와 차트가 강조표시된 직후에
발생합니다.

callback함수 parameter :

  ----------------------------------
  obj 차트 object 입니다.\\
  Event 발생시 수행됩니다.\\
  on 메소드를 사용하여 수행합니다.
  ----------------------------------

------------------------------------------------------------------------

### onannotatebegin

이 이벤트는 주석이 시작될 때 발생합니다

callback함수 parameter :

  ----------------------------------
  obj 차트 object입니다.\\
  Event 발생시 수행됩니다.\\
  on 메소드를 사용하여 수행합니다.
  ----------------------------------

------------------------------------------------------------------------

### onannotate

이 이벤트는 주석을 추가하는 동안 (반복적으로) 발생합니다.

callback함수 parameter :

  ----------------------------------
  obj 차트 object입니다.\\
  Event 발생시 수행됩니다.\\
  on 메소드를 사용하여 수행합니다.
  ----------------------------------

------------------------------------------------------------------------

### onannotateclear

이 이벤트는 DxChart.clearAnnotations()함수가 끝날 때 발생합니다

callback함수 parameter :

  ----------------------------------
  obj 차트 object입니다.\\
  Event 발생시 수행됩니다.\\
  on 메소드를 사용하여 수행합니다.
  ----------------------------------

------------------------------------------------------------------------

### onannotateend

이 이벤트는 주석이 끝나면 시작됩니다

callback함수 parameter :

  ----------------------------------
  obj 차트 object입니다.\\
  Event 발생시 수행됩니다.\\
  on 메소드를 사용하여 수행합니다.
  ----------------------------------

------------------------------------------------------------------------

### onbeforeclear

이 이벤트는 DxChart.clear()함수 시작 시 발생합니다.

callback함수 parameter :

  ----------------------------------
  obj 차트 object입니다.\\
  Event 발생시 수행됩니다.\\
  on 메소드를 사용하여 수행합니다.
  ----------------------------------

------------------------------------------------------------------------

### onbeforecontextmenu

이 이벤트는 컨텍스트 메뉴가 활성화되어 있어 나타나려고 할 때 발생합니다.

callback함수 parameter :

  ----------------------------------
  obj 차트 object입니다.\\
  Event 발생시 수행됩니다.\\
  on 메소드를 사용하여 수행합니다.
  ----------------------------------

------------------------------------------------------------------------

### onbeforedraw

이 이벤트는 draw()함수가 시작될 때 발생합니다.

callback함수 parameter :

  ----------------------------------
  obj 차트 object입니다.\\
  Event 발생시 수행됩니다.\\
  on 메소드를 사용하여 수행합니다.
  ----------------------------------

------------------------------------------------------------------------

### onbeforeinteractivekey

이 이벤트는 대화형 키를 사용하는 경우 키와 차트가 강조표시되기 직전에
발생합니다.

callback함수 parameter :

  ----------------------------------
  obj 차트 object입니다.\\
  Event 발생시 수행됩니다.\\
  on 메소드를 사용하여 수행합니다.
  ----------------------------------

------------------------------------------------------------------------

### onbeforetooltip

이 이벤트는 tooltip 표시 프로세스가 시작될 때 발생합니다.

callback함수 parameter :

  ----------------------------------
  obj 차트 object입니다.\\
  Event 발생시 수행됩니다.\\
  on 메소드를 사용하여 수행합니다.
  ----------------------------------

------------------------------------------------------------------------

### onclick

이 이벤트는 shape가 클릭될 때 발생합니다.

callback함수 parameter :

  ---------------------------------------------------------------------
  obj         차트 object입니다.\
              Event 발생시 수행됩니다.\
              on 메소드를 사용하여 수행합니다.
  ----------- ---------------------------------------------------------
  shape       선택영역의 object입니다.\
              Event 발생시 수행됩니다.\
              on 메소드를 사용하여 수행합니다.

  ---------------------------------------------------------------------

### onchange

callback함수 parameter :

  ----------------------------------
  obj 차트 object입니다.\\
  Event 발생시 수행됩니다.\\
  on 메소드를 사용하여 수행합니다.
  ----------------------------------

------------------------------------------------------------------------

### onchangebegin

callback함수 parameter :

  ----------------------------------
  obj 차트 object입니다.\\
  Event 발생시 수행됩니다.\\
  on 메소드를 사용하여 수행합니다.
  ----------------------------------

------------------------------------------------------------------------

### onclear

이 이벤트는 DxChart.clear()함수가 끝날 때 발생합니다

callback함수 parameter :

  ----------------------------------
  obj 차트 object입니다.\\
  Event 발생시 수행됩니다.\\
  on 메소드를 사용하여 수행합니다.
  ----------------------------------

------------------------------------------------------------------------

### oncontextmenu

이 이벤트는 컨텍스트 메뉴가 활성화되어 표시될 때 발생합니다.

callback함수 parameter :

  ----------------------------------
  obj 차트 object입니다.\\
  Event 발생시 수행됩니다.\\
  on 메소드를 사용하여 수행합니다.
  ----------------------------------

------------------------------------------------------------------------

### onenddraw

이 이벤트는 함수가 끝날 때 발생합니다

callback함수 parameter :

  ----------------------------------
  obj 차트 object입니다.\\
  Event 발생시 수행됩니다.\\
  on 메소드를 사용하여 수행합니다.
  ----------------------------------

------------------------------------------------------------------------

### onfirstdraw

이 이벤트는 draw()함수가 끝날 때 발생하지만, 함수가 처음 호출될 때만
발생합니다

callback함수 parameter :

  ----------------------------------
  obj 차트 object입니다.\\
  Event 발생시 수행됩니다.\\
  on 메소드를 사용하여 수행합니다.
  ----------------------------------

------------------------------------------------------------------------

### onkeyclick

이 이벤트는 키를 클릭할 때 발생합니다. 그러나 대화형 키를 사용할 필요는
없습니다.

callback함수 parameter :

  ----------------------------------
  obj 차트 object입니다.\\
  Event 발생시 수행됩니다.\\
  on 메소드를 사용하여 수행합니다.
  ----------------------------------

------------------------------------------------------------------------

### onmouseout

이 이벤트는 이전에 마우스를 올려놓은 차트의 막대에서 마우스를 멀리
이동할 때만 실행됩니다.

callback함수 parameter :

  ---------------------------------------------------------------------
  obj         차트 object입니다.\
              Event 발생시 수행됩니다.\
              on 메소드를 사용하여 수행합니다.
  ----------- ---------------------------------------------------------
  event       event 정보입니다.

  ---------------------------------------------------------------------

### ontooltip

이 이벤트는 tooltip이 표시된 후에 시작됩니다.

callback함수 parameter :

  ----------------------------------
  obj 차트 object입니다.\\
  Event 발생시 수행됩니다.\\
  on 메소드를 사용하여 수행합니다.
  ----------------------------------

------------------------------------------------------------------------

# **차트 종류**

## 막대차트(bar)

막대 그래프는 여러 항목간 값의 차이를 강조하거나 값의 전반적인 분포를
시각화 할 때 사용하는 차트입니다.

또한 막대 차트는 가로축으로 표시될 항목의 개수가 최대 10개 이하일 경우에
사용하는 것이 좋습니다.

![](media/image51.png){width="5.141732283464567in"
height="3.214466316710411in"}

## 라인차트(line)

선 그래프는 시간 경과에 따른 연속형 변수의 변동을 보여줍니다. 선
그래프를 선 차트, 추세도, 런 차트 또는 "시계열도"라고도 합니다.

![스크린샷, 라인, 다채로움이(가) 표시된 사진 자동 생성된
설명](media/image52.png){width="5.141732283464567in"
height="3.2065201224846893in"}

## activity 차트(activity)

시간에 따라 다양한 활동의 진행 상태를 시각화 하는 차트입니다. 시간 축에
따라 활동의 시작, 종료, 지속 시간 등을 나타내어 일정 관리나 프로세스
분석에 활용됩니다

![원, 다채로움, 그래픽, 예술이(가) 표시된 사진 자동 생성된
설명](media/image53.png){width="4.57583552055993in"
height="2.8666666666666667in"}

## 양극성 차트(bipolar)

![건물, 사각형, 대칭, 직사각형이(가) 표시된 사진 자동 생성된
설명](media/image54.png){width="5.141732283464567in"
height="3.220472440944882in"}양극성 차트는 다양한 값의 소비나 증감을
시각적으로 표현하는 데 사용됩니다. 예를 들어, 전력 소비량, 재고량, 익과
지출의 차이 등을 양극성 차트로 표현하여 데이터의 추이나 변화를 쉽게
이해할 수 있습니다.

## 연료 차트(fuel)

어떤 값의 소비나 증감을 나타내기 위해 사용되는 차트입니다. 연료 탱크의
남은 양이나 소비량 등을 시각적으로 표현하여 추이나 변화를 파악할 수
있습니다.

![스크린샷, 라인이(가) 표시된 사진 자동 생성된
설명](media/image55.png){width="5.141732283464567in"
height="3.2211898512685915in"}

## Funnel 차트(funnel)

![스크린샷, 다채로움, 그래픽, 디자인이(가) 표시된 사진 자동 생성된
설명](media/image56.png){width="5.141732283464567in"
height="3.220472440944882in"}다양한 단계의 데이터나 과정을 나타내기 위해
사용되는 차트입니다. 꼭지 부분이 좁고 점차 넓어지는 형태로 데이터의
유입과 이탈을 시각화 합니다.

## 간트 차트(gantt)

프로젝트 일정 관리에 사용되는 차트입니다. 각 작업의 시작일과 종료일을
시간의 흐름에 따라 막대로 표현하여 작업의 진행 상황과 일정을 파악할 수
있습니다

![스크린샷, 사각형, 라인, 직사각형이(가) 표시된 사진 자동 생성된
설명](media/image57.png){width="5.141732283464567in"
height="3.2211898512685915in"}

## 게이지 차트(gauge)

![](media/image58.png){width="5.141732283464567in"
height="3.220472440944882in"}단일 값의 상태를 나타내기 위해 사용되는
차트입니다. 일반적으로 원형 모양이며, 값의 범위에 따라 채워지는 영역을
표시하여 해당 값의 상태를 표현합니다

## 가로 막대 차트(hbar)

가로막대 그래프는 표시해야 할 항목의 개수가 많을 경우 사용하는
차트입니다. 주로 표시해야 할 항목이 많아 세로막대 그래프로는 간결한
데이터 시각화가 어려울 경우에 사용합니다.

![스크린샷, 다채로움, 라인, 직사각형이(가) 표시된 사진 자동 생성된
설명](media/image59.png){width="5.141732283464567in"
height="3.214466316710411in"}

## 히트맵 차트(heatmap)

![스크린샷, 사각형, 직사각형, 다채로움이(가) 표시된 사진 자동 생성된
설명](media/image60.png){width="5.141732283464567in"
height="3.220472440944882in"}히트맵 차트는 데이터를 시각적으로 표현하기
위한 도구로 사용되는 그래프 형식입니다. 주로 2차원 격자 형태로 표시되며,
격자의 각 셀은 값의 크기 또는 빈도를 나타냅니다.

## 말발굽 차트(horseshoe)

데이터의 상대적인 크기와 비율을 표현하는 데에 주로 사용됩니다. 전체
데이터 집합을 기준으로 각 데이터 요소의 비율을 나타내어, 섹션 간의
상대적인 비교를 시각적으로 보여줍니다.

![원, 예술, 흑백이(가) 표시된 사진 자동 생성된
설명](media/image61.png){width="5.141732283464567in"
height="3.2211898512685915in"}

## 수평 진행 차트(hprogress)

![다채로움, 스크린샷, 라인, 빛이(가) 표시된 사진 자동 생성된
설명](media/image62.png){width="5.141732283464567in"
height="3.220472440944882in"}선형적인 진행 상태를 수평 한 차트입니다.
단일 값의 진행 상태를 수평 바 형태로 표현하여 진척도를 시각화 합니다

## 미터 차트(meter)

특정 값의 크기나 비율을 표현하는 데 사용되는 차트입니다. 보통 바늘이나
지시자가 원형 미터 판 위를 움직이면서 값을 나타냅니다.

![원, 그래픽, 스크린샷, 천문학이(가) 표시된 사진 자동 생성된
설명](media/image63.png){width="5.141732283464567in"
height="3.2190649606299213in"}

## 계기판 차트(odo)

![원, 시계, 다채로움, 그래픽이(가) 표시된 사진 자동 생성된
설명](media/image64.png){width="5.141732283464567in"
height="3.220472440944882in"}주로 측정된 값을 표시하기 위해 사용되는
차트입니다. 바늘이 원 형태의 스케일 위를 움직이며 값을 나타내어
시각적으로 읽을 수 있습니다

## 조직구조 차트(org)

조직 구조를 시각화하기 위해 사용되는 차트입니다. 계층적인 관계를
보여주고, 조직의 부서나 직원 간의 관계를 표현합니다.

![다채로움, 사각형, 스크린샷, 직사각형이(가) 표시된 사진 자동 생성된
설명](media/image65.png){width="5.141732283464567in"
height="3.1622200349956255in"}

## 파이 차트(pie)

![](media/image66.png){width="5.141666666666667in"
height="2.3958333333333335in"}파이 차트는 하나의 원을 여러 영역 또는
조각으로 나눈 원 그래프입니다. 각 조각은 해당 변수에 대한 한 수준의
관측치 개수 또는 백분율을 나타냅니다. 파이 차트는 대개 기업에서
활용합니다. 고객 유형별 백분율, 다양한 제품별 매출 백분율, 다양한 국가별
수익 등을 보여주는 차트를 예로 들 수 있습니다.

## 피라미드 차트(pyramid)

계층적인 데이터를 비교할 때 사용되는 차트입니다. 위쪽에서 아래쪽으로
점차 크기가 작아지는 형태로 데이터를 나타내어 비율이나 비교 결과를
시각적으로 보여줍니다

![스크린샷, 다채로움, 디자인이(가) 표시된 사진 자동 생성된
설명](media/image67.png){width="4.542250656167979in" height="2.84375in"}

## 레이더 차트(radar)

![디자인, 종이접기이(가) 표시된 사진 중간 신뢰도로 자동 생성된
설명](media/image68.png){width="5.141732283464567in"
height="3.204724409448819in"}레이더 차트는 어떤 측정 목표에 대한
평가항목이 여러 개일 때 항목 수에 따라 원을 같은 간격으로 나누고,
중심으로부터 일정 간격으로 동심으로 척도를 재는 칸을 나누어 각
평가항목의 정량화된 점수에 따라 그 위치에 점을 찍고 평가항목간 점을 이어
선으로 만들어 항목 간 균형을 한눈에 볼 수 있도록 해주는 도표입니다.

## 로즈 차트(rose)

로즈 차트는 주로 원형 그래프 형태로 표현되는 차트입니다. 데이터의 분포와
패턴을 시각적으로 파악하는 데 사용됩니다. 또한 각 범주 간의 비교 뿐만
아니라 시계 방향으로 데이터의 변화나 패턴을 시각화 할 수 있는 유용한
도구입니다. 특히 주기성이나 계절성 데이터의 시각화에 자주 사용됩니다.
예를 들어, 연간 판매량의 계절성 변동이나 24시간 동안의 온도 변화 등을
로즈 차트로 표현할 수 있습니다.

![](media/image69.png){width="4.422475940507437in"
height="2.75797353455818in"}

## 산점도 차트(rscatter)

![원, 스크린샷, 디자인이(가) 표시된 사진 자동 생성된
설명](media/image70.png){width="4.6875in"
height="2.920138888888889in"}산점도 차트와 유사하지만, x축과 y축이
반대로 배치된 차트입니다. 두 변수 간의 상관 관계를 시각화 하는 데
사용됩니다

## 분산형 차트(scatter)

데이터의 두 변수 간의 관계를 시각적으로 나타내는 차트입니다. 점들이
평면상에 분포되어 데이터 간의 상관 관계를 확인할 수 있습니다

![스크린샷, 우주이(가) 표시된 사진 자동 생성된
설명](media/image71.png){width="5.141732283464567in"
height="3.2065201224846893in"}

## 세그먼트 차트(segment)

![원, 디자인이(가) 표시된 사진 자동 생성된
설명](media/image72.png){width="5.141732283464567in"
height="3.220472440944882in"}전체에 대한 부분의 비율을 나타내기 위해
사용되는 차트입니다. 원형 또는 반원형으로 구성되며, 각 부분의 크기에
따라 세그먼트의 영역이 구분됩니다.

## 반원형 진행 차트(semicircularprogress)

원의 반원 형태로 진행 상태를 시각화 하는 차트입니다. 진행 상태에 따라
반원이 채워지는 모습으로 진척도를 표현합니다

![그래픽, 원, 그래픽 디자인, 다채로움이(가) 표시된 사진 자동 생성된
설명](media/image73.png){width="5.141732283464567in"
height="3.2211898512685915in"}

## 온도계 차트(thermometer)

온도를 나타내기 위해 사용되는 차트입니다. 온도 스케일을 가진 원통
모양으로 표현되며, 현재 온도를 나타내는 지시자가 표시됩니다

![실린더, 일러스트레이션이(가) 표시된 사진 자동 생성된
설명](media/image74.png){width="2.3031496062992125in"
height="2.673228346456693in"}

## 트리 차트(tree)

트리 차트는 계층적인 데이터 구조를 시각화하기 위한 그래프 형식입니다.
주로 계층적인 구조를 가진 데이터를 나타내는데 사용되며, 부모-자식 관계를
가진 노드들로 구성됩니다.

![흑백, 흑백 사진, 모노크롬, 블랙이(가) 표시된 사진 자동 생성된
설명](media/image75.png){width="5.141732283464567in"
height="3.1622200349956255in"}

## 수직 진행 차트(vprogress)

![다채로움, 스크린샷, 직사각형, 사각형이(가) 표시된 사진 자동 생성된
설명](media/image76.png){width="1.8937007874015748in"
height="2.9645669291338583in"}선형적인 진행 상태를 시각화 하는 데
사용되는 차트입니다. 주로 단일 값의 진행 상태를 바 형태로 표현하여
진척도를 보여줍니다

## 워터폴 차트(waterfall)

수입과 지출, 변화 등 순차적으로 합산되는 데이터를 표현하는 차트입니다.
막대의 상승과 하강으로 수치의 증감과 합계를 보여줍니다.

![사각형, 다채로움, 스크린샷, 직사각형이(가) 표시된 사진 자동 생성된
설명](media/image77.png){width="5.141732283464567in"
height="3.2211898512685915in"}

# **관련사이트**

-   DXChart 홈페이지 : <http://chart.dxtobe.com>

-   DXChart 기술사이트 : <http://chart.dxtobe.com/chartTech/index.html>

-   DxTobe 홈페이지 : <http://www.dxtobe.com>

-   Nexacro 기술사이트 :
    <http://support.tobesoft.co.kr/Support/?menu=home>

# #Appendix1 . DXChart의 차트별 Effect함수의 종류

  <table align="center">
    <tr>
      <th>차트종류</th>
      <th>effect종류</th>
      <th>drawAni()의 첫번째 파라미터</th>
      <th>Default</th>
    </tr>
    <tr>
      <td>activity</td>
      <td>grow</td>
      <td>grow</td>
      <td>grow</td>
    </tr>
    <tr>
      <td>bar</td>
      <td>wave</td>
      <td>wave</td>
      <td>grow</td>
    </tr>
    <tr>
      <td></td>
      <td>grow</td>
      <td>grow</td>
      <td></td>
    </tr>
    <tr>
      <td>bipolar</td>
      <td>wave</td>
      <td>wave</td>
      <td>grow</td>
    </tr>
    <tr>
      <td></td>
      <td>grow</td>
      <td>grow</td>
      <td></td>
    </tr>
    <tr>
      <td>fuel</td>
      <td>grow</td>
      <td>grow</td>
      <td>grow</td>
    </tr>
    <tr>
      <td>funnel</td>
      <td>\-</td>
      <td>\-</td>
      <td>draw</td>
    </tr>
    <tr>
      <td>gauge</td>
      <td>grow</td>
      <td>grow</td>
      <td>grow</td>
    </tr>
    <tr>
      <td>gantt</td>
      <td>grow</td>
      <td>grow</td>
      <td>grow</td>
    </tr>
    <tr>
      <td>hbar</td>
      <td>grow</td>
      <td>grow</td>
      <td>grow</td>
    </tr>
    <tr>
      <td></td>
      <td>wave</td>
      <td>wave</td>
      <td></td>
    </tr>
    <tr>
      <td>horseshoe</td>
      <td>grow</td>
      <td>grow</td>
      <td>grow</td>
    </tr>
    <tr>
      <td>hprogress</td>
      <td>grow</td>
      <td>grow</td>
      <td>grow</td>
    </tr>
    <tr>
      <td>line</td>
      <td>unfold</td>
      <td>unfold (toBottom)</td>
      <td>wave(toTop)</td>
    </tr>
    <tr>
      <td></td>
      <td>Unfoldfromcentertrace</td>
      <td>Unfoldfromcentertrace (fromCenter)</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>foldtocenter</td>
      <td>foldtocenter (toCenter)</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>trace</td>
      <td>trace(toRight)</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>wave</td>
      <td>wave(toTop)</td>
      <td></td>
    </tr>
    <tr>
      <td>meter</td>
      <td>grow</td>
      <td>grow</td>
      <td>grow</td>
    </tr>
    <tr>
      <td>odo</td>
      <td>grow</td>
      <td>grow</td>
      <td>grow</td>
    </tr>
    <tr>
      <td>pie</td>
      <td>grow</td>
      <td>grow</td>
      <td>grow</td>
    </tr>
    <tr>
      <td></td>
      <td>explode</td>
      <td>explode</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>roundrobin</td>
      <td>roundRobin</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
  </tr>



## Appendix2 . DXChart의 권장사양

  <table align="center">
    <tr>
      <th>사용자 H/W</th>
      <th>운영환경(서버)</th>
      <th>운영환경(사용자)</th>
    </tr>
    <tr>
      <td>
        1. CPU: Intel Pentium4 or AMD x86 or AMDx86/64, 2 GHZ Processor<br>
        2. Memory: 4G 이상<br>
        3. HDD: 60GB 이상
      </td>
      <td>
        - 지원WAS: 무관<br>
        (WebLogic, Web Sphere, Jeus, Tomcat, JBoss, IIS 등)<br>
        - 지원플랫폼: 무관<br>
        (Windows, AIX, Red Hat Enterprise Linux 등)
      </td>
      <td>
        - OS: Windows XP 이상<br>
        Mac 등<br>
        - 브라우저:<br>
        파이어폭스 3.0 이상, 구글 크롬 6.0 이상, 사파리 3.2 이상
      </td>
    </tr>
  </table>

