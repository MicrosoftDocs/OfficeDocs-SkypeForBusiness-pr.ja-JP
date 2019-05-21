---
title: Skype for Business のグループ通話のピックアップを計画する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3dc0eca8-c773-463c-96bb-9cd6afa2a840
description: Skype for Business Server Enterprise Voice でグループ通話のピックアップを計画しています。これにより、ユーザーは、他のユーザーに対して元々意図した通話に応答することができます。
ms.openlocfilehash: c729e2d672d104337820c44fa41c113dded3110f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34276839"
---
# <a name="plan-for-group-call-pickup-in-skype-for-business"></a><span data-ttu-id="a2007-103">Skype for Business のグループ通話のピックアップを計画する</span><span class="sxs-lookup"><span data-stu-id="a2007-103">Plan for Group Call Pickup in Skype for Business</span></span>
 
<span data-ttu-id="a2007-104">Skype for Business Server Enterprise Voice でグループ通話のピックアップを計画しています。これにより、ユーザーは、他のユーザーに対して元々意図した通話に応答することができます。</span><span class="sxs-lookup"><span data-stu-id="a2007-104">Planning for Group Call Pickup in Skype for Business Server Enterprise Voice, which enables users to answer calls originally intended for others.</span></span>
  
<span data-ttu-id="a2007-105">グループ通話のピックアップを使用すると、ユーザーは自分の電話から同僚への着信に応答できます。</span><span class="sxs-lookup"><span data-stu-id="a2007-105">Group Call Pickup enables users to answer incoming calls to their colleagues from their own phones.</span></span> <span data-ttu-id="a2007-106">これにより、他のユーザーが通話ピックアップグループ番号にダイヤルすることによって着信に応答できるようになり、ユーザーの回線の可用性が向上します。</span><span class="sxs-lookup"><span data-stu-id="a2007-106">This increases the availability of a user's line by enabling other users to answer an incoming call by dialing a call pickup group number.</span></span> <span data-ttu-id="a2007-107">グループ通話のピックアップが展開されると、ボイスメールにルーティングされる着信の数が大幅に減少する可能性があります。これは、組織外のユーザーからの通話に特に便利です。</span><span class="sxs-lookup"><span data-stu-id="a2007-107">When Group Call Pickup is deployed, the number of incoming calls that are routed to voice mail can be significantly reduced, which is particularly useful for calls from customers who are external to your organization.</span></span>
  
<span data-ttu-id="a2007-108">グループ通話の集配機能は、office を開いている環境のビジネスユニット向けに設計されています。</span><span class="sxs-lookup"><span data-stu-id="a2007-108">The Group Call Pickup feature is designed in particular for business units in open office environments.</span></span> <span data-ttu-id="a2007-109">着信通話は、意図した宛先にのみ着信するため、中断されません。</span><span class="sxs-lookup"><span data-stu-id="a2007-109">Incoming calls are not disruptive because they ring only at the intended destination.</span></span> <span data-ttu-id="a2007-110">ただし、リングを聞く他のユーザーは、グループ番号にダイヤルするだけで通話を受けることができます。</span><span class="sxs-lookup"><span data-stu-id="a2007-110">Other users who hear the ring, however, can still pick up the call simply by dialing the group number.</span></span> 
  
<span data-ttu-id="a2007-111">ユーザーのオフィスのレイアウトがオープンでない場合、または地理的に分散された複数のユーザーが一般的な業務を分担している場合は、チーム呼び出しによって最適なソリューションが実現します。</span><span class="sxs-lookup"><span data-stu-id="a2007-111">In environments where users are not located in an open office layout, or where users who share a common responsibility are geographically distributed, team call presents the most suitable solution.</span></span> <span data-ttu-id="a2007-112">グループ通話の集配とチーム呼び出しの主な違いは、グループ通話のピックアップによって着信が発信された場合に限られます。ただし、グループ番号をダイヤルすることによって応答できます。</span><span class="sxs-lookup"><span data-stu-id="a2007-112">The primary difference between Group Call Pickup and team call is that, with Group Call Pickup, an incoming call rings only at the intended destination, but anyone can still choose to answer it by dialing a group number.</span></span> <span data-ttu-id="a2007-113">GroupCallPickupでは、呼び出し音は着信先でしか鳴りませんが、グループ番号をダイヤルすればだれでも電話をとれます。</span><span class="sxs-lookup"><span data-stu-id="a2007-113">With team call, the call rings at all the team members' phones, and any user in the team can pick up the phone to answer the call.</span></span> <span data-ttu-id="a2007-114">グループ通話のピックアップとチーム呼び出しの違いは、グループ通話のピックアップが Skype for Business Server を使用して管理者によって管理されていることです。</span><span class="sxs-lookup"><span data-stu-id="a2007-114">An additional difference between Group Call Pickup and team call is that Group Call Pickup is managed by an administrator, through Skype for Business Server.</span></span> <span data-ttu-id="a2007-115">チーム通話では、エンドユーザーが Skype for Business クライアントを使用して機能を管理します。</span><span class="sxs-lookup"><span data-stu-id="a2007-115">With team call, end users manage the feature by using the Skype for Business client.</span></span> <span data-ttu-id="a2007-116">このため、グループ通話のピックアップでは、この通話管理の局面を一元管理できます。</span><span class="sxs-lookup"><span data-stu-id="a2007-116">With Group Call Pickup, therefore, this aspect of call management can be centralized.</span></span>
  
