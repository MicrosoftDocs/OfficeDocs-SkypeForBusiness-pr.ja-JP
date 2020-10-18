---
title: 'Lync Server 2013: 暗号化'
description: 'Lync Server 2013: 暗号化。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Encryption for Lync Server 2013
ms:assetid: d18c74a6-385b-407b-98eb-0d525fa38fea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481135(v=OCS.15)
ms:contentKeyID: 59893874
ms.date: 09/14/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ab2c46af16cfdbb9a01631777e65219acb2ceb2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575653"
---
# <a name="encryption-for-lync-server-2013"></a><span data-ttu-id="8f575-103">Lync Server 2013 の暗号化</span><span class="sxs-lookup"><span data-stu-id="8f575-103">Encryption for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8f575-104">_**トピックの最終更新日:** 2017-09-14_</span><span class="sxs-lookup"><span data-stu-id="8f575-104">_**Topic Last Modified:** 2017-09-14_</span></span>

<span data-ttu-id="8f575-105">Microsoft Lync Server 2013 は TLS と MTLS を使用してインスタントメッセージを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="8f575-105">Microsoft Lync Server 2013 uses TLS and MTLS to encrypt instant messages.</span></span> <span data-ttu-id="8f575-106">すべてのサーバー間トラフィックは、トラフィックが内部ネットワークに限定されているか、または内部ネットワーク境界を越えているかに関係なく、MTLS を必要とします。</span><span class="sxs-lookup"><span data-stu-id="8f575-106">All server-to-server traffic requires MTLS, regardless of whether the traffic is confined to the internal network or crosses the internal network perimeter.</span></span> <span data-ttu-id="8f575-107">TLS はオプションですが、仲介サーバーとメディアゲートウェイ間で強く推奨されます。</span><span class="sxs-lookup"><span data-stu-id="8f575-107">TLS is optional but strongly recommended between the Mediation Server and media gateway.</span></span> <span data-ttu-id="8f575-108">このリンクで TLS が構成されている場合は、MTLS が必要です。</span><span class="sxs-lookup"><span data-stu-id="8f575-108">If TLS is configured on this link, MTLS is required.</span></span> <span data-ttu-id="8f575-109">そのため、仲介サーバーによって信頼されている CA からの証明書を使用してゲートウェイを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8f575-109">Therefore, the gateway must be configured with a certificate from a CA that is trusted by the Mediation Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8f575-110">SSL 3.0 に関するセキュリティアドバイザリは、2014で公開されました。</span><span class="sxs-lookup"><span data-stu-id="8f575-110">A security advisory regarding SSL 3.0 was published in 2014.</span></span> <span data-ttu-id="8f575-111">Lync Server 2013 で SSL 3.0 を無効にする方法はサポートされています。</span><span class="sxs-lookup"><span data-stu-id="8f575-111">Disabling SSL 3.0 in Lync Server 2013 is a supported option.</span></span> <span data-ttu-id="8f575-112">セキュリティアドバイザリの詳細については、「」を参照してください <A class=uri href="https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/">https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/</A> 。</span><span class="sxs-lookup"><span data-stu-id="8f575-112">To learn more about the security advisory, see <A class=uri href="https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/">https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/</A>.</span></span>



</div>

<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="security" alt="security" /><span data-ttu-id="8f575-114">セキュリティに関する注意事項:</span><span class="sxs-lookup"><span data-stu-id="8f575-114">Security Note:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="8f575-115">最強の暗号化プロトコルが使用されるように、Lync Server 2013 は tls 暗号化プロトコルを次の順序でクライアントに提供します。 <strong>tls 1.2</strong> 、 <strong>tls 1.1</strong>、 <strong>tls 1.0</strong>。</span><span class="sxs-lookup"><span data-stu-id="8f575-115">To ensure the strongest cryptographic protocol is used, Lync Server 2013 will offer TLS encryption protocols in the following order to clients: <strong>TLS 1.2</strong> , <strong>TLS 1.1</strong>, <strong>TLS 1.0</strong>.</span></span> <span data-ttu-id="8f575-116">TLS は Lync Server 2013 の重要な部分であるため、サポートされている環境を維持するために必要です。</span><span class="sxs-lookup"><span data-stu-id="8f575-116">TLS is a critical aspect of Lync Server 2013 and thus it is required in order to maintain a supported environment.</span></span></td>
</tr>
</tbody>
</table>


</div>

