---
title: 'Lync Server 2013: XMPP フェデレーション パートナーのネゴシエーション設定'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Negotiation settings for XMPP federated partners
ms:assetid: ef773942-ef92-4f71-85a1-738dfebdfa00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552456(v=OCS.15)
ms:contentKeyID: 48679567
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 02d72870e4060be6aa4ec428159af7ab19cb68b1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826711"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="negotiation-settings-for-xmpp-federated-partners-in-lync-server-2013"></a><span data-ttu-id="b5c8f-102">Lync Server 2013 の XMPP フェデレーション パートナーのネゴシエーション設定</span><span class="sxs-lookup"><span data-stu-id="b5c8f-102">Negotiation settings for XMPP federated partners in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b5c8f-103">_**最終更新日:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="b5c8f-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="b5c8f-104">XMPP パートナーの構成でのネゴシエーションの種類の設定には、さまざまな組み合わせが用意されています。</span><span class="sxs-lookup"><span data-stu-id="b5c8f-104">The settings for the negotiation types in the configuration of an XMPP Partner have a wide variety of possible combinations.</span></span> <span data-ttu-id="b5c8f-105">これらの組み合わせの一部は有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="b5c8f-105">Not all of these combinations are valid.</span></span> <span data-ttu-id="b5c8f-106">このトピックで詳しく説明する表では、有効な設定と無効な設定を定義しています。</span><span class="sxs-lookup"><span data-stu-id="b5c8f-106">The table detailed in this topic will define the valid and not valid settings.</span></span> <span data-ttu-id="b5c8f-107">一般的な構成は、最初の表の2番目の表で、可能なすべての組み合わせの詳細を示しています。</span><span class="sxs-lookup"><span data-stu-id="b5c8f-107">Common configurations are presented in the first table, the second table detailing all possible combinations.</span></span> <span data-ttu-id="b5c8f-108">*トランスポート層セキュリティ*(TLS) も使用できる**場合を除き**、*単純な認証とセキュリティレイヤー* (SASL) を持つことはできないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="b5c8f-108">Note that you cannot have *Simple Authentication and Security Layer* (SASL) **unless** *Transport Layer Security* (TLS) is also available.</span></span> <span data-ttu-id="b5c8f-109">SASL は、暗号化されていない (読み取り可能な) 形式で送信され、TLS などの別の手段で保護されている場合を除き、送信しないでください。</span><span class="sxs-lookup"><span data-stu-id="b5c8f-109">SASL is sent in an unencrypted (readable) format and should never be transmitted unless protected by another means, such as TLS.</span></span>

