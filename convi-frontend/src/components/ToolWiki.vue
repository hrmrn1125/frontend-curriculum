<template>
<div class="l-toolWiki">
  <div class="p-textWrap">
    <h1>1. ブラウザ</h1>
    <h2>インストール</h2>
    <p class="p-text">
      以下リンクからインストールしてください。<br>
      <a class="c-link" href="https://www.google.co.jp/chrome/" target="_blank" rel="noopener noreferrer">Google Chrome</a><br>
      インストールしたらデベロッパーツールの使い方も同時に確認しましょう。<br>
      デザイン崩れが無いか、エラーが無いかなど重要な事項をデベロッパーツールで確認し、<br>それから制作物を提出していくことになりますので、知識を持っていることが必須のツールです。<br>
      <a class="c-link" href="https://willcloud.jp/knowhow/dev-tools-01/" target="_blank" rel="noopener noreferrer">デベロッパーツールの基本的な使い方</a>
    </p>
  </div>
  <div class="p-textWrap">
    <h1>2. テキストエディタ</h1>
    <div>
      <h2>インストール</h2>
      <p class="p-text">
        以下のリンク先から自分のOS(MACやWindowsなど)にあったソフトをインストールしてください。
        <a class="c-link" href="https://code.visualstudio.com/" target="_blank" rel="noopener noreferrer">Visual Studio Code</a>
      </p>
    </div>
    <div>
      <h2>拡張機能</h2>
      <p class="p-text">
        下記拡張機能をインストールしてください。
      </p>
      <table class="p-table">
        <tr>
          <th>名前</th>
          <th>機能概要</th>
        </tr>
        <tr>
          <td>Japanese Language Pack for Visual Studio Code</td>
          <td>VS Codeを日本語にする</td>
        </tr>
        <tr>
          <td>indent-rainbow</td>
          <td>インデントに各色で色付けする</td>
        </tr>
        <tr>
          <td>Trailing Spaces</td>
          <td>不要な余白を可視化する</td>
        </tr>
        <tr>
          <td>zenkaku</td>
          <td>全角スペースを可視化する</td>
        </tr>
        <tr>
          <td>Rainbow Brackets</td>
          <td>括弧に色付けすることで対応位置がわかりやすくなる</td>
        </tr>
        <tr>
          <td>Path Autocomplete</td>
          <td>ファイルパスを補完候補に表示する</td>
        </tr>
        <tr>
          <td>Code Spell Checker</td>
          <td>コードのスペルミスを指摘する</td>
        </tr>
        <tr>
          <td>Prettier - Code formatter</td>
          <td>コードを解析し、独自のルールで再出力し、必要に応じてコードを折り返す</td>
        </tr>
        <tr>
          <td>endwise</td>
          <td>endの記述が必要な際に自動で挿入してくれる</td>
        </tr>
        <tr>
          <td>Editor Config for VS Code</td>
          <td>Editor Configファイルを適用させる</td>
        </tr>
        <tr>
          <td>vscode-icons</td>
          <td>各フォルダ、ファイルにアイコンをつけてくれる</td>
        </tr>
        <tr>
          <td>ESLint</td>
          <td>開いたフォルダーにインストールされているESLintライブラリを使用する</td>
        </tr>
        <tr>
          <td>.ejs</td>
          <td>ejsファイルをハイライトする</td>
        </tr>
      </table>
    </div>
    <div>
      <h2>設定ファイル</h2>
      <p class="p-textBtm">
        下記を設定ファイル(User Settings)に追加してください。<br><br>
        【手順】<br>
        1. &nbsp;左下の歯車マークをクリックし、「設定」をクリック<br>
        2.「設定」ファイルが開かれる為、「設定の検索」という検索バーに「settings」と入力<br>
        3.「settings.jsonで編集」というリンクをクリックしてファイルを開き、<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{ }内に追加(元々記述されているコードがある場合はその下に追加する)
      </p>
      <div class="p-codeBlock">
        <button class="p-copyBtn" @click="writeToClipboard()">
          <img src="../assets/images/copy-icon.png" alt="Copy">
        </button>
        <div class="p-fileName">settings.json</div>
        <pre>
          <code id="target">
            
            
            ,"editor.formatOnSave": true,
              "[javascript]": {
                "editor.formatOnSave": true
            },
            "emmet.includeLanguages": {
              "ejs": "html",
              },
            "prettier.eslintIntegration": true,
            "files.associations": {
              "*.ejs": "html"
            }</code>
        </pre>
      </div>
    </div>
  </div>
  <div class="p-textWrap">
    <h1>3. Git</h1>
    <h2>Gitとは何か？</h2>
    <p class="p-text">
      Gitとは、ファイルのバージョン管理を簡単にしてくれるシステムです。<br>
      複数の開発者が一つのシステムを作っていくとき、コードを書いたファイルをまとめたり、ファイル名が被らない<br>(勝手に上書きされてしまわない)ようにするのは、手動では大変ですよね？<br><br>
      そういった際に活躍するのがGitです。<br><br>
      Gitの基本概念についての詳細は、下記リンクから「Gitを使ったバージョン管理」〜「ワークツリーとインデックス」を読んでください！(必読)<br>
      <a class="c-link" href="https://backlog.com/ja/git-tutorial/intro/01/" target="_blank" rel="noopener noreferrer">【必読】(サル先生のGit入門) Gitを使ったバージョン管理</a><br>
      ※「サル先生のGit入門」通称「サルGit」は、ここから先に起こりうる問題(Git関連のエラー等)の大多数を解決に導いてくれる重要なサイトです！必ず目を通し、何度も読んで理解していきましょう。
    </p>
    <h2>インストール</h2>
    <p class="p-text">
      以下リンクから「Gitのインストール」〜「初期設定」までを読んで、実行してください。<br>
      <a class="c-link" href="https://backlog.com/ja/git-tutorial/intro/05/" target="_blank" rel="noopener noreferrer">(サル先生のGit入門) Gitのインストール</a><br>
      サルGitでは次項で説明する「SourceTree」というツールを用いていますが、それを使わずにGitインストール・初期設定をすることも可能です。<br>
      是非調べてやってみましょう。以下のサイトが比較的分かりやすいです。<br>
      <a class="c-link" href="https://www.sejuku.net/blog/73444" target="_blank" rel="noopener noreferrer">Gitをインストールしてみよう！Windows/Macどちらも丁寧に解説</a><br>
      ※公式サイトからインストーラーをダウンロード → 設定を変えずNextをひたすら押していきインストール完了 → ユーザー名とメールアドレスをコマンドで設定、という流れで完了となります。<br>
    </p>
  </div>
