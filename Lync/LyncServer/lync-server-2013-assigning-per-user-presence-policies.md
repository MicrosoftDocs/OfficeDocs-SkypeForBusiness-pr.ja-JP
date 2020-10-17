---
title: 'Lync Server 2013: ユーザーごとのプレゼンスポリシーの割り当て'
description: 'Lync Server 2013: ユーザーごとのプレゼンスポリシーの割り当て。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assigning per-user presence policies
ms:assetid: fd1097b7-248d-4b78-8c43-456b03257c18
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182614(v=OCS.15)
ms:contentKeyID: 48185955
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5c3d4b4bda0c4bb85065d546fdbb4b2578db0e3f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563373"
---
# <a name="assigning-per-user-presence-policies-in-lync-server-2013"></a><span data-ttu-id="d37a3-103">Lync Server 2013 でユーザーごとのプレゼンスポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="d37a3-103">Assigning per-user presence policies in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d37a3-104">_**トピックの最終更新日:** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="d37a3-104">_**Topic Last Modified:** 2012-10-11_</span></span>

<span data-ttu-id="d37a3-105">プレゼンス ポリシーは、プレゼンスに影響する一連の制限および制約事項です。</span><span class="sxs-lookup"><span data-stu-id="d37a3-105">A presence policy is a set of limits and restrictions that affect presence.</span></span> <span data-ttu-id="d37a3-106">次の表では、Lync Server 2013 で利用できるプレゼンスポリシーの設定について説明します。</span><span class="sxs-lookup"><span data-stu-id="d37a3-106">The following table describes the presence policy settings available in Lync Server 2013.</span></span>

### <a name="presence-policy-settings"></a><span data-ttu-id="d37a3-107">プレゼンス ポリシー設定</span><span class="sxs-lookup"><span data-stu-id="d37a3-107">Presence Policy Settings</span></span>

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
<th><span data-ttu-id="d37a3-108">XML 名</span><span class="sxs-lookup"><span data-stu-id="d37a3-108">XML name</span></span></th>
<th><span data-ttu-id="d37a3-109">表示名</span><span class="sxs-lookup"><span data-stu-id="d37a3-109">Display name</span></span></th>
<th><span data-ttu-id="d37a3-110">説明</span><span class="sxs-lookup"><span data-stu-id="d37a3-110">Description</span></span></th>
<th><span data-ttu-id="d37a3-111">型</span><span class="sxs-lookup"><span data-stu-id="d37a3-111">Type</span></span></th>
<th><span data-ttu-id="d37a3-112">値</span><span class="sxs-lookup"><span data-stu-id="d37a3-112">Value</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d37a3-113">カテゴリのサブスクリプション</span><span class="sxs-lookup"><span data-stu-id="d37a3-113">CategorySubscriptions</span></span></p></td>
<td><p><span data-ttu-id="d37a3-114">サブスクライバー カテゴリ サブスクリプションの最大数</span><span class="sxs-lookup"><span data-stu-id="d37a3-114">Maximum Number of Subscriber Category Subscriptions</span></span></p></td>
<td><p><span data-ttu-id="d37a3-p102">サブスクライバー カテゴリ サブスクリプションの数を制限します。 たとえば Communicator は、ユーザーのプレゼンスに加入するとき、連絡先カード、予定表データ、メモ、サービス、および状態カテゴリごとにカテゴリ サブスクリプションを取得します。</span><span class="sxs-lookup"><span data-stu-id="d37a3-p102">Limits the number of subscriber category subscriptions. For example, when Communicator subscribes to a user’s presence, it obtains a category subscription for each of the contact card, calendar data, notes, services, and state categories.</span></span></p>
<p><span data-ttu-id="d37a3-117">設定が 0 の場合は、そのユーザーまたは連絡先オブジェクトに他のユーザーが加入することはできないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="d37a3-117">A setting of 0 means that the user or contact object cannot be subscribed to by others.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="d37a3-118">この設定が高い値に設定されているとパフォーマンスに著しい影響を与える可能性があり、平均的なユーザーには、そのユーザーのプレゼンスに多くのユーザーが加入しています。</span><span class="sxs-lookup"><span data-stu-id="d37a3-118">This setting can have a significant impact on performance if it is set to a high number, and the average user has a large number of users subscribing to his or her presence.</span></span>


