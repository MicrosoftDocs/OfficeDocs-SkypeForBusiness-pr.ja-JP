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

# <a name="enabling-or-disabling-push-notifications-for-iphones-in-lync-server-2013"></a><span data-ttu-id="f22a6-102">Lync Server 2013 での iPhones のプッシュ通知を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="f22a6-102">Enabling or disabling push notifications for iPhones in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f22a6-103">_**最終更新日:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="f22a6-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="f22a6-104">プッシュ通知は、モバイルアプリケーションが非アクティブになっている場合でも、バッジ、アイコン、または通知の形式で、iPhone に送信できます。</span><span class="sxs-lookup"><span data-stu-id="f22a6-104">Push notifications, in the form of badges, icons, or alerts, can be sent to an iPhone even when the mobile application is inactive.</span></span> <span data-ttu-id="f22a6-105">プッシュ通知は、新規または不在着信した IM の招待状やボイスメールなどのイベントをユーザーに通知します。</span><span class="sxs-lookup"><span data-stu-id="f22a6-105">Push notifications notify a user of events such as a new or missed IM invitation and voice mail.</span></span> <span data-ttu-id="f22a6-106">IPhone のプッシュ通知を有効または無効にするには、Lync Server 2013 コントロールパネルまたは Lync Server 2013 Management Shell を使用します。</span><span class="sxs-lookup"><span data-stu-id="f22a6-106">You can enable or disable push notifications for iPhone by using either Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-enable-push-notifications-for-iphone-by-using-lync-server-control-panel"></a><span data-ttu-id="f22a6-107">Lync Server コントロールパネルを使用して iPhone のプッシュ通知を有効にするには</span><span class="sxs-lookup"><span data-stu-id="f22a6-107">To enable push notifications for iPhone by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="f22a6-108">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="f22a6-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f22a6-109">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="f22a6-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f22a6-110">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f22a6-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f22a6-111">左側のナビゲーションバーで、[**クライアント**] をクリックし、[**プッシュ通知の構成**] ナビゲーションボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="f22a6-111">In the left navigation bar, click **Clients**, and then click the **Push Notification Configuration** navigation button.</span></span>

4.  <span data-ttu-id="f22a6-112">[**プッシュ通知の構成**] ページで、編集するサイトをクリックし、[**編集**] メニューをクリックして、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f22a6-112">On the **Push Notification Configuration** page, click the site you want to edit, click the **Edit** menu, and then click **Show details**.</span></span>

5.  <span data-ttu-id="f22a6-113">[ **Apple プッシュ通知を有効にする**] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="f22a6-113">Click the **Enable Apple push notifications** checkbox.</span></span>

6.  <span data-ttu-id="f22a6-114">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f22a6-114">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-disable-push-notifications-for-iphone-by-using-lync-server-control-panel"></a><span data-ttu-id="f22a6-115">Lync Server コントロールパネルを使用して iPhone のプッシュ通知を無効にするには</span><span class="sxs-lookup"><span data-stu-id="f22a6-115">To disable push notifications for iPhone by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="f22a6-116">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="f22a6-116">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f22a6-117">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="f22a6-117">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f22a6-118">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f22a6-118">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f22a6-119">左側のナビゲーションバーで、[**クライアント**] をクリックし、[**プッシュ通知の構成**] ナビゲーションボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="f22a6-119">In the left navigation bar, click **Clients**, and then click the **Push Notification Configuration** navigation button.</span></span>

4.  <span data-ttu-id="f22a6-120">[**プッシュ通知の構成**] ページで、編集するサイトをクリックし、[**編集**] メニューをクリックして、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f22a6-120">On the **Push Notification Configuration** page, click the site you want to edit, click the **Edit** menu, and then click **Show details**.</span></span>

5.  <span data-ttu-id="f22a6-121">[ **Apple プッシュ通知を有効にする**] チェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="f22a6-121">Clear the **Enable Apple push notifications** checkbox.</span></span>

6.  <span data-ttu-id="f22a6-122">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f22a6-122">Click **Commit**.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-push-notifications-to-iphone-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="f22a6-123">Windows PowerShell コマンドレットを使用して、iPhone へのプッシュ通知を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="f22a6-123">Enabling or Disabling Push Notifications to iPhone by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="f22a6-124">Apple iPhone へのプッシュ通知を有効または無効にするには、 **Set-csp・の設定**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="f22a6-124">Push notifications to Apple iPhone can be enabled or disabled by using the **Set-CsPushNotificationConfiguration** cmdlet.</span></span> <span data-ttu-id="f22a6-125">このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="f22a6-125">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="f22a6-126">リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、「Lync Server Windows PowerShell のブログ記事」を参照してください[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。「リモート PowerShell を使用して Microsoft Lync Server 2010 を管理する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f22a6-126">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-push-notifications-for-iphone"></a><span data-ttu-id="f22a6-127">IPhone でプッシュ通知を有効にするには</span><span class="sxs-lookup"><span data-stu-id="f22a6-127">To enable push notifications for iPhone</span></span>

  - <span data-ttu-id="f22a6-128">IPhone でプッシュ通知を有効にするには、EnableApplePushNotificationService プロパティの値を True ($True) に設定します。</span><span class="sxs-lookup"><span data-stu-id="f22a6-128">To enable push notifications for iPhone set the value of the EnableApplePushNotificationService property to True ($True).</span></span> <span data-ttu-id="f22a6-129">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="f22a6-129">For example:</span></span>
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableApplePushNotificationService $True

</div>

<div>

## <a name="to-disable-push-notifications-for-iphone"></a><span data-ttu-id="f22a6-130">IPhone のプッシュ通知を無効にするには</span><span class="sxs-lookup"><span data-stu-id="f22a6-130">To disable push notifications for iPhone</span></span>

  - <span data-ttu-id="f22a6-131">IPhone のプッシュ通知を無効にするには、EnableApplePushNotificationService プロパティの値を False ($False) に設定します。</span><span class="sxs-lookup"><span data-stu-id="f22a6-131">To disable push notifications for iPhone set the value of the EnableApplePushNotificationService property to False ($False).</span></span> <span data-ttu-id="f22a6-132">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="f22a6-132">For example:</span></span>
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableApplePushNotificationService $False

</div>

<span data-ttu-id="f22a6-133">詳細については、「 [Set-cspの設定](https://docs.microsoft.com/powershell/module/skype/Set-CsPushNotificationConfiguration)」の「ヘルプ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f22a6-133">For more information, see the help topic for the [Set-CsPushNotificationConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPushNotificationConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f22a6-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="f22a6-134">See Also</span></span>


[<span data-ttu-id="f22a6-135">Lync Server 2013 でプッシュ通知を構成する</span><span class="sxs-lookup"><span data-stu-id="f22a6-135">Configuring for push notifications in Lync Server 2013</span></span>](lync-server-2013-configuring-for-push-notifications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

