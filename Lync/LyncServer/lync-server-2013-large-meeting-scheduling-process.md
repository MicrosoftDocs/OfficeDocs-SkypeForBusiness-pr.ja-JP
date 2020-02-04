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
ms.openlocfilehash: b2cfe26b70db612249ca840c86b41fb3d60db663
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738217"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="large-meeting-scheduling-process-in-lync-server-2013"></a><span data-ttu-id="ba74f-102">Lync Server 2013 での大規模な会議のスケジュールプロセス</span><span class="sxs-lookup"><span data-stu-id="ba74f-102">Large-meeting scheduling process in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ba74f-103">_**最終更新日:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="ba74f-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="ba74f-104">専用の大規模な会議プールでは、一度に1つの大きな会議のみがサポートされるため、大規模な会議の競合を防ぐために、大規模な会議のスケジュールプロセスを実装することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ba74f-104">Because only one large meeting at a time is supported on the dedicated large meeting pool, we recommend implementing a large meeting scheduling process to help prevent large meeting conflicts.</span></span> <span data-ttu-id="ba74f-105">このようなスケジュールプロセスの目的は、大規模な会議の設定を簡単にすることです。</span><span class="sxs-lookup"><span data-stu-id="ba74f-105">The purpose of such the scheduling process is to facilitate setting up large meetings.</span></span> <span data-ttu-id="ba74f-106">このような機能は、Lync Server または Lync Server クライアントによって直接提供されるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="ba74f-106">Such capability is not provided directly by Lync Server or Lync Server clients.</span></span> <span data-ttu-id="ba74f-107">こうしたプロセスを実装する 1 つの方法は、組織のサポート チームのチケット システム (使用できる場合) を使用することです。</span><span class="sxs-lookup"><span data-stu-id="ba74f-107">One way to implement such a process is to use your organization’s support team’s ticketing system, if available.</span></span>

<span data-ttu-id="ba74f-108">大規模な会議の開催者の場合、大規模な会議のスケジュールを設定するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="ba74f-108">For organizers of large meetings, scheduling a large meeting involves completing the following steps:</span></span>

1.  <span data-ttu-id="ba74f-p102">会議の開催者または代理人は、予定されている会議の時刻、時間、および規模に加えて、発表者のリストを決定します。予測される会議の規模が 250 人を超える場合、または 250 人以下の会議に対して最高のユーザー エクスペリエンスを保証する場合、開催者または代理人は、大規模会議に対して要求を提出します。</span><span class="sxs-lookup"><span data-stu-id="ba74f-p102">The meeting organizer or delegate determines the time, duration, and size of an upcoming meeting, in addition to the list of presenters. If the anticipated meeting size exceeds 250 users or to ensure the best user experience for a meeting of fewer than 250 users, the organizer or the delegate submits a request for a large meeting.</span></span>

2.  <span data-ttu-id="ba74f-p103">スケジュール担当スタッフは、要求された日時が利用できるかどうかを確認します。大規模会議は専用プールで一度に 1 つだけサポートされるため、スケジュール担当スタッフは、大規模会議の予定表をチェックして、要求された日時に別の会議がスケジュールされているかどうかを判定する必要があります。要求された日時が利用できる場合、スタッフは会議の要求を承認します。</span><span class="sxs-lookup"><span data-stu-id="ba74f-p103">The scheduling staff checks to see whether the requested date and time is available. Since we support only a single large meeting on the dedicated pool at a time, the scheduling staff needs to check the large-meeting calendar to determine whether there is another meeting scheduled for the requested date and time. If the requested time is available, the staff approves the meeting request.</span></span>

3.  <span data-ttu-id="ba74f-114">要求が承認された場合、スケジュールスタッフは (専用プールの資格情報を使用)、Lync 2013 用のオンライン会議アドインを使用して、専用の大規模な会議プールで会議を設定します。</span><span class="sxs-lookup"><span data-stu-id="ba74f-114">If the request is approved, the scheduling staff (using credentials on the dedicated pool) uses Online Meeting Add-in for Lync 2013 with Outlook to set up a meeting on the dedicated large-meeting pool.</span></span> <span data-ttu-id="ba74f-115">会議に参加するために使用する URL は、承認通知の一部として要求者に提供されます。</span><span class="sxs-lookup"><span data-stu-id="ba74f-115">The URL to be used to join the meeting is provided to the requester as part of the approval notice.</span></span>

4.  <span data-ttu-id="ba74f-p105">会議の開催者または代理人は、Outlook を使用して、予定されている会議をスケジュールし、会議に参加するための URL を会議の招待状に追加します。次に、会議の開催者または代理人は、招待するユーザーを指定して、会議の招待状を送信します。</span><span class="sxs-lookup"><span data-stu-id="ba74f-p105">The meeting organizer or delegate uses Outlook to schedule the upcoming meeting, adding the URL for joining the meeting to the meeting invitation. The meeting organizer or delegate then specifies the users to be invited and sends out the meeting invitation.</span></span>
    
    <span data-ttu-id="ba74f-118">次の図は、大規模な会議をスケジュールするための一般的な要求ワークフローと承認ワークフローを示しています。</span><span class="sxs-lookup"><span data-stu-id="ba74f-118">The following figure illustrates a typical request and approval workflow for scheduling large meetings.</span></span>
    
    <span data-ttu-id="ba74f-119">![5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d](images/JJ205334.5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d(OCS.15).jpg "5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d")</span><span class="sxs-lookup"><span data-stu-id="ba74f-119">![5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d](images/JJ205334.5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d(OCS.15).jpg "5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d")</span></span>  

</div>

<span> </span>

</div>

</div>

</div>

