---
title: 'Lync Server 2013: ボイス ルート構成ファイルのインポート'
TOCTitle: ボイス ルート構成ファイルのインポート
ms:assetid: 4bac05e5-ed8b-4f10-96b0-b8a65ff356ec
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398301(v=OCS.15)
ms:contentKeyID: 48272017
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でのボイス ルート構成ファイルのインポート

 

_**トピックの最終更新日:** 2012-11-01_

音声ルーティング構成を公開せずに保存する場合、この手順を実行して、Lync Server コントロール パネルの構成のエクスポート コマンドおよびインポート コマンドを使用し、音声ルーティング構成のスナップショットを保存して取得します。音声ルーティング構成ファイル (.vcfg) をインポートするまでに、サーバーで音声ルーティング構成が変更されていた場合、Lync Server コントロール パネルの \[**音声ルーティング**\] グループの各種ページで、音声ルーティングに未確定の変更があることが表示されます。これらの未確定の変更は、調整が必要な 2 つの構成間の相違です。

グループ内のいずれかのページで、設定に対して未確定の変更を行った場合、これらの変更はエクスポートされた音声構成ファイル (.vcfg) に保存されます。このことにより、変更を公開する前に、複数のセッションで音声ルーティング構成を変更できます。

## 音声ルーティング構成をインポートするには

1.  RTCUniversalServerAdmins グループのメンバーとして、あるいは CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。詳細については、「[Lync Server 2013 でのセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)」を参照してください。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**音声ルーティング**\] をクリックします。

4.  \[**操作**\] メニューの \[**構成のインポート**\] をクリックします。

5.  インポートする構成ファイルを検索し、\[**開く**\] をクリックします。

6.  \[**確定**\] をクリックし、\[**すべて確定**\] をクリックします。
    
    > [!NOTE]
    > 音声構成ファイルをインポートする場合は、必ず [<strong>すべて確定</strong>] コマンドを実行して構成変更を公開する必要があります。詳細については、「操作」のドキュメントの「<a href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 での音声ルーティング構成に対する保留中の変更の公開</a>」を参照してください。


## 関連項目

#### タスク

[Lync Server 2013 でのボイス ルート構成ファイルのエクスポート](lync-server-2013-export-a-voice-route-configuration-file.md)  
[Lync Server 2013 での音声ルーティング構成に対する保留中の変更の公開](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)

