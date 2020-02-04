---
title: 'Lync Server 2013: グループ通話のピックアップの概要'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Group Call Pickup
ms:assetid: 3dc0eca8-c773-463c-96bb-9cd6afa2a840
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945623(v=OCS.15)
ms:contentKeyID: 51541466
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0efc85b28a689b43d024d9996211a70dcd91cee0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755551"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="2169c-102">Lync Server 2013 でのグループ通話のピックアップの概要</span><span class="sxs-lookup"><span data-stu-id="2169c-102">Overview of Group Call Pickup in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2169c-103">_**最終更新日:** 2013-02-12_</span><span class="sxs-lookup"><span data-stu-id="2169c-103">_**Topic Last Modified:** 2013-02-12_</span></span>

<span data-ttu-id="2169c-104">グループ通話のピックアップ (Lync Server 2013 の累積更新プログラムの新機能: 2013 年2月) では、ユーザーは自分の電話から同僚への着信に応答できます。</span><span class="sxs-lookup"><span data-stu-id="2169c-104">Group Call Pickup, a new feature in Cumulative Updates for Lync Server 2013: February 2013, lets users answer incoming calls to their colleagues from their own phones.</span></span> <span data-ttu-id="2169c-105">この新機能により、他のユーザーが通話ピックアップグループ番号にダイヤルすることによって着信通話に応答できるようになり、ユーザーの回線の可用性が向上します。</span><span class="sxs-lookup"><span data-stu-id="2169c-105">This new feature increases the availability of a user's line by enabling other users to answer an incoming call by dialing a call pickup group number.</span></span> <span data-ttu-id="2169c-106">グループ通話のピックアップが展開されると、ボイスメールにルーティングされる着信の数が大幅に減少する可能性があります。これは、組織外のユーザーからの通話に特に便利です。</span><span class="sxs-lookup"><span data-stu-id="2169c-106">When Group Call Pickup is deployed, the number of incoming calls that are routed to voice mail can be significantly reduced, which is particularly useful for calls from customers who are external to your organization.</span></span>

<span data-ttu-id="2169c-107">グループ通話の集配機能は、office を開いている環境のビジネスユニット向けに設計されています。</span><span class="sxs-lookup"><span data-stu-id="2169c-107">The Group Call Pickup feature is designed in particular for business units in open office environments.</span></span> <span data-ttu-id="2169c-108">着信通話は、意図した宛先にのみ着信するため、中断されません。</span><span class="sxs-lookup"><span data-stu-id="2169c-108">Incoming calls are not disruptive because they ring only at the intended destination.</span></span> <span data-ttu-id="2169c-109">ただし、リングを聞く他のユーザーは、グループ番号にダイヤルするだけで通話を受けることができます。</span><span class="sxs-lookup"><span data-stu-id="2169c-109">Other users who hear the ring, however, can still pick up the call simply by dialing the group number.</span></span>

<span data-ttu-id="2169c-110">ユーザーのオフィスのレイアウトがオープンでない場合、または地理的に分散された複数のユーザーが一般的な業務を分担している場合は、チーム呼び出しによって最適なソリューションが実現します。</span><span class="sxs-lookup"><span data-stu-id="2169c-110">In environments where users are not located in an open office layout, or where users who share a common responsibility are geographically distributed, team call presents the most suitable solution.</span></span> <span data-ttu-id="2169c-111">グループ通話の集配とチーム呼び出しの主な違いは、グループ通話のピックアップによって着信が発信された場合に限られます。ただし、グループ番号をダイヤルすることによって応答できます。</span><span class="sxs-lookup"><span data-stu-id="2169c-111">The primary difference between Group Call Pickup and team call is that, with Group Call Pickup, an incoming call rings only at the intended destination, but anyone can still choose to answer it by dialing a group number.</span></span> <span data-ttu-id="2169c-112">GroupCallPickupでは、呼び出し音は着信先でしか鳴りませんが、グループ番号をダイヤルすればだれでも電話をとれます。</span><span class="sxs-lookup"><span data-stu-id="2169c-112">With team call, the call rings at all the team members' phones, and any user in the team can pick up the phone to answer the call.</span></span> <span data-ttu-id="2169c-113">グループ通話のピックアップとチーム呼び出しの違いは、グループ通話のピックアップが Lync Server を介して管理者によって管理されることです。</span><span class="sxs-lookup"><span data-stu-id="2169c-113">An additional difference between Group Call Pickup and team call is that Group Call Pickup is managed by an administrator, through Lync Server.</span></span> <span data-ttu-id="2169c-114">チーム呼び出しでは、エンドユーザーが Lync クライアントを使用して機能を管理します。</span><span class="sxs-lookup"><span data-stu-id="2169c-114">With team call, end users manage the feature by using the Lync client.</span></span> <span data-ttu-id="2169c-115">このため、グループ通話のピックアップでは、この通話管理の局面を一元管理できます。</span><span class="sxs-lookup"><span data-stu-id="2169c-115">With Group Call Pickup, therefore, this aspect of call management can be centralized.</span></span>

