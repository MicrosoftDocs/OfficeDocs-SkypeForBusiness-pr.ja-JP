---
title: 'Lync Server 2013: XMPP フェデレーションパートナーのネゴシエーション設定'
description: 'Lync Server 2013: XMPP フェデレーションパートナーのネゴシエーション設定。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Negotiation settings for XMPP federated partners
ms:assetid: ef773942-ef92-4f71-85a1-738dfebdfa00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552456(v=OCS.15)
ms:contentKeyID: 48679567
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ac3d9c69d407dc750a1afb35f0a448869a88f09
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578643"
---
# <a name="negotiation-settings-for-xmpp-federated-partners-in-lync-server-2013"></a><span data-ttu-id="06fad-103">Lync Server 2013 での XMPP フェデレーションパートナーのネゴシエーション設定</span><span class="sxs-lookup"><span data-stu-id="06fad-103">Negotiation settings for XMPP federated partners in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="06fad-104">_**トピックの最終更新日:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="06fad-104">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="06fad-105">XMPP パートナーの構成におけるネゴシエーションの種類の設定には、さまざまな組み合わせがあります。</span><span class="sxs-lookup"><span data-stu-id="06fad-105">The settings for the negotiation types in the configuration of an XMPP Partner have a wide variety of possible combinations.</span></span> <span data-ttu-id="06fad-106">これらの組み合わせのすべてが有効なわけではありません。</span><span class="sxs-lookup"><span data-stu-id="06fad-106">Not all of these combinations are valid.</span></span> <span data-ttu-id="06fad-107">このトピックで詳細に記載されている表では、有効で有効な設定を定義しています。</span><span class="sxs-lookup"><span data-stu-id="06fad-107">The table detailed in this topic will define the valid and not valid settings.</span></span> <span data-ttu-id="06fad-108">一般的な構成については、第1の表で、考えられるすべての組み合わせの詳細な2番目の表で説明します。</span><span class="sxs-lookup"><span data-stu-id="06fad-108">Common configurations are presented in the first table, the second table detailing all possible combinations.</span></span> <span data-ttu-id="06fad-109">*トランスポート層セキュリティ*(TLS) も使用できる**場合を除き**、*単純な認証およびセキュリティ層*(SASL) を使用することはできないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="06fad-109">Note that you cannot have *Simple Authentication and Security Layer* (SASL) **unless** *Transport Layer Security* (TLS) is also available.</span></span> <span data-ttu-id="06fad-110">SASL は暗号化されていない (読み取り可能な) 形式で送信されるため、TLS などの別の手段で保護されていない限り、送信しないでください。</span><span class="sxs-lookup"><span data-stu-id="06fad-110">SASL is sent in an unencrypted (readable) format and should never be transmitted unless protected by another means, such as TLS.</span></span>

