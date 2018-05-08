---
title: Skype for Business 2015 でのグループ通話ピックアップの計画
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3dc0eca8-c773-463c-96bb-9cd6afa2a840
description: Skype でグループを呼び出すのピックアップのためのビジネス サーバーのエンタープライズ VoIP の計画、ユーザーが他の人の本来の機能の呼び出しに応答できます。
ms.openlocfilehash: 6a2fde93d6fcbfa4e2b382f3512d65a8d986a8ba
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="plan-for-group-call-pickup-in-skype-for-business-2015"></a><span data-ttu-id="a746c-103">Skype for Business 2015 でのグループ通話ピックアップの計画</span><span class="sxs-lookup"><span data-stu-id="a746c-103">Plan for Group Call Pickup in Skype for Business 2015</span></span>
 
<span data-ttu-id="a746c-104">Skype でグループを呼び出すのピックアップのためのビジネス サーバーのエンタープライズ VoIP の計画、ユーザーが他の人の本来の機能の呼び出しに応答できます。</span><span class="sxs-lookup"><span data-stu-id="a746c-104">Planning for Group Call Pickup in Skype for Business Server Enterprise Voice, which enables users to answer calls originally intended for others.</span></span>
  
<span data-ttu-id="a746c-105">グループ コール ピックアップでは、同僚に自分の電話からの着信呼び出しに応答することができます。</span><span class="sxs-lookup"><span data-stu-id="a746c-105">Group Call Pickup enables users to answer incoming calls to their colleagues from their own phones.</span></span> <span data-ttu-id="a746c-106">コール ピックアップ グループの番号をダイヤルして、着信呼び出しに応答するには、他のユーザーを有効にすると、ユーザーの行の可用性が向上します。</span><span class="sxs-lookup"><span data-stu-id="a746c-106">This increases the availability of a user's line by enabling other users to answer an incoming call by dialing a call pickup group number.</span></span> <span data-ttu-id="a746c-107">コール ピックアップのグループが展開されると、ボイスメールにルーティングされる着信呼び出しの数が大幅に削減できますは、組織の外部ユーザーからの呼び出しの場合に特に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a746c-107">When Group Call Pickup is deployed, the number of incoming calls that are routed to voice mail can be significantly reduced, which is particularly useful for calls from customers who are external to your organization.</span></span>
  
<span data-ttu-id="a746c-108">グループ コール ピックアップ機能が開放されたオフィス環境でのビジネス ・ ユニットの特に設計されています。</span><span class="sxs-lookup"><span data-stu-id="a746c-108">The Group Call Pickup feature is designed in particular for business units in open office environments.</span></span> <span data-ttu-id="a746c-109">目的の宛先にのみ、着信音のため、着信呼び出しは停止ではありません。</span><span class="sxs-lookup"><span data-stu-id="a746c-109">Incoming calls are not disruptive because they ring only at the intended destination.</span></span> <span data-ttu-id="a746c-110">耳、リングでは、他のユーザー、まだピックアップでき呼び出しグループ番号をダイヤルするだけで。</span><span class="sxs-lookup"><span data-stu-id="a746c-110">Other users who hear the ring, however, can still pick up the call simply by dialing the group number.</span></span> 
  
<span data-ttu-id="a746c-111">ユーザーのオフィスのレイアウトがオープンでない場合、または地理的に分散された複数のユーザーが一般的な業務を分担している場合は、チーム呼び出しによって最適なソリューションが実現します。</span><span class="sxs-lookup"><span data-stu-id="a746c-111">In environments where users are not located in an open office layout, or where users who share a common responsibility are geographically distributed, team call presents the most suitable solution.</span></span> <span data-ttu-id="a746c-112">コール ピックアップのグループおよびチーム呼び出しの主な違いが、グループを呼び出すのピックアップで、目的の宛先にのみ、着信呼び出しが鳴ってだれでもにグループ番号をダイヤルして応答することはできます。</span><span class="sxs-lookup"><span data-stu-id="a746c-112">The primary difference between Group Call Pickup and team call is that, with Group Call Pickup, an incoming call rings only at the intended destination, but anyone can still choose to answer it by dialing a group number.</span></span> <span data-ttu-id="a746c-113">チームの呼び出し、呼び出しは、チーム メンバーの電話の場合は、リングに、呼び出しに応答するのにはチーム内のすべてのユーザーが電話に出ることができます。</span><span class="sxs-lookup"><span data-stu-id="a746c-113">With team call, the call rings at all the team members' phones, and any user in the team can pick up the phone to answer the call.</span></span> <span data-ttu-id="a746c-114">コール ピックアップのグループおよびチーム呼び出しの間の他の違いは、グループ コール ピックアップは、Skype のビジネス サーバーで、管理者によって管理されています。</span><span class="sxs-lookup"><span data-stu-id="a746c-114">An additional difference between Group Call Pickup and team call is that Group Call Pickup is managed by an administrator, through Skype for Business Server.</span></span> <span data-ttu-id="a746c-115">チームの呼び出しでは、エンド ・ ユーザーは、ビジネス クライアント用の Skype を使用して機能を管理します。</span><span class="sxs-lookup"><span data-stu-id="a746c-115">With team call, end users manage the feature by using the Skype for Business client.</span></span> <span data-ttu-id="a746c-116">グループを呼び出すのピックアップでそのため、呼び出しの管理のこの側面を一元化できます。</span><span class="sxs-lookup"><span data-stu-id="a746c-116">With Group Call Pickup, therefore, this aspect of call management can be centralized.</span></span>
  
