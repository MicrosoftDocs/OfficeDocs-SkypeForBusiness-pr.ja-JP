---
title: 'Lync Server 2013: 内部サーバーに対する証明書要件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate requirements for internal servers
ms:assetid: 0444cdbd-538c-43b1-b9a1-9d7d6cf818d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398094(v=OCS.15)
ms:contentKeyID: 48183270
ms.date: 02/17/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0351ab4f54273e1eccc09992ab933525cc2527ae
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736788"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-requirements-for-internal-servers-in-lync-server-2013"></a><span data-ttu-id="9dfd7-102">Lync Server 2013 の内部サーバーに対する証明書要件</span><span class="sxs-lookup"><span data-stu-id="9dfd7-102">Certificate requirements for internal servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9dfd7-103">_**最終更新日:** 2017-02-17_</span><span class="sxs-lookup"><span data-stu-id="9dfd7-103">_**Topic Last Modified:** 2017-02-17_</span></span>

<span data-ttu-id="9dfd7-104">Lync Server を実行していて、証明書を必要とする内部サーバーには、Standard Edition Server、Enterprise Edition フロントエンドサーバー、仲介サーバー、およびディレクターが含まれます。</span><span class="sxs-lookup"><span data-stu-id="9dfd7-104">Internal servers that are running Lync Server and that require certificates include Standard Edition server, Enterprise Edition Front End Server, Mediation Server, and Director.</span></span> <span data-ttu-id="9dfd7-105">次の表は、これらのサーバーの証明書要件を示しています。</span><span class="sxs-lookup"><span data-stu-id="9dfd7-105">The following table shows the certificate requirements for these servers.</span></span> <span data-ttu-id="9dfd7-106">Lync Server 証明書ウィザードを使って、これらの証明書を要求することができます。</span><span class="sxs-lookup"><span data-stu-id="9dfd7-106">You can use the Lync Server certificate wizard to request these certificates.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="9dfd7-107">ワイルドカード証明書は、フロントエンドプール、フロントエンドサーバー、またはディレクターの単純な Url に関連付けられたサブジェクトの別名でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="9dfd7-107">Wildcard certificates are supported for the subject alternative names associated with the simple URLs on the Front End pool, Front End Server, or Director.</span></span> <span data-ttu-id="9dfd7-108">ワイルドカード証明書のサポートについて詳しくは、「 <A href="lync-server-2013-wildcard-certificate-support.md">Lync Server 2013 でのワイルドカード証明書のサポート</A>」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9dfd7-108">For details about wildcard certificate support, see <A href="lync-server-2013-wildcard-certificate-support.md">Wildcard certificate support in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="9dfd7-109">内部サーバーでは社内のエンタープライズ証明機関 (CA) を使うことをお勧めしますが、パブリック CA を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="9dfd7-109">Although an internal enterprise certification authority (CA) is recommended for internal servers, you can also use a public CA.</span></span> <span data-ttu-id="9dfd7-110">統合通信 (UC) 証明書の特定の要件に準拠し、Microsoft と提携して Lync Server の証明書ウィザードで動作することを確認するパブリック Ca の一覧については、「Microsoft サポート技術情報929395」、「Exchange Server および通信サーバーのユニファイド[https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834)コミュニケーション証明書パートナー」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9dfd7-110">For a list of public CAs that provide certificates that comply with specific requirements for unified communications (UC) certificates and have partnered with Microsoft to ensure they work with the Lync Server Certificate Wizard, see article Microsoft Knowledge Base 929395, "Unified Communications Certificate Partners for Exchange Server and for Communications Server," at [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834).</span></span>