</div>
</template>

<script>
export default {
  name: 'ToolWiki',
  methods: {
    writeToClipboard() {
      const copyText = this.$el.querySelector('#target').textContent
      navigator.clipboard
        .writeText(copyText)
        .then(() => {
          alert('コードをコピーしました')
        })
        .catch(e => {
          console.error(e)
        })
    }
  }
}
</script>


<style>
.l-toolWiki {
  width: 100%;
  height: 100%;
}

.p-textWrap {
  text-align: left;
  margin-bottom: 48px;
}

.p-textWrap:last-child {
  margin-bottom: 0px;
  padding-bottom: 0;
}

.p-text {
  margin-bottom: 36px;
  padding: 0 20px;
}

.p-textBtm {
  margin-bottom: 24px;
  padding: 0 20px;
}

.p-table {
  margin: -16px 20px 40px;
}

.c-link {
  left: 0;
  color: #417CCE;
  display: flex;
  align-items: center;
}

.c-link:after {
  content: '';
  display: inline-block;
  margin-left: 6px;
  width: 16px;
  height: 16px;
  background-image: url(../assets/images/link-newTab.png);
  background-size: contain;
  background-repeat: no-repeat;
}

.p-codeBlock {
  width: 100%;
  height: auto;
  position: relative;
  background-color: #404950;
  border-radius: 10px;
}

.p-codeBlock pre {
  color: #FFFFFF;
}

.p-copyBtn {
  width: 36px;
  height: 36px;
  position: absolute;
  top: 10px;
  right: 10px;
  border: none;
  border-radius: 50%;
  background-color: none;
  padding: 0;
}

.p-copyBtn img {
  width: 36px;
  height: 36px;
}

.p-fileName {
  width: auto;
  height: 22px;
  position: absolute;
  top: 0;
  left: 0;
  border: none;
  border-radius: 10px 0 0 0;
  background-color: #6D7983;
  color: #FFFFFF;
  padding: 6px 10px;
}
</style>