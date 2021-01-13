---
title: Skype for Business Server の通話中オプションを計画する
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
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 5f85c6bc-a962-4283-971c-4380d83b3a66
description: Skype for Business Server の通話中オプション機能について説明します。
ms.openlocfilehash: 558d7486ca7aaa794c3114f5c210702a54e02fc4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813697"
---
# <a name="plan-for-busy-options-for-skype-for-business-server"></a><span data-ttu-id="6f106-103">Skype for Business Server の通話中オプションを計画する</span><span class="sxs-lookup"><span data-stu-id="6f106-103">Plan for Busy Options for Skype for Business Server</span></span>
 
<span data-ttu-id="6f106-104">Skype for Business Server の通話中オプション機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="6f106-104">Read about the Busy Options feature in Skype for Business Server.</span></span>
  
<span data-ttu-id="6f106-105">通話中オプションは、2016 年 7 月の累積的な更新プログラムで導入された新しい音声ポリシーで、ユーザーが既に通話中または電話会議中の場合や、通話を保留にした場合の着信の処理方法を構成できます。</span><span class="sxs-lookup"><span data-stu-id="6f106-105">Busy Options is a new voice policy introduced in the July 2016 Cumulative Update that allows you to configure how incoming calls are handled when a user is already in a call or conference, or has a call placed on hold.</span></span> <span data-ttu-id="6f106-106">新しい通話または着信呼び出しは、ビジー信号で拒否するか、ボイス メールに転送できます。</span><span class="sxs-lookup"><span data-stu-id="6f106-106">New or incoming calls can be rejected with a busy signal or forwarded to voice mail.</span></span> 
  
<span data-ttu-id="6f106-107">ビジー オプション ポリシーは、ペアのフロント エンド プールと存続可能ブランチ サーバー (SBS) のフェールオーバーと障害復旧に対してサポートされています。</span><span class="sxs-lookup"><span data-stu-id="6f106-107">The Busy Options policy is supported for failover and disaster recovery on paired Front End Pools and Survivable Branch Servers (SBS).</span></span>
  
<span data-ttu-id="6f106-108">このトピックでは、取り込み中オプションの機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="6f106-108">This topic describes the features of Busy Options.</span></span> <span data-ttu-id="6f106-109">通話中オプションをインストールおよび構成する方法については、「Skype for Business Server の通話中オプションのインストールと [構成」を参照してください](../../deploy/deploy-enterprise-voice/install-and-configure-busy-options.md)。</span><span class="sxs-lookup"><span data-stu-id="6f106-109">For information about how to install and configure Busy Options, see [Install and configure Busy Options for Skype for Business Server](../../deploy/deploy-enterprise-voice/install-and-configure-busy-options.md).</span></span>
  
## <a name="configuration-options"></a><span data-ttu-id="6f106-110">構成オプション</span><span class="sxs-lookup"><span data-stu-id="6f106-110">Configuration options</span></span>

<span data-ttu-id="6f106-111">組織で [取り込み中オプション] が有効になっている場合、組織内のすべてのユーザー (エンタープライズ VoIP ユーザーと エンタープライズ VoIP ユーザーの両方) は、次の機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="6f106-111">If Busy Options is enabled for the organization, all users in your organization, both Enterprise Voice and non-Enterprise Voice users, can use the following features:</span></span>
  
- <span data-ttu-id="6f106-112">取り込み中 - ユーザーがビジー状態の場合、新しい着信呼び出しがビジー信号で拒否されます。</span><span class="sxs-lookup"><span data-stu-id="6f106-112">Busy on Busy - In which new incoming calls will be rejected with a busy signal if the user is busy.</span></span>
    
- <span data-ttu-id="6f106-113">通話中のボイスメール - ユーザーがビジー状態の場合に、新しい着信呼び出しがボイス メールに転送されます。</span><span class="sxs-lookup"><span data-stu-id="6f106-113">Voicemail on Busy - In which new incoming calls will be forwarded to voice mail if the user is busy.</span></span>
    
