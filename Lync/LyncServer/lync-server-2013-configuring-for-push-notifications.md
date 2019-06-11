---
title: 'Lync Server 2013: プッシュ通知を構成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring for push notifications
ms:assetid: d77f2c06-0fe6-45d5-8f08-808ab871b3e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690047(v=OCS.15)
ms:contentKeyID: 48185574
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 08492aaa6fc8c9fb6569ad6ad642a5cc1157a2ec
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840250"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-for-push-notifications-in-lync-server-2013"></a><span data-ttu-id="38805-102">Lync Server 2013 でプッシュ通知を構成する</span><span class="sxs-lookup"><span data-stu-id="38805-102">Configuring for push notifications in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="38805-103">_**最終更新日:** 2013-02-12_</span><span class="sxs-lookup"><span data-stu-id="38805-103">_**Topic Last Modified:** 2013-02-12_</span></span>

<span data-ttu-id="38805-104">プッシュ通知は、モバイルアプリケーションが非アクティブになっている場合でも、バッジ、アイコン、または通知の形式でモバイルデバイスに送信できます。</span><span class="sxs-lookup"><span data-stu-id="38805-104">Push notifications, in the form of badges, icons, or alerts, can be sent to a mobile device even when the mobile application is inactive.</span></span> <span data-ttu-id="38805-105">プッシュ通知は、新規または不在着信した IM の招待状やボイスメールなどのイベントをユーザーに通知します。</span><span class="sxs-lookup"><span data-stu-id="38805-105">Push notifications notify a user of events such as a new or missed IM invitation and voice mail.</span></span> <span data-ttu-id="38805-106">Lync Server 2013 モビリティサービスは、クラウドベースの Lync Server プッシュ通知サービスに通知を送信します。これにより、通知は Apple プッシュ通知サービス (APNS) (Lync 2010 モバイルクライアントを実行している Apple デバイス) に送信されます。Microsoft プッシュ通知サービス (MPNS) (Lync 2010 モバイルクライアントまたは Lync 2013 クライアントを実行している Windows Phone デバイスの場合)。</span><span class="sxs-lookup"><span data-stu-id="38805-106">The Lync Server 2013 Mobility Service sends the notifications to the cloud-based Lync Server Push Notification Service, which then sends the notifications to the Apple Push Notification Service (APNS) (for an Apple device running the Lync 2010 Mobile client) or the Microsoft Push Notification Service (MPNS) (for a Windows Phone device running the Lync 2010 Mobile or the Lync 2013 Mobile client).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="38805-107">Lync 2010 Mobile または Lync 2013 モバイルクライアントで Windows Phone を使用している場合、プッシュ通知は重要な考慮事項です。</span><span class="sxs-lookup"><span data-stu-id="38805-107">If you use Windows Phone with Lync 2010 Mobile or Lync 2013 Mobile client, push notification is an important consideration.</span></span><BR><span data-ttu-id="38805-108">Apple デバイスで Lync 2010 Mobile を使用している場合、プッシュ通知は重要な考慮事項です。</span><span class="sxs-lookup"><span data-stu-id="38805-108">If you use Lync 2010 Mobile on Apple devices, push notification is an important consideration.</span></span><BR><span data-ttu-id="38805-109">Apple デバイスで Lync 2013 Mobile を使用している場合は、プッシュ通知は不要になります。</span><span class="sxs-lookup"><span data-stu-id="38805-109">If you use Lync 2013 Mobile on Apple devices, you no longer need push notification.</span></span>



</div>

