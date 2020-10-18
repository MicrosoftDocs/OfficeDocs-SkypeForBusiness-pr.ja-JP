---
title: 'Lync Server 2013: 内部サーバーの証明書要件'
description: 'Lync Server 2013: 内部サーバーの証明書要件。'
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
ms.openlocfilehash: dc1a627dd762c849b848087a96e00e19d320ef01
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575213"
---
# <a name="certificate-requirements-for-internal-servers-in-lync-server-2013"></a><span data-ttu-id="adde3-103">Lync Server 2013 の内部サーバーの証明書要件</span><span class="sxs-lookup"><span data-stu-id="adde3-103">Certificate requirements for internal servers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="adde3-104">_**トピックの最終更新日:** 2017-02-17_</span><span class="sxs-lookup"><span data-stu-id="adde3-104">_**Topic Last Modified:** 2017-02-17_</span></span>

<span data-ttu-id="adde3-105">Lync Server を実行していて、証明書を必要とする内部サーバーには、Standard Edition サーバー、Enterprise Edition フロントエンドサーバー、仲介サーバー、ディレクターがあります。</span><span class="sxs-lookup"><span data-stu-id="adde3-105">Internal servers that are running Lync Server and that require certificates include Standard Edition server, Enterprise Edition Front End Server, Mediation Server, and Director.</span></span> <span data-ttu-id="adde3-106">次の表に、これらのサーバーの証明書要件を示します。</span><span class="sxs-lookup"><span data-stu-id="adde3-106">The following table shows the certificate requirements for these servers.</span></span> <span data-ttu-id="adde3-107">Lync Server 証明書ウィザードを使用して、これらの証明書を要求できます。</span><span class="sxs-lookup"><span data-stu-id="adde3-107">You can use the Lync Server certificate wizard to request these certificates.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="adde3-108">ワイルドカード証明書は、フロントエンドプール、フロントエンドサーバー、またはディレクターの簡易 Url に関連付けられたサブジェクトの別名に対してサポートされています。</span><span class="sxs-lookup"><span data-stu-id="adde3-108">Wildcard certificates are supported for the subject alternative names associated with the simple URLs on the Front End pool, Front End Server, or Director.</span></span> <span data-ttu-id="adde3-109">ワイルドカード証明書のサポートの詳細については、「 <A href="lync-server-2013-wildcard-certificate-support.md">Lync Server 2013 のワイルドカード証明書のサポート</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="adde3-109">For details about wildcard certificate support, see <A href="lync-server-2013-wildcard-certificate-support.md">Wildcard certificate support in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="adde3-110">内部サーバーには内部のエンタープライズ証明機関 (CA) をお勧めしますが、パブリック CA を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="adde3-110">Although an internal enterprise certification authority (CA) is recommended for internal servers, you can also use a public CA.</span></span> <span data-ttu-id="adde3-111">統合コミュニケーション (UC) 証明書の特定の要件に準拠した証明書を提供し、Microsoft と提携して Lync Server 証明書ウィザードを使用できるようにするパブリック Ca の一覧については、「Microsoft Knowledge Base 929395 の記事「Exchange Server と通信サーバーのための統合コミュニケーション証明書パートナー」 () を参照してください [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834) 。</span><span class="sxs-lookup"><span data-stu-id="adde3-111">For a list of public CAs that provide certificates that comply with specific requirements for unified communications (UC) certificates and have partnered with Microsoft to ensure they work with the Lync Server Certificate Wizard, see article Microsoft Knowledge Base 929395, "Unified Communications Certificate Partners for Exchange Server and for Communications Server," at [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834).</span></span>

<span data-ttu-id="adde3-112">Exchange 2013 などの他のアプリケーションやサーバーと通信するには、他のアプリケーションと製品でサポートされている証明書が必要です。</span><span class="sxs-lookup"><span data-stu-id="adde3-112">Communication with other applications and servers, such as Exchange 2013, requires a certificate that is supported by the other applications and products.</span></span> <span data-ttu-id="adde3-113">2013リリース、Lync Server 2013、および Exchange 2013 および SharePoint Server を含むその他の Microsoft サーバー製品については、サーバー間の認証と承認のための Open Authorization (OAuth) プロトコルをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="adde3-113">For the 2013 release, Lync Server 2013 and other Microsoft server products, including Exchange 2013 and SharePoint Server, support the Open Authorization (OAuth) protocol for server-to-server authentication and authorization.</span></span> <span data-ttu-id="adde3-114">詳細については、「展開」のドキュメントまたは「操作」のドキュメントの「 [Lync server 2013 でのサーバー間認証 (OAuth) およびパートナーアプリケーションの管理](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="adde3-114">For details, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) in the Deployment documentation or the Operations documentation.</span></span>

