---
title: 'Lync Server 2013: XMPP フェデレーションパートナーのネゴシエーション設定'
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
ms.openlocfilehash: bdb09d52970b5fd97395acda6a2e4fbc824a378d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48505594"
---
# <a name="negotiation-settings-for-xmpp-federated-partners-in-lync-server-2013"></a><span data-ttu-id="2043e-102">Lync Server 2013 での XMPP フェデレーションパートナーのネゴシエーション設定</span><span class="sxs-lookup"><span data-stu-id="2043e-102">Negotiation settings for XMPP federated partners in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2043e-103">_**トピックの最終更新日:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="2043e-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="2043e-104">XMPP パートナーの構成におけるネゴシエーションの種類の設定には、さまざまな組み合わせがあります。</span><span class="sxs-lookup"><span data-stu-id="2043e-104">The settings for the negotiation types in the configuration of an XMPP Partner have a wide variety of possible combinations.</span></span> <span data-ttu-id="2043e-105">これらの組み合わせのすべてが有効なわけではありません。</span><span class="sxs-lookup"><span data-stu-id="2043e-105">Not all of these combinations are valid.</span></span> <span data-ttu-id="2043e-106">このトピックで詳細に記載されている表では、有効で有効な設定を定義しています。</span><span class="sxs-lookup"><span data-stu-id="2043e-106">The table detailed in this topic will define the valid and not valid settings.</span></span> <span data-ttu-id="2043e-107">一般的な構成については、第1の表で、考えられるすべての組み合わせの詳細な2番目の表で説明します。</span><span class="sxs-lookup"><span data-stu-id="2043e-107">Common configurations are presented in the first table, the second table detailing all possible combinations.</span></span> <span data-ttu-id="2043e-108">*トランスポート層セキュリティ*(TLS) も使用できる**場合を除き**、*単純な認証およびセキュリティ層*(SASL) を使用することはできないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="2043e-108">Note that you cannot have *Simple Authentication and Security Layer* (SASL) **unless** *Transport Layer Security* (TLS) is also available.</span></span> <span data-ttu-id="2043e-109">SASL は暗号化されていない (読み取り可能な) 形式で送信されるため、TLS などの別の手段で保護されていない限り、送信しないでください。</span><span class="sxs-lookup"><span data-stu-id="2043e-109">SASL is sent in an unencrypted (readable) format and should never be transmitted unless protected by another means, such as TLS.</span></span>

