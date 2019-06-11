---
title: 'Lync Server 2013: エッジ サーバーの計画に影響する Lync Server 2013 での変更点'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Changes in Lync Server 2013 that affect Edge Server planning
ms:assetid: 66305160-c9b8-4bc4-9f24-8ee8d9a294f7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204965(v=OCS.15)
ms:contentKeyID: 48184378
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 71d13b40430455c87a60c0fadc20980df5a8aa1b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840612"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-in-lync-server-2013-that-affect-edge-server-planning"></a><span data-ttu-id="073af-102">エッジ サーバーの計画に影響する Lync Server 2013 での変更点</span><span class="sxs-lookup"><span data-stu-id="073af-102">Changes in Lync Server 2013 that affect Edge Server planning</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="073af-103">_**最終更新日:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="073af-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="073af-104">Lync Server 2013 には、ユーザーの機能と通信方法を拡張する新機能が導入されています。</span><span class="sxs-lookup"><span data-stu-id="073af-104">Lync Server 2013 introduces new features that extend the features and communications methods for your users.</span></span> <span data-ttu-id="073af-105">また、Lync Server 2013 では、組織で利用できるサービスをより適切に統合および拡張するために、既存のサービスへの変更が導入されています。</span><span class="sxs-lookup"><span data-stu-id="073af-105">Also, Lync Server 2013 introduces changes to existing services to better integrate and extend the services that are available to your organization.</span></span> <span data-ttu-id="073af-106">以下は、Lync Server 2013 Edge Server サービスの計画と展開に影響を与える可能性のある変更内容をまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="073af-106">Following is a summary of changes that may affect your planning and deployment of Lync Server 2013 Edge Server services.</span></span>

<div>

## <a name="support-for-ipv6-addressing"></a><span data-ttu-id="073af-107">IPv6 アドレス指定のサポート</span><span class="sxs-lookup"><span data-stu-id="073af-107">Support for IPv6 Addressing</span></span>

<span data-ttu-id="073af-108">Lync Server 2013 は、すべての Edge Server サービスの IPv6 アドレス指定をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="073af-108">Lync Server 2013 supports IPv6 addressing for all Edge Server services.</span></span> <span data-ttu-id="073af-109">Windows Server の構成を通じてインターフェイスの IPv6 アドレスを指定している場合は、トポロジビルダーの IP アドレス構成を使用して、エッジサーバー構成の IPv6 アドレスを使うことができます。</span><span class="sxs-lookup"><span data-stu-id="073af-109">If you have provided IPv6 addresses for the interfaces through configuration in Windows Server, you can use IPv6 addresses in your Edge Server configuration through the IP address configuration in Topology Builder.</span></span> <span data-ttu-id="073af-110">さらに、拡張メッセージングとプレゼンスプロトコル (XMPP) は IPv6 をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="073af-110">Additionally, the extensible messaging and presence protocol (XMPP) supports IPv6.</span></span> <span data-ttu-id="073af-111">追加の構成は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="073af-111">No additional configuration is required.</span></span> <span data-ttu-id="073af-112">IPv6 がトポロジで構成されている場合、XMPP は IPv6 を使用します (必要な場合)。</span><span class="sxs-lookup"><span data-stu-id="073af-112">If IPv6 is configured in the topology, XMPP will use IPv6 (where required).</span></span>

<span data-ttu-id="073af-113">Lync Server 2013 で IPv6 をサポートするための追加の要件として、IPv6 アドレスを検出し、解決する必要があるレコードのドメインネームシステムレコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="073af-113">An added requirement to support IPv6 in Lync Server 2013 is to create domain name system records for records that must be discovered and resolved to an IPv6 address.</span></span> <span data-ttu-id="073af-114">IPv6 DNS は、 **AAAA**と呼ばれるホストレコードと "クワッド-A" を使用します。</span><span class="sxs-lookup"><span data-stu-id="073af-114">IPv6 DNS uses host records that are defined as **AAAA** and called “quad-A”.</span></span> <span data-ttu-id="073af-115">その他の種類のレコードは、IPv4 に対応しています。</span><span class="sxs-lookup"><span data-stu-id="073af-115">Other record types are consistent with their IPv4 counterparts.</span></span>

