#GitHub Tutorial
GitHubに関しての簡単なtutorialです。

##gitに関して
gitは，linuxのソースコードの管理の為に開発されたバージョン管理システムです。
ソースコードはバージョンアップを繰り返しながら変化していきます。簡単に言うと，gitを使えばこのバージョンアップを
すべて記録し，後からたどれるようになります。また，複数人で開発する際に同じソースコードを編集するというのを
より簡単に行うことができます。

##GitHubに関して
GitHubは，gitによるソースコードの管理をサポートするサービスです。localにあるgitのレポジトリを
github上にリモートレポジトリとして保存してくれるというのが一番大きな機能です。このリモートレポジトリを共有して
複数人開発をすることができます。また，gitは基本的にCUIで動かしますが，githubによってGUI的に操作したり閲覧したりすることができます。
wikiやissuesなどの機能もあり，バグ報告なども行うことができるかと思います。

##実際のワークフロー
gitおよびgithubを使うにあたって次の二つのパターンがあると思います。
* 開発を始めるにあたってgithub上に新しいrepositoryを作成する。
* 既にgithub上にあるrepositoryをローカルにclone(コピー)して開発を始める

今のところ複数人で開発することは少ない，またrepositoryを作る練習もかねて前者のパターンを
やってみましょう。

### TASK1:repository の初期化
まず，localにrepositoryを作るために初期化をする必要があります。
適当なディレクトリを作成してgitのレポジトリ化しましょう。
```
mkdir GitHubTutorial
cd GitHubTutorial
git init
```
gitの設定ファイルが生成されていることが分かります。
```
ls -a
```

###TASK2:READMEの作成
このチュートリアルのように，githubではREADMEというファイルが自動的に表示されるようになっています。ここではREADME.mdという，md(マークダウン)形式にファイルが用いいられます。このファイルを作成してみましょう。内容は何でもかまいません。
```
vim README.md
```
gitに変更を記録するためにはcommitをしなければなりません。以下のように行います
```
git add README.md
git status
git commit -m "message"
```
まずcommitするファイルをaddで選択し（stage），commitで実際にその変更をgitに記録します。
この繰り返しでソースコードをアップデートしていきます。

###TASK3:github上にレポジトリを作成,アップロード
先ほど作成したファイルをgithubにアップロードする為に，github上に新しいレポジトリを作りましょう
そのレポジトリにローカルのデータをコピー（push）します。
```
git remote add origin :url
git push -u origin master
```

###TASK5:コミットをもとに戻す
特定のバージョンに戻すことができます。
```
git revert :commitID
```