### <a name="common-xmpp-federation-negotiation-methods"></a><span data-ttu-id="b5c8f-110">一般的な XMPP のフェデレーションネゴシエーションの方法</span><span class="sxs-lookup"><span data-stu-id="b5c8f-110">Common XMPP Federation Negotiation Methods</span></span>

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
<th><span data-ttu-id="b5c8f-111">トランスポート層セキュリティ (TLS)</span><span class="sxs-lookup"><span data-stu-id="b5c8f-111">Transport Layer Security (TLS)</span></span></th>
<th><span data-ttu-id="b5c8f-112">簡易認証とセキュリティレイヤー (SASL)</span><span class="sxs-lookup"><span data-stu-id="b5c8f-112">Simple Authentication and Security Layer (SASL)</span></span></th>
<th><span data-ttu-id="b5c8f-113">ダイヤルバックの認証</span><span class="sxs-lookup"><span data-stu-id="b5c8f-113">Dialback Authentication</span></span></th>
<th><span data-ttu-id="b5c8f-114">予期される認証方法</span><span class="sxs-lookup"><span data-stu-id="b5c8f-114">Expected Authentication Method(s)</span></span></th>
<th><span data-ttu-id="b5c8f-115">ノート</span><span class="sxs-lookup"><span data-stu-id="b5c8f-115">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b5c8f-116">必須</span><span class="sxs-lookup"><span data-stu-id="b5c8f-116">Required</span></span></p></td>
<td><p><span data-ttu-id="b5c8f-117">必須</span><span class="sxs-lookup"><span data-stu-id="b5c8f-117">Required</span></span></p></td>
<td><p><span data-ttu-id="b5c8f-118">False</span><span class="sxs-lookup"><span data-stu-id="b5c8f-118">False</span></span></p></td>
<td><p><span data-ttu-id="b5c8f-119">TLS 経由の SASL</span><span class="sxs-lookup"><span data-stu-id="b5c8f-119">SASL over TLS</span></span></p></td>
<td><p><span data-ttu-id="b5c8f-120">TLS と SASL は、SASL メッセージストリームがセキュリティで保護されていることを確認するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="b5c8f-120">TLS and SASL required helps to ensure that the SASL message stream is secure.</span></span> <span data-ttu-id="b5c8f-121">コールバックは使用できません。 XMPP フェデレーションパートナーが TLS を必須またはオプションに設定していない場合は、フォールバックメソッドに使用できません。</span><span class="sxs-lookup"><span data-stu-id="b5c8f-121">Dialback is not available and cannot be used for a fallback method if the XMPP federated partner has not set TLS to required or optional.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5c8f-122">必須</span><span class="sxs-lookup"><span data-stu-id="b5c8f-122">Required</span></span></p></td>
<td><p><span data-ttu-id="b5c8f-123">省略可能</span><span class="sxs-lookup"><span data-stu-id="b5c8f-123">Optional</span></span></p></td>
<td><p><span data-ttu-id="b5c8f-124">True</span><span class="sxs-lookup"><span data-stu-id="b5c8f-124">True</span></span></p></td>
<td><p><span data-ttu-id="b5c8f-125">TLS 経由の SASL、TLS コールバック、TCP コールバック</span><span class="sxs-lookup"><span data-stu-id="b5c8f-125">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="b5c8f-126">XMPP フェデレーションパートナーが、オプションまたは必須の SASL に SASL を設定している場合は、TLS を要求することによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="b5c8f-126">By requiring TLS, if the XMPP federated partner has set SASL to optional or required SASL is used.</span></span> <span data-ttu-id="b5c8f-127">SASL が利用できない場合は、TLS 経由のダイヤルバックが使用されます。</span><span class="sxs-lookup"><span data-stu-id="b5c8f-127">If SASL is not available, Dialback over TLS will be used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5c8f-128">省略可能</span><span class="sxs-lookup"><span data-stu-id="b5c8f-128">Optional</span></span></p></td>
<td><p><span data-ttu-id="b5c8f-129">省略可能</span><span class="sxs-lookup"><span data-stu-id="b5c8f-129">Optional</span></span></p></td>
<td><p><span data-ttu-id="b5c8f-130">True</span><span class="sxs-lookup"><span data-stu-id="b5c8f-130">True</span></span></p></td>
<td><p><span data-ttu-id="b5c8f-131">TLS 経由の SASL、TLS コールバック、TCP コールバック</span><span class="sxs-lookup"><span data-stu-id="b5c8f-131">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="b5c8f-132">提供されているネゴシエーションの方法は非常に柔軟ですが、これらの設定は XMPP フェデレーションパートナーの設定に依存します。</span><span class="sxs-lookup"><span data-stu-id="b5c8f-132">While very flexible in the negotiation methods offered, these settings rely on the XMPP federation partner’s settings.</span></span> <span data-ttu-id="b5c8f-133">パートナーに TLS がオプションまたは必須であるが、SASL はサポートされていない場合は、TLS のコールバックが利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="b5c8f-133">If the partner has TLS optional or required but SASL is not supported, TLS Dialback will be available.</span></span> <span data-ttu-id="b5c8f-134">パートナーの TLS と SASL がオプションまたは必須に設定されている場合は、SASL を介した TLS の最適な選択が使用されます。</span><span class="sxs-lookup"><span data-stu-id="b5c8f-134">If the partner has TLS and SASL set to optional or required, the optimal selection of TLS over SASL is used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5c8f-135">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="b5c8f-135">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="b5c8f-136">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="b5c8f-136">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="b5c8f-137">True</span><span class="sxs-lookup"><span data-stu-id="b5c8f-137">True</span></span></p></td>
<td><p><span data-ttu-id="b5c8f-138">TCP コールバック</span><span class="sxs-lookup"><span data-stu-id="b5c8f-138">TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="b5c8f-139">多くの場合、TCP コールバックは唯一の解決策です。</span><span class="sxs-lookup"><span data-stu-id="b5c8f-139">In many cases, TCP Dialback is the only possible solution.</span></span> <span data-ttu-id="b5c8f-140">他のオプションよりも望ましいのは、何らかの信頼レベルを提供することです。</span><span class="sxs-lookup"><span data-stu-id="b5c8f-140">Less desirable than other options, it does provide some level of trust.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="xmpp-federation-negotiation-methods-matrix---complete"></a><span data-ttu-id="b5c8f-141">XMPP フェデレーションネゴシエーションメソッドマトリックス-完了</span><span class="sxs-lookup"><span data-stu-id="b5c8f-141">XMPP Federation Negotiation Methods Matrix - Complete</span></span>

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
<th><span data-ttu-id="b5c8f-142">トランスポート層セキュリティ (TLS)</span><span class="sxs-lookup"><span data-stu-id="b5c8f-142">Transport Layer Security (TLS)</span></span></th>
<th><span data-ttu-id="b5c8f-143">簡易認証とセキュリティレイヤー (SASL)</span><span class="sxs-lookup"><span data-stu-id="b5c8f-143">Simple Authentication and Security Layer (SASL)</span></span></th>
<th><span data-ttu-id="b5c8f-144">ダイヤルバックの認証</span><span class="sxs-lookup"><span data-stu-id="b5c8f-144">Dialback Authentication</span></span></th>
<th><span data-ttu-id="b5c8f-145">予期される認証方法</span><span class="sxs-lookup"><span data-stu-id="b5c8f-145">Expected Authentication Method</span></span></th>
<th><span data-ttu-id="b5c8f-146">無効な構成のメモ、警告、またはエラー</span><span class="sxs-lookup"><span data-stu-id="b5c8f-146">Notes, Warning or Error for Not Valid Configuration</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b5c8f-147">必須</span><span class="sxs-lookup"><span data-stu-id="b5c8f-147">Required</span></span></p></td>
<td><p><span data-ttu-id="b5c8f-148">必須</span><span class="sxs-lookup"><span data-stu-id="b5c8f-148">Required</span></span></p></td>
<td><p><span data-ttu-id="b5c8f-149">True</span><span class="sxs-lookup"><span data-stu-id="b5c8f-149">True</span></span></p></td>
<td><p><span data-ttu-id="b5c8f-150">TLS 経由の SASL</span><span class="sxs-lookup"><span data-stu-id="b5c8f-150">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="b5c8f-151">SASL と TLS の両方が必要な場合、コールバックは動作しません。</span><span class="sxs-lookup"><span data-stu-id="b5c8f-151">Dialback will not operate if both SASL and TLS are required.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5c8f-152">必須</span><span class="sxs-lookup"><span data-stu-id="b5c8f-152">Required</span></span></p></td>
<td><p><span data-ttu-id="b5c8f-153">必須</span><span class="sxs-lookup"><span data-stu-id="b5c8f-153">Required</span></span></p></td>
<td><p><span data-ttu-id="b5c8f-154">False</span><span class="sxs-lookup"><span data-stu-id="b5c8f-154">False</span></span></p></td>
<td><p><span data-ttu-id="b5c8f-155">TLS 経由の SASL</span><span class="sxs-lookup"><span data-stu-id="b5c8f-155">SASL over TLS</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5c8f-156">省略可能</span><span class="sxs-lookup"><span data-stu-id="b5c8f-156">Optional</span></span></p></td>
<td><p><span data-ttu-id="b5c8f-157">必須</span><span class="sxs-lookup"><span data-stu-id="b5c8f-157">Required</span></span></p></td>
<td><p><span data-ttu-id="b5c8f-158">True</span><span class="sxs-lookup"><span data-stu-id="b5c8f-158">True</span></span></p></td>
<td><p><span data-ttu-id="b5c8f-159">TLS 経由の SASL、TLS コールバック、TCP コールバック</span><span class="sxs-lookup"><span data-stu-id="b5c8f-159">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="b5c8f-160">SASL には TLS が必要です。</span><span class="sxs-lookup"><span data-stu-id="b5c8f-160">SASL requires TLS.</span></span> <span data-ttu-id="b5c8f-161">TLS をオプションとして許可すると、セッションのネゴシエーションが失敗する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b5c8f-161">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5c8f-162">省略可能</span><span class="sxs-lookup"><span data-stu-id="b5c8f-162">Optional</span></span></p></td>
<td><p><span data-ttu-id="b5c8f-163">必須</span><span class="sxs-lookup"><span data-stu-id="b5c8f-163">Required</span></span></p></td>
<td><p><span data-ttu-id="b5c8f-164">False</span><span class="sxs-lookup"><span data-stu-id="b5c8f-164">False</span></span></p></td>
<td><p><span data-ttu-id="b5c8f-165">TLS 経由の SASL</span><span class="sxs-lookup"><span data-stu-id="b5c8f-165">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="b5c8f-166">SASL には TLS が必要です。</span><span class="sxs-lookup"><span data-stu-id="b5c8f-166">SASL requires TLS.</span></span> <span data-ttu-id="b5c8f-167">TLS をオプションとして許可すると、セッションのネゴシエーションが失敗する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b5c8f-167">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5c8f-168">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="b5c8f-168">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="b5c8f-169">必須</span><span class="sxs-lookup"><span data-stu-id="b5c8f-169">Required</span></span></p></td>
<td><p><span data-ttu-id="b5c8f-170">True</span><span class="sxs-lookup"><span data-stu-id="b5c8f-170">True</span></span></p></td>
<td><p><span data-ttu-id="b5c8f-171">TCP コールバック</span><span class="sxs-lookup"><span data-stu-id="b5c8f-171">TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="b5c8f-172">SASL には TLS が必要です。</span><span class="sxs-lookup"><span data-stu-id="b5c8f-172">SASL requires TLS.</span></span> <span data-ttu-id="b5c8f-173">TLS をオプションとして許可すると、セッションのネゴシエーションが失敗する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b5c8f-173">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5c8f-174">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="b5c8f-174">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="b5c8f-175">必須</span><span class="sxs-lookup"><span data-stu-id="b5c8f-175">Required</span></span></p></td>
<td><p><span data-ttu-id="b5c8f-176">False</span><span class="sxs-lookup"><span data-stu-id="b5c8f-176">False</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="b5c8f-177">有効な構成ではありません</span><span class="sxs-lookup"><span data-stu-id="b5c8f-177">Not Valid Configuration</span></span>


