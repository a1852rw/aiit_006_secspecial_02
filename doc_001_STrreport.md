# 課題1の報告書

## 報告する内容について
### ST選択と報告の形式
- IPAのサイトより認証のされたSTを選択する
    - JISEC認証製品リスト ( https://www.ipa.go.jp/security/jisec/certified_products/cert_list.html )
- 選定は過去3年以内(2015年~)の製品が望ましい
- CCのバージョンは3.1とする
- EALのレベルは問わない
- 15分程度の時間で発表できる分量とする(PPTだと10枚程度)
- なるべく興味を持てる製品を選択することが望ましい

### 報告の中でまとめる内容について
- 選択したSTのTOEについてまとめる
- セキュリティ課題についてまとめる
- セキュリティ対策方針についてまとめる

### EALについて
- 選択したSTのEALを調べ妥当性について考察する 

## 報告書本文
### STの選択について
- 選択したTOE
    - 認証番号：C0532
    - 製品名：Defense Platform Business Edition CC Ver.3.6.1.5
    - TOE名：Defense Platform Business Edition CC
    - EAL：EAL3
    - カテゴリ：ホワイトリスト型マルウェア対策ソフトウェア
    - CCバージョン：3.1 リリース4
    - CCRA相互承認の範囲：EAL2+ALC_FLR.2
    - 認証年月日：2016年12月9日
    - 提供者：ハミングヘッズ株式会社
    - 掲載ページ：https://www.ipa.go.jp/security/jisec/certified_products/c0532/c0532_it5526.html
    - 選択した理由：セキュリティソフトに興味があり該当する者の中で唯一のマルウェア対策ソフトであったため
- 選択したST
    - ST名称：Defense Platform Business Edition CCセキュリティターゲット
    - バージョン：1.41版
    - 形式：PDFファイル (掲載ページにて確認)
    - 掲載ページ：https://www.ipa.go.jp/security/jisec/certified_products/c0532/c0532_st.pdf
- 参照した資料
    - 認証報告書：[c0532_rpt.pdf](https://www.ipa.go.jp/security/jisec/certified_products/c0532/c0532_rpt.pdf)
    - 認証書：[c0532_img.pdf](https://www.ipa.go.jp/security/jisec/certified_products/c0532/c0532_img.pdf)
    - ST：[c0532_st.pdf](https://www.ipa.go.jp/security/jisec/certified_products/c0532/c0532_st.pdf)

### TOEの説明
[ハミングヘッズ株式会社のホームページ](https://www.act2.com/dep/) およびセキュリティターゲット(以下「本ST」)内の記述をもとにTOEを説明する。
今回選択したTOE(以下「本TOE」)はハミングヘッズ株式会社(以下「ハミングヘッズ社」)の開発したホワイトリスト型マルウェア対策ソフトウェアであり、本TOEでは「Defense Platform Business Edition」ビジネスエディションのサーバプログラムとクライアントプログラムが含まれる。インストール先端末のハードウェアとソフトウェアはTOEの範囲には含まれない。
また、TOEを構成する文書としてマニュアルやガイダンスあわせて8種類がある。
TOEは管理者がサーバおよびユーザのPCにインストールをすると想定されている。その際にWindwosおよびUEFIの設定も管理者の責任において行う必要がある。

### 本TOEのセキュリティ課題について
本TOEがセキュリティ課題とする脅威は二種類ある。一つ目が「T.WRITE_RESOURCE」であり、プログラムが管理者の許可なく保護対象を書き換えること。もう一つが「T.INFORMATION_LEAKAGE」であり、プログラムが管理者の許可なくユーザのデータを外部に送信することである。

### セキュリティ課題への対応方法について
本TOEには「判定機能」「管理機能」「監査機能」でセキュリティ課題への対応を行う。
「判定機能」はユーザのPC上で動作し、管理者の設定したホワイトリストにより保護対象への書き込みと管理者の許可しない通信の検出とブロックを行う。(ハミングヘッズ社ホームページによると本TOEには「検知モード」があり、インストール先PCの動作履歴を蓄積することができる。そこからホワイトリストを作成することで管理者の負担を減らすことができる)
「管理機能」「監査機能」は


### EALの説明
本STの動作保証レベルはEAL3である。
保証クラスと保証コンポーネントについては本STのP37を参照のこと。内容を読み取るためにCCパート3を参照する必要がある。
EAL3では方式テストが行われる。また開発環境の確認や構成管理システムの確認、サブシステムまでに開発者の行ったテスト結果の確認も行われる。

### EALの妥当性について考察
EALの内容を確認しつつ考察した。