<span data-ttu-id="8f575-p104">クライアント間のトラフィックに対する要件は、そのトラフィックが内部の企業ファイアウォールを越えるかどうかによって異なります。厳密に言えば、内部のトラフィックでは、TLS を使用することも (インスタント メッセージが暗号化される)、TCP を使用することも (インスタント メッセージが暗号化されない) できます。</span><span class="sxs-lookup"><span data-stu-id="8f575-p104">Requirements for client-to-client traffic depend on whether that traffic crosses the internal corporate firewall. Strictly internal traffic can use either TLS, in which case the instant message is encrypted, or TCP, in which case it is not.</span></span>

<span data-ttu-id="8f575-119">次の表に、各種トラフィックのプロトコル要件をまとめます。</span><span class="sxs-lookup"><span data-stu-id="8f575-119">The following table summarizes the protocol requirements for each type of traffic.</span></span>

### <a name="traffic-protection"></a><span data-ttu-id="8f575-120">トラフィックの保護</span><span class="sxs-lookup"><span data-stu-id="8f575-120">Traffic Protection</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8f575-121">トラフィックの種類</span><span class="sxs-lookup"><span data-stu-id="8f575-121">Traffic type</span></span></th>
<th><span data-ttu-id="8f575-122">保護用プロトコル</span><span class="sxs-lookup"><span data-stu-id="8f575-122">Protected by</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8f575-123">サーバー間</span><span class="sxs-lookup"><span data-stu-id="8f575-123">Server-to-server</span></span></p></td>
<td><p><span data-ttu-id="8f575-124">MTLS</span><span class="sxs-lookup"><span data-stu-id="8f575-124">MTLS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f575-125">クライアントからサーバーへ</span><span class="sxs-lookup"><span data-stu-id="8f575-125">Client-to-server</span></span></p></td>
<td><p><span data-ttu-id="8f575-126">TLS</span><span class="sxs-lookup"><span data-stu-id="8f575-126">TLS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f575-127">インスタント メッセージングおよびプレゼンス</span><span class="sxs-lookup"><span data-stu-id="8f575-127">Instant messaging and presence</span></span></p></td>
<td><p><span data-ttu-id="8f575-128">TLS (TLS 用に構成されている場合)</span><span class="sxs-lookup"><span data-stu-id="8f575-128">TLS (if configured for TLS)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f575-129">オーディオとビデオ、およびメディアのデスクトップ共有</span><span class="sxs-lookup"><span data-stu-id="8f575-129">Audio and video and desktop sharing of media</span></span></p></td>
<td><p><span data-ttu-id="8f575-130">SRTP</span><span class="sxs-lookup"><span data-stu-id="8f575-130">SRTP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f575-131">デスクトップ共有 (シグナリング)</span><span class="sxs-lookup"><span data-stu-id="8f575-131">Desktop sharing (signaling)</span></span></p></td>
<td><p><span data-ttu-id="8f575-132">TLS</span><span class="sxs-lookup"><span data-stu-id="8f575-132">TLS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f575-133">Web 会議</span><span class="sxs-lookup"><span data-stu-id="8f575-133">Web conferencing</span></span></p></td>
<td><p><span data-ttu-id="8f575-134">TLS</span><span class="sxs-lookup"><span data-stu-id="8f575-134">TLS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f575-135">会議コンテンツのダウンロード、アドレス帳のダウンロード、配布グループの拡張</span><span class="sxs-lookup"><span data-stu-id="8f575-135">Meeting content download, address book download, distribution group expansion</span></span></p></td>
<td><p><span data-ttu-id="8f575-136">HTTPS</span><span class="sxs-lookup"><span data-stu-id="8f575-136">HTTPS</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="media-encryption"></a><span data-ttu-id="8f575-137">メディアの暗号化</span><span class="sxs-lookup"><span data-stu-id="8f575-137">Media Encryption</span></span>