### <a name="common-xmpp-federation-negotiation-methods"></a><span data-ttu-id="06fad-111">よく使用される XMPP フェデレーションのネゴシエーション方式</span><span class="sxs-lookup"><span data-stu-id="06fad-111">Common XMPP Federation Negotiation Methods</span></span>

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
<th><span data-ttu-id="06fad-112">トランスポート層セキュリティ (TLS)</span><span class="sxs-lookup"><span data-stu-id="06fad-112">Transport Layer Security (TLS)</span></span></th>
<th><span data-ttu-id="06fad-113">簡易認証およびセキュリティ層 (SASL)</span><span class="sxs-lookup"><span data-stu-id="06fad-113">Simple Authentication and Security Layer (SASL)</span></span></th>
<th><span data-ttu-id="06fad-114">ダイヤルバック認証</span><span class="sxs-lookup"><span data-stu-id="06fad-114">Dialback Authentication</span></span></th>
<th><span data-ttu-id="06fad-115">期待される認証方式</span><span class="sxs-lookup"><span data-stu-id="06fad-115">Expected Authentication Method(s)</span></span></th>
<th><span data-ttu-id="06fad-116">Notes</span><span class="sxs-lookup"><span data-stu-id="06fad-116">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="06fad-117">必須</span><span class="sxs-lookup"><span data-stu-id="06fad-117">Required</span></span></p></td>
<td><p><span data-ttu-id="06fad-118">必須</span><span class="sxs-lookup"><span data-stu-id="06fad-118">Required</span></span></p></td>
<td><p><span data-ttu-id="06fad-119">False</span><span class="sxs-lookup"><span data-stu-id="06fad-119">False</span></span></p></td>
<td><p><span data-ttu-id="06fad-120">SASL over TLS</span><span class="sxs-lookup"><span data-stu-id="06fad-120">SASL over TLS</span></span></p></td>
<td><p><span data-ttu-id="06fad-p102">SASL メッセージ ストリームをセキュアにするために TLS と SASL が必要です。ダイヤルバックは利用できません。XMPP フェデレーション パートナーが TLS を必須またはオプションに設定していない場合の代替手段には使用できません。</span><span class="sxs-lookup"><span data-stu-id="06fad-p102">TLS and SASL required helps to ensure that the SASL message stream is secure. Dialback is not available and cannot be used for a fallback method if the XMPP federated partner has not set TLS to required or optional.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06fad-123">必須</span><span class="sxs-lookup"><span data-stu-id="06fad-123">Required</span></span></p></td>
<td><p><span data-ttu-id="06fad-124">省略可能</span><span class="sxs-lookup"><span data-stu-id="06fad-124">Optional</span></span></p></td>
<td><p><span data-ttu-id="06fad-125">正</span><span class="sxs-lookup"><span data-stu-id="06fad-125">True</span></span></p></td>
<td><p><span data-ttu-id="06fad-126">SASL over TLS、TLS ダイヤルバック、TCP ダイヤルバック</span><span class="sxs-lookup"><span data-stu-id="06fad-126">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="06fad-p103">TLS を必須にすると、XMPP フェデレーション パートナーが SASL をオプションまたは必須に設定していた場合は SASL が使用されます。SASL が利用できない場合は、ダイヤルバック over TLS が使用されます。</span><span class="sxs-lookup"><span data-stu-id="06fad-p103">By requiring TLS, if the XMPP federated partner has set SASL to optional or required SASL is used. If SASL is not available, Dialback over TLS will be used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06fad-129">省略可能</span><span class="sxs-lookup"><span data-stu-id="06fad-129">Optional</span></span></p></td>
<td><p><span data-ttu-id="06fad-130">オプション</span><span class="sxs-lookup"><span data-stu-id="06fad-130">Optional</span></span></p></td>
<td><p><span data-ttu-id="06fad-131">正</span><span class="sxs-lookup"><span data-stu-id="06fad-131">True</span></span></p></td>
<td><p><span data-ttu-id="06fad-132">SASL over TLS、TLS ダイヤルバック、TCP ダイヤルバック</span><span class="sxs-lookup"><span data-stu-id="06fad-132">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="06fad-p104">きわめて柔軟なネゴシエーション方式が用意されているものの、これらの設定は XMPP フェデレーション パートナーの設定に依存します。パートナーが TLS をオプションまたは必須にしているのに SASL がサポートされていない場合は、TLS ダイヤルバックが利用できます。パートナーが TLS と SASL をオプションまたは必須に設定している場合は、最適な選択肢である TLS over SASL が使用されます。</span><span class="sxs-lookup"><span data-stu-id="06fad-p104">While very flexible in the negotiation methods offered, these settings rely on the XMPP federation partner’s settings. If the partner has TLS optional or required but SASL is not supported, TLS Dialback will be available. If the partner has TLS and SASL set to optional or required, the optimal selection of TLS over SASL is used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06fad-136">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="06fad-136">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="06fad-137">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="06fad-137">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="06fad-138">正</span><span class="sxs-lookup"><span data-stu-id="06fad-138">True</span></span></p></td>
<td><p><span data-ttu-id="06fad-139">TCP ダイヤルバック</span><span class="sxs-lookup"><span data-stu-id="06fad-139">TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="06fad-p105">多くの場合、使用できるソリューションは TCP ダイヤルバックのみです。ほかのオプションに比べると好ましくありませんが、ある程度の信頼は提供されます。</span><span class="sxs-lookup"><span data-stu-id="06fad-p105">In many cases, TCP Dialback is the only possible solution. Less desirable than other options, it does provide some level of trust.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="xmpp-federation-negotiation-methods-matrix---complete"></a><span data-ttu-id="06fad-142">XMPP フェデレーション ネゴシエーション方式のマトリックス - すべて</span><span class="sxs-lookup"><span data-stu-id="06fad-142">XMPP Federation Negotiation Methods Matrix - Complete</span></span>

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
<th><span data-ttu-id="06fad-143">トランスポート層セキュリティ (TLS)</span><span class="sxs-lookup"><span data-stu-id="06fad-143">Transport Layer Security (TLS)</span></span></th>
<th><span data-ttu-id="06fad-144">簡易認証およびセキュリティ層 (SASL)</span><span class="sxs-lookup"><span data-stu-id="06fad-144">Simple Authentication and Security Layer (SASL)</span></span></th>
<th><span data-ttu-id="06fad-145">ダイヤルバック認証</span><span class="sxs-lookup"><span data-stu-id="06fad-145">Dialback Authentication</span></span></th>
<th><span data-ttu-id="06fad-146">期待される認証方式</span><span class="sxs-lookup"><span data-stu-id="06fad-146">Expected Authentication Method</span></span></th>
<th><span data-ttu-id="06fad-147">無効な構成に関するメモ、警告、またはエラー</span><span class="sxs-lookup"><span data-stu-id="06fad-147">Notes, Warning or Error for Not Valid Configuration</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="06fad-148">必須</span><span class="sxs-lookup"><span data-stu-id="06fad-148">Required</span></span></p></td>
<td><p><span data-ttu-id="06fad-149">必須</span><span class="sxs-lookup"><span data-stu-id="06fad-149">Required</span></span></p></td>
<td><p><span data-ttu-id="06fad-150">正</span><span class="sxs-lookup"><span data-stu-id="06fad-150">True</span></span></p></td>
<td><p><span data-ttu-id="06fad-151">SASL over TLS</span><span class="sxs-lookup"><span data-stu-id="06fad-151">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="06fad-152">SASL と TLS の両方が必須の場合、ダイヤルバックは機能しません。</span><span class="sxs-lookup"><span data-stu-id="06fad-152">Dialback will not operate if both SASL and TLS are required.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06fad-153">必須</span><span class="sxs-lookup"><span data-stu-id="06fad-153">Required</span></span></p></td>
<td><p><span data-ttu-id="06fad-154">必須</span><span class="sxs-lookup"><span data-stu-id="06fad-154">Required</span></span></p></td>
<td><p><span data-ttu-id="06fad-155">False</span><span class="sxs-lookup"><span data-stu-id="06fad-155">False</span></span></p></td>
<td><p><span data-ttu-id="06fad-156">SASL over TLS</span><span class="sxs-lookup"><span data-stu-id="06fad-156">SASL over TLS</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06fad-157">省略可能</span><span class="sxs-lookup"><span data-stu-id="06fad-157">Optional</span></span></p></td>
<td><p><span data-ttu-id="06fad-158">必須</span><span class="sxs-lookup"><span data-stu-id="06fad-158">Required</span></span></p></td>
<td><p><span data-ttu-id="06fad-159">正</span><span class="sxs-lookup"><span data-stu-id="06fad-159">True</span></span></p></td>
<td><p><span data-ttu-id="06fad-160">SASL over TLS、TLS ダイヤルバック、TCP ダイヤルバック</span><span class="sxs-lookup"><span data-stu-id="06fad-160">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="06fad-p106">SASL には TLS が必須です。TLS をオプションとして許可すると、セッションのネゴシエーションが失敗する場合があります。</span><span class="sxs-lookup"><span data-stu-id="06fad-p106">SASL requires TLS. Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06fad-163">省略可能</span><span class="sxs-lookup"><span data-stu-id="06fad-163">Optional</span></span></p></td>
<td><p><span data-ttu-id="06fad-164">必須</span><span class="sxs-lookup"><span data-stu-id="06fad-164">Required</span></span></p></td>
<td><p><span data-ttu-id="06fad-165">False</span><span class="sxs-lookup"><span data-stu-id="06fad-165">False</span></span></p></td>
<td><p><span data-ttu-id="06fad-166">SASL over TLS</span><span class="sxs-lookup"><span data-stu-id="06fad-166">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="06fad-p107">SASL には TLS が必須です。TLS をオプションとして許可すると、セッションのネゴシエーションが失敗する場合があります。</span><span class="sxs-lookup"><span data-stu-id="06fad-p107">SASL requires TLS. Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06fad-169">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="06fad-169">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="06fad-170">必須</span><span class="sxs-lookup"><span data-stu-id="06fad-170">Required</span></span></p></td>
<td><p><span data-ttu-id="06fad-171">正</span><span class="sxs-lookup"><span data-stu-id="06fad-171">True</span></span></p></td>
<td><p><span data-ttu-id="06fad-172">TCP ダイヤルバック</span><span class="sxs-lookup"><span data-stu-id="06fad-172">TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="06fad-p108">SASL には TLS が必須です。TLS をオプションとして許可すると、セッションのネゴシエーションが失敗する場合があります。</span><span class="sxs-lookup"><span data-stu-id="06fad-p108">SASL requires TLS. Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06fad-175">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="06fad-175">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="06fad-176">必須</span><span class="sxs-lookup"><span data-stu-id="06fad-176">Required</span></span></p></td>
<td><p><span data-ttu-id="06fad-177">False</span><span class="sxs-lookup"><span data-stu-id="06fad-177">False</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="06fad-178">無効な構成</span><span class="sxs-lookup"><span data-stu-id="06fad-178">Not Valid Configuration</span></span>


