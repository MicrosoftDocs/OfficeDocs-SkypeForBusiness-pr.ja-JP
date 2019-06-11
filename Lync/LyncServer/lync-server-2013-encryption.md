---
title: 'Lync Server 2013: 暗号化'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Encryption for Lync Server 2013
ms:assetid: d18c74a6-385b-407b-98eb-0d525fa38fea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481135(v=OCS.15)
ms:contentKeyID: 59893874
ms.date: 09/14/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 01c989213b050bdb536e95a8a42e8f7b35292eaf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833233"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="encryption-for-lync-server-2013"></a><span data-ttu-id="1711f-102">Lync Server 2013 の暗号化</span><span class="sxs-lookup"><span data-stu-id="1711f-102">Encryption for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1711f-103">_**最終更新日:** 2017-09-14_</span><span class="sxs-lookup"><span data-stu-id="1711f-103">_**Topic Last Modified:** 2017-09-14_</span></span>

<span data-ttu-id="1711f-104">Microsoft Lync Server 2013 は、TLS と MTLS を使ってインスタントメッセージを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="1711f-104">Microsoft Lync Server 2013 uses TLS and MTLS to encrypt instant messages.</span></span> <span data-ttu-id="1711f-105">トラフィックが内部ネットワークに限定されているか、内部ネットワークの境界を越えるかに関係なく、MTLS は、サーバー間のすべてのトラフィックに必要です。</span><span class="sxs-lookup"><span data-stu-id="1711f-105">All server-to-server traffic requires MTLS, regardless of whether the traffic is confined to the internal network or crosses the internal network perimeter.</span></span> <span data-ttu-id="1711f-106">TLS は必須ではありませんが、仲介サーバーとメディアゲートウェイ間で行うことを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1711f-106">TLS is optional but strongly recommended between the Mediation Server and media gateway.</span></span> <span data-ttu-id="1711f-107">この接続に TLS を構成する場合は MTLS も必要です。</span><span class="sxs-lookup"><span data-stu-id="1711f-107">If TLS is configured on this link, MTLS is required.</span></span> <span data-ttu-id="1711f-108">そのため、ゲートウェイは、仲介サーバーによって信頼されている CA からの証明書を使って構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1711f-108">Therefore, the gateway must be configured with a certificate from a CA that is trusted by the Mediation Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1711f-109">SSL 3.0 に関するセキュリティ アドバイザリが 2014 年に公開されました。</span><span class="sxs-lookup"><span data-stu-id="1711f-109">A security advisory regarding SSL 3.0 was published in 2014.</span></span> <span data-ttu-id="1711f-110">Lync Server 2013 での SSL 3.0 の無効化はサポートされています。</span><span class="sxs-lookup"><span data-stu-id="1711f-110">Disabling SSL 3.0 in Lync Server 2013 is a supported option.</span></span> <span data-ttu-id="1711f-111">セキュリティアドバイザリの詳細については、 <A class=uri href="https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/">https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/</A>を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1711f-111">To learn more about the security advisory, see <A class=uri href="https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/">https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/</A>.</span></span>



</div>

<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="証券" alt="security" /><span data-ttu-id="1711f-113">セキュリティメモ:</span><span class="sxs-lookup"><span data-stu-id="1711f-113">Security Note:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="1711f-114">最強の暗号化プロトコルを使用するために、Lync Server 2013 は次の順序で TLS 暗号化プロトコルをクライアントに提供します。 <strong>tls 1.2</strong> 、 <strong>tls 1.1</strong>、 <strong>tls 1.0</strong>。</span><span class="sxs-lookup"><span data-stu-id="1711f-114">To ensure the strongest cryptographic protocol is used, Lync Server 2013 will offer TLS encryption protocols in the following order to clients: <strong>TLS 1.2</strong> , <strong>TLS 1.1</strong>, <strong>TLS 1.0</strong>.</span></span> <span data-ttu-id="1711f-115">TLS は Lync Server 2013 の重要な部分であるため、サポートされている環境を維持するために必要です。</span><span class="sxs-lookup"><span data-stu-id="1711f-115">TLS is a critical aspect of Lync Server 2013 and thus it is required in order to maintain a supported environment.</span></span></td>
</tr>
</tbody>
</table>


</div>