### <a name="common-xmpp-federation-negotiation-methods"></a><span data-ttu-id="2043e-110">よく使用される XMPP フェデレーションのネゴシエーション方式</span><span class="sxs-lookup"><span data-stu-id="2043e-110">Common XMPP Federation Negotiation Methods</span></span>

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
<th><span data-ttu-id="2043e-111">トランスポート層セキュリティ (TLS)</span><span class="sxs-lookup"><span data-stu-id="2043e-111">Transport Layer Security (TLS)</span></span></th>
<th><span data-ttu-id="2043e-112">簡易認証およびセキュリティ層 (SASL)</span><span class="sxs-lookup"><span data-stu-id="2043e-112">Simple Authentication and Security Layer (SASL)</span></span></th>
<th><span data-ttu-id="2043e-113">ダイヤルバック認証</span><span class="sxs-lookup"><span data-stu-id="2043e-113">Dialback Authentication</span></span></th>
<th><span data-ttu-id="2043e-114">期待される認証方式</span><span class="sxs-lookup"><span data-stu-id="2043e-114">Expected Authentication Method(s)</span></span></th>
<th><span data-ttu-id="2043e-115">Notes</span><span class="sxs-lookup"><span data-stu-id="2043e-115">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2043e-116">必須</span><span class="sxs-lookup"><span data-stu-id="2043e-116">Required</span></span></p></td>
<td><p><span data-ttu-id="2043e-117">必須</span><span class="sxs-lookup"><span data-stu-id="2043e-117">Required</span></span></p></td>
<td><p><span data-ttu-id="2043e-118">False</span><span class="sxs-lookup"><span data-stu-id="2043e-118">False</span></span></p></td>
<td><p><span data-ttu-id="2043e-119">SASL over TLS</span><span class="sxs-lookup"><span data-stu-id="2043e-119">SASL over TLS</span></span></p></td>
<td><p><span data-ttu-id="2043e-p102">SASL メッセージ ストリームをセキュアにするために TLS と SASL が必要です。ダイヤルバックは利用できません。XMPP フェデレーション パートナーが TLS を必須またはオプションに設定していない場合の代替手段には使用できません。</span><span class="sxs-lookup"><span data-stu-id="2043e-p102">TLS and SASL required helps to ensure that the SASL message stream is secure. Dialback is not available and cannot be used for a fallback method if the XMPP federated partner has not set TLS to required or optional.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2043e-122">必須</span><span class="sxs-lookup"><span data-stu-id="2043e-122">Required</span></span></p></td>
<td><p><span data-ttu-id="2043e-123">省略可能</span><span class="sxs-lookup"><span data-stu-id="2043e-123">Optional</span></span></p></td>
<td><p><span data-ttu-id="2043e-124">正</span><span class="sxs-lookup"><span data-stu-id="2043e-124">True</span></span></p></td>
<td><p><span data-ttu-id="2043e-125">SASL over TLS、TLS ダイヤルバック、TCP ダイヤルバック</span><span class="sxs-lookup"><span data-stu-id="2043e-125">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="2043e-p103">TLS を必須にすると、XMPP フェデレーション パートナーが SASL をオプションまたは必須に設定していた場合は SASL が使用されます。SASL が利用できない場合は、ダイヤルバック over TLS が使用されます。</span><span class="sxs-lookup"><span data-stu-id="2043e-p103">By requiring TLS, if the XMPP federated partner has set SASL to optional or required SASL is used. If SASL is not available, Dialback over TLS will be used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2043e-128">省略可能</span><span class="sxs-lookup"><span data-stu-id="2043e-128">Optional</span></span></p></td>
<td><p><span data-ttu-id="2043e-129">オプション</span><span class="sxs-lookup"><span data-stu-id="2043e-129">Optional</span></span></p></td>
<td><p><span data-ttu-id="2043e-130">正</span><span class="sxs-lookup"><span data-stu-id="2043e-130">True</span></span></p></td>
<td><p><span data-ttu-id="2043e-131">SASL over TLS、TLS ダイヤルバック、TCP ダイヤルバック</span><span class="sxs-lookup"><span data-stu-id="2043e-131">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="2043e-p104">きわめて柔軟なネゴシエーション方式が用意されているものの、これらの設定は XMPP フェデレーション パートナーの設定に依存します。パートナーが TLS をオプションまたは必須にしているのに SASL がサポートされていない場合は、TLS ダイヤルバックが利用できます。パートナーが TLS と SASL をオプションまたは必須に設定している場合は、最適な選択肢である TLS over SASL が使用されます。</span><span class="sxs-lookup"><span data-stu-id="2043e-p104">While very flexible in the negotiation methods offered, these settings rely on the XMPP federation partner’s settings. If the partner has TLS optional or required but SASL is not supported, TLS Dialback will be available. If the partner has TLS and SASL set to optional or required, the optimal selection of TLS over SASL is used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2043e-135">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="2043e-135">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="2043e-136">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="2043e-136">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="2043e-137">正</span><span class="sxs-lookup"><span data-stu-id="2043e-137">True</span></span></p></td>
<td><p><span data-ttu-id="2043e-138">TCP ダイヤルバック</span><span class="sxs-lookup"><span data-stu-id="2043e-138">TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="2043e-p105">多くの場合、使用できるソリューションは TCP ダイヤルバックのみです。ほかのオプションに比べると好ましくありませんが、ある程度の信頼は提供されます。</span><span class="sxs-lookup"><span data-stu-id="2043e-p105">In many cases, TCP Dialback is the only possible solution. Less desirable than other options, it does provide some level of trust.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="xmpp-federation-negotiation-methods-matrix---complete"></a><span data-ttu-id="2043e-141">XMPP フェデレーション ネゴシエーション方式のマトリックス - すべて</span><span class="sxs-lookup"><span data-stu-id="2043e-141">XMPP Federation Negotiation Methods Matrix - Complete</span></span>

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
<th><span data-ttu-id="2043e-142">トランスポート層セキュリティ (TLS)</span><span class="sxs-lookup"><span data-stu-id="2043e-142">Transport Layer Security (TLS)</span></span></th>
<th><span data-ttu-id="2043e-143">簡易認証およびセキュリティ層 (SASL)</span><span class="sxs-lookup"><span data-stu-id="2043e-143">Simple Authentication and Security Layer (SASL)</span></span></th>
<th><span data-ttu-id="2043e-144">ダイヤルバック認証</span><span class="sxs-lookup"><span data-stu-id="2043e-144">Dialback Authentication</span></span></th>
<th><span data-ttu-id="2043e-145">期待される認証方式</span><span class="sxs-lookup"><span data-stu-id="2043e-145">Expected Authentication Method</span></span></th>
<th><span data-ttu-id="2043e-146">無効な構成に関するメモ、警告、またはエラー</span><span class="sxs-lookup"><span data-stu-id="2043e-146">Notes, Warning or Error for Not Valid Configuration</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2043e-147">必須</span><span class="sxs-lookup"><span data-stu-id="2043e-147">Required</span></span></p></td>
<td><p><span data-ttu-id="2043e-148">必須</span><span class="sxs-lookup"><span data-stu-id="2043e-148">Required</span></span></p></td>
<td><p><span data-ttu-id="2043e-149">正</span><span class="sxs-lookup"><span data-stu-id="2043e-149">True</span></span></p></td>
<td><p><span data-ttu-id="2043e-150">SASL over TLS</span><span class="sxs-lookup"><span data-stu-id="2043e-150">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="2043e-151">SASL と TLS の両方が必須の場合、ダイヤルバックは機能しません。</span><span class="sxs-lookup"><span data-stu-id="2043e-151">Dialback will not operate if both SASL and TLS are required.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2043e-152">必須</span><span class="sxs-lookup"><span data-stu-id="2043e-152">Required</span></span></p></td>
<td><p><span data-ttu-id="2043e-153">必須</span><span class="sxs-lookup"><span data-stu-id="2043e-153">Required</span></span></p></td>
<td><p><span data-ttu-id="2043e-154">False</span><span class="sxs-lookup"><span data-stu-id="2043e-154">False</span></span></p></td>
<td><p><span data-ttu-id="2043e-155">SASL over TLS</span><span class="sxs-lookup"><span data-stu-id="2043e-155">SASL over TLS</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2043e-156">省略可能</span><span class="sxs-lookup"><span data-stu-id="2043e-156">Optional</span></span></p></td>
<td><p><span data-ttu-id="2043e-157">必須</span><span class="sxs-lookup"><span data-stu-id="2043e-157">Required</span></span></p></td>
<td><p><span data-ttu-id="2043e-158">正</span><span class="sxs-lookup"><span data-stu-id="2043e-158">True</span></span></p></td>
<td><p><span data-ttu-id="2043e-159">SASL over TLS、TLS ダイヤルバック、TCP ダイヤルバック</span><span class="sxs-lookup"><span data-stu-id="2043e-159">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="2043e-p106">SASL には TLS が必須です。TLS をオプションとして許可すると、セッションのネゴシエーションが失敗する場合があります。</span><span class="sxs-lookup"><span data-stu-id="2043e-p106">SASL requires TLS. Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2043e-162">省略可能</span><span class="sxs-lookup"><span data-stu-id="2043e-162">Optional</span></span></p></td>
<td><p><span data-ttu-id="2043e-163">必須</span><span class="sxs-lookup"><span data-stu-id="2043e-163">Required</span></span></p></td>
<td><p><span data-ttu-id="2043e-164">False</span><span class="sxs-lookup"><span data-stu-id="2043e-164">False</span></span></p></td>
<td><p><span data-ttu-id="2043e-165">SASL over TLS</span><span class="sxs-lookup"><span data-stu-id="2043e-165">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="2043e-p107">SASL には TLS が必須です。TLS をオプションとして許可すると、セッションのネゴシエーションが失敗する場合があります。</span><span class="sxs-lookup"><span data-stu-id="2043e-p107">SASL requires TLS. Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2043e-168">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="2043e-168">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="2043e-169">必須</span><span class="sxs-lookup"><span data-stu-id="2043e-169">Required</span></span></p></td>
<td><p><span data-ttu-id="2043e-170">正</span><span class="sxs-lookup"><span data-stu-id="2043e-170">True</span></span></p></td>
<td><p><span data-ttu-id="2043e-171">TCP ダイヤルバック</span><span class="sxs-lookup"><span data-stu-id="2043e-171">TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="2043e-p108">SASL には TLS が必須です。TLS をオプションとして許可すると、セッションのネゴシエーションが失敗する場合があります。</span><span class="sxs-lookup"><span data-stu-id="2043e-p108">SASL requires TLS. Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2043e-174">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="2043e-174">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="2043e-175">必須</span><span class="sxs-lookup"><span data-stu-id="2043e-175">Required</span></span></p></td>
<td><p><span data-ttu-id="2043e-176">False</span><span class="sxs-lookup"><span data-stu-id="2043e-176">False</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="2043e-177">無効な構成</span><span class="sxs-lookup"><span data-stu-id="2043e-177">Not Valid Configuration</span></span>


