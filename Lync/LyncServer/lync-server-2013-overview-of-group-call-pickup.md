---
title: 'Lync Server 2013: グループ通話ピックアップの概要'
description: 'Lync Server 2013: グループ通話ピックアップの概要。'
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
ms.openlocfilehash: c968ac466c7242253cb5a9594e1942d86031494d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562883"
---
# <a name="overview-of-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="62408-103">Lync Server 2013 でのグループ通話ピックアップの概要</span><span class="sxs-lookup"><span data-stu-id="62408-103">Overview of Group Call Pickup in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="62408-104">_**トピックの最終更新日:** 2013-02-12_</span><span class="sxs-lookup"><span data-stu-id="62408-104">_**Topic Last Modified:** 2013-02-12_</span></span>

<span data-ttu-id="62408-105">グループ通話ピックアップ (Lync Server 2013 の累積的な更新プログラムの新機能: 2 月 2013) を使用すると、ユーザーは自分の電話から自分の仕事仲間への着信呼び出しに応答できます。</span><span class="sxs-lookup"><span data-stu-id="62408-105">Group Call Pickup, a new feature in Cumulative Updates for Lync Server 2013: February 2013, lets users answer incoming calls to their colleagues from their own phones.</span></span> <span data-ttu-id="62408-106">この新しい機能により、他のユーザーが通話ピックアップグループ番号をダイヤルして着信呼び出しに応答できるようになり、ユーザーの回線の可用性が向上します。</span><span class="sxs-lookup"><span data-stu-id="62408-106">This new feature increases the availability of a user's line by enabling other users to answer an incoming call by dialing a call pickup group number.</span></span> <span data-ttu-id="62408-107">グループ通話ピックアップを展開すると、ボイスメールにルーティングされる着信呼び出しの数を大幅に削減できます。これは、組織外のお客様からの通話に特に便利です。</span><span class="sxs-lookup"><span data-stu-id="62408-107">When Group Call Pickup is deployed, the number of incoming calls that are routed to voice mail can be significantly reduced, which is particularly useful for calls from customers who are external to your organization.</span></span>

<span data-ttu-id="62408-108">グループ通話ピックアップ機能は、open office 環境のビジネス単位に特化して設計されています。</span><span class="sxs-lookup"><span data-stu-id="62408-108">The Group Call Pickup feature is designed in particular for business units in open office environments.</span></span> <span data-ttu-id="62408-109">着信呼び出しは、目的の宛先にのみ着信するので、停止することはありません。</span><span class="sxs-lookup"><span data-stu-id="62408-109">Incoming calls are not disruptive because they ring only at the intended destination.</span></span> <span data-ttu-id="62408-110">ただし、着信音を聞く他のユーザーは、グループ番号をダイヤルするだけで通話を選択できます。</span><span class="sxs-lookup"><span data-stu-id="62408-110">Other users who hear the ring, however, can still pick up the call simply by dialing the group number.</span></span>

