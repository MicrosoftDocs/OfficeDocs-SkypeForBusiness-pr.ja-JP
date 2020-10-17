---
title: 'Lync Server 2013: プッシュ通知の構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring for push notifications
ms:assetid: d77f2c06-0fe6-45d5-8f08-808ab871b3e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690047(v=OCS.15)
ms:contentKeyID: 48185574
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4f68cafcfcc616bd6e467514704416f134de3665
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517494"
---
# <a name="configuring-for-push-notifications-in-lync-server-2013"></a><span data-ttu-id="3bce3-102">Lync Server 2013 でのプッシュ通知の構成</span><span class="sxs-lookup"><span data-stu-id="3bce3-102">Configuring for push notifications in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3bce3-103">_**トピックの最終更新日:** 2013-02-12_</span><span class="sxs-lookup"><span data-stu-id="3bce3-103">_**Topic Last Modified:** 2013-02-12_</span></span>

<span data-ttu-id="3bce3-104">プッシュ通知は、バッジ、アイコン、または通知の形式で、モバイルアプリケーションが非アクティブな場合でもモバイルデバイスに送信できます。</span><span class="sxs-lookup"><span data-stu-id="3bce3-104">Push notifications, in the form of badges, icons, or alerts, can be sent to a mobile device even when the mobile application is inactive.</span></span> <span data-ttu-id="3bce3-105">プッシュ通知は、ユーザーに、新規または不在着信の IM 招待状、ボイス メールなどのイベントを通知します。</span><span class="sxs-lookup"><span data-stu-id="3bce3-105">Push notifications notify a user of events such as a new or missed IM invitation and voice mail.</span></span> <span data-ttu-id="3bce3-106">Lync Server 2013 Mobility Service は、クラウドベースの Lync Server プッシュ通知サービスに通知を送信します。これにより、Apple Push Notification Service (APNS)、または Microsoft プッシュ通知サービス (MPNS) (Lync 2010 Mobile または Lync 2013 モバイルクライアントを実行している Windows Phone デバイスの場合) に通知が送信2010されます。</span><span class="sxs-lookup"><span data-stu-id="3bce3-106">The Lync Server 2013 Mobility Service sends the notifications to the cloud-based Lync Server Push Notification Service, which then sends the notifications to the Apple Push Notification Service (APNS) (for an Apple device running the Lync 2010 Mobile client) or the Microsoft Push Notification Service (MPNS) (for a Windows Phone device running the Lync 2010 Mobile or the Lync 2013 Mobile client).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="3bce3-107">Lync 2010 mobile または Lync 2013 Mobile クライアントで Windows Phone を使用する場合、プッシュ通知は重要な考慮事項です。</span><span class="sxs-lookup"><span data-stu-id="3bce3-107">If you use Windows Phone with Lync 2010 Mobile or Lync 2013 Mobile client, push notification is an important consideration.</span></span><BR><span data-ttu-id="3bce3-108">Apple デバイスで Lync 2010 Mobile を使用する場合、プッシュ通知は重要な考慮事項です。</span><span class="sxs-lookup"><span data-stu-id="3bce3-108">If you use Lync 2010 Mobile on Apple devices, push notification is an important consideration.</span></span><BR><span data-ttu-id="3bce3-109">Apple デバイスで Lync 2013 Mobile を使用する場合、プッシュ通知は不要になります。</span><span class="sxs-lookup"><span data-stu-id="3bce3-109">If you use Lync 2013 Mobile on Apple devices, you no longer need push notification.</span></span>



</div>

