---
title: Skype for Business Server 2015 での回線共有機能の計画
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/21/2016
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
ms.assetid: 6356aad4-700d-495c-8fc8-58eb1d4f6f18
description: このトピックでは、Skype for Business Server 2015、2015 年 11 月の累積的な更新プログラムで回線共有機能 (SLA) を計画する方法について説明します。
ms.openlocfilehash: d7fa13b36c232e37c79e8509de71b4ac29ceff72
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813347"
---
# <a name="plan-for-shared-line-appearance-in-skype-for-business-server-2015"></a><span data-ttu-id="0bd69-103">Skype for Business Server 2015 での回線共有機能の計画</span><span class="sxs-lookup"><span data-stu-id="0bd69-103">Plan for Shared Line Appearance in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="0bd69-104">このトピックでは、Skype for Business Server 2015、2015 年 11 月の累積的な更新プログラムで回線共有機能 (SLA) を計画する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0bd69-104">Read this topic to learn how to plan for Shared Line Appearance (SLA) in Skype for Business Server 2015, November 2015 Cumulative Update.</span></span> 
  
<span data-ttu-id="0bd69-105">回線共有機能は、共有番号と呼ばれる特定の番号で複数の通話を処理する Skype for Business の機能です。</span><span class="sxs-lookup"><span data-stu-id="0bd69-105">Shared Line Appearance is a feature in Skype for Business for handling multiple calls on a specific number called a shared number.</span></span> <span data-ttu-id="0bd69-106">SLA では、エンタープライズ ボイスが有効な Skype for Business ユーザーを複数の回線で共有番号として構成し、複数の通話に応答できます。</span><span class="sxs-lookup"><span data-stu-id="0bd69-106">SLA can configure any enterprise voice enabled Skype for Business user as a shared number with multiple lines to respond to multiple calls.</span></span> <span data-ttu-id="0bd69-107">通話は実際には共有番号で受信されません。代わりに、共有番号の代理人として機能するユーザーに転送されます。</span><span class="sxs-lookup"><span data-stu-id="0bd69-107">The calls are not actually received on the shared number, instead they are forwarded to users that act as delegates for the shared number.</span></span> <span data-ttu-id="0bd69-108">任意の代理人が通話を受け取る一方で、残りの代理人は電話で通話を受け取ったユーザーと、その結果ビジーになった回線に関する通知を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="0bd69-108">Any one of the delegates can pick up the call while the rest of the delegates get a notification on their phone about who picked up the call and which line has become busy as a result.</span></span> <span data-ttu-id="0bd69-109">回線数と代理人の両方が、SLA の共有番号に対して構成できます。</span><span class="sxs-lookup"><span data-stu-id="0bd69-109">Both the number of lines and the delegates are configurable for a shared number in SLA.</span></span> <span data-ttu-id="0bd69-110">また、BusyOption (すべての回線がビジー状態の場合に行う処理) や MissedCallOption (どの代理人も通話を受けない場合) などの高度なオプションも、共有番号に対して構成できます。</span><span class="sxs-lookup"><span data-stu-id="0bd69-110">In addition, advanced options, such as BusyOption (what happens in a situation when all lines are busy) and MissedCallOption (the case in which none of the delegates pick up a call), can also be configured for a shared number.</span></span>
  
<span data-ttu-id="0bd69-111">SLA は、次の電話デバイスでのみサポートされます (コンピューター、携帯電話、その他のデバイスの Skype for Business クライアントではサポートされていません)。</span><span class="sxs-lookup"><span data-stu-id="0bd69-111">SLA is supported only on the following phone devices (it is not supported for Skype for Business clients on computers, mobile phones, or other devices):</span></span> 
  
- <span data-ttu-id="0bd69-112">Polycom VVX300 とファームウェア更新プログラム 5.4.1</span><span class="sxs-lookup"><span data-stu-id="0bd69-112">Polycom VVX300 with firmware update 5.4.1</span></span>
    
- <span data-ttu-id="0bd69-113">Polycom VVX400 とファームウェア更新プログラム 5.4.1</span><span class="sxs-lookup"><span data-stu-id="0bd69-113">Polycom VVX400 with firmware update 5.4.1</span></span>
    
- <span data-ttu-id="0bd69-114">Polycom VVX500 とファームウェア更新プログラム 5.4.1</span><span class="sxs-lookup"><span data-stu-id="0bd69-114">Polycom VVX500 with firmware update 5.4.1</span></span>
    
