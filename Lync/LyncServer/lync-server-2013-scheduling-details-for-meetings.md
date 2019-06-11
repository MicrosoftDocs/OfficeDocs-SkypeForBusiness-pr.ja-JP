---
title: 'Lync Server 2013: 会議のスケジュールの詳細'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Scheduling details
ms:assetid: 39ca6fff-2c15-4347-9f1f-6c8687a39a49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204823(v=OCS.15)
ms:contentKeyID: 48183910
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f027aac5372865bfb2803e19591dadaa1aca4805
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822252"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scheduling-details-for-meetings-in-lync-server-2013"></a><span data-ttu-id="bf71a-102">Lync Server 2013 での会議のスケジュールの詳細</span><span class="sxs-lookup"><span data-stu-id="bf71a-102">Scheduling details for meetings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bf71a-103">_**最終更新日:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="bf71a-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="bf71a-104">要求された時間に、その他の会議がスケジュール設定されていないことを確認した後で、要求を処理する大規模会議サポート スタッフは、大規模会議プールに会議をスケジュール設定します。</span><span class="sxs-lookup"><span data-stu-id="bf71a-104">After checking to ensure that no other meeting is scheduled at the requested time, the large meeting support staff that handles the request schedules the meeting on the large-meeting pool.</span></span> <span data-ttu-id="bf71a-105">Lync Server 2013 クライアントと共にインストールされた lync 用オンライン会議アドインを使用して、専用の大規模な会議プールで Lync Server が有効になっているユーザーの資格情報を使用して、このタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="bf71a-105">Use the Online Meeting Add-in for Lync that is installed with the Lync Server 2013 client to perform this task, using the credentials of a user enabled for Lync Server in the dedicated large-meeting pool.</span></span>

