
> **DXChart 개발자 튜토리얼**
>
> **(Nexacro용)**
---

**\[목 차\]**
각각의 목차를 클릭시 해당 페이지로 이동합니다

 [**1.** **DxChart 준비하기**](DxChart준비하기/DxChart_준비하기.md#dxchart-준비하기)
   - [Nexacro Project 만들기](#nexacro-project-만들기)
   - [차트모듈 설치하기](#차트모듈-설치하기)
   - [샘플화면 만들기](#샘플화면-만들기)
   - [차트함수 만들기](#차트함수-만들기)
   - [구성요소 용어 설명](#구성요소-용어-설명)
   - [데이터 형식](#데이터-형식)
     - [data Property](#data-property)
     - [binddataset Property](#binddataset-property)

 [**2.** **DxChart 속성**](DxChart속성/DxChart_속성.md##DxChart-속성)
   - [Margin (옵션 - margin 그룹)](#margin-옵션---margin-그룹)
   - [X축 (옵션 - xaxis 그룹)](#text-property-예제)
   - [Y축 (옵션 - yaxis 그룹)](#y축-옵션-yaxis-그룹)
   - [배경 (옵션 - background 그룹)](#\_Toc162962562)
   - [제목 (옵션 - title 그룹)](#제목-옵션-title-그룹)
   - [범례](#_Toc162962564)
   - [툴팁](#_Toc162962565)
   - [라벨 (옵션 - labels 그룹)](#\_Toc162962566)
   - [그외](#_Toc162962570)

[**3.** **차트의 주요 메소드**](DxChart기타기능/DxChart_기타기능.md##차트의-주요-메소드)

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





