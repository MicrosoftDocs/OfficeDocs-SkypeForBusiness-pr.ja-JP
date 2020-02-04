---
title: 'Lync Server 2013: モビリティの要件の定義'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your mobility requirements
ms:assetid: b7608335-cdeb-4aae-8e4b-d80c55f0d62b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690039(v=OCS.15)
ms:contentKeyID: 48185226
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2721f88ce703fe4c26fbc7a9a6cd02cdde6b14a8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762755"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-mobility-requirements-for-lync-server-2013"></a><span data-ttu-id="5d7ca-102">Lync Server 2013 でのモビリティの要件の定義</span><span class="sxs-lookup"><span data-stu-id="5d7ca-102">Defining your mobility requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5d7ca-103">_**最終更新日:** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="5d7ca-103">_**Topic Last Modified:** 2013-02-14_</span></span>

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="5d7ca-104">Lync 2010 Mobile および Lync 2013 モバイルクライアントを使用している場合、Lync Server 2013 のモバイル機能の計画フェーズでは、展開の手順を決定する意思決定を行います。</span><span class="sxs-lookup"><span data-stu-id="5d7ca-104">During the planning phase for the Lync Server 2013 mobility feature, when you are using Lync 2010 Mobile and Lync 2013 Mobile clients, you make decisions that determine your deployment steps.</span></span>