<span data-ttu-id="2169c-116">グループ通話のピックアップは、コールパークアプリケーションに基づいて構築されます。</span><span class="sxs-lookup"><span data-stu-id="2169c-116">Group Call Pickup is built on the Call Park application.</span></span> <span data-ttu-id="2169c-117">グループ通話のピックアップを展開するときに、通話集配グループ番号として指定されている内線番号の別の範囲を使用して、コールパーク軌道テーブルを構成します。</span><span class="sxs-lookup"><span data-stu-id="2169c-117">When you deploy Group Call Pickup, you configure the call park orbit table with separate ranges of extension numbers that are designated as call pickup group numbers.</span></span> <span data-ttu-id="2169c-118">コール パーク オービット番号と同様、通話ピックアップ グループ番号は、ユーザーも電話も割り当てられていない仮想内線である必要があります。</span><span class="sxs-lookup"><span data-stu-id="2169c-118">Like call park orbit numbers, call pickup group numbers must be virtual extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="2169c-119">グループ通話のピックアップを展開する各フロントエンドプールには、1つ以上の通話ピックアップグループ番号が含まれていることがあります。</span><span class="sxs-lookup"><span data-stu-id="2169c-119">Each Front End pool where you deploy Group Call Pickup can have one or more ranges of call pickup group numbers.</span></span> <span data-ttu-id="2169c-120">グループ番号の範囲は、Lync Server 展開でグローバルに一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="2169c-120">The group number ranges must be globally unique across the Lync Server deployment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2169c-121">通話パークの軌道番号として指定された番号範囲は、Lync Server コントロールパネルを使って管理または表示することはできません。</span><span class="sxs-lookup"><span data-stu-id="2169c-121">Number ranges that are designated as Group Call Pickup numbers in the call park orbit table cannot be managed or viewed by using the Lync Server Control Panel.</span></span> <span data-ttu-id="2169c-122">通話パークの軌道の表にあるすべての番号範囲を表示する唯一の方法は、Lync Server 管理シェルを使うことです。</span><span class="sxs-lookup"><span data-stu-id="2169c-122">The only way to see all the number ranges in the call park orbit table is to use Lync Server Management Shell.</span></span> <span data-ttu-id="2169c-123">同様に、グループ通話の集配番号を追加、変更、または削除するには、Lync Server 管理シェルを使用する方法しかありません。</span><span class="sxs-lookup"><span data-stu-id="2169c-123">Similarly, the only way to add, modify, or remove Group Call Pickup numbers is to use Lync Server Management Shell.</span></span>



</div>

<span data-ttu-id="2169c-p106">通話ピックアップ グループ番号を構成したら、ユーザーを通話ピックアップ グループに割り当てます。通話ピックアップ グループに割り当てられたユーザーにかかってきた電話は、他のユーザーがとることができます。通話ピックアップ グループに割り当てられたユーザーに電話がかかってきたときに、その電話に気が付いた他のユーザーが電話をとるには、通話ピックアップ グループ番号に手動でダイヤルします。電話をとるユーザーは、そのグループのメンバーである必要はありません。他のユーザーが電話をとると、電話がかかってきた番号に通知が送信されます。</span><span class="sxs-lookup"><span data-stu-id="2169c-p106">After you configure the call pickup group numbers, you assign users to a call pickup group. Any user who is assigned to a call pickup group can have their calls answered by other users. When a call comes in to a user who is assigned to a call pickup group, any other user who notices the call can answer it by manually dialing the call pickup group number. The user who picks up the call does not need to be a member of the group. When a call is picked up by another user, a notification is sent to the number originally called.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2169c-129">ユーザーがメンバーになれるのは、1 つの通話ピックアップ グループだけです。</span><span class="sxs-lookup"><span data-stu-id="2169c-129">A user can be a member of only one call pickup group.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="2169c-130">Lync Server の展開のユーザーは、通話ピックアップグループメンバーへの通話に応答できますが、通話に応答するユーザーは、ダイヤルする適切な通話ピックアップグループ番号を知っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="2169c-130">Although any user in the Lync Server deployment can answer a call to a call pickup group member, the person answering the call must know the correct call pickup group number to dial.</span></span>



</div>

<span data-ttu-id="2169c-131">グループ内の複数の電話の呼び出し音が鳴っている場合、ユーザーが通話ピックアップ グループ番号をダイヤルして電話をとると、一番長く呼び出し音が鳴っている電話につながります。</span><span class="sxs-lookup"><span data-stu-id="2169c-131">If a user dials a call pickup group number to answer a call when multiple phones in the group are ringing, the user answers the call that has been ringing the longest.</span></span>

<span data-ttu-id="2169c-132">同時呼び出しの設定は、グループ通話ピックアップを利用しているユーザーに対して有効です。</span><span class="sxs-lookup"><span data-stu-id="2169c-132">Simultaneous ringing settings will work for users who have group call pickup.</span></span> <span data-ttu-id="2169c-133">つまり、グループ通話のピックアップを持っているユーザに発信された通話は、設定されているすべての宛先に対して呼び出しを行い、別のユーザが通話に応答することができます。</span><span class="sxs-lookup"><span data-stu-id="2169c-133">That is, a call made to a user who has Group Call Pickup will ring for all the configured destinations, and another user can answer the call.</span></span> <span data-ttu-id="2169c-134">ただし、すべてのチーム メンバーを呼び出すようにユーザーが同時呼び出しを構成している場合、このルールは適用されません。</span><span class="sxs-lookup"><span data-stu-id="2169c-134">The exception to this rule is when the user configures simultaneous ringing to call all the team members.</span></span>

