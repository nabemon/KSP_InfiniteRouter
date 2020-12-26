# KSP Infinite Router
KSP Multi Script for manual divisi of Infinite Brass/Woodwinds.<br>
It allows you to assign each note to divisi parts you want to play in.<br>
To use this script, you can use Infinite Brass/Woodwinds as an ensemble patch without recording each part.

## Usage

## Note

## How it works

# Japanese

## 概要
Infinite Brass/Woodwindsで手動ディヴィジを行うためのマルチスクリプトです。
アーティキュレーション（属性）で、ノートごとに演奏させるパートを指定することができます。
Infinite Brass/Woodwindsを、パートごとに入力しなくても、通常のアンサンブル音源に近い感覚で扱えるようになります。

## 使い方
InfiniteRouter.kspをダウンロードして、KONTAKTのスクリプトフォルダに置きます。

- Windowsの場合
    - C:\Users\(ユーザ名)\Documents\Native Instruments\Kontakt\presets\Multiscripts
- Macの場合
    - Macintosh HD>ユーザ>(ユーザ名)>書類>Native Instruments>Kontakt>presets>Multiscripts

各楽器ごとにKONTAKTを立ち上げ、それぞれのパッチを読み込みます。
このとき、チャンネルは1〜6を使用してください。

<img width="329" alt="Kontakt_1" src="https://user-images.githubusercontent.com/46624978/103148888-e874a080-47a7-11eb-88fd-253d375799cd.png">


KSPで、さきほどのInfiniteRouter.kspを読み込みます。
<img width="665" alt="Kontakt_2" src="https://user-images.githubusercontent.com/46624978/103148948-6cc72380-47a8-11eb-8ab4-ec5dbc127775.png">

メニューで最大パートを指定します。
例えば、Horn 1〜6であれば6 Partsを、Flute 1〜3であれば3 Partsです。
<img width="653" alt="InfiniteRouter" src="https://user-images.githubusercontent.com/46624978/103148959-9bdd9500-47a8-11eb-9a45-412bd852f5fa.png">

CubaseのExpression Mapをダウンロードして、読み込みます。
<img width="653" alt="Expmap" src="https://user-images.githubusercontent.com/46624978/103149034-3b028c80-47a9-11eb-8579-13ad985aa808.png">

TouchOSC用のコントローラーも用意しました。タブレットをお持ちの方はぜひご活用ください。
<img width="653" alt="TouchOSC" src="https://user-images.githubusercontent.com/46624978/103149051-608f9600-47a9-11eb-8ff7-0543f079e4a9.PNG">

## 注意点

- 早いフレーズや大量のデータが集中すると、処理落ちしてCCが正しく処理されない可能性があります。
- あくまでもスケッチ用途で、本番では各パートに直接振り分けることをオススメします。
- 本スクリプトは、もちろんInfinite Brass/Woodwinds以外の音源にも使用可能です。ただ、キースイッチに対応していないので、その辺りは各自でカスタマイズしてください。

## 仕組み

Ch1-6に立ち上げた各パートに対して、入力されたノートのチャンネルに応じて以下のような動作をします。
- Ch1-6
    - 素通し
- Ch7
    - パート1(Ch1)+パート2(Ch2)にルーティング
- Ch8
    - 最大パート3の場合
        - パート2(Ch2)+パート3(Ch3)にルーティング
    - 最大パート4 or 6の場合
        - パート3(Ch3)+パート4(Ch4)にルーティング
- Ch9
  - パート5(Ch5)+パート6(Ch6)にルーティング
- Ch10
  - パート1+2+3にルーティング
- Ch11
  - パート4+5+6にルーティング
- Ch 12
  - 全パートにルーティング

MIDI CCは最大パート数に応じて、全てのチャンネルにルーティングされます







