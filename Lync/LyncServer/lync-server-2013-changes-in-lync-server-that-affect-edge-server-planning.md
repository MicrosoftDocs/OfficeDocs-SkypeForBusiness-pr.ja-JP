---
title: 'Lync server 2013: エッジサーバーの計画に影響する Lync Server の変更点'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changes in Lync Server 2013 that affect Edge Server planning
ms:assetid: 66305160-c9b8-4bc4-9f24-8ee8d9a294f7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204965(v=OCS.15)
ms:contentKeyID: 48184378
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2903bd2701ac860232dd73342ed280688feac34b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188000"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="changes-in-lync-server-2013-that-affect-edge-server-planning"></a><span data-ttu-id="5926e-102">エッジサーバーの計画に影響する Lync Server 2013 の変更点</span><span class="sxs-lookup"><span data-stu-id="5926e-102">Changes in Lync Server 2013 that affect Edge Server planning</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5926e-103">_**トピックの最終更新日:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="5926e-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="5926e-104">Lync Server 2013 には、ユーザーの機能や通信方法を拡張する新機能が導入されています。</span><span class="sxs-lookup"><span data-stu-id="5926e-104">Lync Server 2013 introduces new features that extend the features and communications methods for your users.</span></span> <span data-ttu-id="5926e-105">また、Lync Server 2013 では、組織で使用できるサービスをより適切に統合および拡張するための既存のサービスへの変更が導入されています。</span><span class="sxs-lookup"><span data-stu-id="5926e-105">Also, Lync Server 2013 introduces changes to existing services to better integrate and extend the services that are available to your organization.</span></span> <span data-ttu-id="5926e-106">Lync Server 2013 エッジサーバーサービスの計画と展開に影響する可能性のある変更の概要を次に示します。</span><span class="sxs-lookup"><span data-stu-id="5926e-106">Following is a summary of changes that may affect your planning and deployment of Lync Server 2013 Edge Server services.</span></span>

<div>

## <a name="support-for-ipv6-addressing"></a><span data-ttu-id="5926e-107">IPv6 アドレス指定のサポート</span><span class="sxs-lookup"><span data-stu-id="5926e-107">Support for IPv6 Addressing</span></span>

<span data-ttu-id="5926e-108">Lync Server 2013 は、すべてのエッジサーバーサービスの IPv6 アドレスをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="5926e-108">Lync Server 2013 supports IPv6 addressing for all Edge Server services.</span></span> <span data-ttu-id="5926e-109">Windows Server の構成を使用してインターフェイスの IPv6 アドレスを指定した場合は、トポロジビルダーの IP アドレス構成を使用して、エッジサーバー構成で IPv6 アドレスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="5926e-109">If you have provided IPv6 addresses for the interfaces through configuration in Windows Server, you can use IPv6 addresses in your Edge Server configuration through the IP address configuration in Topology Builder.</span></span> <span data-ttu-id="5926e-110">さらに、XMPP (Extensible Messaging and Presence Protocol) も IPv6 をサポートします。</span><span class="sxs-lookup"><span data-stu-id="5926e-110">Additionally, the extensible messaging and presence protocol (XMPP) supports IPv6.</span></span> <span data-ttu-id="5926e-111">追加構成は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="5926e-111">No additional configuration is required.</span></span> <span data-ttu-id="5926e-112">トポロジで IPv6 を構成すると、XMPP で IPv6 が使用されます (必要な場合)。</span><span class="sxs-lookup"><span data-stu-id="5926e-112">If IPv6 is configured in the topology, XMPP will use IPv6 (where required).</span></span>

