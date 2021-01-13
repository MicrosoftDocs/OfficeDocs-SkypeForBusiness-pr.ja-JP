---
title: Skype for Business でのグループ通話ピックアップの計画
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3dc0eca8-c773-463c-96bb-9cd6afa2a840
description: Skype for Business Server エンタープライズ VoIP でのグループ通話ピックアップの計画。これにより、ユーザーは本来は他のユーザー向け通話に応答できます。
ms.openlocfilehash: 874b9385352a8c51d9c9a356dd0ccc2ca3070601
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825617"
---
# <a name="plan-for-group-call-pickup-in-skype-for-business"></a><span data-ttu-id="2f32f-103">Skype for Business でのグループ通話ピックアップの計画</span><span class="sxs-lookup"><span data-stu-id="2f32f-103">Plan for Group Call Pickup in Skype for Business</span></span>
 
<span data-ttu-id="2f32f-104">Skype for Business Server エンタープライズ VoIP でのグループ通話ピックアップの計画。これにより、ユーザーは本来は他のユーザー向け通話に応答できます。</span><span class="sxs-lookup"><span data-stu-id="2f32f-104">Planning for Group Call Pickup in Skype for Business Server Enterprise Voice, which enables users to answer calls originally intended for others.</span></span>
  
<span data-ttu-id="2f32f-105">グループ通話ピックアップを使用すると、ユーザーは自分の電話から同僚への着信呼び出しに応答できます。</span><span class="sxs-lookup"><span data-stu-id="2f32f-105">Group Call Pickup enables users to answer incoming calls to their colleagues from their own phones.</span></span> <span data-ttu-id="2f32f-106">これにより、他のユーザーが通話ピックアップ グループ番号をダイヤルして着信呼び出しに応答できると、ユーザーの回線の可用性が向上します。</span><span class="sxs-lookup"><span data-stu-id="2f32f-106">This increases the availability of a user's line by enabling other users to answer an incoming call by dialing a call pickup group number.</span></span> <span data-ttu-id="2f32f-107">グループ通話ピックアップを展開すると、ボイス メールにルーティングされる着信呼び出しの数が大幅に減少する可能性があります。これは、組織外の顧客からの通話に特に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="2f32f-107">When Group Call Pickup is deployed, the number of incoming calls that are routed to voice mail can be significantly reduced, which is particularly useful for calls from customers who are external to your organization.</span></span>
  
<span data-ttu-id="2f32f-108">グループ通話ピックアップ機能は、特にオープン オフィス環境のビジネス単位向けに設計されています。</span><span class="sxs-lookup"><span data-stu-id="2f32f-108">The Group Call Pickup feature is designed in particular for business units in open office environments.</span></span> <span data-ttu-id="2f32f-109">着信呼び出しは、目的の宛先でのみ呼び出すので、中断しません。</span><span class="sxs-lookup"><span data-stu-id="2f32f-109">Incoming calls are not disruptive because they ring only at the intended destination.</span></span> <span data-ttu-id="2f32f-110">ただし、リングを聞いた他のユーザーは、グループ番号をダイヤルするだけで通話を受け取る可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2f32f-110">Other users who hear the ring, however, can still pick up the call simply by dialing the group number.</span></span> 
  