<span data-ttu-id="6f106-114">取り込み中オプション機能は、フェールオーバー機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="6f106-114">The Busy Options feature provides failover capability.</span></span> <span data-ttu-id="6f106-115">問題が発生し、ユーザーが別のフロントエンド サーバーまたは Skype for Business Server の別のプールにフェールオーバーした場合、通話中オプションの設定は保持されます。</span><span class="sxs-lookup"><span data-stu-id="6f106-115">If a problem occurs and users fail over to another Front End Server or to another pool in Skype for Business Server, their Busy Options settings will be preserved.</span></span>
  
<span data-ttu-id="6f106-116">通話中オプションの構成方法に関係なく、通話中または電話会議中のユーザー、または通話が保留されているユーザーは、新しい通話や会議を開始する操作を妨げるものではありません。</span><span class="sxs-lookup"><span data-stu-id="6f106-116">Regardless of how their busy options are configured, users in a call or conference, or those with a call on hold, are not prevented from initiating new calls or conferences.</span></span> 
  
<span data-ttu-id="6f106-117">構成後、通話中オプションの設定は、ユーザーのすべての Skype for Business 通話デバイスとクライアントに対して有効になります。</span><span class="sxs-lookup"><span data-stu-id="6f106-117">After configuration, the Busy Options setting is in effect for all the user's Skype for Business call devices and clients.</span></span> <span data-ttu-id="6f106-118">ユーザーの通話中オプションの設定に基づいて、拒否またはボイス メールに送信された通話は、ユーザーがサインインしている Macintosh、Windows デスクトップ、モバイル クライアント、IP 電話など、ユーザーの通話デバイスでは呼び出し音を鳴らしません。</span><span class="sxs-lookup"><span data-stu-id="6f106-118">Based on the user's Busy Options settings, the call that is rejected or sent to voice mail would not ring on any of the user's call devices--including Macintosh, Windows Desktop, mobile clients, or IP phones--on which the user is signed in.</span></span> 
  
<span data-ttu-id="6f106-119">ユーザーには、Skype for Business のクライアントとデバイスで、通話の間に関する通知が表示され、メールでも通知されます。</span><span class="sxs-lookup"><span data-stu-id="6f106-119">Users will see missed-call notifications on their Skype for Business clients and devices, and they will be notified by email as well.</span></span> <span data-ttu-id="6f106-120">通話中に通話中のため通話が拒否された発信者には、到達しようとしたユーザーが別の通話でビジー状態であることを示す通知が Skype for Business クライアントに表示されます。</span><span class="sxs-lookup"><span data-stu-id="6f106-120">Callers whose call was rejected due to Busy on Busy will see a notification in their Skype for Business client stating that the user they attempted to reach is busy on another call.</span></span>
  
<span data-ttu-id="6f106-121">通話中オプション機能を構成するには、Skype for Business PowerShell コマンドレットを使用して次の処理を行います。</span><span class="sxs-lookup"><span data-stu-id="6f106-121">You can configure the Busy Options feature by using Skype for Business PowerShell cmdlets to:</span></span>
  
- <span data-ttu-id="6f106-122">エンタープライズの通話中オプション音声ポリシーを有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="6f106-122">Enable or disable Busy Options Voice policy for the Enterprise.</span></span>
    
- <span data-ttu-id="6f106-123">エンタープライズ内のすべてのユーザーの通話中に通話中または通話中のボイスメールを管理します。</span><span class="sxs-lookup"><span data-stu-id="6f106-123">Administer Busy on Busy or Voicemail on Busy for all the users in the Enterprise.</span></span>
    
- <span data-ttu-id="6f106-124">特定のフロント エンド プールにホームしているすべてのユーザーに対して、通話中に通話中に通話中または通話中にボイスメールを管理します。</span><span class="sxs-lookup"><span data-stu-id="6f106-124">Administer Busy on Busy or Voicemail on Busy for all the users homed in a particular Front End pool.</span></span>
    
- <span data-ttu-id="6f106-125">ユーザーの一覧の通話中に通話中または通話中のボイスメールを管理します。</span><span class="sxs-lookup"><span data-stu-id="6f106-125">Administer Busy on Busy or Voicemail on Busy for a list of users.</span></span>
    