<span data-ttu-id="a746c-117">グループ コール ピックアップ コール パーク アプリケーションがビルドされます。</span><span class="sxs-lookup"><span data-stu-id="a746c-117">Group Call Pickup is built on the Call Park application.</span></span> <span data-ttu-id="a746c-118">コール ピックアップのグループを配置するときは、コール ピックアップ グループの番号として指定されている内線番号の範囲が別のコール パークの移動テーブルを構成します。</span><span class="sxs-lookup"><span data-stu-id="a746c-118">When you deploy Group Call Pickup, you configure the call park orbit table with separate ranges of extension numbers that are designated as call pickup group numbers.</span></span> <span data-ttu-id="a746c-119">コール パーク オービット番号と同様、通話ピックアップ グループ番号は、ユーザーも電話も割り当てられていない仮想内線である必要があります。</span><span class="sxs-lookup"><span data-stu-id="a746c-119">Like call park orbit numbers, call pickup group numbers must be virtual extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="a746c-120">コール ピックアップのグループを展開する各フロント エンド プールでは、コール ピックアップ グループ番号の 1 つまたは複数の範囲を持つことができます。</span><span class="sxs-lookup"><span data-stu-id="a746c-120">Each Front End pool where you deploy Group Call Pickup can have one or more ranges of call pickup group numbers.</span></span> <span data-ttu-id="a746c-121">グループの数値の範囲は、ビジネス サーバー配置の Skype 間でグローバルに一意でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="a746c-121">The group number ranges must be globally unique across the Skype for Business Server deployment.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="a746c-122">コール パーク軌道のグループを呼び出すピックアップ番号として指定されている数値の範囲は、ビジネス サーバーのコントロール パネルの Skype を使用して表示または管理できません。</span><span class="sxs-lookup"><span data-stu-id="a746c-122">Number ranges that are designated as Group Call Pickup numbers in the call park orbit table cannot be managed or viewed by using the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="a746c-123">コール パーク軌道テーブル内のすべての番号範囲を確認する唯一の方法では、ビジネスのサーバー管理シェルの Skype を使用します。</span><span class="sxs-lookup"><span data-stu-id="a746c-123">The only way to see all the number ranges in the call park orbit table is to use Skype for Business Server Management Shell.</span></span> <span data-ttu-id="a746c-124">同様を追加するには、唯一の方法を変更するか、コール ピックアップのグループ番号の削除は、ビジネス サーバー管理シェルの Skype を使用します。</span><span class="sxs-lookup"><span data-stu-id="a746c-124">Similarly, the only way to add, modify, or remove Group Call Pickup numbers is to use Skype for Business Server Management Shell.</span></span> 
  
