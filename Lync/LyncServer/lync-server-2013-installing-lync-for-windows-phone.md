---
title: Lync for Windows Phone のインストール
TOCTitle: Lync for Windows Phone のインストール
ms:assetid: bf502546-ff69-489f-a92e-a78b58803d53
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Hh690996(v=OCS.15)
ms:contentKeyID: 52056693
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync for Windows Phone のインストール

 

_**トピックの最終更新日:** 2016-12-08_

Lync 2013 for Windows Phone は、ユーザーがインストールできるアプリケーションで、Windows Phone Marketplace から入手できます。

## Lync for Windows Mobile のインストール

<http://go.microsoft.com/fwlink/?linkid=231901> の Windows Phone Marketplace にユーザーをダイレクトして、Lync 2013 for Windows Phone をデバイスにインストールするようにユーザーに指示できます。

## DNS SRV レコードを使って Exchange Web サービスを公開する場合

Lync クライアントの Exchange 統合を有効にするために、組織によっては DNS SRV レコードを使って Exchange Web サービスの URL を公開します。Microsoft Download Center のドキュメント「Microsoft Exchange Server 統合についての理解とトラブルシューティング」([http://go.microsoft.com/fwlink/?LinkID=391095](http://go.microsoft.com/fwlink/?linkid=391095)) のシナリオでは、これが必須として説明されています。しかし、Windows Phone プラットフォームは SRV 参照をサポートしないため、Windows Phone ユーザーの Exchange 統合はこのシナリオには従いません。Windows Phone ユーザーには、自動的にサーバーを検出できるようにするのではなく Exchange Web サービスの URL を指定するように指示してください。

Windows Phones で Lync の設定を構成するために、ユーザーには、次のように指示します。

1.  Windows Phone の Lync の設定で、\[**Exchange**\] の画面を選びます。

2.  \[**サーバーの自動検出**\] を \[**オフ**\] にします。

3.  空白のフィールドをタップして、Exchange Web サービスの完全修飾ドメイン名 (FQDN) または URL を入力します。
    
    > [!NOTE]
    > Exchange Web サービス サーバーの完全修飾ドメイン名 (FQDN) と 完全な URL のどちらかを指定します。FQDN を指定すると、プロトコル (https://) と Exchange Web サービスのパス (/ews/exchange.asmx) は自動的に追加されます。Exchange Web サービスのパスが異なる場合は、完全な URL を指定します。


4.  画面を閉じます。

## モバイル クライアント インストールの検証

クライアントを構成して正常にサインインした後、次のテストを行って、インストールした Lync 2013 がモバイル デバイスで正しく動作することを確認します。

**会社のディレクトリにある連絡先の検索**

1.  連絡先一覧の下部で、**\[検索\]** をタップします。

2.  グローバル アドレス一覧にだけ含まれる連絡先を検索します。

3.  連絡先名が検索結果に表示されることを確認します。

**インスタント メッセージングおよびプレゼンスのテスト**

1.  連絡先一覧で、連絡先をタップします。

2.  連絡先カードで、\[**IM**\] アイコンをタップします。

3.  インスタント メッセージング (IM) ウィンドウが表示され、IM の入力と送信が可能であることを確認します。

**ダイヤルアウト会議のテスト**

1.  Outlook で、Lync 会議をスケジューリングします。

2.  モバイル デバイスで、会議の招待状を開きます。

3.  参加する会議のリンクをクリックします。

4.  会議サービスからの通話に応答し、会議のオーディオに接続していることを確認します。

**プッシュ通知のテスト**

1.  ユーザー A のモバイル デバイスで、ユーザー A のアカウントを使用して Lync にサインインします。

2.  モバイル デバイスで別のアプリケーションを開きます。

3.  異なるクライアントで、ユーザー B のアカウントを使用して Lync にサインインします。

4.  IM をユーザー B からユーザー A に送信します。

5.  IM 通知がユーザー A のモバイル デバイスに表示されていることを確認します。

