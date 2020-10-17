---
title: 'Lync Server 2013: 内部サーバーの証明書要件'
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
ms.openlocfilehash: c56554a26e5f64089a766300f375039409680578
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526244"
---
# <a name="certificate-requirements-for-internal-servers-in-lync-server-2013"></a><span data-ttu-id="f46db-102">Lync Server 2013 の内部サーバーの証明書要件</span><span class="sxs-lookup"><span data-stu-id="f46db-102">Certificate requirements for internal servers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f46db-103">_**トピックの最終更新日:** 2017-02-17_</span><span class="sxs-lookup"><span data-stu-id="f46db-103">_**Topic Last Modified:** 2017-02-17_</span></span>

<span data-ttu-id="f46db-104">Lync Server を実行していて、証明書を必要とする内部サーバーには、Standard Edition サーバー、Enterprise Edition フロントエンドサーバー、仲介サーバー、ディレクターがあります。</span><span class="sxs-lookup"><span data-stu-id="f46db-104">Internal servers that are running Lync Server and that require certificates include Standard Edition server, Enterprise Edition Front End Server, Mediation Server, and Director.</span></span> <span data-ttu-id="f46db-105">次の表に、これらのサーバーの証明書要件を示します。</span><span class="sxs-lookup"><span data-stu-id="f46db-105">The following table shows the certificate requirements for these servers.</span></span> <span data-ttu-id="f46db-106">Lync Server 証明書ウィザードを使用して、これらの証明書を要求できます。</span><span class="sxs-lookup"><span data-stu-id="f46db-106">You can use the Lync Server certificate wizard to request these certificates.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="f46db-107">ワイルドカード証明書は、フロントエンドプール、フロントエンドサーバー、またはディレクターの簡易 Url に関連付けられたサブジェクトの別名に対してサポートされています。</span><span class="sxs-lookup"><span data-stu-id="f46db-107">Wildcard certificates are supported for the subject alternative names associated with the simple URLs on the Front End pool, Front End Server, or Director.</span></span> <span data-ttu-id="f46db-108">ワイルドカード証明書のサポートの詳細については、「 <A href="lync-server-2013-wildcard-certificate-support.md">Lync Server 2013 のワイルドカード証明書のサポート</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f46db-108">For details about wildcard certificate support, see <A href="lync-server-2013-wildcard-certificate-support.md">Wildcard certificate support in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="f46db-109">内部サーバーには内部のエンタープライズ証明機関 (CA) をお勧めしますが、パブリック CA を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="f46db-109">Although an internal enterprise certification authority (CA) is recommended for internal servers, you can also use a public CA.</span></span> <span data-ttu-id="f46db-110">統合コミュニケーション (UC) 証明書の特定の要件に準拠した証明書を提供し、Microsoft と提携して Lync Server 証明書ウィザードを使用できるようにするパブリック Ca の一覧については、「Microsoft Knowledge Base 929395 の記事「Exchange Server と通信サーバーのための統合コミュニケーション証明書パートナー」 () を参照してください [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834) 。</span><span class="sxs-lookup"><span data-stu-id="f46db-110">For a list of public CAs that provide certificates that comply with specific requirements for unified communications (UC) certificates and have partnered with Microsoft to ensure they work with the Lync Server Certificate Wizard, see article Microsoft Knowledge Base 929395, "Unified Communications Certificate Partners for Exchange Server and for Communications Server," at [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834).</span></span>