<span data-ttu-id="a746c-p106">通話ピックアップ グループ番号を構成したら、ユーザーを通話ピックアップ グループに割り当てます。通話ピックアップ グループに割り当てられたユーザーにかかってきた電話は、他のユーザーがとることができます。通話ピックアップ グループに割り当てられたユーザーに電話がかかってきたときに、その電話に気が付いた他のユーザーが電話をとるには、通話ピックアップ グループ番号に手動でダイヤルします。電話をとるユーザーは、そのグループのメンバーである必要はありません。他のユーザーが電話をとると、電話がかかってきた番号に通知が送信されます。</span><span class="sxs-lookup"><span data-stu-id="a746c-p106">After you configure the call pickup group numbers, you assign users to a call pickup group. Any user who is assigned to a call pickup group can have their calls answered by other users. When a call comes in to a user who is assigned to a call pickup group, any other user who notices the call can answer it by manually dialing the call pickup group number. The user who picks up the call does not need to be a member of the group. When a call is picked up by another user, a notification is sent to the number originally called.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a746c-130">ユーザーがメンバーになれるのは、1 つの通話ピックアップ グループだけです。</span><span class="sxs-lookup"><span data-stu-id="a746c-130">A user can be a member of only one call pickup group.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="a746c-131">ビジネス サーバー配置の Skype で、任意のユーザーは、コール ピックアップ グループのメンバーへの呼び出しに応答できます、ですが、呼び出しに回答する人は、正しいコール ピックアップ グループ番号をダイヤルするを知る必要があります。</span><span class="sxs-lookup"><span data-stu-id="a746c-131">Although any user in the Skype for Business Server deployment can answer a call to a call pickup group member, the person answering the call must know the correct call pickup group number to dial.</span></span> 
  
<span data-ttu-id="a746c-132">グループ内の複数の電話の呼び出し音が鳴っている場合、ユーザーが通話ピックアップ グループ番号をダイヤルして電話をとると、一番長く呼び出し音が鳴っている電話につながります。</span><span class="sxs-lookup"><span data-stu-id="a746c-132">If a user dials a call pickup group number to answer a call when multiple phones in the group are ringing, the user answers the call that has been ringing the longest.</span></span>
  
<span data-ttu-id="a746c-133">同時呼び出しの設定は、グループ通話ピックアップを利用しているユーザーに対して有効です。</span><span class="sxs-lookup"><span data-stu-id="a746c-133">Simultaneous ringing settings will work for users who have group call pickup.</span></span> <span data-ttu-id="a746c-134">つまり、コール ピックアップのグループを持つユーザーに対して行われた呼び出しは、構成されているすべての宛先のリングは、他のユーザーが呼び出しに応答できます。</span><span class="sxs-lookup"><span data-stu-id="a746c-134">That is, a call made to a user who has Group Call Pickup will ring for all the configured destinations, and another user can answer the call.</span></span> <span data-ttu-id="a746c-135">ただし、すべてのチーム メンバーを呼び出すようにユーザーが同時呼び出しを構成している場合、このルールは適用されません。</span><span class="sxs-lookup"><span data-stu-id="a746c-135">The exception to this rule is when the user configures simultaneous ringing to call all the team members.</span></span>
  
<span data-ttu-id="a746c-136">グループ コール ピックアップは、次の種類の呼び出しに応答するのには使用できません。</span><span class="sxs-lookup"><span data-stu-id="a746c-136">Group Call Pickup cannot be used to answer the following types of calls:</span></span>
  
- <span data-ttu-id="a746c-137">プライベート回線の呼び出し</span><span class="sxs-lookup"><span data-stu-id="a746c-137">Calls to a private line</span></span>
    
- <span data-ttu-id="a746c-138">[友人および家族] プライバシー関係に割り当てられた連絡先からの呼び出し</span><span class="sxs-lookup"><span data-stu-id="a746c-138">Calls from a contact who has been assigned the Friends and Family privacy relationship</span></span>
    
    > [!TIP]
    > <span data-ttu-id="a746c-139">コール ピックアップ グループのメンバーであるユーザーは、ビジネス クライアント用の Skype での個人の連絡先として、連絡先をマークすることによってグループを呼び出すピックアップを取得してから、特定の呼び出しを防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="a746c-139">A user who is a member of a call pickup group can prevent certain calls from being retrieved through Group Call Pickup by marking the contact as a personal contact in the Skype for Business client.</span></span> <span data-ttu-id="a746c-140">連絡先を個人連絡先としてマークするには、そのプライバシー関係を [友人および家族] に設定します。</span><span class="sxs-lookup"><span data-stu-id="a746c-140">To mark a contact as a personal contact, set the Privacy Relationship for the contact to Friends and Family.</span></span> <span data-ttu-id="a746c-141">プライバシー関係の連絡先からのすべての着信呼び出しは、友人に設定し、コール ピックアップのグループを使用して、ファミリを取得することはできません。</span><span class="sxs-lookup"><span data-stu-id="a746c-141">Any incoming call from contacts with the Privacy Relationship set to Friends and Family cannot be retrieved by using Group Call Pickup.</span></span> 
  
