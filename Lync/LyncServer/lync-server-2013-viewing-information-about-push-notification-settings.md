---
title: プッシュ通知の設定に関する情報の表示
TOCTitle: プッシュ通知の設定に関する情報の表示
ms:assetid: be5c6b01-4294-4d17-9772-fed40201e8a5
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ721868(v=OCS.15)
ms:contentKeyID: 49887124
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# プッシュ通知の設定に関する情報の表示

 

_**トピックの最終更新日:** 2013-02-23_

バッジ、アイコン、または警告の形で表示されるプッシュ通知は、モバイル アプリケーションが非アクティブなときでもモバイル デバイスに送信することができます。プッシュ通知は、新規または不在着信した IM への招待や、ボイス メールなどのイベントをユーザーに通知します。モバイル デバイス向けの情報プッシュ通知設定は、Lync Server 2013 コントロール パネル または Lync Server 2013 管理シェル を使用して表示できます。

## Lync Server コントロール パネル からのプッシュ通知情報を表示するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで、\[**クライアント**\] をクリックし、\[**プッシュ通知の構成**\] ナビゲーション ボタンをクリックします。

4.  \[**プッシュ通知の構成**\] ページで、表示したいサイトをクリックして、\[**編集**\]、\[**詳細の表示**\] の順にクリックします。

## Windows PowerShell コマンドレットを使用してプッシュ通知の構成情報を表示するには

Lync Server 管理シェル と **Get-CsPushNotificationConfiguration** コマンドレットを使用して、プッシュ通知の構成設定を表示できます。このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモート セッションから実行できます。リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 ([http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)) を参照してください。

## プッシュ通知の構成情報を表示するには

  - すべてのプッシュ通知の構成設定に関する情報を表示するには、Lync Server 管理シェル で次のコマンドを入力して Enter キーを押します。
    
        Get-CsPushNotificationConfiguration
    
    次のような情報が表示されます。
    
        Identity                               : Global
        EnableApplePushNotificationService     : False
        EnableMicrosoftPushNotificationService : False

詳細については、[Get-CsPushNotificationConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsPushNotificationConfiguration) コマンドレットのヘルプ トピックを参照してください。

## 関連項目

#### タスク

[Lync Server 2013 でプッシュ通知を構成する](lync-server-2013-configuring-for-push-notifications.md)

