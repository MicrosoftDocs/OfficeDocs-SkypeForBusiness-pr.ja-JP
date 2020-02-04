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
ms.openlocfilehash: c6f9f7994981a860aaa02d4674d6a3248c3593d6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762595"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-mobility-in-lync-server-2013"></a><span data-ttu-id="de45c-102">Lync Server 2013 のモビリティの展開プロセス</span><span class="sxs-lookup"><span data-stu-id="de45c-102">Deployment process for mobility in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="de45c-103">_**最終更新日:** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="de45c-103">_**Topic Last Modified:** 2013-02-19_</span></span>

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013. It is noted accordingly.

<span data-ttu-id="de45c-104">このセクションでは、Lync Server 2013 モビリティ機能の展開に必要な一連の手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="de45c-104">This section describes the sequence of steps required to deploy the Lync Server 2013 mobility feature.</span></span>

### <a name="mobility-deployment-process"></a><span data-ttu-id="de45c-105">モバイル展開プロセス</span><span class="sxs-lookup"><span data-stu-id="de45c-105">Mobility Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="de45c-106">段階</span><span class="sxs-lookup"><span data-stu-id="de45c-106">Phase</span></span></th>
<th><span data-ttu-id="de45c-107">ステップ</span><span class="sxs-lookup"><span data-stu-id="de45c-107">Steps</span></span></th>
<th><span data-ttu-id="de45c-108">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="de45c-108">Permissions</span></span></th>
<th><span data-ttu-id="de45c-109">「展開」のドキュメント</span><span class="sxs-lookup"><span data-stu-id="de45c-109">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="de45c-110">ドメインネームシステム (DNS) レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="de45c-110">Create Domain Name System (DNS) records</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="de45c-111">内部の自動検出サービス URL を解決する内部 DNS CNAME または A (IPv6、AAAA) レコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="de45c-111">Create an internal DNS CNAME or A (host, if IPv6, AAAA) record to resolve the internal Autodiscover Service URL.</span></span></p></li>
<li><p><span data-ttu-id="de45c-112">外部の自動検出サービス URL を解決するには、外部 DNS CNAME または A (IPv6、AAAA) レコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="de45c-112">Create an external DNS CNAME or A (host, if IPv6, AAAA) record to resolve the external Autodiscover Service URL.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="de45c-113">Domain Admins</span><span class="sxs-lookup"><span data-stu-id="de45c-113">Domain Admins</span></span></p>
<p><span data-ttu-id="de45c-114">DnsAdmins</span><span class="sxs-lookup"><span data-stu-id="de45c-114">DnsAdmins</span></span></p></td>
<td><p><span data-ttu-id="de45c-115"><a href="lync-server-2013-creating-dns-records-for-the-autodiscover-service.md">Lync Server 2013 での自動検出サービスの DNS レコードの作成</a></span><span class="sxs-lookup"><span data-stu-id="de45c-115"><a href="lync-server-2013-creating-dns-records-for-the-autodiscover-service.md">Creating DNS records for the Autodiscover Service in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="de45c-116">証明書を変更する</span><span class="sxs-lookup"><span data-stu-id="de45c-116">Modify certificates</span></span></p></td>
<td><p><span data-ttu-id="de45c-117">モバイルユーザーへのセキュリティで保護された接続をサポートするために、次の証明書にサブジェクト代替名のエントリを追加します。</span><span class="sxs-lookup"><span data-stu-id="de45c-117">Add subject alternative name entries to the following certificates to support secure connections for mobile users:</span></span></p>
<ul>
<li><p><span data-ttu-id="de45c-118">ディレクター証明書</span><span class="sxs-lookup"><span data-stu-id="de45c-118">Director certificate</span></span></p></li>
<li><p><span data-ttu-id="de45c-119">フロントエンドプールの証明書</span><span class="sxs-lookup"><span data-stu-id="de45c-119">Front End pool certificate</span></span></p></li>
<li><p><span data-ttu-id="de45c-120">リバースプロキシ証明書</span><span class="sxs-lookup"><span data-stu-id="de45c-120">Reverse proxy certificate</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="de45c-121">ローカル管理者</span><span class="sxs-lookup"><span data-stu-id="de45c-121">Local administrator</span></span></p></td>
<td><p><span data-ttu-id="de45c-122"><a href="lync-server-2013-modifying-certificates-for-mobility.md">Lync Server 2013 でのモビリティに合わせた証明書の変更</a></span><span class="sxs-lookup"><span data-stu-id="de45c-122"><a href="lync-server-2013-modifying-certificates-for-mobility.md">Modifying certificates for mobility in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="de45c-123">リバース プロキシを構成する</span><span class="sxs-lookup"><span data-stu-id="de45c-123">Configure the reverse proxy</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="de45c-124">サブジェクトの代替名を使用して、セキュリティで保護されたソケットレイヤー (SSL) リスナーに証明書を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="de45c-124">Assign certificates updated with subject alternative names to the Secure Sockets Layer (SSL) Listener.</span></span></p></li>
<li><p><span data-ttu-id="de45c-125">外部自動検出サービス URL の web 公開ルールを再構成します。</span><span class="sxs-lookup"><span data-stu-id="de45c-125">Reconfigure the web publishing rule for the external Autodiscover Service URL.</span></span></p></li>
<li><p><span data-ttu-id="de45c-126">フロントエンドプールの外部の Lync Server 2013 Web サービスの URL に web 発行ルールが存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="de45c-126">Be sure that a web publishing rule exists for the external Lync Server 2013 Web Services URL on your Front End pool.</span></span></p></li>
</ul>
<p><span data-ttu-id="de45c-127">または</span><span class="sxs-lookup"><span data-stu-id="de45c-127">Or</span></span></p>
<ul>
<li><p><span data-ttu-id="de45c-128">最初の自動検出要求に HTTP を使用し、証明書のサブジェクト代替名の一覧を更新しない場合は、新しい web 公開ルールを構成するか、ポート 80 HTTP の既存の公開ルールを再設定します。</span><span class="sxs-lookup"><span data-stu-id="de45c-128">If you choose to use HTTP for the initial Autodiscover request and do not update subject alternative name lists on the certificates, configure a new web publishing rule or reconfigure an existing publishing rule for port 80 HTTP.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="de45c-129">ローカル管理者</span><span class="sxs-lookup"><span data-stu-id="de45c-129">Local administrator</span></span></p></td>
<td><p><span data-ttu-id="de45c-130"><a href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Lync Server 2013 での、モビリティに合わせたリバース プロキシの構成</a></span><span class="sxs-lookup"><span data-stu-id="de45c-130"><a href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Configuring the reverse proxy for mobility in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="de45c-131">Mcx Mobility Service を使用して Lync 2010 Mobile のモバイル展開をテストする</span><span class="sxs-lookup"><span data-stu-id="de45c-131">Test your mobility deployment for Lync 2010 Mobile using the Mcx Mobility Service</span></span></p></td>
<td><p><span data-ttu-id="de45c-132"><strong>CsMcxP2PIM</strong>を実行して、1人のユーザーから別のユーザーへのインスタントメッセージの送信をテストします。</span><span class="sxs-lookup"><span data-stu-id="de45c-132">Run <strong>Test-CsMcxP2PIM</strong> to test sending an instant message from one person to another.</span></span></p>
<p><span data-ttu-id="de45c-133">オプションの完全な一覧については、「 <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM">CsMcxP2PIM</a>の Lync Server 管理シェルコマンドレット」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="de45c-133">See the Lync Server Management Shell cmdlet documentation for <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM">Test-CsMcxP2PIM</a> for a complete list of options.</span></span></p></td>
<td><p><span data-ttu-id="de45c-134">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="de45c-134">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="de45c-135"><a href="lync-server-2013-verifying-your-mobility-deployment.md">Lync Server 2013 でのモビリティ展開の確認</a></span><span class="sxs-lookup"><span data-stu-id="de45c-135"><a href="lync-server-2013-verifying-your-mobility-deployment.md">Verifying your mobility deployment in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="de45c-136">UCWA Web コンポーネントを使用して Lync 2013 モバイルクライアント用のモバイル展開をテストする</span><span class="sxs-lookup"><span data-stu-id="de45c-136">Test your mobility deployment for Lync 2013 Mobile clients using the UCWA Web components</span></span></p></td>
<td><p><span data-ttu-id="de45c-137"><strong>CsUcwaConference</strong>コマンドレットを使用して、事前に定義されたテストユーザーまたは実際のユーザーが ucwa を使用して会議を作成し、参加できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="de45c-137">Use the <strong>Test-CsUcwaConference</strong> cmdlet to test and verify that pre-defined test users or a pair of actual users can use UCWA to create and participate in a conference.</span></span></p>
<p><span data-ttu-id="de45c-138">オプションの完全な一覧については、「 <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference">CsUcwaConference</a>の Lync Server 管理シェルコマンドレット」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="de45c-138">See the Lync Server Management Shell cmdlet documentation for <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference">Test-CsUcwaConference</a> for a complete list of options.</span></span></p></td>
<td><p><span data-ttu-id="de45c-139">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="de45c-139">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="de45c-140"><a href="lync-server-2013-verifying-your-mobility-deployment.md">Lync Server 2013 でのモビリティ展開の確認</a></span><span class="sxs-lookup"><span data-stu-id="de45c-140"><a href="lync-server-2013-verifying-your-mobility-deployment.md">Verifying your mobility deployment in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="de45c-141">プッシュ通知を構成する</span><span class="sxs-lookup"><span data-stu-id="de45c-141">Configure for push notifications</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="de45c-142">Lync Server 2013 Edge サーバーの場合は、Lync Server online ホスティングプロバイダーを追加して、ホスティングプロバイダーフェデレーションを構成します。</span><span class="sxs-lookup"><span data-stu-id="de45c-142">For Lync Server 2013 Edge Servers, add a Lync Server online hosting provider and configure hosting provider federation.</span></span></p></li>
<li><p><span data-ttu-id="de45c-143">Lync Server 2010 Edge サーバーの場合は、Lync Server online ホスティングプロバイダーを追加して、ホスティングプロバイダーフェデレーションを構成します。</span><span class="sxs-lookup"><span data-stu-id="de45c-143">For Lync Server 2010  Edge Servers, add a Lync Server online hosting provider and configure hosting provider federation.</span></span></p></li>
<li><p><span data-ttu-id="de45c-144">Office Communications Server 2007 R2 Edge サーバーの場合は、フェデレーションパートナーを追加します。</span><span class="sxs-lookup"><span data-stu-id="de45c-144">For Office Communications Server 2007 R2 Edge Servers, add a federated partner.</span></span></p></li>
<li><p><span data-ttu-id="de45c-145">Wi-fi ネットワーク経由でのプッシュ通知をサポートする場合は、TCP ポート5223用のファイアウォール規則を構成します。</span><span class="sxs-lookup"><span data-stu-id="de45c-145">If you want to support push notifications over a Wi-Fi network, configure a firewall rule outbound for TCP port 5223.</span></span></p></li>
<li><p><span data-ttu-id="de45c-146"><strong>Set-cspの設定</strong>コマンドレットを使用して、Apple Push notification SERVICE (APNS) と Microsoft プッシュ通知サービス (MPNS) へのプッシュ通知を有効にします。</span><span class="sxs-lookup"><span data-stu-id="de45c-146">Use the <strong>Set-CsPushNotificationConfiguration</strong> cmdlet to enable push notifications to the Apple Push Notification Service (APNS) and Microsoft Push Notification Service (MPNS).</span></span> <span data-ttu-id="de45c-147">この機能は既定では無効になっています。</span><span class="sxs-lookup"><span data-stu-id="de45c-147">This feature is disabled by default.</span></span></p></li>
<li><p><span data-ttu-id="de45c-148"><strong>CsFederatedPartner</strong>コマンドレットを使用して、フェデレーション構成とテスト用<strong>CsMCXPushNotification</strong>コマンドレットをテストして、プッシュ通知をテストします。</span><span class="sxs-lookup"><span data-stu-id="de45c-148">Use the <strong>Test-CsFederatedPartner</strong> cmdlet to test the federation configuration and the <strong>Test-CsMCXPushNotification</strong> cmdlet to test push notifications.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="de45c-149">Apple デバイスと Windows Phone での Lync 2010 モバイルクライアントでは、プッシュ通知が使われます。</span><span class="sxs-lookup"><span data-stu-id="de45c-149">Push notifications are used for Lync 2010 Mobile clients on Apple devices and Windows Phone</span></span><BR><span data-ttu-id="de45c-150">Windows Phone のみの Lync 2013 モバイルクライアントでプッシュ通知が必要</span><span class="sxs-lookup"><span data-stu-id="de45c-150">Push notification is required for Lync 2013 Mobile clients on Windows Phone only</span></span>