<span data-ttu-id="adde3-115">Windows 7 オペレーティングシステム、Windows Server 2008 オペレーティングシステム、Windows Server 2008 R2 オペレーティングシステム、Windows Vista オペレーティングシステム、および Microsoft Lync Phone Edition を実行しているクライアントからの接続については、Lync Server 2013 では、SHA-256 暗号化ハッシュ関数を使用して署名された証明書をサポートしていますが、必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="adde3-115">For connections from clients running Windows 7 operating system, Windows Server 2008 operating system, Windows Server 2008 R2 operating system, Windows Vista operating system, and Microsoft Lync Phone Edition, Lync Server 2013 includes support for (but does not require) certificates signed using the SHA-256 cryptographic hash function.</span></span> <span data-ttu-id="adde3-116">SHA-256 を使用する外部アクセスをサポートするには、SHA-256 を使用するパブリック CA が外部証明書を発行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="adde3-116">To support external access using SHA-256, the external certificate is issued by a public CA using SHA-256.</span></span>

<span data-ttu-id="adde3-p106">次の表に、フロント エンド プールと Standard Edition サーバーの各サーバーの役割における証明書要件を示します。 これらはすべて、標準 Web サーバー、秘密キー、エクスポート不可能です。</span><span class="sxs-lookup"><span data-stu-id="adde3-p106">The following tables show certificate requirements by server role for Front End pools and Standard Edition servers. All these are standard web server certificates, private key, non-exportable.</span></span>

<span data-ttu-id="adde3-119">サーバーの拡張キー使用法 (EKU) は、証明書ウィザードを使って証明書を要求する際に自動的に構成されます。</span><span class="sxs-lookup"><span data-stu-id="adde3-119">Note that server enhanced key usage (EKU) is automatically configured when you use the certificate wizard to request certificates.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="adde3-120">各証明書のフレンドリ名は、コンピューターストア内で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="adde3-120">Each certificate Friendly Name must be unique in the computer store.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="adde3-121">DNS で sipinternal.contoso.com または sipexternal.contoso.com を構成した場合は、証明書のサブジェクトの別名に追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="adde3-121">If you have configured sipinternal.contoso.com or sipexternal.contoso.com in your DNS, you will need to add them in the certificate’s Subject Alternative Name.</span></span>



</div>