</div></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="06fad-p109">SASL には TLS が必須ですが　TLS は利用できないため、SASL/TLS は成功しません。TCP ダイヤルバックは False に設定され、使用されません。</span><span class="sxs-lookup"><span data-stu-id="06fad-p109">Because SASL requires TLS, and TLS is not available, SASL/TLS cannot succeed. TCP Dialback is set to false, and cannot be used.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06fad-181">必須</span><span class="sxs-lookup"><span data-stu-id="06fad-181">Required</span></span></p></td>
<td><p><span data-ttu-id="06fad-182">省略可能</span><span class="sxs-lookup"><span data-stu-id="06fad-182">Optional</span></span></p></td>
<td><p><span data-ttu-id="06fad-183">正</span><span class="sxs-lookup"><span data-stu-id="06fad-183">True</span></span></p></td>
<td><p><span data-ttu-id="06fad-184">SASL over TLS、TLS ダイヤルバック</span><span class="sxs-lookup"><span data-stu-id="06fad-184">SASL over TLS, TLS Dialback</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06fad-185">必須</span><span class="sxs-lookup"><span data-stu-id="06fad-185">Required</span></span></p></td>
<td><p><span data-ttu-id="06fad-186">省略可能</span><span class="sxs-lookup"><span data-stu-id="06fad-186">Optional</span></span></p></td>
<td><p><span data-ttu-id="06fad-187">False</span><span class="sxs-lookup"><span data-stu-id="06fad-187">False</span></span></p></td>
<td><p><span data-ttu-id="06fad-188">SASL over TLS</span><span class="sxs-lookup"><span data-stu-id="06fad-188">SASL over TLS</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06fad-189">省略可能</span><span class="sxs-lookup"><span data-stu-id="06fad-189">Optional</span></span></p></td>
<td><p><span data-ttu-id="06fad-190">オプション</span><span class="sxs-lookup"><span data-stu-id="06fad-190">Optional</span></span></p></td>
<td><p><span data-ttu-id="06fad-191">正</span><span class="sxs-lookup"><span data-stu-id="06fad-191">True</span></span></p></td>
<td><p><span data-ttu-id="06fad-192">SASL over TLS、TLS ダイヤルバック、TCP ダイヤルバック</span><span class="sxs-lookup"><span data-stu-id="06fad-192">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="06fad-p110">SASL には TLS が必須です。TLS をオプションとして許可すると、セッションのネゴシエーションが失敗する場合があります。</span><span class="sxs-lookup"><span data-stu-id="06fad-p110">SASL requires TLS. Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06fad-195">省略可能</span><span class="sxs-lookup"><span data-stu-id="06fad-195">Optional</span></span></p></td>
<td><p><span data-ttu-id="06fad-196">オプション</span><span class="sxs-lookup"><span data-stu-id="06fad-196">Optional</span></span></p></td>
<td><p><span data-ttu-id="06fad-197">False</span><span class="sxs-lookup"><span data-stu-id="06fad-197">False</span></span></p></td>
<td><p><span data-ttu-id="06fad-198">SASL over TLS</span><span class="sxs-lookup"><span data-stu-id="06fad-198">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="06fad-p111">SASL には TLS が必須です。TLS をオプションとして許可すると、セッションのネゴシエーションが失敗する場合があります。</span><span class="sxs-lookup"><span data-stu-id="06fad-p111">SASL requires TLS. Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06fad-201">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="06fad-201">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="06fad-202">省略可能</span><span class="sxs-lookup"><span data-stu-id="06fad-202">Optional</span></span></p></td>
<td><p><span data-ttu-id="06fad-203">正</span><span class="sxs-lookup"><span data-stu-id="06fad-203">True</span></span></p></td>
<td><p><span data-ttu-id="06fad-204">TCP ダイヤルバック</span><span class="sxs-lookup"><span data-stu-id="06fad-204">TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="06fad-p112">SASL には TLS が必須です。TLS をオプションとして許可すると、セッションのネゴシエーションが失敗する場合があります。</span><span class="sxs-lookup"><span data-stu-id="06fad-p112">SASL requires TLS. Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06fad-207">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="06fad-207">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="06fad-208">省略可能</span><span class="sxs-lookup"><span data-stu-id="06fad-208">Optional</span></span></p></td>
<td><p><span data-ttu-id="06fad-209">False</span><span class="sxs-lookup"><span data-stu-id="06fad-209">False</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="06fad-210">無効な構成</span><span class="sxs-lookup"><span data-stu-id="06fad-210">Not Valid Configuration</span></span>


