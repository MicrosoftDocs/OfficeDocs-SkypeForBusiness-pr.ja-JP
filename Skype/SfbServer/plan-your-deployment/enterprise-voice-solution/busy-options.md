---
title: Skype for Business Server の通話中オプションの計画
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 5f85c6bc-a962-4283-971c-4380d83b3a66
description: 詳細については、「Skype for Business Server の取り込みオプション機能」を参照してください。
ms.openlocfilehash: 8e88b4bf3b92c7fea9bcf79822e2711ff3bee7de
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277105"
---
# <a name="plan-for-busy-options-for-skype-for-business-server"></a><span data-ttu-id="1bba5-103">Skype for Business Server の通話中オプションの計画</span><span class="sxs-lookup"><span data-stu-id="1bba5-103">Plan for Busy Options for Skype for Business Server</span></span>
 
<span data-ttu-id="1bba5-104">詳細については、「Skype for Business Server の取り込みオプション機能」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1bba5-104">Read about the Busy Options feature in Skype for Business Server.</span></span>
  
<span data-ttu-id="1bba5-105">通話中オプションは、2016 年 7 月の累積更新プログラムで導入された新たなボイス ポリシーで、ユーザーが通話中や会議中の場合、または通話を保留にしている場合の着信処理方法を構成することができます。</span><span class="sxs-lookup"><span data-stu-id="1bba5-105">Busy Options is a new voice policy introduced in the July 2016 Cumulative Update that allows you to configure how incoming calls are handled when a user is already in a call or conference, or has a call placed on hold.</span></span> <span data-ttu-id="1bba5-106">着信があった場合に、話中音を流すかボイスメールに転送できます。</span><span class="sxs-lookup"><span data-stu-id="1bba5-106">New or incoming calls can be rejected with a busy signal or forwarded to voice mail.</span></span> 
  
<span data-ttu-id="1bba5-107">ペアになったフロント エンド プールと存続可能ブランチ サーバー (SBS) でのフェールオーバーおよび障害復旧用に、通話中オプション ポリシーがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="1bba5-107">The Busy Options policy is supported for failover and disaster recovery on paired Front End Pools and Survivable Branch Servers (SBS).</span></span>
  
