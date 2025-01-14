# Receptionist

参考動画：https://youtu.be/p9ki89buY68 <br>
※ 参考動画は完璧ではありません．年によってルールも異なるので，あくまで参考程度にしてください．

※ 詳細なルールや配点につきましては，アリーナ環境が決まり次第，追加していきます．気になる点や議論したい点などがありましたら，[Issues](https://github.com/RoboCupAtHomeJP/Rule2022/issues)へお願いします．

<br>

## メインゴール
このタスクでは，会場に到着したゲストへの受付を行い，リビングルームに案内することを想定しています．このとき，ゲストの名前や好きな飲み物等を聞き，オーナ(ジョン)に紹介します．また，到着したばかりのゲストに空いている席を案内します．

※ Educationリーグと同じ競技を採用していますが，差別化のため異なる採点方式を用いています．

<br>

## フォーカス
このタスクは，人認識，既知環境でのマッピングやナビゲーション，音声対話，タスクプランニングなどに焦点を当てています．

<br>

## セットアップ
- ロケーション： 家庭環境を模したアリーナ環境が用いられます．特に競技はリビングルームで行われます．アリーナ内は事前にマッピングすることができます(既知の環境)．
- スタートロケーション： ロボットは，アリーナ内のあらかじめ決められた場所(入口ドア付近)からスタートします．
- オーナー(ジョン)：オーナー(ジョン)の位置は，事前にロボットに知らされています．リビングルームの指定された場所に座っています．オーナー(ジョン)は各チームから選出してください．

<br>

## シナリオ
### a. スタートフェーズ
1. 競技時間：競技時間は7分間になります．
2. 配置：レフェリーは，チームにロボットをスタート位置へ移動させるよう指示します．
3. スタート：レフェリーはスタートの合図を出し，タイマーをスタートさせます．同時にチームは最後の簡単なセットアップ(スタートボタンを押す等)を完了し，エリアを離れます．このとき，ボタンを2つ以上押すなど複雑なセットアップ手順の実施は認められません．また，これ以降チームがロボットに触れると即座に失格になります．
4. ゲスト：各ゲストにはあらかじめ名前と好きな飲み物が設定されています．
5. ゴール：1人のゲストに対して，レセプションフェーズとガイドフェーズを行います．これを2人に行うことを目標としています．

### b. レセプションフェーズ
1. ゲストの検出：ロボットは会場に到着し，部屋に入ってきたゲストを検出します．
2. ゲストの受付：その後，ロボットはゲストの名前と好きな飲み物についての情報を聞きます．このとき，ロボットが名前や好きな飲み物について理解できなかった場合，もう一度発言を繰り返すように要求することができます．ここで，ロボットはゲストの年齢も推定します．
3. ゲストの紹介：到着したゲストをオーナーであるジョンに紹介します．このとき，ロボットは紹介する人を指さし，名前と好きな飲み物について紹介します．もし名前を間違得てしまった場合は減点されてしまいます．

### c. ガイドフェーズ
1. 案内：ゲストを空いている席へと案内し，その席に座ってもらいます．このとき，ロボットはゲストが座れる場所を指さします．
2. 席の入れ替え：新しいゲストが来るたびに，リビングにいるゲストたちの場所を交換します．このとき，レセプションフェーズにて推定した年齢をもとに，最年長の方を優先してソファーに座らせて上げるように誘導します．

<br>

## デウスエクスマキナ
本タスクでは，次のデウスエクスマキナが採用されます．デウスエクスマキナでは該当アクションの点数は入らないが，より簡単な手法でアクションをスキップし，タスクを継続することができます．

<table>
  <tr>
    <th> <b>Action<b> </th>
    <th> <b>Bypassing<b> </th>
  </tr>
   <tr>
    <td> オーナ(ジョン)の特定 </td>
    <td>
      <ul>
        <li> オーナ(ジョン)にマーカを持たせることで，オーナ(ジョン)を特定する </li>
      </ul> 
    </td>
  </tr>
  <tr>
    <td> 空いている席の特定 </td>
    <td>
      <ul>
        <li> 空いている席にマーカを設置することで，席が空いていることを特定する </li>
      </ul> 
    </td>
  </tr>
  <tr>
    <td> 年齢の推定 </td>
    <td>
      <ul>
        <li> ゲストの年齢を推定するのではなく，音声対話によって年齢を聞く </li>
        <li> この場合，「最年長の方をソファに座らせる」の得点は半分になる </li>
      </ul> 
    </td>
  </tr>
</table>

<br>

## スコアシート
<table>
  <tr>
    <th> <b>Action</b> </th>
    <th> <b>Score</b> </th>
  </tr>
  <tr>
    <td colspan="2" align="center"> <b> メインタスク </b> </td>
  </tr>
  <tr>
    <td> 1人目のゲストをオーナ(ジョン)に紹介する <br> 
      <ul>
        <li> 1人目のゲストの名前を紹介する </li>
        <li> 1人目のゲストの好きな飲み物を紹介する </li>
        <li> 紹介中，1人目のゲストを指差す／向く </li>
      </ul> 
    </td>
    <td align="center"> <!-- 50 <br>　--> 25 <br> 25 <br> 35 </td>
  </tr>
  <tr>
    <td> 1人目のゲストに空いている席を案内する <br> 
      <ul>
        <li> 空席を検出する </li>
        <li> 空席を指差す／向いて提供する </li>
      </ul> 
    </td>
    <td align="center"> <!-- 75 <br> --> 60 <br> 65 </td>
  </tr>
  <tr>
    <td> 2人目のゲストをオーナ(ジョン)に紹介する <br> 
      <ul>
        <li> 2人目のゲストの名前を紹介する </li>
        <li> 2人目のゲストの好きな飲み物を紹介する </li>
        <li> 紹介中，2人目のゲストを指差す／向く </li>
      </ul> 
    </td>
    <td align="center"> <!-- 50 <br> --> 25 <br> 25 <br> 35 </td>
  </tr>
  <tr>
    <td> 2人目のゲストに空いている席を案内する <br> 
      <ul>
        <li> 空席を検出する </li>
        <li> 空席を指差す／向いて提供する </li>
      </ul> 
    </td>
    <td align="center"> <!-- 75 <br> --> 60 <br> 65 </td>
  </tr>
  <tr>
    <td colspan="2" align="center"> <b> ボーナスタスク </b> </td>
  </tr>
  <tr>
    <td> 最年長の方をソファに座らせる <br> </td>
    <td align="center"> 80 </td>
  </tr>
  <tr>
    <td colspan="2" align="center"> <b>ペナルティ</b> </td>
  </tr>
  <tr>
    <td> 不参加(無断) </td>
    <td align="center"> -500 </td>
  </tr>
  <tr>
    <td> <b> 合計(ボーナスタスクを含む) </b> </td>
    <td align="center"> <b> 500 </b> </td>
  </tr>
</table>

※ Educationリーグと同じ競技を採用していますが，差別化のため異なる採点方式を用いています．
※ 本大会ではアリーナ環境にドアが無いことから，「ゲストに対して入り口のドアを開けてあげる」のタスクや得点は無くなりました．

<br>

## 運営(EC)による指示
- 準備
  - ボランティア3名に名前と飲み物を割り当てます．
  - リビングルームに人を配置します(配置し直す)．
- アナウンス(競技スタート2時間前)
  - ロボットのスタート地点の選択し，アナウンスします．
  - ボランティアをジョンと選択し，アナウンスします．

<br>

## レフェリー(TC)の動き
※TCは各チームから数名選出され，他チームの競技において以下を行ってもらいます．
- 競技開始30分前に集まり，説明を受け，スコアシートを受け取ります．
- シナリオに記載のレフェリーとして行動します．
- 競技を採点します．
- 他のTCと採点内容を確認します．
- スコアシートを提出します．