- <span data-ttu-id="a746c-142">音声ビデオ通話のビデオ部分</span><span class="sxs-lookup"><span data-stu-id="a746c-142">Video portion of audio/video calls</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="a746c-p109">音声ビデオ通話については、ユーザーは音声のみを受け取ります。電話をかけたユーザーまたは電話をとったユーザーのどちらかが、通話をエスカレートして、ビデオを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="a746c-p109">If a user answers an audio/video call, the user receives only the audio. Either the person calling or the person answering the call can escalate the call to add video.</span></span> 
  
- <span data-ttu-id="a746c-145">チーム呼び出しメンバーにルーティングされた同時呼び出し</span><span class="sxs-lookup"><span data-stu-id="a746c-145">Simultaneous ringing calls that are routed to team call members</span></span>
    
- <span data-ttu-id="a746c-146">代理人にルーティングされた呼び出し</span><span class="sxs-lookup"><span data-stu-id="a746c-146">Calls routed to a delegate</span></span>
    
- <span data-ttu-id="a746c-147">応答グループにルーティングされた呼び出し</span><span class="sxs-lookup"><span data-stu-id="a746c-147">Calls routed to a response group</span></span>
    
<span data-ttu-id="a746c-148">次の種類のユーザーは、コール ピックアップのグループに参加できません。</span><span class="sxs-lookup"><span data-stu-id="a746c-148">The following types of users cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="a746c-149">グループ コール ピックアップ グループに含めることができないと、有効になっているグループを呼び出すピックアップを持つユーザーへの呼び出しを取得できない。</span><span class="sxs-lookup"><span data-stu-id="a746c-149">That is, they should not be included in a Group Call Pickup group, and they cannot pick up calls for users who have Group Call Pickup enabled.</span></span>
  
- <span data-ttu-id="a746c-150">ハイブリッド環境の常時オンラインのユーザー</span><span class="sxs-lookup"><span data-stu-id="a746c-150">Users who are homed online in a hybrid deployment</span></span>
    
- <span data-ttu-id="a746c-151">ビジネス サーバー 2015 のプールのいずれか、Skype または Lync Server 2013 プールと Lync Server 2013 の累積的な更新ではないユーザー: 設置型展開で 2013年 2 月</span><span class="sxs-lookup"><span data-stu-id="a746c-151">Users who are not homed on either a Skype for Business Server 2015 pool or a Lync Server 2013 pool with Cumulative Updates for Lync Server 2013: February 2013 in an on-premises deployment</span></span>
    
<span data-ttu-id="a746c-p111">通話ピックアップ グループのメンバーへの電話をだれもとらない場合、その電話は、クライアント設定で指定されているようにルーティングされます。つまり、呼び出しはボイスメールに送られるか、クライアント設定で指定されているように、別の宛先に転送されます。</span><span class="sxs-lookup"><span data-stu-id="a746c-p111">If no one answers a call to a member of a call pickup group, the call is routed as specified in the client settings. That is, the call goes to voicemail or is forwarded to a different destination, as specified in the client settings.</span></span>
  
## <a name="deployment-and-requirements"></a><span data-ttu-id="a746c-154">展開と要件</span><span class="sxs-lookup"><span data-stu-id="a746c-154">Deployment and requirements</span></span>

<span data-ttu-id="a746c-155">グループ コール ピックアップは、エンタープライズ VoIP とコール パーク アプリケーションを配置するときに自動的に配置されます。</span><span class="sxs-lookup"><span data-stu-id="a746c-155">Group Call Pickup is automatically deployed when you deploy Enterprise Voice and the Call Park application.</span></span> <span data-ttu-id="a746c-156">グループ コール ピックアップを有効にするにはコール ピックアップ グループにユーザーを割り当てると、グループ呼び出しのピックアップのため、ユーザーを有効にすることによって、コール ピックアップ グループの番号として、指定された数値の範囲が別のコール パークの移動テーブルを構成しています。</span><span class="sxs-lookup"><span data-stu-id="a746c-156">You enable Group Call Pickup by configuring the Call Park orbit table with separate ranges of numbers designated as call pickup group numbers, and then by assigning users to call pickup groups and enabling the users for Group Call Pickup.</span></span>
  
## <a name="clients-supported-for-group-call-pickup"></a><span data-ttu-id="a746c-157">グループ コール ピックアップのためにサポートされているクライアント</span><span class="sxs-lookup"><span data-stu-id="a746c-157">Clients supported for Group Call Pickup</span></span>