<span data-ttu-id="2f32f-111">ユーザーがオープンなオフィス レイアウトに配置されていない環境や、共通の責任を持つユーザーが地理的に分散している環境では、チームコールが最も適したソリューションを提供します。</span><span class="sxs-lookup"><span data-stu-id="2f32f-111">In environments where users are not located in an open office layout, or where users who share a common responsibility are geographically distributed, team call presents the most suitable solution.</span></span> <span data-ttu-id="2f32f-112">グループ通話ピックアップとチーム通話の主な違いは、グループ通話ピックアップでは、着信呼び出しは目的の宛先でのみ鳴りますが、誰でもグループ番号をダイヤルして応答できる点です。</span><span class="sxs-lookup"><span data-stu-id="2f32f-112">The primary difference between Group Call Pickup and team call is that, with Group Call Pickup, an incoming call rings only at the intended destination, but anyone can still choose to answer it by dialing a group number.</span></span> <span data-ttu-id="2f32f-113">チーム通話では、すべてのチーム メンバーの電話で通話が鳴り、チーム内の任意のユーザーが電話を受け取って通話に応答できます。</span><span class="sxs-lookup"><span data-stu-id="2f32f-113">With team call, the call rings at all the team members' phones, and any user in the team can pick up the phone to answer the call.</span></span> <span data-ttu-id="2f32f-114">グループ通話ピックアップとチーム通話の別の違いは、グループ通話ピックアップは Skype for Business Server を通じて管理者によって管理される点です。</span><span class="sxs-lookup"><span data-stu-id="2f32f-114">An additional difference between Group Call Pickup and team call is that Group Call Pickup is managed by an administrator, through Skype for Business Server.</span></span> <span data-ttu-id="2f32f-115">チーム通話では、エンド ユーザーは Skype for Business クライアントを使用して機能を管理します。</span><span class="sxs-lookup"><span data-stu-id="2f32f-115">With team call, end users manage the feature by using the Skype for Business client.</span></span> <span data-ttu-id="2f32f-116">したがって、グループ通話ピックアップを使用すると、通話管理のこの側面を一元化できます。</span><span class="sxs-lookup"><span data-stu-id="2f32f-116">With Group Call Pickup, therefore, this aspect of call management can be centralized.</span></span>
  
<span data-ttu-id="2f32f-117">グループ通話ピックアップはコール パーク アプリケーション上に構築されます。</span><span class="sxs-lookup"><span data-stu-id="2f32f-117">Group Call Pickup is built on the Call Park application.</span></span> <span data-ttu-id="2f32f-118">グループ通話ピックアップを展開する場合は、通話ピックアップ グループ番号として指定される個別の内線番号の範囲でコール パーク オービット テーブルを構成します。</span><span class="sxs-lookup"><span data-stu-id="2f32f-118">When you deploy Group Call Pickup, you configure the call park orbit table with separate ranges of extension numbers that are designated as call pickup group numbers.</span></span> <span data-ttu-id="2f32f-119">コール パーク オービット番号と同様に、通話ピックアップ グループ番号は、ユーザーまたは電話が割り当てられていない仮想内線番号である必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f32f-119">Like call park orbit numbers, call pickup group numbers must be virtual extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="2f32f-120">グループ通話ピックアップを展開する各フロントエンド プールには、1 つ以上の通話ピックアップ グループ番号の範囲を設定できます。</span><span class="sxs-lookup"><span data-stu-id="2f32f-120">Each Front End pool where you deploy Group Call Pickup can have one or more ranges of call pickup group numbers.</span></span> <span data-ttu-id="2f32f-121">グループ番号の範囲は、Skype for Business Server 展開全体でグローバルに一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f32f-121">The group number ranges must be globally unique across the Skype for Business Server deployment.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="2f32f-122">コール パーク オービット テーブルでグループ通話ピックアップ番号として指定されている番号範囲は、Skype for Business Server コントロール パネルを使用して管理または表示することはできません。</span><span class="sxs-lookup"><span data-stu-id="2f32f-122">Number ranges that are designated as Group Call Pickup numbers in the call park orbit table cannot be managed or viewed by using the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="2f32f-123">コール パーク オービット テーブル内のすべての番号範囲を表示する唯一の方法は、Skype for Business Server 管理シェルを使用する方法です。</span><span class="sxs-lookup"><span data-stu-id="2f32f-123">The only way to see all the number ranges in the call park orbit table is to use Skype for Business Server Management Shell.</span></span> <span data-ttu-id="2f32f-124">同様に、グループ通話ピックアップ番号を追加、変更、または削除する唯一の方法は、Skype for Business Server 管理シェルを使用する方法です。</span><span class="sxs-lookup"><span data-stu-id="2f32f-124">Similarly, the only way to add, modify, or remove Group Call Pickup numbers is to use Skype for Business Server Management Shell.</span></span> 
  
