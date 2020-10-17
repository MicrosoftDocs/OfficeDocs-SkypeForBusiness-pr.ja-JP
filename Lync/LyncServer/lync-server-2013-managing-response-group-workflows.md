---
title: 'Lync Server 2013: 応答グループのワークフローの管理'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing Response Group workflows
ms:assetid: 42cfccdd-2844-4875-b4e3-813e1df15f08
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520986(v=OCS.15)
ms:contentKeyID: 48183974
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 54f24b79c9b06beaae2c0964b662e62f330a5061
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507224"
---
# <a name="managing-response-group-workflows-in-lync-server-2013"></a><span data-ttu-id="6dd79-102">Lync Server 2013 での応答グループワークフローの管理</span><span class="sxs-lookup"><span data-stu-id="6dd79-102">Managing Response Group workflows in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6dd79-103">_**トピックの最終更新日:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="6dd79-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="6dd79-104">応答グループワークフローは、エージェントが通話に応答する時間に電話が応答するまでの通話の動作を定義します。</span><span class="sxs-lookup"><span data-stu-id="6dd79-104">A Response Group workflow defines the behavior of a call from the time that the phone rings to the time that an agent answers the call.</span></span> <span data-ttu-id="6dd79-105">ワークフローには、キューやルーティングの情報およびハント グループまたは対話型音声応答 (IVR) 情報も含まれます。</span><span class="sxs-lookup"><span data-stu-id="6dd79-105">The workflow includes queue and routing information, and includes either hunt group or interactive voice response (IVR) information.</span></span>

<span data-ttu-id="6dd79-106">このセクションのトピックでは、IVR ワークフロー設計のベスト プラクティスを特定し、カスタマイズされた営業時間と休日セットを作成する方法、ワークフローを作成または変更する方法、およびワークグループを削除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6dd79-106">Topics in this section identify best practices for designing IVR workflows, and explain how to create customized business hours and holiday sets, how to create or modify workflows, and how to delete workgroups.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="6dd79-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="6dd79-107">In This Section</span></span>

  - [<span data-ttu-id="6dd79-108">Lync Server 2013 での対話型音声応答呼び出しフローの設計</span><span class="sxs-lookup"><span data-stu-id="6dd79-108">Design interactive voice response call flows in Lync Server 2013</span></span>](lync-server-2013-design-interactive-voice-response-call-flows.md)

  - [<span data-ttu-id="6dd79-109">オプションLync Server 2013 で応答グループの営業時間を定義する</span><span class="sxs-lookup"><span data-stu-id="6dd79-109">(Optional) Define Response Group business hours in Lync Server 2013</span></span>](lync-server-2013-optional-define-response-group-business-hours.md)

  - [<span data-ttu-id="6dd79-110">オプションLync Server 2013 で応答グループの休日セットを定義する</span><span class="sxs-lookup"><span data-stu-id="6dd79-110">(Optional) Define Response Group holiday sets in Lync Server 2013</span></span>](lync-server-2013-optional-define-response-group-holiday-sets.md)

  - [<span data-ttu-id="6dd79-111">Lync Server 2013 でのワークフローの作成または変更</span><span class="sxs-lookup"><span data-stu-id="6dd79-111">Create or modify a workflow in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-workflow.md)

  - [<span data-ttu-id="6dd79-112">Lync Server 2013 でワークフローを削除する</span><span class="sxs-lookup"><span data-stu-id="6dd79-112">Delete a workflow in Lync Server 2013</span></span>](lync-server-2013-delete-a-workflow.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

