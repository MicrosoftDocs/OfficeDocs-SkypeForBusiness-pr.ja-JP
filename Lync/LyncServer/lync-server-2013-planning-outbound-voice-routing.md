---
title: 'Lync Server 2013: 発信音声ルーティングの計画'
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
ms.openlocfilehash: 9d33fbe8d15b78bed9dd651cd7facf35a8249f64
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747667"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-outbound-voice-routing-in-lync-server-2013"></a><span data-ttu-id="365bd-102">Lync Server 2013 での発信音声ルーティングの計画</span><span class="sxs-lookup"><span data-stu-id="365bd-102">Planning outbound voice routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="365bd-103">_**最終更新日:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="365bd-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="365bd-104">発信通話ルーティングは、公衆交換電話網 (PSTN) ゲートウェイ、トランク、またはプライベート支店交換 (PBX) に向けての通話に適用されます。</span><span class="sxs-lookup"><span data-stu-id="365bd-104">Outbound call routing applies to calls that are destined for a public switched telephone network (PSTN) gateway, trunk, or private branch exchange (PBX).</span></span> <span data-ttu-id="365bd-105">ユーザーが通話を発信すると、サーバーでは、必要に応じて、電話番号が E.i 形式に正規化され、SIP URI と照合されるようになります。</span><span class="sxs-lookup"><span data-stu-id="365bd-105">When a user places a call, the server normalizes the phone number to E.164 format, if necessary, and attempts to match it to a SIP URI.</span></span> <span data-ttu-id="365bd-106">一致する SIP URI が見つからない場合は、指定されたダイヤル文字列に基づいて発信通話ルーティング ロジックが適用されます。</span><span class="sxs-lookup"><span data-stu-id="365bd-106">If the server cannot make the match, it applies outbound call routing logic based on the supplied dial string.</span></span> <span data-ttu-id="365bd-107">ユーザーは、次の表で説明するサーバー設定を構成することで、そのロジックを定義します。</span><span class="sxs-lookup"><span data-stu-id="365bd-107">You define that logic by configuring the server settings that are described in the following table.</span></span>