<span data-ttu-id="a746c-158">コール ピックアップのグループのメンバーへの呼び出しに応答するクライアントを次のいずれかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="a746c-158">Any of the following clients can be used to answer calls to Group Call Pickup members:</span></span>
  
- <span data-ttu-id="a746c-159">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="a746c-159">Skype for Business</span></span>
    
- <span data-ttu-id="a746c-160">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="a746c-160">Lync 2013</span></span>
    
- <span data-ttu-id="a746c-161">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="a746c-161">Lync 2010</span></span>
    
- <span data-ttu-id="a746c-162">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="a746c-162">Lync Phone Edition</span></span>
    
> [!NOTE]
> <span data-ttu-id="a746c-163">コール ピックアップのグループのメンバーへの呼び出しに応答するのにはこれらのクライアントのいずれかのユーザーを使用できますが、ユーザーのホーム ビジネス サーバー プールまたは Lync Server 2013 プールの Lync Server 2013 の累積的な更新プログラムでの Skype にする必要があります: 2013年 2 月。</span><span class="sxs-lookup"><span data-stu-id="a746c-163">Users can use any of these clients to answer calls to Group Call Pickup members, but the users must be homed on a Skype for Business Server pool or a Lync Server 2013 pool with Cumulative Updates for Lync Server 2013: February 2013.</span></span> 
  
<span data-ttu-id="a746c-164">コール ピックアップのグループのメンバーへの呼び出しを選択するためには、次のクライアントおよびデバイスがサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="a746c-164">The following clients and devices are not supported for picking up calls to Group Call Pickup members:</span></span>
  
- <span data-ttu-id="a746c-165">Lync Mobile</span><span class="sxs-lookup"><span data-stu-id="a746c-165">Lync Mobile</span></span>
    
- <span data-ttu-id="a746c-166">Windows 8 および Windows RT 向け Lync アプリ</span><span class="sxs-lookup"><span data-stu-id="a746c-166">Lync app for Windows 8 and Windows RT</span></span>
    
- <span data-ttu-id="a746c-167">Lync for iPad</span><span class="sxs-lookup"><span data-stu-id="a746c-167">Lync for iPad</span></span>
    
- <span data-ttu-id="a746c-168">アナログ電話</span><span class="sxs-lookup"><span data-stu-id="a746c-168">Analog phones</span></span>
    
- <span data-ttu-id="a746c-169">公衆交換電話網 (PSTN) の番号を持つ電話</span><span class="sxs-lookup"><span data-stu-id="a746c-169">Phones with public switched telephone network (PSTN) numbers</span></span>
    
## <a name="capacity-planning"></a><span data-ttu-id="a746c-170">処理能力の計画</span><span class="sxs-lookup"><span data-stu-id="a746c-170">Capacity planning</span></span>

<span data-ttu-id="a746c-171">次の表では、容量計画の基礎として使用できるグループを呼び出すピックアップ ユーザー モデルについて説明します。</span><span class="sxs-lookup"><span data-stu-id="a746c-171">The following table describes the Group Call Pickup user model that you can use as the basis for capacity planning requirements.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="a746c-172">グループ コール ピックアップは、コール パーク アプリケーションに基づいています。</span><span class="sxs-lookup"><span data-stu-id="a746c-172">Group Call Pickup is based on the Call Park application.</span></span> <span data-ttu-id="a746c-173">災害復旧計画、容量のペアになったプールの各プールがありますコール パーク サービス グループ コール ピックアップでは、両方のプール内のワークロードを処理することに留意してください。</span><span class="sxs-lookup"><span data-stu-id="a746c-173">Keep in mind that, for disaster recovery capacity planning, each pool of a paired pool should be able to handle the workloads for Call Park services, including Group Call Pickup, in both pools.</span></span> 
  
<span data-ttu-id="a746c-174">**グループ通話ピックアップ ユーザー モデル**</span><span class="sxs-lookup"><span data-stu-id="a746c-174">**Group Call Pickup User Model**</span></span>