</div>

<div>

## <a name="support-for-extensible-messaging-and-presence-protocol-xmpp-deployment"></a><span data-ttu-id="073af-116">拡張メッセージングとプレゼンスプロトコル (XMPP) 展開のサポート</span><span class="sxs-lookup"><span data-stu-id="073af-116">Support for Extensible Messaging and Presence Protocol (XMPP) Deployment</span></span>

<span data-ttu-id="073af-117">エッジサーバーでは、完全に統合された XMPP プロキシ (エッジサーバーに展開されている) と XMPP ゲートウェイ (フロントエンドサーバーに展開されている) が導入されています。</span><span class="sxs-lookup"><span data-stu-id="073af-117">Edge Server introduces a fully integrated XMPP proxy (deployed on the Edge Servers) and an XMPP gateway (deployed on your Front End Servers).</span></span> <span data-ttu-id="073af-118">XMPP フェデレーションは、オプションのコンポーネントとして展開できます。</span><span class="sxs-lookup"><span data-stu-id="073af-118">You can deploy XMPP federation as an optional component.</span></span> <span data-ttu-id="073af-119">XMPP プロキシと XMPP ゲートウェイを追加して構成することにより、Microsoft Lync 2013 ユーザーは、インスタントメッセージング (IM) とプレゼンスのために、XMPP ベースのパートナーから連絡先を追加できるようになります。</span><span class="sxs-lookup"><span data-stu-id="073af-119">By adding and configuring the XMPP proxy and XMPP gateway, you can enable your Microsoft Lync 2013 users to add contacts from XMPP-based partners for instant messaging (IM) and presence.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="073af-120">現時点では、Edge Server の XMPP サービスは、Lync Server クライアントと XMPP ベースの連絡先との間で IM とプレゼンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="073af-120">Currently, the XMPP services in Edge Server only provide IM and presence between Lync Server clients and XMPP-based contacts.</span></span> <span data-ttu-id="073af-121">さらに、XMPP は1つのサイトでのみホストされます。</span><span class="sxs-lookup"><span data-stu-id="073af-121">Additionally, XMPP is hosted in only one site.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="073af-p106">Lync Server 2013 の XMPP 機能は、Google Talk とのインスタント メッセージングのフェデレーションについては Microsoft によってテストとサポートが行われています。その他の XMPP システムについては、Lync Server 2013 とのフェデレーションのサポートや、展開またはトラブルシューティングの推奨事項に関して、サード パーティ ベンダーに問い合わせて確認してください。</span><span class="sxs-lookup"><span data-stu-id="073af-p106">The XMPP capability of Lync Server 2013 is tested and supported by Microsoft for instant messaging federation with Google Talk. For any other XMPP systems contact the third-party vendor to verify that they support federation with Lync Server 2013, and for any deployment or troubleshooting recommendations.</span></span>



</div>

</div>

<div>

## <a name="support-for-rolling-audiovideo-authentication-and-server-to-server-authentication-certificates"></a><span data-ttu-id="073af-124">ローリングオーディオ/ビデオ認証とサーバー間認証証明書のサポート</span><span class="sxs-lookup"><span data-stu-id="073af-124">Support for Rolling Audio/Video Authentication and Server to Server Authentication Certificates</span></span>