<span data-ttu-id="3bce3-110">プッシュ通知をサポートするようにトポロジを構成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="3bce3-110">Configure your topology to support push notifications by doing the following:</span></span>

  - <span data-ttu-id="3bce3-111">使用している環境に Lync Server 2010 または Lync Server 2013 エッジサーバーがある場合は、新しいホスティングプロバイダーである Microsoft Lync Online を追加して、組織と Lync Online の間のホスティングプロバイダーフェデレーションを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3bce3-111">If your environment has a Lync Server 2010 or Lync Server 2013 Edge Server, you need to add a new hosting provider, Microsoft Lync Online, and then set up hosting provider federation between your organization and Lync Online.</span></span>

  - <span data-ttu-id="3bce3-112">ご使用の環境に Office Communications Server 2007 R2 エッジサーバーがある場合は、push.lync.com との直接 SIP フェデレーションを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3bce3-112">If your environment has a Office Communications Server 2007 R2 Edge Server, you need to set up direct SIP federation with push.lync.com.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3bce3-113">Push.lync.com は、プッシュ通知サービス用の Microsoft Office 365 ドメインです。</span><span class="sxs-lookup"><span data-stu-id="3bce3-113">Push.lync.com is a Microsoft Office 365 domain for Push Notification Service.</span></span>

    
    </div>

  - <span data-ttu-id="3bce3-114">プッシュ通知を有効にするには、 **Set-Cspの設定** コマンドレットを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3bce3-114">To enable push notifications, you need to run the **Set-CsPushNotificationConfiguration** cmdlet.</span></span> <span data-ttu-id="3bce3-115">既定では、プッシュ通知はオフになっています。</span><span class="sxs-lookup"><span data-stu-id="3bce3-115">By default, push notifications are turned off.</span></span>

  - <span data-ttu-id="3bce3-116">フェデレーション構成とプッシュ通知をテストします。</span><span class="sxs-lookup"><span data-stu-id="3bce3-116">Test the federation configuration and push notifications.</span></span>

<div>

## <a name="to-configure-for-push-notifications-with-lync-server-2013-or-lync-server-2010edge-server"></a><span data-ttu-id="3bce3-117">Lync server 2013 または Lync Server 2010 エッジサーバーでプッシュ通知を構成するには</span><span class="sxs-lookup"><span data-stu-id="3bce3-117">To configure for push notifications with Lync Server 2013 or Lync Server 2010 Edge Server</span></span>

1.  <span data-ttu-id="3bce3-118">Lync Server 管理シェルと Ocscore がインストールされているコンピューターに、RtcUniversalServerAdmins グループのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="3bce3-118">Log on to a computer where Lync Server Management Shell and Ocscore are installed as a member of the RtcUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="3bce3-119">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="3bce3-119">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="3bce3-120">Lync Server online ホスティングプロバイダーを追加します。</span><span class="sxs-lookup"><span data-stu-id="3bce3-120">Add a Lync Server online hosting provider.</span></span> <span data-ttu-id="3bce3-121">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="3bce3-121">At the command line, type:</span></span>
    
        New-CsHostingProvider -Identity <unique identifier for Lync Online hosting provider> -Enabled $True -ProxyFqdn <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
    
    <span data-ttu-id="3bce3-122">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="3bce3-122">For example:</span></span>
    
        New-CsHostingProvider -Identity "LyncOnline" -Enabled $True -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3bce3-123">1つのホスティングプロバイダーとの間に複数のフェデレーション関係を設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="3bce3-123">You cannot have more than one federation relationship with a single hosting provider.</span></span> <span data-ttu-id="3bce3-124">つまり、sipfed.online.lync.com とのフェデレーション関係を持つホスティングプロバイダーを既にセットアップしている場合は、ホスティングプロバイダーの id が Nm-lynconline-w15-long 以外のものであっても、別のホスティングプロバイダーを追加しないでください。</span><span class="sxs-lookup"><span data-stu-id="3bce3-124">That is, if you have already set up a hosting provider that has a federation relationship with sipfed.online.lync.com, do not add another hosting provider for it, even if the identity of the hosting provider is something other than LyncOnline.</span></span>

    
    </div>

4.  <span data-ttu-id="3bce3-125">組織と、Lync Online のプッシュ通知サービスとの間のホスティングプロバイダーフェデレーションを設定します。</span><span class="sxs-lookup"><span data-stu-id="3bce3-125">Set up hosting provider federation between your organization and the Push Notification Service at Lync Online.</span></span> <span data-ttu-id="3bce3-126">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="3bce3-126">At the command line, type:</span></span>
    
        New-CsAllowedDomain -Identity "push.lync.com"

</div>

<div>

## <a name="to-configure-for-push-notifications-with-office-communications-server-2007-r2edge-server"></a><span data-ttu-id="3bce3-127">Office Communications Server 2007 R2 エッジサーバーでプッシュ通知を構成するには</span><span class="sxs-lookup"><span data-stu-id="3bce3-127">To configure for push notifications with Office Communications Server 2007 R2 Edge Server</span></span>

