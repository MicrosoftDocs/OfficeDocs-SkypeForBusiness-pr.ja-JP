---
title: 'Lync Server 2013: 応答グループの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Response Group
ms:assetid: c56db929-cb21-4af0-be3f-c8f807b78a5a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205249(v=OCS.15)
ms:contentKeyID: 48185359
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c4d12d1ee21cfa5e480dea52a0de9f89b250715c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840179"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-response-group-in-lync-server-2013"></a><span data-ttu-id="5bf2e-102">Lync Server 2013 での応答グループの構成</span><span class="sxs-lookup"><span data-stu-id="5bf2e-102">Configuring Response Group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5bf2e-103">_**最終更新日:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="5bf2e-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="5bf2e-104">[応答グループ] は、ヘルプデスクや顧客サービスデスクなどの*エージェント*と呼ばれる、着信通話をルーティングしてキューに登録するエンタープライズ voip 機能です。</span><span class="sxs-lookup"><span data-stu-id="5bf2e-104">Response Group is an Enterprise Voice feature that routes and queues incoming calls to groups of people, called *agents*, such as a help desk or a customer service desk.</span></span>

<span data-ttu-id="5bf2e-105">エンタープライズボイスの展開時に、応答グループに必要なコンポーネントが、フロントエンドサーバーまたは Standard Edition サーバーにインストールされ、自動的に有効になります。</span><span class="sxs-lookup"><span data-stu-id="5bf2e-105">The components that Response Group requires are installed and enabled automatically on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="5bf2e-106">ユーザーが応答グループを利用できるようにするには、エージェントグループ、[キュー]、[ワークフロー] を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5bf2e-106">To make Response Group available to users, you must configure agent groups, then queues, and then workflows.</span></span> <span data-ttu-id="5bf2e-107">さらに、応答グループ管理者は、既存のワークフローの構成を応答グループマネージャーに委任することができます。これにより、ワークフローと関連するエージェントグループおよびキューを変更して再構成することができます。</span><span class="sxs-lookup"><span data-stu-id="5bf2e-107">Additionally, a Response Group Administrator can delegate configuration of an existing workflow to a Response Group Manager, who can then modify and reconfigure the workflow and its associated agent groups and queues.</span></span>

<span data-ttu-id="5bf2e-108">このセクションでは、Lync Server 2013 応答グループの構成について説明します。</span><span class="sxs-lookup"><span data-stu-id="5bf2e-108">This section guides you through the configuration of Lync Server 2013 Response Group.</span></span> <span data-ttu-id="5bf2e-109">応答グループに関連する計画セクションを既に読んでいて、enterprise Edition サーバーまたはエンタープライズ Voip サーバーを展開していることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="5bf2e-109">It assumes that you have already read the planning sections related to Response Group and have deployed an Enterprise Edition server or a Standard Edition server with Enterprise Voice.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="5bf2e-110">Lync Server 管理シェルを使用した応答グループの作成について詳しくは、「at で<A href="http://go.microsoft.com/fwlink/p/?linkid=204108">http://go.microsoft.com/fwlink/p/?linkId=204108</A>の Lync Server 管理シェルを使用した最初の応答グループの作成」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="5bf2e-110">For details about creating a Response Group by using Lync Server Management Shell, including a sample script, see "Creating Your First Response Group Using Lync Server Management Shell" at <A href="http://go.microsoft.com/fwlink/p/?linkid=204108">http://go.microsoft.com/fwlink/p/?linkId=204108</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="5bf2e-111">このセクション中</span><span class="sxs-lookup"><span data-stu-id="5bf2e-111">In This Section</span></span>

  - [<span data-ttu-id="5bf2e-112">Lync Server 2013 の応答グループ構成のアクセス許可と前提条件</span><span class="sxs-lookup"><span data-stu-id="5bf2e-112">Response Group configuration permissions and prerequisites in Lync Server 2013</span></span>](lync-server-2013-response-group-configuration-permissions-and-prerequisites.md)

  - [<span data-ttu-id="5bf2e-113">Lync Server 2013 の応答グループの展開プロセス</span><span class="sxs-lookup"><span data-stu-id="5bf2e-113">Deployment process for Response Group in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-response-group.md)

  - [<span data-ttu-id="5bf2e-114">Lync Server 2013 でのワークフロー作成のシナリオの概要</span><span class="sxs-lookup"><span data-stu-id="5bf2e-114">Overview of workflow creation scenarios in Lync Server 2013</span></span>](lync-server-2013-overview-of-workflow-creation-scenarios.md)

  - [<span data-ttu-id="5bf2e-115">Lync Server 2013 での応答グループのエージェント グループの作成</span><span class="sxs-lookup"><span data-stu-id="5bf2e-115">Create Response Group agent groups Lync Server 2013</span></span>](lync-server-2013-create-response-group-agent-groups.md)

  - [<span data-ttu-id="5bf2e-116">Lync Server 2013 での応答グループのキューの作成</span><span class="sxs-lookup"><span data-stu-id="5bf2e-116">Create Response Group queues in Lync Server 2013</span></span>](lync-server-2013-create-response-group-queues.md)

  - [<span data-ttu-id="5bf2e-117">省略Lync Server 2013 での応答グループの営業時間の定義</span><span class="sxs-lookup"><span data-stu-id="5bf2e-117">(Optional) Define Response Group business hours in Lync Server 2013</span></span>](lync-server-2013-optional-define-response-group-business-hours.md)

  - [<span data-ttu-id="5bf2e-118">省略Lync Server 2013 で回答グループの休日セットを定義する</span><span class="sxs-lookup"><span data-stu-id="5bf2e-118">(Optional) Define Response Group holiday sets in Lync Server 2013</span></span>](lync-server-2013-optional-define-response-group-holiday-sets.md)

  - [<span data-ttu-id="5bf2e-119">Lync Server 2013 での応答グループのワークフローの作成</span><span class="sxs-lookup"><span data-stu-id="5bf2e-119">Create Response Group workflows in Lync Server 2013</span></span>](lync-server-2013-create-response-group-workflows.md)

  - [<span data-ttu-id="5bf2e-120">省略Lync Server 2013 での応答グループの展開を確認する</span><span class="sxs-lookup"><span data-stu-id="5bf2e-120">(Optional) Verify Response Group deployment in Lync Server 2013</span></span>](lync-server-2013-optional-verify-response-group-deployment.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5bf2e-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="5bf2e-121">See Also</span></span>


[<span data-ttu-id="5bf2e-122">Lync Server 2013 の通話管理機能の計画</span><span class="sxs-lookup"><span data-stu-id="5bf2e-122">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