<span data-ttu-id="a2007-117">グループ通話のピックアップは、コールパークアプリケーションに基づいて構築されます。</span><span class="sxs-lookup"><span data-stu-id="a2007-117">Group Call Pickup is built on the Call Park application.</span></span> <span data-ttu-id="a2007-118">グループ通話のピックアップを展開するときに、通話集配グループ番号として指定されている内線番号の別の範囲を使用して、コールパーク軌道テーブルを構成します。</span><span class="sxs-lookup"><span data-stu-id="a2007-118">When you deploy Group Call Pickup, you configure the call park orbit table with separate ranges of extension numbers that are designated as call pickup group numbers.</span></span> <span data-ttu-id="a2007-119">コール パーク オービット番号と同様、通話ピックアップ グループ番号は、ユーザーも電話も割り当てられていない仮想内線である必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2007-119">Like call park orbit numbers, call pickup group numbers must be virtual extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="a2007-120">グループ通話のピックアップを展開する各フロントエンドプールには、1つ以上の通話ピックアップグループ番号が含まれていることがあります。</span><span class="sxs-lookup"><span data-stu-id="a2007-120">Each Front End pool where you deploy Group Call Pickup can have one or more ranges of call pickup group numbers.</span></span> <span data-ttu-id="a2007-121">グループ番号の範囲は、Skype for Business Server の展開でグローバルに一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2007-121">The group number ranges must be globally unique across the Skype for Business Server deployment.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="a2007-122">通話パークの軌道番号として指定された番号範囲は、Skype for Business Server コントロールパネルを使って管理または表示することはできません。</span><span class="sxs-lookup"><span data-stu-id="a2007-122">Number ranges that are designated as Group Call Pickup numbers in the call park orbit table cannot be managed or viewed by using the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="a2007-123">コールパークの軌道のすべての番号範囲を表示する唯一の方法は、Skype for Business Server Management Shell を使用することです。</span><span class="sxs-lookup"><span data-stu-id="a2007-123">The only way to see all the number ranges in the call park orbit table is to use Skype for Business Server Management Shell.</span></span> <span data-ttu-id="a2007-124">同様に、グループ通話の集配番号を追加、変更、または削除するには、Skype for Business Server 管理シェルを使用する方法しかありません。</span><span class="sxs-lookup"><span data-stu-id="a2007-124">Similarly, the only way to add, modify, or remove Group Call Pickup numbers is to use Skype for Business Server Management Shell.</span></span> 
  
