# Tezos技術文書翻訳について

## 翻訳ソースについて

### PDF、Webページから翻訳しない

流布されている文書はPDFやWebページとして閲覧するものですが、翻訳はそこから**行ってはいけません**。翻訳を指示する場合も閲覧用最終出力を指定してはいけません。(参考としてこういう見た目の文書だ、と言うですと伝えるのは可。)

### ソースファイルを翻訳する

Teozs技術文書のほとんどは、LaTeX、Sphinx (reST)、Markdownというファイル形式で書かれています。このファイルに対して翻訳を指示、作業を行います。

* LaTeX https://ja.wikipedia.org/wiki/LaTeX
* Sphinx (reST) http://www.sphinx-doc.org/ja/stable/index.html
* Markdown https://ja.wikipedia.org/wiki/Markdown  たとえば、この文書はMarkdownで書かれています。

よほど特殊な事情がない限り、邦訳する場合は同じファイル形式を使ってください。
これらのツールの使い方や文書の書き方がわからないならば学んでください。

ソースファイルが見つからない場合、PDF や Webページから翻訳するのではなく、まず、ソースを探してください。ソースが見つからないのであれば、Tezos Japan Foundation の人に聞いてください。

ソースファイルを編集する利点は:

* ツールを選ばない: テキストデータなので、編集は容易で、誰でも見ることができる。
* 時間短縮: 元のレイアウト情報や数式データをそのまま利用可能。
* 同一文書内に元言語と翻訳の両方を置ける: 元の文を同じファイルに残しながら翻訳が可能。
* レビューのしやすさ: 翻訳に疑問があればコメントとして書き込める。
* 更新のしやすさ: 元のデータが更新された場合、その差分から翻訳のどこを直すべきかすぐわかる。

元のソースファイルを確認せず Microsoft Office 製品で翻訳を始めるのは絶対にやめてください。以上の利点が全て失われてしまいます。

翻訳指示者は、もし上記の条件を明示したにも関わらず、無視した翻訳が送られてきた場合、問答無用で差し戻ししてください。

### オリジナルソースのファイルの入手場所、バージョンをきちんと指定する

オープンソースとして公開されている文書ソースは、ほぼ全てバージョン管理システムGitを使って管理されています。翻訳を依頼する場合は、このソースの

* 場所 (URL)
* バージョン (commit hash)

を必ず指定してください。こうすることで、翻訳ターゲットが特定され、元文書の複数のバージョン間の細かい差異からくる翻訳の問題がなくなります。

また、元文書がアップデートされた場合、翻訳ターゲットとなったバージョンが明らかなので、差分を機械的に取得することが可能で、翻訳のアップデートも簡単に行えます。

## 翻訳データ蓄積について

翻訳データは、元文書が Git repository で管理されているならば、それを Tezos Japan Foundation の repository に import してブランチとして管理してください。

