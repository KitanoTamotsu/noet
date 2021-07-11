## 　　Lesson32.　ListFilterを使ってみる
#### 開発メモ
### 1.LitsFilterってなんだろう
　ListFilterもScriptFilter同様にAlfredの出力を行うものです
<br>　Alfredに何か入力したら、それに反応して表示される行フォーマットのあれです
<br>　ScriptFilterはその名の通りスクリプトで動的に出力フォーマットを作成しますが
<br>　ListFilterは静的に設定パネルで作成します
<br>　具体的には、RSSみたいに刻々と変化する情報をインターネットから取得する場合は
<br>　ScriptFilterが適しています。一方、定型的な操作はListFilterが適しています
### 2.フローの構成
　今回は、ListFilterとScriptFilterを2段構えで利用します
<br>　題材はよろず投稿サイトのnote.com。色々なアクセス方法があるので、
<br>　そのアクセス方法や一覧をListFilterで提供して、個々のページへの
<br>　アクセスをScriptFilterで実現します
<br>　別の言い方をすれば、トップページと第1階層のページをListFilterで、
<br>　第2階層以下をScriptFilterで提供するというイメージでもよいかと思います
### 3.ListFilter
　ListFilterは設定パネルで作成します
<br>　すでにJson出力フォーマットを知っている方には理解しやすいとおもいます
<br>　出力フォーマットの要素で言えば、title,subtitle,arg,iconをGUIで設定すればOK　
<br>　今回argについては任意の数字を設定していて、後続で稼働する
<br>　ScriptFilterの振り分けをしています
### 4.ScriptFilterの振り分け
　後続のScriptFilterは、それぞれソースコードが変わるので個々に作成しています
<br>　そのためConditionalユーティリティでフローを分岐させています
<br>　ArgandValsユーティリティがあるのは、標準出力をクリアもしくは設定して
<br>　ScriptFilterが表示される際のデフォルト文言をコントロールするためのです
### 4.ScriptFilter
　ScriptFilterは、今までのLessonと同様の作りです
<br>　・cURLで該当ページのソースを取得
<br>　・ソースを解釈して、必要な要素を配列に格納
<br>　・AlfredのJson出力フォーマットを作成
<br>　という感じ
<br>　なお、ヘルプセンターについては、ヒアドキュメントで作っています
#### 背景
　ListFilterのサンプルを作ろうと試行錯誤しました
<br>　定例作業的なものだと、あまりに個人的なローカルサンプルになりだし
<br>　そもそも私のmacはインターネット閲覧と写真編集しかしてないですし
<br>　そんなおりnote.comを発見
<br>　検索での閲覧、カテゴリーからのアクセス、タグからのアクセスなど
<br>　いろいろなアクセスが整理されていたので取り上げました
#### 取扱説明
### 機能:
　Note.comサイトの投稿記事を閲覧する
### インストール:
　1.[alfredworkflow](https://github.com/KitanoTamotsu/noet/releases/download/1.0/note.com.alfredworkflow.zip)をダウンロード 
<br>　2.ファイルをダブルクリックしてワークフローに登録

### 使い方:
　Alfredからキーワード『note』で起動
<br>
<br>
[トップページに戻る](https://kitanotamotsu.github.io/)

