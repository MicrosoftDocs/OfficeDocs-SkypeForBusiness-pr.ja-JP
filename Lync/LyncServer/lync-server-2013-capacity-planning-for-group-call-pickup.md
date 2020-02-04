---
title: 'Lync Server 2013: グループ通話のピックアップのキャパシティ計画'
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
ms.openlocfilehash: 8d694b20d026d83b4cef37c713e38ab8066e22f3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730297"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="f7de2-102">Lync Server 2013 でのグループ通話の集配のキャパシティ計画</span><span class="sxs-lookup"><span data-stu-id="f7de2-102">Capacity planning for Group Call Pickup in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f7de2-103">_**最終更新日:** 2013-02-12_</span><span class="sxs-lookup"><span data-stu-id="f7de2-103">_**Topic Last Modified:** 2013-02-12_</span></span>

<div id="sectionSection0" class="section">

<span data-ttu-id="f7de2-104">次の表では、キャパシティ計画の要件の基礎として使用できるグループ通話ピックアップユーザーモデルについて説明します。</span><span class="sxs-lookup"><span data-stu-id="f7de2-104">The following table describes the Group Call Pickup user model that you can use as the basis for capacity planning requirements.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f7de2-105">グループ通話のピックアップは、コールパークアプリケーションに基づいています。</span><span class="sxs-lookup"><span data-stu-id="f7de2-105">Group Call Pickup is based on the Call Park application.</span></span> <span data-ttu-id="f7de2-106">障害復旧のキャパシティ計画の場合、ペアプールの各プールでは、両方のプールのグループ通話のピックアップを含む、コールパークサービスのワークロードを処理できる必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="f7de2-106">Keep in mind that, for disaster recovery capacity planning, each pool of a paired pool should be able to handle the workloads for Call Park services, including Group Call Pickup, in both pools.</span></span>



</div>

### <a name="group-call-pickup-user-model"></a><span data-ttu-id="f7de2-107">グループ通話のピックアップユーザーモデル</span><span class="sxs-lookup"><span data-stu-id="f7de2-107">Group Call Pickup User Model</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f7de2-108">指標</span><span class="sxs-lookup"><span data-stu-id="f7de2-108">Metric</span></span></th>
<th><span data-ttu-id="f7de2-109">フロントエンドプールあたり (8 個のフロントエンドサーバーを含む)</span><span class="sxs-lookup"><span data-stu-id="f7de2-109">Per Front End pool (with 8 Front End Servers)</span></span></th>
<th><span data-ttu-id="f7de2-110">Standard Edition サーバーごと</span><span class="sxs-lookup"><span data-stu-id="f7de2-110">Per Standard Edition server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f7de2-111">グループあたりの推奨ユーザー数</span><span class="sxs-lookup"><span data-stu-id="f7de2-111">Recommended number of users per group</span></span></p></td>
<td><p><span data-ttu-id="f7de2-112">50</span><span class="sxs-lookup"><span data-stu-id="f7de2-112">50</span></span></p></td>
<td><p><span data-ttu-id="f7de2-113">50</span><span class="sxs-lookup"><span data-stu-id="f7de2-113">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f7de2-114">推奨グループ数</span><span class="sxs-lookup"><span data-stu-id="f7de2-114">Recommended number of groups</span></span></p></td>
<td><p><span data-ttu-id="f7de2-115">500</span><span class="sxs-lookup"><span data-stu-id="f7de2-115">500</span></span></p></td>
<td><p><span data-ttu-id="f7de2-116">60</span><span class="sxs-lookup"><span data-stu-id="f7de2-116">60</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f7de2-117">プールあたりの、グループ通話ピックアップが可能な最大ユーザー数</span><span class="sxs-lookup"><span data-stu-id="f7de2-117">Maximum number of users per pool enabled for Group Call Pickup</span></span></p></td>
<td><p><span data-ttu-id="f7de2-118">25,000</span><span class="sxs-lookup"><span data-stu-id="f7de2-118">25,000</span></span></p></td>
<td><p><span data-ttu-id="f7de2-119">3,000</span><span class="sxs-lookup"><span data-stu-id="f7de2-119">3,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f7de2-120">プールおよび分あたりの、グループ通話ピックアップが可能な総ユーザー数に対する着信通話数の最大比率</span><span class="sxs-lookup"><span data-stu-id="f7de2-120">Maximum rate of incoming calls to total users enabled for Group Call Pickup per pool per minute</span></span></p></td>
<td><p><span data-ttu-id="f7de2-121">500</span><span class="sxs-lookup"><span data-stu-id="f7de2-121">500</span></span></p></td>
<td><p><span data-ttu-id="f7de2-122">60</span><span class="sxs-lookup"><span data-stu-id="f7de2-122">60</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f7de2-123">プールおよび分あたりの、グループ通話ピックアップによって取得される通話数の最大比率</span><span class="sxs-lookup"><span data-stu-id="f7de2-123">Maximum rate of calls retrieved by users with Group Call Pickup per pool per minute</span></span></p></td>
<td><p><span data-ttu-id="f7de2-124">200</span><span class="sxs-lookup"><span data-stu-id="f7de2-124">200</span></span></p></td>
<td><p><span data-ttu-id="f7de2-125">50</span><span class="sxs-lookup"><span data-stu-id="f7de2-125">25</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <UL>
> <LI>
> <P><span data-ttu-id="f7de2-126">フロントエンドサーバーの数が8個以下のフロントエンドプールの場合は、数値を直線的に計算します。</span><span class="sxs-lookup"><span data-stu-id="f7de2-126">For Front End pools that have fewer than eight Front End Servers, calculate the metrics linearly.</span></span> <span data-ttu-id="f7de2-127">たとえば、フロントエンドプールに1つのフロントエンドサーバーがある場合は、テーブルに表示されている値の1/8 としての最大読み込みを計算します。</span><span class="sxs-lookup"><span data-stu-id="f7de2-127">For example, if your Front End pool has one Front End Server, calculate the maximum load as 1/8 of the values shown in the table.</span></span></P>
> <LI>
> <P><span data-ttu-id="f7de2-128">プールあたりのユーザー数の上限を超えていない限り、1つのグループに対して推奨されるユーザー数とグループ数を増減できます。</span><span class="sxs-lookup"><span data-stu-id="f7de2-128">You can increase or decrease the recommended number of users per group and number of groups as long as you do not exceed the maximum number of users per pool.</span></span> <span data-ttu-id="f7de2-129">たとえば、グループ通話のピックアップ用に有効になっているユーザーの数がユーザーモデルの最大数 (120 グループの場合は、グループ通話のピックアップでは3000ユーザー) のままであるため、標準エディションのサーバーではグループあたり25人のユーザーを持つ120グループを持つことができます。</span><span class="sxs-lookup"><span data-stu-id="f7de2-129">For example, your Standard Edition server can have 120 groups with 25 users per group because the number of users enabled for Group Call Pickup is still within the user model maximum (that is, 120 groups times 25 users is 3,000 users enabled for Group Call Pickup).</span></span></P></LI></UL>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