- <span data-ttu-id="6f106-126">1 人のユーザーの通話中に通話中または通話中のボイスメールを管理します。</span><span class="sxs-lookup"><span data-stu-id="6f106-126">Administer Busy on Busy or Voicemail on Busy for a single user.</span></span>
    
## <a name="interoperability-with-voice-applications"></a><span data-ttu-id="6f106-127">音声アプリケーションとの相互運用性</span><span class="sxs-lookup"><span data-stu-id="6f106-127">Interoperability with Voice applications</span></span>

<span data-ttu-id="6f106-128">通話中オプションは、Skype for Business の次の音声アプリケーションとの相互運用性を提供します。</span><span class="sxs-lookup"><span data-stu-id="6f106-128">Busy Options provides interoperability with the following Voice applications in Skype for Business:</span></span>
  
- <span data-ttu-id="6f106-129">応答グループ (RGS)</span><span class="sxs-lookup"><span data-stu-id="6f106-129">Response Groups (RGS)</span></span>
    
  - <span data-ttu-id="6f106-130">応答グループ番号に設定されている取り込み中オプションは、システムによって無視されます。複数の同時通話が許可されます。</span><span class="sxs-lookup"><span data-stu-id="6f106-130">Busy Options set on Response Group numbers will be ignored by the system; multiple concurrent calls will be allowed.</span></span> 
    
  - <span data-ttu-id="6f106-131">[取り込み中オプション] 設定のエージェントの応答グループの現在のアテンダント ルーティング エクスペリエンスは変更されません。</span><span class="sxs-lookup"><span data-stu-id="6f106-131">The current Attendant routing experience in Response Groups will remain unchanged for the Agents with Busy Options settings.</span></span>
    
  - <span data-ttu-id="6f106-132">応答グループエージェントであるユーザーへの応答グループからの呼び出しは、通話中オプションの設定によって調整されません。また、現在の RGS エクスペリエンスは維持されます。</span><span class="sxs-lookup"><span data-stu-id="6f106-132">The calls coming from Response Groups to the users who are Response Groups Agents will not be throttled by Busy Options settings and the current RGS experience will be maintained.</span></span>
    
  - <span data-ttu-id="6f106-133">エージェントに対する非 RGS 関連の呼び出しは、通話中オプションの設定によって受け入れらされます。</span><span class="sxs-lookup"><span data-stu-id="6f106-133">The non-RGS related calls to the Agents will be honored by their Busy Options settings.</span></span>
    
- <span data-ttu-id="6f106-134">チーム呼び出し</span><span class="sxs-lookup"><span data-stu-id="6f106-134">Team Call</span></span>
    
  - <span data-ttu-id="6f106-135">チーム通話用に設定されているユーザーへの着信呼び出しは、通話中に通話中に通話中を無視し、通話中にボイスメール設定を無視するように優先されます。</span><span class="sxs-lookup"><span data-stu-id="6f106-135">Incoming calls to users who are set up for a Team Call will be prioritized to ignore Busy on Busy and Voicemail on Busy settings.</span></span>
    
  - <span data-ttu-id="6f106-136">現在のチーム通話のエクスペリエンスは変更されず、ユーザーに対して通話中オプションが設定されます。</span><span class="sxs-lookup"><span data-stu-id="6f106-136">The current Team Call experience will remain unchanged with Busy Options set for the users.</span></span>
    
  - <span data-ttu-id="6f106-137">そのようなユーザーに対するチーム通話以外の通話は、通話中オプションの設定によって受け入れらされます。</span><span class="sxs-lookup"><span data-stu-id="6f106-137">The non-Team Call related calls to such users will be honored by their Busy Options settings.</span></span>
    