### <a name="certificates-for-standard-edition-server"></a><span data-ttu-id="adde3-122">Standard Edition サーバーの証明書</span><span class="sxs-lookup"><span data-stu-id="adde3-122">Certificates for Standard Edition Server</span></span>

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
<th><span data-ttu-id="adde3-123">証明書</span><span class="sxs-lookup"><span data-stu-id="adde3-123">Certificate</span></span></th>
<th><span data-ttu-id="adde3-124">サブジェクト名/共通名</span><span class="sxs-lookup"><span data-stu-id="adde3-124">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="adde3-125">サブジェクト名の別名</span><span class="sxs-lookup"><span data-stu-id="adde3-125">Subject alternative name</span></span></th>
<th><span data-ttu-id="adde3-126">例</span><span class="sxs-lookup"><span data-stu-id="adde3-126">Example</span></span></th>
<th><span data-ttu-id="adde3-127">Comments</span><span class="sxs-lookup"><span data-stu-id="adde3-127">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="adde3-128">既定値</span><span class="sxs-lookup"><span data-stu-id="adde3-128">Default</span></span></p></td>
<td><p><span data-ttu-id="adde3-129">プールの完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="adde3-129">Fully qualified domain name (FQDN) of the pool</span></span></p></td>
<td><p><span data-ttu-id="adde3-130">プールの FQDN およびサーバーの FQDN</span><span class="sxs-lookup"><span data-stu-id="adde3-130">FQDN of the pool and the FQDN of the server</span></span></p>
<p><span data-ttu-id="adde3-131">SIP ドメインが複数あり、自動クライアント構成が有効にされている場合は、証明書ウィザードで、サポートされている各 SIP ドメイン FQDN が検出され、追加されます。</span><span class="sxs-lookup"><span data-stu-id="adde3-131">If you have multiple SIP domains and have enabled automatic client configuration, the certificate wizard detects and adds each supported SIP domain FQDNs.</span></span></p>
<p><span data-ttu-id="adde3-132">このプールがクライアントの自動ログオン サーバーであり、グループ ポリシーで厳密なドメイン ネーム システム (DNS) マッチングが必要となる場合は、sip.sipdomain のエントリ (存在するそれぞれの SIP 用) も必要となります。</span><span class="sxs-lookup"><span data-stu-id="adde3-132">If this pool is the auto-logon server for clients and strict Domain Name System (DNS) matching is required in group policy, you also need entries for sip.sipdomain (for each SIP domain you have).</span></span></p></td>
<td><p><span data-ttu-id="adde3-133">SN = se01。SAN = se01</span><span class="sxs-lookup"><span data-stu-id="adde3-133">SN=se01.contoso.com; SAN=se01.contoso.com</span></span></p>
<p><span data-ttu-id="adde3-134">このプールがクライアントの自動ログオン サーバーであり、グループ ポリシーで厳密な DNS マッチングが必要となる場合は、SAN=sip.contoso.com、SAN=sip.fabrikam.com も必要となります。</span><span class="sxs-lookup"><span data-stu-id="adde3-134">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="adde3-135">Standard Edition サーバーに関しては、サーバー FQDN とプール FQDN は同じです。</span><span class="sxs-lookup"><span data-stu-id="adde3-135">On Standard Edition server, the server FQDN is the same as the pool FQDN.</span></span></p>
<p><span data-ttu-id="adde3-136">このウィザードでは、セットアップ時に指定した SIP ドメインが検出され、サブジェクト名の別名に自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="adde3-136">The wizard detects any SIP domains you specified during setup and automatically adds them to the subject alternative name.</span></span></p>
<p><span data-ttu-id="adde3-137">この証明書は、サーバー間認証に使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="adde3-137">You can also use this certificate for Server-to-Server Authentication.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="adde3-138">内部 Web</span><span class="sxs-lookup"><span data-stu-id="adde3-138">Web internal</span></span></p></td>
<td><p><span data-ttu-id="adde3-139">サーバーの FQDN</span><span class="sxs-lookup"><span data-stu-id="adde3-139">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="adde3-140">次のうちのすべて:</span><span class="sxs-lookup"><span data-stu-id="adde3-140">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="adde3-141">内部 Web FQDN (サーバーの FQDN と同じ)</span><span class="sxs-lookup"><span data-stu-id="adde3-141">Internal web FQDN (which is the same as the FQDN of the server)</span></span></p></li>
<li><p><span data-ttu-id="adde3-142">簡単な会議 URL</span><span class="sxs-lookup"><span data-stu-id="adde3-142">Meet simple URLs</span></span></p></li>
<li><p><span data-ttu-id="adde3-143">簡単なダイヤルイン URL</span><span class="sxs-lookup"><span data-stu-id="adde3-143">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="adde3-144">簡単な管理 URL</span><span class="sxs-lookup"><span data-stu-id="adde3-144">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="adde3-145">または、簡易 URL のワイルドカード エントリ</span><span class="sxs-lookup"><span data-stu-id="adde3-145">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="adde3-146">SN = se01。SAN = se01。SAN = contoso .com。SAN = fabrikam .comSAN = ダイヤルイン。SAN = 管理</span><span class="sxs-lookup"><span data-stu-id="adde3-146">SN=se01.contoso.com; SAN=se01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span></span></p>
<p><span data-ttu-id="adde3-147">ワイルドカード証明書使用時:</span><span class="sxs-lookup"><span data-stu-id="adde3-147">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="adde3-148">SN = se01。SAN = se01。SAN = \* .com</span><span class="sxs-lookup"><span data-stu-id="adde3-148">SN=se01.contoso.com; SAN=se01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="adde3-149">トポロジビルダーで内部 web FQDN を上書きすることはできません。</span><span class="sxs-lookup"><span data-stu-id="adde3-149">You cannot override the Internal web FQDN in Topology Builder.</span></span></p>
<p><span data-ttu-id="adde3-150">会議の簡易 URL が複数存在する場合、それらすべてをサブジェクト名の別名として含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="adde3-150">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="adde3-151">簡易 URL エントリにはワイルドカード エントリがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="adde3-151">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="adde3-152">外部 Web</span><span class="sxs-lookup"><span data-stu-id="adde3-152">Web external</span></span></p></td>
<td><p><span data-ttu-id="adde3-153">サーバーの FQDN</span><span class="sxs-lookup"><span data-stu-id="adde3-153">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="adde3-154">次のうちのすべて:</span><span class="sxs-lookup"><span data-stu-id="adde3-154">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="adde3-155">外部 Web FQDN</span><span class="sxs-lookup"><span data-stu-id="adde3-155">External web FQDN</span></span></p></li>
<li><p><span data-ttu-id="adde3-156">簡単なダイヤルイン URL</span><span class="sxs-lookup"><span data-stu-id="adde3-156">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="adde3-157">SIP ドメインごとに単純な Url を満たす</span><span class="sxs-lookup"><span data-stu-id="adde3-157">Meet simple URLs per SIP domain</span></span></p></li>
<li><p><span data-ttu-id="adde3-158">または、簡易 URL のワイルドカード エントリ</span><span class="sxs-lookup"><span data-stu-id="adde3-158">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="adde3-159">SN = se01。SAN = webcon01。SAN = contoso .com。SAN = fabrikam .comSAN = ダイヤルイン .com</span><span class="sxs-lookup"><span data-stu-id="adde3-159">SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span></span></p>
<p><span data-ttu-id="adde3-160">ワイルドカード証明書使用時:</span><span class="sxs-lookup"><span data-stu-id="adde3-160">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="adde3-161">SN = se01。SAN = webcon01。SAN = \* .com</span><span class="sxs-lookup"><span data-stu-id="adde3-161">SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="adde3-162">会議の簡易 URL が複数存在する場合、それらすべてをサブジェクト名の別名として含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="adde3-162">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="adde3-163">簡易 URL エントリにはワイルドカード エントリがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="adde3-163">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-front-end-server-in-a-front-end-pool"></a><span data-ttu-id="adde3-164">フロント エンド プールのフロント エンド サーバーの証明書</span><span class="sxs-lookup"><span data-stu-id="adde3-164">Certificates for Front End Server in a Front End Pool</span></span>

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
<th><span data-ttu-id="adde3-165">証明書</span><span class="sxs-lookup"><span data-stu-id="adde3-165">Certificate</span></span></th>
<th><span data-ttu-id="adde3-166">サブジェクト名/共通名</span><span class="sxs-lookup"><span data-stu-id="adde3-166">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="adde3-167">サブジェクト名の別名</span><span class="sxs-lookup"><span data-stu-id="adde3-167">Subject alternative name</span></span></th>
<th><span data-ttu-id="adde3-168">例</span><span class="sxs-lookup"><span data-stu-id="adde3-168">Example</span></span></th>
<th><span data-ttu-id="adde3-169">Comments</span><span class="sxs-lookup"><span data-stu-id="adde3-169">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="adde3-170">既定値</span><span class="sxs-lookup"><span data-stu-id="adde3-170">Default</span></span></p></td>
<td><p><span data-ttu-id="adde3-171">プールの FQDN</span><span class="sxs-lookup"><span data-stu-id="adde3-171">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="adde3-172">プールの FQDN およびサーバーの FQDN。</span><span class="sxs-lookup"><span data-stu-id="adde3-172">FQDN of the pool and FQDN of the server.</span></span></p>
<p><span data-ttu-id="adde3-173">SIP ドメインが複数あり、自動クライアント構成が有効にされている場合は、証明書ウィザードで、サポートされている各 SIP ドメイン FQDN が検出され、追加されます。</span><span class="sxs-lookup"><span data-stu-id="adde3-173">If you have multiple SIP domains and have enabled automatic client configuration, the certificate wizard detects and adds each supported SIP domain FQDNs.</span></span></p>
<p><span data-ttu-id="adde3-174">このプールがクライアントの自動ログオン サーバーであり、グループ ポリシーで厳密な DNS マッチングが必要となる場合は、sip.sipdomain のエントリ (存在するそれぞれの SIP 用) も必要となります。</span><span class="sxs-lookup"><span data-stu-id="adde3-174">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need entries for sip.sipdomain (for each SIP domain you have).</span></span></p></td>
<td><p><span data-ttu-id="adde3-175">SN = eepool。SAN = eepool、SAN = ee01</span><span class="sxs-lookup"><span data-stu-id="adde3-175">SN=eepool.contoso.com; SAN=eepool.contoso.com; SAN=ee01.contoso.com</span></span></p>
<p><span data-ttu-id="adde3-176">このプールがクライアントの自動ログオン サーバーであり、グループ ポリシーで厳密な DNS マッチングが必要となる場合は、SAN=sip.contoso.com、SAN=sip.fabrikam.com も必要となります。</span><span class="sxs-lookup"><span data-stu-id="adde3-176">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="adde3-177">このウィザードでは、セットアップ時に指定した SIP ドメインが検出され、サブジェクト名の別名に自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="adde3-177">The wizard detects any SIP domains you specified during setup and automatically adds them to the subject alternative name.</span></span></p>
<p><span data-ttu-id="adde3-178">この証明書は、サーバー間認証に使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="adde3-178">You can also use this certificate for Server-to-Server Authentication.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="adde3-179">内部 Web</span><span class="sxs-lookup"><span data-stu-id="adde3-179">Web Internal</span></span></p></td>
<td><p><span data-ttu-id="adde3-180">プールの FQDN</span><span class="sxs-lookup"><span data-stu-id="adde3-180">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="adde3-181">次のうちのすべて:</span><span class="sxs-lookup"><span data-stu-id="adde3-181">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="adde3-182">内部 web FQDN (サーバーの FQDN と同じではない)</span><span class="sxs-lookup"><span data-stu-id="adde3-182">Internal web FQDN (which is NOT the same as the FQDN of the server)</span></span></p></li>
<li><p><span data-ttu-id="adde3-183">サーバーの FQDN</span><span class="sxs-lookup"><span data-stu-id="adde3-183">Server FQDN</span></span></p></li>
<li><p><span data-ttu-id="adde3-184">Lync プールの FQDN</span><span class="sxs-lookup"><span data-stu-id="adde3-184">Lync pool FQDN</span></span></p></li>
<li><p><span data-ttu-id="adde3-185">簡単な会議 URL</span><span class="sxs-lookup"><span data-stu-id="adde3-185">Meet simple URLs</span></span></p></li>
<li><p><span data-ttu-id="adde3-186">簡単なダイヤルイン URL</span><span class="sxs-lookup"><span data-stu-id="adde3-186">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="adde3-187">簡単な管理 URL</span><span class="sxs-lookup"><span data-stu-id="adde3-187">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="adde3-188">または、簡易 URL のワイルドカード エントリ</span><span class="sxs-lookup"><span data-stu-id="adde3-188">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="adde3-189">SN = ee01。SAN = ee01。SAN = contoso .com。SAN = fabrikam .comSAN = ダイヤルイン。SAN = 管理</span><span class="sxs-lookup"><span data-stu-id="adde3-189">SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span></span></p>
<p><span data-ttu-id="adde3-190">ワイルドカード証明書使用時:</span><span class="sxs-lookup"><span data-stu-id="adde3-190">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="adde3-191">SN = ee01。SAN = ee01。SAN = \* .com</span><span class="sxs-lookup"><span data-stu-id="adde3-191">SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="adde3-192">会議の簡易 URL が複数存在する場合、それらすべてをサブジェクト名の別名として含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="adde3-192">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="adde3-193">簡易 URL エントリにはワイルドカード エントリがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="adde3-193">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="adde3-194">外部 Web</span><span class="sxs-lookup"><span data-stu-id="adde3-194">Web external</span></span></p></td>
<td><p><span data-ttu-id="adde3-195">プールの FQDN</span><span class="sxs-lookup"><span data-stu-id="adde3-195">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="adde3-196">次のうちのすべて:</span><span class="sxs-lookup"><span data-stu-id="adde3-196">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="adde3-197">外部 Web FQDN</span><span class="sxs-lookup"><span data-stu-id="adde3-197">External web FQDN</span></span></p></li>
<li><p><span data-ttu-id="adde3-198">簡単なダイヤルイン URL</span><span class="sxs-lookup"><span data-stu-id="adde3-198">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="adde3-199">簡単な管理 URL</span><span class="sxs-lookup"><span data-stu-id="adde3-199">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="adde3-200">または、簡易 URL のワイルドカード エントリ</span><span class="sxs-lookup"><span data-stu-id="adde3-200">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="adde3-201">SN = ee01。SAN = webcon01。SAN = contoso .com。SAN = fabrikam .comSAN = ダイヤルイン .com</span><span class="sxs-lookup"><span data-stu-id="adde3-201">SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span></span></p>
<p><span data-ttu-id="adde3-202">ワイルドカード証明書使用時:</span><span class="sxs-lookup"><span data-stu-id="adde3-202">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="adde3-203">SN = ee01。SAN = webcon01。SAN = \* .com</span><span class="sxs-lookup"><span data-stu-id="adde3-203">SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="adde3-204">会議の簡易 URL が複数存在する場合、それらすべてをサブジェクト名の別名として含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="adde3-204">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="adde3-205">簡易 URL エントリにはワイルドカード エントリがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="adde3-205">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-director"></a><span data-ttu-id="adde3-206">ディレクターの証明書</span><span class="sxs-lookup"><span data-stu-id="adde3-206">Certificates for Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="adde3-207">証明書</span><span class="sxs-lookup"><span data-stu-id="adde3-207">Certificate</span></span></th>
<th><span data-ttu-id="adde3-208">サブジェクト名/共通名</span><span class="sxs-lookup"><span data-stu-id="adde3-208">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="adde3-209">サブジェクト名の別名</span><span class="sxs-lookup"><span data-stu-id="adde3-209">Subject alternative name</span></span></th>
<th><span data-ttu-id="adde3-210">例</span><span class="sxs-lookup"><span data-stu-id="adde3-210">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="adde3-211">既定値</span><span class="sxs-lookup"><span data-stu-id="adde3-211">Default</span></span></p></td>
<td><p><span data-ttu-id="adde3-212">ディレクター プールの FQDN</span><span class="sxs-lookup"><span data-stu-id="adde3-212">FQDN of the Director pool</span></span></p></td>
<td><p><span data-ttu-id="adde3-213">ディレクターの FQDN、ディレクター プールの FQDN</span><span class="sxs-lookup"><span data-stu-id="adde3-213">FQDN of the Director, FQDN of the Director pool</span></span></p>
<p><span data-ttu-id="adde3-214">このプールがクライアントの自動ログオン サーバーであり、グループ ポリシーで厳密な DNS マッチングが必要となる場合は、sip.sipdomain のエントリ (存在するそれぞれの SIP 用) も必要となります。</span><span class="sxs-lookup"><span data-stu-id="adde3-214">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need entries for sip.sipdomain (for each SIP domain you have).</span></span></p></td>
<td><p><span data-ttu-id="adde3-215">SN = pool.contoso.com;SAN = pool.contoso.com;SAN = dir01</span><span class="sxs-lookup"><span data-stu-id="adde3-215">SN=dir-pool.contoso.com; SAN=dir-pool.contoso.com; SAN=dir01.contoso.com</span></span></p>
<p><span data-ttu-id="adde3-216">このディレクター プールがクライアントの自動ログオン サーバーであり、グループ ポリシーで厳密な DNS マッチングが必要となる場合は、SAN=sip.contoso.com、SAN=sip.fabrikam.com も必要となります。</span><span class="sxs-lookup"><span data-stu-id="adde3-216">If this Director pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="adde3-217">内部 Web</span><span class="sxs-lookup"><span data-stu-id="adde3-217">Web Internal</span></span></p></td>
<td><p><span data-ttu-id="adde3-218">サーバーの FQDN</span><span class="sxs-lookup"><span data-stu-id="adde3-218">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="adde3-219">次のうちのすべて:</span><span class="sxs-lookup"><span data-stu-id="adde3-219">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="adde3-220">内部 Web FQDN (サーバーの FQDN と同じ)</span><span class="sxs-lookup"><span data-stu-id="adde3-220">Internal web FQDN (which is the same as the FQDN of the server)</span></span></p></li>
<li><p><span data-ttu-id="adde3-221">サーバーの FQDN</span><span class="sxs-lookup"><span data-stu-id="adde3-221">Server FQDN</span></span></p></li>
<li><p><span data-ttu-id="adde3-222">Lync プールの FQDN</span><span class="sxs-lookup"><span data-stu-id="adde3-222">Lync pool FQDN</span></span></p></li>
<li><p><span data-ttu-id="adde3-223">簡単な会議 URL</span><span class="sxs-lookup"><span data-stu-id="adde3-223">Meet simple URLs</span></span></p></li>
<li><p><span data-ttu-id="adde3-224">簡単なダイヤルイン URL</span><span class="sxs-lookup"><span data-stu-id="adde3-224">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="adde3-225">簡単な管理 URL</span><span class="sxs-lookup"><span data-stu-id="adde3-225">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="adde3-226">または、簡易 URL のワイルドカード エントリ</span><span class="sxs-lookup"><span data-stu-id="adde3-226">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="adde3-227">SN = dir01。SAN = dir01。SAN = contoso .com。SAN = fabrikam .comSAN = ダイヤルイン。SAN = 管理</span><span class="sxs-lookup"><span data-stu-id="adde3-227">SN=dir01.contoso.com; SAN=dir01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span></span></p>
<p><span data-ttu-id="adde3-228">SN = dir01。SAN = dir01 (SAN = \* .com)</span><span class="sxs-lookup"><span data-stu-id="adde3-228">SN=dir01.contoso.com; SAN=dir01.contoso.com SAN=\*.contoso.com</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="adde3-229">外部 Web</span><span class="sxs-lookup"><span data-stu-id="adde3-229">Web external</span></span></p></td>
<td><p><span data-ttu-id="adde3-230">サーバーの FQDN</span><span class="sxs-lookup"><span data-stu-id="adde3-230">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="adde3-231">次のうちのすべて:</span><span class="sxs-lookup"><span data-stu-id="adde3-231">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="adde3-232">外部 Web FQDN</span><span class="sxs-lookup"><span data-stu-id="adde3-232">External web FQDN</span></span></p></li>
<li><p><span data-ttu-id="adde3-233">簡単なダイヤルイン URL</span><span class="sxs-lookup"><span data-stu-id="adde3-233">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="adde3-234">簡単な管理 URL</span><span class="sxs-lookup"><span data-stu-id="adde3-234">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="adde3-235">または、簡易 URL のワイルドカード エントリ</span><span class="sxs-lookup"><span data-stu-id="adde3-235">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="adde3-236">ディレクターの外部 web FQDN は、フロントエンドプールまたはフロントエンドサーバーとは別のものにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="adde3-236">The Director external web FQDN must be different from the Front End pool or Front End Server.</span></span></p>
<p><span data-ttu-id="adde3-237">SN = dir01。SAN = directorwebcon01、SAN = 「contoso .com」SAN = fabrikam .comSAN = ダイヤルイン .com</span><span class="sxs-lookup"><span data-stu-id="adde3-237">SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span></span></p>
<p><span data-ttu-id="adde3-238">SN = dir01。SAN = directorwebcon01 (SAN = \* .com)</span><span class="sxs-lookup"><span data-stu-id="adde3-238">SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=\*.contoso.com</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="adde3-p107">スタンドアロン仲介サーバー プールが存在する場合、プール内の仲介サーバーごとに、次の表に示す証明書が必要です。仲介サーバーがフロント エンド サーバーと併置されている場合、前の「フロント エンド プールのフロント エンド サーバーの証明書」の表に記載されていた証明書で十分です。</span><span class="sxs-lookup"><span data-stu-id="adde3-p107">If you have a stand-alone Mediation Server pool, the Mediation Servers in it each need the certificates listed in the following table. If you collocate Mediation Server with the Front End Servers, the certificates listed in the “Certificates for Front End Server in Front End Pool” table earlier in this topic are sufficient.</span></span>

