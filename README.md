どうも、さかなのまえあしです。<br>
今回はトリアコンタンさんのElectronForMzプロジェクトでローカルセーブに成功したっぽい物ができたので検証用にクローンして差分をアップデートさせていただきました<br>
改変したのはmain.jsとプラグインのElectronForMz.jsになります<br>

あ、ちなみにAIにやってもらったので技術的なことについてはさっぱりです<br>

使い方はトリアコンタンさんのQiitaか<br>
https://qiita.com/triacontane/items/a8610bff9778ca2aaa3e<br>
私が実際にやってみた結果<br>
https://note.com/good_acacia483/n/nadf37f39c8f4<br>
を参考にしてください<br>

色々とテストしてみましたが、Windowsでの動作は問題はないと思われます<br>
（Ubuntu環境ではElectoronをインストールしたフォルダの下層にsaveフォルダが作成されました）<br>
（Macは持ってないのでテストできません）<br>
心配な方は改変したソースコードを読んで各自判断をしてください。<br>

この改造版でできるようになることは

１．ゲームの実行ファイルと同じ場所に「save」フォルダが作られる<br>
２．Web版と同じファイル構成（localStorage）を使いつつ、保存場所だけ実行ファイルと同じ場所（「save」フォルダ）に変更<br>
３、複数のゲームをデブロイしても一つのファイルに複数のゲームのデータが保持されるということがなくなる<br>
４．ゲーム削除時の対象となるゲームのデータ削除が容易に





LinuxやMacで１ゲームごとに１セーブフォルダを実現しようと思ったら<br>
一番確実なのは、package.jsonにゲーム名を明示的に設定しておくことだそうです。<br>

本家のトリアコンタンさんのプロジェクトを利用して実行してください。（こちらの版はWinで実行ファイルのフォルダにsaveフォルダを作成することに特化しています）<br>
package.jsonを作成したゲームごとに書き換え<br>
    "name": "electron-for-mz",<br>
この部分の名前を書き換えることで作成されるフォルダが変わるはず……<br>

こちら方面をオートでしてくれる改造はゲームタイトルを収得することができなかった為諦めました<br>

現状のElectronforMzではセーブファイルの扱い方に不満があったのでAIに指示してなんとか形になりました。<br>
（改造前はデフォルトで使えば一つのDBに複数のゲームデータが入る状態だった）<br>
ゲームごとにフォルダを変えれば少なくとも消したいゲームのデータだけ（丸ごとですが）消すことができるようになります<br>

この改造版について、トリアコンタンさんへの質問はしないようお願いいたします。