<span data-ttu-id="8f575-138">メディアトラフィックは、セキュリティで保護された RTP (SRTP) を使用して暗号化されます。 Real-Time トランスポートプロトコル (RTP) のプロファイルは、機密性、認証、および再生攻撃保護を RTP トラフィックに提供します。</span><span class="sxs-lookup"><span data-stu-id="8f575-138">Media traffic is encrypted using Secure RTP (SRTP), a profile of Real-Time Transport Protocol (RTP) that provides confidentiality, authentication, and replay attack protection to RTP traffic.</span></span> <span data-ttu-id="8f575-139">さらに、仲介サーバーとその内部の次ホップの間で双方向に流れるメディアも、SRTP を使用して暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="8f575-139">In addition, media flowing in both directions between the Mediation Server and its internal next hop is also encrypted using SRTP.</span></span> <span data-ttu-id="8f575-140">仲介サーバーとメディアゲートウェイ間の両方の方向に流れるメディアは、既定では暗号化されません。</span><span class="sxs-lookup"><span data-stu-id="8f575-140">Media flowing in both directions between the Mediation Server and a media gateway is not encrypted by default.</span></span> <span data-ttu-id="8f575-141">仲介サーバーはメディアゲートウェイへの暗号化をサポートできますが、ゲートウェイは、証明書の MTLS と記憶域をサポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8f575-141">The Mediation Server can support encryption to the media gateway, but the gateway must support MTLS and storage of a certificate.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8f575-142">音声/ビデオ (A/V) は、新しいバージョンの Windows Live Messenger でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="8f575-142">Audio/Video (A/V) is supported with the new version of Windows Live Messenger.</span></span> <span data-ttu-id="8f575-143">Windows Live Messenger で音声ビデオ フェデレーションを実装する場合は、Lync Server の暗号化レベルを変更する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="8f575-143">If you are implementing A/V federation with Windows Live Messenger, you must also modify the Lync Server encryption level.</span></span> <span data-ttu-id="8f575-144">既定では、暗号化レベルは "必須" です。</span><span class="sxs-lookup"><span data-stu-id="8f575-144">By default, the encryption level is Required.</span></span> <span data-ttu-id="8f575-145">Lync Server 管理シェルを使用して、この設定を [サポート] に変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8f575-145">You must change this setting to Supported by using the Lync Server Management Shell.</span></span> <span data-ttu-id="8f575-146">詳細については、「展開」のドキュメントの「Deployment <A href="lync-server-2013-deploying-external-user-access.md">external user access In Lync Server 2013</A> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f575-146">For more information, see <A href="lync-server-2013-deploying-external-user-access.md">Deploying external user access in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="8f575-147">音声およびビデオのメディアトラフィックは、Microsoft Lync 2013 と Windows Live クライアントの間では暗号化されません。</span><span class="sxs-lookup"><span data-stu-id="8f575-147">Audio and video media traffic is not encrypted between Microsoft Lync 2013 and Windows Live clients.</span></span>

</div>

<div>

## <a name="fips"></a><span data-ttu-id="8f575-148">使う</span><span class="sxs-lookup"><span data-stu-id="8f575-148">FIPS</span></span>

<span data-ttu-id="8f575-149">Lync Server 2013 と Microsoft Exchange Server 2013 は、Windows Server オペレーティングシステムがシステム暗号化用の FIPS 140-2 アルゴリズムを使用するように構成されている場合、連邦情報処理規格 (FIPS) の140-2 アルゴリズムをサポートするように動作します。</span><span class="sxs-lookup"><span data-stu-id="8f575-149">Lync Server 2013 and Microsoft Exchange Server 2013 operate with support for Federal Information Processing Standard (FIPS) 140-2 algorithms if the Windows Server operating systems are configured to use the FIPS 140-2 algorithms for system cryptography.</span></span> <span data-ttu-id="8f575-150">FIPS サポートを実装するには、Lync Server 2013 を実行している各サーバーをサポートするように構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8f575-150">To implement FIPS support, you must configure each server running Lync Server 2013 to support it.</span></span> <span data-ttu-id="8f575-151">FIPS 準拠アルゴリズムの使用方法、および FIPS サポートを実装する方法の詳細については、「Microsoft サポート技術情報の記事811833」を参照してください。 Windows XP 以降のバージョンの Windows では、「システム暗号化: 暗号化、ハッシュ、署名に FIPS 準拠アルゴリズムを使用する」のセキュリティ設定を有効にした場合の影響 [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833) 。</span><span class="sxs-lookup"><span data-stu-id="8f575-151">For details about the use of FIPS-compliant algorithms and how to implement FIPS support, see Microsoft Knowledge Base article 811833, The effects of enabling the “System cryptography: Use FIPS compliant algorithms for encryption, hashing, and signing" security setting in Windows XP and in later versions of Windows at [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833).</span></span> <span data-ttu-id="8f575-152">Exchange 2010 の FIPS 140-2 サポートおよび制限事項の詳細については、「Exchange 2010 SP1 とサポート」の「FIPS 準拠アルゴリズムのサポート」を参照してください [https://go.microsoft.com/fwlink/p/?LinkId=205335](https://go.microsoft.com/fwlink/p/?linkid=205335) 。</span><span class="sxs-lookup"><span data-stu-id="8f575-152">For details about FIPS 140-2 support and limitations in Exchange 2010, see Exchange 2010 SP1 and Support for FIPS Compliant Algorithms at [https://go.microsoft.com/fwlink/p/?LinkId=205335](https://go.microsoft.com/fwlink/p/?linkid=205335).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