<span data-ttu-id="38805-110">次の操作を実行して、プッシュ通知をサポートするようにトポロジを構成します。</span><span class="sxs-lookup"><span data-stu-id="38805-110">Configure your topology to support push notifications by doing the following:</span></span>

  - <span data-ttu-id="38805-111">使用している環境に Lync Server 2010 または Lync Server 2013 Edge サーバーがある場合は、新しいホスティングプロバイダーである Microsoft Lync Online を追加し、組織と Lync Online の間でホスティングプロバイダーフェデレーションを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="38805-111">If your environment has a Lync Server 2010 or Lync Server 2013 Edge Server, you need to add a new hosting provider, Microsoft Lync Online, and then set up hosting provider federation between your organization and Lync Online.</span></span>

  - <span data-ttu-id="38805-112">使用している環境に Office Communications Server 2007 R2 Edge サーバーがある場合は、push.lync.com との直接 SIP フェデレーションを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="38805-112">If your environment has a Office Communications Server 2007 R2 Edge Server, you need to set up direct SIP federation with push.lync.com.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="38805-113">Push.lync.com は、プッシュ通知サービス用の Microsoft Office 365 ドメインです。</span><span class="sxs-lookup"><span data-stu-id="38805-113">Push.lync.com is a Microsoft Office 365 domain for Push Notification Service.</span></span>

    
    </div>

  - <span data-ttu-id="38805-114">プッシュ通知を有効にするには、 **Set-Cspの設定**コマンドレットを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="38805-114">To enable push notifications, you need to run the **Set-CsPushNotificationConfiguration** cmdlet.</span></span> <span data-ttu-id="38805-115">既定では、プッシュ通知は無効になっています。</span><span class="sxs-lookup"><span data-stu-id="38805-115">By default, push notifications are turned off.</span></span>

  - <span data-ttu-id="38805-116">フェデレーション構成とプッシュ通知をテストします。</span><span class="sxs-lookup"><span data-stu-id="38805-116">Test the federation configuration and push notifications.</span></span>

<div>

## <a name="to-configure-for-push-notifications-with-lync-server-2013-or-lync-server-2010edge-server"></a><span data-ttu-id="38805-117">Lync Server 2013 または Lync Server 2010 エッジサーバーを使用してプッシュ通知を構成するには</span><span class="sxs-lookup"><span data-stu-id="38805-117">To configure for push notifications with Lync Server 2013 or Lync Server 2010 Edge Server</span></span>

1.  <span data-ttu-id="38805-118">Lync Server 管理シェルと Ocscore が RtcUniversalServerAdmins グループのメンバーとしてインストールされているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="38805-118">Log on to a computer where Lync Server Management Shell and Ocscore are installed as a member of the RtcUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="38805-119">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="38805-119">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="38805-120">Lync Server online ホスティングプロバイダーを追加します。</span><span class="sxs-lookup"><span data-stu-id="38805-120">Add a Lync Server online hosting provider.</span></span> <span data-ttu-id="38805-121">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="38805-121">At the command line, type:</span></span>
    
        New-CsHostingProvider -Identity <unique identifier for Lync Online hosting provider> -Enabled $True -ProxyFqdn <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
    
    <span data-ttu-id="38805-122">例:</span><span class="sxs-lookup"><span data-stu-id="38805-122">For example:</span></span>
    
        New-CsHostingProvider -Identity "LyncOnline" -Enabled $True -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="38805-123">1つのホスティングプロバイダーとの間に複数のフェデレーション関係を設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="38805-123">You cannot have more than one federation relationship with a single hosting provider.</span></span> <span data-ttu-id="38805-124">つまり、sipfed.online.lync.com とのフェデレーション関係を持つホスティングプロバイダーを既に設定している場合は、ホスティングプロバイダーの id が LyncOnline 以外のものであっても、別のホスティングプロバイダーを追加しないでください。</span><span class="sxs-lookup"><span data-stu-id="38805-124">That is, if you have already set up a hosting provider that has a federation relationship with sipfed.online.lync.com, do not add another hosting provider for it, even if the identity of the hosting provider is something other than LyncOnline.</span></span>

    
    </div>

4.  <span data-ttu-id="38805-125">組織と Lync Online のプッシュ通知サービス間のホスティングプロバイダーフェデレーションをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="38805-125">Set up hosting provider federation between your organization and the Push Notification Service at Lync Online.</span></span> <span data-ttu-id="38805-126">コマンド ラインで次を入力します。</span><span class="sxs-lookup"><span data-stu-id="38805-126">At the command line, type:</span></span>
    
        New-CsAllowedDomain -Identity "push.lync.com"

</div>

<div>

## <a name="to-configure-for-push-notifications-with-office-communications-server-2007-r2edge-server"></a><span data-ttu-id="38805-127">Office Communications Server 2007 R2 Edge サーバーでのプッシュ通知を構成するには</span><span class="sxs-lookup"><span data-stu-id="38805-127">To configure for push notifications with Office Communications Server 2007 R2 Edge Server</span></span>

