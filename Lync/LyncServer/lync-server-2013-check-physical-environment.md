---
title: 'Lync Server 2013: 物理環境を確認する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Performing physical environmental checks
ms:assetid: 153aee5e-3adf-4dbf-bf41-53e4fba51fb0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720558(v=OCS.15)
ms:contentKeyID: 63969582
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 07335046dc4b37d0e5327ded0a12293657f5fe43
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840578"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="performing-physical-environmental-checks"></a><span data-ttu-id="c3bd4-102">物理的な環境のチェックを実行する</span><span class="sxs-lookup"><span data-stu-id="c3bd4-102">Performing physical environmental checks</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c3bd4-103">_**最終更新日:** 2014-04-30_</span><span class="sxs-lookup"><span data-stu-id="c3bd4-103">_**Topic Last Modified:** 2014-04-30_</span></span>

<span data-ttu-id="c3bd4-104">Lync Server 2013 展開のパフォーマンス、可用性、機能を確認する前に、物理環境を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3bd4-104">Before checking the performance, availability, and functionality of the Lync Server 2013 deployment, you should check the physical environment.</span></span> <span data-ttu-id="c3bd4-105">たとえば、サーバーの室温の温度が下げられているか、ネットワークケーブルを交換しなければならない場合があります。</span><span class="sxs-lookup"><span data-stu-id="c3bd4-105">For example, the server room temperature might have to be lowered, or a network cable might have to be replaced.</span></span> <span data-ttu-id="c3bd4-106">最善の結果を得るには、次の物理的な環境検査を実行します。</span><span class="sxs-lookup"><span data-stu-id="c3bd4-106">For best results, perform the following physical environmental inspections:</span></span>

  - <span data-ttu-id="c3bd4-107">**物理セキュリティ**   は、ロック、ドア、アクセス制限されたルームなどの物理的なセキュリティ保護を保護する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3bd4-107">**Physical security measures**   Physical security protection such as locks, doors, and restricted-access rooms must be secured.</span></span> <span data-ttu-id="c3bd4-108">許可されていない強制された入力と機器の破損を確認します。</span><span class="sxs-lookup"><span data-stu-id="c3bd4-108">Check for any unauthorized and forced entries and signs of equipment damage.</span></span>

  - <span data-ttu-id="c3bd4-109">**温度と湿度**   の高温、低品質の気流、湿度は、ハードウェアコンポーネントのオーバーヒートを引き起こす可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c3bd4-109">**Temperature and humidity**   High temperature, poor air flow, and humidity can cause hardware components to overheat.</span></span> <span data-ttu-id="c3bd4-110">温度と湿度をチェックして、加熱や空調などの環境システムがハードウェアの製造元の仕様に従って許容条件を満たしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c3bd4-110">Check temperature and humidity to help to make sure that the environmental systems such as heating and air conditioning can maintain acceptable conditions and function within the hardware manufacturer's specifications.</span></span> <span data-ttu-id="c3bd4-111">新しい機器が最近インストールされた場合は、両サーバー間の気流フローが unimpeded であり、製造元の仕様を満たしていることも確認してください。</span><span class="sxs-lookup"><span data-stu-id="c3bd4-111">When new equipment has recently been installed, also check that air flow both to and from the servers is unimpeded and meets manufacturer spec.</span></span>

  - <span data-ttu-id="c3bd4-112">**デバイスとコンポーネント**   Lync Server 2013 組織は、機能している物理ネットワークと関連ハードウェアに依存しています。</span><span class="sxs-lookup"><span data-stu-id="c3bd4-112">**Devices and components**   The Lync Server 2013 organization relies on a functioning physical network and related hardware.</span></span> <span data-ttu-id="c3bd4-113">ルーター、スイッチ、ハブ、物理ケーブル、コネクタが動作可能であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c3bd4-113">Make sure that routers, switches, hubs, physical cables, and connectors are operational.</span></span>

<span data-ttu-id="c3bd4-114">これらのチェックを行う方法についての詳細は、インストールサイトと選択されたサーバーハードウェアによって大きく異なります。</span><span class="sxs-lookup"><span data-stu-id="c3bd4-114">The specifics on how to perform these checks will depend greatly on your installation site and the server hardware that was chosen.</span></span> <span data-ttu-id="c3bd4-115">このチェックを初めて実行するときは、ハードウェアのドキュメントを参照し、後で参照するために必要なパラメーターをメモしてください。</span><span class="sxs-lookup"><span data-stu-id="c3bd4-115">The first time that you perform this check, refer to the hardware documentation and note the desired parameters for future reference.</span></span>

### <a name="desired-server-space-environment"></a><span data-ttu-id="c3bd4-116">必要なサーバースペース環境</span><span class="sxs-lookup"><span data-stu-id="c3bd4-116">Desired server space environment</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c3bd4-117">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c3bd4-117">Parameter</span></span></th>
<th><span data-ttu-id="c3bd4-118">目的の値または範囲</span><span class="sxs-lookup"><span data-stu-id="c3bd4-118">Desired value or range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c3bd4-119">危険</span><span class="sxs-lookup"><span data-stu-id="c3bd4-119">Temperature</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3bd4-120">湿気</span><span class="sxs-lookup"><span data-stu-id="c3bd4-120">Humidity</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3bd4-121">サーバーの正面</span><span class="sxs-lookup"><span data-stu-id="c3bd4-121">Front of server faces</span></span></p></td>
<td><p><span data-ttu-id="c3bd4-122">ホット通路/低通路</span><span class="sxs-lookup"><span data-stu-id="c3bd4-122">Hot aisle / cold aisle</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3bd4-123">Unimpeded 排気クリアランス</span><span class="sxs-lookup"><span data-stu-id="c3bd4-123">Unimpeded exhaust clearance</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