<span data-ttu-id="2169c-135">グループ通話のピックアップを使用して、次の種類の通話に応答することはできません。</span><span class="sxs-lookup"><span data-stu-id="2169c-135">Group Call Pickup cannot be used to answer the following types of calls:</span></span>

  - <span data-ttu-id="2169c-136">プライベート回線の呼び出し</span><span class="sxs-lookup"><span data-stu-id="2169c-136">Calls to a private line</span></span>

  - <span data-ttu-id="2169c-137">[友人および家族] プライバシー関係に割り当てられた連絡先からの呼び出し</span><span class="sxs-lookup"><span data-stu-id="2169c-137">Calls from a contact who has been assigned the Friends and Family privacy relationship</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="2169c-138">通話ピックアップグループのメンバーであるユーザーは、連絡先を Lync クライアントで個人用の連絡先としてマークすることで、特定の着信がグループ通話のピックアップによって取得されないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="2169c-138">A user who is a member of a call pickup group can prevent certain calls from being retrieved through Group Call Pickup by marking the contact as a personal contact in the Lync client.</span></span> <span data-ttu-id="2169c-139">連絡先を個人連絡先としてマークするには、そのプライバシー関係を [友人および家族] に設定します。</span><span class="sxs-lookup"><span data-stu-id="2169c-139">To mark a contact as a personal contact, set the Privacy Relationship for the contact to Friends and Family.</span></span> <span data-ttu-id="2169c-140">プライバシー関係が設定されている連絡先からの着信通話は、グループ通話のピックアップを使って取得することはできません。</span><span class="sxs-lookup"><span data-stu-id="2169c-140">Any incoming call from contacts with the Privacy Relationship set to Friends and Family cannot be retrieved by using Group Call Pickup.</span></span>

    
    </div>

  - <span data-ttu-id="2169c-141">音声ビデオ通話のビデオ部分</span><span class="sxs-lookup"><span data-stu-id="2169c-141">Video portion of audio/video calls</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2169c-p109">音声ビデオ通話については、ユーザーは音声のみを受け取ります。電話をかけたユーザーまたは電話をとったユーザーのどちらかが、通話をエスカレートして、ビデオを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="2169c-p109">If a user answers an audio/video call, the user receives only the audio. Either the person calling or the person answering the call can escalate the call to add video.</span></span>

    
    </div>

  - <span data-ttu-id="2169c-144">チーム呼び出しメンバーにルーティングされた同時呼び出し</span><span class="sxs-lookup"><span data-stu-id="2169c-144">Simultaneous ringing calls that are routed to team call members</span></span>

  - <span data-ttu-id="2169c-145">代理人にルーティングされた呼び出し</span><span class="sxs-lookup"><span data-stu-id="2169c-145">Calls routed to a delegate</span></span>

  - <span data-ttu-id="2169c-146">応答グループにルーティングされた呼び出し</span><span class="sxs-lookup"><span data-stu-id="2169c-146">Calls routed to a response group</span></span>

<span data-ttu-id="2169c-147">次の種類のユーザーはグループ通話のピックアップに参加できません。</span><span class="sxs-lookup"><span data-stu-id="2169c-147">The following types of users cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="2169c-148">つまり、グループ通話のピックアップグループに含まれておらず、グループ通話のピックアップが有効になっているユーザーに対して通話を受信することはできません。</span><span class="sxs-lookup"><span data-stu-id="2169c-148">That is, they should not be included in a Group Call Pickup group, and they cannot pick up calls for users who have Group Call Pickup enabled.</span></span>

  - <span data-ttu-id="2169c-149">ハイブリッド環境の常時オンラインのユーザー</span><span class="sxs-lookup"><span data-stu-id="2169c-149">Users who are homed online in a hybrid deployment</span></span>

  - <span data-ttu-id="2169c-150">Lync server 2013 プールをホームにしていないユーザーのうち、Lync Server 2013 の累積更新プログラムが適用されている場合: オンプレミスの展開での2013年2月</span><span class="sxs-lookup"><span data-stu-id="2169c-150">Users who are not homed on a Lync Server 2013 pool with Cumulative Updates for Lync Server 2013: February 2013 in an on-premises deployment</span></span>

<span data-ttu-id="2169c-p111">通話ピックアップ グループのメンバーへの電話をだれもとらない場合、その電話は、クライアント設定で指定されているようにルーティングされます。つまり、呼び出しはボイスメールに送られるか、クライアント設定で指定されているように、別の宛先に転送されます。</span><span class="sxs-lookup"><span data-stu-id="2169c-p111">If no one answers a call to a member of a call pickup group, the call is routed as specified in the client settings. That is, the call goes to voicemail or is forwarded to a different destination, as specified in the client settings.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