</div></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="2043e-p109">SASL には TLS が必須ですが　TLS は利用できないため、SASL/TLS は成功しません。TCP ダイヤルバックは False に設定され、使用されません。</span><span class="sxs-lookup"><span data-stu-id="2043e-p109">Because SASL requires TLS, and TLS is not available, SASL/TLS cannot succeed. TCP Dialback is set to false, and cannot be used.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2043e-180">必須</span><span class="sxs-lookup"><span data-stu-id="2043e-180">Required</span></span></p></td>
<td><p><span data-ttu-id="2043e-181">省略可能</span><span class="sxs-lookup"><span data-stu-id="2043e-181">Optional</span></span></p></td>
<td><p><span data-ttu-id="2043e-182">正</span><span class="sxs-lookup"><span data-stu-id="2043e-182">True</span></span></p></td>
<td><p><span data-ttu-id="2043e-183">SASL over TLS、TLS ダイヤルバック</span><span class="sxs-lookup"><span data-stu-id="2043e-183">SASL over TLS, TLS Dialback</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2043e-184">必須</span><span class="sxs-lookup"><span data-stu-id="2043e-184">Required</span></span></p></td>
<td><p><span data-ttu-id="2043e-185">省略可能</span><span class="sxs-lookup"><span data-stu-id="2043e-185">Optional</span></span></p></td>
<td><p><span data-ttu-id="2043e-186">False</span><span class="sxs-lookup"><span data-stu-id="2043e-186">False</span></span></p></td>
<td><p><span data-ttu-id="2043e-187">SASL over TLS</span><span class="sxs-lookup"><span data-stu-id="2043e-187">SASL over TLS</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2043e-188">省略可能</span><span class="sxs-lookup"><span data-stu-id="2043e-188">Optional</span></span></p></td>
<td><p><span data-ttu-id="2043e-189">オプション</span><span class="sxs-lookup"><span data-stu-id="2043e-189">Optional</span></span></p></td>
<td><p><span data-ttu-id="2043e-190">正</span><span class="sxs-lookup"><span data-stu-id="2043e-190">True</span></span></p></td>
<td><p><span data-ttu-id="2043e-191">SASL over TLS、TLS ダイヤルバック、TCP ダイヤルバック</span><span class="sxs-lookup"><span data-stu-id="2043e-191">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="2043e-p110">SASL には TLS が必須です。TLS をオプションとして許可すると、セッションのネゴシエーションが失敗する場合があります。</span><span class="sxs-lookup"><span data-stu-id="2043e-p110">SASL requires TLS. Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2043e-194">省略可能</span><span class="sxs-lookup"><span data-stu-id="2043e-194">Optional</span></span></p></td>
<td><p><span data-ttu-id="2043e-195">オプション</span><span class="sxs-lookup"><span data-stu-id="2043e-195">Optional</span></span></p></td>
<td><p><span data-ttu-id="2043e-196">False</span><span class="sxs-lookup"><span data-stu-id="2043e-196">False</span></span></p></td>
<td><p><span data-ttu-id="2043e-197">SASL over TLS</span><span class="sxs-lookup"><span data-stu-id="2043e-197">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="2043e-p111">SASL には TLS が必須です。TLS をオプションとして許可すると、セッションのネゴシエーションが失敗する場合があります。</span><span class="sxs-lookup"><span data-stu-id="2043e-p111">SASL requires TLS. Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2043e-200">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="2043e-200">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="2043e-201">省略可能</span><span class="sxs-lookup"><span data-stu-id="2043e-201">Optional</span></span></p></td>
<td><p><span data-ttu-id="2043e-202">正</span><span class="sxs-lookup"><span data-stu-id="2043e-202">True</span></span></p></td>
<td><p><span data-ttu-id="2043e-203">TCP ダイヤルバック</span><span class="sxs-lookup"><span data-stu-id="2043e-203">TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="2043e-p112">SASL には TLS が必須です。TLS をオプションとして許可すると、セッションのネゴシエーションが失敗する場合があります。</span><span class="sxs-lookup"><span data-stu-id="2043e-p112">SASL requires TLS. Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2043e-206">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="2043e-206">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="2043e-207">省略可能</span><span class="sxs-lookup"><span data-stu-id="2043e-207">Optional</span></span></p></td>
<td><p><span data-ttu-id="2043e-208">False</span><span class="sxs-lookup"><span data-stu-id="2043e-208">False</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="2043e-209">無効な構成</span><span class="sxs-lookup"><span data-stu-id="2043e-209">Not Valid Configuration</span></span>