### <a name="certificates-for-stand-alone-mediation-server"></a><span data-ttu-id="adde3-241">スタンドアロンの仲介サーバーの証明書</span><span class="sxs-lookup"><span data-stu-id="adde3-241">Certificates for Stand-alone Mediation Server</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="adde3-242">証明書</span><span class="sxs-lookup"><span data-stu-id="adde3-242">Certificate</span></span></th>
<th><span data-ttu-id="adde3-243">サブジェクト名/共通名</span><span class="sxs-lookup"><span data-stu-id="adde3-243">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="adde3-244">サブジェクト名の別名</span><span class="sxs-lookup"><span data-stu-id="adde3-244">Subject alternative name</span></span></th>
<th><span data-ttu-id="adde3-245">例</span><span class="sxs-lookup"><span data-stu-id="adde3-245">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="adde3-246">既定値</span><span class="sxs-lookup"><span data-stu-id="adde3-246">Default</span></span></p></td>
<td><p><span data-ttu-id="adde3-247">プールの FQDN</span><span class="sxs-lookup"><span data-stu-id="adde3-247">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="adde3-248">プールの FQDN</span><span class="sxs-lookup"><span data-stu-id="adde3-248">FQDN of the pool</span></span></p>
<p><span data-ttu-id="adde3-249">プール メンバー サーバーの FQDN</span><span class="sxs-lookup"><span data-stu-id="adde3-249">FQDN of pool member server</span></span></p></td>
<td><p><span data-ttu-id="adde3-250">SN = medsvr-pool.contoso.net;SAN = medsvr-pool.contoso.net;SAN = medsvr01</span><span class="sxs-lookup"><span data-stu-id="adde3-250">SN=medsvr-pool.contoso.net; SAN=medsvr-pool.contoso.net; SAN=medsvr01.contoso.net</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-survivable-branch-appliance"></a><span data-ttu-id="adde3-251">存続可能ブランチ アプライアンスの証明書</span><span class="sxs-lookup"><span data-stu-id="adde3-251">Certificates for Survivable Branch Appliance</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="adde3-252">証明書</span><span class="sxs-lookup"><span data-stu-id="adde3-252">Certificate</span></span></th>
<th><span data-ttu-id="adde3-253">サブジェクト名/共通名</span><span class="sxs-lookup"><span data-stu-id="adde3-253">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="adde3-254">サブジェクト名の別名</span><span class="sxs-lookup"><span data-stu-id="adde3-254">Subject alternative name</span></span></th>
<th><span data-ttu-id="adde3-255">例</span><span class="sxs-lookup"><span data-stu-id="adde3-255">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="adde3-256">既定値</span><span class="sxs-lookup"><span data-stu-id="adde3-256">Default</span></span></p></td>
<td><p><span data-ttu-id="adde3-257">アプライアンスの FQDN</span><span class="sxs-lookup"><span data-stu-id="adde3-257">FQDN of the appliance</span></span></p></td>
<td><p><span data-ttu-id="adde3-258">SIP。 &lt;microsoft.rtc.management.xds.sipdomain &gt; (SIP ドメインごとに1つのエントリが必要)</span><span class="sxs-lookup"><span data-stu-id="adde3-258">SIP.&lt;sipdomain&gt; (need one entry per SIP domain)</span></span></p></td>
<td><p><span data-ttu-id="adde3-259">SN = sba01;SAN = sip。SAN: fabrikam. .com</span><span class="sxs-lookup"><span data-stu-id="adde3-259">SN=sba01.contoso.net; SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="adde3-260">関連項目</span><span class="sxs-lookup"><span data-stu-id="adde3-260">See Also</span></span>


[<span data-ttu-id="adde3-261">Lync Server 2013 でのワイルドカード証明書のサポート</span><span class="sxs-lookup"><span data-stu-id="adde3-261">Wildcard certificate support in Lync Server 2013</span></span>](lync-server-2013-wildcard-certificate-support.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