</div></td>
<td><p><span data-ttu-id="d37a3-119">整数</span><span class="sxs-lookup"><span data-stu-id="d37a3-119">Integer</span></span></p></td>
<td><p><span data-ttu-id="d37a3-120">0-3000</span><span class="sxs-lookup"><span data-stu-id="d37a3-120">0-3000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d37a3-121">PromptedSubscribers</span><span class="sxs-lookup"><span data-stu-id="d37a3-121">PromptedSubscribers</span></span></p></td>
<td><p><span data-ttu-id="d37a3-122">キューに入れられるプレゼンス サブスクリプション通知の最大数</span><span class="sxs-lookup"><span data-stu-id="d37a3-122">Maximum Number of Queued Presence Subscription Alerts</span></span></p></td>
<td><p><span data-ttu-id="d37a3-p103">要求されたサブスクライバー テーブルのエントリ数を制限します。 この設定により、指定されたユーザーの場合にキューに入れることができるプロンプトの最大数が決まります。 たとえば、ユーザー A がユーザー B のプレゼンスに加入すると、ユーザー B は、ユーザー A が現在ユーザー B に加入したことを示すプロンプトを受信し、ユーザー B の要求されたサブスクライバー テーブルで受信確認プロンプトが作成されます。 ユーザー B がサブスクリプションを受け入れる、つまり確認すると、その受信確認プロンプトはユーザー B の要求されたサブスクライバー テーブルから削除されます。</span><span class="sxs-lookup"><span data-stu-id="d37a3-p103">Limits the number of entries in the prompted subscribers table. This setting determines the maximum number of prompts that can be queued for a given user. For example, when user A subscribes to user B’s presence, user B receives a prompt that user A is now subscribed to user B, and an acknowledgement prompt is created in user B’s prompted subscribers table. After user B accepts, or acknowledges, the subscription, the acknowledgement prompt is removed from user B’s prompted subscribers table.</span></span></p>
<p><span data-ttu-id="d37a3-127">設定が 0 の場合は、そのユーザーのプレゼンスに他のユーザーが加入しても、そのユーザーにプロンプトが送信されることはないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="d37a3-127">A setting of 0 means that the user is not prompted when someone subscribes to his or her presence.</span></span></p></td>
<td><p><span data-ttu-id="d37a3-128">整数またはトークン</span><span class="sxs-lookup"><span data-stu-id="d37a3-128">Integer or Token</span></span></p></td>
<td><p><span data-ttu-id="d37a3-129">0-500</span><span class="sxs-lookup"><span data-stu-id="d37a3-129">0-500</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d37a3-130">既定では、Lync Server を展開すると、 **既定のポリシー** と **サービス: 中** プレゼンスポリシーがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="d37a3-130">By default, the **Default Policy** and **Service: Medium** presence policies are installed when you deploy Lync Server.</span></span> <span data-ttu-id="d37a3-131">次の表に、この 2 つのプレゼンス ポリシーの具体的な設定の説明を示します。</span><span class="sxs-lookup"><span data-stu-id="d37a3-131">The following table describes the specific settings of the two presence policies.</span></span>

### <a name="presence-policies"></a><span data-ttu-id="d37a3-132">プレゼンス ポリシー</span><span class="sxs-lookup"><span data-stu-id="d37a3-132">Presence Policies</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d37a3-133">[ポリシー名]</span><span class="sxs-lookup"><span data-stu-id="d37a3-133">Policy name</span></span></th>
<th><span data-ttu-id="d37a3-134">説明</span><span class="sxs-lookup"><span data-stu-id="d37a3-134">Description</span></span></th>
<th><span data-ttu-id="d37a3-135">カテゴリのサブスクリプション</span><span class="sxs-lookup"><span data-stu-id="d37a3-135">CategorySubscriptions</span></span></th>
<th><span data-ttu-id="d37a3-136">PromptedSubscribers</span><span class="sxs-lookup"><span data-stu-id="d37a3-136">PromptedSubscribers</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d37a3-137">[既定のポリシー]</span><span class="sxs-lookup"><span data-stu-id="d37a3-137">Default Policy</span></span></p></td>
<td><p><span data-ttu-id="d37a3-p105">標準的なユーザーを対象とするポリシー。 これは既定のプレゼンス ポリシーです。</span><span class="sxs-lookup"><span data-stu-id="d37a3-p105">Policy for typical users. This is the default presence policy.</span></span></p></td>
<td><p><span data-ttu-id="d37a3-140">1000</span><span class="sxs-lookup"><span data-stu-id="d37a3-140">1000</span></span></p></td>
<td><p><span data-ttu-id="d37a3-141">200</span><span class="sxs-lookup"><span data-stu-id="d37a3-141">200</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d37a3-142">サービス: 中</span><span class="sxs-lookup"><span data-stu-id="d37a3-142">Service: Medium</span></span></p></td>
<td><p><span data-ttu-id="d37a3-143">より多くのユーザーがオブジェクトのプレゼンスに加入する必要があるアプリケーションを対象とするポリシー。</span><span class="sxs-lookup"><span data-stu-id="d37a3-143">Policy for applications that require more users to subscribe to the object’s presence.</span></span></p></td>
<td><p><span data-ttu-id="d37a3-144">1000</span><span class="sxs-lookup"><span data-stu-id="d37a3-144">1000</span></span></p></td>
<td><p><span data-ttu-id="d37a3-145">.0</span><span class="sxs-lookup"><span data-stu-id="d37a3-145">0</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

