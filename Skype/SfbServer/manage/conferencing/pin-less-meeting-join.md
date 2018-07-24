---
title: Skype for Business Server に PIN 非使用の会議参加を構成する
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c21e8861-bb75-45e8-8485-38daa3b8121c
description: '概要: レス暗証番号 (pin) を構成する方法を説明する会議のビジネス サーバーの Skype に参加するオプションです。'
ms.openlocfilehash: 843ea92a331391faa47e4cbc32191312c6dfbc6b
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "20985964"
---
# <a name="configure-pin-less-meeting-join-in-skype-for-business-server"></a><span data-ttu-id="e31c0-103">Skype for Business Server に PIN 非使用の会議参加を構成する</span><span class="sxs-lookup"><span data-stu-id="e31c0-103">Configure PIN-less meeting join in Skype for Business Server</span></span>
 
<span data-ttu-id="e31c0-104">**の概要:** レス暗証番号 (pin) を構成する方法については会議のビジネス サーバーの Skype に参加するオプション。</span><span class="sxs-lookup"><span data-stu-id="e31c0-104">**Summary:** Learn how to configure the PIN-less meeting join option in Skype for Business Server.</span></span>
  
<span data-ttu-id="e31c0-105">ダイヤルインの呼び出し元が会議に参加しようとすると、会議自動応答 (CAA) サービス、呼び出し側ロビー & #x 2014; とは異なる保持のペンで発表者がいない場合は、呼び出しとダイヤルインの呼び出し元の引出線の暗証番号 (pin) に入っていません。</span><span class="sxs-lookup"><span data-stu-id="e31c0-105">When a dial-in caller attempts to join a meeting, the Conference Auto Attendant (CAA) service places the caller in a holding pen that is different from the Lobby &#x2014; if a presenter is not already on a call, and the dial-in caller has not entered a leader PIN.</span></span> <span data-ttu-id="e31c0-106">PIN 非使用の会議参加オプションでは、ダイヤル イン発信者が最初の通話ユーザーであっても主催者 PIN を入力することなく会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="e31c0-106">The PIN-less meeting join option allows dial-in callers to join a meeting without entering a leader PIN even if they are the first person on a call.</span></span> 
  
<span data-ttu-id="e31c0-107">この機能を構成する場合は、次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="e31c0-107">Keep the following in mind when configuring this feature:</span></span>
  
- <span data-ttu-id="e31c0-108">プライベート会議にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="e31c0-108">Applies to private meetings only.</span></span>
    
- <span data-ttu-id="e31c0-109">認証ユーザーが存在しなくても PSTN 発信者がプライベート会議に留まることができます。</span><span class="sxs-lookup"><span data-stu-id="e31c0-109">Allows PSTN callers to stay in private meetings without the presence of authenticated users.</span></span>
    
- <span data-ttu-id="e31c0-110">設定の変更後、既存のすべてのプライベート会議と新しいプライベート会議に適用されます。</span><span class="sxs-lookup"><span data-stu-id="e31c0-110">After the setting is changed, it applies to all existing and new private meetings.</span></span>
    
- <span data-ttu-id="e31c0-111">開催者のサイトまたはグローバル レベルで有効にできます。</span><span class="sxs-lookup"><span data-stu-id="e31c0-111">Can be enabled either at the site of the organizer or at the global level.</span></span>
    
- <span data-ttu-id="e31c0-112">ロビーをバイパスするユーザーのオプションは、次のいずれかに設定できます。</span><span class="sxs-lookup"><span data-stu-id="e31c0-112">Options for who can bypass the lobby can be set for either of the following:</span></span> 
    
  - <span data-ttu-id="e31c0-113">**組織内の誰でも、発信者が直接参加する**</span><span class="sxs-lookup"><span data-stu-id="e31c0-113">**Anyone from my Organization with Callers get in directly**</span></span>
    
  - <span data-ttu-id="e31c0-114">**誰でも (制限なし)、発信者が直接参加する** (これは既定の設定です)。</span><span class="sxs-lookup"><span data-stu-id="e31c0-114">**Anyone (no restrictions) with Callers get in directly** (This is the default setting.)</span></span>
    
- <span data-ttu-id="e31c0-115">PIN 非使用の参加を有効に構成した場合でも、CAA サービスでは主催者 PIN のプロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e31c0-115">When configured to enable PIN-less join, the CAA service still prompts for a leader PIN.</span></span> <span data-ttu-id="e31c0-116">ユーザーは、PIN の入力にかかわらず、会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="e31c0-116">Users can join the meeting whether or not a PIN is entered.</span></span> <span data-ttu-id="e31c0-117">ただし、引出線の暗証番号 (pin) を入力する機能を維持したままリーダーとして認証し、必要に応じて会議を管理するのにはダイヤルインの呼び出し元を使用できます。</span><span class="sxs-lookup"><span data-stu-id="e31c0-117">However, retaining the ability to enter a leader PIN allows a dial-in caller to authenticate as a leader and manage the meeting if necessary.</span></span>
    
## <a name="configure-pin-less-meeting-join"></a><span data-ttu-id="e31c0-118">PIN 非使用の会議参加の構成</span><span class="sxs-lookup"><span data-stu-id="e31c0-118">Configure PIN-less meeting join</span></span>

<span data-ttu-id="e31c0-119">ユーザーの暗証番号 (pin) のない会議の参加を有効にするには、次のように AllowAnonymousPstnActivation パラメーターを使用して[セット CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps)コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="e31c0-119">To enable PIN-less meeting join for your users, use the [Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) cmdlet with the AllowAnonymousPstnActivation parameter as follows:</span></span>
  
```
Set-CsDialInConferencingConfiguration -Identity  < global or site:sitename>  -AllowAnonymousPstnActivation $True
```

<span data-ttu-id="e31c0-120">たとえば、次のコマンドによって、サイト Redmond に対して PIN 非使用の会議参加を有効にします。</span><span class="sxs-lookup"><span data-stu-id="e31c0-120">For example, the following command enables PIN-less meeting join for the site Redmond:</span></span>
  
```
Set-CsDialInConferencingConfiguration -Identity site:Redmond -AllowAnonymousPstnActivation $True
```

<span data-ttu-id="e31c0-121">PIN 非使用の会議参加を有効にした場合、セキュリティ上の理由から、ConferencingPolicy を以下のように設定することにより、匿名ユーザーのダイヤル発信を制限することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e31c0-121">For security purposes, when PIN-less meeting join is turned on, you might want to restrict anonymous users from dialing out by ensuring the ConferencingPolicy is set as follows:</span></span>
  
```
Set-CsConferencingPolicy [-Identity <XdsIdentity>] -AllowAnonymousUsersToDialOut $False
```

<span data-ttu-id="e31c0-122">詳細については、[セット CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e31c0-122">For more information, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
  