</div></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="06fad-p113">SASL には TLS が必須です。TLS をオプションとして許可すると、セッションのネゴシエーションが失敗する場合があります。</span><span class="sxs-lookup"><span data-stu-id="06fad-p113">SASL requires TLS. Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06fad-213">必須</span><span class="sxs-lookup"><span data-stu-id="06fad-213">Required</span></span></p></td>
<td><p><span data-ttu-id="06fad-214">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="06fad-214">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="06fad-215">正</span><span class="sxs-lookup"><span data-stu-id="06fad-215">True</span></span></p></td>
<td><p><span data-ttu-id="06fad-216">TLS ダイヤルバック</span><span class="sxs-lookup"><span data-stu-id="06fad-216">TLS Dialback</span></span></p></td>
<td><p><span data-ttu-id="06fad-217">TLS ダイヤルバックを許可する構成です。</span><span class="sxs-lookup"><span data-stu-id="06fad-217">Configuration allows for TLS Dialback.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06fad-218">必須</span><span class="sxs-lookup"><span data-stu-id="06fad-218">Required</span></span></p></td>
<td><p><span data-ttu-id="06fad-219">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="06fad-219">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="06fad-220">False</span><span class="sxs-lookup"><span data-stu-id="06fad-220">False</span></span></p></td>
<td><p><span data-ttu-id="06fad-221">無効な構成</span><span class="sxs-lookup"><span data-stu-id="06fad-221">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="06fad-222">SASL またはダイヤルバックを有効化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="06fad-222">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06fad-223">省略可能</span><span class="sxs-lookup"><span data-stu-id="06fad-223">Optional</span></span></p></td>
<td><p><span data-ttu-id="06fad-224">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="06fad-224">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="06fad-225">正</span><span class="sxs-lookup"><span data-stu-id="06fad-225">True</span></span></p></td>
<td><p><span data-ttu-id="06fad-226">TLS ダイヤルバック、TCP ダイヤルバック</span><span class="sxs-lookup"><span data-stu-id="06fad-226">TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="06fad-227">もう一方のエンドポイントが選択したネゴシエーションに基づいて、TCP または TLS ダイヤルバックを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="06fad-227">Based on negotiation choices of the other end point, TCP or TLS Dialback will be accepted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06fad-228">省略可能</span><span class="sxs-lookup"><span data-stu-id="06fad-228">Optional</span></span></p></td>
<td><p><span data-ttu-id="06fad-229">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="06fad-229">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="06fad-230">False</span><span class="sxs-lookup"><span data-stu-id="06fad-230">False</span></span></p></td>
<td><p><span data-ttu-id="06fad-231">無効な構成</span><span class="sxs-lookup"><span data-stu-id="06fad-231">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="06fad-232">SASL またはダイヤルバックを有効化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="06fad-232">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06fad-233">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="06fad-233">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="06fad-234">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="06fad-234">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="06fad-235">正</span><span class="sxs-lookup"><span data-stu-id="06fad-235">True</span></span></p></td>
<td><p><span data-ttu-id="06fad-236">TCP ダイヤルバック</span><span class="sxs-lookup"><span data-stu-id="06fad-236">TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="06fad-237">利用できるネゴシエーション方式は TCP ダイヤルバック のみです。</span><span class="sxs-lookup"><span data-stu-id="06fad-237">TCP Dialback is the only negotiation method available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06fad-238">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="06fad-238">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="06fad-239">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="06fad-239">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="06fad-240">False</span><span class="sxs-lookup"><span data-stu-id="06fad-240">False</span></span></p></td>
<td><p><span data-ttu-id="06fad-241">無効な構成</span><span class="sxs-lookup"><span data-stu-id="06fad-241">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="06fad-242">SASL またはダイヤルバックを有効化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="06fad-242">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

