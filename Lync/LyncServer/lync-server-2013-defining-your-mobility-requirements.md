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
ms.openlocfilehash: 15fe7352e4c2c5190bae27febeafcd57a94924f0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137848"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="defining-your-mobility-requirements-for-lync-server-2013"></a><span data-ttu-id="0168c-102">Lync Server 2013 のモビリティ要件の定義</span><span class="sxs-lookup"><span data-stu-id="0168c-102">Defining your mobility requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0168c-103">_**トピックの最終更新日:** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="0168c-103">_**Topic Last Modified:** 2013-02-14_</span></span>

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="0168c-104">Lync 2010 Mobile および Lync 2013 Mobile クライアントを使用している場合は、Lync Server 2013 モビリティ機能の計画フェーズで、展開の手順を決定する決定を行います。</span><span class="sxs-lookup"><span data-stu-id="0168c-104">During the planning phase for the Lync Server 2013 mobility feature, when you are using Lync 2010 Mobile and Lync 2013 Mobile clients, you make decisions that determine your deployment steps.</span></span>

<span data-ttu-id="0168c-105">考慮する必要がある決定事項は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="0168c-105">Here are the decisions that you must consider:</span></span>

  - <span data-ttu-id="0168c-106">**Lync モバイル クライアントで、自動検出を使用しますか。**</span><span class="sxs-lookup"><span data-stu-id="0168c-106">**Do you want to use automatic discovery for Lync mobile clients?**</span></span>
    
    <span data-ttu-id="0168c-107">自動検出をサポートする必要がある場合は、新しい内部および外部のドメインネームシステム (DNS) レコードを作成し、フロントエンドサーバー、ディレクター、リバースプロキシの証明書にサブジェクトの別名を追加して、既存の公開ルールを変更する必要があります。リバースプロキシで。</span><span class="sxs-lookup"><span data-stu-id="0168c-107">If you want to support automatic discovery, you need to create new internal and external Domain Name System (DNS) records, add subject alternative names to certificates on the Front End Servers, Directors, and reverse proxy, and modify the existing publishing rules on the reverse proxy.</span></span> <span data-ttu-id="0168c-108">詳細については、「 [Lync Server 2013 でのモビリティの技術要件](lync-server-2013-technical-requirements-for-mobility.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0168c-108">For details, see [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span></span> <span data-ttu-id="0168c-109">自動検出を使用すると、ユーザーは、モバイルデバイスの設定に Url を入力することなく、企業ネットワークの内外にある任意の場所から Lync Server 2013 Web サービスを自動的に検索できます。</span><span class="sxs-lookup"><span data-stu-id="0168c-109">With automatic discovery, users can automatically locate Lync Server 2013 Web Services from anywhere inside or outside the corporate network, without entering URLs in their mobile device settings.</span></span>
    
    <span data-ttu-id="0168c-110">自動検出の代わりに手動設定を使用する場合、モバイルユーザーはモバイルデバイスに以下の Url を手動で入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0168c-110">If you use manual settings instead of automatic discovery, mobile users need to manually enter the following URLs in their mobile devices:</span></span>
    
      - <span data-ttu-id="0168c-111">外部\<アクセス用の\>Https://extpoolfqdn/autodiscover/autodiscoverservice.svc/root (</span><span class="sxs-lookup"><span data-stu-id="0168c-111">https://\<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.svc/Root for external access</span></span>
    
      - <span data-ttu-id="0168c-112">https://\<intpoolfqdn\>/AutoDiscover/autodiscoverservice 内部アクセス用のルート</span><span class="sxs-lookup"><span data-stu-id="0168c-112">https://\<IntPoolFQDN\>/AutoDiscover/ autodiscoverservice.svc/Root for internal access</span></span>
    
    <span data-ttu-id="0168c-p102">自動検出を使用することを強くお勧めします。手動設定を使用するのは、主にトラブルシューティングを行う場合です。</span><span class="sxs-lookup"><span data-stu-id="0168c-p102">We strongly recommend using automatic discovery. The primary use of manual settings is for troubleshooting.</span></span>

  - <span data-ttu-id="0168c-115">**自動検出のサポートを決めた場合は、SIP ドメインごとにサブジェクトの別名でリバース プロキシ上の証明書を更新しますか。**</span><span class="sxs-lookup"><span data-stu-id="0168c-115">**If you decide to support automatic discovery, are you willing to update certificates on the reverse proxy with subject alternative names for each SIP domain?**</span></span>
    
    <span data-ttu-id="0168c-116">SIP ドメインが多い場合、リバース プロキシ上のパブリック証明書の更新は非常に高コストになる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0168c-116">If you have many SIP domains, updating public certificates on the reverse proxy can become very expensive.</span></span> <span data-ttu-id="0168c-117">その場合は、ポート443で HTTPS を使用するのではなく、最初の自動検出サービス要求がポート80で HTTP を使用するように自動検出を実装することを選択できます。</span><span class="sxs-lookup"><span data-stu-id="0168c-117">If this is the case, you can choose to implement automatic discovery so that the initial Autodiscover Service request uses HTTP on port 80, instead of using HTTPS on port 443.</span></span> <span data-ttu-id="0168c-118">ただし、これは推奨されている方法ではありません。</span><span class="sxs-lookup"><span data-stu-id="0168c-118">However, this is not the recommended approach.</span></span> <span data-ttu-id="0168c-119">この代替方法を選択する場合は、リバースプロキシの証明書を更新する必要はありませんが、ポート80で HTTP 用の web 公開ルールを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0168c-119">If you decide to choose this alternative, you do not need to update the certificates on the reverse proxy, but you need to create a web publishing rule for HTTP on port 80.</span></span> <span data-ttu-id="0168c-120">詳細については、「 [Lync Server 2013 でのモビリティの技術要件](lync-server-2013-technical-requirements-for-mobility.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0168c-120">For more details, see [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span></span>

  - <span data-ttu-id="0168c-121">**企業ネットワークの内外で Lync モバイル クライアントをサポートしますか。または企業ネットワークの内部のみでクライアントをサポートしますか。**</span><span class="sxs-lookup"><span data-stu-id="0168c-121">**Do you want to support Lync mobile clients both internal and external to the corporate network, or support clients only inside the corporate network?**</span></span>
    
    <span data-ttu-id="0168c-p104">企業ネットワークの内外でモバイル クライアントをサポートする場合は、モバイル デバイスはどの場所からでもモビリティ機能にアクセスできます。既定の構成は、企業ネットワークの内外でクライアントをサポートするようになっています</span><span class="sxs-lookup"><span data-stu-id="0168c-p104">If you want to support mobile clients internal and external to your network, mobile devices can access mobility features from any location. The default configuration is to support clients both internal and external to the corporate network.</span></span>
    
    <span data-ttu-id="0168c-124">既定の構成では、モバイル クライアントのトラフィックが外部サイトを経由することを許可していますが、モバイル クライアントのトラフィックを内部企業ネットワークに制限することができます。</span><span class="sxs-lookup"><span data-stu-id="0168c-124">Although the default configuration enables mobile client traffic to go through the external site, you can restrict mobile client traffic to the internal corporate network.</span></span> <span data-ttu-id="0168c-125">トラフィックを内部ネットワークに制限すると、モバイル デバイスが企業ネットワーク内に存在する場合に限り、ユーザーはそのモバイル デバイス上で Lync モバイル アプリケーションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="0168c-125">When you restrict the traffic to the internal network, users can use Lync mobile applications on their mobile devices only when they are inside the network.</span></span>
    
    <span data-ttu-id="0168c-126">Mcx mobility service と Lync 2010 Mobile を使用したモビリティをサポートする展開では、 **Set-CsMcxConfiguration**コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="0168c-126">For deployments that support mobility using the Mcx mobility service and Lync 2010 Mobile, you run the **Set-CsMcxConfiguration** cmdlet.</span></span> <span data-ttu-id="0168c-127">内部使用のみのモビリティを設定するには、次のようなコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="0168c-127">To set mobility for internal use only, you would use a command similar to the following:</span></span>
    
        Set-CsMcxConfiguration -Identity site:Redmond -ExposedWebURL Internal
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0168c-128">UCWA には、追加の構成は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="0168c-128">There are no additional configurations required for UCWA.</span></span> <span data-ttu-id="0168c-129">UCWA には、それに相当する内部のみの構成がありません。</span><span class="sxs-lookup"><span data-stu-id="0168c-129">UCWA does not have an equivalent internal-only configuration.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="0168c-130">Lync server 2013&nbsp;フロントエンドサーバーまたはフロントエンドプールを使用していて、lync server&nbsp;2010 フロントエンドサーバーまたはフロントエンドプールを使用して<STRONG>いない</STRONG>場合は、 <STRONG>cookie ベースの永続化の要件はありません</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="0168c-130">If you are using a Lync Server 2013&nbsp;Front End Server or Front End pools and <STRONG>you do not have</STRONG> any Lync Server 2010&nbsp;Front End Servers or Front End pools, <STRONG>there is no requirement for cookie-based persistence</STRONG>.</span></span> <span data-ttu-id="0168c-131">Lync Server 2010&nbsp;のフロントエンドサーバーまたはフロントエンドプールを保持する必要がある場合は、引き続き、cookie ベースの永続化のために lync server 2010 の場合と同じルールが適用されます。</span><span class="sxs-lookup"><span data-stu-id="0168c-131">If you need to retain any Lync Server 2010&nbsp;Front End Servers or Front End pools, the same rules still apply as in Lync Server 2010 for cookie-based persistence.</span></span>

    
    </div>

  - <span data-ttu-id="0168c-132">**Apple iOS デバイスと Windows Phone でプッシュ通知をサポートしますか。**</span><span class="sxs-lookup"><span data-stu-id="0168c-132">**Do you want to support push notifications for Apple iOS devices and Windows Phones?**</span></span>
    
    <span data-ttu-id="0168c-133">プッシュ通知をサポートすると、サポートされている Apple iOS デバイスと Windows Phone は、モバイル アプリケーションが非アクティブな場合に発生するイベントの通知を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="0168c-133">If you support push notifications, supported Apple iOS devices and Windows Phones receive a notification of events that occur when the mobile application is inactive.</span></span> <span data-ttu-id="0168c-134">Lync Online データセンターにあるクラウドベースの Lync Server プッシュ通知サービスとのフェデレーション関係を持つようにエッジサーバーを構成し、コマンドレットを実行してプッシュ通知を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0168c-134">You must configure your Edge Server to have a federation relationship with the cloud-based Lync Server Push Notification Service, which is located in the Lync Online datacenter, and run a cmdlet to enable push notifications.</span></span>
    
    <span data-ttu-id="0168c-135">Wi-fi ネットワーク経由のプッシュ通知をサポートする必要がある場合は、モバイルデバイスプロバイダーの3G またはデータネットワークでプッシュ通知をサポートすることに加えて、エンタープライズ Wi-fi ネットワーク上でポート5223アウトを開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="0168c-135">If you want to support push notifications over your Wi-Fi network, in addition to supporting push notifications over the mobile device providers' 3G or data networks, you must open port 5223 outbound on your enterprise Wi-Fi network.</span></span> <span data-ttu-id="0168c-136">Wi-Fi ネットワークでプッシュ通知をサポートすると、Wi-Fi のみを使用するモバイル デバイスと室内での受信が弱いモバイル デバイスがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="0168c-136">Supporting push notifications over the Wi-Fi network supports mobile devices that use only Wi-Fi and mobile devices that have poor indoor reception.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="0168c-137">Lync 2010 モバイルクライアントを実行している Apple デバイスをサポートする場合にのみ、ポート TCP 5223 を開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="0168c-137">Opening port TCP 5223 is required only when supporting Apple devices running the Lync 2010 Mobile client.</span></span>

    
    </div>
    
    <span data-ttu-id="0168c-138">プッシュ通知をサポートしていない場合、Apple モバイルデバイスおよび Windows Phone のユーザーは、モバイルアプリケーションが非アクティブな場合に発生するインスタントメッセージの招待や不在着信メッセージなどのイベントについては確認できません。</span><span class="sxs-lookup"><span data-stu-id="0168c-138">If you do not support push notifications, users of Apple mobile devices and Windows Phones will not find out about events—such as instant message invitations or missed messages—that occur when the mobile application is inactive.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0168c-139">Apple デバイス上の Lync 2013 モバイルクライアントは、プッシュ通知を必要としません。</span><span class="sxs-lookup"><span data-stu-id="0168c-139">Lync 2013 Mobile clients on Apple devices do not require push notification.</span></span> <span data-ttu-id="0168c-140">Windows Phone 上の Lync 2013 モバイルクライアントは、プッシュ通知を使用します。</span><span class="sxs-lookup"><span data-stu-id="0168c-140">The Lync 2013 Mobile clients on Windows Phone use push notification.</span></span> <span data-ttu-id="0168c-141">プッシュ通知およびプッシュ通知クリアリングハウスの計画は、lync 2013 Mobile クライアントを実行できない Windows Phone および Apple のデバイス上の Lync Mobile に対して同じままです。</span><span class="sxs-lookup"><span data-stu-id="0168c-141">Planning for push notification and the push notification clearinghouse remain the same for Lync Mobile on Windows Phone and Apple devices that are not able to run the Lync 2013 Mobile client.</span></span>

    
    </div>

  - <span data-ttu-id="0168c-142">**すべてのユーザーがモビリティ機能にアクセスできるようにするか、またはこれらの機能にアクセスできるユーザーを指定できるようにしますか。**</span><span class="sxs-lookup"><span data-stu-id="0168c-142">**Do you want all users to have access to mobility features, or do you want to be able to specify which users have access to these features?**</span></span>
    
    <span data-ttu-id="0168c-143">Lync Server 2013 でユーザーが使用できる機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="0168c-143">The table describes features available to users in Lync Server 2013.</span></span> <span data-ttu-id="0168c-144">既定では、勤務先から通話、ボイスオーバー IP (VoIP) を許可、モビリティを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="0168c-144">The defaults allow Call via Work, allow Voice over IP (VoIP), and enable Mobility.</span></span> <span data-ttu-id="0168c-145">利用可能なオプションの全セットを次に示します。</span><span class="sxs-lookup"><span data-stu-id="0168c-145">Here is the full set of available options:</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="0168c-146">Feature/Parameter Name/Scope (ポリシーパラメーター名が同じではない可能性があります)</span><span class="sxs-lookup"><span data-stu-id="0168c-146">Feature/Parameter Name/Scope (Policy parameter names may not be the same)</span></span></th>
    <th><span data-ttu-id="0168c-147">説明</span><span class="sxs-lookup"><span data-stu-id="0168c-147">Description</span></span></th>
    <th><span data-ttu-id="0168c-148">導入</span><span class="sxs-lookup"><span data-stu-id="0168c-148">Introduced</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="0168c-149">モビリティを有効にする</span><span class="sxs-lookup"><span data-stu-id="0168c-149">Enable Mobility</span></span></p>
    <p><span data-ttu-id="0168c-150">パラメーター名:<code>EnableMobility</code></span><span class="sxs-lookup"><span data-stu-id="0168c-150">Parameter Name : <code>EnableMobility</code></span></span></p>
    <p><span data-ttu-id="0168c-151">範囲: グローバル/サイト/ユーザー</span><span class="sxs-lookup"><span data-stu-id="0168c-151">Scope: Global/Site/User</span></span></p></td>
    <td><p><span data-ttu-id="0168c-152">管理者設定 Lync Mobile がインストールされている特定のスコープ内のユーザーを制御するには、ポリシーが False に設定されている場合、ユーザーはクライアントにサインインできません。</span><span class="sxs-lookup"><span data-stu-id="0168c-152">Administrative setting to control users in a given scope that have the Lync Mobile installed, If the policy is set to False, the user would not be able to sign into the client.</span></span></p>
    <p><span data-ttu-id="0168c-153">既定値は True です。</span><span class="sxs-lookup"><span data-stu-id="0168c-153">The default setting is True.</span></span></p></td>
    <td><p><span data-ttu-id="0168c-154">Lync Server 2010 の累積的な更新プログラム:11 月2011</span><span class="sxs-lookup"><span data-stu-id="0168c-154">Cumulative Update for Lync Server 2010: November 2011</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="0168c-155">外部音声を有効にする</span><span class="sxs-lookup"><span data-stu-id="0168c-155">Enable Outside Voice</span></span></p>
    <p><span data-ttu-id="0168c-156">パラメーター名:<code>EnableOutsideVoice</code></span><span class="sxs-lookup"><span data-stu-id="0168c-156">Parameter Name : <code>EnableOutsideVoice</code></span></span></p>
    <p><span data-ttu-id="0168c-157">範囲: グローバル/サイト/ユーザー</span><span class="sxs-lookup"><span data-stu-id="0168c-157">Scope: Global/Site/User</span></span></p></td>
    <td><p><span data-ttu-id="0168c-158">ユーザーが携帯電話番号ではなく勤務先番号を使用して通話を発信または受信できるようにする機能を、勤務先から通話を使用できるように制御します。</span><span class="sxs-lookup"><span data-stu-id="0168c-158">Controls a user’s ability to use Call Via Work, a feature that enables users to make and receive calls by using their work number instead of their mobile number.</span></span> <span data-ttu-id="0168c-159">False に設定されている場合、ユーザーはモバイルデバイスから自分の勤務先番号を使用して通話を発信または受信できません。</span><span class="sxs-lookup"><span data-stu-id="0168c-159">If set to False, the user will not be able to make or receive calls by using their work number from their mobile device.</span></span></p>
    <p><span data-ttu-id="0168c-160">既定値は True です。</span><span class="sxs-lookup"><span data-stu-id="0168c-160">The default setting is True</span></span></p></td>
    <td><p><span data-ttu-id="0168c-161">Lync Server 2010 の累積的な更新プログラム:11 月2011</span><span class="sxs-lookup"><span data-stu-id="0168c-161">Cumulative Update for Lync Server 2010: November 2011</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="0168c-162">IP オーディオおよびビデオを有効にする</span><span class="sxs-lookup"><span data-stu-id="0168c-162">Enable IP Audio and Video</span></span></p>
    <p><span data-ttu-id="0168c-163">パラメーター名:<code>EnableIPAudioVideo</code></span><span class="sxs-lookup"><span data-stu-id="0168c-163">Parameter Name : <code>EnableIPAudioVideo</code></span></span></p>
    <p><span data-ttu-id="0168c-164">範囲: グローバル/サイト/ユーザー</span><span class="sxs-lookup"><span data-stu-id="0168c-164">Scope: Global/Site/User</span></span></p></td>
    <td><p><span data-ttu-id="0168c-165">ユーザーが VoIP を使用して、モバイルデバイスで音声またはビデオ通話を発信または受信できるようにするかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="0168c-165">Controls whether a user can use VoIP to make or receive voice or video calls on their mobile device.</span></span> <span data-ttu-id="0168c-166">False に設定されている場合、ユーザーはデバイス上で VoIP またはビデオ通話を発信または受信できません。</span><span class="sxs-lookup"><span data-stu-id="0168c-166">If set to False, the user will not be able to make or receive VoIP or video calls on their device.</span></span></p>
    <p><span data-ttu-id="0168c-167">既定値は True です。</span><span class="sxs-lookup"><span data-stu-id="0168c-167">The default setting is True.</span></span></p></td>
    <td><p><span data-ttu-id="0168c-168">Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0168c-168">Microsoft Lync Server 2013</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="0168c-169">IP オーディオに WiFi が必要</span><span class="sxs-lookup"><span data-stu-id="0168c-169">Require WiFi for IP Audio</span></span></p>
    <p><span data-ttu-id="0168c-170">パラメーター名:<code>RequireWiFiForIPAudio</code></span><span class="sxs-lookup"><span data-stu-id="0168c-170">Parameter Name : <code>RequireWiFiForIPAudio</code></span></span></p>
    <p><span data-ttu-id="0168c-171">範囲: グローバル/サイト/ユーザー</span><span class="sxs-lookup"><span data-stu-id="0168c-171">Scope: Global/Site/User</span></span></p></td>
    <td><p><span data-ttu-id="0168c-172">この設定では、携帯データネットワークではなく、Wi-fi で VoIP 経由の通話を発信および受信するためにクライアントが必要かどうかを定義します。</span><span class="sxs-lookup"><span data-stu-id="0168c-172">This setting defines whether the client will be required to make and receive calls over VoIP on WiFi instead of the cellular data network.</span></span> <span data-ttu-id="0168c-173">True に設定すると、ユーザーは WiFi ネットワークに接続されている場合にのみ VoIP 通話を発信および受信できるようになります。</span><span class="sxs-lookup"><span data-stu-id="0168c-173">If set to True, the user can make and receive VoIP calls only when connected to a WiFi network.</span></span></p>
    <p><span data-ttu-id="0168c-174">既定値は False です。</span><span class="sxs-lookup"><span data-stu-id="0168c-174">The default setting is False.</span></span></p></td>
    <td><p><span data-ttu-id="0168c-175">Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0168c-175">Microsoft Lync Server 2013</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="0168c-176">IP ビデオに WiFi が必要</span><span class="sxs-lookup"><span data-stu-id="0168c-176">Require WiFi for IP Video</span></span></p>
    <p><span data-ttu-id="0168c-177">パラメーター名:<code>RequireWiFiForIPVideo</code></span><span class="sxs-lookup"><span data-stu-id="0168c-177">Parameter Name : <code>RequireWiFiForIPVideo</code></span></span></p>
    <p><span data-ttu-id="0168c-178">範囲: グローバル/サイト/ユーザー</span><span class="sxs-lookup"><span data-stu-id="0168c-178">Scope: Global/Site/User</span></span></p></td>
    <td><p><span data-ttu-id="0168c-179">この設定では、携帯データネットワークではなく、Wi-fi でビデオ通話を発信および受信するためにクライアントが必要かどうかを定義します。</span><span class="sxs-lookup"><span data-stu-id="0168c-179">This setting defines whether the client will be required to make and receive video calls on Wi-Fi instead of on the cellular data network.</span></span> <span data-ttu-id="0168c-180">True に設定すると、ユーザーは Wi-fi ネットワークに接続されている場合にのみ、ビデオ通話を発信および受信できます。</span><span class="sxs-lookup"><span data-stu-id="0168c-180">If set to True, the user can make and receive video calls only when connected to a Wi-Fi network.</span></span></p>
    <p><span data-ttu-id="0168c-181">既定値は False です。</span><span class="sxs-lookup"><span data-stu-id="0168c-181">The default setting is False.</span></span></p></td>
    <td><p><span data-ttu-id="0168c-182">Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0168c-182">Microsoft Lync Server 2013</span></span></p></td>
    </tr>
    </tbody>
    </table>
    
    <span data-ttu-id="0168c-183">構成できるポリシー設定、およびポリシーを管理する方法については、「 [get-csmobilitypolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy)」、「 [get-csmobilitypolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy)」、「 [get-csmobilitypolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsMobilityPolicy)」、「 [Get-csmobilitypolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsMobilityPolicy) 」、および「 [Remove-get-csmobilitypolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsMobilityPolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0168c-183">For a description of the policy settings that you can configure, and how to manage the policies, see [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy), [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy), [Get-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsMobilityPolicy), [Grant-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsMobilityPolicy) and [Remove-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsMobilityPolicy).</span></span>

  - <span data-ttu-id="0168c-184">**エンタープライズ VoIP が有効になっていないユーザーが、クリックして参加を使用して会議に参加できるようにしますか。**</span><span class="sxs-lookup"><span data-stu-id="0168c-184">**Do you want users who are not enabled for Enterprise Voice to be able to use Click to Join to join conferences?**</span></span>
    
    <span data-ttu-id="0168c-185">モビリティ機能や勤務先電話からの通話機能にアクセスできるユーザーは、エンタープライズ VoIP が有効になっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="0168c-185">For users to have access to mobility features and Call via Work, they must be enabled for Enterprise Voice.</span></span> <span data-ttu-id="0168c-186">ただし、エンタープライズ Voip が有効になっていないユーザーは、適切な音声ポリシーが割り当てられている場合は、モバイルデバイスでリンクをクリックすることで会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="0168c-186">However, users who are not enabled for Enterprise Voice can join conferences by clicking the link on their mobile device, if they have an appropriate voice policy assigned to them.</span></span> <span data-ttu-id="0168c-187">特定の音声ポリシーをこれらのユーザーに割り当てるか、グローバルポリシーまたはサイトレベルのポリシーが適用されるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="0168c-187">You can either assign a specific voice policy to these users or make sure that a global policy or site-level policy exists that applies to them.</span></span> <span data-ttu-id="0168c-188">割り当てる音声ポリシーには、公衆交換電話網 (PSTN) 使用法レコードと、ユーザーが会議に参加するためにダイヤルアウトできる領域を定義するルートがある必要があります。</span><span class="sxs-lookup"><span data-stu-id="0168c-188">The voice policy that you assign must have public switched telephone network (PSTN) usage records and routes that define the areas to which users can dial out to join a conference.</span></span> <span data-ttu-id="0168c-189">音声ポリシー、PSTN 使用法レコード、およびルートの設定の詳細については、「 [Lync Server 2013 での音声ポリシー、pstn 使用法レコード、およびボイスルートの構成](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0168c-189">For details about setting voice policy, PSTN usage records, and routes, see [Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0168c-190">モバイルデバイス上のリンクをクリックすると Lync Server 2013 からの発信通話が発生するため、クリックして参加するモバイルユーザーには音声ポリシーと関連する PSTN 使用法レコードおよび音声ルートが必要です。</span><span class="sxs-lookup"><span data-stu-id="0168c-190">Mobile users who want to use Click to Join require a voice policy, along with the related PSTN usage records and voice routes, because clicking the link on the mobile device results in an outbound call from Lync Server 2013.</span></span>

    
    </div>

<div>

## <a name="see-also"></a><span data-ttu-id="0168c-191">関連項目</span><span class="sxs-lookup"><span data-stu-id="0168c-191">See Also</span></span>


[<span data-ttu-id="0168c-192">Lync Server 2013 でのモビリティの技術要件</span><span class="sxs-lookup"><span data-stu-id="0168c-192">Technical requirements for mobility in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-mobility.md)  


[<span data-ttu-id="0168c-193">Lync Server 2013 での音声ポリシー、PSTN 使用法レコード、およびボイスルートの構成</span><span class="sxs-lookup"><span data-stu-id="0168c-193">Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

