# 卒業論文のチェックリスト

一番大事なのは内容．しかし，体裁が大事なのもまた事実．  
体裁のミスを減らせば，指導者には内容のチェックに注力してもらえるはず．  
状況によって正解は異なるため，すべてを鵜呑みにはしないように（ココ重要）．  
論文執筆の注意事項@Google Driveも参照のこと．  

以下のWebページを参考に，自分が躓きがちなことをまとめた．  
[LaTeXで論文作成のいろいろ](http://www.eng.kagawa-u.ac.jp/~haruna/memo/TeX/TeXtips.html)  
[卒業論文・修士論文自己チェックリスト](http://www.aise.ics.saitama-u.ac.jp/~gotoh/Download/CheckListForTheses-ja.pdf)[PDF]  
[論文執筆のためのチェックリスト](http://kanamori.cs.tsukuba.ac.jp/docs/writing_paper_checklist.pdf)[PDF]  
[卒論・修論チェックリスト](https://qiita.com/tttamaki/items/f553e4cb9f4f08cc8872)  
[参考文献目録の書き方](http://www.okada-lab.org/Ronbun/Citation/ListKakikata.php)  
[使ってはいけない LaTeX のコマンド・パッケージ・作法](http://ichiro-maruta.blogspot.jp/2013/03/latex.html)

## 論文のお約束
### 本文
- [ ] 句読点はすべて全角の「．」「，」．
  - いちいち変換するのは面倒なのでIMEの設定を変えておこう．
- [ ] 参考文献は文中に書く．
  - 例）×`〜が提案されている．[2]` ◯`〜が提案されている[2]．`  
  ピリオドより前に文献番号がくる．
- [ ] 文献を主語にするときは`[2]は〜`とせず，`文献[2]は〜`とする．
- [ ] 著者を主語にするときは人数に対応させる．
  - １人のとき：`A[2]は〜提案した．`
  - ２人のとき：`AとB[2]は〜提案した．`
  - ３人以上のとき：`Aら[2]は〜提案した．`
  - natbib + jecon.bstにより自動化可能．
- [ ] 略語は初めて使う場所でフルスペルを書く．
  - 例）`Intelligent Mechanism Laboratory（IML）`
  - acroパッケージにより自動化可能．
- [ ] 一度しか使わない略語はそもそも略す必要はないと考える．
- [ ] 固有名詞を使うときは`\footnote`か引用で説明する．
- [ ] 英数字とスペースは基本的に半角文字を使う．
- [ ] 図表や数式，参考文献は本文中で必ず何かしら説明があること．本文で触れられていないものは載せないか，付録にする．

### 数式
- [ ] 数式も文章なので「．」「，」をつける．
- [ ] 文書中の数式の記号も数式文字として書く．
  - 例）`$x$は変数である．`
- [ ] 数式で使っている記号はすべて説明する．
- [ ] 数式の変数名は重複させない．
- [ ] ベクトルを表す変数は`\bm`コマンドで太字にする．
- [ ] eqnarrayは古いので使っちゃダメ．
  - `amsmath.sty`の数式コマンドを使おう．
  - （参考）[amsmathの数式環境まとめ
](https://qiita.com/t_kemmochi/items/a4c390b4967b13f3afb7)
- [ ] 複数行に渡る数式は`&`を使って`=`で揃える．

※ 数式のTeXについてはこちらも参照．  
[現代的 LATEX コードのすすめ](https://prml.main.ist.hokudai.ac.jp/~ryo/contents/textech2016/textech.pdf) [PDF]

### 図表
- [ ] 図のキャプションは下，表のキャプションは上．
- [ ] キャプションは文章なので，名詞だけでも「．」で終わる．
- [ ] 図表を引用する場合はキャプションに注釈を付ける．
  - 例）`フレームワークの概要図（文献[1]より抜粋）．`
- [ ] 図はPDF形式推奨（なるべくベクタ画像で）．
- [ ] グラフ中の数値の有効桁を揃える．
- [ ] グラフの縦軸横軸には単位があれば必ず書く．
- [ ] 図表は基本的にはページの上側に揃える．
  - `[!t]`のように!を入れるとTeXが最大限努力する．
- [ ] 図はモノクロ印刷でもわかる色使いだとベター．

### ハイフンの使い分け
- `-` ハイフン
  - ２つの単語を繋げて１つにするとき．  
  例）`state-of-the-art`
- `--` enダッシュ
  - 範囲を表すとき．  
  例）`pp.101--110`
- `---` emダッシュ
  - 説明を書く場合，引用文の先頭，時間の経過，省略などを表すとき．
- `$-$` マイナス
  - マイナスは数式として記述する．

### 参考文献
- [ ] BibTeXを使う．参考文献ベタ打ちはやめておく．
  - BibLaTeX + biber が使えればイマドキ．[参考](http://konn-san.com/prog/why-not-latexmk.html)．
- [ ] Google Scholarからbib表記を取ってこれるが，必ず誤りがないか確認する．
  - 出版社サイトがbibファイルを提供している場合も同様にチェックする．
- [ ] タイトルの大文字小文字は元の文献の通りにする．
  - 通常BibTeXのtitleは先頭文字以外を小文字に変換してしまうが，`{}`で囲んだ文字列は大文字小文字が入力どおりになる．そのため，全体を２重に`{}`で囲っておけば記述したまま表示されるので混乱がない．  
  例）`title={{Image Sentiment Analysis Using Latent Correlations Among Visual, Textual, and Sentiment Views}}`
- [ ] 参考文献リストの著者名はet al. などで省略しない．
- [ ] ファーストネームはイニシャルにする．
  - bibファイルを変えるのではなくstyファイルの設定を変えること．
- [ ] ページ数のハイフンは`-`ではなくenダッシュ`--`で書く．
  - 例）×`pages={101-110}`　◯`pages={101--110}`
- [ ] URLを引用するときは最終アクセス日を書き添える．
  - 例）`[1] flickrBLOG, “Find every photo with flickrs new unified search experience,”  
http://blog.flickr.net/en/2015/05/07/flickr-unified-search/, May 2015, Last accessed: 09/24/2015.`  

```TeX
@misc{
  author       = {flickrBLOG},
  title        = {{Find every photo with Flickr’s new unified search experience}},
  howpublished = "\url{http://blog.flickr.net/en/2015/05/07/flickr-unified-search/}",
  year         = {2015},
  month        = {May},
  note         = {Last accessed: 09/24/2015.},
}
```
- [ ] 略記法を使う場合は略語に統一する．

|用語|略記法|
|:--- |:--- |
|Transactions on|Trans.|
|in Proceedings of|Proc.|
|Conference on|Conf.|
|International|Int.|

## TeXのこと
- [ ] 図・表・数式・引用を本文で参照するときはTeXの機能を必ず使う．
  - `\ref`や`\eqref`や`\cite`のこと
- [ ] `\ref`や`\eqref`や`\cite`の前にはチルダを付ける．
  - 例）`図~\ref{fig:figure}`  
  チルダはそこでの改行を禁止する＆半角スペースをあける，という役割があり，数字だけが行頭に来てしまうのを防ぐ．
  - cleverefパッケージを使うと「図」などを自動表示できる．
- [ ] 参照抜けがないか確認しておく．
  - `?`をPDFから全文検索すると参照エラーがわかる．
- [ ] ダブルクォーテーションは\`\`と''で囲むように書く．
  - そもそも和文ではダブルクォーテーションは使わないのが吉．
- [ ] 小文字の略語のピリオド後のスペースは「\\ 」と書く．
  - 例）`Li et al.\ are`  
  TeXは小文字の半角ピリオドの後が文末と判断し半角スペースを２つ自動で挿入する．  
  したがって，文末ではないピリオド後にはスラッシュと半角スペースを記述し，半角スペース１つにする．
- [ ] 大文字の略語のピリオド前は「\@」と書く．
  - 例）`SIP\@.`  
  大文字の後のピリオドはそのままだと文末として解釈されないので．
- [ ] [使ってはいけないコマンド](http://ichiro-maruta.blogspot.jp/2013/03/latex.html)．古いコマンドはハマリポイントになるので基本的には使わないこと．

|  | Legacy:weary: | Currency:blush: |
|:--- |:--- | :--- |
|太字|`{\bf …}`|`\textbf{…}`|
|強調| |`\emph{…}`|
|イタリック|`{\it …}`|`\textit{…}`|
|デフォルトの太さ| |`\textmd{…}`|
|ローマン体|`{\rm …}`|文章：`\textrm{…}` <br> 数式：`\mathrm{…}`|
|中央揃え|`\begin{center}` <br> `\includegraphics{…}` <br> `\end{center}`| `\centering` <br> `\includegraphics{…}`|
|付録|`\begin{appendix}` <br> `\section{huga}` <br> `\end{appendix}`| `\appendix` <br> `\section{huga}`|
|図を並べる|subfigure, subfig|subcaption|
|箇条書き|enumrate|enumitem|
|アルゴリズム|algorithmic|algpseudocode|
|数式|`\begin{eqnarray}`|`\begin{align}`など|
|グラフィックドライバ|dvips|dvipdfmx|

## 日本語のこと
- [ ] ですます調は使わない．謝辞を除いては．
- [ ] 体言止めは使わない．
- [ ] 章の名前や図表のキャプションをざっくりにしない．
  - 「3章 実験1」だけだとどんな実験をしたのか伝わらないのであまりよくない．
- [ ] 表記ゆれに気をつける．
  - 例）「ユーザー」と「ユーザ」 「行なう」と「行う」
- [ ] 一文は長過ぎないようにする．
- [ ] 読点は息継ぎし易い程度に打つ．
- [ ] 段落の長さは適切に．
  - 一文だけの段落は本当に必要か？
- [ ] 指示語（こそあど）を多用しない．
- [ ] 「〜を行う」というような書き方は冗長な可能性あり．
  - 例）×「検討が行われている．」 ◯「検討されている．」
- [ ] 可能性（possibility）は「ある／なし」，蓋然性（probability）は「高い／低い」[要出典]．
- [ ] 口語表現はご法度．
  - 例）〜的な，正直〜，いまいち〜．
- [ ] ベターな書き方リスト．あくまで参考程度に．

| Before:weary: | After:blush: |
|:--- |:--- |
|こういった|こうした|
|当り|当たり|
|高ければ|高い場合|
|〜が違う場合|〜が異なる場合|
|〜していく|〜する|
|〜なら|〜であれば|
|〜するのに|〜するために|
|〜する事|〜すること|
|〜と言える|〜といえる|
|〜に連れ|〜につれ|
|僅かに|わずかに|
