---
title: 'Lync Server 2013: Windows Phone のプッシュ通知を有効または無効にする'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling or disabling push notifications for Windows Phones
ms:assetid: a34f0c5c-4228-40e3-9d93-bc0b5df4895d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688162(v=OCS.15)
ms:contentKeyID: 49733767
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d1b4c8f1f86fa1456230ad4695de0f5b8c56d406
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735634"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-or-disabling-push-notifications-for-windows-phones-in-lync-server-2013"></a><span data-ttu-id="e0794-102">Lync Server 2013 での Windows Phone のプッシュ通知を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="e0794-102">Enabling or disabling push notifications for Windows Phones in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e0794-103">_**トピックの最終更新日:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="e0794-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="e0794-104">プッシュ通知は、モバイルアプリケーションが非アクティブになっている場合でも、バッジ、アイコン、または警告の形式で Windows Phone に送信できます。</span><span class="sxs-lookup"><span data-stu-id="e0794-104">Push notifications, in the form of badges, icons, or alerts, can be sent to a Windows Phone even when the mobile application is inactive.</span></span> <span data-ttu-id="e0794-105">プッシュ通知は、新規または不在着信した IM の招待状やボイスメールなどのイベントをユーザーに通知します。</span><span class="sxs-lookup"><span data-stu-id="e0794-105">Push notifications notify a user of events such as a new or missed IM invitation and voice mail.</span></span> <span data-ttu-id="e0794-106">Windows Phone デバイスのプッシュ通知を有効または無効にするには、Lync Server 2013 コントロールパネルまたは Lync Server 2013 Management Shell を使用します。</span><span class="sxs-lookup"><span data-stu-id="e0794-106">You can enable or disable push notifications for Windows Phone devices by using either Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-enable-push-notifications-for-windows-phone-by-using-lync-server-control-panel"></a><span data-ttu-id="e0794-107">Lync Server コントロールパネルを使用して Windows Phone のプッシュ通知を有効にするには</span><span class="sxs-lookup"><span data-stu-id="e0794-107">To enable push notifications for Windows Phone by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="e0794-108">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="e0794-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e0794-109">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="e0794-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e0794-110">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e0794-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e0794-111">左側のナビゲーションバーで、[**クライアント**] をクリックし、[**プッシュ通知の構成**] ナビゲーションボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e0794-111">In the left navigation bar, click **Clients**, and then click the **Push Notification Configuration** navigation button.</span></span>

4.  <span data-ttu-id="e0794-112">[**プッシュ通知の構成**] ページで、編集するサイトをクリックし、[**編集**] メニューをクリックして、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e0794-112">On the **Push Notification Configuration** page, click the site you want to edit, click the **Edit** menu, and then click **Show details**.</span></span>

5.  <span data-ttu-id="e0794-113">[ **Microsoft プッシュ通知を有効にする**] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="e0794-113">Click the **Enable Microsoft push notifications** checkbox.</span></span>

6.  <span data-ttu-id="e0794-114">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e0794-114">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-disable-push-notifications-for-windows-phone-by-using-lync-server-control-panel"></a><span data-ttu-id="e0794-115">Lync Server コントロールパネルを使用して Windows Phone のプッシュ通知を無効にするには</span><span class="sxs-lookup"><span data-stu-id="e0794-115">To disable push notifications for Windows Phone by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="e0794-116">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="e0794-116">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e0794-117">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="e0794-117">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e0794-118">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e0794-118">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e0794-119">左側のナビゲーションバーで、[**クライアント**] をクリックし、[**プッシュ通知の構成**] ナビゲーションボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e0794-119">In the left navigation bar, click **Clients**, and then click the **Push Notification Configuration** navigation button.</span></span>

4.  <span data-ttu-id="e0794-120">[**プッシュ通知の構成**] ページで、編集するサイトをクリックし、[**編集**] メニューをクリックして、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e0794-120">On the **Push Notification Configuration** page, click the site you want to edit, click the **Edit** menu, and then click **Show details**.</span></span>

5.  <span data-ttu-id="e0794-121">[ **Microsoft プッシュ通知を有効にする**] チェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="e0794-121">Clear the **Enable Microsoft push notifications** checkbox.</span></span>

6.  <span data-ttu-id="e0794-122">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e0794-122">Click **Commit**.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-push-notifications-for-windows-phone-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="e0794-123">Windows PowerShell コマンドレットを使用して、Windows Phone のプッシュ通知を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="e0794-123">Enabling or Disabling Push Notifications for Windows Phone by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="e0794-124">Windows Phone のプッシュ通知を有効または無効にするには、 **Set-csp・の設定**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="e0794-124">You can enable or disable push notifications for Windows Phone by using the **Set-CsPushNotificationConfiguration** cmdlet.</span></span> <span data-ttu-id="e0794-125">このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="e0794-125">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="e0794-126">リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。</span><span class="sxs-lookup"><span data-stu-id="e0794-126">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-push-notifications-for-windows-phone"></a><span data-ttu-id="e0794-127">Windows Phone のプッシュ通知を有効にするには</span><span class="sxs-lookup"><span data-stu-id="e0794-127">To enable push notifications for Windows Phone</span></span>

  - <span data-ttu-id="e0794-128">Windows Phone のプッシュ通知を有効にするには、EnableMicrosoftPushNotificationService プロパティの値を True ($True) に設定します。</span><span class="sxs-lookup"><span data-stu-id="e0794-128">To enable push notifications for Windows Phone set the value of the EnableMicrosoftPushNotificationService property to True ($True).</span></span> <span data-ttu-id="e0794-129">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="e0794-129">For example:</span></span>
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableMicrosoftPushNotificationService $True

</div>

<div>

## <a name="to-disable-push-notifications-for-windows-phone"></a><span data-ttu-id="e0794-130">Windows Phone のプッシュ通知を無効にするには</span><span class="sxs-lookup"><span data-stu-id="e0794-130">To disable push notifications for Windows Phone</span></span>

  - <span data-ttu-id="e0794-131">Windows Phone のプッシュ通知を無効にするには、EnableMicrosoftPushNotificationService プロパティの値を False ($False) に設定します。</span><span class="sxs-lookup"><span data-stu-id="e0794-131">To disable push notifications for Windows Phone set the value of the EnableMicrosoftPushNotificationService property to False ($False).</span></span> <span data-ttu-id="e0794-132">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="e0794-132">For example:</span></span>
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableMicrosoftPushNotificationService $False

</div>

<span data-ttu-id="e0794-133">詳細については、「 [Set-cspの設定](https://docs.microsoft.com/powershell/module/skype/Set-CsPushNotificationConfiguration)」の「ヘルプ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e0794-133">For more information, see the help topic for the [Set-CsPushNotificationConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPushNotificationConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e0794-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="e0794-134">See Also</span></span>


[<span data-ttu-id="e0794-135">Lync Server 2013 でプッシュ通知を構成する</span><span class="sxs-lookup"><span data-stu-id="e0794-135">Configuring for push notifications in Lync Server 2013</span></span>](lync-server-2013-configuring-for-push-notifications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

