---
title: 'Lync Server 2013: グループ通話ピックアップの容量計画'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning for Group Call Pickup
ms:assetid: 0d654a19-6cf0-4118-903d-ec2c4e519253
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ984297(v=OCS.15)
ms:contentKeyID: 51476680
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1ee25eb942a044840fac6aef0f5126f06b03cd9f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137206"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="2daa2-102">Lync Server 2013 でのグループ通話ピックアップの処理能力計画</span><span class="sxs-lookup"><span data-stu-id="2daa2-102">Capacity planning for Group Call Pickup in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2daa2-103">_**トピックの最終更新日:** 2013-02-12_</span><span class="sxs-lookup"><span data-stu-id="2daa2-103">_**Topic Last Modified:** 2013-02-12_</span></span>

<div id="sectionSection0" class="section">

<span data-ttu-id="2daa2-104">次の表では、容量計画の要件の基礎として使用できるグループ通話ピックアップユーザーモデルについて説明します。</span><span class="sxs-lookup"><span data-stu-id="2daa2-104">The following table describes the Group Call Pickup user model that you can use as the basis for capacity planning requirements.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2daa2-105">グループ通話ピックアップは、コールパークアプリケーションに基づいています。</span><span class="sxs-lookup"><span data-stu-id="2daa2-105">Group Call Pickup is based on the Call Park application.</span></span> <span data-ttu-id="2daa2-106">障害復旧の処理能力を計画する場合は、ペアになっているプールの各プールで、両方のプールのグループ通話ピックアップを含むコールパークサービスのワークロードを処理できる必要があることに留意してください。</span><span class="sxs-lookup"><span data-stu-id="2daa2-106">Keep in mind that, for disaster recovery capacity planning, each pool of a paired pool should be able to handle the workloads for Call Park services, including Group Call Pickup, in both pools.</span></span>



</div>

### <a name="group-call-pickup-user-model"></a><span data-ttu-id="2daa2-107">グループ通話ピックアップユーザーモデル</span><span class="sxs-lookup"><span data-stu-id="2daa2-107">Group Call Pickup User Model</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2daa2-108">測定基準</span><span class="sxs-lookup"><span data-stu-id="2daa2-108">Metric</span></span></th>
<th><span data-ttu-id="2daa2-109">フロントエンドプールごと (8 台のフロントエンドサーバー)</span><span class="sxs-lookup"><span data-stu-id="2daa2-109">Per Front End pool (with 8 Front End Servers)</span></span></th>
<th><span data-ttu-id="2daa2-110">Standard Edition サーバーごと</span><span class="sxs-lookup"><span data-stu-id="2daa2-110">Per Standard Edition server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2daa2-111">グループあたりの推奨ユーザー数</span><span class="sxs-lookup"><span data-stu-id="2daa2-111">Recommended number of users per group</span></span></p></td>
<td><p><span data-ttu-id="2daa2-112">50</span><span class="sxs-lookup"><span data-stu-id="2daa2-112">50</span></span></p></td>
<td><p><span data-ttu-id="2daa2-113">50</span><span class="sxs-lookup"><span data-stu-id="2daa2-113">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2daa2-114">推奨されるグループの数</span><span class="sxs-lookup"><span data-stu-id="2daa2-114">Recommended number of groups</span></span></p></td>
<td><p><span data-ttu-id="2daa2-115">500</span><span class="sxs-lookup"><span data-stu-id="2daa2-115">500</span></span></p></td>
<td><p><span data-ttu-id="2daa2-116">60</span><span class="sxs-lookup"><span data-stu-id="2daa2-116">60</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2daa2-117">グループ通話ピックアップを有効にしたプールあたりの最大ユーザー数</span><span class="sxs-lookup"><span data-stu-id="2daa2-117">Maximum number of users per pool enabled for Group Call Pickup</span></span></p></td>
<td><p><span data-ttu-id="2daa2-118">25,000</span><span class="sxs-lookup"><span data-stu-id="2daa2-118">25,000</span></span></p></td>
<td><p><span data-ttu-id="2daa2-119">3,000</span><span class="sxs-lookup"><span data-stu-id="2daa2-119">3,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2daa2-120">プールごとに1分あたりにグループ通話ピックアップが有効になっているユーザー総数に対する着信通話の最大速度</span><span class="sxs-lookup"><span data-stu-id="2daa2-120">Maximum rate of incoming calls to total users enabled for Group Call Pickup per pool per minute</span></span></p></td>
<td><p><span data-ttu-id="2daa2-121">500</span><span class="sxs-lookup"><span data-stu-id="2daa2-121">500</span></span></p></td>
<td><p><span data-ttu-id="2daa2-122">60</span><span class="sxs-lookup"><span data-stu-id="2daa2-122">60</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2daa2-123">プールごとに1分あたりにグループ通話ピックアップがあるユーザーによって取得される通話の最大速度</span><span class="sxs-lookup"><span data-stu-id="2daa2-123">Maximum rate of calls retrieved by users with Group Call Pickup per pool per minute</span></span></p></td>
<td><p><span data-ttu-id="2daa2-124">200</span><span class="sxs-lookup"><span data-stu-id="2daa2-124">200</span></span></p></td>
<td><p><span data-ttu-id="2daa2-125">まで</span><span class="sxs-lookup"><span data-stu-id="2daa2-125">25</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <UL>
> <LI>
> <P><span data-ttu-id="2daa2-126">フロントエンドサーバーが8台未満のフロントエンドプールの場合は、測定値を直線的に計算します。</span><span class="sxs-lookup"><span data-stu-id="2daa2-126">For Front End pools that have fewer than eight Front End Servers, calculate the metrics linearly.</span></span> <span data-ttu-id="2daa2-127">たとえば、フロントエンドプールに1台のフロントエンドサーバーがある場合は、表に示されている値の最大負荷を1/8 として計算します。</span><span class="sxs-lookup"><span data-stu-id="2daa2-127">For example, if your Front End pool has one Front End Server, calculate the maximum load as 1/8 of the values shown in the table.</span></span></P>
> <LI>
> <P><span data-ttu-id="2daa2-128">プールあたりのユーザーの最大数を超過しない限り、グループあたりのユーザー数を増減できます。また、グループの数を減らすこともできます。</span><span class="sxs-lookup"><span data-stu-id="2daa2-128">You can increase or decrease the recommended number of users per group and number of groups as long as you do not exceed the maximum number of users per pool.</span></span> <span data-ttu-id="2daa2-129">たとえば、Standard Edition サーバーでは、グループ通話ピックアップが有効になっているユーザーの数がユーザーモデルの最大数 (つまり、25ユーザー3000がグループ通話ピックアップを有効にした場合は 120) の範囲内にあるために、グループごとに25ユーザーの120グループを持つことができます。</span><span class="sxs-lookup"><span data-stu-id="2daa2-129">For example, your Standard Edition server can have 120 groups with 25 users per group because the number of users enabled for Group Call Pickup is still within the user model maximum (that is, 120 groups times 25 users is 3,000 users enabled for Group Call Pickup).</span></span></P></LI></UL>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

