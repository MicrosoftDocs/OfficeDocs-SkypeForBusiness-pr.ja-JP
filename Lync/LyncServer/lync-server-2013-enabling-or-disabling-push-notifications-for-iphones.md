---
title: 'Lync Server 2013: iPhones のプッシュ通知を有効または無効にする'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enabling or disabling push notifications for iPhones
ms:assetid: 8bbf531a-807f-4a8f-814a-94bfed8f97ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688122(v=OCS.15)
ms:contentKeyID: 49733719
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ccd4e4c65c539f5a6af36d1012c32059b3e291a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833240"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-or-disabling-push-notifications-for-iphones-in-lync-server-2013"></a>Lync Server 2013 での iPhones のプッシュ通知を有効または無効にする

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-23_

プッシュ通知は、モバイルアプリケーションが非アクティブになっている場合でも、バッジ、アイコン、または通知の形式で、iPhone に送信できます。 プッシュ通知は、新規または不在着信した IM の招待状やボイスメールなどのイベントをユーザーに通知します。 IPhone のプッシュ通知を有効または無効にするには、Lync Server 2013 コントロールパネルまたは Lync Server 2013 Management Shell を使用します。

<div>

## <a name="to-enable-push-notifications-for-iphone-by-using-lync-server-control-panel"></a>Lync Server コントロールパネルを使用して iPhone のプッシュ通知を有効にするには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーションバーで、[**クライアント**] をクリックし、[**プッシュ通知の構成**] ナビゲーションボタンをクリックします。

4.  [**プッシュ通知の構成**] ページで、編集するサイトをクリックし、[**編集**] メニューをクリックして、[**詳細の表示**] をクリックします。

5.  [ **Apple プッシュ通知を有効にする**] チェックボックスをオンにします。

6.  [**コミット**] をクリックします。

</div>

<div>

## <a name="to-disable-push-notifications-for-iphone-by-using-lync-server-control-panel"></a>Lync Server コントロールパネルを使用して iPhone のプッシュ通知を無効にするには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーションバーで、[**クライアント**] をクリックし、[**プッシュ通知の構成**] ナビゲーションボタンをクリックします。

4.  [**プッシュ通知の構成**] ページで、編集するサイトをクリックし、[**編集**] メニューをクリックして、[**詳細の表示**] をクリックします。

5.  [ **Apple プッシュ通知を有効にする**] チェックボックスをオフにします。

6.  [**コミット**] をクリックします。

</div>

<div>

## <a name="enabling-or-disabling-push-notifications-to-iphone-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用して、iPhone へのプッシュ通知を有効または無効にする

Apple iPhone へのプッシュ通知を有効または無効にするには、 **Set-csp・の設定**コマンドレットを使用します。 このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、「Lync Server Windows PowerShell のブログ記事」を参照してください[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。「リモート PowerShell を使用して Microsoft Lync Server 2010 を管理する」を参照してください。

<div>

## <a name="to-enable-push-notifications-for-iphone"></a>IPhone でプッシュ通知を有効にするには

  - IPhone でプッシュ通知を有効にするには、EnableApplePushNotificationService プロパティの値を True ($True) に設定します。 次に例を示します。
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableApplePushNotificationService $True

</div>

<div>

## <a name="to-disable-push-notifications-for-iphone"></a>IPhone のプッシュ通知を無効にするには

  - IPhone のプッシュ通知を無効にするには、EnableApplePushNotificationService プロパティの値を False ($False) に設定します。 次に例を示します。
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableApplePushNotificationService $False

</div>

詳細については、「 [Set-cspの設定](https://docs.microsoft.com/powershell/module/skype/Set-CsPushNotificationConfiguration)」の「ヘルプ」を参照してください。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でプッシュ通知を構成する](lync-server-2013-configuring-for-push-notifications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

