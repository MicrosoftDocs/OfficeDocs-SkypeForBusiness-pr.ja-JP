---
title: 'Lync Server 2013: 物理環境の確認'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Performing physical environmental checks
ms:assetid: 153aee5e-3adf-4dbf-bf41-53e4fba51fb0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720558(v=OCS.15)
ms:contentKeyID: 63969582
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 17905a8cd379e5fe2b97b494a00b37a181541900
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151077"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="performing-physical-environmental-checks"></a><span data-ttu-id="a0062-102">物理的な環境のチェックの実行</span><span class="sxs-lookup"><span data-stu-id="a0062-102">Performing physical environmental checks</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a0062-103">_**トピックの最終更新日:** 2014-04-30_</span><span class="sxs-lookup"><span data-stu-id="a0062-103">_**Topic Last Modified:** 2014-04-30_</span></span>

<span data-ttu-id="a0062-104">Lync Server 2013 展開のパフォーマンス、可用性、および機能を確認する前に、物理環境を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a0062-104">Before checking the performance, availability, and functionality of the Lync Server 2013 deployment, you should check the physical environment.</span></span> <span data-ttu-id="a0062-105">たとえば、サーバーの室温を下げる必要がある場合や、ネットワークケーブルを交換する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="a0062-105">For example, the server room temperature might have to be lowered, or a network cable might have to be replaced.</span></span> <span data-ttu-id="a0062-106">最良の結果を得るには、次の物理的な環境検査を実行します。</span><span class="sxs-lookup"><span data-stu-id="a0062-106">For best results, perform the following physical environmental inspections:</span></span>

  - <span data-ttu-id="a0062-107">**物理的なセキュリティ対策**   ロック、ドア、制限付きアクセスルームなどの物理的なセキュリティ保護をセキュリティで保護する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a0062-107">**Physical security measures**   Physical security protection such as locks, doors, and restricted-access rooms must be secured.</span></span> <span data-ttu-id="a0062-108">許可されていない強制のエントリと機器の損傷の兆候を確認します。</span><span class="sxs-lookup"><span data-stu-id="a0062-108">Check for any unauthorized and forced entries and signs of equipment damage.</span></span>

  - <span data-ttu-id="a0062-109">**温度と湿度**   の高い気温、通気流量、および湿度は、ハードウェアコンポーネントのオーバーヒートを引き起こす可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a0062-109">**Temperature and humidity**   High temperature, poor air flow, and humidity can cause hardware components to overheat.</span></span> <span data-ttu-id="a0062-110">温度と湿度をチェックして、暖房や空調などの環境システムが、ハードウェア製造元の仕様の範囲内で許容できる条件と機能を維持できることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="a0062-110">Check temperature and humidity to help to make sure that the environmental systems such as heating and air conditioning can maintain acceptable conditions and function within the hardware manufacturer's specifications.</span></span> <span data-ttu-id="a0062-111">新しい装置を最近インストールした場合は、サーバーとの間の気流フローが unimpeded で、製造元の仕様を満たしていることも確認してください。</span><span class="sxs-lookup"><span data-stu-id="a0062-111">When new equipment has recently been installed, also check that air flow both to and from the servers is unimpeded and meets manufacturer spec.</span></span>

  - <span data-ttu-id="a0062-112">**デバイスとコンポーネント**   Lync Server 2013 組織は、機能している物理ネットワークと関連するハードウェアに依存しています。</span><span class="sxs-lookup"><span data-stu-id="a0062-112">**Devices and components**   The Lync Server 2013 organization relies on a functioning physical network and related hardware.</span></span> <span data-ttu-id="a0062-113">ルーター、スイッチ、ハブ、物理ケーブル、およびコネクタが動作していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="a0062-113">Make sure that routers, switches, hubs, physical cables, and connectors are operational.</span></span>

<span data-ttu-id="a0062-114">これらのチェックを実行する方法についての詳細は、インストールサイトと選択したサーバーハードウェアに大きく依存します。</span><span class="sxs-lookup"><span data-stu-id="a0062-114">The specifics on how to perform these checks will depend greatly on your installation site and the server hardware that was chosen.</span></span> <span data-ttu-id="a0062-115">このチェックを初めて実行するときは、ハードウェアのドキュメントを参照し、後で参照するために必要なパラメーターを確認してください。</span><span class="sxs-lookup"><span data-stu-id="a0062-115">The first time that you perform this check, refer to the hardware documentation and note the desired parameters for future reference.</span></span>

### <a name="desired-server-space-environment"></a><span data-ttu-id="a0062-116">必要なサーバー容量環境</span><span class="sxs-lookup"><span data-stu-id="a0062-116">Desired server space environment</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a0062-117">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a0062-117">Parameter</span></span></th>
<th><span data-ttu-id="a0062-118">目的の値または範囲</span><span class="sxs-lookup"><span data-stu-id="a0062-118">Desired value or range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a0062-119">温度</span><span class="sxs-lookup"><span data-stu-id="a0062-119">Temperature</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0062-120">湿気</span><span class="sxs-lookup"><span data-stu-id="a0062-120">Humidity</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0062-121">サーバーフェイスの正面</span><span class="sxs-lookup"><span data-stu-id="a0062-121">Front of server faces</span></span></p></td>
<td><p><span data-ttu-id="a0062-122">ホット通路/コールド通路</span><span class="sxs-lookup"><span data-stu-id="a0062-122">Hot aisle / cold aisle</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0062-123">Unimpeded 排気認可上限</span><span class="sxs-lookup"><span data-stu-id="a0062-123">Unimpeded exhaust clearance</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