<span data-ttu-id="1bba5-108">ここでは通話中オプション機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="1bba5-108">This topic describes the features of Busy Options.</span></span> <span data-ttu-id="1bba5-109">通話中オプションのインストールと構成方法については、「[Install and configure Busy Options for Skype for Business Server](../../deploy/deploy-enterprise-voice/install-and-configure-busy-options.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1bba5-109">For information about how to install and configure Busy Options, see [Install and configure Busy Options for Skype for Business Server](../../deploy/deploy-enterprise-voice/install-and-configure-busy-options.md).</span></span>
  
## <a name="configuration-options"></a><span data-ttu-id="1bba5-110">構成オプション</span><span class="sxs-lookup"><span data-stu-id="1bba5-110">Configuration options</span></span>

<span data-ttu-id="1bba5-111">通話中オプションが組織で有効になっていれば、エンタープライズ VoIP を使用するユーザーも使用しないユーザーも、組織内の全ユーザーが次の機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="1bba5-111">If Busy Options is enabled for the organization, all users in your organization, both Enterprise Voice and non-Enterprise Voice users, can use the following features:</span></span>
  
- <span data-ttu-id="1bba5-112">通話中に話中音 - 通話中に別の着信があると、話中音を流して着信を拒否します。</span><span class="sxs-lookup"><span data-stu-id="1bba5-112">Busy on Busy - In which new incoming calls will be rejected with a busy signal if the user is busy.</span></span>
    
- <span data-ttu-id="1bba5-113">通話中にボイスメール - 通話中に別の着信があると、ボイスメールに転送します。</span><span class="sxs-lookup"><span data-stu-id="1bba5-113">Voicemail on Busy - In which new incoming calls will be forwarded to voice mail if the user is busy.</span></span>
    
<span data-ttu-id="1bba5-114">通話中オプション機能にはフェールオーバー機能が備わっています。</span><span class="sxs-lookup"><span data-stu-id="1bba5-114">The Busy Options feature provides failover capability.</span></span> <span data-ttu-id="1bba5-115">問題が発生し、ユーザーが別のフロントエンドサーバーまたは Skype for Business Server の別のプールにフェールオーバーした場合、そのビジーオプションの設定は保持されます。</span><span class="sxs-lookup"><span data-stu-id="1bba5-115">If a problem occurs and users fail over to another Front End Server or to another pool in Skype for Business Server, their Busy Options settings will be preserved.</span></span>
  
<span data-ttu-id="1bba5-116">通話中オプションがどう構成されていても、通話中や会議中または通話を保留にしているユーザーが、新たな発信や会議を開始できなくなるわけではありません。  </span><span class="sxs-lookup"><span data-stu-id="1bba5-116">Regardless of how their busy options are configured, users in a call or conference, or those with a call on hold, are not prevented from initiating new calls or conferences.</span></span> 
  
<span data-ttu-id="1bba5-117">構成後、[取り込み中] オプションの設定は、すべてのユーザーの Skype for Business 通話デバイスとクライアントで有効になります。</span><span class="sxs-lookup"><span data-stu-id="1bba5-117">After configuration, the Busy Options setting is in effect for all the user's Skype for Business call devices and clients.</span></span> <span data-ttu-id="1bba5-118">ユーザーの [取り込み中] オプションの設定に基づいて、拒否またはボイスメールに送信された通話は、ユーザーがサインインしたときに、Macintosh、Windows デスクトップ、モバイルクライアント、または IP 電話など、どのユーザーの通話デバイスでも呼び出されません。</span><span class="sxs-lookup"><span data-stu-id="1bba5-118">Based on the user's Busy Options settings, the call that is rejected or sent to voice mail would not ring on any of the user's call devices--including Macintosh, Windows Desktop, mobile clients, or IP phones--on which the user is signed in.</span></span> 
  
<span data-ttu-id="1bba5-119">ユーザーには、Skype for Business クライアントとデバイスで不在着信通知が表示され、メールでも通知されます。</span><span class="sxs-lookup"><span data-stu-id="1bba5-119">Users will see missed-call notifications on their Skype for Business clients and devices, and they will be notified by email as well.</span></span> <span data-ttu-id="1bba5-120">「通話中に話中音」機能により通話を拒否された発信者は、相手が通話中であることを示す通知を Skype for Business クライアントで受け取ります。</span><span class="sxs-lookup"><span data-stu-id="1bba5-120">Callers whose call was rejected due to Busy on Busy will see a notification in their Skype for Business client stating that the user they attempted to reach is busy on another call.</span></span>
  
<span data-ttu-id="1bba5-121">Skype for Business PowerShell コマンドレットを使用して、取り込み中のオプションを設定して、次のことを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="1bba5-121">You can configure the Busy Options feature by using Skype for Business PowerShell cmdlets to:</span></span>
  
- <span data-ttu-id="1bba5-122">エンタープライズ用通話中オプション ボイス ポリシーを有効または無効にする。</span><span class="sxs-lookup"><span data-stu-id="1bba5-122">Enable or disable Busy Options Voice policy for the Enterprise.</span></span>
    
- <span data-ttu-id="1bba5-123">エンタープライズ中の全ユーザーに対して、「通話中に話中音」または「通話中にボイスメール」を管理する。</span><span class="sxs-lookup"><span data-stu-id="1bba5-123">Administer Busy on Busy or Voicemail on Busy for all the users in the Enterprise.</span></span>
    
- <span data-ttu-id="1bba5-124">特定のフロント エンド プールに所属する全ユーザーに対して、「通話中に話中音」または「通話中にボイスメール」を管理する。</span><span class="sxs-lookup"><span data-stu-id="1bba5-124">Administer Busy on Busy or Voicemail on Busy for all the users homed in a particular Front End pool.</span></span>
    
- <span data-ttu-id="1bba5-125">ユーザー リストに対して、「通話中に話中音」または「通話中にボイスメール」を管理する。</span><span class="sxs-lookup"><span data-stu-id="1bba5-125">Administer Busy on Busy or Voicemail on Busy for a list of users.</span></span>
    
- <span data-ttu-id="1bba5-126">1 ユーザーに対して、「通話中に話中音」または「通話中にボイスメール」を管理する。</span><span class="sxs-lookup"><span data-stu-id="1bba5-126">Administer Busy on Busy or Voicemail on Busy for a single user.</span></span>
    
## <a name="interoperability-with-voice-applications"></a><span data-ttu-id="1bba5-127">ボイス アプリケーションとの相互運用性</span><span class="sxs-lookup"><span data-stu-id="1bba5-127">Interoperability with Voice applications</span></span>

<span data-ttu-id="1bba5-128">[取り込み中] オプションでは、Skype for Business の次の音声アプリケーションとの相互運用性が提供されます。</span><span class="sxs-lookup"><span data-stu-id="1bba5-128">Busy Options provides interoperability with the following Voice applications in Skype for Business:</span></span>
  
- <span data-ttu-id="1bba5-129">応答グループ (RGS)</span><span class="sxs-lookup"><span data-stu-id="1bba5-129">Response Groups (RGS)</span></span>
    
  - <span data-ttu-id="1bba5-130">応答グループの数に対して設定された通話中オプションは無視され、複数の同時着信は許可されます。</span><span class="sxs-lookup"><span data-stu-id="1bba5-130">Busy Options set on Response Group numbers will be ignored by the system; multiple concurrent calls will be allowed.</span></span> 
    
  - <span data-ttu-id="1bba5-131">エージェントに対する応答グループ中の現在の応答ルーティング エクスペリエンスは、通話中オプション設定により変わることがありません。</span><span class="sxs-lookup"><span data-stu-id="1bba5-131">The current Attendant routing experience in Response Groups will remain unchanged for the Agents with Busy Options settings.</span></span>
    
  - <span data-ttu-id="1bba5-132">応答グループエージェントであるユーザーへの応答グループからの着信は、通話中オプション設定により制限されず、現在の RGS エクスペリエンスは保持されます。</span><span class="sxs-lookup"><span data-stu-id="1bba5-132">The calls coming from Response Groups to the users who are Response Groups Agents will not be throttled by Busy Options settings and the current RGS experience will be maintained.</span></span>
    
  - <span data-ttu-id="1bba5-133">エージェントへの RGS に関係のない着信は、通話中オプション設定の対象となります。</span><span class="sxs-lookup"><span data-stu-id="1bba5-133">The non-RGS related calls to the Agents will be honored by their Busy Options settings.</span></span>
    
- <span data-ttu-id="1bba5-134">チーム着信</span><span class="sxs-lookup"><span data-stu-id="1bba5-134">Team Call</span></span>
    
  - <span data-ttu-id="1bba5-135">チーム呼び出しに対して設定されているユーザーへの着信通話には、[取り込み中] および [取り込み中] の設定で [取り込み中] というメッセージが優先されます。</span><span class="sxs-lookup"><span data-stu-id="1bba5-135">Incoming calls to users who are set up for a Team Call will be prioritized to ignore Busy on Busy and Voicemail on Busy settings.</span></span>
    
  - <span data-ttu-id="1bba5-136">現在のチーム着信エクスペリエンスは、ユーザーの通話中オプション設定により変わることがありません。</span><span class="sxs-lookup"><span data-stu-id="1bba5-136">The current Team Call experience will remain unchanged with Busy Options set for the users.</span></span>
    
  - <span data-ttu-id="1bba5-137">このようなユーザーへのチーム着信とは関係のない着信は、通話中オプション設定の対象となります。</span><span class="sxs-lookup"><span data-stu-id="1bba5-137">The non-Team Call related calls to such users will be honored by their Busy Options settings.</span></span>
    
- <span data-ttu-id="1bba5-138">上司/管理者委任 </span><span class="sxs-lookup"><span data-stu-id="1bba5-138">Boss/Admin Delegation</span></span> 
    
  - <span data-ttu-id="1bba5-139">上司または管理者として上司または管理者の代理人として設定されているユーザーへの着信通話は、[取り込み中] および [取り込み中] に設定されているときに優先されます。</span><span class="sxs-lookup"><span data-stu-id="1bba5-139">Incoming calls to users who are set up for a Boss/Admin Delegation either as Boss or an Admin will be prioritized to ignore Busy on Busy and Voicemail on Busy settings.</span></span>
    
  - <span data-ttu-id="1bba5-140">現在の上司/管理者委任エクスペリエンスは、管理者または上司の通話中オプション設定により変わることがありません。</span><span class="sxs-lookup"><span data-stu-id="1bba5-140">The current Boss/Admin Delegation experience will remain unchanged with Busy Options set for the Admins or Boss.</span></span>
    
  - <span data-ttu-id="1bba5-141">上司/管理者委任とは関係のない管理者への着信は、通話中オプション設定の対象となります。</span><span class="sxs-lookup"><span data-stu-id="1bba5-141">The non-Boss/Admin Delegation related calls to Admins will be honored by their Busy Options settings.</span></span>
    
- <span data-ttu-id="1bba5-142">回線共有機能   </span><span class="sxs-lookup"><span data-stu-id="1bba5-142">Shared Line Appearance</span></span> 
    
  - <span data-ttu-id="1bba5-143">回線共有機能用に設定されたユーザー アカウントの通話中オプション設定は無視されます。</span><span class="sxs-lookup"><span data-stu-id="1bba5-143">Busy Options settings on user accounts set up for Shared Line Appearance will be ignored.</span></span> 
    
  - <span data-ttu-id="1bba5-144">共有された回線の外観は、取り込み中、取り込み中のオプションでは、[取り込み中] の場合にのみ有効になります。</span><span class="sxs-lookup"><span data-stu-id="1bba5-144">Shared Line Appearance's native Busy on Busy and Voicemail on Busy options will be honored instead.</span></span>
    
- <span data-ttu-id="1bba5-145">コール パーキング サービス </span><span class="sxs-lookup"><span data-stu-id="1bba5-145">Call Parking Service</span></span> 
    
  - <span data-ttu-id="1bba5-146">タイムアウトにより取得できず、かけ直された保管着信は、通話中オプションで着信を保管しているユーザーであっても、呼び出しが行われます。</span><span class="sxs-lookup"><span data-stu-id="1bba5-146">Parked calls that were not retrieved and are ringing back due to timing out will be allowed to ring though to the user who parked the call by the Busy Options.</span></span> 
    
- <span data-ttu-id="1bba5-147">電話会議</span><span class="sxs-lookup"><span data-stu-id="1bba5-147">Call Conferencing</span></span>
    
  - <span data-ttu-id="1bba5-148">電話会議中のユーザーは話し中とみなされ、着信があっも拒否され、通話中オプション設定に従って話中音を流すかボイスメール転送されます。</span><span class="sxs-lookup"><span data-stu-id="1bba5-148">Users in conference calls are considered Busy and new incoming calls will be rejected with a busy signal or forwarded to voice mail according to their Busy Options settings.</span></span>
    
  - <span data-ttu-id="1bba5-149">会議中のユーザーは、通話中オプションによって新たな発信や会議を開始できなくなるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="1bba5-149">Users in conferences are not prevented from initiating new calls or conferences by Busy Options.</span></span>
    
  - <span data-ttu-id="1bba5-150">会議中であっても、別の会議への出席依頼を受け取ることはできますが、ピアツーピア着信は、通話中オプション設定に従って拒否されます。</span><span class="sxs-lookup"><span data-stu-id="1bba5-150">Users in conferences are still able to receive new conference invitations, but new peer-to-peer calls will be rejected according to their Busy Options settings.</span></span>
    
- <span data-ttu-id="1bba5-151">同時呼び出しと通話転送</span><span class="sxs-lookup"><span data-stu-id="1bba5-151">Simultaneous Ring and Call Forwarding</span></span>
    
    <span data-ttu-id="1bba5-152">通話中に話中音の機能は、同時呼び出しと通話転送と連携するよう設計されていません。</span><span class="sxs-lookup"><span data-stu-id="1bba5-152">The Busy on Busy feature is not designed to work with Simultaneous Ring and Call Forwarding.</span></span>
    

