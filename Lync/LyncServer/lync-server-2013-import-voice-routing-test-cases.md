---
title: 'Lync Server 2013: 音声ルーティング テスト ケースのインポート'
TOCTitle: 音声ルーティング テスト ケースのインポート
ms:assetid: 6546e24c-9ad2-428b-92b2-63948ed0f884
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398460(v=OCS.15)
ms:contentKeyID: 48272292
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 音声ルーティング テスト ケースのインポート

 

_**トピックの最終更新日:** 2013-02-21_

テスト ケースを使用すると、組織の音声ルートをテストできます。ダイヤルする番号、ダイヤル プラン、使用する音声ポリシーなどを定義し、Lync Server 2013 が指定された条件下で指定された番号を PSTN ネットワークに正常にルーティングできることを確認できます。

テスト ケースは、通常は、ケースを作成して実行したサーバーにのみ保存されます (テスト ケースは Lync Server コントロール パネルで作成できます)。ただし、これらのテスト ケースは XML ファイル (拡張子 .vtest) としてエクスポートし、他のサーバーにインポートできます。これにより、同じテストをトポロジの別の地点に配置された別のコンピューターで実行できます。

## 音声ルーティングのテスト ケースをインポートするには

1.  RTCUniversalServerAdmins グループのメンバーとして、あるいは CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。詳細については、「[Lync Server 2013 でのセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)」を参照してください。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**音声ルーティング**\] をクリックします。

4.  \[**操作**\] メニューの \[**テスト ケースのインポート**\] をクリックします。

5.  インポートするテスト ケースのファイル (.vtest) を探して、\[**開く**\] をクリックします。

6.  \[**確定**\] をクリックし、\[**すべて確定**\] をクリックします。
    
    > [!NOTE]
    > .vtest ファイルをインポートするときは常に、[<strong>すべて確定</strong>] コマンドを実行して、テスト ケースを公開する必要があります。詳細については、「操作」のドキュメントの「<a href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 での音声ルーティング構成に対する保留中の変更の公開</a>」を参照してください。


## 関連項目

#### タスク

[Lync Server 2013 での音声ルーティング テスト ケースのエクスポート](lync-server-2013-export-voice-routing-test-cases.md)

