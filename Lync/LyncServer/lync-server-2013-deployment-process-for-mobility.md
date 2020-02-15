---
title: 'Lync Server 2013: モビリティの展開プロセス'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for mobility
ms:assetid: 5a1cebda-c14b-4ff4-9c36-f7caa868160f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690023(v=OCS.15)
ms:contentKeyID: 48184220
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 337e85520cb2a285f4e4743837aafa4136c89f27
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035319"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-mobility-in-lync-server-2013"></a><span data-ttu-id="97e72-102">Lync Server 2013 でのモビリティの展開プロセス</span><span class="sxs-lookup"><span data-stu-id="97e72-102">Deployment process for mobility in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="97e72-103">_**トピックの最終更新日:** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="97e72-103">_**Topic Last Modified:** 2013-02-19_</span></span>

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013. It is noted accordingly.

<span data-ttu-id="97e72-104">このセクションでは、Lync Server 2013 モビリティ機能を展開するために必要な一連の手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="97e72-104">This section describes the sequence of steps required to deploy the Lync Server 2013 mobility feature.</span></span>

### <a name="mobility-deployment-process"></a><span data-ttu-id="97e72-105">モビリティの展開プロセス</span><span class="sxs-lookup"><span data-stu-id="97e72-105">Mobility Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="97e72-106">フェーズ</span><span class="sxs-lookup"><span data-stu-id="97e72-106">Phase</span></span></th>
<th><span data-ttu-id="97e72-107">手順</span><span class="sxs-lookup"><span data-stu-id="97e72-107">Steps</span></span></th>
<th><span data-ttu-id="97e72-108">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="97e72-108">Permissions</span></span></th>
<th><span data-ttu-id="97e72-109">展開のドキュメント</span><span class="sxs-lookup"><span data-stu-id="97e72-109">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="97e72-110">ドメイン ネーム システム (DNS) レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="97e72-110">Create Domain Name System (DNS) records</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="97e72-111">内部の自動検出サービス URL を解決するための内部 DNS CNAME または A (host、if IPv6、AAAA) レコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="97e72-111">Create an internal DNS CNAME or A (host, if IPv6, AAAA) record to resolve the internal Autodiscover Service URL.</span></span></p></li>
<li><p><span data-ttu-id="97e72-112">外部の自動検出サービス URL を解決する外部 DNS CNAME または A (host、if IPv6、AAAA) レコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="97e72-112">Create an external DNS CNAME or A (host, if IPv6, AAAA) record to resolve the external Autodiscover Service URL.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="97e72-113">Domain Admins</span><span class="sxs-lookup"><span data-stu-id="97e72-113">Domain Admins</span></span></p>
<p><span data-ttu-id="97e72-114">DnsAdmins</span><span class="sxs-lookup"><span data-stu-id="97e72-114">DnsAdmins</span></span></p></td>
<td><p><span data-ttu-id="97e72-115"><a href="lync-server-2013-creating-dns-records-for-the-autodiscover-service.md">Lync Server 2013 での自動検出サービスの DNS レコードの作成</a></span><span class="sxs-lookup"><span data-stu-id="97e72-115"><a href="lync-server-2013-creating-dns-records-for-the-autodiscover-service.md">Creating DNS records for the Autodiscover Service in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97e72-116">証明書を変更する</span><span class="sxs-lookup"><span data-stu-id="97e72-116">Modify certificates</span></span></p></td>
<td><p><span data-ttu-id="97e72-117">サブジェクトの別名エントリを以下の証明書に追加し、モバイル ユーザーのセキュリティで保護された接続をサポートします。</span><span class="sxs-lookup"><span data-stu-id="97e72-117">Add subject alternative name entries to the following certificates to support secure connections for mobile users:</span></span></p>
<ul>
<li><p><span data-ttu-id="97e72-118">ディレクター証明書</span><span class="sxs-lookup"><span data-stu-id="97e72-118">Director certificate</span></span></p></li>
<li><p><span data-ttu-id="97e72-119">フロントエンドプールの証明書</span><span class="sxs-lookup"><span data-stu-id="97e72-119">Front End pool certificate</span></span></p></li>
<li><p><span data-ttu-id="97e72-120">リバース プロキシの証明書</span><span class="sxs-lookup"><span data-stu-id="97e72-120">Reverse proxy certificate</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="97e72-121">ローカル管理者</span><span class="sxs-lookup"><span data-stu-id="97e72-121">Local administrator</span></span></p></td>
<td><p><span data-ttu-id="97e72-122"><a href="lync-server-2013-modifying-certificates-for-mobility.md">Lync Server 2013 でのモビリティの証明書の変更</a></span><span class="sxs-lookup"><span data-stu-id="97e72-122"><a href="lync-server-2013-modifying-certificates-for-mobility.md">Modifying certificates for mobility in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97e72-123">リバース プロキシを構成する</span><span class="sxs-lookup"><span data-stu-id="97e72-123">Configure the reverse proxy</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="97e72-124">サブジェクトの別名で更新された証明書を SSL (Secure Sockets Layer) リスナーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="97e72-124">Assign certificates updated with subject alternative names to the Secure Sockets Layer (SSL) Listener.</span></span></p></li>
<li><p><span data-ttu-id="97e72-125">外部自動検出サービス URL の web 公開ルールを再構成します。</span><span class="sxs-lookup"><span data-stu-id="97e72-125">Reconfigure the web publishing rule for the external Autodiscover Service URL.</span></span></p></li>
<li><p><span data-ttu-id="97e72-126">フロントエンドプールに外部 Lync Server 2013 Web サービス URL 用の web 公開ルールが存在することを確認してください。</span><span class="sxs-lookup"><span data-stu-id="97e72-126">Be sure that a web publishing rule exists for the external Lync Server 2013 Web Services URL on your Front End pool.</span></span></p></li>
</ul>
<p><span data-ttu-id="97e72-127">または</span><span class="sxs-lookup"><span data-stu-id="97e72-127">Or</span></span></p>
<ul>
<li><p><span data-ttu-id="97e72-128">最初の自動検出要求に HTTP を使用し、証明書のサブジェクトの別名リストを更新しない場合は、新しい web 公開ルールを構成するか、ポート 80 HTTP の既存の公開ルールを再構成します。</span><span class="sxs-lookup"><span data-stu-id="97e72-128">If you choose to use HTTP for the initial Autodiscover request and do not update subject alternative name lists on the certificates, configure a new web publishing rule or reconfigure an existing publishing rule for port 80 HTTP.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="97e72-129">ローカル管理者</span><span class="sxs-lookup"><span data-stu-id="97e72-129">Local administrator</span></span></p></td>
<td><p><span data-ttu-id="97e72-130"><a href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Lync Server 2013 でのモビリティのリバースプロキシの構成</a></span><span class="sxs-lookup"><span data-stu-id="97e72-130"><a href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Configuring the reverse proxy for mobility in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97e72-131">Mcx Mobility Service を使用して Lync 2010 Mobile のモビリティ展開をテストする</span><span class="sxs-lookup"><span data-stu-id="97e72-131">Test your mobility deployment for Lync 2010 Mobile using the Mcx Mobility Service</span></span></p></td>
<td><p><span data-ttu-id="97e72-132"><strong>Test-CsMcxP2PIM</strong> を実行し、ユーザー間のインスタント メッセージの送信をテストします。</span><span class="sxs-lookup"><span data-stu-id="97e72-132">Run <strong>Test-CsMcxP2PIM</strong> to test sending an instant message from one person to another.</span></span></p>
<p><span data-ttu-id="97e72-133">オプションの完全な一覧については、「 <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM">test-csmcxp2pim</a> 」の Lync Server Management Shell コマンドレットのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="97e72-133">See the Lync Server Management Shell cmdlet documentation for <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM">Test-CsMcxP2PIM</a> for a complete list of options.</span></span></p></td>
<td><p><span data-ttu-id="97e72-134">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="97e72-134">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="97e72-135"><a href="lync-server-2013-verifying-your-mobility-deployment.md">Lync Server 2013 でのモビリティの展開の確認</a></span><span class="sxs-lookup"><span data-stu-id="97e72-135"><a href="lync-server-2013-verifying-your-mobility-deployment.md">Verifying your mobility deployment in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97e72-136">UCWA Web コンポーネントを使用して Lync 2013 Mobile クライアントのモビリティ展開をテストする</span><span class="sxs-lookup"><span data-stu-id="97e72-136">Test your mobility deployment for Lync 2013 Mobile clients using the UCWA Web components</span></span></p></td>
<td><p><span data-ttu-id="97e72-137"><strong>Test-csucwaconference</strong>コマンドレットを使用して、定義済みのテストユーザーまたは実際のユーザーのペアが、ucwa を使用して会議を作成して参加できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="97e72-137">Use the <strong>Test-CsUcwaConference</strong> cmdlet to test and verify that pre-defined test users or a pair of actual users can use UCWA to create and participate in a conference.</span></span></p>
<p><span data-ttu-id="97e72-138">オプションの完全な一覧については、「 <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference">test-csucwaconference</a> 」の Lync Server Management Shell コマンドレットのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="97e72-138">See the Lync Server Management Shell cmdlet documentation for <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference">Test-CsUcwaConference</a> for a complete list of options.</span></span></p></td>
<td><p><span data-ttu-id="97e72-139">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="97e72-139">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="97e72-140"><a href="lync-server-2013-verifying-your-mobility-deployment.md">Lync Server 2013 でのモビリティの展開の確認</a></span><span class="sxs-lookup"><span data-stu-id="97e72-140"><a href="lync-server-2013-verifying-your-mobility-deployment.md">Verifying your mobility deployment in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97e72-141">プッシュ通知を構成する</span><span class="sxs-lookup"><span data-stu-id="97e72-141">Configure for push notifications</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="97e72-142">Lync Server 2013 エッジサーバーの場合は、Lync Server online ホスティングプロバイダーを追加し、ホスティングプロバイダーフェデレーションを構成します。</span><span class="sxs-lookup"><span data-stu-id="97e72-142">For Lync Server 2013 Edge Servers, add a Lync Server online hosting provider and configure hosting provider federation.</span></span></p></li>
<li><p><span data-ttu-id="97e72-143">Lync Server 2010 エッジサーバーの場合は、Lync Server online ホスティングプロバイダーを追加し、ホスティングプロバイダーフェデレーションを構成します。</span><span class="sxs-lookup"><span data-stu-id="97e72-143">For Lync Server 2010  Edge Servers, add a Lync Server online hosting provider and configure hosting provider federation.</span></span></p></li>
<li><p><span data-ttu-id="97e72-144">Office Communications Server 2007 R2 エッジサーバーの場合は、フェデレーションパートナーを追加します。</span><span class="sxs-lookup"><span data-stu-id="97e72-144">For Office Communications Server 2007 R2 Edge Servers, add a federated partner.</span></span></p></li>
<li><p><span data-ttu-id="97e72-145">Wi-fi ネットワーク経由のプッシュ通知をサポートする場合は、TCP ポート5223に対する送信ファイアウォールルールを構成します。</span><span class="sxs-lookup"><span data-stu-id="97e72-145">If you want to support push notifications over a Wi-Fi network, configure a firewall rule outbound for TCP port 5223.</span></span></p></li>
<li><p><span data-ttu-id="97e72-146">Apple Push Notification Service (APNS) および Microsoft プッシュ通知サービス (MPNS) へのプッシュ通知を有効にするには、 <strong>Set-Cspの Notificationconfiguration</strong>コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="97e72-146">Use the <strong>Set-CsPushNotificationConfiguration</strong> cmdlet to enable push notifications to the Apple Push Notification Service (APNS) and Microsoft Push Notification Service (MPNS).</span></span> <span data-ttu-id="97e72-147">既定では、この機能は無効になっています。</span><span class="sxs-lookup"><span data-stu-id="97e72-147">This feature is disabled by default.</span></span></p></li>
<li><p><span data-ttu-id="97e72-148">プッシュ通知をテストするには、 <strong>test-csfederatedpartner</strong>コマンドレットを使用してフェデレーション構成をテストし、 <strong>CsMCXPushNotification</strong>コマンドレットをテストします。</span><span class="sxs-lookup"><span data-stu-id="97e72-148">Use the <strong>Test-CsFederatedPartner</strong> cmdlet to test the federation configuration and the <strong>Test-CsMCXPushNotification</strong> cmdlet to test push notifications.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="97e72-149">プッシュ通知は、Apple デバイスおよび Windows Phone の Lync 2010 モバイルクライアントで使用されます。</span><span class="sxs-lookup"><span data-stu-id="97e72-149">Push notifications are used for Lync 2010 Mobile clients on Apple devices and Windows Phone</span></span><BR><span data-ttu-id="97e72-150">Windows Phone のみの Lync 2013 モバイルクライアントでプッシュ通知が必要</span><span class="sxs-lookup"><span data-stu-id="97e72-150">Push notification is required for Lync 2013 Mobile clients on Windows Phone only</span></span>