- <span data-ttu-id="6f106-138">上司/管理者の委任</span><span class="sxs-lookup"><span data-stu-id="6f106-138">Boss/Admin Delegation</span></span> 
    
  - <span data-ttu-id="6f106-139">上司または管理者の代理として設定されているユーザーへの着信呼び出しは、上司または管理者として優先され、通話中の通話中に通話中および通話中にボイスメールの設定を無視するように設定されます。</span><span class="sxs-lookup"><span data-stu-id="6f106-139">Incoming calls to users who are set up for a Boss/Admin Delegation either as Boss or an Admin will be prioritized to ignore Busy on Busy and Voicemail on Busy settings.</span></span>
    
  - <span data-ttu-id="6f106-140">現在の上司/管理者委任エクスペリエンスは、管理者または上司に対して [取り込み中オプション] が設定された状態で変更されません。</span><span class="sxs-lookup"><span data-stu-id="6f106-140">The current Boss/Admin Delegation experience will remain unchanged with Busy Options set for the Admins or Boss.</span></span>
    
  - <span data-ttu-id="6f106-141">上司/管理者以外の代理に関連する管理者への呼び出しは、通話中オプションの設定によって受け入れらされます。</span><span class="sxs-lookup"><span data-stu-id="6f106-141">The non-Boss/Admin Delegation related calls to Admins will be honored by their Busy Options settings.</span></span>
    
- <span data-ttu-id="6f106-142">回線共有機能</span><span class="sxs-lookup"><span data-stu-id="6f106-142">Shared Line Appearance</span></span> 
    
  - <span data-ttu-id="6f106-143">回線共有機能用に設定されたユーザー アカウントの [取り込み中オプション] 設定は無視されます。</span><span class="sxs-lookup"><span data-stu-id="6f106-143">Busy Options settings on user accounts set up for Shared Line Appearance will be ignored.</span></span> 
    
  - <span data-ttu-id="6f106-144">代わりに、回線共有機能のネイティブの通話中の通話中と通話中のボイスメールのオプションが使用されます。</span><span class="sxs-lookup"><span data-stu-id="6f106-144">Shared Line Appearance's native Busy on Busy and Voicemail on Busy options will be honored instead.</span></span>
    
- <span data-ttu-id="6f106-145">コール コール コール サービス</span><span class="sxs-lookup"><span data-stu-id="6f106-145">Call Parking Service</span></span> 
    
  - <span data-ttu-id="6f106-146">通話中オプションによって通話をパークしたユーザーに対して、通話が取れなすぎて、タイミングアウトのために呼び出し音が鳴っているパークされた通話は、呼び出し音を鳴らすことができます。</span><span class="sxs-lookup"><span data-stu-id="6f106-146">Parked calls that were not retrieved and are ringing back due to timing out will be allowed to ring though to the user who parked the call by the Busy Options.</span></span> 
    
- <span data-ttu-id="6f106-147">通話会議</span><span class="sxs-lookup"><span data-stu-id="6f106-147">Call Conferencing</span></span>
    
  - <span data-ttu-id="6f106-148">電話会議のユーザーは通話中と見なされ、新しい着信呼び出しはビジー 信号で拒否するか、通話中オプションの設定に従ってボイス メールに転送されます。</span><span class="sxs-lookup"><span data-stu-id="6f106-148">Users in conference calls are considered Busy and new incoming calls will be rejected with a busy signal or forwarded to voice mail according to their Busy Options settings.</span></span>
    
  - <span data-ttu-id="6f106-149">会議のユーザーは、通話中オプションによって新しい通話や会議を開始できない。</span><span class="sxs-lookup"><span data-stu-id="6f106-149">Users in conferences are not prevented from initiating new calls or conferences by Busy Options.</span></span>
    
  - <span data-ttu-id="6f106-150">会議のユーザーは引き続き新しい会議出席依頼を受信できますが、新しいピアツーピア通話は通話中オプションの設定に従って拒否されます。</span><span class="sxs-lookup"><span data-stu-id="6f106-150">Users in conferences are still able to receive new conference invitations, but new peer-to-peer calls will be rejected according to their Busy Options settings.</span></span>
    
- <span data-ttu-id="6f106-151">同時呼び出しと呼び出し転送</span><span class="sxs-lookup"><span data-stu-id="6f106-151">Simultaneous Ring and Call Forwarding</span></span>
    
    <span data-ttu-id="6f106-152">通話中に取り込み中機能は、同時呼び出しと通話転送を使用するようには設計されていない。</span><span class="sxs-lookup"><span data-stu-id="6f106-152">The Busy on Busy feature is not designed to work with Simultaneous Ring and Call Forwarding.</span></span>
    