<span data-ttu-id="9dfd7-111">他のアプリケーションやサーバー (Exchange 2013 など) との通信には、他のアプリケーションや製品でサポートされている証明書が必要です。</span><span class="sxs-lookup"><span data-stu-id="9dfd7-111">Communication with other applications and servers, such as Exchange 2013, requires a certificate that is supported by the other applications and products.</span></span> <span data-ttu-id="9dfd7-112">2013リリース、Lync Server 2013、および Exchange 2013 および SharePoint Server を含むその他の Microsoft サーバー製品については、サーバー間の認証と承認のための Open Authorization (OAuth) プロトコルをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="9dfd7-112">For the 2013 release, Lync Server 2013 and other Microsoft server products, including Exchange 2013 and SharePoint Server, support the Open Authorization (OAuth) protocol for server-to-server authentication and authorization.</span></span> <span data-ttu-id="9dfd7-113">詳細については、展開ドキュメントまたは運用マニュアルの「 [Lync server 2013 でサーバー間認証 (OAuth) とパートナーアプリケーションを管理する](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9dfd7-113">For details, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) in the Deployment documentation or the Operations documentation.</span></span>

<span data-ttu-id="9dfd7-114">Windows 7 オペレーティングシステム、windows Server 2008 オペレーティングシステム、windows Server 2008 R2 オペレーティングシステム、Windows Vista オペレーティングシステム、および Microsoft Lync Phone Edition 2013 を実行しているクライアントからの接続については、のサポートが含まれます (ただし、256 SHA-1 暗号化ハッシュ関数を使用して署名された証明書を要求します。</span><span class="sxs-lookup"><span data-stu-id="9dfd7-114">For connections from clients running Windows 7 operating system, Windows Server 2008 operating system, Windows Server 2008 R2 operating system, Windows Vista operating system, and Microsoft Lync Phone Edition, Lync Server 2013 includes support for (but does not require) certificates signed using the SHA-256 cryptographic hash function.</span></span> <span data-ttu-id="9dfd7-115">SHA-256 を使って外部アクセスをサポートするために、外部証明書は SHA-256 を使ってパブリック CA によって発行されます。</span><span class="sxs-lookup"><span data-stu-id="9dfd7-115">To support external access using SHA-256, the external certificate is issued by a public CA using SHA-256.</span></span>

<span data-ttu-id="9dfd7-116">次の表は、フロントエンドプールと Standard Edition サーバーのサーバーロールごとの証明書要件を示しています。</span><span class="sxs-lookup"><span data-stu-id="9dfd7-116">The following tables show certificate requirements by server role for Front End pools and Standard Edition servers.</span></span> <span data-ttu-id="9dfd7-117">これらはすべて、標準の web サーバー証明書、秘密キー、エクスポートできません。</span><span class="sxs-lookup"><span data-stu-id="9dfd7-117">All these are standard web server certificates, private key, non-exportable.</span></span>

<span data-ttu-id="9dfd7-118">証明書ウィザードを使用して証明書を要求するときに、サーバーの拡張キー使用法 (EKU) が自動的に構成されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="9dfd7-118">Note that server enhanced key usage (EKU) is automatically configured when you use the certificate wizard to request certificates.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9dfd7-119">各証明書のフレンドリ名は、コンピューターストア内で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="9dfd7-119">Each certificate Friendly Name must be unique in the computer store.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="9dfd7-120">DNS で sipinternal.contoso.com または sipexternal.contoso.com を構成している場合は、証明書のサブジェクトの代替名にそれらを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9dfd7-120">If you have configured sipinternal.contoso.com or sipexternal.contoso.com in your DNS, you will need to add them in the certificate’s Subject Alternative Name.</span></span>



</div>

### <a name="certificates-for-standard-edition-server"></a><span data-ttu-id="9dfd7-121">Standard Edition Server 用の証明書</span><span class="sxs-lookup"><span data-stu-id="9dfd7-121">Certificates for Standard Edition Server</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9dfd7-122">証明書</span><span class="sxs-lookup"><span data-stu-id="9dfd7-122">Certificate</span></span></th>
<th><span data-ttu-id="9dfd7-123">サブジェクト名/共通名</span><span class="sxs-lookup"><span data-stu-id="9dfd7-123">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="9dfd7-124">サブジェクトの別名</span><span class="sxs-lookup"><span data-stu-id="9dfd7-124">Subject alternative name</span></span></th>
<th><span data-ttu-id="9dfd7-125">例</span><span class="sxs-lookup"><span data-stu-id="9dfd7-125">Example</span></span></th>
<th><span data-ttu-id="9dfd7-126">コメント</span><span class="sxs-lookup"><span data-stu-id="9dfd7-126">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9dfd7-127">Default</span><span class="sxs-lookup"><span data-stu-id="9dfd7-127">Default</span></span></p></td>
<td><p><span data-ttu-id="9dfd7-128">プールの完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="9dfd7-128">Fully qualified domain name (FQDN) of the pool</span></span></p></td>
<td><p><span data-ttu-id="9dfd7-129">プールの FQDN とサーバーの FQDN</span><span class="sxs-lookup"><span data-stu-id="9dfd7-129">FQDN of the pool and the FQDN of the server</span></span></p>
<p><span data-ttu-id="9dfd7-130">SIP ドメインが複数あり、自動クライアント構成が有効な場合は、証明書ウィザードによって、サポートされている各 SIP ドメインの FQDN が検出され、追加されます。</span><span class="sxs-lookup"><span data-stu-id="9dfd7-130">If you have multiple SIP domains and have enabled automatic client configuration, the certificate wizard detects and adds each supported SIP domain FQDNs.</span></span></p>
<p><span data-ttu-id="9dfd7-131">このプールがクライアントの自動ログオン サーバーであり、グループ ポリシーで厳密なドメイン ネーム システム (DNS) マッチングが必要な場合は、sip.sipdomain のエントリ (所有する各 SIP ドメイン用) も必要となります。</span><span class="sxs-lookup"><span data-stu-id="9dfd7-131">If this pool is the auto-logon server for clients and strict Domain Name System (DNS) matching is required in group policy, you also need entries for sip.sipdomain (for each SIP domain you have).</span></span></p></td>
<td><p><span data-ttu-id="9dfd7-132">SN=se01.contoso.com; SAN=se01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9dfd7-132">SN=se01.contoso.com; SAN=se01.contoso.com</span></span></p>
<p><span data-ttu-id="9dfd7-133">このプールがクライアントの自動ログオン サーバーであり、グループ ポリシーで厳密な DNS マッチングが必要な場合は、SAN=sip.contoso.com、SAN=sip.fabrikam.com も必要です。</span><span class="sxs-lookup"><span data-stu-id="9dfd7-133">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="9dfd7-134">Standard Edition server では、サーバーの FQDN はプールの FQDN と同じです。</span><span class="sxs-lookup"><span data-stu-id="9dfd7-134">On Standard Edition server, the server FQDN is the same as the pool FQDN.</span></span></p>
<p><span data-ttu-id="9dfd7-135">このウィザードでは、セットアップ時に指定した SIP ドメインが検出され、サブジェクトの別名に自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="9dfd7-135">The wizard detects any SIP domains you specified during setup and automatically adds them to the subject alternative name.</span></span></p>
<p><span data-ttu-id="9dfd7-136">また、この証明書はサーバー間認証でも使用できます。</span><span class="sxs-lookup"><span data-stu-id="9dfd7-136">You can also use this certificate for Server-to-Server Authentication.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9dfd7-137">内部 Web</span><span class="sxs-lookup"><span data-stu-id="9dfd7-137">Web internal</span></span></p></td>
<td><p><span data-ttu-id="9dfd7-138">サーバーの FQDN</span><span class="sxs-lookup"><span data-stu-id="9dfd7-138">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="9dfd7-139">次のうちのすべて:</span><span class="sxs-lookup"><span data-stu-id="9dfd7-139">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="9dfd7-140">内部 Web FQDN (サーバーの FQDN と同じ)</span><span class="sxs-lookup"><span data-stu-id="9dfd7-140">Internal web FQDN (which is the same as the FQDN of the server)</span></span></p></li>
<li><p><span data-ttu-id="9dfd7-141">会議の簡易 URL</span><span class="sxs-lookup"><span data-stu-id="9dfd7-141">Meet simple URLs</span></span></p></li>
<li><p><span data-ttu-id="9dfd7-142">ダイヤルインの簡易 URL</span><span class="sxs-lookup"><span data-stu-id="9dfd7-142">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="9dfd7-143">管理の簡易 URL</span><span class="sxs-lookup"><span data-stu-id="9dfd7-143">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="9dfd7-144">または、単純な Url のワイルドカードエントリ</span><span class="sxs-lookup"><span data-stu-id="9dfd7-144">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="9dfd7-145">SN=se01.contoso.com; SAN=se01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9dfd7-145">SN=se01.contoso.com; SAN=se01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span></span></p>
<p><span data-ttu-id="9dfd7-146">ワイルドカード証明書使用時:</span><span class="sxs-lookup"><span data-stu-id="9dfd7-146">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="9dfd7-147">SN=se01.contoso.com; SAN=se01.contoso.com; SAN=\*.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9dfd7-147">SN=se01.contoso.com; SAN=se01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="9dfd7-148">トポロジビルダーで内部 web FQDN を上書きすることはできません。</span><span class="sxs-lookup"><span data-stu-id="9dfd7-148">You cannot override the Internal web FQDN in Topology Builder.</span></span></p>
<p><span data-ttu-id="9dfd7-149">複数の条件を満たす単純な Url がある場合は、それらのすべてを対象の代替名として含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="9dfd7-149">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="9dfd7-150">簡易 URL エントリではワイルドカード エントリがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="9dfd7-150">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9dfd7-151">外部 Web</span><span class="sxs-lookup"><span data-stu-id="9dfd7-151">Web external</span></span></p></td>
<td><p><span data-ttu-id="9dfd7-152">サーバーの FQDN</span><span class="sxs-lookup"><span data-stu-id="9dfd7-152">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="9dfd7-153">次のうちのすべて:</span><span class="sxs-lookup"><span data-stu-id="9dfd7-153">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="9dfd7-154">外部 Web FQDN</span><span class="sxs-lookup"><span data-stu-id="9dfd7-154">External web FQDN</span></span></p></li>
<li><p><span data-ttu-id="9dfd7-155">ダイヤルインの簡易 URL</span><span class="sxs-lookup"><span data-stu-id="9dfd7-155">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="9dfd7-156">SIP ドメインごとの会議の簡易 URL</span><span class="sxs-lookup"><span data-stu-id="9dfd7-156">Meet simple URLs per SIP domain</span></span></p></li>
<li><p><span data-ttu-id="9dfd7-157">または、単純な Url のワイルドカードエントリ</span><span class="sxs-lookup"><span data-stu-id="9dfd7-157">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="9dfd7-158">SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9dfd7-158">SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span></span></p>
<p><span data-ttu-id="9dfd7-159">ワイルドカード証明書使用時:</span><span class="sxs-lookup"><span data-stu-id="9dfd7-159">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="9dfd7-160">SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=\*.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9dfd7-160">SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="9dfd7-161">複数の条件を満たす単純な Url がある場合は、それらのすべてを対象の代替名として含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="9dfd7-161">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="9dfd7-162">簡易 URL エントリではワイルドカード エントリがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="9dfd7-162">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-front-end-server-in-a-front-end-pool"></a><span data-ttu-id="9dfd7-163">フロントエンドプールのフロントエンドサーバー用の証明書</span><span class="sxs-lookup"><span data-stu-id="9dfd7-163">Certificates for Front End Server in a Front End Pool</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9dfd7-164">証明書</span><span class="sxs-lookup"><span data-stu-id="9dfd7-164">Certificate</span></span></th>
<th><span data-ttu-id="9dfd7-165">サブジェクト名/共通名</span><span class="sxs-lookup"><span data-stu-id="9dfd7-165">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="9dfd7-166">サブジェクトの別名</span><span class="sxs-lookup"><span data-stu-id="9dfd7-166">Subject alternative name</span></span></th>
<th><span data-ttu-id="9dfd7-167">例</span><span class="sxs-lookup"><span data-stu-id="9dfd7-167">Example</span></span></th>
<th><span data-ttu-id="9dfd7-168">コメント</span><span class="sxs-lookup"><span data-stu-id="9dfd7-168">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9dfd7-169">Default</span><span class="sxs-lookup"><span data-stu-id="9dfd7-169">Default</span></span></p></td>
<td><p><span data-ttu-id="9dfd7-170">プールの FQDN</span><span class="sxs-lookup"><span data-stu-id="9dfd7-170">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="9dfd7-171">サーバーのプールと FQDN の FQDN。</span><span class="sxs-lookup"><span data-stu-id="9dfd7-171">FQDN of the pool and FQDN of the server.</span></span></p>
<p><span data-ttu-id="9dfd7-172">SIP ドメインが複数あり、自動クライアント構成が有効な場合は、証明書ウィザードによって、サポートされている各 SIP ドメインの FQDN が検出され、追加されます。</span><span class="sxs-lookup"><span data-stu-id="9dfd7-172">If you have multiple SIP domains and have enabled automatic client configuration, the certificate wizard detects and adds each supported SIP domain FQDNs.</span></span></p>
<p><span data-ttu-id="9dfd7-173">このプールがクライアント用の自動ログオンサーバーであり、かつ厳密な DNS 一致がグループポリシーで必要となる場合は、sipdomain (SIP ドメインごとに) を入力する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="9dfd7-173">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need entries for sip.sipdomain (for each SIP domain you have).</span></span></p></td>
<td><p><span data-ttu-id="9dfd7-174">SN=eepool.contoso.com; SAN=eepool.contoso.com; SAN=ee01.contoso.com </span><span class="sxs-lookup"><span data-stu-id="9dfd7-174">SN=eepool.contoso.com; SAN=eepool.contoso.com; SAN=ee01.contoso.com</span></span></p>
<p><span data-ttu-id="9dfd7-175">このプールがクライアントの自動ログオン サーバーであり、グループ ポリシーで厳密な DNS マッチングが必要な場合は、SAN=sip.contoso.com、SAN=sip.fabrikam.com も必要です。</span><span class="sxs-lookup"><span data-stu-id="9dfd7-175">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="9dfd7-176">このウィザードでは、セットアップ時に指定した SIP ドメインが検出され、サブジェクトの別名に自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="9dfd7-176">The wizard detects any SIP domains you specified during setup and automatically adds them to the subject alternative name.</span></span></p>
<p><span data-ttu-id="9dfd7-177">また、この証明書はサーバー間認証でも使用できます。</span><span class="sxs-lookup"><span data-stu-id="9dfd7-177">You can also use this certificate for Server-to-Server Authentication.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9dfd7-178">Web 内部</span><span class="sxs-lookup"><span data-stu-id="9dfd7-178">Web Internal</span></span></p></td>
<td><p><span data-ttu-id="9dfd7-179">プールの FQDN</span><span class="sxs-lookup"><span data-stu-id="9dfd7-179">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="9dfd7-180">次のうちのすべて:</span><span class="sxs-lookup"><span data-stu-id="9dfd7-180">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="9dfd7-181">内部 Web FQDN (サーバーの FQDN とは異なる)</span><span class="sxs-lookup"><span data-stu-id="9dfd7-181">Internal web FQDN (which is NOT the same as the FQDN of the server)</span></span></p></li>
<li><p><span data-ttu-id="9dfd7-182">サーバーの FQDN</span><span class="sxs-lookup"><span data-stu-id="9dfd7-182">Server FQDN</span></span></p></li>
<li><p><span data-ttu-id="9dfd7-183">Lync プールの FQDN</span><span class="sxs-lookup"><span data-stu-id="9dfd7-183">Lync pool FQDN</span></span></p></li>
<li><p><span data-ttu-id="9dfd7-184">会議の簡易 URL</span><span class="sxs-lookup"><span data-stu-id="9dfd7-184">Meet simple URLs</span></span></p></li>
<li><p><span data-ttu-id="9dfd7-185">ダイヤルインの簡易 URL</span><span class="sxs-lookup"><span data-stu-id="9dfd7-185">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="9dfd7-186">管理の簡易 URL</span><span class="sxs-lookup"><span data-stu-id="9dfd7-186">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="9dfd7-187">または、単純な Url のワイルドカードエントリ</span><span class="sxs-lookup"><span data-stu-id="9dfd7-187">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="9dfd7-188">SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9dfd7-188">SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span></span></p>
<p><span data-ttu-id="9dfd7-189">ワイルドカード証明書使用時:</span><span class="sxs-lookup"><span data-stu-id="9dfd7-189">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="9dfd7-190">SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=\*.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9dfd7-190">SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="9dfd7-191">複数の条件を満たす単純な Url がある場合は、それらのすべてを対象の代替名として含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="9dfd7-191">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="9dfd7-192">簡易 URL エントリではワイルドカード エントリがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="9dfd7-192">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9dfd7-193">外部 Web</span><span class="sxs-lookup"><span data-stu-id="9dfd7-193">Web external</span></span></p></td>
<td><p><span data-ttu-id="9dfd7-194">プールの FQDN</span><span class="sxs-lookup"><span data-stu-id="9dfd7-194">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="9dfd7-195">次のうちのすべて:</span><span class="sxs-lookup"><span data-stu-id="9dfd7-195">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="9dfd7-196">外部 Web FQDN</span><span class="sxs-lookup"><span data-stu-id="9dfd7-196">External web FQDN</span></span></p></li>
<li><p><span data-ttu-id="9dfd7-197">ダイヤルインの簡易 URL</span><span class="sxs-lookup"><span data-stu-id="9dfd7-197">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="9dfd7-198">管理の簡易 URL</span><span class="sxs-lookup"><span data-stu-id="9dfd7-198">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="9dfd7-199">または、単純な Url のワイルドカードエントリ</span><span class="sxs-lookup"><span data-stu-id="9dfd7-199">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="9dfd7-200">SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9dfd7-200">SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span></span></p>
<p><span data-ttu-id="9dfd7-201">ワイルドカード証明書使用時:</span><span class="sxs-lookup"><span data-stu-id="9dfd7-201">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="9dfd7-202">SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=\*.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9dfd7-202">SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="9dfd7-203">複数の条件を満たす単純な Url がある場合は、それらのすべてを対象の代替名として含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="9dfd7-203">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="9dfd7-204">簡易 URL エントリではワイルドカード エントリがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="9dfd7-204">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-director"></a><span data-ttu-id="9dfd7-205">ディレクター用の証明書</span><span class="sxs-lookup"><span data-stu-id="9dfd7-205">Certificates for Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9dfd7-206">証明書</span><span class="sxs-lookup"><span data-stu-id="9dfd7-206">Certificate</span></span></th>
<th><span data-ttu-id="9dfd7-207">サブジェクト名/共通名</span><span class="sxs-lookup"><span data-stu-id="9dfd7-207">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="9dfd7-208">サブジェクトの別名</span><span class="sxs-lookup"><span data-stu-id="9dfd7-208">Subject alternative name</span></span></th>
<th><span data-ttu-id="9dfd7-209">例</span><span class="sxs-lookup"><span data-stu-id="9dfd7-209">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9dfd7-210">Default</span><span class="sxs-lookup"><span data-stu-id="9dfd7-210">Default</span></span></p></td>
<td><p><span data-ttu-id="9dfd7-211">ディレクタープールの FQDN</span><span class="sxs-lookup"><span data-stu-id="9dfd7-211">FQDN of the Director pool</span></span></p></td>
<td><p><span data-ttu-id="9dfd7-212">ディレクタープールの FQDN の fqdn。</span><span class="sxs-lookup"><span data-stu-id="9dfd7-212">FQDN of the Director, FQDN of the Director pool</span></span></p>
<p><span data-ttu-id="9dfd7-213">このプールがクライアント用の自動ログオンサーバーであり、かつ厳密な DNS 一致がグループポリシーで必要となる場合は、sipdomain (SIP ドメインごとに) を入力する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="9dfd7-213">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need entries for sip.sipdomain (for each SIP domain you have).</span></span></p></td>
<td><p><span data-ttu-id="9dfd7-214">SN = dir-pool.contoso.com;SAN = dir-pool.contoso.com;SAN = dir01</span><span class="sxs-lookup"><span data-stu-id="9dfd7-214">SN=dir-pool.contoso.com; SAN=dir-pool.contoso.com; SAN=dir01.contoso.com</span></span></p>
<p><span data-ttu-id="9dfd7-215">このディレクタープールがクライアント用の自動ログオンサーバーであり、かつ厳密な DNS 一致がグループポリシーで必要な場合は、SAN = sip-pstn を使用する必要もあります。サン = sip-pstn</span><span class="sxs-lookup"><span data-stu-id="9dfd7-215">If this Director pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9dfd7-216">Web 内部</span><span class="sxs-lookup"><span data-stu-id="9dfd7-216">Web Internal</span></span></p></td>
<td><p><span data-ttu-id="9dfd7-217">サーバーの FQDN</span><span class="sxs-lookup"><span data-stu-id="9dfd7-217">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="9dfd7-218">次のうちのすべて:</span><span class="sxs-lookup"><span data-stu-id="9dfd7-218">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="9dfd7-219">内部 Web FQDN (サーバーの FQDN と同じ)</span><span class="sxs-lookup"><span data-stu-id="9dfd7-219">Internal web FQDN (which is the same as the FQDN of the server)</span></span></p></li>
<li><p><span data-ttu-id="9dfd7-220">サーバーの FQDN</span><span class="sxs-lookup"><span data-stu-id="9dfd7-220">Server FQDN</span></span></p></li>
<li><p><span data-ttu-id="9dfd7-221">Lync プールの FQDN</span><span class="sxs-lookup"><span data-stu-id="9dfd7-221">Lync pool FQDN</span></span></p></li>
<li><p><span data-ttu-id="9dfd7-222">会議の簡易 URL</span><span class="sxs-lookup"><span data-stu-id="9dfd7-222">Meet simple URLs</span></span></p></li>
<li><p><span data-ttu-id="9dfd7-223">ダイヤルインの簡易 URL</span><span class="sxs-lookup"><span data-stu-id="9dfd7-223">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="9dfd7-224">管理の簡易 URL</span><span class="sxs-lookup"><span data-stu-id="9dfd7-224">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="9dfd7-225">または、単純な Url のワイルドカードエントリ</span><span class="sxs-lookup"><span data-stu-id="9dfd7-225">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="9dfd7-226">SN=dir01.contoso.com; SAN=dir01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9dfd7-226">SN=dir01.contoso.com; SAN=dir01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span></span></p>
<p><span data-ttu-id="9dfd7-227">SN=dir01.contoso.com; SAN=dir01.contoso.com SAN=\*.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9dfd7-227">SN=dir01.contoso.com; SAN=dir01.contoso.com SAN=\*.contoso.com</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9dfd7-228">外部 Web</span><span class="sxs-lookup"><span data-stu-id="9dfd7-228">Web external</span></span></p></td>
<td><p><span data-ttu-id="9dfd7-229">サーバーの FQDN</span><span class="sxs-lookup"><span data-stu-id="9dfd7-229">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="9dfd7-230">次のうちのすべて:</span><span class="sxs-lookup"><span data-stu-id="9dfd7-230">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="9dfd7-231">外部 Web FQDN</span><span class="sxs-lookup"><span data-stu-id="9dfd7-231">External web FQDN</span></span></p></li>
<li><p><span data-ttu-id="9dfd7-232">ダイヤルインの簡易 URL</span><span class="sxs-lookup"><span data-stu-id="9dfd7-232">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="9dfd7-233">管理の簡易 URL</span><span class="sxs-lookup"><span data-stu-id="9dfd7-233">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="9dfd7-234">または、単純な Url のワイルドカードエントリ</span><span class="sxs-lookup"><span data-stu-id="9dfd7-234">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="9dfd7-235">ディレクターの外部 web FQDN は、フロントエンドプールまたはフロントエンドサーバーと異なっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="9dfd7-235">The Director external web FQDN must be different from the Front End pool or Front End Server.</span></span></p>
<p><span data-ttu-id="9dfd7-236">SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9dfd7-236">SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span></span></p>
<p><span data-ttu-id="9dfd7-237">SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=\*.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9dfd7-237">SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=\*.contoso.com</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="9dfd7-238">スタンドアロンの仲介サーバープールを使用している場合、それぞれの仲介サーバーには、次の表に示す証明書が必要です。</span><span class="sxs-lookup"><span data-stu-id="9dfd7-238">If you have a stand-alone Mediation Server pool, the Mediation Servers in it each need the certificates listed in the following table.</span></span> <span data-ttu-id="9dfd7-239">フロントエンドサーバーによって仲介サーバーがある場合は、このトピックの前半の「フロントエンドプールの証明書」の表に記載されている証明書を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9dfd7-239">If you collocate Mediation Server with the Front End Servers, the certificates listed in the “Certificates for Front End Server in Front End Pool” table earlier in this topic are sufficient.</span></span>

### <a name="certificates-for-stand-alone-mediation-server"></a><span data-ttu-id="9dfd7-240">スタンドアロンの仲介サーバー用の証明書</span><span class="sxs-lookup"><span data-stu-id="9dfd7-240">Certificates for Stand-alone Mediation Server</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9dfd7-241">証明書</span><span class="sxs-lookup"><span data-stu-id="9dfd7-241">Certificate</span></span></th>
<th><span data-ttu-id="9dfd7-242">サブジェクト名/共通名</span><span class="sxs-lookup"><span data-stu-id="9dfd7-242">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="9dfd7-243">サブジェクトの別名</span><span class="sxs-lookup"><span data-stu-id="9dfd7-243">Subject alternative name</span></span></th>
<th><span data-ttu-id="9dfd7-244">例</span><span class="sxs-lookup"><span data-stu-id="9dfd7-244">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9dfd7-245">Default</span><span class="sxs-lookup"><span data-stu-id="9dfd7-245">Default</span></span></p></td>
<td><p><span data-ttu-id="9dfd7-246">プールの FQDN</span><span class="sxs-lookup"><span data-stu-id="9dfd7-246">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="9dfd7-247">プールの FQDN</span><span class="sxs-lookup"><span data-stu-id="9dfd7-247">FQDN of the pool</span></span></p>
<p><span data-ttu-id="9dfd7-248">プールメンバーサーバーの FQDN</span><span class="sxs-lookup"><span data-stu-id="9dfd7-248">FQDN of pool member server</span></span></p></td>
<td><p><span data-ttu-id="9dfd7-249">SN=medsvr-pool.contoso.net; SAN=medsvr-pool.contoso.net; SAN=medsvr01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="9dfd7-249">SN=medsvr-pool.contoso.net; SAN=medsvr-pool.contoso.net; SAN=medsvr01.contoso.net</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-survivable-branch-appliance"></a><span data-ttu-id="9dfd7-250">Survivable Branch Appliance 用の証明書</span><span class="sxs-lookup"><span data-stu-id="9dfd7-250">Certificates for Survivable Branch Appliance</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9dfd7-251">証明書</span><span class="sxs-lookup"><span data-stu-id="9dfd7-251">Certificate</span></span></th>
<th><span data-ttu-id="9dfd7-252">サブジェクト名/共通名</span><span class="sxs-lookup"><span data-stu-id="9dfd7-252">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="9dfd7-253">サブジェクトの別名</span><span class="sxs-lookup"><span data-stu-id="9dfd7-253">Subject alternative name</span></span></th>
<th><span data-ttu-id="9dfd7-254">例</span><span class="sxs-lookup"><span data-stu-id="9dfd7-254">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9dfd7-255">Default</span><span class="sxs-lookup"><span data-stu-id="9dfd7-255">Default</span></span></p></td>
<td><p><span data-ttu-id="9dfd7-256">アプライアンスの FQDN</span><span class="sxs-lookup"><span data-stu-id="9dfd7-256">FQDN of the appliance</span></span></p></td>
<td><p><span data-ttu-id="9dfd7-257">フェデレーション.&lt;SIPDOMAIN&gt; (SIP ドメインごとに1つのエントリが必要)</span><span class="sxs-lookup"><span data-stu-id="9dfd7-257">SIP.&lt;sipdomain&gt; (need one entry per SIP domain)</span></span></p></td>
<td><p><span data-ttu-id="9dfd7-258">SN=sba01.contoso.net; SAN=sip.contoso.com; SAN=sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="9dfd7-258">SN=sba01.contoso.net; SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="9dfd7-259">関連項目</span><span class="sxs-lookup"><span data-stu-id="9dfd7-259">See Also</span></span>


[<span data-ttu-id="9dfd7-260">Lync Server 2013 のワイルドカード証明書のサポート</span><span class="sxs-lookup"><span data-stu-id="9dfd7-260">Wildcard certificate support in Lync Server 2013</span></span>](lync-server-2013-wildcard-certificate-support.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

