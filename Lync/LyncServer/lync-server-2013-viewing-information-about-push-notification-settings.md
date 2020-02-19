---
title: 'Lync Server 2013: プッシュ通知設定に関する情報の表示'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing information about push notification settings
ms:assetid: be5c6b01-4294-4d17-9772-fed40201e8a5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721868(v=OCS.15)
ms:contentKeyID: 49733801
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 73345feedda10a5cd7979b7683b5a700de578085
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136585"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="viewing-information-about-push-notification-settings-in-lync-server-2013"></a>Lync Server 2013 のプッシュ通知設定に関する情報の表示

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-23_

プッシュ通知は、バッジ、アイコン、または通知の形式で、モバイルアプリケーションが非アクティブな場合でもモバイルデバイスに送信できます。 プッシュ通知は、ユーザーに、新規または不在着信の IM 招待状、ボイス メールなどのイベントを通知します。 モバイルデバイスの情報プッシュ通知の設定は、Lync Server 2013 コントロールパネルまたは Lync Server 2013 管理シェルのいずれかを使用して表示できます。

<div>

## <a name="to-view-push-notification-information-from-lync-server-control-panel"></a>Lync Server コントロールパネルからプッシュ通知情報を表示するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで [**クライアント**] をクリックし、[**プッシュ通知構成**] ナビゲーション ボタンをクリックします。

4.  [**プッシュ通知の構成**] ページで、表示するサイトをクリックし、[**編集**] メニューをクリックして、[**詳細の表示**] をクリックします。

</div>

<div>

## <a name="viewing-push-notification-information-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用してプッシュ通知情報を表示する

プッシュ通知の構成設定を表示するには、Windows PowerShell と、コマンドレットの**取得**を使用します。 このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。

<div>

## <a name="to-view-push-notification-configuration-information"></a>プッシュ通知の構成情報を表示するには

  - すべてのプッシュ通知構成設定に関する情報を表示するには、Lync Server 管理シェルで次のコマンドを入力し、enter キーを押します。
    
        Get-CsPushNotificationConfiguration
    
    次のような情報が表示されます。
    
        Identity                               : Global
        EnableApplePushNotificationService     : False
        EnableMicrosoftPushNotificationService : False

</div>

詳細については、「Get-help」と[いう](https://docs.microsoft.com/powershell/module/skype/Get-CsPushNotificationConfiguration)コマンドレットのヘルプトピックを参照してください。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でのプッシュ通知の構成](lync-server-2013-configuring-for-push-notifications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

