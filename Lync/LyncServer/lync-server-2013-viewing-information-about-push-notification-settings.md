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

# <a name="viewing-information-about-push-notification-settings-in-lync-server-2013"></a><span data-ttu-id="533c5-102">Lync Server 2013 のプッシュ通知設定に関する情報の表示</span><span class="sxs-lookup"><span data-stu-id="533c5-102">Viewing information about push notification settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="533c5-103">_**トピックの最終更新日:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="533c5-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="533c5-104">プッシュ通知は、バッジ、アイコン、または通知の形式で、モバイルアプリケーションが非アクティブな場合でもモバイルデバイスに送信できます。</span><span class="sxs-lookup"><span data-stu-id="533c5-104">Push notifications, in the form of badges, icons, or alerts, can be sent to a mobile device even when the mobile application is inactive.</span></span> <span data-ttu-id="533c5-105">プッシュ通知は、ユーザーに、新規または不在着信の IM 招待状、ボイス メールなどのイベントを通知します。</span><span class="sxs-lookup"><span data-stu-id="533c5-105">Push notifications notify a user of events such as a new or missed IM invitation and voice mail.</span></span> <span data-ttu-id="533c5-106">モバイルデバイスの情報プッシュ通知の設定は、Lync Server 2013 コントロールパネルまたは Lync Server 2013 管理シェルのいずれかを使用して表示できます。</span><span class="sxs-lookup"><span data-stu-id="533c5-106">You can view information push notifications settings for mobile devices by using either Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-view-push-notification-information-from-lync-server-control-panel"></a><span data-ttu-id="533c5-107">Lync Server コントロールパネルからプッシュ通知情報を表示するには</span><span class="sxs-lookup"><span data-stu-id="533c5-107">To view push notification information from Lync Server Control Panel</span></span>

1.  <span data-ttu-id="533c5-108">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="533c5-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="533c5-109">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="533c5-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="533c5-110">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="533c5-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="533c5-111">左側のナビゲーション バーで [**クライアント**] をクリックし、[**プッシュ通知構成**] ナビゲーション ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="533c5-111">In the left navigation bar, click **Clients**, and then click the **Push Notification Configuration** navigation button.</span></span>

4.  <span data-ttu-id="533c5-112">[**プッシュ通知の構成**] ページで、表示するサイトをクリックし、[**編集**] メニューをクリックして、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="533c5-112">On the **Push Notification Configuration** page, click the site you want to view, click the **Edit** menu, and then click **Show details**.</span></span>

</div>

<div>

## <a name="viewing-push-notification-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="533c5-113">Windows PowerShell コマンドレットを使用してプッシュ通知情報を表示する</span><span class="sxs-lookup"><span data-stu-id="533c5-113">Viewing Push Notification Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="533c5-114">プッシュ通知の構成設定を表示するには、Windows PowerShell と、コマンドレットの**取得**を使用します。</span><span class="sxs-lookup"><span data-stu-id="533c5-114">You can view push notification configuration settings by using Windows PowerShell and the **Get-CsPushNotificationConfiguration** cmdlet.</span></span> <span data-ttu-id="533c5-115">このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="533c5-115">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="533c5-116">リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。</span><span class="sxs-lookup"><span data-stu-id="533c5-116">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-push-notification-configuration-information"></a><span data-ttu-id="533c5-117">プッシュ通知の構成情報を表示するには</span><span class="sxs-lookup"><span data-stu-id="533c5-117">To view push notification configuration information</span></span>

  - <span data-ttu-id="533c5-118">すべてのプッシュ通知構成設定に関する情報を表示するには、Lync Server 管理シェルで次のコマンドを入力し、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="533c5-118">To view information about all your push notification configuration settings, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsPushNotificationConfiguration
    
    <span data-ttu-id="533c5-119">次のような情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="533c5-119">That will return information similar to this:</span></span>
    
        Identity                               : Global
        EnableApplePushNotificationService     : False
        EnableMicrosoftPushNotificationService : False

</div>

<span data-ttu-id="533c5-120">詳細については、「Get-help」と[いう](https://docs.microsoft.com/powershell/module/skype/Get-CsPushNotificationConfiguration)コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="533c5-120">For more information, see the help topic for the [Get-CsPushNotificationConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsPushNotificationConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="533c5-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="533c5-121">See Also</span></span>


[<span data-ttu-id="533c5-122">Lync Server 2013 でのプッシュ通知の構成</span><span class="sxs-lookup"><span data-stu-id="533c5-122">Configuring for push notifications in Lync Server 2013</span></span>](lync-server-2013-configuring-for-push-notifications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