<span data-ttu-id="2f32f-125">通話ピックアップ グループ番号を構成した後、通話ピックアップ グループにユーザーを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f32f-125">After you configure the call pickup group numbers, you assign users to a call pickup group.</span></span> <span data-ttu-id="2f32f-126">通話ピックアップ グループに割り当てられているすべてのユーザーは、他のユーザーが通話に応答できます。</span><span class="sxs-lookup"><span data-stu-id="2f32f-126">Any user who is assigned to a call pickup group can have their calls answered by other users.</span></span> <span data-ttu-id="2f32f-127">通話ピックアップ グループに割り当てられているユーザーに通話が発信された場合、その通話に気付いた他のユーザーは、通話ピックアップ グループ番号を手動でダイヤルして応答できます。</span><span class="sxs-lookup"><span data-stu-id="2f32f-127">When a call comes in to a user who is assigned to a call pickup group, any other user who notices the call can answer it by manually dialing the call pickup group number.</span></span> <span data-ttu-id="2f32f-128">通話を受け取るユーザーは、グループのメンバーである必要はない。</span><span class="sxs-lookup"><span data-stu-id="2f32f-128">The user who picks up the call does not need to be a member of the group.</span></span> <span data-ttu-id="2f32f-129">別のユーザーが通話を受け取ると、最初に呼び出された番号に通知が送信されます。</span><span class="sxs-lookup"><span data-stu-id="2f32f-129">When a call is picked up by another user, a notification is sent to the number originally called.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2f32f-130">ユーザーは、1 つの通話ピックアップ グループのメンバーになじむ必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f32f-130">A user can be a member of only one call pickup group.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="2f32f-131">Skype for Business Server 展開のユーザーは通話ピックアップ グループ のメンバーへの通話に応答することができますが、通話に応答するユーザーは、ダイヤルする正しい通話ピックアップ グループ番号を知っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f32f-131">Although any user in the Skype for Business Server deployment can answer a call to a call pickup group member, the person answering the call must know the correct call pickup group number to dial.</span></span> 
  
<span data-ttu-id="2f32f-132">ユーザーが、グループ内の複数の電話が呼び出し音を鳴らしているときに通話に応答するために通話ピックアップ グループ番号をダイヤルすると、最も長く呼び出し音が鳴っている通話に応答します。</span><span class="sxs-lookup"><span data-stu-id="2f32f-132">If a user dials a call pickup group number to answer a call when multiple phones in the group are ringing, the user answers the call that has been ringing the longest.</span></span>
  
<span data-ttu-id="2f32f-133">同時呼び出し設定は、グループ通話ピックアップを使用しているユーザーに対して機能します。</span><span class="sxs-lookup"><span data-stu-id="2f32f-133">Simultaneous ringing settings will work for users who have group call pickup.</span></span> <span data-ttu-id="2f32f-134">つまり、グループ通話ピックアップを持つユーザーに対して行われた通話は、構成済みのすべての宛先に対して呼び出され、別のユーザーが通話に応答できます。</span><span class="sxs-lookup"><span data-stu-id="2f32f-134">That is, a call made to a user who has Group Call Pickup will ring for all the configured destinations, and another user can answer the call.</span></span> <span data-ttu-id="2f32f-135">このルールの例外は、ユーザーがすべてのチーム メンバーを呼び出す同時呼び出しを構成する場合です。</span><span class="sxs-lookup"><span data-stu-id="2f32f-135">The exception to this rule is when the user configures simultaneous ringing to call all the team members.</span></span>
  