<span data-ttu-id="62408-111">ユーザーが開いているオフィスレイアウトにない場合、または一般的な責任を共有するユーザーが地理的に分散している場合、team call は最適なソリューションを提示します。</span><span class="sxs-lookup"><span data-stu-id="62408-111">In environments where users are not located in an open office layout, or where users who share a common responsibility are geographically distributed, team call presents the most suitable solution.</span></span> <span data-ttu-id="62408-112">グループ通話ピックアップとチーム呼び出しの主な違いは、グループ通話ピックアップを使用した場合に、目的の宛先でのみ着信呼び出しが発生するということですが、ユーザーはグループ番号をダイヤルして応答することもできます。</span><span class="sxs-lookup"><span data-stu-id="62408-112">The primary difference between Group Call Pickup and team call is that, with Group Call Pickup, an incoming call rings only at the intended destination, but anyone can still choose to answer it by dialing a group number.</span></span> <span data-ttu-id="62408-113">チーム呼び出しでは、すべてのチームメンバーの電話で呼び出しが発信され、チーム内のすべてのユーザーが電話を選択して通話に応答できます。</span><span class="sxs-lookup"><span data-stu-id="62408-113">With team call, the call rings at all the team members' phones, and any user in the team can pick up the phone to answer the call.</span></span> <span data-ttu-id="62408-114">グループ通話ピックアップとチーム呼び出しの違いは、グループ通話ピックアップが Lync Server を介して管理者によって管理されるということです。</span><span class="sxs-lookup"><span data-stu-id="62408-114">An additional difference between Group Call Pickup and team call is that Group Call Pickup is managed by an administrator, through Lync Server.</span></span> <span data-ttu-id="62408-115">チーム呼び出しでは、エンドユーザーが Lync クライアントを使用して機能を管理します。</span><span class="sxs-lookup"><span data-stu-id="62408-115">With team call, end users manage the feature by using the Lync client.</span></span> <span data-ttu-id="62408-116">このため、グループ通話ピックアップを使用すると、通話管理のこの側面を集中管理することができます。</span><span class="sxs-lookup"><span data-stu-id="62408-116">With Group Call Pickup, therefore, this aspect of call management can be centralized.</span></span>

<span data-ttu-id="62408-117">グループ通話ピックアップは、コールパークアプリケーション上に構築されます。</span><span class="sxs-lookup"><span data-stu-id="62408-117">Group Call Pickup is built on the Call Park application.</span></span> <span data-ttu-id="62408-118">グループ通話ピックアップを展開する場合は、通話ピックアップグループ番号として指定された個別の内線番号の範囲を使用してコールパークオービットテーブルを構成します。</span><span class="sxs-lookup"><span data-stu-id="62408-118">When you deploy Group Call Pickup, you configure the call park orbit table with separate ranges of extension numbers that are designated as call pickup group numbers.</span></span> <span data-ttu-id="62408-119">コールパークオービット番号と同様に、通話ピックアップグループ番号は、ユーザーまたは電話が割り当てられていない仮想内線である必要があります。</span><span class="sxs-lookup"><span data-stu-id="62408-119">Like call park orbit numbers, call pickup group numbers must be virtual extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="62408-120">グループ通話ピックアップを展開する各フロントエンドプールには、1つまたは複数の通話ピックアップグループ番号範囲を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="62408-120">Each Front End pool where you deploy Group Call Pickup can have one or more ranges of call pickup group numbers.</span></span> <span data-ttu-id="62408-121">グループ番号の範囲は、Lync Server 展開間でグローバルに一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="62408-121">The group number ranges must be globally unique across the Lync Server deployment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="62408-122">コールパークオービットテーブルのグループ通話ピックアップ番号として指定されている番号範囲は、Lync Server コントロールパネルを使用しても管理または表示できません。</span><span class="sxs-lookup"><span data-stu-id="62408-122">Number ranges that are designated as Group Call Pickup numbers in the call park orbit table cannot be managed or viewed by using the Lync Server Control Panel.</span></span> <span data-ttu-id="62408-123">コールパークオービットの表のすべての番号範囲を表示する唯一の方法は、Lync Server 管理シェルを使用することです。</span><span class="sxs-lookup"><span data-stu-id="62408-123">The only way to see all the number ranges in the call park orbit table is to use Lync Server Management Shell.</span></span> <span data-ttu-id="62408-124">同様に、グループ通話ピックアップ番号を追加、変更、または削除する唯一の方法は、Lync Server 管理シェルを使用することです。</span><span class="sxs-lookup"><span data-stu-id="62408-124">Similarly, the only way to add, modify, or remove Group Call Pickup numbers is to use Lync Server Management Shell.</span></span>



</div>