Gitってなにrepositoryって? 勉強してください(https://www.oreilly.co.jp/books/9784873114408/) 。

翻訳者はすでに Git を使える人材であることが望ましいです。翻訳文書を Git repository でバージョン管理することで、

* 翻訳の修正作業
* 元文書がアップデートされた際の翻訳データの追随
* 翻訳レビュー

が非常に楽になります。

## 翻訳者の能力

ほとんどのTezos文書は(インタビュー記事でもない限り)技術文書です。技術文書の翻訳は単なる英文和訳よりも難しいです。翻訳者の条件を挙げます:

最低限

* 科学論文を日本語と英語で執筆した経験がある
* 日本語での学会発表を行なったことがある(スライド和訳の場合)

あると望ましい条件

* 技術文書の翻訳実績がある (実績を見ることで能力を推し量れます。間違いだらけの訳をする人もいるので、中身を評価すること)
* 計算機科学か暗号通貨の勉強をしている修士課程学生またはそれ以上の学歴。
* LaTeX, Sphinx (reST), Markdown, Git の使用経験

これらの条件を満たさない人に発注してもまともな翻訳をしてくれません。
翻訳のレビューに非常に時間を取られるので、時間とお金の無駄になります。

このような技術文書のスキルは一朝一夕に得られたり、教えられたりするものではなく、数年の学究経験が必要です。一から育てるのはTezos Japanには無理だと思ってください。

計算機科学か暗号通貨の博士課程学生であれば、すでに技術英語、技術邦文にすでに親しみ、Git、LaTeXやMarkdownを使用したことがあり、Tezos技術文書に書かれている内容の一部はすでに十分知っていると期待できます。それでも翻訳をちょっとやってもらって能力を確かめたいところですが、、、

## 翻訳レビュー

翻訳レビューは計算機科学の学位取得者や暗号通貨技術者によって行われるべきです。

## 翻訳の仕方

### 元の文を残す

LaTeX, reST, Markdownとも内容をコメントアウトすることが可能なので、
元の文章をできるだけそのままコメント内に残して、翻訳文とオリジナルを簡単に対比できるようにしてください。翻訳作業とレビュー作業を軽減できます。

### 理解できない文章を無理に訳さない

自分が読んで理解できない文章の単語をとにかく日本語に訳してつなぎ合わせ、はいこれ翻訳、というのは絶対にやめてください。

#### 勉強する

もし元の文章に理解できない技術的な部分があれば、それについて勉強するのも翻訳の仕事です。ぜひ勉強してください。

#### 判らないものは判らないと明示する

勉強はしてみたが難しかったり、締め切りがタイトで勉強する時間がない場合、翻訳できそうにない、してみたが自信がない文章については、お茶は濁さずに、**できません、こう訳しましたが自信がありませんと明示**してください。

適当な訳を何も言わずに翻訳に混ぜられると、翻訳レビューワーはあなたの訳した**全ての**文章を信用できなくなり、全文を精査しなければいけなくなります。それはレビューワーが一から文章を翻訳するより長く時間がかかります。そうなると、あなたの価値はゼロどころかマイナスになりますから、あなたに翻訳は二度と発注されません。

#### メモを残す

翻訳していて気になったこと、よく判らないこと、本文自体がおかしいと思ったことはコメントとして翻訳に残してください。

### 翻訳例

以下に期待される翻訳例を載せます。私が作業中の`position_paper`の訳の一部です:

```latex
\begin{abstract}
%% The popularization of Bitcoin, a decentralized crypto-currency has inspired the
%% production of several alternative, or ``alt'', currencies.
%% Ethereum, CryptoNote,
%% and Zerocash all represent unique contributions to the crypto-currency space.
%% Although most alt currencies harbor their own source of innovation, they have
%% no means of adopting the innovations of other currencies which may succeed them.
%% We aim to remedy the potential for atrophied evolution in the crypto-currency 
%% space by presenting Tezos, a generic and self-amending crypto-ledger.
分散暗号通貨Bitcoinの普及は代替暗号通貨、いわゆる「アルトコイン」の誕生を引き起こした。
Ethereum、CryptoNote、Zerocashはそれぞれ暗号通貨技術の発展に独自の貢献をはたした。
ほとんどの代替通貨が独自のイノベーションのアイデアを持ってはいるが、\memo{source を源泉と訳すと硬いので}
他通貨のアイデアを利用して自通貨を成功に導くすべを持っていない。
暗号通貨技術発展が萎縮してしまう可能性を打破するため、
我々は一般的で\xxx{generic}自己修正可能な暗号台帳であるTezosを提案する。
\memo{generic => 一般的で、とした。ledgerは台帳と訳す。元帳だと唯一しかないイメージを持つため。 amendment => 修正。改正でも良いが、自己改正よりは自己修正のほうが耳障りが良い}

%% Tezos can instantiate any blockchain based protocol.
%% Its seed protocol specifies
%% a procedure for stakeholders to approve amendments to the protocol,
%% \emph{including} amendments to the amendment procedure itself.
%% Upgrades to Tezos are staged through a testing environment to allow
%% stakeholders to recall potentially problematic amendments.
Tezosはブロックチェーンに基づいたプロトコルならば何にでも採用する\xxx{instantiate}ことができる。
\memo{instansiate の訳語が良いものがない}
その開始時プロトコルには、\emph{修正手順自体への修正も含む}、
\memo{genesis ではなく seed とあるので原初、原始は避けた}
ステークホルダー(通貨保有者)によるプロトコル修正承認の手順が定められている。
\memo{利害関係者とすると後の文でおかしくなるところがあるので単にステークホルダーとする}
Tezosのアップグレードは段階的に行われる。
修正はまずテスト環境に適用される。もしそこで問題が発見された場合は、ステークホルダーはその修正を廃案とすることができる。
```

* データは`https://github.com/tezos/tezos-papers`のcommit`6909c0c8`の`position_paper.tex`を元にしています。
* 元のファイルはLaTeXで書かれているのでそのソースを元に編集しています
* 元の文章は段落ごとにコメントされ、翻訳はその後に続きます
* `\xxx{...}`や`\memo{...}`は訳として不安な部分だったり、訳出する時の選択を記録するメモです。
