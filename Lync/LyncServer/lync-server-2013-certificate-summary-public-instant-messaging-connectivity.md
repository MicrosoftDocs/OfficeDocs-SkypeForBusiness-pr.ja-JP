---
title: 'Lync Server 2013: 証明書の概要-パブリックインスタントメッセージングの接続'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Public instant messaging connectivity
ms:assetid: 2b3687ee-50c2-4c1c-880e-8dcf8bd4f309
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618370(v=OCS.15)
ms:contentKeyID: 49105657
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5c93e79eed643d608ac9ab04516222227fc7c1f6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736637"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---public-instant-messaging-connectivity-in-lync-server-2013"></a><span data-ttu-id="422ae-102">証明書の概要-Lync Server 2013 でのパブリックインスタントメッセージング接続</span><span class="sxs-lookup"><span data-stu-id="422ae-102">Certificate summary - Public instant messaging connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="422ae-103">_**最終更新日:** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="422ae-103">_**Topic Last Modified:** 2013-02-19_</span></span>

<span data-ttu-id="422ae-104">パブリックインスタントメッセージング接続用の証明書を構成するには、まず、America Online (AOL) には固有のものが必要であることを除き、他の SIP フェデレーションタイプまたは標準エッジサーバーの証明書には何も違いがないことに注意してください。証明書の構成。</span><span class="sxs-lookup"><span data-stu-id="422ae-104">To configure certificates for public Instant Messaging connectivity, you should first notice that there is nothing different from other SIP federation types or even standard Edge Server certificates, except that America Online (AOL) requires a unique certificate configuration.</span></span> <span data-ttu-id="422ae-105">America Online では、通常のサーバー拡張キー使用法 (EKU) に加えて、証明書または証明書 (Edge プールの場合) がクライアント EKU も含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="422ae-105">In addition to the usual server enhanced key usage (EKU), America Online requires the certificate or certificates (in the case of an Edge pool) to also contain the client EKU.</span></span> <span data-ttu-id="422ae-106">クライアント EKU は証明書に追加されたものであり、エッジサーバーに割り当てられている外部公開証明書の一部です。</span><span class="sxs-lookup"><span data-stu-id="422ae-106">The client EKU is an addition to the certificate, and is part of the external public certificate that is assigned to your Edge Server.</span></span>

<div>

## <a name="certificate-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="422ae-107">証明書の概要–パブリックインスタントメッセージング接続</span><span class="sxs-lookup"><span data-stu-id="422ae-107">Certificate Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="422ae-108">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="422ae-108">Component</span></span></th>
<th><span data-ttu-id="422ae-109">サブジェクト名</span><span class="sxs-lookup"><span data-stu-id="422ae-109">Subject name</span></span></th>
<th><span data-ttu-id="422ae-110">サブジェクト代替名 (SAN)/Order</span><span class="sxs-lookup"><span data-stu-id="422ae-110">Subject alternative names (SAN)/Order</span></span></th>
<th><span data-ttu-id="422ae-111">コメント</span><span class="sxs-lookup"><span data-stu-id="422ae-111">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="422ae-112">外部/アクセスエッジ</span><span class="sxs-lookup"><span data-stu-id="422ae-112">External/Access Edge</span></span></p></td>
<td><p><span data-ttu-id="422ae-113">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="422ae-113">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="422ae-114">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="422ae-114">sip.contoso.com</span></span></p>
<p><span data-ttu-id="422ae-115">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="422ae-115">webcon.contoso.com</span></span></p>
<p><span data-ttu-id="422ae-116">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="422ae-116">sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="422ae-117">証明書はパブリック CA からである必要があります。また、AOL とのパブリック IM 接続を展開する場合は、サーバーの EKU とクライアントの EKU を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="422ae-117">The certificate must be from a Public CA, and must have the server EKU and client EKU if public IM connectivity with AOL is to be deployed.</span></span> <span data-ttu-id="422ae-118">証明書は、次のための外部エッジサーバーインターフェイスに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="422ae-118">The certificate is assigned to the external Edge Server interfaces for:</span></span></p>
<ul>
<li><p><span data-ttu-id="422ae-119">アクセス エッジ サービス</span><span class="sxs-lookup"><span data-stu-id="422ae-119">Access Edge service</span></span></p></li>
<li><p><span data-ttu-id="422ae-120">Web 会議エッジ サービス</span><span class="sxs-lookup"><span data-stu-id="422ae-120">Web Conferencing Edge service</span></span></p></li>
<li><p><span data-ttu-id="422ae-121">音声ビデオ エッジ サービス</span><span class="sxs-lookup"><span data-stu-id="422ae-121">A/V Edge service</span></span></p></li>
</ul>
<p><span data-ttu-id="422ae-122">San は、トポロジビルダーの定義に基づいて、自動的に証明書に追加されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="422ae-122">Note that SANs are automatically added to the certificate based on your definitions in Topology Builder.</span></span> <span data-ttu-id="422ae-123">必要に応じて、必要に応じて SAN エントリを追加します。これには、サポートが必要な追加の SIP ドメインや他のエントリも含まれます。</span><span class="sxs-lookup"><span data-stu-id="422ae-123">You add SAN entries as needed for additional SIP domains and other entries that you need to support.</span></span> <span data-ttu-id="422ae-124">サブジェクト名は SAN でレプリケートされ、正しい操作のために存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="422ae-124">The subject name is replicated in the SAN and must be present for correct operation.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="422ae-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="422ae-125">See Also</span></span>


[<span data-ttu-id="422ae-126">Lync Server 2013 の外部ユーザー アクセスのシナリオ</span><span class="sxs-lookup"><span data-stu-id="422ae-126">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

