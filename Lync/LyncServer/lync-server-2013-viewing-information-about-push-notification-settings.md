---
title: 'Lync Server 2013: プッシュ通知設定に関する情報の表示'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Viewing information about push notification settings
ms:assetid: be5c6b01-4294-4d17-9772-fed40201e8a5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721868(v=OCS.15)
ms:contentKeyID: 49733801
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: da9279d09ab3b344514a472f3fb0f38e7071aabd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848179"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-information-about-push-notification-settings-in-lync-server-2013"></a>Lync Server 2013 でのプッシュ通知設定に関する情報の表示

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-23_

プッシュ通知は、モバイルアプリケーションが非アクティブになっている場合でも、バッジ、アイコン、または通知の形式でモバイルデバイスに送信できます。 プッシュ通知は、新規または不在着信した IM の招待状やボイスメールなどのイベントをユーザーに通知します。 Lync Server 2013 コントロールパネルまたは Lync Server 2013 Management Shell を使用して、モバイルデバイスの情報プッシュ通知の設定を表示できます。

<div>

## <a name="to-view-push-notification-information-from-lync-server-control-panel"></a>Lync Server コントロールパネルからプッシュ通知情報を表示するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーションバーで、[**クライアント**] をクリックし、[**プッシュ通知の構成**] ナビゲーションボタンをクリックします。

4.  [**プッシュ通知の構成**] ページで、表示するサイトをクリックし、[**編集**] メニューをクリックして、[**詳細の表示**] をクリックします。

</div>

<div>

## <a name="viewing-push-notification-information-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用したプッシュ通知情報の表示

プッシュ通知の構成設定を表示するには、Windows PowerShell と、" **Get-Cspの設定**" コマンドレットを使用します。 このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、「Lync Server Windows PowerShell のブログ記事」を参照してください[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。「リモート PowerShell を使用して Microsoft Lync Server 2010 を管理する」を参照してください。

<div>

## <a name="to-view-push-notification-configuration-information"></a>プッシュ通知の構成情報を表示するには

  - すべてのプッシュ通知の構成設定に関する情報を表示するには、Lync Server 管理シェルで次のコマンドを入力し、enter キーを押します。
    
        Get-CsPushNotificationConfiguration
    
    次のような情報が表示されます。
    
        Identity                               : Global
        EnableApplePushNotificationService     : False
        EnableMicrosoftPushNotificationService : False

</div>

詳細については、「[収集-Cspの設定](https://docs.microsoft.com/powershell/module/skype/Get-CsPushNotificationConfiguration)」の「ヘルプ」を参照してください。

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