</div></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="2043e-p113">SASL には TLS が必須です。TLS をオプションとして許可すると、セッションのネゴシエーションが失敗する場合があります。</span><span class="sxs-lookup"><span data-stu-id="2043e-p113">SASL requires TLS. Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2043e-212">必須</span><span class="sxs-lookup"><span data-stu-id="2043e-212">Required</span></span></p></td>
<td><p><span data-ttu-id="2043e-213">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="2043e-213">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="2043e-214">正</span><span class="sxs-lookup"><span data-stu-id="2043e-214">True</span></span></p></td>
<td><p><span data-ttu-id="2043e-215">TLS ダイヤルバック</span><span class="sxs-lookup"><span data-stu-id="2043e-215">TLS Dialback</span></span></p></td>
<td><p><span data-ttu-id="2043e-216">TLS ダイヤルバックを許可する構成です。</span><span class="sxs-lookup"><span data-stu-id="2043e-216">Configuration allows for TLS Dialback.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2043e-217">必須</span><span class="sxs-lookup"><span data-stu-id="2043e-217">Required</span></span></p></td>
<td><p><span data-ttu-id="2043e-218">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="2043e-218">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="2043e-219">False</span><span class="sxs-lookup"><span data-stu-id="2043e-219">False</span></span></p></td>
<td><p><span data-ttu-id="2043e-220">無効な構成</span><span class="sxs-lookup"><span data-stu-id="2043e-220">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="2043e-221">SASL またはダイヤルバックを有効化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2043e-221">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2043e-222">省略可能</span><span class="sxs-lookup"><span data-stu-id="2043e-222">Optional</span></span></p></td>
<td><p><span data-ttu-id="2043e-223">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="2043e-223">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="2043e-224">正</span><span class="sxs-lookup"><span data-stu-id="2043e-224">True</span></span></p></td>
<td><p><span data-ttu-id="2043e-225">TLS ダイヤルバック、TCP ダイヤルバック</span><span class="sxs-lookup"><span data-stu-id="2043e-225">TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="2043e-226">もう一方のエンドポイントが選択したネゴシエーションに基づいて、TCP または TLS ダイヤルバックを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="2043e-226">Based on negotiation choices of the other end point, TCP or TLS Dialback will be accepted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2043e-227">省略可能</span><span class="sxs-lookup"><span data-stu-id="2043e-227">Optional</span></span></p></td>
<td><p><span data-ttu-id="2043e-228">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="2043e-228">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="2043e-229">False</span><span class="sxs-lookup"><span data-stu-id="2043e-229">False</span></span></p></td>
<td><p><span data-ttu-id="2043e-230">無効な構成</span><span class="sxs-lookup"><span data-stu-id="2043e-230">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="2043e-231">SASL またはダイヤルバックを有効化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2043e-231">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2043e-232">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="2043e-232">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="2043e-233">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="2043e-233">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="2043e-234">正</span><span class="sxs-lookup"><span data-stu-id="2043e-234">True</span></span></p></td>
<td><p><span data-ttu-id="2043e-235">TCP ダイヤルバック</span><span class="sxs-lookup"><span data-stu-id="2043e-235">TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="2043e-236">利用できるネゴシエーション方式は TCP ダイヤルバック のみです。</span><span class="sxs-lookup"><span data-stu-id="2043e-236">TCP Dialback is the only negotiation method available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2043e-237">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="2043e-237">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="2043e-238">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="2043e-238">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="2043e-239">False</span><span class="sxs-lookup"><span data-stu-id="2043e-239">False</span></span></p></td>
<td><p><span data-ttu-id="2043e-240">無効な構成</span><span class="sxs-lookup"><span data-stu-id="2043e-240">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="2043e-241">SASL またはダイヤルバックを有効化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2043e-241">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