<span data-ttu-id="5926e-113">Lync Server 2013 で IPv6 をサポートするための追加の要件は、検出して IPv6 アドレスに解決する必要があるレコードのドメインネームシステムレコードを作成することです。</span><span class="sxs-lookup"><span data-stu-id="5926e-113">An added requirement to support IPv6 in Lync Server 2013 is to create domain name system records for records that must be discovered and resolved to an IPv6 address.</span></span> <span data-ttu-id="5926e-114">IPv6 DNS は、**AAAA** と定義され、"quad-A" と呼ばれるホスト レコードを使用します。</span><span class="sxs-lookup"><span data-stu-id="5926e-114">IPv6 DNS uses host records that are defined as **AAAA** and called “quad-A”.</span></span> <span data-ttu-id="5926e-115">他のレコードの種類は、IPv4 の対応する種類と一致します。</span><span class="sxs-lookup"><span data-stu-id="5926e-115">Other record types are consistent with their IPv4 counterparts.</span></span>

</div>

<div>

## <a name="support-for-extensible-messaging-and-presence-protocol-xmpp-deployment"></a><span data-ttu-id="5926e-116">XMPP (Extensible Messaging and Presence Protocol) 展開のサポート</span><span class="sxs-lookup"><span data-stu-id="5926e-116">Support for Extensible Messaging and Presence Protocol (XMPP) Deployment</span></span>

<span data-ttu-id="5926e-117">エッジサーバーでは、完全に統合された XMPP プロキシ (エッジサーバーに展開される) と XMPP ゲートウェイ (フロントエンドサーバーに展開される) が導入されています。</span><span class="sxs-lookup"><span data-stu-id="5926e-117">Edge Server introduces a fully integrated XMPP proxy (deployed on the Edge Servers) and an XMPP gateway (deployed on your Front End Servers).</span></span> <span data-ttu-id="5926e-118">オプションのコンポーネントとして XMPP フェデレーションを展開できます。</span><span class="sxs-lookup"><span data-stu-id="5926e-118">You can deploy XMPP federation as an optional component.</span></span> <span data-ttu-id="5926e-119">XMPP プロキシと XMPP ゲートウェイを追加して構成することで、Microsoft Lync 2013 ユーザーがインスタントメッセージング (IM) とプレゼンスの XMPP ベースのパートナーから連絡先を追加できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="5926e-119">By adding and configuring the XMPP proxy and XMPP gateway, you can enable your Microsoft Lync 2013 users to add contacts from XMPP-based partners for instant messaging (IM) and presence.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5926e-120">現時点では、エッジサーバーの XMPP サービスでは、Lync Server クライアントと XMPP ベースの連絡先の間で IM とプレゼンスのみが提供されています。</span><span class="sxs-lookup"><span data-stu-id="5926e-120">Currently, the XMPP services in Edge Server only provide IM and presence between Lync Server clients and XMPP-based contacts.</span></span> <span data-ttu-id="5926e-121">さらに、XMPP は 1 つのサイトでのみホストされます。</span><span class="sxs-lookup"><span data-stu-id="5926e-121">Additionally, XMPP is hosted in only one site.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="5926e-p106">Lync Server 2013 の XMPP 機能は、Google Talk とのインスタント メッセージングのフェデレーションについては Microsoft によってテストとサポートが行われています。その他の XMPP システムについては、Lync Server 2013 とのフェデレーションのサポートや、展開またはトラブルシューティングの推奨事項に関して、サード パーティ ベンダーに問い合わせて確認してください。</span><span class="sxs-lookup"><span data-stu-id="5926e-p106">The XMPP capability of Lync Server 2013 is tested and supported by Microsoft for instant messaging federation with Google Talk. For any other XMPP systems contact the third-party vendor to verify that they support federation with Lync Server 2013, and for any deployment or troubleshooting recommendations.</span></span>



</div>

</div>

<div>

## <a name="support-for-rolling-audiovideo-authentication-and-server-to-server-authentication-certificates"></a><span data-ttu-id="5926e-124">音声ビデオ認証証明書およびサーバー間認証証明書のサポート</span><span class="sxs-lookup"><span data-stu-id="5926e-124">Support for Rolling Audio/Video Authentication and Server to Server Authentication Certificates</span></span>

