---
title: 'Lync Server 2013: iPhones のプッシュ通知の有効化または無効化'
description: 'Lync Server 2013: iPhones のプッシュ通知の有効化または無効化。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling or disabling push notifications for iPhones
ms:assetid: 8bbf531a-807f-4a8f-814a-94bfed8f97ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688122(v=OCS.15)
ms:contentKeyID: 49733719
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 07a9c5ec442c3628455797b987d8b2f22677e70e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546503"
---
# <a name="enabling-or-disabling-push-notifications-for-iphones-in-lync-server-2013"></a><span data-ttu-id="5dd6f-103">Lync Server 2013 での iPhones のプッシュ通知の有効化または無効化</span><span class="sxs-lookup"><span data-stu-id="5dd6f-103">Enabling or disabling push notifications for iPhones in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5dd6f-104">_**トピックの最終更新日:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="5dd6f-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="5dd6f-105">プッシュ通知は、バッジ、アイコン、または通知の形式で、モバイルアプリケーションが非アクティブな場合でも、iPhone に送信できます。</span><span class="sxs-lookup"><span data-stu-id="5dd6f-105">Push notifications, in the form of badges, icons, or alerts, can be sent to an iPhone even when the mobile application is inactive.</span></span> <span data-ttu-id="5dd6f-106">プッシュ通知は、ユーザーに、新規または不在着信の IM 招待状、ボイス メールなどのイベントを通知します。</span><span class="sxs-lookup"><span data-stu-id="5dd6f-106">Push notifications notify a user of events such as a new or missed IM invitation and voice mail.</span></span> <span data-ttu-id="5dd6f-107">IPhone のプッシュ通知を有効または無効にするには、Lync Server 2013 コントロールパネルまたは Lync Server 2013 管理シェルを使用します。</span><span class="sxs-lookup"><span data-stu-id="5dd6f-107">You can enable or disable push notifications for iPhone by using either Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-enable-push-notifications-for-iphone-by-using-lync-server-control-panel"></a><span data-ttu-id="5dd6f-108">Lync Server コントロールパネルを使用して、iPhone のプッシュ通知を有効にするには</span><span class="sxs-lookup"><span data-stu-id="5dd6f-108">To enable push notifications for iPhone by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="5dd6f-109">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="5dd6f-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="5dd6f-110">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="5dd6f-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="5dd6f-111">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5dd6f-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="5dd6f-112">左側のナビゲーション バーで [**クライアント**] をクリックし、[**プッシュ通知構成**] ナビゲーション ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="5dd6f-112">In the left navigation bar, click **Clients**, and then click the **Push Notification Configuration** navigation button.</span></span>

4.  <span data-ttu-id="5dd6f-113">[ **プッシュ通知の構成** ] ページで、編集するサイトをクリックし、[ **編集** ] メニューをクリックして、[ **詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5dd6f-113">On the **Push Notification Configuration** page, click the site you want to edit, click the **Edit** menu, and then click **Show details**.</span></span>

5.  <span data-ttu-id="5dd6f-114">[**Apple Push 通知を有効にする**] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="5dd6f-114">Click the **Enable Apple push notifications** checkbox.</span></span>

6.  <span data-ttu-id="5dd6f-115">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5dd6f-115">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-disable-push-notifications-for-iphone-by-using-lync-server-control-panel"></a><span data-ttu-id="5dd6f-116">Lync Server コントロールパネルを使用して、iPhone のプッシュ通知を無効にするには</span><span class="sxs-lookup"><span data-stu-id="5dd6f-116">To disable push notifications for iPhone by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="5dd6f-117">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="5dd6f-117">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="5dd6f-118">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="5dd6f-118">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="5dd6f-119">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5dd6f-119">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="5dd6f-120">左側のナビゲーション バーで [**クライアント**] をクリックし、[**プッシュ通知構成**] ナビゲーション ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="5dd6f-120">In the left navigation bar, click **Clients**, and then click the **Push Notification Configuration** navigation button.</span></span>

4.  <span data-ttu-id="5dd6f-121">[ **プッシュ通知の構成** ] ページで、編集するサイトをクリックし、[ **編集** ] メニューをクリックして、[ **詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5dd6f-121">On the **Push Notification Configuration** page, click the site you want to edit, click the **Edit** menu, and then click **Show details**.</span></span>

5.  <span data-ttu-id="5dd6f-122">[**Apple Push 通知を有効にする**] チェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="5dd6f-122">Clear the **Enable Apple push notifications** checkbox.</span></span>

6.  <span data-ttu-id="5dd6f-123">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5dd6f-123">Click **Commit**.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-push-notifications-to-iphone-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="5dd6f-124">Windows PowerShell コマンドレットを使用して、iPhone へのプッシュ通知を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="5dd6f-124">Enabling or Disabling Push Notifications to iPhone by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="5dd6f-125">Apple iPhone へのプッシュ通知を有効または無効にするには、 **Set-Cspの設定** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="5dd6f-125">Push notifications to Apple iPhone can be enabled or disabled by using the **Set-CsPushNotificationConfiguration** cmdlet.</span></span> <span data-ttu-id="5dd6f-126">このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="5dd6f-126">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="5dd6f-127">リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。</span><span class="sxs-lookup"><span data-stu-id="5dd6f-127">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-push-notifications-for-iphone"></a><span data-ttu-id="5dd6f-128">IPhone のプッシュ通知を有効にするには</span><span class="sxs-lookup"><span data-stu-id="5dd6f-128">To enable push notifications for iPhone</span></span>

  - <span data-ttu-id="5dd6f-129">IPhone のプッシュ通知を有効にするには、EnableApplePushNotificationService プロパティの値を True ($True) に設定します。</span><span class="sxs-lookup"><span data-stu-id="5dd6f-129">To enable push notifications for iPhone set the value of the EnableApplePushNotificationService property to True ($True).</span></span> <span data-ttu-id="5dd6f-130">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="5dd6f-130">For example:</span></span>
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableApplePushNotificationService $True

</div>

<div>

## <a name="to-disable-push-notifications-for-iphone"></a><span data-ttu-id="5dd6f-131">IPhone のプッシュ通知を無効にするには</span><span class="sxs-lookup"><span data-stu-id="5dd6f-131">To disable push notifications for iPhone</span></span>

  - <span data-ttu-id="5dd6f-132">IPhone のプッシュ通知を無効にするには、EnableApplePushNotificationService プロパティの値を False ($False) に設定します。</span><span class="sxs-lookup"><span data-stu-id="5dd6f-132">To disable push notifications for iPhone set the value of the EnableApplePushNotificationService property to False ($False).</span></span> <span data-ttu-id="5dd6f-133">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="5dd6f-133">For example:</span></span>
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableApplePushNotificationService $False

</div>

<span data-ttu-id="5dd6f-134">詳細については、[Set-CsPushNotificationConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPushNotificationConfiguration) コマンドレットのヘルプ トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5dd6f-134">For more information, see the help topic for the [Set-CsPushNotificationConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPushNotificationConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5dd6f-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="5dd6f-135">See Also</span></span>


[<span data-ttu-id="5dd6f-136">Lync Server 2013 でのプッシュ通知の構成</span><span class="sxs-lookup"><span data-stu-id="5dd6f-136">Configuring for push notifications in Lync Server 2013</span></span>](lync-server-2013-configuring-for-push-notifications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

