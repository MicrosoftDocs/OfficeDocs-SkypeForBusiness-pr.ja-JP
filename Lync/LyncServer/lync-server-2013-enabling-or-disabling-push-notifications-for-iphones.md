---
title: iPhone のプッシュ通知の有効化または無効化
TOCTitle: iPhone のプッシュ通知の有効化または無効化
ms:assetid: 8bbf531a-807f-4a8f-814a-94bfed8f97ef
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ688122(v=OCS.15)
ms:contentKeyID: 49887038
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# iPhone のプッシュ通知の有効化または無効化

 

_**トピックの最終更新日:** 2013-02-23_

プッシュ通知は、モバイル アプリケーションが非アクティブであっても、バッジ、アイコン、または警告の形式で iPhone に送信できます。プッシュ通知は、ユーザーに、新規または不在着信の IM 招待状、ボイス メールなどのイベントを通知します。Lync Server 2013 コントロール パネルまたは Lync Server 2013 管理シェル を使用して、iPhone のプッシュ通知の有効と無効を切り替えることができます。

## Lync Server コントロール パネルから iPhone のプッシュ通知を有効にするには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**クライアント**\] をクリックし、\[**プッシュ通知構成**\] ナビゲーション ボタンをクリックします。

4.  \[**プッシュ通知構成**\] ページで、編集するサイトをクリックし、\[**編集**\] メニューをクリックして、\[**詳細の表示**\] をクリックします。

5.  \[**Apple Push 通知を有効にする**\] チェックボックスをオンにします。

6.  \[**確定**\] をクリックします。

## Lync Server コントロール パネルから iPhone のプッシュ通知を無効にするには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**クライアント**\] をクリックし、\[**プッシュ通知構成**\] ナビゲーション ボタンをクリックします。

4.  \[**プッシュ通知構成**\] ページで、編集するサイトをクリックし、\[**編集**\] メニューをクリックして、\[**詳細の表示**\] をクリックします。

5.  \[**Apple Push 通知を有効にする**\] チェックボックスをオフにします。

6.  \[**確定**\] をクリックします。

## Windows PowerShell コマンドレットを使用して iPhone へのプッシュ通知を有効または無効にするには

**Set-CsPushNotificationConfiguration** コマンドレットを使用して、Apple iPhone へのプッシュ通知を有効にすることができます。このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 ([http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)) を参照してください。

## iPhone のプッシュ通知を有効にするには

  - iPhone のプッシュ通知を有効にするには、EnableApplePushNotificationService プロパティの値を True ($True) に設定します。次に例を示します。
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableApplePushNotificationService $True

## iPhone のプッシュ通知を無効にするには

  - iPhone のプッシュ通知を無効にするには、EnableApplePushNotificationService プロパティの値を False ($False) に設定します。次に例を示
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableApplePushNotificationService $False

詳細については、[Set-CsPushNotificationConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsPushNotificationConfiguration) コマンドレットのヘルプ トピックを参照してください。

## 関連項目

#### タスク

[Lync Server 2013 でプッシュ通知を構成する](lync-server-2013-configuring-for-push-notifications.md)

