---
title: 'Lync Server 2013: 会議のスケジュールの詳細'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scheduling details
ms:assetid: 39ca6fff-2c15-4347-9f1f-6c8687a39a49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204823(v=OCS.15)
ms:contentKeyID: 48183910
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2fa7186ed00ea2c42db392af72555bdbbbeeaaab
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144165"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="scheduling-details-for-meetings-in-lync-server-2013"></a><span data-ttu-id="3cf8f-102">Lync Server 2013 での会議のスケジュールの詳細</span><span class="sxs-lookup"><span data-stu-id="3cf8f-102">Scheduling details for meetings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3cf8f-103">_**トピックの最終更新日:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="3cf8f-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="3cf8f-104">要求された時間に他の会議がスケジュールされていないことを確認した後、要求を処理する大規模会議サポートスタッフが、大規模な会議のプールで会議をスケジュールします。</span><span class="sxs-lookup"><span data-stu-id="3cf8f-104">After checking to ensure that no other meeting is scheduled at the requested time, the large meeting support staff that handles the request schedules the meeting on the large-meeting pool.</span></span> <span data-ttu-id="3cf8f-105">Lync server 2013 クライアントと共にインストールされる lync 用オンラインミーティングアドインを使用して、専用の大規模な会議プールで Lync Server が有効になっているユーザーの資格情報を使用してこのタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="3cf8f-105">Use the Online Meeting Add-in for Lync that is installed with the Lync Server 2013 client to perform this task, using the credentials of a user enabled for Lync Server in the dedicated large-meeting pool.</span></span>