<span data-ttu-id="2f32f-136">グループ通話ピックアップを使用して、次の種類の通話に応答することはできません。</span><span class="sxs-lookup"><span data-stu-id="2f32f-136">Group Call Pickup cannot be used to answer the following types of calls:</span></span>
  
- <span data-ttu-id="2f32f-137">プライベート回線への呼び出し</span><span class="sxs-lookup"><span data-stu-id="2f32f-137">Calls to a private line</span></span>
    
- <span data-ttu-id="2f32f-138">友人と家族のプライバシー関係が割り当てられている連絡先からの呼び出し</span><span class="sxs-lookup"><span data-stu-id="2f32f-138">Calls from a contact who has been assigned the Friends and Family privacy relationship</span></span>
    
    > [!TIP]
    > <span data-ttu-id="2f32f-139">通話ピックアップ グループのメンバーであるユーザーは、Skype for Business クライアントで連絡先を個人連絡先としてマークすることで、グループ通話ピックアップを通じて特定の通話を取得できなくなります。</span><span class="sxs-lookup"><span data-stu-id="2f32f-139">A user who is a member of a call pickup group can prevent certain calls from being retrieved through Group Call Pickup by marking the contact as a personal contact in the Skype for Business client.</span></span> <span data-ttu-id="2f32f-140">連絡先を個人用連絡先としてマークするには、連絡先のプライバシー関係を [友人と家族] に設定します。</span><span class="sxs-lookup"><span data-stu-id="2f32f-140">To mark a contact as a personal contact, set the Privacy Relationship for the contact to Friends and Family.</span></span> <span data-ttu-id="2f32f-141">プライバシー関係が [友人と家族] に設定されている連絡先からの着信は、グループ通話ピックアップを使用して取得できません。</span><span class="sxs-lookup"><span data-stu-id="2f32f-141">Any incoming call from contacts with the Privacy Relationship set to Friends and Family cannot be retrieved by using Group Call Pickup.</span></span> 
  
- <span data-ttu-id="2f32f-142">音声ビデオ通話のビデオ部分</span><span class="sxs-lookup"><span data-stu-id="2f32f-142">Video portion of audio/video calls</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="2f32f-143">ユーザーが音声/ビデオ通話に応答すると、音声のみを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="2f32f-143">If a user answers an audio/video call, the user receives only the audio.</span></span> <span data-ttu-id="2f32f-144">通話するユーザーまたは通話に応答したユーザーは、通話をエスカレートしてビデオを追加できます。</span><span class="sxs-lookup"><span data-stu-id="2f32f-144">Either the person calling or the person answering the call can escalate the call to add video.</span></span> 
  
- <span data-ttu-id="2f32f-145">チーム呼び出しメンバーにルーティングされる同時呼び出し</span><span class="sxs-lookup"><span data-stu-id="2f32f-145">Simultaneous ringing calls that are routed to team call members</span></span>
    
- <span data-ttu-id="2f32f-146">代理人にルーティングされた通話</span><span class="sxs-lookup"><span data-stu-id="2f32f-146">Calls routed to a delegate</span></span>
    
- <span data-ttu-id="2f32f-147">応答グループにルーティングされた通話</span><span class="sxs-lookup"><span data-stu-id="2f32f-147">Calls routed to a response group</span></span>
    
<span data-ttu-id="2f32f-148">次の種類のユーザーは、グループ通話ピックアップに参加できません。</span><span class="sxs-lookup"><span data-stu-id="2f32f-148">The following types of users cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="2f32f-149">つまり、グループ通話ピックアップ グループに含めず、グループ通話ピックアップが有効になっているユーザーの通話を受け取る必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f32f-149">That is, they should not be included in a Group Call Pickup group, and they cannot pick up calls for users who have Group Call Pickup enabled.</span></span>
  
- <span data-ttu-id="2f32f-150">ハイブリッド展開でオンラインに配置されているユーザー</span><span class="sxs-lookup"><span data-stu-id="2f32f-150">Users who are homed online in a hybrid deployment</span></span>
    