</div></li>
</ul></td>
<td><p><span data-ttu-id="97e72-151">RtcUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="97e72-151">RtcUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="97e72-152"><a href="lync-server-2013-configuring-for-push-notifications.md">Lync Server 2013 でのプッシュ通知の構成</a></span><span class="sxs-lookup"><span data-stu-id="97e72-152"><a href="lync-server-2013-configuring-for-push-notifications.md">Configuring for push notifications in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97e72-153">モビリティポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="97e72-153">Configure mobility policy</span></span></p></td>
<td><p><span data-ttu-id="97e72-154"><strong>Get-csmobilitypolicy</strong>コマンドレットを使用して、次のことを許可または禁止します。</span><span class="sxs-lookup"><span data-stu-id="97e72-154">Use the <strong>Set-CsMobilityPolicy</strong> cmdlet to allow or disallow:</span></span></p>
<ul>
<li><p><span data-ttu-id="97e72-155">勤務先から通話</span><span class="sxs-lookup"><span data-stu-id="97e72-155">Call via Work</span></span></p></li>
<li><p><span data-ttu-id="97e72-156">IP オーディオと IP ビデオを有効にする</span><span class="sxs-lookup"><span data-stu-id="97e72-156">Enable IP Audio and IP Video</span></span></p></li>
<li><p><span data-ttu-id="97e72-157">IP オーディオまたは IP ビデオに WiFi が必要</span><span class="sxs-lookup"><span data-stu-id="97e72-157">Require WiFi for IP Audio and/or IP Video</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="97e72-158">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="97e72-158">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="97e72-159"><a href="lync-server-2013-configuring-mobility-policy.md">Lync Server 2013 でのモビリティポリシーの構成</a></span><span class="sxs-lookup"><span data-stu-id="97e72-159"><a href="lync-server-2013-configuring-mobility-policy.md">Configuring mobility policy in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