<span data-ttu-id="62408-125">通話ピックアップグループ番号を構成した後、ユーザーを通話ピックアップグループに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="62408-125">After you configure the call pickup group numbers, you assign users to a call pickup group.</span></span> <span data-ttu-id="62408-126">通話ピックアップグループに割り当てられているユーザーは、他のユーザーによって通話に応答できます。</span><span class="sxs-lookup"><span data-stu-id="62408-126">Any user who is assigned to a call pickup group can have their calls answered by other users.</span></span> <span data-ttu-id="62408-127">通話ピックアップグループに割り当てられているユーザーに通話が着信すると、その通話に通知を受け取った他のユーザーは、通話ピックアップグループ番号を手動でダイヤルすることによってその通話に応答できます。</span><span class="sxs-lookup"><span data-stu-id="62408-127">When a call comes in to a user who is assigned to a call pickup group, any other user who notices the call can answer it by manually dialing the call pickup group number.</span></span> <span data-ttu-id="62408-128">呼び出しをピックアップするユーザーは、グループのメンバーである必要はありません。</span><span class="sxs-lookup"><span data-stu-id="62408-128">The user who picks up the call does not need to be a member of the group.</span></span> <span data-ttu-id="62408-129">別のユーザーによって通話が選択されると、最初に呼び出した番号に通知が送信されます。</span><span class="sxs-lookup"><span data-stu-id="62408-129">When a call is picked up by another user, a notification is sent to the number originally called.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="62408-130">ユーザーは、1つの通話ピックアップグループのみのメンバーになることができます。</span><span class="sxs-lookup"><span data-stu-id="62408-130">A user can be a member of only one call pickup group.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="62408-131">Lync Server 展開のユーザーは、通話ピックアップグループメンバーへの通話に応答できますが、呼び出しに応答するユーザーは、ダイヤルする正しい通話ピックアップグループ番号を知っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="62408-131">Although any user in the Lync Server deployment can answer a call to a call pickup group member, the person answering the call must know the correct call pickup group number to dial.</span></span>



</div>

<span data-ttu-id="62408-132">グループ内の複数の電話の呼び出しに応答するためにユーザーが通話ピックアップグループ番号をダイヤルすると、ユーザーは最も長い通話に応答します。</span><span class="sxs-lookup"><span data-stu-id="62408-132">If a user dials a call pickup group number to answer a call when multiple phones in the group are ringing, the user answers the call that has been ringing the longest.</span></span>

<span data-ttu-id="62408-133">同時呼び出しの設定は、グループ通話ピックアップを持つユーザーに対して機能します。</span><span class="sxs-lookup"><span data-stu-id="62408-133">Simultaneous ringing settings will work for users who have group call pickup.</span></span> <span data-ttu-id="62408-134">つまり、グループ通話ピックアップを持つユーザーに対して行われた呼び出しは、構成されたすべての送信先に対してリングを行い、別のユーザーが通話に応答することができます。</span><span class="sxs-lookup"><span data-stu-id="62408-134">That is, a call made to a user who has Group Call Pickup will ring for all the configured destinations, and another user can answer the call.</span></span> <span data-ttu-id="62408-135">このルールの例外は、ユーザーがすべてのチームメンバーを呼び出すように同時呼び出しを構成する場合です。</span><span class="sxs-lookup"><span data-stu-id="62408-135">The exception to this rule is when the user configures simultaneous ringing to call all the team members.</span></span>