- <span data-ttu-id="2f32f-151">Skype for Business Server 2015 プールまたは Lync Server 2013 の累積的な更新プログラムが適用された Lync Server 2013 プールにホームではないユーザー: オンプレミス展開での 2013 年 2 月</span><span class="sxs-lookup"><span data-stu-id="2f32f-151">Users who are not homed on either a Skype for Business Server 2015 pool or a Lync Server 2013 pool with Cumulative Updates for Lync Server 2013: February 2013 in an on-premises deployment</span></span>
    
<span data-ttu-id="2f32f-152">通話ピックアップ グループのメンバーへの通話に誰も応答しない場合、その通話はクライアント設定で指定された方法でルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="2f32f-152">If no one answers a call to a member of a call pickup group, the call is routed as specified in the client settings.</span></span> <span data-ttu-id="2f32f-153">つまり、通話はボイスメールに送信され、クライアント設定で指定されている別の宛先に転送されます。</span><span class="sxs-lookup"><span data-stu-id="2f32f-153">That is, the call goes to voicemail or is forwarded to a different destination, as specified in the client settings.</span></span>
  
## <a name="deployment-and-requirements"></a><span data-ttu-id="2f32f-154">展開と要件</span><span class="sxs-lookup"><span data-stu-id="2f32f-154">Deployment and requirements</span></span>

<span data-ttu-id="2f32f-155">グループ通話ピックアップは、グループ通話ピックアップとコール エンタープライズ VoIP展開すると自動的に展開されます。</span><span class="sxs-lookup"><span data-stu-id="2f32f-155">Group Call Pickup is automatically deployed when you deploy Enterprise Voice and the Call Park application.</span></span> <span data-ttu-id="2f32f-156">グループ通話ピックアップを有効にするには、通話ピックアップ グループ番号として指定された個別の番号範囲でコール パーク オービット テーブルを構成し、次に、ユーザーを通話ピックアップ グループに割り当て、ユーザーにグループ通話ピックアップを有効にすることで有効にできます。</span><span class="sxs-lookup"><span data-stu-id="2f32f-156">You enable Group Call Pickup by configuring the Call Park orbit table with separate ranges of numbers designated as call pickup group numbers, and then by assigning users to call pickup groups and enabling the users for Group Call Pickup.</span></span>
  
## <a name="clients-supported-for-group-call-pickup"></a><span data-ttu-id="2f32f-157">グループ通話ピックアップでサポートされるクライアント</span><span class="sxs-lookup"><span data-stu-id="2f32f-157">Clients supported for Group Call Pickup</span></span>

<span data-ttu-id="2f32f-158">次のクライアントを使用して、グループ通話ピックアップ メンバーへの通話に応答できます。</span><span class="sxs-lookup"><span data-stu-id="2f32f-158">Any of the following clients can be used to answer calls to Group Call Pickup members:</span></span>
  
- <span data-ttu-id="2f32f-159">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="2f32f-159">Skype for Business</span></span>
    
- <span data-ttu-id="2f32f-160">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="2f32f-160">Lync 2013</span></span>
    
- <span data-ttu-id="2f32f-161">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="2f32f-161">Lync 2010</span></span>
    
- <span data-ttu-id="2f32f-162">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="2f32f-162">Lync Phone Edition</span></span>
    
> [!NOTE]
> <span data-ttu-id="2f32f-163">ユーザーは、これらのクライアントを使用してグループ通話ピックアップ メンバーへの通話に応答できますが、ユーザーは Skype for Business Server プールまたは Lync Server 2013 の累積的な更新プログラムが適用された Lync Server 2013 プール (2013 年 2 月) にホームとして参加している必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f32f-163">Users can use any of these clients to answer calls to Group Call Pickup members, but the users must be homed on a Skype for Business Server pool or a Lync Server 2013 pool with Cumulative Updates for Lync Server 2013: February 2013.</span></span> 
  
