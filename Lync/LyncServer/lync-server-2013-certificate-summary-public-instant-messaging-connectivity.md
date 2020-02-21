---
title: 'Lync Server 2013: 証明書の概要-パブリックインスタントメッセージング接続'
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
ms.openlocfilehash: 3cacf411f348199376e1564be37f683854480872
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187410"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-summary---public-instant-messaging-connectivity-in-lync-server-2013"></a><span data-ttu-id="5b66e-102">証明書の概要-Lync Server 2013 でのパブリックインスタントメッセージング接続</span><span class="sxs-lookup"><span data-stu-id="5b66e-102">Certificate summary - Public instant messaging connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5b66e-103">_**トピックの最終更新日:** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="5b66e-103">_**Topic Last Modified:** 2013-02-19_</span></span>

<span data-ttu-id="5b66e-104">パブリックインスタントメッセージング接続の証明書を構成するには、最初に、他の SIP フェデレーションタイプまたは標準エッジサーバー証明書とは異なるものがあることに注意してください。ただし、America Online (AOL) には固有のものが必要です。証明書の構成。</span><span class="sxs-lookup"><span data-stu-id="5b66e-104">To configure certificates for public Instant Messaging connectivity, you should first notice that there is nothing different from other SIP federation types or even standard Edge Server certificates, except that America Online (AOL) requires a unique certificate configuration.</span></span> <span data-ttu-id="5b66e-105">通常のサーバー拡張キー使用法 (EKU) に加えて、America Online では証明書または証明書 (エッジプールの場合) にもクライアント EKU を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="5b66e-105">In addition to the usual server enhanced key usage (EKU), America Online requires the certificate or certificates (in the case of an Edge pool) to also contain the client EKU.</span></span> <span data-ttu-id="5b66e-106">クライアント EKU は証明書に追加され、エッジサーバーに割り当てられている外部公開証明書の一部です。</span><span class="sxs-lookup"><span data-stu-id="5b66e-106">The client EKU is an addition to the certificate, and is part of the external public certificate that is assigned to your Edge Server.</span></span>

<div>

## <a name="certificate-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="5b66e-107">証明書の概要 - パブリック インスタント メッセージング接続</span><span class="sxs-lookup"><span data-stu-id="5b66e-107">Certificate Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5b66e-108">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="5b66e-108">Component</span></span></th>
<th><span data-ttu-id="5b66e-109">サブジェクト名</span><span class="sxs-lookup"><span data-stu-id="5b66e-109">Subject name</span></span></th>
<th><span data-ttu-id="5b66e-110">サブジェクトの別名 (SAN)/順序</span><span class="sxs-lookup"><span data-stu-id="5b66e-110">Subject alternative names (SAN)/Order</span></span></th>
<th><span data-ttu-id="5b66e-111">コメント</span><span class="sxs-lookup"><span data-stu-id="5b66e-111">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5b66e-112">外部/アクセス エッジ</span><span class="sxs-lookup"><span data-stu-id="5b66e-112">External/Access Edge</span></span></p></td>
<td><p><span data-ttu-id="5b66e-113">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5b66e-113">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5b66e-114">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5b66e-114">sip.contoso.com</span></span></p>
<p><span data-ttu-id="5b66e-115">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5b66e-115">webcon.contoso.com</span></span></p>
<p><span data-ttu-id="5b66e-116">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="5b66e-116">sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="5b66e-117">証明書は、パブリック CA からのものである必要があり、AOL とのパブリック IM 接続を展開する場合は、サーバー EKU とクライアント EKU を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="5b66e-117">The certificate must be from a Public CA, and must have the server EKU and client EKU if public IM connectivity with AOL is to be deployed.</span></span> <span data-ttu-id="5b66e-118">証明書は、次のような外部エッジサーバーインターフェイスに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="5b66e-118">The certificate is assigned to the external Edge Server interfaces for:</span></span></p>
<ul>
<li><p><span data-ttu-id="5b66e-119">アクセス エッジ サービス</span><span class="sxs-lookup"><span data-stu-id="5b66e-119">Access Edge service</span></span></p></li>
<li><p><span data-ttu-id="5b66e-120">Web 会議エッジ サービス</span><span class="sxs-lookup"><span data-stu-id="5b66e-120">Web Conferencing Edge service</span></span></p></li>
<li><p><span data-ttu-id="5b66e-121">音声ビデオ エッジ サービス</span><span class="sxs-lookup"><span data-stu-id="5b66e-121">A/V Edge service</span></span></p></li>
</ul>
<p><span data-ttu-id="5b66e-p103">SAN は、トポロジ ビルダーの定義に基づいて自動的に証明書に追加されます。追加の SIP ドメインで必要な SAN エントリや、サポートする必要がある他のエントリを追加します。SAN にはサブジェクト名がレプリケートされるため、正常に動作するためにはサブジェクト名が存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="5b66e-p103">Note that SANs are automatically added to the certificate based on your definitions in Topology Builder. You add SAN entries as needed for additional SIP domains and other entries that you need to support. The subject name is replicated in the SAN and must be present for correct operation.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5b66e-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="5b66e-125">See Also</span></span>


[<span data-ttu-id="5b66e-126">Lync Server 2013 での外部ユーザーアクセスのシナリオ</span><span class="sxs-lookup"><span data-stu-id="5b66e-126">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