<span data-ttu-id="62408-136">グループ通話ピックアップを使用して次の種類の通話に応答することはできません。</span><span class="sxs-lookup"><span data-stu-id="62408-136">Group Call Pickup cannot be used to answer the following types of calls:</span></span>

  - <span data-ttu-id="62408-137">プライベート行の呼び出し</span><span class="sxs-lookup"><span data-stu-id="62408-137">Calls to a private line</span></span>

  - <span data-ttu-id="62408-138">友人および家族のプライバシー関係が割り当てられている連絡先からの呼び出し</span><span class="sxs-lookup"><span data-stu-id="62408-138">Calls from a contact who has been assigned the Friends and Family privacy relationship</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="62408-139">通話ピックアップグループのメンバーであるユーザーは、その連絡先を Lync クライアントの個人用連絡先としてマークすることによって、グループ通話ピックアップで特定の呼び出しが取得されないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="62408-139">A user who is a member of a call pickup group can prevent certain calls from being retrieved through Group Call Pickup by marking the contact as a personal contact in the Lync client.</span></span> <span data-ttu-id="62408-140">連絡先を個人連絡先としてマークするには、連絡先のプライバシー関係を [友人と家族] に設定します。</span><span class="sxs-lookup"><span data-stu-id="62408-140">To mark a contact as a personal contact, set the Privacy Relationship for the contact to Friends and Family.</span></span> <span data-ttu-id="62408-141">プライバシー関係が [友人および家族] に設定されている連絡先からの着信呼び出しは、グループ通話ピックアップを使用して取得することはできません。</span><span class="sxs-lookup"><span data-stu-id="62408-141">Any incoming call from contacts with the Privacy Relationship set to Friends and Family cannot be retrieved by using Group Call Pickup.</span></span>

    
    </div>

  - <span data-ttu-id="62408-142">音声ビデオ通話のビデオ部分</span><span class="sxs-lookup"><span data-stu-id="62408-142">Video portion of audio/video calls</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="62408-143">ユーザーが音声ビデオ通話に応答した場合、ユーザーは音声のみを受信します。</span><span class="sxs-lookup"><span data-stu-id="62408-143">If a user answers an audio/video call, the user receives only the audio.</span></span> <span data-ttu-id="62408-144">通話または呼び出しに応答する人のいずれかが通話をエスカレートして、ビデオを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="62408-144">Either the person calling or the person answering the call can escalate the call to add video.</span></span>

    
    </div>

  - <span data-ttu-id="62408-145">チーム呼び出しメンバーにルーティングされる同時呼び出し</span><span class="sxs-lookup"><span data-stu-id="62408-145">Simultaneous ringing calls that are routed to team call members</span></span>

  - <span data-ttu-id="62408-146">代理人にルーティングされた通話</span><span class="sxs-lookup"><span data-stu-id="62408-146">Calls routed to a delegate</span></span>

  - <span data-ttu-id="62408-147">応答グループにルーティングされた通話</span><span class="sxs-lookup"><span data-stu-id="62408-147">Calls routed to a response group</span></span>

<span data-ttu-id="62408-148">次の種類のユーザーは、グループ通話ピックアップに参加できません。</span><span class="sxs-lookup"><span data-stu-id="62408-148">The following types of users cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="62408-149">つまり、グループ通話ピックアップグループに含まれないようにする必要があります。また、グループ通話ピックアップが有効になっているユーザーに対して通話を取得することはできません。</span><span class="sxs-lookup"><span data-stu-id="62408-149">That is, they should not be included in a Group Call Pickup group, and they cannot pick up calls for users who have Group Call Pickup enabled.</span></span>

  - <span data-ttu-id="62408-150">ハイブリッド展開でオンラインに所属しているユーザー</span><span class="sxs-lookup"><span data-stu-id="62408-150">Users who are homed online in a hybrid deployment</span></span>

  - <span data-ttu-id="62408-151">Lync Server 2013 の累積的な更新プログラムを適用して Lync Server 2013 プールに所属していないユーザー (社内展開の場合は2013年2月)</span><span class="sxs-lookup"><span data-stu-id="62408-151">Users who are not homed on a Lync Server 2013 pool with Cumulative Updates for Lync Server 2013: February 2013 in an on-premises deployment</span></span>

<span data-ttu-id="62408-152">通話ピックアップグループのメンバーへの通話に応答しない場合は、クライアント設定で指定された方法で呼び出しがルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="62408-152">If no one answers a call to a member of a call pickup group, the call is routed as specified in the client settings.</span></span> <span data-ttu-id="62408-153">つまり、呼び出しはボイスメールに送られるか、クライアント設定で指定された別の宛先に転送されます。</span><span class="sxs-lookup"><span data-stu-id="62408-153">That is, the call goes to voicemail or is forwarded to a different destination, as specified in the client settings.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

