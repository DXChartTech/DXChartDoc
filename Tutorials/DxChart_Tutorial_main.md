> <link rel="stylesheet" type="text/css" href="../index.css">


> **DXChart 개발자 튜토리얼**
>
> **(Nexacro용)**
---

**\[목 차\]**
각각의 목차의 ***대제목*** 을  클릭시 해당 페이지로 이동합니다

 [**1.** **DxChart 준비하기**](DxChart준비하기/DxChart_준비하기.md#dxchart-준비하기)
   
   - [Nexacro Project 만들기](DxChart준비하기/DxChart_준비하기.md#nexacro-project-만들기)
   - [차트모듈 설치하기](DxChart준비하기/DxChart_준비하기.md#차트모듈-설치하기)
   - [샘플화면 만들기](DxChart준비하기/DxChart_준비하기.md##샘플화면-만들기)
   - [차트함수 만들기](DxChart준비하기/DxChart_준비하기.md##차트함수-만들기)
   - [구성요소 용어 설명](DxChart준비하기/DxChart_준비하기.md##구성요소-용어-설명)
   - [데이터 형식](DxChart준비하기/DxChart_준비하기.md##데이터-형식)
     - [data Property](DxChart준비하기/DxChart_준비하기.md##data-property)
     - [binddataset Property](DxChart준비하기/DxChart_준비하기.md##binddataset-property)

 [**2.** **DxChart 속성**](DxChart속성/DxChart_속성.md#DxChart-속성)

   - [Margin (옵션 - margin 그룹)](DxChart속성/DxChart_속성.md#margin-옵션---margin-그룹)
   - [Margin Property 예제](DxChart속성/DxChart_속성.md#margin-사용-예제)
   - [Text Property 예제](DxChart속성/DxChart_속성.md#text-property-예제)
   - [제목 (옵션 - title 그룹)](DxChart속성/DxChart_속성.md#제목-옵션-title-그룹)
   - [X축 (옵션 - xaxis 그룹)](DxChart속성/DxChart_속성.md#x축-옵션-xaxis-그룹)
   - [Y축 (옵션 - yaxis 그룹)](DxChart속성/DxChart_속성.md#y축-옵션-yaxis-그룹)
   - [Background 설정하기](DxChart속성/DxChart_속성.md#background-설정하기)
   - [Label 설정하기](DxChart속성/DxChart_속성.md#label-설정하기)
   - [범례](DxChart속성/DxChart_속성.md#범례-설정하기)
   - [툴팁](DxChart속성/DxChart_속성.md#툴팁-설정하기)
   
[**3.** **Effect 설정하기**](DxChartEffect설정하기/DxChart_Effect설정하기.md#effect-설정하기)

   - [Draw](DxChartEffect설정하기/DxChart_Effect설정하기.md#draw)
   - [drawAni](DxChartEffect설정하기/DxChart_Effect설정하기.md#drawani)
   - [wave](DxChartEffect설정하기/DxChart_Effect설정하기.md#wave)
   - [grow](DxChartEffect설정하기/DxChart_Effect설정하기.md#grow)
   - [trace](DxChartEffect설정하기/DxChart_Effect설정하기.md#trace)
   - [unfold](DxChartEffect설정하기/DxChart_Effect설정하기.md#unfold-tobottom)
   - [unfoldFromCenterTrace (fromCenter)](DxChartEffect설정하기/DxChart_Effect설정하기.md#unfoldfromcentertrace-fromcenter)
   - [foldtocenter (toCenter)](DxChartEffect설정하기/DxChart_Effect설정하기.md#foldtocenter-tocenter)
   - [roundRobin 및 roundRobinSequential](DxChartEffect설정하기/DxChart_Effect설정하기.md#roundrobin-및-roundrobinsequential)
   - [implode](DxChartEffect설정하기/DxChart_Effect설정하기.md#implode)
   - [explode](DxChartEffect설정하기/DxChart_Effect설정하기.md#explode)
   - [차트 별 Effect 종류](DxChartEffect설정하기/DxChart_Effect설정하기.md#차트-별-effect-종류)


[**4.** **Multi Chart 생성하기**](DxChartEffect설정하기/DxChart_Effect설정하기.md#multi-chart-생성하기)
   - [Bar 및 Line 차트](DxChartEffect설정하기/DxChart_Effect설정하기.md#bar-및-line-차트)
   - [Bar 및 Pie 차트](DxChartEffect설정하기/DxChart_Effect설정하기.md#bar-및-pie-차트)
  

[**5.** **기타기능** ](DxChart기타기능/DxChart_기타기능.md#기타기능)

   - [ConvertDataset](DxChart기타기능/DxChart_기타기능.md#convertdataset)

   - [datachangeevent](DxChart기타기능/DxChart_기타기능.md#datachangeevent)   



[**6.** **차트 종류**](#차트-종류)

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