<span data-ttu-id="f46db-111">Exchange 2013 などの他のアプリケーションやサーバーと通信するには、他のアプリケーションと製品でサポートされている証明書が必要です。</span><span class="sxs-lookup"><span data-stu-id="f46db-111">Communication with other applications and servers, such as Exchange 2013, requires a certificate that is supported by the other applications and products.</span></span> <span data-ttu-id="f46db-112">2013リリース、Lync Server 2013、および Exchange 2013 および SharePoint Server を含むその他の Microsoft サーバー製品については、サーバー間の認証と承認のための Open Authorization (OAuth) プロトコルをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="f46db-112">For the 2013 release, Lync Server 2013 and other Microsoft server products, including Exchange 2013 and SharePoint Server, support the Open Authorization (OAuth) protocol for server-to-server authentication and authorization.</span></span> <span data-ttu-id="f46db-113">詳細については、「展開」のドキュメントまたは「操作」のドキュメントの「 [Lync server 2013 でのサーバー間認証 (OAuth) およびパートナーアプリケーションの管理](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f46db-113">For details, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) in the Deployment documentation or the Operations documentation.</span></span>

<span data-ttu-id="f46db-114">Windows 7 オペレーティングシステム、Windows Server 2008 オペレーティングシステム、Windows Server 2008 R2 オペレーティングシステム、Windows Vista オペレーティングシステム、および Microsoft Lync Phone Edition を実行しているクライアントからの接続については、Lync Server 2013 では、SHA-256 暗号化ハッシュ関数を使用して署名された証明書をサポートしていますが、必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="f46db-114">For connections from clients running Windows 7 operating system, Windows Server 2008 operating system, Windows Server 2008 R2 operating system, Windows Vista operating system, and Microsoft Lync Phone Edition, Lync Server 2013 includes support for (but does not require) certificates signed using the SHA-256 cryptographic hash function.</span></span> <span data-ttu-id="f46db-115">SHA-256 を使用する外部アクセスをサポートするには、SHA-256 を使用するパブリック CA が外部証明書を発行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f46db-115">To support external access using SHA-256, the external certificate is issued by a public CA using SHA-256.</span></span>

<span data-ttu-id="f46db-p106">次の表に、フロント エンド プールと Standard Edition サーバーの各サーバーの役割における証明書要件を示します。 これらはすべて、標準 Web サーバー、秘密キー、エクスポート不可能です。</span><span class="sxs-lookup"><span data-stu-id="f46db-p106">The following tables show certificate requirements by server role for Front End pools and Standard Edition servers. All these are standard web server certificates, private key, non-exportable.</span></span>

<span data-ttu-id="f46db-118">サーバーの拡張キー使用法 (EKU) は、証明書ウィザードを使って証明書を要求する際に自動的に構成されます。</span><span class="sxs-lookup"><span data-stu-id="f46db-118">Note that server enhanced key usage (EKU) is automatically configured when you use the certificate wizard to request certificates.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f46db-119">各証明書のフレンドリ名は、コンピューターストア内で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="f46db-119">Each certificate Friendly Name must be unique in the computer store.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="f46db-120">DNS で sipinternal.contoso.com または sipexternal.contoso.com を構成した場合は、証明書のサブジェクトの別名に追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f46db-120">If you have configured sipinternal.contoso.com or sipexternal.contoso.com in your DNS, you will need to add them in the certificate’s Subject Alternative Name.</span></span>



</div>

### <a name="certificates-for-standard-edition-server"></a><span data-ttu-id="f46db-121">Standard Edition サーバーの証明書</span><span class="sxs-lookup"><span data-stu-id="f46db-121">Certificates for Standard Edition Server</span></span>

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
<th><span data-ttu-id="f46db-122">証明書</span><span class="sxs-lookup"><span data-stu-id="f46db-122">Certificate</span></span></th>
<th><span data-ttu-id="f46db-123">サブジェクト名/共通名</span><span class="sxs-lookup"><span data-stu-id="f46db-123">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="f46db-124">サブジェクト名の別名</span><span class="sxs-lookup"><span data-stu-id="f46db-124">Subject alternative name</span></span></th>
<th><span data-ttu-id="f46db-125">例</span><span class="sxs-lookup"><span data-stu-id="f46db-125">Example</span></span></th>
<th><span data-ttu-id="f46db-126">Comments</span><span class="sxs-lookup"><span data-stu-id="f46db-126">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f46db-127">既定値</span><span class="sxs-lookup"><span data-stu-id="f46db-127">Default</span></span></p></td>
<td><p><span data-ttu-id="f46db-128">プールの完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="f46db-128">Fully qualified domain name (FQDN) of the pool</span></span></p></td>
<td><p><span data-ttu-id="f46db-129">プールの FQDN およびサーバーの FQDN</span><span class="sxs-lookup"><span data-stu-id="f46db-129">FQDN of the pool and the FQDN of the server</span></span></p>
<p><span data-ttu-id="f46db-130">SIP ドメインが複数あり、自動クライアント構成が有効にされている場合は、証明書ウィザードで、サポートされている各 SIP ドメイン FQDN が検出され、追加されます。</span><span class="sxs-lookup"><span data-stu-id="f46db-130">If you have multiple SIP domains and have enabled automatic client configuration, the certificate wizard detects and adds each supported SIP domain FQDNs.</span></span></p>
<p><span data-ttu-id="f46db-131">このプールがクライアントの自動ログオン サーバーであり、グループ ポリシーで厳密なドメイン ネーム システム (DNS) マッチングが必要となる場合は、sip.sipdomain のエントリ (存在するそれぞれの SIP 用) も必要となります。</span><span class="sxs-lookup"><span data-stu-id="f46db-131">If this pool is the auto-logon server for clients and strict Domain Name System (DNS) matching is required in group policy, you also need entries for sip.sipdomain (for each SIP domain you have).</span></span></p></td>
<td><p><span data-ttu-id="f46db-132">SN = se01。SAN = se01</span><span class="sxs-lookup"><span data-stu-id="f46db-132">SN=se01.contoso.com; SAN=se01.contoso.com</span></span></p>
<p><span data-ttu-id="f46db-133">このプールがクライアントの自動ログオン サーバーであり、グループ ポリシーで厳密な DNS マッチングが必要となる場合は、SAN=sip.contoso.com、SAN=sip.fabrikam.com も必要となります。</span><span class="sxs-lookup"><span data-stu-id="f46db-133">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="f46db-134">Standard Edition サーバーに関しては、サーバー FQDN とプール FQDN は同じです。</span><span class="sxs-lookup"><span data-stu-id="f46db-134">On Standard Edition server, the server FQDN is the same as the pool FQDN.</span></span></p>
<p><span data-ttu-id="f46db-135">このウィザードでは、セットアップ時に指定した SIP ドメインが検出され、サブジェクト名の別名に自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="f46db-135">The wizard detects any SIP domains you specified during setup and automatically adds them to the subject alternative name.</span></span></p>
<p><span data-ttu-id="f46db-136">この証明書は、サーバー間認証に使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="f46db-136">You can also use this certificate for Server-to-Server Authentication.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f46db-137">内部 Web</span><span class="sxs-lookup"><span data-stu-id="f46db-137">Web internal</span></span></p></td>
<td><p><span data-ttu-id="f46db-138">サーバーの FQDN</span><span class="sxs-lookup"><span data-stu-id="f46db-138">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="f46db-139">次のうちのすべて:</span><span class="sxs-lookup"><span data-stu-id="f46db-139">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="f46db-140">内部 Web FQDN (サーバーの FQDN と同じ)</span><span class="sxs-lookup"><span data-stu-id="f46db-140">Internal web FQDN (which is the same as the FQDN of the server)</span></span></p></li>
<li><p><span data-ttu-id="f46db-141">簡単な会議 URL</span><span class="sxs-lookup"><span data-stu-id="f46db-141">Meet simple URLs</span></span></p></li>
<li><p><span data-ttu-id="f46db-142">簡単なダイヤルイン URL</span><span class="sxs-lookup"><span data-stu-id="f46db-142">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="f46db-143">簡単な管理 URL</span><span class="sxs-lookup"><span data-stu-id="f46db-143">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="f46db-144">または、簡易 URL のワイルドカード エントリ</span><span class="sxs-lookup"><span data-stu-id="f46db-144">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="f46db-145">SN = se01。SAN = se01。SAN = contoso .com。SAN = fabrikam .comSAN = ダイヤルイン。SAN = 管理</span><span class="sxs-lookup"><span data-stu-id="f46db-145">SN=se01.contoso.com; SAN=se01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span></span></p>
<p><span data-ttu-id="f46db-146">ワイルドカード証明書使用時:</span><span class="sxs-lookup"><span data-stu-id="f46db-146">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="f46db-147">SN = se01。SAN = se01。SAN = \* .com</span><span class="sxs-lookup"><span data-stu-id="f46db-147">SN=se01.contoso.com; SAN=se01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f46db-148">トポロジビルダーで内部 web FQDN を上書きすることはできません。</span><span class="sxs-lookup"><span data-stu-id="f46db-148">You cannot override the Internal web FQDN in Topology Builder.</span></span></p>
<p><span data-ttu-id="f46db-149">会議の簡易 URL が複数存在する場合、それらすべてをサブジェクト名の別名として含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="f46db-149">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="f46db-150">簡易 URL エントリにはワイルドカード エントリがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="f46db-150">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f46db-151">外部 Web</span><span class="sxs-lookup"><span data-stu-id="f46db-151">Web external</span></span></p></td>
<td><p><span data-ttu-id="f46db-152">サーバーの FQDN</span><span class="sxs-lookup"><span data-stu-id="f46db-152">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="f46db-153">次のうちのすべて:</span><span class="sxs-lookup"><span data-stu-id="f46db-153">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="f46db-154">外部 Web FQDN</span><span class="sxs-lookup"><span data-stu-id="f46db-154">External web FQDN</span></span></p></li>
<li><p><span data-ttu-id="f46db-155">簡単なダイヤルイン URL</span><span class="sxs-lookup"><span data-stu-id="f46db-155">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="f46db-156">SIP ドメインごとに単純な Url を満たす</span><span class="sxs-lookup"><span data-stu-id="f46db-156">Meet simple URLs per SIP domain</span></span></p></li>
<li><p><span data-ttu-id="f46db-157">または、簡易 URL のワイルドカード エントリ</span><span class="sxs-lookup"><span data-stu-id="f46db-157">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="f46db-158">SN = se01。SAN = webcon01。SAN = contoso .com。SAN = fabrikam .comSAN = ダイヤルイン .com</span><span class="sxs-lookup"><span data-stu-id="f46db-158">SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span></span></p>
<p><span data-ttu-id="f46db-159">ワイルドカード証明書使用時:</span><span class="sxs-lookup"><span data-stu-id="f46db-159">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="f46db-160">SN = se01。SAN = webcon01。SAN = \* .com</span><span class="sxs-lookup"><span data-stu-id="f46db-160">SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f46db-161">会議の簡易 URL が複数存在する場合、それらすべてをサブジェクト名の別名として含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="f46db-161">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="f46db-162">簡易 URL エントリにはワイルドカード エントリがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="f46db-162">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-front-end-server-in-a-front-end-pool"></a><span data-ttu-id="f46db-163">フロント エンド プールのフロント エンド サーバーの証明書</span><span class="sxs-lookup"><span data-stu-id="f46db-163">Certificates for Front End Server in a Front End Pool</span></span>

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
<th><span data-ttu-id="f46db-164">証明書</span><span class="sxs-lookup"><span data-stu-id="f46db-164">Certificate</span></span></th>
<th><span data-ttu-id="f46db-165">サブジェクト名/共通名</span><span class="sxs-lookup"><span data-stu-id="f46db-165">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="f46db-166">サブジェクト名の別名</span><span class="sxs-lookup"><span data-stu-id="f46db-166">Subject alternative name</span></span></th>
<th><span data-ttu-id="f46db-167">例</span><span class="sxs-lookup"><span data-stu-id="f46db-167">Example</span></span></th>
<th><span data-ttu-id="f46db-168">Comments</span><span class="sxs-lookup"><span data-stu-id="f46db-168">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f46db-169">既定値</span><span class="sxs-lookup"><span data-stu-id="f46db-169">Default</span></span></p></td>
<td><p><span data-ttu-id="f46db-170">プールの FQDN</span><span class="sxs-lookup"><span data-stu-id="f46db-170">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="f46db-171">プールの FQDN およびサーバーの FQDN。</span><span class="sxs-lookup"><span data-stu-id="f46db-171">FQDN of the pool and FQDN of the server.</span></span></p>
<p><span data-ttu-id="f46db-172">SIP ドメインが複数あり、自動クライアント構成が有効にされている場合は、証明書ウィザードで、サポートされている各 SIP ドメイン FQDN が検出され、追加されます。</span><span class="sxs-lookup"><span data-stu-id="f46db-172">If you have multiple SIP domains and have enabled automatic client configuration, the certificate wizard detects and adds each supported SIP domain FQDNs.</span></span></p>
<p><span data-ttu-id="f46db-173">このプールがクライアントの自動ログオン サーバーであり、グループ ポリシーで厳密な DNS マッチングが必要となる場合は、sip.sipdomain のエントリ (存在するそれぞれの SIP 用) も必要となります。</span><span class="sxs-lookup"><span data-stu-id="f46db-173">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need entries for sip.sipdomain (for each SIP domain you have).</span></span></p></td>
<td><p><span data-ttu-id="f46db-174">SN = eepool。SAN = eepool、SAN = ee01</span><span class="sxs-lookup"><span data-stu-id="f46db-174">SN=eepool.contoso.com; SAN=eepool.contoso.com; SAN=ee01.contoso.com</span></span></p>
<p><span data-ttu-id="f46db-175">このプールがクライアントの自動ログオン サーバーであり、グループ ポリシーで厳密な DNS マッチングが必要となる場合は、SAN=sip.contoso.com、SAN=sip.fabrikam.com も必要となります。</span><span class="sxs-lookup"><span data-stu-id="f46db-175">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="f46db-176">このウィザードでは、セットアップ時に指定した SIP ドメインが検出され、サブジェクト名の別名に自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="f46db-176">The wizard detects any SIP domains you specified during setup and automatically adds them to the subject alternative name.</span></span></p>
<p><span data-ttu-id="f46db-177">この証明書は、サーバー間認証に使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="f46db-177">You can also use this certificate for Server-to-Server Authentication.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f46db-178">内部 Web</span><span class="sxs-lookup"><span data-stu-id="f46db-178">Web Internal</span></span></p></td>
<td><p><span data-ttu-id="f46db-179">プールの FQDN</span><span class="sxs-lookup"><span data-stu-id="f46db-179">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="f46db-180">次のうちのすべて:</span><span class="sxs-lookup"><span data-stu-id="f46db-180">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="f46db-181">内部 web FQDN (サーバーの FQDN と同じではない)</span><span class="sxs-lookup"><span data-stu-id="f46db-181">Internal web FQDN (which is NOT the same as the FQDN of the server)</span></span></p></li>
<li><p><span data-ttu-id="f46db-182">サーバーの FQDN</span><span class="sxs-lookup"><span data-stu-id="f46db-182">Server FQDN</span></span></p></li>
<li><p><span data-ttu-id="f46db-183">Lync プールの FQDN</span><span class="sxs-lookup"><span data-stu-id="f46db-183">Lync pool FQDN</span></span></p></li>
<li><p><span data-ttu-id="f46db-184">簡単な会議 URL</span><span class="sxs-lookup"><span data-stu-id="f46db-184">Meet simple URLs</span></span></p></li>
<li><p><span data-ttu-id="f46db-185">簡単なダイヤルイン URL</span><span class="sxs-lookup"><span data-stu-id="f46db-185">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="f46db-186">簡単な管理 URL</span><span class="sxs-lookup"><span data-stu-id="f46db-186">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="f46db-187">または、簡易 URL のワイルドカード エントリ</span><span class="sxs-lookup"><span data-stu-id="f46db-187">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="f46db-188">SN = ee01。SAN = ee01。SAN = contoso .com。SAN = fabrikam .comSAN = ダイヤルイン。SAN = 管理</span><span class="sxs-lookup"><span data-stu-id="f46db-188">SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span></span></p>
<p><span data-ttu-id="f46db-189">ワイルドカード証明書使用時:</span><span class="sxs-lookup"><span data-stu-id="f46db-189">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="f46db-190">SN = ee01。SAN = ee01。SAN = \* .com</span><span class="sxs-lookup"><span data-stu-id="f46db-190">SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f46db-191">会議の簡易 URL が複数存在する場合、それらすべてをサブジェクト名の別名として含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="f46db-191">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="f46db-192">簡易 URL エントリにはワイルドカード エントリがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="f46db-192">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f46db-193">外部 Web</span><span class="sxs-lookup"><span data-stu-id="f46db-193">Web external</span></span></p></td>
<td><p><span data-ttu-id="f46db-194">プールの FQDN</span><span class="sxs-lookup"><span data-stu-id="f46db-194">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="f46db-195">次のうちのすべて:</span><span class="sxs-lookup"><span data-stu-id="f46db-195">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="f46db-196">外部 Web FQDN</span><span class="sxs-lookup"><span data-stu-id="f46db-196">External web FQDN</span></span></p></li>
<li><p><span data-ttu-id="f46db-197">簡単なダイヤルイン URL</span><span class="sxs-lookup"><span data-stu-id="f46db-197">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="f46db-198">簡単な管理 URL</span><span class="sxs-lookup"><span data-stu-id="f46db-198">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="f46db-199">または、簡易 URL のワイルドカード エントリ</span><span class="sxs-lookup"><span data-stu-id="f46db-199">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="f46db-200">SN = ee01。SAN = webcon01。SAN = contoso .com。SAN = fabrikam .comSAN = ダイヤルイン .com</span><span class="sxs-lookup"><span data-stu-id="f46db-200">SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span></span></p>
<p><span data-ttu-id="f46db-201">ワイルドカード証明書使用時:</span><span class="sxs-lookup"><span data-stu-id="f46db-201">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="f46db-202">SN = ee01。SAN = webcon01。SAN = \* .com</span><span class="sxs-lookup"><span data-stu-id="f46db-202">SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f46db-203">会議の簡易 URL が複数存在する場合、それらすべてをサブジェクト名の別名として含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="f46db-203">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="f46db-204">簡易 URL エントリにはワイルドカード エントリがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="f46db-204">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-director"></a><span data-ttu-id="f46db-205">ディレクターの証明書</span><span class="sxs-lookup"><span data-stu-id="f46db-205">Certificates for Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f46db-206">証明書</span><span class="sxs-lookup"><span data-stu-id="f46db-206">Certificate</span></span></th>
<th><span data-ttu-id="f46db-207">サブジェクト名/共通名</span><span class="sxs-lookup"><span data-stu-id="f46db-207">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="f46db-208">サブジェクト名の別名</span><span class="sxs-lookup"><span data-stu-id="f46db-208">Subject alternative name</span></span></th>
<th><span data-ttu-id="f46db-209">例</span><span class="sxs-lookup"><span data-stu-id="f46db-209">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f46db-210">既定値</span><span class="sxs-lookup"><span data-stu-id="f46db-210">Default</span></span></p></td>
<td><p><span data-ttu-id="f46db-211">ディレクター プールの FQDN</span><span class="sxs-lookup"><span data-stu-id="f46db-211">FQDN of the Director pool</span></span></p></td>
<td><p><span data-ttu-id="f46db-212">ディレクターの FQDN、ディレクター プールの FQDN</span><span class="sxs-lookup"><span data-stu-id="f46db-212">FQDN of the Director, FQDN of the Director pool</span></span></p>
<p><span data-ttu-id="f46db-213">このプールがクライアントの自動ログオン サーバーであり、グループ ポリシーで厳密な DNS マッチングが必要となる場合は、sip.sipdomain のエントリ (存在するそれぞれの SIP 用) も必要となります。</span><span class="sxs-lookup"><span data-stu-id="f46db-213">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need entries for sip.sipdomain (for each SIP domain you have).</span></span></p></td>
<td><p><span data-ttu-id="f46db-214">SN = pool.contoso.com;SAN = pool.contoso.com;SAN = dir01</span><span class="sxs-lookup"><span data-stu-id="f46db-214">SN=dir-pool.contoso.com; SAN=dir-pool.contoso.com; SAN=dir01.contoso.com</span></span></p>
<p><span data-ttu-id="f46db-215">このディレクター プールがクライアントの自動ログオン サーバーであり、グループ ポリシーで厳密な DNS マッチングが必要となる場合は、SAN=sip.contoso.com、SAN=sip.fabrikam.com も必要となります。</span><span class="sxs-lookup"><span data-stu-id="f46db-215">If this Director pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f46db-216">内部 Web</span><span class="sxs-lookup"><span data-stu-id="f46db-216">Web Internal</span></span></p></td>
<td><p><span data-ttu-id="f46db-217">サーバーの FQDN</span><span class="sxs-lookup"><span data-stu-id="f46db-217">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="f46db-218">次のうちのすべて:</span><span class="sxs-lookup"><span data-stu-id="f46db-218">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="f46db-219">内部 Web FQDN (サーバーの FQDN と同じ)</span><span class="sxs-lookup"><span data-stu-id="f46db-219">Internal web FQDN (which is the same as the FQDN of the server)</span></span></p></li>
<li><p><span data-ttu-id="f46db-220">サーバーの FQDN</span><span class="sxs-lookup"><span data-stu-id="f46db-220">Server FQDN</span></span></p></li>
<li><p><span data-ttu-id="f46db-221">Lync プールの FQDN</span><span class="sxs-lookup"><span data-stu-id="f46db-221">Lync pool FQDN</span></span></p></li>
<li><p><span data-ttu-id="f46db-222">簡単な会議 URL</span><span class="sxs-lookup"><span data-stu-id="f46db-222">Meet simple URLs</span></span></p></li>
<li><p><span data-ttu-id="f46db-223">簡単なダイヤルイン URL</span><span class="sxs-lookup"><span data-stu-id="f46db-223">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="f46db-224">簡単な管理 URL</span><span class="sxs-lookup"><span data-stu-id="f46db-224">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="f46db-225">または、簡易 URL のワイルドカード エントリ</span><span class="sxs-lookup"><span data-stu-id="f46db-225">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="f46db-226">SN = dir01。SAN = dir01。SAN = contoso .com。SAN = fabrikam .comSAN = ダイヤルイン。SAN = 管理</span><span class="sxs-lookup"><span data-stu-id="f46db-226">SN=dir01.contoso.com; SAN=dir01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span></span></p>
<p><span data-ttu-id="f46db-227">SN = dir01。SAN = dir01 (SAN = \* .com)</span><span class="sxs-lookup"><span data-stu-id="f46db-227">SN=dir01.contoso.com; SAN=dir01.contoso.com SAN=\*.contoso.com</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f46db-228">外部 Web</span><span class="sxs-lookup"><span data-stu-id="f46db-228">Web external</span></span></p></td>
<td><p><span data-ttu-id="f46db-229">サーバーの FQDN</span><span class="sxs-lookup"><span data-stu-id="f46db-229">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="f46db-230">次のうちのすべて:</span><span class="sxs-lookup"><span data-stu-id="f46db-230">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="f46db-231">外部 Web FQDN</span><span class="sxs-lookup"><span data-stu-id="f46db-231">External web FQDN</span></span></p></li>
<li><p><span data-ttu-id="f46db-232">簡単なダイヤルイン URL</span><span class="sxs-lookup"><span data-stu-id="f46db-232">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="f46db-233">簡単な管理 URL</span><span class="sxs-lookup"><span data-stu-id="f46db-233">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="f46db-234">または、簡易 URL のワイルドカード エントリ</span><span class="sxs-lookup"><span data-stu-id="f46db-234">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="f46db-235">ディレクターの外部 web FQDN は、フロントエンドプールまたはフロントエンドサーバーとは別のものにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f46db-235">The Director external web FQDN must be different from the Front End pool or Front End Server.</span></span></p>
<p><span data-ttu-id="f46db-236">SN = dir01。SAN = directorwebcon01、SAN = 「contoso .com」SAN = fabrikam .comSAN = ダイヤルイン .com</span><span class="sxs-lookup"><span data-stu-id="f46db-236">SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span></span></p>
<p><span data-ttu-id="f46db-237">SN = dir01。SAN = directorwebcon01 (SAN = \* .com)</span><span class="sxs-lookup"><span data-stu-id="f46db-237">SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=\*.contoso.com</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="f46db-p107">スタンドアロン仲介サーバー プールが存在する場合、プール内の仲介サーバーごとに、次の表に示す証明書が必要です。仲介サーバーがフロント エンド サーバーと併置されている場合、前の「フロント エンド プールのフロント エンド サーバーの証明書」の表に記載されていた証明書で十分です。</span><span class="sxs-lookup"><span data-stu-id="f46db-p107">If you have a stand-alone Mediation Server pool, the Mediation Servers in it each need the certificates listed in the following table. If you collocate Mediation Server with the Front End Servers, the certificates listed in the “Certificates for Front End Server in Front End Pool” table earlier in this topic are sufficient.</span></span>

### <a name="certificates-for-stand-alone-mediation-server"></a><span data-ttu-id="f46db-240">スタンドアロンの仲介サーバーの証明書</span><span class="sxs-lookup"><span data-stu-id="f46db-240">Certificates for Stand-alone Mediation Server</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f46db-241">証明書</span><span class="sxs-lookup"><span data-stu-id="f46db-241">Certificate</span></span></th>
<th><span data-ttu-id="f46db-242">サブジェクト名/共通名</span><span class="sxs-lookup"><span data-stu-id="f46db-242">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="f46db-243">サブジェクト名の別名</span><span class="sxs-lookup"><span data-stu-id="f46db-243">Subject alternative name</span></span></th>
<th><span data-ttu-id="f46db-244">例</span><span class="sxs-lookup"><span data-stu-id="f46db-244">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f46db-245">既定値</span><span class="sxs-lookup"><span data-stu-id="f46db-245">Default</span></span></p></td>
<td><p><span data-ttu-id="f46db-246">プールの FQDN</span><span class="sxs-lookup"><span data-stu-id="f46db-246">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="f46db-247">プールの FQDN</span><span class="sxs-lookup"><span data-stu-id="f46db-247">FQDN of the pool</span></span></p>
<p><span data-ttu-id="f46db-248">プール メンバー サーバーの FQDN</span><span class="sxs-lookup"><span data-stu-id="f46db-248">FQDN of pool member server</span></span></p></td>
<td><p><span data-ttu-id="f46db-249">SN = medsvr-pool.contoso.net;SAN = medsvr-pool.contoso.net;SAN = medsvr01</span><span class="sxs-lookup"><span data-stu-id="f46db-249">SN=medsvr-pool.contoso.net; SAN=medsvr-pool.contoso.net; SAN=medsvr01.contoso.net</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-survivable-branch-appliance"></a><span data-ttu-id="f46db-250">存続可能ブランチ アプライアンスの証明書</span><span class="sxs-lookup"><span data-stu-id="f46db-250">Certificates for Survivable Branch Appliance</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f46db-251">証明書</span><span class="sxs-lookup"><span data-stu-id="f46db-251">Certificate</span></span></th>
<th><span data-ttu-id="f46db-252">サブジェクト名/共通名</span><span class="sxs-lookup"><span data-stu-id="f46db-252">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="f46db-253">サブジェクト名の別名</span><span class="sxs-lookup"><span data-stu-id="f46db-253">Subject alternative name</span></span></th>
<th><span data-ttu-id="f46db-254">例</span><span class="sxs-lookup"><span data-stu-id="f46db-254">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f46db-255">既定値</span><span class="sxs-lookup"><span data-stu-id="f46db-255">Default</span></span></p></td>
<td><p><span data-ttu-id="f46db-256">アプライアンスの FQDN</span><span class="sxs-lookup"><span data-stu-id="f46db-256">FQDN of the appliance</span></span></p></td>
<td><p><span data-ttu-id="f46db-257">SIP。 &lt;microsoft.rtc.management.xds.sipdomain &gt; (SIP ドメインごとに1つのエントリが必要)</span><span class="sxs-lookup"><span data-stu-id="f46db-257">SIP.&lt;sipdomain&gt; (need one entry per SIP domain)</span></span></p></td>
<td><p><span data-ttu-id="f46db-258">SN = sba01;SAN = sip。SAN: fabrikam. .com</span><span class="sxs-lookup"><span data-stu-id="f46db-258">SN=sba01.contoso.net; SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="f46db-259">関連項目</span><span class="sxs-lookup"><span data-stu-id="f46db-259">See Also</span></span>


[<span data-ttu-id="f46db-260">Lync Server 2013 でのワイルドカード証明書のサポート</span><span class="sxs-lookup"><span data-stu-id="f46db-260">Wildcard certificate support in Lync Server 2013</span></span>](lync-server-2013-wildcard-certificate-support.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