</div></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="b5c8f-178">SASL には TLS が必要であるため、TLS は利用できません。 SASL/TLS は成功しません。</span><span class="sxs-lookup"><span data-stu-id="b5c8f-178">Because SASL requires TLS, and TLS is not available, SASL/TLS cannot succeed.</span></span> <span data-ttu-id="b5c8f-179">TCP コールバックは false に設定されているため、使用できません。</span><span class="sxs-lookup"><span data-stu-id="b5c8f-179">TCP Dialback is set to false, and cannot be used.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5c8f-180">必須</span><span class="sxs-lookup"><span data-stu-id="b5c8f-180">Required</span></span></p></td>
<td><p><span data-ttu-id="b5c8f-181">省略可能</span><span class="sxs-lookup"><span data-stu-id="b5c8f-181">Optional</span></span></p></td>
<td><p><span data-ttu-id="b5c8f-182">True</span><span class="sxs-lookup"><span data-stu-id="b5c8f-182">True</span></span></p></td>
<td><p><span data-ttu-id="b5c8f-183">Tls による SASL、TLS のコールバック</span><span class="sxs-lookup"><span data-stu-id="b5c8f-183">SASL over TLS, TLS Dialback</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5c8f-184">必須</span><span class="sxs-lookup"><span data-stu-id="b5c8f-184">Required</span></span></p></td>
<td><p><span data-ttu-id="b5c8f-185">省略可能</span><span class="sxs-lookup"><span data-stu-id="b5c8f-185">Optional</span></span></p></td>
<td><p><span data-ttu-id="b5c8f-186">False</span><span class="sxs-lookup"><span data-stu-id="b5c8f-186">False</span></span></p></td>
<td><p><span data-ttu-id="b5c8f-187">TLS 経由の SASL</span><span class="sxs-lookup"><span data-stu-id="b5c8f-187">SASL over TLS</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5c8f-188">省略可能</span><span class="sxs-lookup"><span data-stu-id="b5c8f-188">Optional</span></span></p></td>
<td><p><span data-ttu-id="b5c8f-189">省略可能</span><span class="sxs-lookup"><span data-stu-id="b5c8f-189">Optional</span></span></p></td>
<td><p><span data-ttu-id="b5c8f-190">True</span><span class="sxs-lookup"><span data-stu-id="b5c8f-190">True</span></span></p></td>
<td><p><span data-ttu-id="b5c8f-191">TLS 経由の SASL、TLS コールバック、TCP コールバック</span><span class="sxs-lookup"><span data-stu-id="b5c8f-191">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="b5c8f-192">SASL には TLS が必要です。</span><span class="sxs-lookup"><span data-stu-id="b5c8f-192">SASL requires TLS.</span></span> <span data-ttu-id="b5c8f-193">TLS をオプションとして許可すると、セッションのネゴシエーションが失敗する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b5c8f-193">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5c8f-194">省略可能</span><span class="sxs-lookup"><span data-stu-id="b5c8f-194">Optional</span></span></p></td>
<td><p><span data-ttu-id="b5c8f-195">省略可能</span><span class="sxs-lookup"><span data-stu-id="b5c8f-195">Optional</span></span></p></td>
<td><p><span data-ttu-id="b5c8f-196">False</span><span class="sxs-lookup"><span data-stu-id="b5c8f-196">False</span></span></p></td>
<td><p><span data-ttu-id="b5c8f-197">TLS 経由の SASL</span><span class="sxs-lookup"><span data-stu-id="b5c8f-197">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="b5c8f-198">SASL には TLS が必要です。</span><span class="sxs-lookup"><span data-stu-id="b5c8f-198">SASL requires TLS.</span></span> <span data-ttu-id="b5c8f-199">TLS をオプションとして許可すると、セッションのネゴシエーションが失敗する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b5c8f-199">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5c8f-200">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="b5c8f-200">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="b5c8f-201">省略可能</span><span class="sxs-lookup"><span data-stu-id="b5c8f-201">Optional</span></span></p></td>
<td><p><span data-ttu-id="b5c8f-202">True</span><span class="sxs-lookup"><span data-stu-id="b5c8f-202">True</span></span></p></td>
<td><p><span data-ttu-id="b5c8f-203">TCP コールバック</span><span class="sxs-lookup"><span data-stu-id="b5c8f-203">TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="b5c8f-204">SASL には TLS が必要です。</span><span class="sxs-lookup"><span data-stu-id="b5c8f-204">SASL requires TLS.</span></span> <span data-ttu-id="b5c8f-205">TLS をオプションとして許可すると、セッションのネゴシエーションが失敗する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b5c8f-205">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5c8f-206">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="b5c8f-206">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="b5c8f-207">省略可能</span><span class="sxs-lookup"><span data-stu-id="b5c8f-207">Optional</span></span></p></td>
<td><p><span data-ttu-id="b5c8f-208">False</span><span class="sxs-lookup"><span data-stu-id="b5c8f-208">False</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="b5c8f-209">有効な構成ではありません</span><span class="sxs-lookup"><span data-stu-id="b5c8f-209">Not Valid Configuration</span></span>