<span data-ttu-id="5926e-p107">証明書は、音声ビデオ認証サービスのクライアントおよび他のコンシューマーに対して発行されるトークンを生成するため、およびサーバー間認証のために使用されます。音声ビデオ認証証明書の種類は AudioVideoAuthentication\*\* であり、サーバー間認証証明書の種類は OAuthTokenIssuer です。\*\*</span><span class="sxs-lookup"><span data-stu-id="5926e-p107">A certificate is used to generate tokens that are issued to clients and other consumers of the A/V Authentication service and for server to server authentication. The Audio/Video Authentication certificate is of type *AudioVideoAuthentication* and the Server to Server Authentication certificate is of type *OAuthTokenIssuer*.</span></span>

<span data-ttu-id="5926e-p108">音声ビデオ認証では、トークンを使用してポート割り当て要求が認証されます。このトークンは、最大 8 時間 (トークンの既定のライフタイム)、キャッシュされます。通常の操作では、これは、認証マテリアルを作成して音声ビデオ コンシューマーに配布するための非常に信頼できる方法です。ただし、証明書のライフタイムは有限であり、あらかじめ定義された日時に期限切れになります (日時は作成日と、証明書を作成した証明機関で採用されているポリシーに基づきます。この種類の証明書は、通常は 2 年間有効です）。証明書が期限切れになると、期限切れになった証明書によって作成され、コンシューマーによってキャッシュされたすべてのトークンは無効になります。期限切れの証明書によって作成されたトークンを使用しようとすると、メディア リレーの割り当てが失敗し、現在の音声ビデオ セッションが失敗します。クライアントが通常の音声ビデオ機能を再開するには、有効な証明書によって作成された新しいトークンを取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5926e-p108">For Audio/Video Authentication, tokens are used to authenticate port allocation requests, and the tokens are cached for up to 8 hours – the default lifetime of the token. Under normal operation, this is a very reliable method to create and distribute authentication material to the A/V consumers. However, certificates have a finite lifetime and expire on a predefined date and time (based on creation date and the policies enforced at the certification authority that created the certificate, typically 2 years for this type of certificate). When the certificate expires, any tokens created by the expired certificate and cached by consumers become not valid. Any attempts to use a token created with an expired certificate would result in failed Media Relay allocations and any current Audio/Video sessions will fail. The client would need to acquire a new token created by a valid certificate to resume normal Audio and Video functionality.</span></span>

<span data-ttu-id="5926e-133">サーバー間認証は、展開内のすべてのサーバーに対して要求され、適用されるグローバル証明書によって管理されます。</span><span class="sxs-lookup"><span data-stu-id="5926e-133">Server to Server Authentication is managed by a global certificate that is requested and applied to all servers in the deployment.</span></span> <span data-ttu-id="5926e-134">この証明書は、Lync Server 2013 のサーバーの認証と、Exchange 2013 および Microsoft SharePoint Server 2013 への認証を担当します。</span><span class="sxs-lookup"><span data-stu-id="5926e-134">The certificate is responsible for authenticating servers in Lync Server 2013 as well as authenticating to Exchange 2013 and Microsoft SharePoint Server 2013.</span></span> <span data-ttu-id="5926e-135">サーバー間認証のしくみの詳細については、「 [Lync server 2013 でのサーバー間認証 (OAuth) およびパートナーアプリケーションの管理](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5926e-135">For more information on how Server to Server Authentication works, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md).</span></span> <span data-ttu-id="5926e-136">音声ビデオ認証プロセスとサーバー間認証プロセスの非常に重要な相違点は、認証 (トークン) のライフタイムです。</span><span class="sxs-lookup"><span data-stu-id="5926e-136">One very important difference between the Audio/Video Authentication process and the Server to Server Authentication process is the lifetime of the authentication, or tokens.</span></span> <span data-ttu-id="5926e-137">音声ビデオ認証では、認証は 8 時間後に期限が切れます。</span><span class="sxs-lookup"><span data-stu-id="5926e-137">For Audio/Video Authentication, the authentication expires after eight hours.</span></span> <span data-ttu-id="5926e-138">サーバー間認証のライフタイムは 24 時間です。</span><span class="sxs-lookup"><span data-stu-id="5926e-138">Server-to-Server Authentication has a lifetime of 24 hours.</span></span> <span data-ttu-id="5926e-139">これらの証明書の種類に応じて、計画を立てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="5926e-139">You must plan accordingly for each of the certificate types.</span></span>

<span data-ttu-id="5926e-140">Lync Server 2013 の新機能は、現在の証明書の有効期限が切れる前に、代替の音声/ビデオ認証証明書およびサーバーからサーバーへの認証証明書をステージングできる機能です。</span><span class="sxs-lookup"><span data-stu-id="5926e-140">New for Lync Server 2013 is the ability to stage a replacement Audio/Video Authentication certificate and Server to Server Authentication certificate in advance of the expiration of the current certificate.</span></span> <span data-ttu-id="5926e-141">この操作の後、新しい証明書を使用して、新しいトークンと新しい認証要求が生成されます。</span><span class="sxs-lookup"><span data-stu-id="5926e-141">The new certificate is then used for generating new tokens or new authentication requests.</span></span> <span data-ttu-id="5926e-142">ただし、古い証明書は、現在のセッションと認証を検証するために保持されます。</span><span class="sxs-lookup"><span data-stu-id="5926e-142">but retains the old certificate for verifying the current sessions and authentications..</span></span> <span data-ttu-id="5926e-143">これにより、トークンと証明書の期限切れによるエラーのほぼすべてを効果的に防止できます。</span><span class="sxs-lookup"><span data-stu-id="5926e-143">What this accomplishes is to effectively prevent nearly all failures due to token and certificate expirations.</span></span> <span data-ttu-id="5926e-144">この機能とその構成方法の詳細については、「 [Lync Server 2013 でのステージング AV および OAuth 証明書」を](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)参照してください。</span><span class="sxs-lookup"><span data-stu-id="5926e-144">For details of this feature and how to configure it, see [Staging AV and OAuth certificates in Lync Server 2013 using -Roll in Set-CsCertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)</span></span>

</div>

<div>

## <a name="reduced-reliance-on-cookie-based-affinity"></a><span data-ttu-id="5926e-145">Cookie ベースのアフィニティに対する依存性の低減</span><span class="sxs-lookup"><span data-stu-id="5926e-145">Reduced Reliance on Cookie-based Affinity</span></span>

<span data-ttu-id="5926e-146">以前のバージョンの Lync Server と Office Communications Server では、Web サービスが cookie ベースのアフィニティを使用して、クライアントと Web サービスのセッション状態が確実に維持されていました。</span><span class="sxs-lookup"><span data-stu-id="5926e-146">In previous versions of Lync Server and Office Communications Server, cookie-based affinity was used by the Web services to ensure that the client and Web services session state was maintained.</span></span> <span data-ttu-id="5926e-147">Lync Server 2013 Web サービスは、cookie ベースのアフィニティのほとんどの要件を排除する組み込みのアフィニティメカニズムを使用します。</span><span class="sxs-lookup"><span data-stu-id="5926e-147">Lync Server 2013 Web services use a built in affinity mechanism that eliminates most of the requirements for cookie-based affinity.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="5926e-148">Microsoft Lync 2010 モバイルクライアントは依然として cookie ベースのアフィニティを使用する必要があります。すべてのクライアントを今後の Microsoft Lync Mobile クライアントに移行するまでは、cookie ベースのアフィニティを構成する必要があります (リリースされていない日付はまだ確定していません)。</span><span class="sxs-lookup"><span data-stu-id="5926e-148">The Microsoft Lync 2010 Mobile client must still use cookie-based affinity and will require configuration of cookie-based affinity until you have migrated all clients to the upcoming Microsoft Lync Mobile client (Date of release not yet determined).</span></span>



</div>

<span data-ttu-id="5926e-149">Lync Server 2013 における cookie ベースのアフィニティの詳細については、「 [Lync server 2013 での外部ユーザーアクセスに必要なコンポーネント](lync-server-2013-components-required-for-external-user-access.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5926e-149">For details about cookie-based affinity in Lync Server 2013, see [Components required for external user access in Lync Server 2013](lync-server-2013-components-required-for-external-user-access.md).</span></span>

</div>

<div>

## <a name="autodiscover-enhancements"></a><span data-ttu-id="5926e-150">自動検出の拡張</span><span class="sxs-lookup"><span data-stu-id="5926e-150">AutoDiscover Enhancements</span></span>

<span data-ttu-id="5926e-151">Lync Server 2013 の自動検出機能を使用すると、クライアントは通信に使用できるその他の機能を検索できます。</span><span class="sxs-lookup"><span data-stu-id="5926e-151">The autodiscover feature in Lync Server 2013 enables clients to locate additional features that are made available for communication.</span></span> <span data-ttu-id="5926e-152">自動検出は、Lync Server 2010 用の累積的な更新プログラム (2011 年11月、モビリティと Microsoft Lync 2010 Mobile) で初めて導入されました。</span><span class="sxs-lookup"><span data-stu-id="5926e-152">Autodiscover was first introduced in the cumulative update for Lync Server 2010: November 2011 for Mobility and Microsoft Lync 2010 Mobile.</span></span> <span data-ttu-id="5926e-153">自動検出機能 (DNS レコード名 LyncDiscover および LyncDiscoverInternal によっても知られています) を使用すると、クライアントはモビリティサービス (Microsoft Lync 2010 モバイルクライアントの場合)、Microsoft Lync Web App、および Lync Web スケジューラを検索して使用することができます。およびMicrosoft Exchange Server および SharePoint Server との通信。</span><span class="sxs-lookup"><span data-stu-id="5926e-153">The autodiscover feature (also known by the DNS record names LyncDiscover and LyncDiscoverInternal) allows clients to locate and use mobility services (for Microsoft Lync 2010 Mobile clients), the Microsoft Lync Web App, and the Lync Web scheduler, as well as communications with Microsoft Exchange Server and SharePoint Server.</span></span> <span data-ttu-id="5926e-154">自動検出は、インフラストラクチャおよび Lync Server 2013 サーバーのセットアップと展開の通常の一部としてインストールされます。</span><span class="sxs-lookup"><span data-stu-id="5926e-154">Autodiscover is installed as normal part of the setup and deployment of your infrastructure and Lync Server 2013 servers.</span></span> <span data-ttu-id="5926e-155">トポロジビルダーおよび Lync Server 展開ウィザードは、Lync Server 2010 の累積的な更新プログラム (11 月 2011) で必要だった構成タスクの大部分を排除します。</span><span class="sxs-lookup"><span data-stu-id="5926e-155">The Topology Builder and Lync Server Deployment Wizard eliminate most of the configuration tasks that were required in cumulative update for Lync Server 2010: November 2011.</span></span>

</div>

<div>

## <a name="services-for-mobile-clients"></a><span data-ttu-id="5926e-156">モバイル クライアントに対するサービス</span><span class="sxs-lookup"><span data-stu-id="5926e-156">Services for Mobile Clients</span></span>

<span data-ttu-id="5926e-157">Lync Server 2010 の累積的な更新プログラム (2011 年11月) で導入されました。 lync Server 2013 のモビリティサービスを使用すると、サポートされている Apple iOS、Android、Windows Phone、または Nokia のモバイルデバイスを使用して、Lync Mobile およびタブレットデバイスを実行している携帯電話を利用できます。インスタントメッセージの送受信、連絡先の表示、プレゼンスの表示などのアクティビティ。</span><span class="sxs-lookup"><span data-stu-id="5926e-157">Introduced in the cumulative update for Lync Server 2010: November 2011, mobility services in Lync Server 2013 enable mobile phones running Lync Mobile and tablet devices using supported Apple iOS, Android, Windows Phone, or Nokia mobile devices to perform activities such as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span> <span data-ttu-id="5926e-158">また、クリックして会議に参加、勤務先から通話、同一番号接続、ボイス メール、不在着信など、いくつかのエンタープライズ VoIP 機能もサポートされます。</span><span class="sxs-lookup"><span data-stu-id="5926e-158">In addition, mobile devices support some Enterprise Voice features, such as click to join a conference, Call via Work, single number reach, voice mail, and missed call notification.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5926e-159">モビリティ サービスは、フロントエンド サーバーに展開されたリバース プロキシと公開されたサービスを使用します。</span><span class="sxs-lookup"><span data-stu-id="5926e-159">The mobility services use the reverse proxy and published services that are deployed on your Front End Servers.</span></span> <span data-ttu-id="5926e-160">エッジ サーバーの変更は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="5926e-160">No changes are required to Edge Servers.</span></span> <span data-ttu-id="5926e-161">少なくとも、Lync Server アクセスエッジサービスを実行しているサーバーからの送信 SIP/TCP/5061from 必要です。</span><span class="sxs-lookup"><span data-stu-id="5926e-161">Minimally you need outbound SIP/TCP/5061from the server running the Lync Server Access Edge service.</span></span>



</div>

</div>

<div>

## <a name="director-role-is-optional"></a><span data-ttu-id="5926e-162">ディレクターの役割はオプション</span><span class="sxs-lookup"><span data-stu-id="5926e-162">Director Role is Optional</span></span>

<span data-ttu-id="5926e-163">Lync Server 2013 トポロジ内のディレクターサーバーの役割は変更されていません。</span><span class="sxs-lookup"><span data-stu-id="5926e-163">The role of the Director server in the Lync Server 2013 topology has not changed.</span></span> <span data-ttu-id="5926e-164">これまでと同様、Web サービスをホストし、ユーザーからの要求を事前認証し、外部ユーザーをそれぞれのホーム プールに導きます。</span><span class="sxs-lookup"><span data-stu-id="5926e-164">It still hosts web services, preauthenticates incoming user requests, and directs external users to their home pool.</span></span> <span data-ttu-id="5926e-165">推奨される役割からオプションの役割にディレクターを変更することで、Microsoft はディレクターの価値を減少することを意図したものではありません。</span><span class="sxs-lookup"><span data-stu-id="5926e-165">By changing the Director from a recommended role to an optional role, Microsoft does not intend to diminish the value of the Director.</span></span> <span data-ttu-id="5926e-166">この目的は、機能を損なうことなく、サーバー数とその他のハードウェア要件 (ディレクターのハードウェアロードバランサーなど) を削減することです。</span><span class="sxs-lookup"><span data-stu-id="5926e-166">The intention is to reduce server count and other hardware requirements (for example, hardware load balancers for the Director) without compromising features and functionality.</span></span> <span data-ttu-id="5926e-167">フロントエンドサーバーは、提供されるサービスに影響を与えることなく、ディレクターと同じジョブを実行できるため、ディレクターを展開することができます。</span><span class="sxs-lookup"><span data-stu-id="5926e-167">Because the Front End Servers can do the same job as the Director with no impact to services provided, you can deploy Directors if you choose to.</span></span> <span data-ttu-id="5926e-168">フロントエンドサーバーがディレクターの代わりに同じサービスを提供するという自信を持ってディレクターを除外することができます。</span><span class="sxs-lookup"><span data-stu-id="5926e-168">You can safely exclude the Director with confidence that the Front End Servers will provide the same services in place of a Director.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

