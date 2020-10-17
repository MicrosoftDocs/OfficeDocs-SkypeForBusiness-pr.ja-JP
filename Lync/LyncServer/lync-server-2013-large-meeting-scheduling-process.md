---
title: 'Lync Server 2013: 大規模な会議のスケジュール処理'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Large-meeting scheduling process
ms:assetid: de267458-885f-4176-a8d7-1a218e67640e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205334(v=OCS.15)
ms:contentKeyID: 48185639
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4fb2de8387abb48ad67b8a39bc1ac3ffc353a9b7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514014"
---
# <a name="large-meeting-scheduling-process-in-lync-server-2013"></a><span data-ttu-id="38cb4-102">Lync Server 2013 での大規模な会議のスケジューリングプロセス</span><span class="sxs-lookup"><span data-stu-id="38cb4-102">Large-meeting scheduling process in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="38cb4-103">_**トピックの最終更新日:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="38cb4-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="38cb4-104">専用の大規模な会議プールでは、一度に1つの大規模な会議のみがサポートされるので、大規模な会議の競合を防ぐために、大規模な会議のスケジュールプロセスを実装することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="38cb4-104">Because only one large meeting at a time is supported on the dedicated large meeting pool, we recommend implementing a large meeting scheduling process to help prevent large meeting conflicts.</span></span> <span data-ttu-id="38cb4-105">このようなスケジュールプロセスの目的は、大規模な会議の設定を容易にすることです。</span><span class="sxs-lookup"><span data-stu-id="38cb4-105">The purpose of such the scheduling process is to facilitate setting up large meetings.</span></span> <span data-ttu-id="38cb4-106">このような機能は、Lync Server または Lync Server クライアントによって直接提供されるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="38cb4-106">Such capability is not provided directly by Lync Server or Lync Server clients.</span></span> <span data-ttu-id="38cb4-107">このようなプロセスを実装する方法の1つとして、組織のサポートチームのチケットシステムを使用する方法があります (利用可能な場合)。</span><span class="sxs-lookup"><span data-stu-id="38cb4-107">One way to implement such a process is to use your organization’s support team’s ticketing system, if available.</span></span>

<span data-ttu-id="38cb4-108">大規模な会議の開催者の場合、大規模な会議のスケジュールを設定するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="38cb4-108">For organizers of large meetings, scheduling a large meeting involves completing the following steps:</span></span>

1.  <span data-ttu-id="38cb4-109">会議の開催者または代理人は、発表者のリストに加えて、今後の会議の時間、期間、およびサイズを決定します。</span><span class="sxs-lookup"><span data-stu-id="38cb4-109">The meeting organizer or delegate determines the time, duration, and size of an upcoming meeting, in addition to the list of presenters.</span></span> <span data-ttu-id="38cb4-110">予定されている会議のサイズが250ユーザーを超えている場合、またはユーザーが250ユーザーより少ない会議に最高のユーザー環境を確保する場合は、開催者または代理人が大規模会議の要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="38cb4-110">If the anticipated meeting size exceeds 250 users or to ensure the best user experience for a meeting of fewer than 250 users, the organizer or the delegate submits a request for a large meeting.</span></span>

2.  <span data-ttu-id="38cb4-111">スケジュールスタッフは、要求された日付と時刻が利用可能かどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="38cb4-111">The scheduling staff checks to see whether the requested date and time is available.</span></span> <span data-ttu-id="38cb4-112">一度に専用プールに対して1つの大規模な会議のみをサポートしているため、スケジュール担当者は、要求された日時に別の会議がスケジュールされているかどうかを確認するために、大規模な会議予定表をチェックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="38cb4-112">Since we support only a single large meeting on the dedicated pool at a time, the scheduling staff needs to check the large-meeting calendar to determine whether there is another meeting scheduled for the requested date and time.</span></span> <span data-ttu-id="38cb4-113">要求された時間が利用可能な場合、スタッフは会議出席依頼を承認します。</span><span class="sxs-lookup"><span data-stu-id="38cb4-113">If the requested time is available, the staff approves the meeting request.</span></span>

3.  <span data-ttu-id="38cb4-114">要求が承認された場合、(専用プールの資格情報を使用する) スケジュール担当者は Lync 2013 用オンラインミーティングアドインを使用して、専用の大規模な会議プールで会議を設定します。</span><span class="sxs-lookup"><span data-stu-id="38cb4-114">If the request is approved, the scheduling staff (using credentials on the dedicated pool) uses Online Meeting Add-in for Lync 2013 with Outlook to set up a meeting on the dedicated large-meeting pool.</span></span> <span data-ttu-id="38cb4-115">会議への参加に使用される URL は、承認通知の一部として依頼者に提供されます。</span><span class="sxs-lookup"><span data-stu-id="38cb4-115">The URL to be used to join the meeting is provided to the requester as part of the approval notice.</span></span>

4.  <span data-ttu-id="38cb4-116">会議の開催者または代理人は、Outlook を使用して今後の会議をスケジュールし、会議出席依頼に参加するための URL を追加します。</span><span class="sxs-lookup"><span data-stu-id="38cb4-116">The meeting organizer or delegate uses Outlook to schedule the upcoming meeting, adding the URL for joining the meeting to the meeting invitation.</span></span> <span data-ttu-id="38cb4-117">会議の開催者または代理人は、招待されるユーザーを指定し、会議出席依頼を送信します。</span><span class="sxs-lookup"><span data-stu-id="38cb4-117">The meeting organizer or delegate then specifies the users to be invited and sends out the meeting invitation.</span></span>
    
    <span data-ttu-id="38cb4-118">次の図は、大規模な会議をスケジュールするための一般的な要求および承認のワークフローを示しています。</span><span class="sxs-lookup"><span data-stu-id="38cb4-118">The following figure illustrates a typical request and approval workflow for scheduling large meetings.</span></span>
    
    <span data-ttu-id="38cb4-119">![5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d](images/JJ205334.5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d(OCS.15).jpg "5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d")</span><span class="sxs-lookup"><span data-stu-id="38cb4-119">![5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d](images/JJ205334.5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d(OCS.15).jpg "5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d")</span></span>  

</div>

<span> </span>

</div>

</div>

</div>