<span data-ttu-id="a2007-p106">通話ピックアップ グループ番号を構成したら、ユーザーを通話ピックアップ グループに割り当てます。通話ピックアップ グループに割り当てられたユーザーにかかってきた電話は、他のユーザーがとることができます。通話ピックアップ グループに割り当てられたユーザーに電話がかかってきたときに、その電話に気が付いた他のユーザーが電話をとるには、通話ピックアップ グループ番号に手動でダイヤルします。電話をとるユーザーは、そのグループのメンバーである必要はありません。他のユーザーが電話をとると、電話がかかってきた番号に通知が送信されます。</span><span class="sxs-lookup"><span data-stu-id="a2007-p106">After you configure the call pickup group numbers, you assign users to a call pickup group. Any user who is assigned to a call pickup group can have their calls answered by other users. When a call comes in to a user who is assigned to a call pickup group, any other user who notices the call can answer it by manually dialing the call pickup group number. The user who picks up the call does not need to be a member of the group. When a call is picked up by another user, a notification is sent to the number originally called.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a2007-130">ユーザーがメンバーになれるのは、1 つの通話ピックアップ グループだけです。</span><span class="sxs-lookup"><span data-stu-id="a2007-130">A user can be a member of only one call pickup group.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="a2007-131">Skype for Business Server の展開では、通話のピックアップグループメンバーへの通話に応答できますが、通話に応答するユーザーは、ダイヤルする適切な通話ピックアップグループ番号を知っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2007-131">Although any user in the Skype for Business Server deployment can answer a call to a call pickup group member, the person answering the call must know the correct call pickup group number to dial.</span></span> 
  
<span data-ttu-id="a2007-132">グループ内の複数の電話の呼び出し音が鳴っている場合、ユーザーが通話ピックアップ グループ番号をダイヤルして電話をとると、一番長く呼び出し音が鳴っている電話につながります。</span><span class="sxs-lookup"><span data-stu-id="a2007-132">If a user dials a call pickup group number to answer a call when multiple phones in the group are ringing, the user answers the call that has been ringing the longest.</span></span>
  
<span data-ttu-id="a2007-133">同時呼び出しの設定は、グループ通話ピックアップを利用しているユーザーに対して有効です。</span><span class="sxs-lookup"><span data-stu-id="a2007-133">Simultaneous ringing settings will work for users who have group call pickup.</span></span> <span data-ttu-id="a2007-134">つまり、グループ通話のピックアップを持っているユーザに発信された通話は、設定されているすべての宛先に対して呼び出しを行い、別のユーザが通話に応答することができます。</span><span class="sxs-lookup"><span data-stu-id="a2007-134">That is, a call made to a user who has Group Call Pickup will ring for all the configured destinations, and another user can answer the call.</span></span> <span data-ttu-id="a2007-135">ただし、すべてのチーム メンバーを呼び出すようにユーザーが同時呼び出しを構成している場合、このルールは適用されません。</span><span class="sxs-lookup"><span data-stu-id="a2007-135">The exception to this rule is when the user configures simultaneous ringing to call all the team members.</span></span>
  
<span data-ttu-id="a2007-136">グループ通話のピックアップを使用して、次の種類の通話に応答することはできません。</span><span class="sxs-lookup"><span data-stu-id="a2007-136">Group Call Pickup cannot be used to answer the following types of calls:</span></span>
  
- <span data-ttu-id="a2007-137">プライベート回線の呼び出し</span><span class="sxs-lookup"><span data-stu-id="a2007-137">Calls to a private line</span></span>
    
- <span data-ttu-id="a2007-138">[友人および家族] プライバシー関係に割り当てられた連絡先からの呼び出し</span><span class="sxs-lookup"><span data-stu-id="a2007-138">Calls from a contact who has been assigned the Friends and Family privacy relationship</span></span>
    
    > [!TIP]
    > <span data-ttu-id="a2007-139">通話ピックアップグループのメンバーであるユーザーは、Skype for Business クライアントで連絡先を個人の連絡先としてマークすることによって、グループ通話のピックアップによって特定の着信が取得されないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="a2007-139">A user who is a member of a call pickup group can prevent certain calls from being retrieved through Group Call Pickup by marking the contact as a personal contact in the Skype for Business client.</span></span> <span data-ttu-id="a2007-140">連絡先を個人連絡先としてマークするには、そのプライバシー関係を [友人および家族] に設定します。</span><span class="sxs-lookup"><span data-stu-id="a2007-140">To mark a contact as a personal contact, set the Privacy Relationship for the contact to Friends and Family.</span></span> <span data-ttu-id="a2007-141">プライバシー関係が設定されている連絡先からの着信通話は、グループ通話のピックアップを使って取得することはできません。</span><span class="sxs-lookup"><span data-stu-id="a2007-141">Any incoming call from contacts with the Privacy Relationship set to Friends and Family cannot be retrieved by using Group Call Pickup.</span></span> 
  