### <a name="lync-server-outbound-call-routing-settings"></a><span data-ttu-id="365bd-108">Lync Server の送信通話ルーティング設定</span><span class="sxs-lookup"><span data-stu-id="365bd-108">Lync Server Outbound Call Routing Settings</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="365bd-109">オブジェクト</span><span class="sxs-lookup"><span data-stu-id="365bd-109">Object</span></span></th>
<th><span data-ttu-id="365bd-110">説明</span><span class="sxs-lookup"><span data-stu-id="365bd-110">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="365bd-111">ダイヤル プラン</span><span class="sxs-lookup"><span data-stu-id="365bd-111">Dial Plan</span></span></p></td>
<td><p><span data-ttu-id="365bd-112">ダイヤル プランとは、電話番号の承認と通話のルーティングを目的として、特定の場所、個々のユーザー、または連絡先オブジェクトの電話番号を 1 つの標準形式 (E.164) に変換する正規化ルールのセットに名前を付けたものです。</span><span class="sxs-lookup"><span data-stu-id="365bd-112">A dial plan is a named set of normalization rules that translates phone numbers for a named location, individual user, or contact object into a single standard (E.164) format for purposes of phone authorization and call routing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="365bd-113">正規化ルール</span><span class="sxs-lookup"><span data-stu-id="365bd-113">Normalization rule</span></span></p></td>
<td><p><span data-ttu-id="365bd-p102">正規化ルールは、さまざまな形式で表現された電話番号を指定された各場所、ユーザー、または連絡先オブジェクトにルーティングする方法を定義します。ダイヤル元の場所および電話をかける人や連絡先オブジェクトによって、同じダイヤル文字列が異なる方法で解釈および変換される場合があります。特定の位置に関連付けられた正規化ルールをまとめたものが、ダイヤル プランです。</span><span class="sxs-lookup"><span data-stu-id="365bd-p102">Normalization rules define how phone numbers expressed in various formats are to be routed for each specified location, user, or contact object. The same dial string may be interpreted and translated differently, depending on the location from which it is dialed and the person or contact object that makes the call. A set of normalization rules associated with a particular location constitutes a dial plan.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="365bd-117">音声ポリシー</span><span class="sxs-lookup"><span data-stu-id="365bd-117">Voice policy</span></span></p></td>
<td><p><span data-ttu-id="365bd-p103">音声ポリシーでは、1 つ以上の PSTN 使用法レコードを 1 人のユーザーまたはユーザーのグループに関連付けます。音声ポリシーも、ユーザーが有効と無効を切り替えられる通話機能のリストを提供します。</span><span class="sxs-lookup"><span data-stu-id="365bd-p103">A voice policy associates one or more PSTN usage records with one user or a group of users. A voice policy also provides a list of calling features that you can enable or disable.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="365bd-120">PSTN 使用法レコード</span><span class="sxs-lookup"><span data-stu-id="365bd-120">PSTN usage record</span></span></p></td>
<td><p><span data-ttu-id="365bd-121">PSTN 使用法レコードは、組織内のさまざまなユーザーまたはグループが利用できる通話のクラス (内部、市内、長距離など) を指定します。</span><span class="sxs-lookup"><span data-stu-id="365bd-121">A PSTN usage record specifies a class of call (such as internal, local, or long distance) that can be made by various users, or groups of users, in an organization.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="365bd-122">通話ルート</span><span class="sxs-lookup"><span data-stu-id="365bd-122">Call Route</span></span></p></td>
<td><p><span data-ttu-id="365bd-p104">通話ルートでは、通話先の電話番号を特定のトランクおよび PSTN 使用法レコードに関連付けます。PSTN ゲートウェイはトランクとみなされます。</span><span class="sxs-lookup"><span data-stu-id="365bd-p104">A call route associates destination phone numbers with particular trunks and PSTN usage records. A PSTN gateway is considered a trunk.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a><span data-ttu-id="365bd-125">このセクション中</span><span class="sxs-lookup"><span data-stu-id="365bd-125">In This Section</span></span>

<span data-ttu-id="365bd-126">このセクションでは、次の発信通話ルーティングサーバー設定を構成するためのガイドラインについて説明します。</span><span class="sxs-lookup"><span data-stu-id="365bd-126">This section provides guidelines for configuring the following outbound call routing server settings:</span></span>

  - <span></span>  
    [<span data-ttu-id="365bd-127">Lync Server 2013 でのダイヤルプランと正規化ルール</span><span class="sxs-lookup"><span data-stu-id="365bd-127">Dial plans and normalization rules in Lync Server 2013</span></span>](lync-server-2013-dial-plans-and-normalization-rules.md)

  - <span></span>  
    [<span data-ttu-id="365bd-128">Lync Server 2013 の音声ポリシー</span><span class="sxs-lookup"><span data-stu-id="365bd-128">Voice policies in Lync Server 2013</span></span>](lync-server-2013-voice-policies.md)

  - <span></span>  
    [<span data-ttu-id="365bd-129">Lync Server 2013 の PSTN 使用法レコード</span><span class="sxs-lookup"><span data-stu-id="365bd-129">PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-pstn-usage-records.md)

  - <span></span>  
    [<span data-ttu-id="365bd-130">Lync Server 2013 の音声ルート</span><span class="sxs-lookup"><span data-stu-id="365bd-130">Voice routes in Lync Server 2013</span></span>](lync-server-2013-voice-routes.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="365bd-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="365bd-131">See Also</span></span>


[<span data-ttu-id="365bd-132">Lync Server 2013 での SIP トランク</span><span class="sxs-lookup"><span data-stu-id="365bd-132">SIP trunking in Lync Server 2013</span></span>](lync-server-2013-sip-trunking.md)  
[<span data-ttu-id="365bd-133">Lync Server 2013 での直接 SIP 接続</span><span class="sxs-lookup"><span data-stu-id="365bd-133">Direct SIP connections in Lync Server 2013</span></span>](lync-server-2013-direct-sip-connections.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