1.  <span data-ttu-id="3bce3-128">RtcUniversalServerAdmins グループのメンバーとしてエッジサーバーにログオンします。</span><span class="sxs-lookup"><span data-stu-id="3bce3-128">Log on to the Edge Server as a member of the RtcUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="3bce3-129">[ **スタート**]、[ **すべてのプログラム**]、[ **管理ツール**]、[ **コンピューターの管理**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="3bce3-129">Click **Start**, click **All Programs**, click **Administrative Tools**, and then click **Computer Management**.</span></span>

3.  <span data-ttu-id="3bce3-130">コンソールツリーで、[ **サービスとアプリケーション**] を展開し、[ **Microsoft Office Communications Server 2007 R2**] を右クリックし、[ **プロパティ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3bce3-130">In the console tree, expand **Services and Applications**, right-click **Microsoft Office Communications Server 2007 R2**, and then click **Properties**.</span></span>

4.  <span data-ttu-id="3bce3-131">[ **許可** ] タブで、[ **追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3bce3-131">On the **Allow** tab, click **Add**.</span></span>

5.  <span data-ttu-id="3bce3-132">[ **フェデレーションパートナーの追加** ] ダイアログボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="3bce3-132">In the **Add Federated Partner** dialog box, do the following:</span></span>
    
      - <span data-ttu-id="3bce3-133">[ **フェデレーションパートナーのドメイン名**] に、「 **push.lync.com**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="3bce3-133">In **Federated partner domain name**, type **push.lync.com**.</span></span>
    
      - <span data-ttu-id="3bce3-134">[ **フェデレーションパートナーのアクセスエッジサーバー**] で、「 **sipfed.online.lync.com**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="3bce3-134">In **Federated partner Access Edge Server**, type **sipfed.online.lync.com**.</span></span>
    
      - <span data-ttu-id="3bce3-135">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3bce3-135">Click **OK**.</span></span>

</div>

<div>

## <a name="to-enable-push-notifications"></a><span data-ttu-id="3bce3-136">プッシュ通知を有効にするには</span><span class="sxs-lookup"><span data-stu-id="3bce3-136">To enable push notifications</span></span>

1.  <span data-ttu-id="3bce3-137">Lync Server 管理シェルと Ocscore がインストールされているコンピューターに CsAdministrator の役割のメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="3bce3-137">Log on to a computer where Lync Server Management Shell and Ocscore are installed as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="3bce3-138">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="3bce3-138">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="3bce3-139">プッシュ通知を有効にします。</span><span class="sxs-lookup"><span data-stu-id="3bce3-139">Enable push notifications.</span></span> <span data-ttu-id="3bce3-140">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="3bce3-140">At the command line, type:</span></span>
    
        Set-CsPushNotificationConfiguration -EnableApplePushNotificationService $True -EnableMicrosoftPushNotificationService $True

4.  <span data-ttu-id="3bce3-141">フェデレーションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="3bce3-141">Enable federation.</span></span> <span data-ttu-id="3bce3-142">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="3bce3-142">At the command line, type:</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

</div>

<div>

## <a name="to-test-federation-and-push-notifications"></a><span data-ttu-id="3bce3-143">フェデレーションとプッシュ通知をテストするには</span><span class="sxs-lookup"><span data-stu-id="3bce3-143">To test federation and push notifications</span></span>

1.  <span data-ttu-id="3bce3-144">Lync Server 管理シェルと Ocscore がインストールされているコンピューターに CsAdministrator の役割のメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="3bce3-144">Log on to a computer where Lync Server Management Shell and Ocscore are installed as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="3bce3-145">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="3bce3-145">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="3bce3-146">フェデレーション構成をテストします。</span><span class="sxs-lookup"><span data-stu-id="3bce3-146">Test the federation configuration.</span></span> <span data-ttu-id="3bce3-147">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="3bce3-147">At the command line, type:</span></span>
    
        Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
    
    <span data-ttu-id="3bce3-148">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="3bce3-148">For example:</span></span>
    
        Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com

4.  <span data-ttu-id="3bce3-149">プッシュ通知をテストします。</span><span class="sxs-lookup"><span data-stu-id="3bce3-149">Test push notifications.</span></span> <span data-ttu-id="3bce3-150">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="3bce3-150">At the command line, type:</span></span>
    
        Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
    
    <span data-ttu-id="3bce3-151">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="3bce3-151">For example:</span></span>
    
        Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3bce3-152">関連項目</span><span class="sxs-lookup"><span data-stu-id="3bce3-152">See Also</span></span>


[<span data-ttu-id="3bce3-153">Test-csfederatedpartner</span><span class="sxs-lookup"><span data-stu-id="3bce3-153">Test-CsFederatedPartner</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner)  
[<span data-ttu-id="3bce3-154">テスト-CsMcxPushNotification</span><span class="sxs-lookup"><span data-stu-id="3bce3-154">Test-CsMcxPushNotification</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxPushNotification)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