<span data-ttu-id="2f32f-164">次のクライアントとデバイスは、グループ通話ピックアップ メンバーへの通話を受け取る場合はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="2f32f-164">The following clients and devices are not supported for picking up calls to Group Call Pickup members:</span></span>
  
- <span data-ttu-id="2f32f-165">Lync Mobile</span><span class="sxs-lookup"><span data-stu-id="2f32f-165">Lync Mobile</span></span>
    
- <span data-ttu-id="2f32f-166">Windows 8 および Windows RT 用の Lync アプリ</span><span class="sxs-lookup"><span data-stu-id="2f32f-166">Lync app for Windows 8 and Windows RT</span></span>
    
- <span data-ttu-id="2f32f-167">Lync for iPad</span><span class="sxs-lookup"><span data-stu-id="2f32f-167">Lync for iPad</span></span>
    
- <span data-ttu-id="2f32f-168">アナログ電話</span><span class="sxs-lookup"><span data-stu-id="2f32f-168">Analog phones</span></span>
    
- <span data-ttu-id="2f32f-169">公衆交換電話網 (PSTN) 番号を持つ電話</span><span class="sxs-lookup"><span data-stu-id="2f32f-169">Phones with public switched telephone network (PSTN) numbers</span></span>
    
## <a name="capacity-planning"></a><span data-ttu-id="2f32f-170">キャパシティ プランニング</span><span class="sxs-lookup"><span data-stu-id="2f32f-170">Capacity planning</span></span>

<span data-ttu-id="2f32f-171">次の表では、容量計画の要件の基礎として使用できるグループ通話ピックアップのユーザー モデルについて説明します。</span><span class="sxs-lookup"><span data-stu-id="2f32f-171">The following table describes the Group Call Pickup user model that you can use as the basis for capacity planning requirements.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="2f32f-172">グループ通話ピックアップはコール パーク アプリケーションに基づいて作成されます。</span><span class="sxs-lookup"><span data-stu-id="2f32f-172">Group Call Pickup is based on the Call Park application.</span></span> <span data-ttu-id="2f32f-173">障害復旧の処理能力の計画では、ペアのプールの各プールが、両方のプールのコール パーク サービス (グループ通話ピックアップを含む) のワークロードを処理できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f32f-173">Keep in mind that, for disaster recovery capacity planning, each pool of a paired pool should be able to handle the workloads for Call Park services, including Group Call Pickup, in both pools.</span></span> 
  
<span data-ttu-id="2f32f-174">**グループ通話ピックアップのユーザー モデル**</span><span class="sxs-lookup"><span data-stu-id="2f32f-174">**Group Call Pickup User Model**</span></span>

