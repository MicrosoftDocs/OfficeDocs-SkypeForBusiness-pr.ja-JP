---
title: 'Lync Server 2013: ユーザーごとのプレゼンスポリシーの割り当て'
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
ms.openlocfilehash: 4ec15b826614afcca970989b6436d3ad94d7941f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722837"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assigning-per-user-presence-policies-in-lync-server-2013"></a><span data-ttu-id="3c000-102">Lync Server 2013 でのユーザーごとのプレゼンスポリシーの割り当て</span><span class="sxs-lookup"><span data-stu-id="3c000-102">Assigning per-user presence policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3c000-103">_**最終更新日:** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="3c000-103">_**Topic Last Modified:** 2012-10-11_</span></span>

<span data-ttu-id="3c000-104">プレゼンスポリシーは、プレゼンスに影響する制限と制限のセットです。</span><span class="sxs-lookup"><span data-stu-id="3c000-104">A presence policy is a set of limits and restrictions that affect presence.</span></span> <span data-ttu-id="3c000-105">次の表では、Lync Server 2013 で使用できるプレゼンスポリシーの設定について説明します。</span><span class="sxs-lookup"><span data-stu-id="3c000-105">The following table describes the presence policy settings available in Lync Server 2013.</span></span>

### <a name="presence-policy-settings"></a><span data-ttu-id="3c000-106">プレゼンスポリシーの設定</span><span class="sxs-lookup"><span data-stu-id="3c000-106">Presence Policy Settings</span></span>

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
<th><span data-ttu-id="3c000-107">XML 名</span><span class="sxs-lookup"><span data-stu-id="3c000-107">XML name</span></span></th>
<th><span data-ttu-id="3c000-108">表示名</span><span class="sxs-lookup"><span data-stu-id="3c000-108">Display name</span></span></th>
<th><span data-ttu-id="3c000-109">説明</span><span class="sxs-lookup"><span data-stu-id="3c000-109">Description</span></span></th>
<th><span data-ttu-id="3c000-110">型</span><span class="sxs-lookup"><span data-stu-id="3c000-110">Type</span></span></th>
<th><span data-ttu-id="3c000-111">値</span><span class="sxs-lookup"><span data-stu-id="3c000-111">Value</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3c000-112">カテゴリのサブスクリプション</span><span class="sxs-lookup"><span data-stu-id="3c000-112">CategorySubscriptions</span></span></p></td>
<td><p><span data-ttu-id="3c000-113">サブスクライバーカテゴリのサブスクリプションの最大数</span><span class="sxs-lookup"><span data-stu-id="3c000-113">Maximum Number of Subscriber Category Subscriptions</span></span></p></td>
<td><p><span data-ttu-id="3c000-114">サブスクライバーカテゴリのサブスクリプションの数を制限します。</span><span class="sxs-lookup"><span data-stu-id="3c000-114">Limits the number of subscriber category subscriptions.</span></span> <span data-ttu-id="3c000-115">たとえば、ユーザーのプレゼンスをサブスクライブしている場合は、連絡先カード、予定表データ、メモ、サービス、状態カテゴリごとに、カテゴリサブスクリプションが取得されます。</span><span class="sxs-lookup"><span data-stu-id="3c000-115">For example, when Communicator subscribes to a user’s presence, it obtains a category subscription for each of the contact card, calendar data, notes, services, and state categories.</span></span></p>
<p><span data-ttu-id="3c000-116">0に設定すると、ユーザーまたは連絡先オブジェクトは、他のユーザーが購読できないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="3c000-116">A setting of 0 means that the user or contact object cannot be subscribed to by others.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="3c000-117">この設定は、高い数値に設定されている場合に、パフォーマンスに大きな影響を与える可能性があります。また、平均的なユーザーが多数のユーザーに対して自分のプレゼンスをサブスクライブしている場合があります。</span><span class="sxs-lookup"><span data-stu-id="3c000-117">This setting can have a significant impact on performance if it is set to a high number, and the average user has a large number of users subscribing to his or her presence.</span></span>


