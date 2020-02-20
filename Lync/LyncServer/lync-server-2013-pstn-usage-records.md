---
title: 'Lync Server 2013: PSTN 使用法レコード'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PSTN usage records
ms:assetid: b5f624aa-abe8-455b-a8e3-c228be230463
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412878(v=OCS.15)
ms:contentKeyID: 48185188
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9b58d6fd9a375544b456905e1479e32432dbac54
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152301"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="pstn-usage-records-in-lync-server-2013"></a><span data-ttu-id="03f1f-102">Lync Server 2013 の PSTN 使用法レコード</span><span class="sxs-lookup"><span data-stu-id="03f1f-102">PSTN usage records in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="03f1f-103">_**トピックの最終更新日:** 2012-09-23_</span><span class="sxs-lookup"><span data-stu-id="03f1f-103">_**Topic Last Modified:** 2012-09-23_</span></span>

<span data-ttu-id="03f1f-p101">PSTN 使用法レコードの計画では、主に、CEO から派遣社員、コンサルタント、および臨時スタッフに至る組織内のすべてのユーザーに現在適用されているすべての通話許可の一覧を作成します。 この作業を行うと、既存の通話許可を再度検証し、それらを修正することができます。 エンタープライズ VoIP の見込みユーザーに適用する通話許可のみに対応した PSTN 使用法レコードを作成することもできますが、現時点で通話許可がエンタープライズ VoIP で有効なユーザー グループのメンバーに適用されるかどうかに関係なく、すべての通話許可に対応した PSTN 使用法レコードを作成する方が、長期的には優れたソリューションになる場合があります。 通話許可の変更や、異なる通話許可を持つ新規ユーザーを追加する場合でも、必要な電話 PSTN 使用法レコードは既に作成済みであるため、新しく作成する必要がありません。</span><span class="sxs-lookup"><span data-stu-id="03f1f-p101">Planning PSTN usage records consists mainly of listing all the call permissions that are currently in force in your organization, from the CEO to temporary workers, consultants, and contingent staff. This process also provides an opportunity to reexamine existing call permissions and revise them. You can create PSTN usage records only for those call permissions that apply to your anticipated Enterprise Voice users, but a better long-range solution might be to create PSTN usage records for all call permissions, regardless of whether some may not currently apply to the group of users to be enabled for Enterprise Voice. If call permissions change or new users with different call permissions are added, you will have already created the required PSTN usage records.</span></span>

<span data-ttu-id="03f1f-108">次の表に、一般的な PSTN 使用法テーブルを示します。</span><span class="sxs-lookup"><span data-stu-id="03f1f-108">The following table shows a typical PSTN usage table.</span></span>

### <a name="pstn-usage-records"></a><span data-ttu-id="03f1f-109">PSTN 使用法レコード</span><span class="sxs-lookup"><span data-stu-id="03f1f-109">PSTN Usage Records</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="03f1f-110">電話属性</span><span class="sxs-lookup"><span data-stu-id="03f1f-110">Phone attribute</span></span></th>
<th><span data-ttu-id="03f1f-111">説明</span><span class="sxs-lookup"><span data-stu-id="03f1f-111">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="03f1f-112">ローカル</span><span class="sxs-lookup"><span data-stu-id="03f1f-112">Local</span></span></p></td>
<td><p><span data-ttu-id="03f1f-113">市内通話</span><span class="sxs-lookup"><span data-stu-id="03f1f-113">Local calls</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03f1f-114">長距離</span><span class="sxs-lookup"><span data-stu-id="03f1f-114">Long-Distance</span></span></p></td>
<td><p><span data-ttu-id="03f1f-115">長距離通話</span><span class="sxs-lookup"><span data-stu-id="03f1f-115">Long distance calls</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03f1f-116">International</span><span class="sxs-lookup"><span data-stu-id="03f1f-116">International</span></span></p></td>
<td><p><span data-ttu-id="03f1f-117">国際通話</span><span class="sxs-lookup"><span data-stu-id="03f1f-117">International calls</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03f1f-118">デリー</span><span class="sxs-lookup"><span data-stu-id="03f1f-118">Delhi</span></span></p></td>
<td><p><span data-ttu-id="03f1f-119">Delhi のフルタイム社員</span><span class="sxs-lookup"><span data-stu-id="03f1f-119">Delhi full-time employees</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03f1f-120">レッドモンド</span><span class="sxs-lookup"><span data-stu-id="03f1f-120">Redmond</span></span></p></td>
<td><p><span data-ttu-id="03f1f-121">Redmond のフルタイム社員</span><span class="sxs-lookup"><span data-stu-id="03f1f-121">Redmond full-time employees</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03f1f-122">RedmondTemps</span><span class="sxs-lookup"><span data-stu-id="03f1f-122">RedmondTemps</span></span></p></td>
<td><p><span data-ttu-id="03f1f-123">Redmond の派遣社員</span><span class="sxs-lookup"><span data-stu-id="03f1f-123">Redmond temporary employees</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03f1f-124">Zurich フルタ</span><span class="sxs-lookup"><span data-stu-id="03f1f-124">Zurich</span></span></p></td>
<td><p><span data-ttu-id="03f1f-125">Zurich のフルタイム社員</span><span class="sxs-lookup"><span data-stu-id="03f1f-125">Zurich full-time employees</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="03f1f-p102">PSTN 使用法レコードは単独では機能しません。 PSTN 使用法レコードは、以下と組み合わせて使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="03f1f-p102">By themselves, PSTN usage records do not do anything. For them to work, you must associate them with the following:</span></span>

  - <span data-ttu-id="03f1f-128">音声ポリシー (ユーザーに割り当てる)</span><span class="sxs-lookup"><span data-stu-id="03f1f-128">Voice policies, which are assigned to users.</span></span>

  - <span data-ttu-id="03f1f-129">ルート (電話番号に割り当てる)</span><span class="sxs-lookup"><span data-stu-id="03f1f-129">Routes, which are assigned to phone numbers.</span></span>

<span data-ttu-id="03f1f-130">音声ポリシーとルートの詳細については、「lync server [2013 の音声ポリシー](lync-server-2013-voice-policies.md) 」および「 [lync server 2013 の音声ルート](lync-server-2013-voice-routes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="03f1f-130">For details about voice policies and routes, see [Voice policies in Lync Server 2013](lync-server-2013-voice-policies.md) and [Voice routes in Lync Server 2013](lync-server-2013-voice-routes.md).</span></span> <span data-ttu-id="03f1f-131">これらを作成して構成する方法の詳細については、「 [Lync Server 2013 で送信呼び出しの音声ルートを構成](lync-server-2013-configuring-voice-routes-for-outbound-calls.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="03f1f-131">For details about how to create and configure them, see [Configuring voice routes for outbound calls in Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