<span data-ttu-id="3cf8f-106">最良のユーザー エクスペリエンスを保証するには、会議の開催者の需要を満たす適切なアクセスレベルと会議設定で、大規模会議をスケジュール設定することが重要です。</span><span class="sxs-lookup"><span data-stu-id="3cf8f-106">To ensure the best user experience, it is important to schedule the large meeting with the right access levels and meeting settings that are appropriate to the meeting organizer’s needs.</span></span> <span data-ttu-id="3cf8f-107">Lync 会議オプションでは、次のスケジュール設定を構成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3cf8f-107">We recommend the following scheduling settings configured in Lync Meeting options:</span></span>

  - <span data-ttu-id="3cf8f-108">専用の会議スペースを再利用せずに、各大規模会議用に新しい会議スペースを使用します。</span><span class="sxs-lookup"><span data-stu-id="3cf8f-108">Use a new meeting space for each large meeting instead of reusing the dedicated meeting space.</span></span>

  - <span data-ttu-id="3cf8f-109">以下のように会議アクセス レベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="3cf8f-109">Specify the meeting access level as follows:</span></span>
    
      - <span data-ttu-id="3cf8f-p103">1 名でも組織外部の招待者がいる場合は、会議アクセスの種類を [**すべてのユーザー (制限なし)**] に設定します。これにより、会議の進行中に、大規模なロビーを管理することを回避できます。</span><span class="sxs-lookup"><span data-stu-id="3cf8f-p103">If at least one invitee is external to the organization, set the meeting access type to **Anyone (no restrictions**. This enables you to avoid having to manage a potentially large lobby when the meeting is in progress.</span></span>
    
      - <span data-ttu-id="3cf8f-112">会議が内部のみの会議の場合、会議アクセスの種類を [**同じ組織のユーザー**] に設定します。</span><span class="sxs-lookup"><span data-stu-id="3cf8f-112">If the meeting is an internal-only meeting, set the meeting access type to **Anyone from my organization**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="3cf8f-113">会議アクセスの種類を [<STRONG>会社内から招待した人</STRONG>] に設定することは避けてください。この設定を使用すると、開催者は招待者リストにすべてのユーザーの電子メール アドレスを追加する必要があり、また配布グループを招待できません。</span><span class="sxs-lookup"><span data-stu-id="3cf8f-113">Avoid setting the meeting access type to <STRONG>People I invite from my company</STRONG> because when you use this setting, organizers must add all user email addresses to the invitee list and you cannot invite a distribution group.</span></span><BR><span data-ttu-id="3cf8f-p104">会議アクセスの種類を、[<STRONG>会議の開催者である自分のみ</STRONG>] に設定することは避けてください。この設定では、発表者を含む会議の参加者全員を、会議実行時にロビーに配置する必要があるからです。この場合、大規模会議の実行責任者は、継続的にロビー名簿を監視して、ロビーにいる新規ユーザーの参加を許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3cf8f-p104">Avoid setting the meeting access type to <STRONG>Only me, the meeting organizer</STRONG> because this setting requires that every meeting participant, including presenters, must be put in the lobby at meeting run time. The person responsible for running the large meeting must then constantly monitor the lobby roster and admit new users who are in the lobby.</span></span>

        
        </div>

  - <span data-ttu-id="3cf8f-116">[**発信者は直接参加する**] 設定のチェックボックスをオンにして、電話からダイヤルインするユーザーが、自動的に会議に参加できるようにします。</span><span class="sxs-lookup"><span data-stu-id="3cf8f-116">Allow users who dial-in from phones to enter the meeting automatically by checking the **Callers get in directly** setting.</span></span>

  - <span data-ttu-id="3cf8f-117">以下のユーザーは明示的に招待します。</span><span class="sxs-lookup"><span data-stu-id="3cf8f-117">Explicitly invite the following users:</span></span>
    
      - <span data-ttu-id="3cf8f-118">会議の主催者と代理人 (要求者)</span><span class="sxs-lookup"><span data-stu-id="3cf8f-118">Meeting organizer and delegate (requester)</span></span>
    
      - <span data-ttu-id="3cf8f-119">会議の要求者が提出した発表者のリスト</span><span class="sxs-lookup"><span data-stu-id="3cf8f-119">The list of presenters provided by a meeting requester</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3cf8f-120">会議アクセスの種類が [<STRONG>選択した個人</STRONG>] に設定された場合、大規模会議の各参加者を、会議の招待者として明示的に追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3cf8f-120">If the meeting access type is set to <STRONG>People I choose</STRONG>, you need to explicitly add each participant of a large meeting as an invitee of the meeting.</span></span>

    
    </div>

  - <span data-ttu-id="3cf8f-p105">発表者は明示的に管理してください。発表者オプションをいずれかの自動昇格値に設定しないでください。以下のユーザーは必ず発表者として追加します。</span><span class="sxs-lookup"><span data-stu-id="3cf8f-p105">Explicitly manage presenters, instead of setting the presenter option to one of the auto-promote values. Be sure to add the following users as presenters:</span></span>
    
      - <span data-ttu-id="3cf8f-123">会議の主催者と代理人 (要求者)</span><span class="sxs-lookup"><span data-stu-id="3cf8f-123">Meeting organizer and delegate (requester)</span></span>
    
      - <span data-ttu-id="3cf8f-124">大規模会議の要求者が提出した発表者のリスト</span><span class="sxs-lookup"><span data-stu-id="3cf8f-124">The list of presenters provided by large meeting requesters</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3cf8f-p106">発表者を明示的に管理することによって、発表者の数を制御できます。これにより、発表者を少数に制限して、効果的な大規模会議ができます。会議の参加者の大部分が参加者役割を持っていれば、誤ってプレゼンテーションの制御を取得する、PowerPoint プレゼンテーションを削除する、発表者のミュートを切り替えるなど、また、その他の会議の中断をもたらす可能性を減らすのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="3cf8f-p106">By explicitly managing presenters, you can control the number of presenters, so that you can limit presenters to a small enough number to make it possible to have an effective large meeting. If the majority of meeting participants have the attendee role, it helps reduce the chance of people accidentally taking control of the presentation, deleting a PowerPoint presentation, muting/unmuting presenters, and other disruptions to the meeting.</span></span>

    
    </div>

  - <span data-ttu-id="3cf8f-127">発表者だけが会議に音声をブロードキャストできるように、[**すべての参加者をミュートにする**] 設定のチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="3cf8f-127">Check the **Mute all attendees** setting to make sure that only presenters can broadcast audio into the meeting.</span></span>

  - <span data-ttu-id="3cf8f-128">発表者だけが会議にビデオをブロードキャストできるように、[**出席者のビデオをブロックする**] 設定のチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="3cf8f-128">Check the **Block attendees’ video** setting to make sure only presenters can broadcast video into the meeting.</span></span>

<span data-ttu-id="3cf8f-129">次の図は、Lync 用オンラインミーティングアドインの推奨設定を示しています。</span><span class="sxs-lookup"><span data-stu-id="3cf8f-129">The following figure shows the recommended settings for the Online Meeting Add-in for Lync.</span></span>

<span data-ttu-id="3cf8f-130">![54e4e70d-06b0-45cd-8d94-bab649cd5dc0](images/JJ204823.54e4e70d-06b0-45cd-8d94-bab649cd5dc0(OCS.15).jpg "54e4e70d-06b0-45cd-8d94-bab649cd5dc0")</span><span class="sxs-lookup"><span data-stu-id="3cf8f-130">![54e4e70d-06b0-45cd-8d94-bab649cd5dc0](images/JJ204823.54e4e70d-06b0-45cd-8d94-bab649cd5dc0(OCS.15).jpg "54e4e70d-06b0-45cd-8d94-bab649cd5dc0")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