</div></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="b5c8f-210">SASL には TLS が必要です。</span><span class="sxs-lookup"><span data-stu-id="b5c8f-210">SASL requires TLS.</span></span> <span data-ttu-id="b5c8f-211">TLS をオプションとして許可すると、セッションのネゴシエーションが失敗する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b5c8f-211">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5c8f-212">必須</span><span class="sxs-lookup"><span data-stu-id="b5c8f-212">Required</span></span></p></td>
<td><p><span data-ttu-id="b5c8f-213">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="b5c8f-213">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="b5c8f-214">True</span><span class="sxs-lookup"><span data-stu-id="b5c8f-214">True</span></span></p></td>
<td><p><span data-ttu-id="b5c8f-215">TLS のコールバック</span><span class="sxs-lookup"><span data-stu-id="b5c8f-215">TLS Dialback</span></span></p></td>
<td><p><span data-ttu-id="b5c8f-216">構成により、TLS のコールバックが可能になります。</span><span class="sxs-lookup"><span data-stu-id="b5c8f-216">Configuration allows for TLS Dialback.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5c8f-217">必須</span><span class="sxs-lookup"><span data-stu-id="b5c8f-217">Required</span></span></p></td>
<td><p><span data-ttu-id="b5c8f-218">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="b5c8f-218">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="b5c8f-219">False</span><span class="sxs-lookup"><span data-stu-id="b5c8f-219">False</span></span></p></td>
<td><p><span data-ttu-id="b5c8f-220">有効な構成ではありません</span><span class="sxs-lookup"><span data-stu-id="b5c8f-220">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="b5c8f-221">SASL またはダイヤルバックを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b5c8f-221">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5c8f-222">省略可能</span><span class="sxs-lookup"><span data-stu-id="b5c8f-222">Optional</span></span></p></td>
<td><p><span data-ttu-id="b5c8f-223">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="b5c8f-223">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="b5c8f-224">True</span><span class="sxs-lookup"><span data-stu-id="b5c8f-224">True</span></span></p></td>
<td><p><span data-ttu-id="b5c8f-225">TLS のダイヤルバック, TCP コールバック</span><span class="sxs-lookup"><span data-stu-id="b5c8f-225">TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="b5c8f-226">他のエンドポイントのネゴシエーションの選択肢に基づいて、TCP または TLS のコールバックが受け入れられます。</span><span class="sxs-lookup"><span data-stu-id="b5c8f-226">Based on negotiation choices of the other end point, TCP or TLS Dialback will be accepted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5c8f-227">省略可能</span><span class="sxs-lookup"><span data-stu-id="b5c8f-227">Optional</span></span></p></td>
<td><p><span data-ttu-id="b5c8f-228">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="b5c8f-228">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="b5c8f-229">False</span><span class="sxs-lookup"><span data-stu-id="b5c8f-229">False</span></span></p></td>
<td><p><span data-ttu-id="b5c8f-230">有効な構成ではありません</span><span class="sxs-lookup"><span data-stu-id="b5c8f-230">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="b5c8f-231">SASL またはダイヤルバックを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b5c8f-231">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5c8f-232">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="b5c8f-232">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="b5c8f-233">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="b5c8f-233">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="b5c8f-234">True</span><span class="sxs-lookup"><span data-stu-id="b5c8f-234">True</span></span></p></td>
<td><p><span data-ttu-id="b5c8f-235">TCP コールバック</span><span class="sxs-lookup"><span data-stu-id="b5c8f-235">TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="b5c8f-236">TCP コールバックは、唯一利用可能なネゴシエーションの方法です。</span><span class="sxs-lookup"><span data-stu-id="b5c8f-236">TCP Dialback is the only negotiation method available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5c8f-237">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="b5c8f-237">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="b5c8f-238">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="b5c8f-238">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="b5c8f-239">False</span><span class="sxs-lookup"><span data-stu-id="b5c8f-239">False</span></span></p></td>
<td><p><span data-ttu-id="b5c8f-240">有効な構成ではありません</span><span class="sxs-lookup"><span data-stu-id="b5c8f-240">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="b5c8f-241">SASL またはダイヤルバックを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b5c8f-241">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