<span data-ttu-id="5d7ca-105">考慮する必要がある決定事項は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5d7ca-105">Here are the decisions that you must consider:</span></span>

  - <span data-ttu-id="5d7ca-106">**Lync モバイルクライアントの自動検出を使用しますか?**</span><span class="sxs-lookup"><span data-stu-id="5d7ca-106">**Do you want to use automatic discovery for Lync mobile clients?**</span></span>
    
    <span data-ttu-id="5d7ca-107">自動検出をサポートする必要がある場合は、新しい内部および外部ドメインネームシステム (DNS) レコードを作成し、フロントエンドサーバー、ディレクター、リバースプロキシ上の証明書にサブジェクトの代替名を追加して、既存の公開ルールを変更する必要があります。リバースプロキシ。</span><span class="sxs-lookup"><span data-stu-id="5d7ca-107">If you want to support automatic discovery, you need to create new internal and external Domain Name System (DNS) records, add subject alternative names to certificates on the Front End Servers, Directors, and reverse proxy, and modify the existing publishing rules on the reverse proxy.</span></span> <span data-ttu-id="5d7ca-108">詳細については、「 [Lync Server 2013 でのモビリティの技術要件](lync-server-2013-technical-requirements-for-mobility.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d7ca-108">For details, see [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span></span> <span data-ttu-id="5d7ca-109">自動検出を使用すると、ユーザーは、モバイルデバイスの設定で Url を入力しなくても、企業ネットワークの内外の任意の場所から Lync Server 2013 Web サービスを自動的に見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="5d7ca-109">With automatic discovery, users can automatically locate Lync Server 2013 Web Services from anywhere inside or outside the corporate network, without entering URLs in their mobile device settings.</span></span>
    
    <span data-ttu-id="5d7ca-110">自動検出の代わりに手動の設定を使用する場合、モバイルユーザーは、モバイルデバイスに次の Url を手動で入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d7ca-110">If you use manual settings instead of automatic discovery, mobile users need to manually enter the following URLs in their mobile devices:</span></span>
    
      - <span data-ttu-id="5d7ca-111">外部\<アクセス用の\>Https://extpoolfqdn/Autodiscover/autodiscoverservice.svc/Root</span><span class="sxs-lookup"><span data-stu-id="5d7ca-111">https://\<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.svc/Root for external access</span></span>
    
      - <span data-ttu-id="5d7ca-112">https://\<intpoolfqdn\>/AutoDiscover/autodiscoverservice、内部アクセス用のルート</span><span class="sxs-lookup"><span data-stu-id="5d7ca-112">https://\<IntPoolFQDN\>/AutoDiscover/ autodiscoverservice.svc/Root for internal access</span></span>
    
    <span data-ttu-id="5d7ca-113">自動検出を使用することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5d7ca-113">We strongly recommend using automatic discovery.</span></span> <span data-ttu-id="5d7ca-114">手動設定の主な用途は、トラブルシューティングです。</span><span class="sxs-lookup"><span data-stu-id="5d7ca-114">The primary use of manual settings is for troubleshooting.</span></span>

  - <span data-ttu-id="5d7ca-115">**自動検出をサポートすることにした場合、リバースプロキシの証明書を各 SIP ドメインのサブジェクト別の名前を使用して更新する必要がありますか?**</span><span class="sxs-lookup"><span data-stu-id="5d7ca-115">**If you decide to support automatic discovery, are you willing to update certificates on the reverse proxy with subject alternative names for each SIP domain?**</span></span>
    
    <span data-ttu-id="5d7ca-116">SIP ドメインが多い場合は、リバースプロキシのパブリック証明書を更新すると非常にコストがかかることがあります。</span><span class="sxs-lookup"><span data-stu-id="5d7ca-116">If you have many SIP domains, updating public certificates on the reverse proxy can become very expensive.</span></span> <span data-ttu-id="5d7ca-117">この場合は、自動検出を実装して、HTTPS をポート443で使う代わりに、最初の自動検出サービス要求でポート80に対して HTTP を使うようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="5d7ca-117">If this is the case, you can choose to implement automatic discovery so that the initial Autodiscover Service request uses HTTP on port 80, instead of using HTTPS on port 443.</span></span> <span data-ttu-id="5d7ca-118">ただし、この方法はお勧めできません。</span><span class="sxs-lookup"><span data-stu-id="5d7ca-118">However, this is not the recommended approach.</span></span> <span data-ttu-id="5d7ca-119">この代替を選択する場合は、リバースプロキシで証明書を更新する必要はありませんが、HTTP 用の web 公開ルールは、ポート80で作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d7ca-119">If you decide to choose this alternative, you do not need to update the certificates on the reverse proxy, but you need to create a web publishing rule for HTTP on port 80.</span></span> <span data-ttu-id="5d7ca-120">詳細については、「 [Lync Server 2013 でのモビリティの技術要件](lync-server-2013-technical-requirements-for-mobility.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d7ca-120">For more details, see [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span></span>

  - <span data-ttu-id="5d7ca-121">**企業ネットワークの内部と外部の両方の Lync モバイルクライアントをサポートしますか。または企業ネットワーク内でのみサポートされているクライアントをサポートしますか?**</span><span class="sxs-lookup"><span data-stu-id="5d7ca-121">**Do you want to support Lync mobile clients both internal and external to the corporate network, or support clients only inside the corporate network?**</span></span>
    
    <span data-ttu-id="5d7ca-122">ネットワークの内部と外部のモバイルクライアントをサポートしたい場合、モバイルデバイスはどこからでもモビリティ機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="5d7ca-122">If you want to support mobile clients internal and external to your network, mobile devices can access mobility features from any location.</span></span> <span data-ttu-id="5d7ca-123">既定の構成では、社内ネットワークと社外のクライアントの両方をサポートします。</span><span class="sxs-lookup"><span data-stu-id="5d7ca-123">The default configuration is to support clients both internal and external to the corporate network.</span></span>
    
    <span data-ttu-id="5d7ca-124">既定の構成では、モバイルクライアントトラフィックが外部サイトを通過できるようになりますが、モバイルクライアントトラフィックを内部の企業ネットワークに制限することができます。</span><span class="sxs-lookup"><span data-stu-id="5d7ca-124">Although the default configuration enables mobile client traffic to go through the external site, you can restrict mobile client traffic to the internal corporate network.</span></span> <span data-ttu-id="5d7ca-125">内部ネットワークへのトラフィックを制限すると、ユーザーは、ネットワーク内にいるときにのみ、モバイルデバイスで Lync モバイルアプリケーションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="5d7ca-125">When you restrict the traffic to the internal network, users can use Lync mobile applications on their mobile devices only when they are inside the network.</span></span>
    
    <span data-ttu-id="5d7ca-126">Mcx mobility service と Lync 2010 Mobile を使ったモビリティをサポートする展開の場合は、 **Set-CsMcxConfiguration**コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="5d7ca-126">For deployments that support mobility using the Mcx mobility service and Lync 2010 Mobile, you run the **Set-CsMcxConfiguration** cmdlet.</span></span> <span data-ttu-id="5d7ca-127">内部使用のためだけにモバイル機能を設定するには、次のようなコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="5d7ca-127">To set mobility for internal use only, you would use a command similar to the following:</span></span>
    
        Set-CsMcxConfiguration -Identity site:Redmond -ExposedWebURL Internal
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5d7ca-128">UCWA には、その他の構成は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="5d7ca-128">There are no additional configurations required for UCWA.</span></span> <span data-ttu-id="5d7ca-129">UCWA には、相当する内部専用構成がありません。</span><span class="sxs-lookup"><span data-stu-id="5d7ca-129">UCWA does not have an equivalent internal-only configuration.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="5d7ca-130">Lync Server&nbsp;2013 フロントエンドサーバーまたはフロントエンドプールを使用してい<STRONG></STRONG>て、Lync Server 2010&nbsp;フロントエンドサーバーまたはフロントエンドプールを使っていない場合は、 <STRONG>cookie ベースの常設は必要ありませ</STRONG>ん。</span><span class="sxs-lookup"><span data-stu-id="5d7ca-130">If you are using a Lync Server 2013&nbsp;Front End Server or Front End pools and <STRONG>you do not have</STRONG> any Lync Server 2010&nbsp;Front End Servers or Front End pools, <STRONG>there is no requirement for cookie-based persistence</STRONG>.</span></span> <span data-ttu-id="5d7ca-131">Lync Server 2010&nbsp;フロントエンドサーバーまたはフロントエンドプールを保持する必要がある場合は、依然として、cookie ベースの常設用に lync server 2010 の場合と同じ規則が適用されます。</span><span class="sxs-lookup"><span data-stu-id="5d7ca-131">If you need to retain any Lync Server 2010&nbsp;Front End Servers or Front End pools, the same rules still apply as in Lync Server 2010 for cookie-based persistence.</span></span>

    
    </div>

  - <span data-ttu-id="5d7ca-132">**Apple iOS デバイスと Windows Phone のプッシュ通知をサポートしますか?**</span><span class="sxs-lookup"><span data-stu-id="5d7ca-132">**Do you want to support push notifications for Apple iOS devices and Windows Phones?**</span></span>
    
    <span data-ttu-id="5d7ca-133">プッシュ通知をサポートしている場合、サポートされている Apple iOS デバイスと Windows Phone は、モバイルアプリケーションが非アクティブなときに発生するイベントの通知を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="5d7ca-133">If you support push notifications, supported Apple iOS devices and Windows Phones receive a notification of events that occur when the mobile application is inactive.</span></span> <span data-ttu-id="5d7ca-134">エッジサーバーは、Lync Online データセンターにあるクラウドベースの Lync Server プッシュ通知サービスとのフェデレーション関係を持ち、プッシュ通知を有効にするコマンドレットを実行するように構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d7ca-134">You must configure your Edge Server to have a federation relationship with the cloud-based Lync Server Push Notification Service, which is located in the Lync Online datacenter, and run a cmdlet to enable push notifications.</span></span>
    
    <span data-ttu-id="5d7ca-135">Wi-fi ネットワーク経由でのプッシュ通知をサポートする場合は、モバイルデバイスプロバイダーの3G またはデータネットワーク経由でのプッシュ通知のサポートに加えて、エンタープライズ Wi-fi ネットワークでポート5223を開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d7ca-135">If you want to support push notifications over your Wi-Fi network, in addition to supporting push notifications over the mobile device providers' 3G or data networks, you must open port 5223 outbound on your enterprise Wi-Fi network.</span></span> <span data-ttu-id="5d7ca-136">Wi-fi ネットワーク経由でのプッシュ通知のサポートには、不適切な室内受信の Wi-fi とモバイルデバイスのみを使用するモバイルデバイスがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="5d7ca-136">Supporting push notifications over the Wi-Fi network supports mobile devices that use only Wi-Fi and mobile devices that have poor indoor reception.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="5d7ca-137">Lync 2010 モバイルクライアントを実行している Apple デバイスをサポートしている場合にのみ、ポート TCP 5223 を開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d7ca-137">Opening port TCP 5223 is required only when supporting Apple devices running the Lync 2010 Mobile client.</span></span>

    
    </div>
    
    <span data-ttu-id="5d7ca-138">プッシュ通知がサポートされていない場合は、Apple モバイルデバイスおよび Windows Phone のユーザーは、モバイルアプリケーションが非アクティブなときに発生する、インスタントメッセージの招待状や不在着信メッセージなどのイベントについては検出されません。</span><span class="sxs-lookup"><span data-stu-id="5d7ca-138">If you do not support push notifications, users of Apple mobile devices and Windows Phones will not find out about events—such as instant message invitations or missed messages—that occur when the mobile application is inactive.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5d7ca-139">Apple デバイス上の Lync 2013 モバイルクライアントでは、プッシュ通知は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="5d7ca-139">Lync 2013 Mobile clients on Apple devices do not require push notification.</span></span> <span data-ttu-id="5d7ca-140">Windows Phone の Lync 2013 モバイルクライアントでは、プッシュ通知が使われます。</span><span class="sxs-lookup"><span data-stu-id="5d7ca-140">The Lync 2013 Mobile clients on Windows Phone use push notification.</span></span> <span data-ttu-id="5d7ca-141">プッシュ通知の計画とプッシュ通知のクリアリングハウスは、Lync 2013 モバイルクライアントを実行できない Windows Phone および Apple デバイス上の Lync Mobile でも同じです。</span><span class="sxs-lookup"><span data-stu-id="5d7ca-141">Planning for push notification and the push notification clearinghouse remain the same for Lync Mobile on Windows Phone and Apple devices that are not able to run the Lync 2013 Mobile client.</span></span>

    
    </div>

  - <span data-ttu-id="5d7ca-142">**すべてのユーザーがモビリティ機能にアクセスできるようにするか、これらの機能にアクセスできるユーザーを指定できるようにする必要がありますか。**</span><span class="sxs-lookup"><span data-stu-id="5d7ca-142">**Do you want all users to have access to mobility features, or do you want to be able to specify which users have access to these features?**</span></span>
    
    <span data-ttu-id="5d7ca-143">この表では、Lync Server 2013 でユーザーが使用できる機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="5d7ca-143">The table describes features available to users in Lync Server 2013.</span></span> <span data-ttu-id="5d7ca-144">既定では、勤務先での通話が許可され、ボイスオーバー IP (VoIP) が許可され、モビリティが有効になります。</span><span class="sxs-lookup"><span data-stu-id="5d7ca-144">The defaults allow Call via Work, allow Voice over IP (VoIP), and enable Mobility.</span></span> <span data-ttu-id="5d7ca-145">使用可能なオプションの全セットを次に示します。</span><span class="sxs-lookup"><span data-stu-id="5d7ca-145">Here is the full set of available options:</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="5d7ca-146">Feature/Parameter Name/Scope (ポリシーパラメーター名は同じではない可能性があります)</span><span class="sxs-lookup"><span data-stu-id="5d7ca-146">Feature/Parameter Name/Scope (Policy parameter names may not be the same)</span></span></th>
    <th><span data-ttu-id="5d7ca-147">説明</span><span class="sxs-lookup"><span data-stu-id="5d7ca-147">Description</span></span></th>
    <th><span data-ttu-id="5d7ca-148">導か</span><span class="sxs-lookup"><span data-stu-id="5d7ca-148">Introduced</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="5d7ca-149">モビリティを有効にする</span><span class="sxs-lookup"><span data-stu-id="5d7ca-149">Enable Mobility</span></span></p>
    <p><span data-ttu-id="5d7ca-150">パラメーター名:<code>EnableMobility</code></span><span class="sxs-lookup"><span data-stu-id="5d7ca-150">Parameter Name : <code>EnableMobility</code></span></span></p>
    <p><span data-ttu-id="5d7ca-151">スコープ: グローバル/サイト/ユーザー</span><span class="sxs-lookup"><span data-stu-id="5d7ca-151">Scope: Global/Site/User</span></span></p></td>
    <td><p><span data-ttu-id="5d7ca-152">管理者設定 Lync Mobile がインストールされている特定のスコープでユーザーを制御するには、ポリシーを False に設定すると、ユーザーはクライアントにサインインできなくなります。</span><span class="sxs-lookup"><span data-stu-id="5d7ca-152">Administrative setting to control users in a given scope that have the Lync Mobile installed, If the policy is set to False, the user would not be able to sign into the client.</span></span></p>
    <p><span data-ttu-id="5d7ca-153">既定の設定は True です。</span><span class="sxs-lookup"><span data-stu-id="5d7ca-153">The default setting is True.</span></span></p></td>
    <td><p><span data-ttu-id="5d7ca-154">Lync Server 2010 の累積更新プログラム: 2011 年11月</span><span class="sxs-lookup"><span data-stu-id="5d7ca-154">Cumulative Update for Lync Server 2010: November 2011</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="5d7ca-155">外部音声を有効にする</span><span class="sxs-lookup"><span data-stu-id="5d7ca-155">Enable Outside Voice</span></span></p>
    <p><span data-ttu-id="5d7ca-156">パラメーター名:<code>EnableOutsideVoice</code></span><span class="sxs-lookup"><span data-stu-id="5d7ca-156">Parameter Name : <code>EnableOutsideVoice</code></span></span></p>
    <p><span data-ttu-id="5d7ca-157">スコープ: グローバル/サイト/ユーザー</span><span class="sxs-lookup"><span data-stu-id="5d7ca-157">Scope: Global/Site/User</span></span></p></td>
    <td><p><span data-ttu-id="5d7ca-158">勤務先のユーザーが通話を使用する機能を制御します。この機能は、ユーザーが携帯電話番号の代わりに勤務先の電話番号を使って通話を発信および受信できるようにします。</span><span class="sxs-lookup"><span data-stu-id="5d7ca-158">Controls a user’s ability to use Call Via Work, a feature that enables users to make and receive calls by using their work number instead of their mobile number.</span></span> <span data-ttu-id="5d7ca-159">False に設定した場合、ユーザーはモバイルデバイスから勤務先の電話番号を使用して通話を発信または受信することができなくなります。</span><span class="sxs-lookup"><span data-stu-id="5d7ca-159">If set to False, the user will not be able to make or receive calls by using their work number from their mobile device.</span></span></p>
    <p><span data-ttu-id="5d7ca-160">既定の設定は True です。</span><span class="sxs-lookup"><span data-stu-id="5d7ca-160">The default setting is True</span></span></p></td>
    <td><p><span data-ttu-id="5d7ca-161">Lync Server 2010 の累積更新プログラム: 2011 年11月</span><span class="sxs-lookup"><span data-stu-id="5d7ca-161">Cumulative Update for Lync Server 2010: November 2011</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="5d7ca-162">IP オーディオと IP ビデオを有効にする</span><span class="sxs-lookup"><span data-stu-id="5d7ca-162">Enable IP Audio and Video</span></span></p>
    <p><span data-ttu-id="5d7ca-163">パラメーター名:<code>EnableIPAudioVideo</code></span><span class="sxs-lookup"><span data-stu-id="5d7ca-163">Parameter Name : <code>EnableIPAudioVideo</code></span></span></p>
    <p><span data-ttu-id="5d7ca-164">スコープ: グローバル/サイト/ユーザー</span><span class="sxs-lookup"><span data-stu-id="5d7ca-164">Scope: Global/Site/User</span></span></p></td>
    <td><p><span data-ttu-id="5d7ca-165">ユーザーがモバイルデバイスで VoIP を使用して音声通話またはビデオ通話を受信できるようにするかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="5d7ca-165">Controls whether a user can use VoIP to make or receive voice or video calls on their mobile device.</span></span> <span data-ttu-id="5d7ca-166">False に設定すると、ユーザーはデバイスで VoIP またはビデオ通話を発信または受信できなくなります。</span><span class="sxs-lookup"><span data-stu-id="5d7ca-166">If set to False, the user will not be able to make or receive VoIP or video calls on their device.</span></span></p>
    <p><span data-ttu-id="5d7ca-167">既定の設定は True です。</span><span class="sxs-lookup"><span data-stu-id="5d7ca-167">The default setting is True.</span></span></p></td>
    <td><p><span data-ttu-id="5d7ca-168">Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5d7ca-168">Microsoft Lync Server 2013</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="5d7ca-169">IP オーディオ用の WiFi が必要</span><span class="sxs-lookup"><span data-stu-id="5d7ca-169">Require WiFi for IP Audio</span></span></p>
    <p><span data-ttu-id="5d7ca-170">パラメーター名:<code>RequireWiFiForIPAudio</code></span><span class="sxs-lookup"><span data-stu-id="5d7ca-170">Parameter Name : <code>RequireWiFiForIPAudio</code></span></span></p>
    <p><span data-ttu-id="5d7ca-171">スコープ: グローバル/サイト/ユーザー</span><span class="sxs-lookup"><span data-stu-id="5d7ca-171">Scope: Global/Site/User</span></span></p></td>
    <td><p><span data-ttu-id="5d7ca-172">この設定は、携帯電話のデータネットワークではなく、WiFi 上の VoIP 経由での通話の発信と受信をクライアントが必要とするかどうかを定義します。</span><span class="sxs-lookup"><span data-stu-id="5d7ca-172">This setting defines whether the client will be required to make and receive calls over VoIP on WiFi instead of the cellular data network.</span></span> <span data-ttu-id="5d7ca-173">True に設定すると、ユーザーは WiFi ネットワークに接続している場合にのみ VoIP 通話を発信および受信できます。</span><span class="sxs-lookup"><span data-stu-id="5d7ca-173">If set to True, the user can make and receive VoIP calls only when connected to a WiFi network.</span></span></p>
    <p><span data-ttu-id="5d7ca-174">既定の設定は False です。</span><span class="sxs-lookup"><span data-stu-id="5d7ca-174">The default setting is False.</span></span></p></td>
    <td><p><span data-ttu-id="5d7ca-175">Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5d7ca-175">Microsoft Lync Server 2013</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="5d7ca-176">IP ビデオ用の WiFi が必要</span><span class="sxs-lookup"><span data-stu-id="5d7ca-176">Require WiFi for IP Video</span></span></p>
    <p><span data-ttu-id="5d7ca-177">パラメーター名:<code>RequireWiFiForIPVideo</code></span><span class="sxs-lookup"><span data-stu-id="5d7ca-177">Parameter Name : <code>RequireWiFiForIPVideo</code></span></span></p>
    <p><span data-ttu-id="5d7ca-178">スコープ: グローバル/サイト/ユーザー</span><span class="sxs-lookup"><span data-stu-id="5d7ca-178">Scope: Global/Site/User</span></span></p></td>
    <td><p><span data-ttu-id="5d7ca-179">この設定は、携帯電話のデータネットワークではなく、wi-fi でのビデオ通話の発信と受信をクライアントが要求するかどうかを定義します。</span><span class="sxs-lookup"><span data-stu-id="5d7ca-179">This setting defines whether the client will be required to make and receive video calls on Wi-Fi instead of on the cellular data network.</span></span> <span data-ttu-id="5d7ca-180">True に設定した場合、ユーザーは、Wi-fi ネットワークに接続されているときにのみビデオ通話を発信および受信できます。</span><span class="sxs-lookup"><span data-stu-id="5d7ca-180">If set to True, the user can make and receive video calls only when connected to a Wi-Fi network.</span></span></p>
    <p><span data-ttu-id="5d7ca-181">既定の設定は False です。</span><span class="sxs-lookup"><span data-stu-id="5d7ca-181">The default setting is False.</span></span></p></td>
    <td><p><span data-ttu-id="5d7ca-182">Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5d7ca-182">Microsoft Lync Server 2013</span></span></p></td>
    </tr>
    </tbody>
    </table>
    
    <span data-ttu-id="5d7ca-183">構成可能なポリシー設定とポリシーの管理方法の説明については、「 [New-set-csmobilitypolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy)、 [Set-set-csmobilitypolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy)、 [Get-set-csmobilitypolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsMobilityPolicy)、 [Grant-set-csmobilitypolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsMobilityPolicy) 、 [Remove-set-csmobilitypolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsMobilityPolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d7ca-183">For a description of the policy settings that you can configure, and how to manage the policies, see [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy), [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy), [Get-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsMobilityPolicy), [Grant-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsMobilityPolicy) and [Remove-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsMobilityPolicy).</span></span>

  - <span data-ttu-id="5d7ca-184">**エンタープライズ Voip が有効になっていないユーザーが、クリックして会議に参加できるようにしますか?**</span><span class="sxs-lookup"><span data-stu-id="5d7ca-184">**Do you want users who are not enabled for Enterprise Voice to be able to use Click to Join to join conferences?**</span></span>
    
    <span data-ttu-id="5d7ca-185">ユーザーがモバイル機能にアクセスし、勤務先から通話を発信できるようにするには、エンタープライズ Voip を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d7ca-185">For users to have access to mobility features and Call via Work, they must be enabled for Enterprise Voice.</span></span> <span data-ttu-id="5d7ca-186">ただし、エンタープライズ Voip を有効にしていないユーザーは、モバイルデバイス上のリンクをクリックすると、適切な音声ポリシーが割り当てられている場合に、会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="5d7ca-186">However, users who are not enabled for Enterprise Voice can join conferences by clicking the link on their mobile device, if they have an appropriate voice policy assigned to them.</span></span> <span data-ttu-id="5d7ca-187">特定のボイスポリシーをこれらのユーザーに割り当てるか、グローバルポリシーまたはサイトレベルのポリシーが存在していることを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="5d7ca-187">You can either assign a specific voice policy to these users or make sure that a global policy or site-level policy exists that applies to them.</span></span> <span data-ttu-id="5d7ca-188">割り当てるボイスポリシーには、公衆交換電話網 (PSTN) 利用状況レコードと、ユーザーが電話会議にダイヤルアウトできる領域を定義するルートが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d7ca-188">The voice policy that you assign must have public switched telephone network (PSTN) usage records and routes that define the areas to which users can dial out to join a conference.</span></span> <span data-ttu-id="5d7ca-189">ボイスポリシー、PSTN 使用状況レコード、およびルートの設定の詳細については、「 [Lync Server 2013 で音声ポリシー、pstn 使用状況レコード、および音声ルートを構成する](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d7ca-189">For details about setting voice policy, PSTN usage records, and routes, see [Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5d7ca-190">クリックして参加したいモバイルユーザーは、モバイルデバイスでリンクをクリックすると、Lync Server 2013 からの発信通話が発生するため、音声ポリシーと関連する PSTN 使用状況レコードと音声ルートが必要になります。</span><span class="sxs-lookup"><span data-stu-id="5d7ca-190">Mobile users who want to use Click to Join require a voice policy, along with the related PSTN usage records and voice routes, because clicking the link on the mobile device results in an outbound call from Lync Server 2013.</span></span>

    
    </div>

<div>

## <a name="see-also"></a><span data-ttu-id="5d7ca-191">関連項目</span><span class="sxs-lookup"><span data-stu-id="5d7ca-191">See Also</span></span>


[<span data-ttu-id="5d7ca-192">Lync Server 2013 でのモビリティの技術要件</span><span class="sxs-lookup"><span data-stu-id="5d7ca-192">Technical requirements for mobility in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-mobility.md)  


[<span data-ttu-id="5d7ca-193">Lync Server 2013 での音声ポリシー、PSTN 使用状況レコード、および音声ルートの構成</span><span class="sxs-lookup"><span data-stu-id="5d7ca-193">Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