|<span data-ttu-id="a746c-175">**メトリック**</span><span class="sxs-lookup"><span data-stu-id="a746c-175">**Metric**</span></span>|<span data-ttu-id="a746c-176">**各フロント エンド プール<br/>で 8 台のフロント エンド サーバー)**</span><span class="sxs-lookup"><span data-stu-id="a746c-176">**Per Front End pool  <br/>  (with 8 Front End Servers)**</span></span>|<span data-ttu-id="a746c-177">**各 Standard Edition サーバー**</span><span class="sxs-lookup"><span data-stu-id="a746c-177">**Per Standard Edition server**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a746c-178">グループあたりの推奨ユーザー数</span><span class="sxs-lookup"><span data-stu-id="a746c-178">Recommended number of users per group</span></span>  <br/> |<span data-ttu-id="a746c-179">50</span><span class="sxs-lookup"><span data-stu-id="a746c-179">50</span></span>  <br/> |<span data-ttu-id="a746c-180">50</span><span class="sxs-lookup"><span data-stu-id="a746c-180">50</span></span>  <br/> |
|<span data-ttu-id="a746c-181">推奨グループ数</span><span class="sxs-lookup"><span data-stu-id="a746c-181">Recommended number of groups</span></span>  <br/> |<span data-ttu-id="a746c-182">500</span><span class="sxs-lookup"><span data-stu-id="a746c-182">500</span></span>  <br/> |<span data-ttu-id="a746c-183">60</span><span class="sxs-lookup"><span data-stu-id="a746c-183">60</span></span>  <br/> |
|<span data-ttu-id="a746c-184">プールあたりの、グループ通話ピックアップが可能な最大ユーザー数</span><span class="sxs-lookup"><span data-stu-id="a746c-184">Maximum number of users per pool enabled for Group Call Pickup</span></span>  <br/> |<span data-ttu-id="a746c-185">25,000</span><span class="sxs-lookup"><span data-stu-id="a746c-185">25,000</span></span>  <br/> |<span data-ttu-id="a746c-186">3,000</span><span class="sxs-lookup"><span data-stu-id="a746c-186">3,000</span></span>  <br/> |
|<span data-ttu-id="a746c-187">プールおよび分あたりの、グループ通話ピックアップが可能な総ユーザー数に対する着信通話数の最大比率</span><span class="sxs-lookup"><span data-stu-id="a746c-187">Maximum rate of incoming calls to total users enabled for Group Call Pickup per pool per minute</span></span>  <br/> |<span data-ttu-id="a746c-188">500</span><span class="sxs-lookup"><span data-stu-id="a746c-188">500</span></span>  <br/> |<span data-ttu-id="a746c-189">60</span><span class="sxs-lookup"><span data-stu-id="a746c-189">60</span></span>  <br/> |
|<span data-ttu-id="a746c-190">プールおよび分あたりの、グループ通話ピックアップによって取得される通話数の最大比率</span><span class="sxs-lookup"><span data-stu-id="a746c-190">Maximum rate of calls retrieved by users with Group Call Pickup per pool per minute</span></span>  <br/> |<span data-ttu-id="a746c-191">200</span><span class="sxs-lookup"><span data-stu-id="a746c-191">200</span></span>  <br/> |<span data-ttu-id="a746c-192">25</span><span class="sxs-lookup"><span data-stu-id="a746c-192">25</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="a746c-193">8 個のフロント エンド サーバーを持つフロント エンド プール、直線的に測定値を計算します。</span><span class="sxs-lookup"><span data-stu-id="a746c-193">For Front End pools that have fewer than eight Front End Servers, calculate the metrics linearly.</span></span> <span data-ttu-id="a746c-194">など、フロント エンド プールに 1 つのフロント エンド サーバーがある場合は、テーブル内の値の 1/8 最大負荷を計算します。</span><span class="sxs-lookup"><span data-stu-id="a746c-194">For example, if your Front End pool has one Front End Server, calculate the maximum load as 1/8 of the values shown in the table.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="a746c-195">大きくしたり、プールあたりのユーザーの最大数を超えない限り、推奨されるグループあたりのユーザー数とグループの数を減らすできます。</span><span class="sxs-lookup"><span data-stu-id="a746c-195">You can increase or decrease the recommended number of users per group and number of groups as long as you do not exceed the maximum number of users per pool.</span></span> <span data-ttu-id="a746c-196">などのコール ピックアップのグループが有効なユーザーの数がユーザー モデルの最大値 (つまり、25 のユーザーは、3,000 人のユーザーがグループのコール ピックアップのため有効になっている 120 のグループ時間) 内であるため、Standard Edition サーバーはグループごとに 25 ユーザーとグループが 120 を持つことができます。</span><span class="sxs-lookup"><span data-stu-id="a746c-196">For example, your Standard Edition server can have 120 groups with 25 users per group because the number of users enabled for Group Call Pickup is still within the user model maximum (that is, 120 groups times 25 users is 3,000 users enabled for Group Call Pickup).</span></span> 
  