- <span data-ttu-id="a2007-142">音声ビデオ通話のビデオ部分</span><span class="sxs-lookup"><span data-stu-id="a2007-142">Video portion of audio/video calls</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="a2007-p109">音声ビデオ通話については、ユーザーは音声のみを受け取ります。電話をかけたユーザーまたは電話をとったユーザーのどちらかが、通話をエスカレートして、ビデオを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="a2007-p109">If a user answers an audio/video call, the user receives only the audio. Either the person calling or the person answering the call can escalate the call to add video.</span></span> 
  
- <span data-ttu-id="a2007-145">チーム呼び出しメンバーにルーティングされた同時呼び出し</span><span class="sxs-lookup"><span data-stu-id="a2007-145">Simultaneous ringing calls that are routed to team call members</span></span>
    
- <span data-ttu-id="a2007-146">代理人にルーティングされた呼び出し</span><span class="sxs-lookup"><span data-stu-id="a2007-146">Calls routed to a delegate</span></span>
    
- <span data-ttu-id="a2007-147">応答グループにルーティングされた呼び出し</span><span class="sxs-lookup"><span data-stu-id="a2007-147">Calls routed to a response group</span></span>
    
<span data-ttu-id="a2007-148">次の種類のユーザーはグループ通話のピックアップに参加できません。</span><span class="sxs-lookup"><span data-stu-id="a2007-148">The following types of users cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="a2007-149">つまり、グループ通話のピックアップグループに含まれておらず、グループ通話のピックアップが有効になっているユーザーに対して通話を受信することはできません。</span><span class="sxs-lookup"><span data-stu-id="a2007-149">That is, they should not be included in a Group Call Pickup group, and they cannot pick up calls for users who have Group Call Pickup enabled.</span></span>
  
- <span data-ttu-id="a2007-150">ハイブリッド環境の常時オンラインのユーザー</span><span class="sxs-lookup"><span data-stu-id="a2007-150">Users who are homed online in a hybrid deployment</span></span>
    
- <span data-ttu-id="a2007-151">Lync Server 2013 の累積更新プログラムが含まれている Skype for Business Server 2015 プールまたは Lync Server 2013 プールをホームにしていないユーザー: オンプレミスの展開では 2013 2 月</span><span class="sxs-lookup"><span data-stu-id="a2007-151">Users who are not homed on either a Skype for Business Server 2015 pool or a Lync Server 2013 pool with Cumulative Updates for Lync Server 2013: February 2013 in an on-premises deployment</span></span>
    
<span data-ttu-id="a2007-p111">通話ピックアップ グループのメンバーへの電話をだれもとらない場合、その電話は、クライアント設定で指定されているようにルーティングされます。つまり、呼び出しはボイスメールに送られるか、クライアント設定で指定されているように、別の宛先に転送されます。</span><span class="sxs-lookup"><span data-stu-id="a2007-p111">If no one answers a call to a member of a call pickup group, the call is routed as specified in the client settings. That is, the call goes to voicemail or is forwarded to a different destination, as specified in the client settings.</span></span>
  
## <a name="deployment-and-requirements"></a><span data-ttu-id="a2007-154">展開と要件</span><span class="sxs-lookup"><span data-stu-id="a2007-154">Deployment and requirements</span></span>

<span data-ttu-id="a2007-155">グループ通話のピックアップは、エンタープライズボイスと Call パークアプリケーションを展開したときに自動的に展開されます。</span><span class="sxs-lookup"><span data-stu-id="a2007-155">Group Call Pickup is automatically deployed when you deploy Enterprise Voice and the Call Park application.</span></span> <span data-ttu-id="a2007-156">グループ通話のピックアップを有効にするには、通話ピックアップグループ番号として指定された別の範囲の番号を使用して、ユーザーをピックアップグループに発信し、グループ通話のピックアップを許可するようにユーザーを割り当てることで、グループ通話のピックアップを有効にします。</span><span class="sxs-lookup"><span data-stu-id="a2007-156">You enable Group Call Pickup by configuring the Call Park orbit table with separate ranges of numbers designated as call pickup group numbers, and then by assigning users to call pickup groups and enabling the users for Group Call Pickup.</span></span>
  
## <a name="clients-supported-for-group-call-pickup"></a><span data-ttu-id="a2007-157">グループ通話のピックアップ用にサポートされるクライアント</span><span class="sxs-lookup"><span data-stu-id="a2007-157">Clients supported for Group Call Pickup</span></span>

