---
title: 'Lync Server 2013: 発信音声ルーティングの計画'
description: 'Lync Server 2013: 発信音声ルーティングの計画。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning outbound voice routing
ms:assetid: 37c55fa4-175a-4190-b9e4-c2e5ac7b9261
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425853(v=OCS.15)
ms:contentKeyID: 48183835
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 057f81b995e231c2025a9fcb07e675086a662efe
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563983"
---
# <a name="planning-outbound-voice-routing-in-lync-server-2013"></a><span data-ttu-id="9d910-103">Lync Server 2013 での発信音声ルーティングの計画</span><span class="sxs-lookup"><span data-stu-id="9d910-103">Planning outbound voice routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9d910-104">_**トピックの最終更新日:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="9d910-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="9d910-p101">発信通話ルーティングは、公衆交換電話網 (PSTN) ゲートウェイ、トランク、または構内交換機 (PBX) に対して発信される通話に適用されます。ユーザーが電話をかけると、サーバーは、電話番号を E.164 形式に正規化し、必要に応じて、一致する SIP URI があるかどうかを調べます。一致する SIP URI が見つからない場合は、指定されたダイヤル文字列に基づいて発信通話ルーティング ロジックが適用されます。ユーザーは、次の表で説明するサーバー設定を構成することで、そのロジックを定義します。</span><span class="sxs-lookup"><span data-stu-id="9d910-p101">Outbound call routing applies to calls that are destined for a public switched telephone network (PSTN) gateway, trunk, or private branch exchange (PBX). When a user places a call, the server normalizes the phone number to E.164 format, if necessary, and attempts to match it to a SIP URI. If the server cannot make the match, it applies outbound call routing logic based on the supplied dial string. You define that logic by configuring the server settings that are described in the following table.</span></span>

### <a name="lync-server-outbound-call-routing-settings"></a><span data-ttu-id="9d910-109">Lync Server 発信通話ルーティング設定</span><span class="sxs-lookup"><span data-stu-id="9d910-109">Lync Server Outbound Call Routing Settings</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9d910-110">オブジェクト</span><span class="sxs-lookup"><span data-stu-id="9d910-110">Object</span></span></th>
<th><span data-ttu-id="9d910-111">説明</span><span class="sxs-lookup"><span data-stu-id="9d910-111">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9d910-112">ダイヤル プラン</span><span class="sxs-lookup"><span data-stu-id="9d910-112">Dial Plan</span></span></p></td>
<td><p><span data-ttu-id="9d910-113">ダイヤル プランとは、電話番号の承認と通話のルーティングを目的として、特定の場所、個々のユーザー、または連絡先オブジェクトの電話番号を 1 つの標準形式 (E.164) に変換する正規化ルールのセットに名前を付けたものです。</span><span class="sxs-lookup"><span data-stu-id="9d910-113">A dial plan is a named set of normalization rules that translates phone numbers for a named location, individual user, or contact object into a single standard (E.164) format for purposes of phone authorization and call routing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d910-114">正規化ルール</span><span class="sxs-lookup"><span data-stu-id="9d910-114">Normalization rule</span></span></p></td>
<td><p><span data-ttu-id="9d910-p102">正規化ルールは、さまざまな形式で表現された電話番号を指定された各場所、ユーザー、または連絡先オブジェクトにルーティングする方法を定義します。ダイヤル元の場所および電話をかける人や連絡先オブジェクトによって、同じダイヤル文字列が異なる方法で解釈および変換される場合があります。特定の位置に関連付けられた正規化ルールをまとめたものが、ダイヤル プランです。</span><span class="sxs-lookup"><span data-stu-id="9d910-p102">Normalization rules define how phone numbers expressed in various formats are to be routed for each specified location, user, or contact object. The same dial string may be interpreted and translated differently, depending on the location from which it is dialed and the person or contact object that makes the call. A set of normalization rules associated with a particular location constitutes a dial plan.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d910-118">音声ポリシー</span><span class="sxs-lookup"><span data-stu-id="9d910-118">Voice policy</span></span></p></td>
<td><p><span data-ttu-id="9d910-p103">音声ポリシーでは、1 つ以上の PSTN 使用法レコードを 1 人のユーザーまたはユーザーのグループに関連付けます。 音声ポリシーも、ユーザーが有効と無効を切り替えできる通話機能のリストを提供します。</span><span class="sxs-lookup"><span data-stu-id="9d910-p103">A voice policy associates one or more PSTN usage records with one user or a group of users. A voice policy also provides a list of calling features that you can enable or disable.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d910-121">PSTN 使用法レコード</span><span class="sxs-lookup"><span data-stu-id="9d910-121">PSTN usage record</span></span></p></td>
<td><p><span data-ttu-id="9d910-122">PSTN 使用法レコードは、組織内のさまざまなユーザーまたはグループが利用できる通話のクラス (内部、市内、長距離など) を指定します。</span><span class="sxs-lookup"><span data-stu-id="9d910-122">A PSTN usage record specifies a class of call (such as internal, local, or long distance) that can be made by various users, or groups of users, in an organization.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d910-123">通話ルート</span><span class="sxs-lookup"><span data-stu-id="9d910-123">Call Route</span></span></p></td>
<td><p><span data-ttu-id="9d910-p104">通話ルートでは、通話先の電話番号を特定のトランクおよび PSTN 使用法レコードに関連付けます。 PSTN ゲートウェイはトランクとみなされます。</span><span class="sxs-lookup"><span data-stu-id="9d910-p104">A call route associates destination phone numbers with particular trunks and PSTN usage records. A PSTN gateway is considered a trunk.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a><span data-ttu-id="9d910-126">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="9d910-126">In This Section</span></span>

<span data-ttu-id="9d910-127">ここでは、次の発信通話ルーティング サーバー設定の構成ガイドラインを提供します。</span><span class="sxs-lookup"><span data-stu-id="9d910-127">This section provides guidelines for configuring the following outbound call routing server settings:</span></span>

  - <span></span>  
    [<span data-ttu-id="9d910-128">Lync Server 2013 のダイヤルプランと正規化ルール</span><span class="sxs-lookup"><span data-stu-id="9d910-128">Dial plans and normalization rules in Lync Server 2013</span></span>](lync-server-2013-dial-plans-and-normalization-rules.md)

  - <span></span>  
    [<span data-ttu-id="9d910-129">Lync Server 2013 の音声ポリシー</span><span class="sxs-lookup"><span data-stu-id="9d910-129">Voice policies in Lync Server 2013</span></span>](lync-server-2013-voice-policies.md)

  - <span></span>  
    [<span data-ttu-id="9d910-130">Lync Server 2013 の PSTN 使用法レコード</span><span class="sxs-lookup"><span data-stu-id="9d910-130">PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-pstn-usage-records.md)

  - <span></span>  
    [<span data-ttu-id="9d910-131">Lync Server 2013 の音声ルート</span><span class="sxs-lookup"><span data-stu-id="9d910-131">Voice routes in Lync Server 2013</span></span>](lync-server-2013-voice-routes.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9d910-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="9d910-132">See Also</span></span>


[<span data-ttu-id="9d910-133">Lync Server 2013 での SIP トランキング</span><span class="sxs-lookup"><span data-stu-id="9d910-133">SIP trunking in Lync Server 2013</span></span>](lync-server-2013-sip-trunking.md)  
[<span data-ttu-id="9d910-134">Lync Server 2013 の直接 SIP 接続</span><span class="sxs-lookup"><span data-stu-id="9d910-134">Direct SIP connections in Lync Server 2013</span></span>](lync-server-2013-direct-sip-connections.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