<span data-ttu-id="bf71a-106">最良のユーザー エクスペリエンスを保証するには、会議の開催者の需要を満たす適切なアクセス レベルと会議設定で、大規模会議をスケジュール設定することが重要です。</span><span class="sxs-lookup"><span data-stu-id="bf71a-106">To ensure the best user experience, it is important to schedule the large meeting with the right access levels and meeting settings that are appropriate to the meeting organizer’s needs.</span></span> <span data-ttu-id="bf71a-107">Lync 会議のオプションで次のスケジュール設定を構成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="bf71a-107">We recommend the following scheduling settings configured in Lync Meeting options:</span></span>

  - <span data-ttu-id="bf71a-108">専用の会議スペースを再利用せずに、各大規模会議用に新しい会議スペースを使用します。</span><span class="sxs-lookup"><span data-stu-id="bf71a-108">Use a new meeting space for each large meeting instead of reusing the dedicated meeting space.</span></span>

  - <span data-ttu-id="bf71a-109">以下のように会議アクセス レベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="bf71a-109">Specify the meeting access level as follows:</span></span>
    
      - <span data-ttu-id="bf71a-110">少なくとも1人の出席者が組織外の場合は、会議アクセスの種類を [すべての人] に設定します **(制限はありません**)。</span><span class="sxs-lookup"><span data-stu-id="bf71a-110">If at least one invitee is external to the organization, set the meeting access type to **Anyone (no restrictions**.</span></span> <span data-ttu-id="bf71a-111">これにより、会議の進行中に、大規模なロビーを管理することを回避できます。</span><span class="sxs-lookup"><span data-stu-id="bf71a-111">This enables you to avoid having to manage a potentially large lobby when the meeting is in progress.</span></span>
    
      - <span data-ttu-id="bf71a-112">会議が内部のみの会議の場合、会議アクセスの種類を [**同じ組織のユーザー**] に設定します。</span><span class="sxs-lookup"><span data-stu-id="bf71a-112">If the meeting is an internal-only meeting, set the meeting access type to **Anyone from my organization**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="bf71a-113">この設定を使用している場合、会議アクセスの種類を<STRONG>会社から招待</STRONG>したユーザーに設定しないようにします。この設定を使用すると、開催者はすべてのユーザーのメールアドレスを招待者リストに追加する必要があり、配布グループを招待することはできません。</span><span class="sxs-lookup"><span data-stu-id="bf71a-113">Avoid setting the meeting access type to <STRONG>People I invite from my company</STRONG> because when you use this setting, organizers must add all user email addresses to the invitee list and you cannot invite a distribution group.</span></span><BR><span data-ttu-id="bf71a-114">この設定では、発表者を含むすべての会議参加者が、会議の実行時にロビーに配置される必要があるため、会議アクセスタイプを [<STRONG>自分のみ]</STRONG>に設定することは避けてください。</span><span class="sxs-lookup"><span data-stu-id="bf71a-114">Avoid setting the meeting access type to <STRONG>Only me, the meeting organizer</STRONG> because this setting requires that every meeting participant, including presenters, must be put in the lobby at meeting run time.</span></span> <span data-ttu-id="bf71a-115">大規模な会議を実行しようとしているユーザーは、ロビーリストを継続的に監視し、ロビー内の新しいユーザーを許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf71a-115">The person responsible for running the large meeting must then constantly monitor the lobby roster and admit new users who are in the lobby.</span></span>

        
        </div>

  - <span data-ttu-id="bf71a-116">[**発信者は直接参加する**] 設定のチェックボックスをオンにして、電話からダイヤルインするユーザーが、自動的に会議に参加できるようにします。</span><span class="sxs-lookup"><span data-stu-id="bf71a-116">Allow users who dial-in from phones to enter the meeting automatically by checking the **Callers get in directly** setting.</span></span>

  - <span data-ttu-id="bf71a-117">以下のユーザーは明示的に招待します。</span><span class="sxs-lookup"><span data-stu-id="bf71a-117">Explicitly invite the following users:</span></span>
    
      - <span data-ttu-id="bf71a-118">会議の主催者と代理人 (要求者)</span><span class="sxs-lookup"><span data-stu-id="bf71a-118">Meeting organizer and delegate (requester)</span></span>
    
      - <span data-ttu-id="bf71a-119">会議の要求者が提出した発表者のリスト</span><span class="sxs-lookup"><span data-stu-id="bf71a-119">The list of presenters provided by a meeting requester</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bf71a-120">会議アクセスの種類が [<STRONG>選択した個人</STRONG>] に設定された場合、大規模会議の各参加者を、会議の招待者として明示的に追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf71a-120">If the meeting access type is set to <STRONG>People I choose</STRONG>, you need to explicitly add each participant of a large meeting as an invitee of the meeting.</span></span>

    
    </div>

  - <span data-ttu-id="bf71a-p105">発表者は明示的に管理してください。発表者オプションをいずれかの自動昇格値に設定しないでください。以下のユーザーは必ず発表者として追加します。</span><span class="sxs-lookup"><span data-stu-id="bf71a-p105">Explicitly manage presenters, instead of setting the presenter option to one of the auto-promote values. Be sure to add the following users as presenters:</span></span>
    
      - <span data-ttu-id="bf71a-123">会議の主催者と代理人 (要求者)</span><span class="sxs-lookup"><span data-stu-id="bf71a-123">Meeting organizer and delegate (requester)</span></span>
    
      - <span data-ttu-id="bf71a-124">大規模会議の要求者が提出した発表者のリスト</span><span class="sxs-lookup"><span data-stu-id="bf71a-124">The list of presenters provided by large meeting requesters</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bf71a-125">発表者の明示的な管理を行うことで、発表者の数を管理することができます。これにより、発表者は、有効な大人数の会議を可能にすることができるようになります。</span><span class="sxs-lookup"><span data-stu-id="bf71a-125">By explicitly managing presenters, you can control the number of presenters, so that you can limit presenters to a small enough number to make it possible to have an effective large meeting.</span></span> <span data-ttu-id="bf71a-126">会議の参加者の大部分が参加者の役割を持っていれば、誤ってプレゼンテーションの制御を取得することや、PowerPoint プレゼンテーションを削除すること、発表者のミュートを切り替えることなど、会議の中断をもたらす操作が行われる可能性を減らすのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="bf71a-126">If the majority of meeting participants have the attendee role, it helps reduce the chance of people accidentally taking control of the presentation, deleting a PowerPoint presentation, muting/unmuting presenters, and other disruptions to the meeting.</span></span>

    
    </div>

  - <span data-ttu-id="bf71a-127">発表者だけが会議に音声をブロードキャストできるように、[**すべての参加者をミュートにする**] 設定のチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="bf71a-127">Check the **Mute all attendees** setting to make sure that only presenters can broadcast audio into the meeting.</span></span>

  - <span data-ttu-id="bf71a-128">発表者だけが会議にビデオをブロードキャストできるように、[**出席者のビデオをブロックする**] 設定のチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="bf71a-128">Check the **Block attendees’ video** setting to make sure only presenters can broadcast video into the meeting.</span></span>

<span data-ttu-id="bf71a-129">次の図は、Lync 用のオンライン会議アドインの推奨される設定を示しています。</span><span class="sxs-lookup"><span data-stu-id="bf71a-129">The following figure shows the recommended settings for the Online Meeting Add-in for Lync.</span></span>

<span data-ttu-id="bf71a-130">![54e4e70d-06b0-45cd-8d94-bab649cd5dc0](images/JJ204823.54e4e70d-06b0-45cd-8d94-bab649cd5dc0(OCS.15).jpg "54e4e70d-06b0-45cd-8d94-bab649cd5dc0")</span><span class="sxs-lookup"><span data-stu-id="bf71a-130">![54e4e70d-06b0-45cd-8d94-bab649cd5dc0](images/JJ204823.54e4e70d-06b0-45cd-8d94-bab649cd5dc0(OCS.15).jpg "54e4e70d-06b0-45cd-8d94-bab649cd5dc0")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

