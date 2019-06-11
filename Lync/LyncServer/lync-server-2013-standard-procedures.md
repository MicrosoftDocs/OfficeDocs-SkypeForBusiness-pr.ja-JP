---
title: 'Lync Server 2013: 標準的な手順'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Standard procedures
ms:assetid: 1b45d610-9840-4568-89e5-004ba31a15cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720323(v=OCS.15)
ms:contentKeyID: 63969581
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0ac1d42075f48b780a96f9ca7ad8b831379b5187
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848668"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="standard-procedures-in-lync-server-2013"></a><span data-ttu-id="23c5f-102">Lync Server 2013 の標準手順</span><span class="sxs-lookup"><span data-stu-id="23c5f-102">Standard procedures in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="23c5f-103">_**最終更新日:** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="23c5f-103">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="23c5f-104">いくつかのリソースを使って、組織に必要な標準手順とその実行方法を定義できます。</span><span class="sxs-lookup"><span data-stu-id="23c5f-104">Several resources can help you define what standard procedures are required in the organization, and how to perform them.</span></span> <span data-ttu-id="23c5f-105">各組織は固有のものであるため、日常的な要件に合わせて、これらのリソースをさらにカスタマイズして、適応することが必要な場合があります。標準的な操作手順の変更とドキュメントの変更が必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="23c5f-105">Because each organization is unique, you may have to additionally customize and adapt these resources to suit everyday requirements.Standard operational procedures change, and documentation occasionally has to be revised.</span></span> <span data-ttu-id="23c5f-106">変更が加えられると、Microsoft の運用フレームワークのサービス管理機能で定義されている変更管理プロセスによって、管理タスクの実行方法とタイミングにどのような影響が及ぶ可能性があるかを特定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="23c5f-106">As changes are made, the change management process, as defined in the Service Management Functions of the Microsoft Operational Framework, should identify how each change is likely to affect how and when administrative tasks are performed.</span></span> <span data-ttu-id="23c5f-107">変更管理関数を使用して、手続きのドキュメントを更新して制御します。タスクを日常的、毎週、毎月、必要に応じて実行する管理可能なワークロードに分割することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="23c5f-107">Use the change management function to update and control the procedural documentation.We recommend that operational tasks be separated into manageable workloads, where tasks are performed on a daily, weekly, monthly, and as-needed basis.</span></span> <span data-ttu-id="23c5f-108">日常的な作業では、システムの機能にとって非常に重要な側面に重点を置いています。また、月次のタスクでは、システムの長期の正常性を確保することに重点を置いています。</span><span class="sxs-lookup"><span data-stu-id="23c5f-108">Daily tasks would focus efforts on aspects that are very important to the functioning of a system and monthly tasks would focus more on ensuring the long-term health of a system.</span></span> <span data-ttu-id="23c5f-109">実行する必要があるタスクは、次のカテゴリに分けることができます。</span><span class="sxs-lookup"><span data-stu-id="23c5f-109">The tasks that must be performed can be separated into the following categories:</span></span>

  - [<span data-ttu-id="23c5f-110">Lync Server 2013 での日次タスク</span><span class="sxs-lookup"><span data-stu-id="23c5f-110">Daily tasks in Lync Server 2013</span></span>](lync-server-2013-daily-tasks.md)

  - [<span data-ttu-id="23c5f-111">Lync Server 2013 での週次タスク</span><span class="sxs-lookup"><span data-stu-id="23c5f-111">Weekly tasks in Lync Server 2013</span></span>](lync-server-2013-weekly-tasks.md)

  - [<span data-ttu-id="23c5f-112">Lync Server 2013 の月次タスク</span><span class="sxs-lookup"><span data-stu-id="23c5f-112">Monthly tasks in Lync Server 2013</span></span>](lync-server-2013-monthly-tasks.md)

  - [<span data-ttu-id="23c5f-113">Lync Server 2013 での必要なタスク</span><span class="sxs-lookup"><span data-stu-id="23c5f-113">As-needed tasks in Lync Server 2013</span></span>](lync-server-2013-as-needed-tasks.md)

<span data-ttu-id="23c5f-114">運用管理のためのドキュメントを準備するときに、チェックリストを使用して、必要なタスクが適切なタイミングで実行されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="23c5f-114">When preparing documentation for operations management, use checklists to help ensure that the required tasks are performed at the appropriate time.</span></span> <span data-ttu-id="23c5f-115">操作のチェックリストを準備する方法の詳細については、「操作のチェックリスト」にあるサンプルチェックリストを参照してください。</span><span class="sxs-lookup"><span data-stu-id="23c5f-115">For detailed information about how to prepare operations checklists, see the sample checklists located in Operations Checklists.</span></span>

<span data-ttu-id="23c5f-116">多くの場合、変更管理はシステム管理が終了する場所に引き継がれます。</span><span class="sxs-lookup"><span data-stu-id="23c5f-116">Frequently, change management takes over where system administration finishes.</span></span> <span data-ttu-id="23c5f-117">タスクが標準的な手順でカバーされている場合は、システム管理機能の一部です。</span><span class="sxs-lookup"><span data-stu-id="23c5f-117">If a task is covered by a standard procedure, it is part of the system administration function.</span></span> <span data-ttu-id="23c5f-118">タスクの標準的な手順がない場合は、変更管理機能を使用して処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="23c5f-118">If there is no standard procedure for a task, it should be handled by using the change management function.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="23c5f-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="23c5f-119">See Also</span></span>


[<span data-ttu-id="23c5f-120">日次タスク チェックリスト</span><span class="sxs-lookup"><span data-stu-id="23c5f-120">Daily task checklist</span></span>](lync-server-2013-operations-checklists.md)  
[<span data-ttu-id="23c5f-121">毎週のタスクチェックリスト</span><span class="sxs-lookup"><span data-stu-id="23c5f-121">Weekly task checklist</span></span>](lync-server-2013-operations-checklists.md)  
[<span data-ttu-id="23c5f-122">毎月のタスクチェックリスト</span><span class="sxs-lookup"><span data-stu-id="23c5f-122">Monthly task checklist</span></span>](lync-server-2013-operations-checklists.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