|<span data-ttu-id="2f32f-175">**測定基準**</span><span class="sxs-lookup"><span data-stu-id="2f32f-175">**Metric**</span></span>|<span data-ttu-id="2f32f-176">**フロント エンド プールごとに  <br/>  (8 つのフロントエンド サーバーを使用)**</span><span class="sxs-lookup"><span data-stu-id="2f32f-176">**Per Front End pool  <br/>  (with 8 Front End Servers)**</span></span>|<span data-ttu-id="2f32f-177">**Standard Edition サーバーごとに**</span><span class="sxs-lookup"><span data-stu-id="2f32f-177">**Per Standard Edition server**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2f32f-178">グループごとの推奨ユーザー数</span><span class="sxs-lookup"><span data-stu-id="2f32f-178">Recommended number of users per group</span></span>  <br/> |<span data-ttu-id="2f32f-179">50</span><span class="sxs-lookup"><span data-stu-id="2f32f-179">50</span></span>  <br/> |<span data-ttu-id="2f32f-180">50</span><span class="sxs-lookup"><span data-stu-id="2f32f-180">50</span></span>  <br/> |
|<span data-ttu-id="2f32f-181">推奨されるグループ数</span><span class="sxs-lookup"><span data-stu-id="2f32f-181">Recommended number of groups</span></span>  <br/> |<span data-ttu-id="2f32f-182">500</span><span class="sxs-lookup"><span data-stu-id="2f32f-182">500</span></span>  <br/> |<span data-ttu-id="2f32f-183">60</span><span class="sxs-lookup"><span data-stu-id="2f32f-183">60</span></span>  <br/> |
|<span data-ttu-id="2f32f-184">グループ通話ピックアップが有効なプールごとの最大ユーザー数</span><span class="sxs-lookup"><span data-stu-id="2f32f-184">Maximum number of users per pool enabled for Group Call Pickup</span></span>  <br/> |<span data-ttu-id="2f32f-185">25,000</span><span class="sxs-lookup"><span data-stu-id="2f32f-185">25,000</span></span>  <br/> |<span data-ttu-id="2f32f-186">3,000</span><span class="sxs-lookup"><span data-stu-id="2f32f-186">3,000</span></span>  <br/> |
|<span data-ttu-id="2f32f-187">1 分あたりのプールあたりのグループ通話ピックアップが有効な合計ユーザーに対する着信呼び出しの最大レート</span><span class="sxs-lookup"><span data-stu-id="2f32f-187">Maximum rate of incoming calls to total users enabled for Group Call Pickup per pool per minute</span></span>  <br/> |<span data-ttu-id="2f32f-188">500</span><span class="sxs-lookup"><span data-stu-id="2f32f-188">500</span></span>  <br/> |<span data-ttu-id="2f32f-189">60</span><span class="sxs-lookup"><span data-stu-id="2f32f-189">60</span></span>  <br/> |
|<span data-ttu-id="2f32f-190">1 分あたりのプールあたりのグループ通話ピックアップを使用するユーザーが取得する通話の最大レート</span><span class="sxs-lookup"><span data-stu-id="2f32f-190">Maximum rate of calls retrieved by users with Group Call Pickup per pool per minute</span></span>  <br/> |<span data-ttu-id="2f32f-191">200</span><span class="sxs-lookup"><span data-stu-id="2f32f-191">200</span></span>  <br/> |<span data-ttu-id="2f32f-192">25</span><span class="sxs-lookup"><span data-stu-id="2f32f-192">25</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="2f32f-193">フロントエンド サーバーが 8 台未満のフロント エンド プールの場合は、メトリックを直線的に計算します。</span><span class="sxs-lookup"><span data-stu-id="2f32f-193">For Front End pools that have fewer than eight Front End Servers, calculate the metrics linearly.</span></span> <span data-ttu-id="2f32f-194">たとえば、フロントエンド プールに 1 台のフロントエンド サーバーがある場合は、表に示されている値の 1/8 として最大負荷を計算します。</span><span class="sxs-lookup"><span data-stu-id="2f32f-194">For example, if your Front End pool has one Front End Server, calculate the maximum load as 1/8 of the values shown in the table.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="2f32f-195">プールごとの最大ユーザー数を超えない限り、グループあたりの推奨ユーザー数とグループ数を増減できます。</span><span class="sxs-lookup"><span data-stu-id="2f32f-195">You can increase or decrease the recommended number of users per group and number of groups as long as you do not exceed the maximum number of users per pool.</span></span> <span data-ttu-id="2f32f-196">たとえば、グループ通話ピックアップが有効なユーザーの数がユーザー モデルの最大数 (つまり、25 ユーザーの 120 グループはグループ通話ピックアップが有効な 3,000 ユーザー) 内にあるため、Standard Edition サーバーはグループごとに 25 ユーザーのグループを持つ 120 グループを持つ可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2f32f-196">For example, your Standard Edition server can have 120 groups with 25 users per group because the number of users enabled for Group Call Pickup is still within the user model maximum (that is, 120 groups times 25 users is 3,000 users enabled for Group Call Pickup).</span></span> 
  