- <span data-ttu-id="0bd69-115">Polycom VVX600 とファームウェア更新プログラム 5.4.1</span><span class="sxs-lookup"><span data-stu-id="0bd69-115">Polycom VVX600 with firmware update 5.4.1</span></span>
    
<span data-ttu-id="0bd69-116">SLA は、2015 年 11 月の累積的な更新プログラムである Skype for Business Server の新機能です。</span><span class="sxs-lookup"><span data-stu-id="0bd69-116">SLA is a new feature in Skype for Business Server, November 2015 Cumulative Update.</span></span> 
  
<span data-ttu-id="0bd69-117">SLA の展開の詳細については [、「Deploy Shared Line Appearance in Skype for Business Server 2015」を参照](../../deploy/deploy-enterprise-voice/deploy-shared-line-appearance.md)してください。</span><span class="sxs-lookup"><span data-stu-id="0bd69-117">For information about deploying SLA, see [Deploy Shared Line Appearance in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-shared-line-appearance.md).</span></span>
  
## <a name="feature-list"></a><span data-ttu-id="0bd69-118">機能リスト</span><span class="sxs-lookup"><span data-stu-id="0bd69-118">Feature List</span></span>

<span data-ttu-id="0bd69-119">SLA グループを設定すると、次の操作が可能です。</span><span class="sxs-lookup"><span data-stu-id="0bd69-119">Setting up an SLA group enables the following:</span></span>
  
- <span data-ttu-id="0bd69-120">グループ内のすべての代理人は、同じ共有番号への着信呼び出しに応答できます。</span><span class="sxs-lookup"><span data-stu-id="0bd69-120">All delegates in the group can answer inbound calls to the same shared number.</span></span> <span data-ttu-id="0bd69-121">通話は、PSTN ベースまたは SIP ベースの場合があります。</span><span class="sxs-lookup"><span data-stu-id="0bd69-121">The calls can be PSTN-based or SIP-based.</span></span>
    
- <span data-ttu-id="0bd69-122">代理人は通話を保留して受け取る場合があります。</span><span class="sxs-lookup"><span data-stu-id="0bd69-122">Delegates can hold and pick up calls.</span></span>
    
- <span data-ttu-id="0bd69-123">代理人は、SLA グループ外の番号に通話を転送できます。</span><span class="sxs-lookup"><span data-stu-id="0bd69-123">Delegates can transfer calls to a number outside of the SLA group.</span></span>
    
- <span data-ttu-id="0bd69-124">代理人は、共有番号に現在の通話数を確認し、それらの各通話の状態を表示できます。</span><span class="sxs-lookup"><span data-stu-id="0bd69-124">Delegates can see how many calls are currently on the shared number, and view the status of each of those calls.</span></span>
    
- <span data-ttu-id="0bd69-125">共有番号の同時通話の最大数を構成できます。</span><span class="sxs-lookup"><span data-stu-id="0bd69-125">You can configure a maximum number of concurrent calls for the shared number.</span></span> <span data-ttu-id="0bd69-126">また、この最大数に達した後に追加の呼び出しを処理する方法を設定できます。</span><span class="sxs-lookup"><span data-stu-id="0bd69-126">You can also set how you want additional calls to be handled after this maximum is reached.</span></span> <span data-ttu-id="0bd69-127">余分な通話は、ビジー信号で拒否するか、代替番号に転送するか、ボイス メールに転送することができます。</span><span class="sxs-lookup"><span data-stu-id="0bd69-127">Excess calls can be rejected with a busy signal, forwarded to an alternate number, or forwarded to voice mail.</span></span>
    
- <span data-ttu-id="0bd69-128">見つからない通話 (一定時間が過ごした後に呼び出しが取り出されない) の処理方法を構成できます。</span><span class="sxs-lookup"><span data-stu-id="0bd69-128">You can configure how you want missed calls (calls not picked up after a certain time) to be handled.</span></span> <span data-ttu-id="0bd69-129">グループ ID のボイス メールを有効にした場合、欠場した通話は自動的にボイス メールに移動します。</span><span class="sxs-lookup"><span data-stu-id="0bd69-129">If you enable voice mail for the group identity, missed calls automatically go to voice mail.</span></span> <span data-ttu-id="0bd69-130">グループ ID (共有番号) に対してボイス メールを有効にしていない場合は、ビジー信号で拒否される、代替番号に転送する、切断された通話を選択できます。</span><span class="sxs-lookup"><span data-stu-id="0bd69-130">If you do not have voice mail enabled for the group identity (shared number), you can choose for missed calls to be rejected with a busy signal, forwarded to an alternate number, or disconnected.</span></span>
    

