# resas

日本のRESAS（地域経済分析システム）APIの利用方法を示す、クライアントサイドJavaScriptのサンプル集です。

**ライブデモ:** [http://codeforfukui.github.io/resas/](http://codeforfukui.github.io/resas/)

## プロジェクトについて

このリポジトリは、RESAS APIから経済・人口データを取得・表示する、シンプルで自己完結型のHTMLおよびJavaScriptアプリケーションを提供します。サンプルはバニラJavaScriptで記述されており、DOM操作やヘルパー関数のために小規模なユーティリティライブラリ（`fukuno.js`）を使用しています。これらは、開発者が自身のウェブアプリケーションにRESASデータを統合する際の実践的なガイドとして役立ちます。

## サンプル

デモサイトには以下のサンプルが含まれています:

*   **[インバウンド観光統計 (`getinbound.html`)](http://codeforfukui.github.io/resas/getinbound.html)**
    *   選択した都道府県のインバウンド観光データ（外国人訪問者数）を表示します。
    *   月や時間帯（昼/夜）でデータをフィルタリングできます。
    *   結果は国別に並べ替えられ、テーブルで表示されます。

*   **[1人あたり地方税 (`gettax.html`)](http://codeforfukui.github.io/resas/gettax.html)**
    *   1人あたりの地方税データをドリルダウン形式で探索できるインターフェースを提供します。
    *   まず都道府県を選択すると、その区市町村一覧が表示されます。
    *   区市町村をクリックすると、その税データを取得し、生のJSONレスポンスを表示します。

*   **[都道府県と区市町村 (`allcity.html`)](http://codeforfukui.github.io/resas/allcity.html)**
    *   すべての都道府県とその区市町村を表示する階層型ブラウザです。
    *   都道府県をクリックすると展開され、都市のリストや「大都市」の数などの統計が表示されます。

*   **[都道府県一覧 (`allpref.html`)](http://codeforfukui.github.io/resas/allpref.html)**
    *   日本の全都道府県の生のJSONデータを取得して表示する基本的なサンプルです。

## 使い方

これらのサンプルを実行するには、RESAS APIキーが必要です。

1.  **APIキーの取得:** [RESAS APIポータル](https://opendata.resas-portal.go.jp)で登録し、無料のAPIキーを取得してください。
2.  **サンプルの表示:** [getinbound.html](http://codeforfukui.github.io/resas/getinbound.html) などのデモページにアクセスします。
3.  **キーの入力:** ページ下部の入力フィールドにAPIキーを貼り付け、「データ取得開始」ボタンをクリックします。キーは今後の利用のためにブラウザのローカルストレージに保存されます。
4.  **データの探索:** ドロップダウンやリストを操作してAPIにクエリを送信し、データを表示します。

## 使用しているAPIエンドポイント

これらのサンプルでは、以下のRESAS APIエンドポイントの利用方法を示しています:

*   `/api/v1-rc.1/prefectures` - すべての都道府県のリストを取得します。
*   `/api/v1-rc.1/cities` - 都道府県内の区市町村のリストを取得します。
*   `/api/v1-rc.1/municipality/taxes/perYear` - 区市町村の1人あたり地方税データを取得します。
*   `/api/v1/partner/docomo/inbound` - NTTドコモが提供するインバウンド観光データを取得します。

*注意: RESAS APIには利用制限があり、通常は1秒あたり5リクエスト、1日あたり2000リクエストまでです。*

## ライセンスと出典

アプリケーションのライセンスは Code for Fukui による CC BY です。

出典：[RESAS（地域経済分析システム）](https://opendata.resas-portal.go.jp)