</div></td>
<td><p><span data-ttu-id="3c000-118">整数型</span><span class="sxs-lookup"><span data-stu-id="3c000-118">Integer</span></span></p></td>
<td><p><span data-ttu-id="3c000-119">0-3000</span><span class="sxs-lookup"><span data-stu-id="3c000-119">0-3000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c000-120">PromptedSubscribers</span><span class="sxs-lookup"><span data-stu-id="3c000-120">PromptedSubscribers</span></span></p></td>
<td><p><span data-ttu-id="3c000-121">キューに登録されているプレゼンス情報の通知の最大数</span><span class="sxs-lookup"><span data-stu-id="3c000-121">Maximum Number of Queued Presence Subscription Alerts</span></span></p></td>
<td><p><span data-ttu-id="3c000-122">プロンプトを表示するサブスクライバーテーブルのエントリ数を制限します。</span><span class="sxs-lookup"><span data-stu-id="3c000-122">Limits the number of entries in the prompted subscribers table.</span></span> <span data-ttu-id="3c000-123">この設定では、特定のユーザーに対してキューに入れることができるプロンプトの最大数を決定します。</span><span class="sxs-lookup"><span data-stu-id="3c000-123">This setting determines the maximum number of prompts that can be queued for a given user.</span></span> <span data-ttu-id="3c000-124">たとえば、ユーザー A がユーザー B のプレゼンスをサブスクライブしている場合、ユーザー B はユーザー A がユーザー B に登録されていることを知らせるメッセージを受け取り、ユーザー b の [プロンプトを表示するサブスクライバー] テーブルに確認メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3c000-124">For example, when user A subscribes to user B’s presence, user B receives a prompt that user A is now subscribed to user B, and an acknowledgement prompt is created in user B’s prompted subscribers table.</span></span> <span data-ttu-id="3c000-125">ユーザー B がサブスクリプションを承認するか、承認すると、確認メッセージがユーザー B のプロンプトのサブスクライバーテーブルから削除されます。</span><span class="sxs-lookup"><span data-stu-id="3c000-125">After user B accepts, or acknowledges, the subscription, the acknowledgement prompt is removed from user B’s prompted subscribers table.</span></span></p>
<p><span data-ttu-id="3c000-126">0に設定すると、他のユーザーが自分のプレゼンスをサブスクライブしているときに、ユーザーにメッセージが表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="3c000-126">A setting of 0 means that the user is not prompted when someone subscribes to his or her presence.</span></span></p></td>
<td><p><span data-ttu-id="3c000-127">Integer または Token</span><span class="sxs-lookup"><span data-stu-id="3c000-127">Integer or Token</span></span></p></td>
<td><p><span data-ttu-id="3c000-128">0-500</span><span class="sxs-lookup"><span data-stu-id="3c000-128">0-500</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="3c000-129">既定では、Lync Server を展開すると、既定の**ポリシー**と**サービス: Medium**プレゼンスポリシーがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="3c000-129">By default, the **Default Policy** and **Service: Medium** presence policies are installed when you deploy Lync Server.</span></span> <span data-ttu-id="3c000-130">次の表では、2つのプレゼンスポリシーの固有の設定について説明します。</span><span class="sxs-lookup"><span data-stu-id="3c000-130">The following table describes the specific settings of the two presence policies.</span></span>

### <a name="presence-policies"></a><span data-ttu-id="3c000-131">プレゼンスポリシー</span><span class="sxs-lookup"><span data-stu-id="3c000-131">Presence Policies</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3c000-132">ポリシー名</span><span class="sxs-lookup"><span data-stu-id="3c000-132">Policy name</span></span></th>
<th><span data-ttu-id="3c000-133">説明</span><span class="sxs-lookup"><span data-stu-id="3c000-133">Description</span></span></th>
<th><span data-ttu-id="3c000-134">カテゴリのサブスクリプション</span><span class="sxs-lookup"><span data-stu-id="3c000-134">CategorySubscriptions</span></span></th>
<th><span data-ttu-id="3c000-135">PromptedSubscribers</span><span class="sxs-lookup"><span data-stu-id="3c000-135">PromptedSubscribers</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3c000-136">既定のポリシー</span><span class="sxs-lookup"><span data-stu-id="3c000-136">Default Policy</span></span></p></td>
<td><p><span data-ttu-id="3c000-137">一般的なユーザー向けのポリシー。</span><span class="sxs-lookup"><span data-stu-id="3c000-137">Policy for typical users.</span></span> <span data-ttu-id="3c000-138">これは既定のプレゼンスポリシーです。</span><span class="sxs-lookup"><span data-stu-id="3c000-138">This is the default presence policy.</span></span></p></td>
<td><p><span data-ttu-id="3c000-139">1000</span><span class="sxs-lookup"><span data-stu-id="3c000-139">1000</span></span></p></td>
<td><p><span data-ttu-id="3c000-140">200</span><span class="sxs-lookup"><span data-stu-id="3c000-140">200</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c000-141">サービス: 媒体</span><span class="sxs-lookup"><span data-stu-id="3c000-141">Service: Medium</span></span></p></td>
<td><p><span data-ttu-id="3c000-142">他のユーザーがオブジェクトのプレゼンスをサブスクライブする必要があるアプリケーションのポリシー。</span><span class="sxs-lookup"><span data-stu-id="3c000-142">Policy for applications that require more users to subscribe to the object’s presence.</span></span></p></td>
<td><p><span data-ttu-id="3c000-143">1000</span><span class="sxs-lookup"><span data-stu-id="3c000-143">1000</span></span></p></td>
<td><p><span data-ttu-id="3c000-144">0</span><span class="sxs-lookup"><span data-stu-id="3c000-144">0</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