<span data-ttu-id="a2007-158">グループ通話のピックアップメンバーの呼び出しに応答するために、次のいずれかのクライアントを使うことができます。</span><span class="sxs-lookup"><span data-stu-id="a2007-158">Any of the following clients can be used to answer calls to Group Call Pickup members:</span></span>
  
- <span data-ttu-id="a2007-159">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="a2007-159">Skype for Business</span></span>
    
- <span data-ttu-id="a2007-160">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="a2007-160">Lync 2013</span></span>
    
- <span data-ttu-id="a2007-161">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="a2007-161">Lync 2010</span></span>
    
- <span data-ttu-id="a2007-162">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="a2007-162">Lync Phone Edition</span></span>
    
> [!NOTE]
> <span data-ttu-id="a2007-163">ユーザーは、次のいずれかのクライアントを使用して、グループ呼び出しのピックアップメンバーへの通話に応答できますが、ユーザーは Skype for business server プールまたは lync server 2013 プールを使っている必要があります。これには、2013年2月の lync server 2013 の累積更新プログラムが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a2007-163">Users can use any of these clients to answer calls to Group Call Pickup members, but the users must be homed on a Skype for Business Server pool or a Lync Server 2013 pool with Cumulative Updates for Lync Server 2013: February 2013.</span></span> 
  
<span data-ttu-id="a2007-164">グループ通話のピックアップメンバーへの通話の発信では、次のクライアントとデバイスはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="a2007-164">The following clients and devices are not supported for picking up calls to Group Call Pickup members:</span></span>
  
- <span data-ttu-id="a2007-165">Lync Mobile</span><span class="sxs-lookup"><span data-stu-id="a2007-165">Lync Mobile</span></span>
    
- <span data-ttu-id="a2007-166">Windows 8 および Windows RT 向け Lync アプリ</span><span class="sxs-lookup"><span data-stu-id="a2007-166">Lync app for Windows 8 and Windows RT</span></span>
    
- <span data-ttu-id="a2007-167">Lync for iPad</span><span class="sxs-lookup"><span data-stu-id="a2007-167">Lync for iPad</span></span>
    
- <span data-ttu-id="a2007-168">アナログ電話</span><span class="sxs-lookup"><span data-stu-id="a2007-168">Analog phones</span></span>
    
- <span data-ttu-id="a2007-169">公衆交換電話網 (PSTN) の番号を持つ電話</span><span class="sxs-lookup"><span data-stu-id="a2007-169">Phones with public switched telephone network (PSTN) numbers</span></span>
    
## <a name="capacity-planning"></a><span data-ttu-id="a2007-170">処理能力の計画</span><span class="sxs-lookup"><span data-stu-id="a2007-170">Capacity planning</span></span>

<span data-ttu-id="a2007-171">次の表では、キャパシティ計画の要件の基礎として使用できるグループ通話ピックアップユーザーモデルについて説明します。</span><span class="sxs-lookup"><span data-stu-id="a2007-171">The following table describes the Group Call Pickup user model that you can use as the basis for capacity planning requirements.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="a2007-172">グループ通話のピックアップは、コールパークアプリケーションに基づいています。</span><span class="sxs-lookup"><span data-stu-id="a2007-172">Group Call Pickup is based on the Call Park application.</span></span> <span data-ttu-id="a2007-173">障害復旧のキャパシティ計画の場合、ペアプールの各プールでは、両方のプールのグループ通話のピックアップを含む、コールパークサービスのワークロードを処理できる必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="a2007-173">Keep in mind that, for disaster recovery capacity planning, each pool of a paired pool should be able to handle the workloads for Call Park services, including Group Call Pickup, in both pools.</span></span> 
  
<span data-ttu-id="a2007-174">**グループ通話のピックアップユーザーモデル**</span><span class="sxs-lookup"><span data-stu-id="a2007-174">**Group Call Pickup User Model**</span></span>

