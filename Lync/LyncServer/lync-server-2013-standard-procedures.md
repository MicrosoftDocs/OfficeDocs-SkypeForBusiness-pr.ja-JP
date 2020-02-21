---
title: 'Lync Server 2013: 標準手順'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Standard procedures
ms:assetid: 1b45d610-9840-4568-89e5-004ba31a15cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720323(v=OCS.15)
ms:contentKeyID: 63969581
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 270261ea61aa8d2b0b8f1d3bbb97257ddd7a17e2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181750"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="standard-procedures-in-lync-server-2013"></a><span data-ttu-id="10eae-102">Lync Server 2013 の標準手順</span><span class="sxs-lookup"><span data-stu-id="10eae-102">Standard procedures in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="10eae-103">_**トピックの最終更新日:** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="10eae-103">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="10eae-104">組織で必要な標準手順を定義し、それらを実行する方法については、いくつかのリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="10eae-104">Several resources can help you define what standard procedures are required in the organization, and how to perform them.</span></span> <span data-ttu-id="10eae-105">各組織は固有のものなので、日常の要件に合わせてこれらのリソースをさらにカスタマイズして適応する必要がある場合があります。標準的な運用手順の変更、およびドキュメントを改訂する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="10eae-105">Because each organization is unique, you may have to additionally customize and adapt these resources to suit everyday requirements.Standard operational procedures change, and documentation occasionally has to be revised.</span></span> <span data-ttu-id="10eae-106">変更が行われると、Microsoft 運用フレームワークのサービス管理機能で定義されている変更管理プロセスによって、管理タスクの実行方法やタイミングにどのような影響が生じる可能性があるかを特定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="10eae-106">As changes are made, the change management process, as defined in the Service Management Functions of the Microsoft Operational Framework, should identify how each change is likely to affect how and when administrative tasks are performed.</span></span> <span data-ttu-id="10eae-107">変更管理機能を使用して、手続きのドキュメントを更新し、制御します。運用タスクは、日単位、週単位、月単位、および必要に応じて、管理可能なワークロードに分けて行うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="10eae-107">Use the change management function to update and control the procedural documentation.We recommend that operational tasks be separated into manageable workloads, where tasks are performed on a daily, weekly, monthly, and as-needed basis.</span></span> <span data-ttu-id="10eae-108">日常のタスクでは、システムの機能にとって非常に重要な側面に焦点を当てることができます。また、月単位のタスクでは、システムの長期的な正常性を確保することに重点を置いています。</span><span class="sxs-lookup"><span data-stu-id="10eae-108">Daily tasks would focus efforts on aspects that are very important to the functioning of a system and monthly tasks would focus more on ensuring the long-term health of a system.</span></span> <span data-ttu-id="10eae-109">実行する必要があるタスクは、次のカテゴリに分けることができます。</span><span class="sxs-lookup"><span data-stu-id="10eae-109">The tasks that must be performed can be separated into the following categories:</span></span>

  - [<span data-ttu-id="10eae-110">Lync Server 2013 の毎日のタスク</span><span class="sxs-lookup"><span data-stu-id="10eae-110">Daily tasks in Lync Server 2013</span></span>](lync-server-2013-daily-tasks.md)

  - [<span data-ttu-id="10eae-111">Lync Server 2013 の週次タスク</span><span class="sxs-lookup"><span data-stu-id="10eae-111">Weekly tasks in Lync Server 2013</span></span>](lync-server-2013-weekly-tasks.md)

  - [<span data-ttu-id="10eae-112">Lync Server 2013 の月次タスク</span><span class="sxs-lookup"><span data-stu-id="10eae-112">Monthly tasks in Lync Server 2013</span></span>](lync-server-2013-monthly-tasks.md)

  - [<span data-ttu-id="10eae-113">Lync Server 2013 で必要になるタスク</span><span class="sxs-lookup"><span data-stu-id="10eae-113">As-needed tasks in Lync Server 2013</span></span>](lync-server-2013-as-needed-tasks.md)

<span data-ttu-id="10eae-114">運用管理のためのドキュメントを準備するときは、チェックリストを使用して、必要なタスクが適切なタイミングで実行されることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="10eae-114">When preparing documentation for operations management, use checklists to help ensure that the required tasks are performed at the appropriate time.</span></span> <span data-ttu-id="10eae-115">操作チェックリストを準備する方法の詳細については、「操作チェックリスト」にあるサンプルチェックリストを参照してください。</span><span class="sxs-lookup"><span data-stu-id="10eae-115">For detailed information about how to prepare operations checklists, see the sample checklists located in Operations Checklists.</span></span>

<span data-ttu-id="10eae-116">多くの場合、変更管理はシステム管理の終了時に引き継がれます。</span><span class="sxs-lookup"><span data-stu-id="10eae-116">Frequently, change management takes over where system administration finishes.</span></span> <span data-ttu-id="10eae-117">タスクが標準的な手順でカバーされている場合は、システム管理機能の一部です。</span><span class="sxs-lookup"><span data-stu-id="10eae-117">If a task is covered by a standard procedure, it is part of the system administration function.</span></span> <span data-ttu-id="10eae-118">タスクの標準手順がない場合は、変更管理機能を使用して処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="10eae-118">If there is no standard procedure for a task, it should be handled by using the change management function.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="10eae-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="10eae-119">See Also</span></span>


[<span data-ttu-id="10eae-120">日毎のタスクチェックリスト</span><span class="sxs-lookup"><span data-stu-id="10eae-120">Daily task checklist</span></span>](lync-server-2013-operations-checklists.md)  
[<span data-ttu-id="10eae-121">毎週のタスクチェックリスト</span><span class="sxs-lookup"><span data-stu-id="10eae-121">Weekly task checklist</span></span>](lync-server-2013-operations-checklists.md)  
[<span data-ttu-id="10eae-122">月次タスクチェックリスト</span><span class="sxs-lookup"><span data-stu-id="10eae-122">Monthly task checklist</span></span>](lync-server-2013-operations-checklists.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