<span data-ttu-id="073af-125">証明書は、A/V 認証サービスのクライアントおよび他のコンシューマーに対して発行されたトークンを生成するために使用され、サーバー間の認証に使われます。</span><span class="sxs-lookup"><span data-stu-id="073af-125">A certificate is used to generate tokens that are issued to clients and other consumers of the A/V Authentication service and for server to server authentication.</span></span> <span data-ttu-id="073af-126">音声/ビデオ認証証明書は種類が*Audiovideoauthentication*であり、サーバー間認証証明書は*Oauthtokenissuer*型です。</span><span class="sxs-lookup"><span data-stu-id="073af-126">The Audio/Video Authentication certificate is of type *AudioVideoAuthentication* and the Server to Server Authentication certificate is of type *OAuthTokenIssuer*.</span></span>

<span data-ttu-id="073af-127">音声/ビデオ認証の場合、トークンはポート割り当て要求を認証するために使用され、トークンは最大8時間 (トークンの既定の有効期間) キャッシュされます。</span><span class="sxs-lookup"><span data-stu-id="073af-127">For Audio/Video Authentication, tokens are used to authenticate port allocation requests, and the tokens are cached for up to 8 hours – the default lifetime of the token.</span></span> <span data-ttu-id="073af-128">通常の操作では、このメソッドを使うと、認証資料を作成し、A/V コンシューマーに配布することができます。</span><span class="sxs-lookup"><span data-stu-id="073af-128">Under normal operation, this is a very reliable method to create and distribute authentication material to the A/V consumers.</span></span> <span data-ttu-id="073af-129">ただし、証明書には有効期限があり、事前定義された日付と時刻で有効期限が切れています (作成日と、証明書を作成した証明機関によって適用されるポリシー (通常は、この種類の証明書の場合は2年間)。</span><span class="sxs-lookup"><span data-stu-id="073af-129">However, certificates have a finite lifetime and expire on a predefined date and time (based on creation date and the policies enforced at the certification authority that created the certificate, typically 2 years for this type of certificate).</span></span> <span data-ttu-id="073af-130">証明書の有効期限が切れると、有効期限が切れた証明書によって作成され、コンシューマーによってキャッシュされたトークンは有効になりません。</span><span class="sxs-lookup"><span data-stu-id="073af-130">When the certificate expires, any tokens created by the expired certificate and cached by consumers become not valid.</span></span> <span data-ttu-id="073af-131">有効期限が切れた証明書で作成されたトークンを使用しようとすると、メディアリレーの割り当てが失敗し、現在のオーディオ/ビデオセッションは失敗します。</span><span class="sxs-lookup"><span data-stu-id="073af-131">Any attempts to use a token created with an expired certificate would result in failed Media Relay allocations and any current Audio/Video sessions will fail.</span></span> <span data-ttu-id="073af-132">クライアントは、通常の音声とビデオの機能を再開するために、有効な証明書によって作成された新しいトークンを取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="073af-132">The client would need to acquire a new token created by a valid certificate to resume normal Audio and Video functionality.</span></span>

<span data-ttu-id="073af-133">サーバー間認証は、展開されているすべてのサーバーに要求されて適用されるグローバル証明書によって管理されます。</span><span class="sxs-lookup"><span data-stu-id="073af-133">Server to Server Authentication is managed by a global certificate that is requested and applied to all servers in the deployment.</span></span> <span data-ttu-id="073af-134">この証明書は、Lync Server 2013 のサーバーの認証と、Exchange 2013 および Microsoft SharePoint Server 2013 の認証に責任を負います。</span><span class="sxs-lookup"><span data-stu-id="073af-134">The certificate is responsible for authenticating servers in Lync Server 2013 as well as authenticating to Exchange 2013 and Microsoft SharePoint Server 2013.</span></span> <span data-ttu-id="073af-135">サーバー間認証のしくみの詳細については、「 [Lync server 2013 でサーバー間認証 (OAuth) とパートナーアプリケーションを管理](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="073af-135">For more information on how Server to Server Authentication works, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md).</span></span> <span data-ttu-id="073af-136">音声/ビデオ認証プロセスとサーバー間の認証プロセスの間の重要な違いの1つは、認証 (トークン) の有効期間です。</span><span class="sxs-lookup"><span data-stu-id="073af-136">One very important difference between the Audio/Video Authentication process and the Server to Server Authentication process is the lifetime of the authentication, or tokens.</span></span> <span data-ttu-id="073af-137">音声/ビデオ認証の場合、認証は8時間後に期限切れとなります。</span><span class="sxs-lookup"><span data-stu-id="073af-137">For Audio/Video Authentication, the authentication expires after eight hours.</span></span> <span data-ttu-id="073af-138">サーバー間認証には、24時間の有効期限があります。</span><span class="sxs-lookup"><span data-stu-id="073af-138">Server-to-Server Authentication has a lifetime of 24 hours.</span></span> <span data-ttu-id="073af-139">各証明書の種類に応じて計画する必要があります。</span><span class="sxs-lookup"><span data-stu-id="073af-139">You must plan accordingly for each of the certificate types.</span></span>

<span data-ttu-id="073af-140">Lync Server 2013 の新機能として、現在の証明書の有効期限が切れる前に、交換用のオーディオ/ビデオ認証証明書とサーバー認証証明書をステージすることができます。</span><span class="sxs-lookup"><span data-stu-id="073af-140">New for Lync Server 2013 is the ability to stage a replacement Audio/Video Authentication certificate and Server to Server Authentication certificate in advance of the expiration of the current certificate.</span></span> <span data-ttu-id="073af-141">新しい証明書を使って、新しいトークンを生成したり、新しい認証要求を生成したりします。</span><span class="sxs-lookup"><span data-stu-id="073af-141">The new certificate is then used for generating new tokens or new authentication requests.</span></span> <span data-ttu-id="073af-142">ただし、現在のセッションと認証を確認するための古い証明書は保持されます。</span><span class="sxs-lookup"><span data-stu-id="073af-142">but retains the old certificate for verifying the current sessions and authentications..</span></span> <span data-ttu-id="073af-143">これにより、トークンと証明書の有効期限が切れたときに発生したほぼすべての障害を効果的に回避することができます。</span><span class="sxs-lookup"><span data-stu-id="073af-143">What this accomplishes is to effectively prevent nearly all failures due to token and certificate expirations.</span></span> <span data-ttu-id="073af-144">この機能と構成方法の詳細については、「 [Lync Server 2013 でのステージング AV と OAuth 証明書の使用](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="073af-144">For details of this feature and how to configure it, see [Staging AV and OAuth certificates in Lync Server 2013 using -Roll in Set-CsCertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)</span></span>

</div>

<div>

## <a name="reduced-reliance-on-cookie-based-affinity"></a><span data-ttu-id="073af-145">Cookie ベースのアフィニティへの依存度の低下</span><span class="sxs-lookup"><span data-stu-id="073af-145">Reduced Reliance on Cookie-based Affinity</span></span>

<span data-ttu-id="073af-146">以前のバージョンの Lync Server と Office Communications Server では、クライアントと Web サービスのセッション状態が維持されるように、Web サービスによって cookie ベースのアフィニティが使用されていました。</span><span class="sxs-lookup"><span data-stu-id="073af-146">In previous versions of Lync Server and Office Communications Server, cookie-based affinity was used by the Web services to ensure that the client and Web services session state was maintained.</span></span> <span data-ttu-id="073af-147">Lync Server 2013 Web サービスでは、cookie ベースのアフィニティの要件をほとんど解消する組み込みのアフィニティメカニズムを使用します。</span><span class="sxs-lookup"><span data-stu-id="073af-147">Lync Server 2013 Web services use a built in affinity mechanism that eliminates most of the requirements for cookie-based affinity.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="073af-148">Microsoft Lync 2010 モバイルクライアントでは、依然として cookie ベースのアフィニティを使用する必要があります。すべてのクライアントを今後の Microsoft Lync モバイルクライアントに移行するまで、cookie ベースのアフィニティの構成が必要になります (リリース日はまだ確定していません)。</span><span class="sxs-lookup"><span data-stu-id="073af-148">The Microsoft Lync 2010 Mobile client must still use cookie-based affinity and will require configuration of cookie-based affinity until you have migrated all clients to the upcoming Microsoft Lync Mobile client (Date of release not yet determined).</span></span>



</div>

<span data-ttu-id="073af-149">Lync Server 2013 での cookie ベースのアフィニティの詳細については、「 [Lync server 2013 での外部ユーザーアクセスに必要なコンポーネント](lync-server-2013-components-required-for-external-user-access.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="073af-149">For details about cookie-based affinity in Lync Server 2013, see [Components required for external user access in Lync Server 2013](lync-server-2013-components-required-for-external-user-access.md).</span></span>

</div>

<div>

## <a name="autodiscover-enhancements"></a><span data-ttu-id="073af-150">自動検出の拡張機能</span><span class="sxs-lookup"><span data-stu-id="073af-150">AutoDiscover Enhancements</span></span>

<span data-ttu-id="073af-151">Lync Server 2013 の自動検出機能を使用すると、クライアントは通信可能なその他の機能を見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="073af-151">The autodiscover feature in Lync Server 2013 enables clients to locate additional features that are made available for communication.</span></span> <span data-ttu-id="073af-152">自動検出は、Lync Server 2010 の累積的な更新プログラムで導入されました。モビリティと Microsoft Lync 2010 Mobile 用の2011年11月。</span><span class="sxs-lookup"><span data-stu-id="073af-152">Autodiscover was first introduced in the cumulative update for Lync Server 2010: November 2011 for Mobility and Microsoft Lync 2010 Mobile.</span></span> <span data-ttu-id="073af-153">自動検出機能 (DNS レコード名 LyncDiscover と LyncDiscoverInternal にも呼ばれます) を使うと、クライアントはモビリティサービス (Microsoft Lync 2010 モバイルクライアント)、Microsoft Lync Web App、Lync Web scheduler などを検索して使用することができます。Microsoft Exchange Server および SharePoint Server との通信。</span><span class="sxs-lookup"><span data-stu-id="073af-153">The autodiscover feature (also known by the DNS record names LyncDiscover and LyncDiscoverInternal) allows clients to locate and use mobility services (for Microsoft Lync 2010 Mobile clients), the Microsoft Lync Web App, and the Lync Web scheduler, as well as communications with Microsoft Exchange Server and SharePoint Server.</span></span> <span data-ttu-id="073af-154">自動検出は、インフラストラクチャと Lync Server 2013 サーバーのセットアップと展開の通常の部分としてインストールされます。</span><span class="sxs-lookup"><span data-stu-id="073af-154">Autodiscover is installed as normal part of the setup and deployment of your infrastructure and Lync Server 2013 servers.</span></span> <span data-ttu-id="073af-155">トポロジビルダーと Lync Server Deployment ウィザードを使用すると、Lync Server 2010 の累積的な更新プログラムで必要とされる構成タスクのほとんどが、2011年11月に行われなくなります。</span><span class="sxs-lookup"><span data-stu-id="073af-155">The Topology Builder and Lync Server Deployment Wizard eliminate most of the configuration tasks that were required in cumulative update for Lync Server 2010: November 2011.</span></span>

</div>

<div>

## <a name="services-for-mobile-clients"></a><span data-ttu-id="073af-156">モバイルクライアント用のサービス</span><span class="sxs-lookup"><span data-stu-id="073af-156">Services for Mobile Clients</span></span>

<span data-ttu-id="073af-157">Lync Server 2010 の累積的な更新プログラムで導入されています。 Lync Server 2013 のモバイルサービス、Android、Windows Phone、Nokia のモバイルデバイスを使用して、Lync Mobile およびタブレットデバイスを実行している携帯電話を有効にし2011ます。インスタントメッセージの送受信、連絡先の表示、プレゼンスの表示などのアクティビティ。</span><span class="sxs-lookup"><span data-stu-id="073af-157">Introduced in the cumulative update for Lync Server 2010: November 2011, mobility services in Lync Server 2013 enable mobile phones running Lync Mobile and tablet devices using supported Apple iOS, Android, Windows Phone, or Nokia mobile devices to perform activities such as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span> <span data-ttu-id="073af-158">さらに、モバイルデバイスでは、クリックして会議に参加したり、勤務先の電話、1回の通話、ボイスメール、不在着信通知など、一部のエンタープライズ音声機能をサポートしたりします。</span><span class="sxs-lookup"><span data-stu-id="073af-158">In addition, mobile devices support some Enterprise Voice features, such as click to join a conference, Call via Work, single number reach, voice mail, and missed call notification.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="073af-159">モビリティサービスは、フロントエンドサーバーに展開されているリバースプロキシと公開されたサービスを使用します。</span><span class="sxs-lookup"><span data-stu-id="073af-159">The mobility services use the reverse proxy and published services that are deployed on your Front End Servers.</span></span> <span data-ttu-id="073af-160">エッジサーバーへの変更は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="073af-160">No changes are required to Edge Servers.</span></span> <span data-ttu-id="073af-161">少なくとも、Lync Server アクセスエッジサービスを実行しているサーバーから発信 SIP/TCP/5061from 必要です。</span><span class="sxs-lookup"><span data-stu-id="073af-161">Minimally you need outbound SIP/TCP/5061from the server running the Lync Server Access Edge service.</span></span>



</div>

</div>

<div>

## <a name="director-role-is-optional"></a><span data-ttu-id="073af-162">ディレクターの役割はオプション</span><span class="sxs-lookup"><span data-stu-id="073af-162">Director Role is Optional</span></span>

<span data-ttu-id="073af-163">Lync Server 2013 トポロジでのディレクターサーバーの役割が変更されていません。</span><span class="sxs-lookup"><span data-stu-id="073af-163">The role of the Director server in the Lync Server 2013 topology has not changed.</span></span> <span data-ttu-id="073af-164">さらに、web サービスをホストして、着信ユーザー要求を事前認証し、外部ユーザーをホームプールにリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="073af-164">It still hosts web services, preauthenticates incoming user requests, and directs external users to their home pool.</span></span> <span data-ttu-id="073af-165">推奨された役割からディレクターをオプションの役割に変更することで、Microsoft はディレクターの価値を減少することを意図していません。</span><span class="sxs-lookup"><span data-stu-id="073af-165">By changing the Director from a recommended role to an optional role, Microsoft does not intend to diminish the value of the Director.</span></span> <span data-ttu-id="073af-166">目的は、機能を損なうことなく、サーバー数とその他のハードウェア要件 (ディレクターのハードウェアロードバランサーなど) を削減することです。</span><span class="sxs-lookup"><span data-stu-id="073af-166">The intention is to reduce server count and other hardware requirements (for example, hardware load balancers for the Director) without compromising features and functionality.</span></span> <span data-ttu-id="073af-167">フロントエンドサーバーは、提供されているサービスに影響を与えずにディレクターと同じジョブを実行できるため、選択する場合は、ディレクターを展開できます。</span><span class="sxs-lookup"><span data-stu-id="073af-167">Because the Front End Servers can do the same job as the Director with no impact to services provided, you can deploy Directors if you choose to.</span></span> <span data-ttu-id="073af-168">フロントエンドサーバーによってディレクターの代わりに同じサービスが提供されるという確信を持って、ディレクターを安全に除外することができます。</span><span class="sxs-lookup"><span data-stu-id="073af-168">You can safely exclude the Director with confidence that the Front End Servers will provide the same services in place of a Director.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