1.  <span data-ttu-id="38805-128">RtcUniversalServerAdmins グループのメンバーとしてエッジサーバーにログオンします。</span><span class="sxs-lookup"><span data-stu-id="38805-128">Log on to the Edge Server as a member of the RtcUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="38805-129">[**スタート**] をクリックし、[**すべてのプログラム**]、[**管理ツール**]、[**コンピューターの管理**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="38805-129">Click **Start**, click **All Programs**, click **Administrative Tools**, and then click **Computer Management**.</span></span>

3.  <span data-ttu-id="38805-130">コンソールツリーで、[**サービスとアプリケーション**] を展開し、[ **Microsoft Office Communications Server 2007 R2**] を右クリックして、[**プロパティ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="38805-130">In the console tree, expand **Services and Applications**, right-click **Microsoft Office Communications Server 2007 R2**, and then click **Properties**.</span></span>

4.  <span data-ttu-id="38805-131">[**許可**] タブの [**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="38805-131">On the **Allow** tab, click **Add**.</span></span>

5.  <span data-ttu-id="38805-132">[**フェデレーションパートナーの追加**] ダイアログボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="38805-132">In the **Add Federated Partner** dialog box, do the following:</span></span>
    
      - <span data-ttu-id="38805-133">[**フェデレーションパートナーのドメイン名**] に「 **push.lync.com**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="38805-133">In **Federated partner domain name**, type **push.lync.com**.</span></span>
    
      - <span data-ttu-id="38805-134">**フェデレーションパートナーのアクセスエッジサーバー**で、「 **sipfed.online.lync.com**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="38805-134">In **Federated partner Access Edge Server**, type **sipfed.online.lync.com**.</span></span>
    
      - <span data-ttu-id="38805-135">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="38805-135">Click **OK**.</span></span>

</div>

<div>

## <a name="to-enable-push-notifications"></a><span data-ttu-id="38805-136">プッシュ通知を有効にするには</span><span class="sxs-lookup"><span data-stu-id="38805-136">To enable push notifications</span></span>

1.  <span data-ttu-id="38805-137">Lync Server 管理シェルと Ocscore が CsAdministrator ロールのメンバーとしてインストールされているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="38805-137">Log on to a computer where Lync Server Management Shell and Ocscore are installed as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="38805-138">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="38805-138">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="38805-139">プッシュ通知を有効にします。</span><span class="sxs-lookup"><span data-stu-id="38805-139">Enable push notifications.</span></span> <span data-ttu-id="38805-140">コマンド ラインで次を入力します。</span><span class="sxs-lookup"><span data-stu-id="38805-140">At the command line, type:</span></span>
    
        Set-CsPushNotificationConfiguration -EnableApplePushNotificationService $True -EnableMicrosoftPushNotificationService $True

4.  <span data-ttu-id="38805-141">フェデレーションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="38805-141">Enable federation.</span></span> <span data-ttu-id="38805-142">コマンド ラインで次を入力します。</span><span class="sxs-lookup"><span data-stu-id="38805-142">At the command line, type:</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

</div>

<div>

## <a name="to-test-federation-and-push-notifications"></a><span data-ttu-id="38805-143">フェデレーションとプッシュ通知をテストするには</span><span class="sxs-lookup"><span data-stu-id="38805-143">To test federation and push notifications</span></span>

1.  <span data-ttu-id="38805-144">Lync Server 管理シェルと Ocscore が CsAdministrator ロールのメンバーとしてインストールされているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="38805-144">Log on to a computer where Lync Server Management Shell and Ocscore are installed as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="38805-145">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="38805-145">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="38805-146">フェデレーション構成をテストします。</span><span class="sxs-lookup"><span data-stu-id="38805-146">Test the federation configuration.</span></span> <span data-ttu-id="38805-147">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="38805-147">At the command line, type:</span></span>
    
        Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
    
    <span data-ttu-id="38805-148">例:</span><span class="sxs-lookup"><span data-stu-id="38805-148">For example:</span></span>
    
        Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com

4.  <span data-ttu-id="38805-149">プッシュ通知をテストします。</span><span class="sxs-lookup"><span data-stu-id="38805-149">Test push notifications.</span></span> <span data-ttu-id="38805-150">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="38805-150">At the command line, type:</span></span>
    
        Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
    
    <span data-ttu-id="38805-151">例:</span><span class="sxs-lookup"><span data-stu-id="38805-151">For example:</span></span>
    
        Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="38805-152">関連項目</span><span class="sxs-lookup"><span data-stu-id="38805-152">See Also</span></span>


[<span data-ttu-id="38805-153">テスト-CsFederatedPartner</span><span class="sxs-lookup"><span data-stu-id="38805-153">Test-CsFederatedPartner</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner)  
[<span data-ttu-id="38805-154">テスト-CsMcxPushNotification</span><span class="sxs-lookup"><span data-stu-id="38805-154">Test-CsMcxPushNotification</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxPushNotification)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

