---
title: Windows Phone のプッシュ通知の有効化または無効化
TOCTitle: Windows Phone のプッシュ通知の有効化または無効化
ms:assetid: a34f0c5c-4228-40e3-9d93-bc0b5df4895d
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ688162(v=OCS.15)
ms:contentKeyID: 49887083
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Windows Phone のプッシュ通知の有効化または無効化

 

_**トピックの最終更新日:** 2013-02-23_

バッジ、アイコン、または警告の形で表示されるプッシュ通知は、モバイル アプリケーションが非アクティブなときでも Windows Phone に送信することができます。プッシュ通知は、新規または不在着信した IM への招待や、ボイス メールなどのイベントをユーザーに通知します。Windows Phone デバイスのプッシュ通知は、Lync Server 2013 コントロール パネルまたは Lync Server 2013 管理シェルを使用して有効または無効にできます。

## Lync Server コントロール パネルで Windows Phone のプッシュ通知を有効にするには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで、\[**クライアント**\] をクリックし、\[**プッシュ通知の構成**\] ナビゲーション ボタンをクリックします。

4.  \[**プッシュ通知の構成**\] ページで、編集したいサイトをクリックして、\[**編集**\]、\[**詳細の表示**\] の順にクリックします。

5.  \[**Microsoft プッシュ通知を有効にする**\] チェック ボックスをオンにします。

6.  \[**確定**\] をクリックします。

## Lync Server コントロール パネルで Windows Phone のプッシュ通知を無効にするには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで、\[**クライアント**\] をクリックし、\[**プッシュ通知の構成**\] ナビゲーション ボタンをクリックします。

4.  \[**プッシュ通知の構成**\] ページで、編集したいサイトをクリックして、\[**編集**\]、\[**詳細の表示**\] の順にクリックします。

5.  \[**Microsoft プッシュ通知を有効にする**\] チェック ボックスをオフにします。

6.  \[**確定**\] をクリックします。

## Windows PowerShell コマンドレットを使用して Windows Phone のプッシュ通知を有効または無効にするには

**Set-CsPushNotificationConfiguration** コマンドレットを使用して Windows Phone のプッシュ通知を有効または無効にすることができます。このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモート セッションから実行できます。リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 ([http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)) を参照してください。

## Windows Phone のプッシュ通知を有効にするには

  - Windows Phone のプッシュ通知を有効にするには、EnableMicrosoftPushNotificationService プロパティの値を True ($True) に設定します。次に例を示します。
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableMicrosoftPushNotificationService $True

## Windows Phone のプッシュ通知を無効にするには

  - Windows Phone のプッシュ通知を無効にするには、EnableMicrosoftPushNotificationService プロパティの値を False ($False) に設定します。次に例を示します。
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableMicrosoftPushNotificationService $False

詳細については、[Set-CsPushNotificationConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsPushNotificationConfiguration) コマンドレットのヘルプ トピックを参照してください。

## 関連項目

#### タスク

[Lync Server 2013 でプッシュ通知を構成する](lync-server-2013-configuring-for-push-notifications.md)