<span data-ttu-id="1711f-116">クライアント間トラフィックの要件は、トラフィックが社内のファイアウォールを通過するかどうかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="1711f-116">Requirements for client-to-client traffic depend on whether that traffic crosses the internal corporate firewall.</span></span> <span data-ttu-id="1711f-117">厳密には、すべての内部トラフィックで TLS を使うことができます。この場合、インスタントメッセージは暗号化され、TCP は使用されません。</span><span class="sxs-lookup"><span data-stu-id="1711f-117">Strictly internal traffic can use either TLS, in which case the instant message is encrypted, or TCP, in which case it is not.</span></span>

<span data-ttu-id="1711f-118">次の表に、各種トラフィックのプロトコル要件をまとめます。</span><span class="sxs-lookup"><span data-stu-id="1711f-118">The following table summarizes the protocol requirements for each type of traffic.</span></span>

### <a name="traffic-protection"></a><span data-ttu-id="1711f-119">トラフィックの保護</span><span class="sxs-lookup"><span data-stu-id="1711f-119">Traffic Protection</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1711f-120">トラフィックの種類</span><span class="sxs-lookup"><span data-stu-id="1711f-120">Traffic type</span></span></th>
<th><span data-ttu-id="1711f-121">保護用プロトコル</span><span class="sxs-lookup"><span data-stu-id="1711f-121">Protected by</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1711f-122">サーバー間</span><span class="sxs-lookup"><span data-stu-id="1711f-122">Server-to-server</span></span></p></td>
<td><p><span data-ttu-id="1711f-123">MTLS</span><span class="sxs-lookup"><span data-stu-id="1711f-123">MTLS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1711f-124">クライアントからサーバー</span><span class="sxs-lookup"><span data-stu-id="1711f-124">Client-to-server</span></span></p></td>
<td><p><span data-ttu-id="1711f-125">TLS</span><span class="sxs-lookup"><span data-stu-id="1711f-125">TLS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1711f-126">インスタント メッセージングとプレゼンス</span><span class="sxs-lookup"><span data-stu-id="1711f-126">Instant messaging and presence</span></span></p></td>
<td><p><span data-ttu-id="1711f-127">TLS (TLS 用に構成されている場合)</span><span class="sxs-lookup"><span data-stu-id="1711f-127">TLS (if configured for TLS)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1711f-128">オーディオとビデオ、メディアのデスクトップ共有</span><span class="sxs-lookup"><span data-stu-id="1711f-128">Audio and video and desktop sharing of media</span></span></p></td>
<td><p><span data-ttu-id="1711f-129">SRTP</span><span class="sxs-lookup"><span data-stu-id="1711f-129">SRTP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1711f-130">デスクトップ共有 (シグナリング)</span><span class="sxs-lookup"><span data-stu-id="1711f-130">Desktop sharing (signaling)</span></span></p></td>
<td><p><span data-ttu-id="1711f-131">TLS</span><span class="sxs-lookup"><span data-stu-id="1711f-131">TLS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1711f-132">Web 会議</span><span class="sxs-lookup"><span data-stu-id="1711f-132">Web conferencing</span></span></p></td>
<td><p><span data-ttu-id="1711f-133">TLS</span><span class="sxs-lookup"><span data-stu-id="1711f-133">TLS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1711f-134">会議コンテンツのダウンロード、アドレス帳のダウンロード、配布グループの拡張</span><span class="sxs-lookup"><span data-stu-id="1711f-134">Meeting content download, address book download, distribution group expansion</span></span></p></td>
<td><p><span data-ttu-id="1711f-135">HTTPS</span><span class="sxs-lookup"><span data-stu-id="1711f-135">HTTPS</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="media-encryption"></a><span data-ttu-id="1711f-136">メディアの暗号化</span><span class="sxs-lookup"><span data-stu-id="1711f-136">Media Encryption</span></span>