</div></li>
</ul></td>
<td><p><span data-ttu-id="de45c-151">RtcUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="de45c-151">RtcUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="de45c-152"><a href="lync-server-2013-configuring-for-push-notifications.md">Lync Server 2013 でプッシュ通知を構成する</a></span><span class="sxs-lookup"><span data-stu-id="de45c-152"><a href="lync-server-2013-configuring-for-push-notifications.md">Configuring for push notifications in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="de45c-153">モビリティポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="de45c-153">Configure mobility policy</span></span></p></td>
<td><p><span data-ttu-id="de45c-154"><strong>Set-csmobilitypolicy</strong>コマンドレットを使用して、次の操作を許可または禁止します。</span><span class="sxs-lookup"><span data-stu-id="de45c-154">Use the <strong>Set-CsMobilityPolicy</strong> cmdlet to allow or disallow:</span></span></p>
<ul>
<li><p><span data-ttu-id="de45c-155">勤務先から通話</span><span class="sxs-lookup"><span data-stu-id="de45c-155">Call via Work</span></span></p></li>
<li><p><span data-ttu-id="de45c-156">IP オーディオと IP ビデオを有効にする</span><span class="sxs-lookup"><span data-stu-id="de45c-156">Enable IP Audio and IP Video</span></span></p></li>
<li><p><span data-ttu-id="de45c-157">[IP オーディオまたは IP ビデオに WiFi を使用する]</span><span class="sxs-lookup"><span data-stu-id="de45c-157">Require WiFi for IP Audio and/or IP Video</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="de45c-158">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="de45c-158">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="de45c-159"><a href="lync-server-2013-configuring-mobility-policy.md">Lync Server 2013 でのモビリティ ポリシーの構成</a></span><span class="sxs-lookup"><span data-stu-id="de45c-159"><a href="lync-server-2013-configuring-mobility-policy.md">Configuring mobility policy in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