|<span data-ttu-id="a2007-175">**指標**</span><span class="sxs-lookup"><span data-stu-id="a2007-175">**Metric**</span></span>|<span data-ttu-id="a2007-176">**フロントエンドプール<br/>あたり (8 個のフロントエンドサーバーを含む)**</span><span class="sxs-lookup"><span data-stu-id="a2007-176">**Per Front End pool  <br/>  (with 8 Front End Servers)**</span></span>|<span data-ttu-id="a2007-177">**Standard Edition サーバーごと**</span><span class="sxs-lookup"><span data-stu-id="a2007-177">**Per Standard Edition server**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a2007-178">グループあたりの推奨ユーザー数</span><span class="sxs-lookup"><span data-stu-id="a2007-178">Recommended number of users per group</span></span>  <br/> |<span data-ttu-id="a2007-179">50</span><span class="sxs-lookup"><span data-stu-id="a2007-179">50</span></span>  <br/> |<span data-ttu-id="a2007-180">50</span><span class="sxs-lookup"><span data-stu-id="a2007-180">50</span></span>  <br/> |
|<span data-ttu-id="a2007-181">推奨グループ数</span><span class="sxs-lookup"><span data-stu-id="a2007-181">Recommended number of groups</span></span>  <br/> |<span data-ttu-id="a2007-182">500</span><span class="sxs-lookup"><span data-stu-id="a2007-182">500</span></span>  <br/> |<span data-ttu-id="a2007-183">60</span><span class="sxs-lookup"><span data-stu-id="a2007-183">60</span></span>  <br/> |
|<span data-ttu-id="a2007-184">プールあたりの、グループ通話ピックアップが可能な最大ユーザー数</span><span class="sxs-lookup"><span data-stu-id="a2007-184">Maximum number of users per pool enabled for Group Call Pickup</span></span>  <br/> |<span data-ttu-id="a2007-185">25,000</span><span class="sxs-lookup"><span data-stu-id="a2007-185">25,000</span></span>  <br/> |<span data-ttu-id="a2007-186">3,000</span><span class="sxs-lookup"><span data-stu-id="a2007-186">3,000</span></span>  <br/> |
|<span data-ttu-id="a2007-187">プールおよび分あたりの、グループ通話ピックアップが可能な総ユーザー数に対する着信通話数の最大比率</span><span class="sxs-lookup"><span data-stu-id="a2007-187">Maximum rate of incoming calls to total users enabled for Group Call Pickup per pool per minute</span></span>  <br/> |<span data-ttu-id="a2007-188">500</span><span class="sxs-lookup"><span data-stu-id="a2007-188">500</span></span>  <br/> |<span data-ttu-id="a2007-189">60</span><span class="sxs-lookup"><span data-stu-id="a2007-189">60</span></span>  <br/> |
|<span data-ttu-id="a2007-190">プールおよび分あたりの、グループ通話ピックアップによって取得される通話数の最大比率</span><span class="sxs-lookup"><span data-stu-id="a2007-190">Maximum rate of calls retrieved by users with Group Call Pickup per pool per minute</span></span>  <br/> |<span data-ttu-id="a2007-191">200</span><span class="sxs-lookup"><span data-stu-id="a2007-191">200</span></span>  <br/> |<span data-ttu-id="a2007-192">50</span><span class="sxs-lookup"><span data-stu-id="a2007-192">25</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="a2007-193">フロントエンドサーバーの数が8個以下のフロントエンドプールの場合は、数値を直線的に計算します。</span><span class="sxs-lookup"><span data-stu-id="a2007-193">For Front End pools that have fewer than eight Front End Servers, calculate the metrics linearly.</span></span> <span data-ttu-id="a2007-194">たとえば、フロントエンドプールに1つのフロントエンドサーバーがある場合は、テーブルに表示されている値の1/8 としての最大読み込みを計算します。</span><span class="sxs-lookup"><span data-stu-id="a2007-194">For example, if your Front End pool has one Front End Server, calculate the maximum load as 1/8 of the values shown in the table.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="a2007-195">プールあたりのユーザー数の上限を超えていない限り、1つのグループに対して推奨されるユーザー数とグループ数を増減できます。</span><span class="sxs-lookup"><span data-stu-id="a2007-195">You can increase or decrease the recommended number of users per group and number of groups as long as you do not exceed the maximum number of users per pool.</span></span> <span data-ttu-id="a2007-196">たとえば、グループ通話のピックアップ用に有効になっているユーザーの数がユーザーモデルの最大数 (120 グループの場合は、グループ通話のピックアップでは3000ユーザー) のままであるため、標準エディションのサーバーではグループあたり25人のユーザーを持つ120グループを持つことができます。</span><span class="sxs-lookup"><span data-stu-id="a2007-196">For example, your Standard Edition server can have 120 groups with 25 users per group because the number of users enabled for Group Call Pickup is still within the user model maximum (that is, 120 groups times 25 users is 3,000 users enabled for Group Call Pickup).</span></span> 
  