<span data-ttu-id="1711f-137">メディア トラフィックは、RTP トラフィックに対して機密性、認証、反射攻撃保護を提供する RTP (Real-Time Transport Protocol) のプロファイルである SRTP (Secure RTP) を使用して暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="1711f-137">Media traffic is encrypted using Secure RTP (SRTP), a profile of Real-Time Transport Protocol (RTP) that provides confidentiality, authentication, and replay attack protection to RTP traffic.</span></span> <span data-ttu-id="1711f-138">さらに、仲介サーバーと内部ネクスト ホップの間で双方向に流れるメディアも SRTP を使用して暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="1711f-138">In addition, media flowing in both directions between the Mediation Server and its internal next hop is also encrypted using SRTP.</span></span> <span data-ttu-id="1711f-139">仲介サーバーとメディアゲートウェイ間の両方向のメディアフローは、既定では暗号化されません。</span><span class="sxs-lookup"><span data-stu-id="1711f-139">Media flowing in both directions between the Mediation Server and a media gateway is not encrypted by default.</span></span> <span data-ttu-id="1711f-140">仲介サーバーはメディアゲートウェイへの暗号化をサポートしていますが、ゲートウェイは、MTLS と証明書のストレージをサポートしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="1711f-140">The Mediation Server can support encryption to the media gateway, but the gateway must support MTLS and storage of a certificate.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1711f-141">オーディオ/ビデオ (A/V) は、新しいバージョンの Windows Live Messenger でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="1711f-141">Audio/Video (A/V) is supported with the new version of Windows Live Messenger.</span></span> <span data-ttu-id="1711f-142">Windows Live Messenger との間で A/V フェデレーションを実装している場合は、Lync Server の暗号化レベルも変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1711f-142">If you are implementing A/V federation with Windows Live Messenger, you must also modify the Lync Server encryption level.</span></span> <span data-ttu-id="1711f-143">既定では、暗号化レベルは "必須" です。</span><span class="sxs-lookup"><span data-stu-id="1711f-143">By default, the encryption level is Required.</span></span> <span data-ttu-id="1711f-144">Lync Server 管理シェルを使用して、この設定を [サポート] に変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1711f-144">You must change this setting to Supported by using the Lync Server Management Shell.</span></span> <span data-ttu-id="1711f-145">詳細については、展開ドキュメントの「 <A href="lync-server-2013-deploying-external-user-access.md">Lync Server 2013 での外部ユーザーアクセスの展開</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1711f-145">For more information, see <A href="lync-server-2013-deploying-external-user-access.md">Deploying external user access in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="1711f-146">オーディオおよびビデオのメディアトラフィックは、Microsoft Lync 2013 と Windows Live クライアントの間で暗号化されません。</span><span class="sxs-lookup"><span data-stu-id="1711f-146">Audio and video media traffic is not encrypted between Microsoft Lync 2013 and Windows Live clients.</span></span>

</div>

<div>

## <a name="fips"></a><span data-ttu-id="1711f-147">FIPS</span><span class="sxs-lookup"><span data-stu-id="1711f-147">FIPS</span></span>

<span data-ttu-id="1711f-148">Lync Server 2013 と Microsoft Exchange Server 2013 は、Windows Server オペレーティングシステムがシステム暗号化用 FIPS 140-2 アルゴリズムを使用するように構成されている場合に、米国連邦情報処理標準 (FIPS) 140-2 アルゴリズムのサポートと共に動作します。</span><span class="sxs-lookup"><span data-stu-id="1711f-148">Lync Server 2013 and Microsoft Exchange Server 2013 operate with support for Federal Information Processing Standard (FIPS) 140-2 algorithms if the Windows Server operating systems are configured to use the FIPS 140-2 algorithms for system cryptography.</span></span> <span data-ttu-id="1711f-149">FIPS サポートを実装するには、Lync Server 2013 を実行している各サーバーでサポートされるように構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1711f-149">To implement FIPS support, you must configure each server running Lync Server 2013 to support it.</span></span> <span data-ttu-id="1711f-150">FIPS 準拠アルゴリズムの使用、および FIPS サポートの実装方法の詳細については、「Microsoft サポート技術情報の記事 811833 (「システム暗号化: 暗号化、ハッシュ、署名のための FIPS 準拠アルゴリズムを使用する」のセキュリティ) を参照してください。Windows XP と windows の以降のバージョンでの設定[http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833)。</span><span class="sxs-lookup"><span data-stu-id="1711f-150">For details about the use of FIPS-compliant algorithms and how to implement FIPS support, see Microsoft Knowledge Base article 811833, The effects of enabling the “System cryptography: Use FIPS compliant algorithms for encryption, hashing, and signing" security setting in Windows XP and in later versions of Windows at [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833).</span></span> <span data-ttu-id="1711f-151">Exchange 2010 の FIPS 140-2 のサポートと制限事項の詳細については、「Exchange 2010 SP1 と FIPS [https://go.microsoft.com/fwlink/p/?LinkId=205335](https://go.microsoft.com/fwlink/p/?linkid=205335)準拠アルゴリズムのサポート」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1711f-151">For details about FIPS 140-2 support and limitations in Exchange 2010, see Exchange 2010 SP1 and Support for FIPS Compliant Algorithms at [https://go.microsoft.com/fwlink/p/?LinkId=205335](https://go.microsoft.com/fwlink/p/?linkid=205335).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

