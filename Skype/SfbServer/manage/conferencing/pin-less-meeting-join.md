---
title: Skype for Business Server で PIN を使用する会議参加を構成する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c21e8861-bb75-45e8-8485-38daa3b8121c
description: '概要: Skype for Business Server で PIN を使用する会議参加オプションを構成する方法について学習します。'
ms.openlocfilehash: 794bf13d92857a18254f903a1c5dcca98d0a1ec0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827987"
---
# <a name="configure-pin-less-meeting-join-in-skype-for-business-server"></a><span data-ttu-id="bfc80-103">Skype for Business Server で PIN を使用する会議参加を構成する</span><span class="sxs-lookup"><span data-stu-id="bfc80-103">Configure PIN-less meeting join in Skype for Business Server</span></span>
 
<span data-ttu-id="bfc80-104">**概要:** Skype for Business Server で PIN を使用する会議参加オプションを構成する方法について学習します。</span><span class="sxs-lookup"><span data-stu-id="bfc80-104">**Summary:** Learn how to configure the PIN-less meeting join option in Skype for Business Server.</span></span>
  
<span data-ttu-id="bfc80-105">ダイヤルイン発信者が会議に参加しようとすると、電話会議 自動応答 (CAA) サービスは、発表者が通話中で、ダイヤルイン発信者がリーダー PIN を入力していない場合、ロビー &#x2014; とは異なる保持ペンで発信者を配置します。</span><span class="sxs-lookup"><span data-stu-id="bfc80-105">When a dial-in caller attempts to join a meeting, the Conference Auto Attendant (CAA) service places the caller in a holding pen that is different from the Lobby &#x2014; if a presenter is not already on a call, and the dial-in caller has not entered a leader PIN.</span></span> <span data-ttu-id="bfc80-106">PIN なし会議参加オプションを使用すると、ダイヤルイン発信者は、通話の最初のユーザーである場合でも、リーダー PIN を入力せずに会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="bfc80-106">The PIN-less meeting join option allows dial-in callers to join a meeting without entering a leader PIN even if they are the first person on a call.</span></span> 
  
<span data-ttu-id="bfc80-107">この機能を構成する場合は、次の注意が必要です。</span><span class="sxs-lookup"><span data-stu-id="bfc80-107">Keep the following in mind when configuring this feature:</span></span>
  
- <span data-ttu-id="bfc80-108">プライベート会議にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="bfc80-108">Applies to private meetings only.</span></span>
    
- <span data-ttu-id="bfc80-109">PSTN 発信者は、認証されたユーザーがいなくてもプライベート会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="bfc80-109">Allows PSTN callers to stay in private meetings without the presence of authenticated users.</span></span>
    
- <span data-ttu-id="bfc80-110">設定が変更された後は、すべての既存および新しいプライベート会議に適用されます。</span><span class="sxs-lookup"><span data-stu-id="bfc80-110">After the setting is changed, it applies to all existing and new private meetings.</span></span>
    
- <span data-ttu-id="bfc80-111">開催者のサイトまたはグローバル レベルで有効にできます。</span><span class="sxs-lookup"><span data-stu-id="bfc80-111">Can be enabled either at the site of the organizer or at the global level.</span></span>
    
- <span data-ttu-id="bfc80-112">ロビーをバイパスできるユーザーのオプションは、次のどちらかに設定できます。</span><span class="sxs-lookup"><span data-stu-id="bfc80-112">Options for who can bypass the lobby can be set for either of the following:</span></span> 
    
  - <span data-ttu-id="bfc80-113">**組織から発信者が直接アクセスできるユーザー**</span><span class="sxs-lookup"><span data-stu-id="bfc80-113">**Anyone from my Organization with Callers get in directly**</span></span>
    
  - <span data-ttu-id="bfc80-114">**発信者が直接アクセス** できるユーザー (制限なし) (これは既定の設定です)。</span><span class="sxs-lookup"><span data-stu-id="bfc80-114">**Anyone (no restrictions) with Callers get in directly** (This is the default setting.)</span></span>
    
- <span data-ttu-id="bfc80-115">PIN レス参加を有効にするように構成されている場合でも、CAA サービスは引き続きリーダー PIN の入力を求めるメッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="bfc80-115">When configured to enable PIN-less join, the CAA service still prompts for a leader PIN.</span></span> <span data-ttu-id="bfc80-116">PIN が入力されている場合でも、ユーザーは会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="bfc80-116">Users can join the meeting whether or not a PIN is entered.</span></span> <span data-ttu-id="bfc80-117">ただし、リーダー PIN を入力する機能を保持すると、ダイヤルイン発信者はリーダーとして認証し、必要に応じて会議を管理できます。</span><span class="sxs-lookup"><span data-stu-id="bfc80-117">However, retaining the ability to enter a leader PIN allows a dial-in caller to authenticate as a leader and manage the meeting if necessary.</span></span>
    
## <a name="configure-pin-less-meeting-join"></a><span data-ttu-id="bfc80-118">PIN を使用する会議参加を構成する</span><span class="sxs-lookup"><span data-stu-id="bfc80-118">Configure PIN-less meeting join</span></span>

<span data-ttu-id="bfc80-119">ユーザーに対して PIN 非使用の会議参加を有効にするには、次のように [Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) コマンドレットを AllowAnonymousPstnActivation パラメーターと一緒に使用します。</span><span class="sxs-lookup"><span data-stu-id="bfc80-119">To enable PIN-less meeting join for your users, use the [Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) cmdlet with the AllowAnonymousPstnActivation parameter as follows:</span></span>
  
```PowerShell
Set-CsDialInConferencingConfiguration -Identity  < global or site:sitename>  -AllowAnonymousPstnActivation $True
```

<span data-ttu-id="bfc80-120">たとえば、次のコマンドは、サイト Redmond に対して PIN を使用する会議参加を有効にしています。</span><span class="sxs-lookup"><span data-stu-id="bfc80-120">For example, the following command enables PIN-less meeting join for the site Redmond:</span></span>
  
```PowerShell
Set-CsDialInConferencingConfiguration -Identity site:Redmond -AllowAnonymousPstnActivation $True
```

<span data-ttu-id="bfc80-121">セキュリティ上の目的から、PIN を使用する会議参加が有効になっている場合は、ConferencingPolicy が次のように設定された状態で匿名ユーザーのダイヤルアウトを制限できます。</span><span class="sxs-lookup"><span data-stu-id="bfc80-121">For security purposes, when PIN-less meeting join is turned on, you might want to restrict anonymous users from dialing out by ensuring the ConferencingPolicy is set as follows:</span></span>
  
```PowerShell
Set-CsConferencingPolicy [-Identity <XdsIdentity>] -AllowAnonymousUsersToDialOut $False
```

<span data-ttu-id="bfc80-122">詳細については [、「Set-CsConferencingPolicy」を参照してください](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="bfc80-122">For more information, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
  

