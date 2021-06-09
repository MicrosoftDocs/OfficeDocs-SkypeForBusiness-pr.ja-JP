---
title: ボイスメール ポリシーの管理
author: dstrome
ms.author: dstrome
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.assetid: 9c590873-b014-4df3-9e27-1bb97322a79d
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
description: ユーザーのボイスメール ポリシーを管理します。
ms.openlocfilehash: 213908183c0d1dc608626272c0ea8aa5af308aff
ms.sourcegitcommit: 8ad05b37c0b714adb069bc2503e88366ab75c57d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/07/2021
ms.locfileid: "52796926"
---
# <a name="setting-voicemail-policies-in-your-organization"></a><span data-ttu-id="032d3-103">組織内のボイスメール ポリシーの設定</span><span class="sxs-lookup"><span data-stu-id="032d3-103">Setting voicemail policies in your organization</span></span>

> [!WARNING]
> <span data-ttu-id="032d3-104">顧客Skype for Business、通話ポリシーを通じてボイスメールを無効Microsoft Teams、ユーザーのボイスメール サービスを無効Skype for Businessがあります。</span><span class="sxs-lookup"><span data-stu-id="032d3-104">For Skype for Business customers, disabling voicemail through a Microsoft Teams calling policy might also disable the voicemail service for your Skype for Business users.</span></span>

<span data-ttu-id="032d3-105">既定では、すべての組織とユーザーに対して、ボイスメール トランスクリプションは有効に、トランスクリプション不適切表現マスキングは無効になっています。ただし、[Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy) と [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Get-CsOnlineVoicemailPolicy) コマンドレットを使用してそれらを制御することができます。</span><span class="sxs-lookup"><span data-stu-id="032d3-105">Voicemail transcription is enabled by default and transcription profanity masking is disabled by default for all organizations and users; however, you can control them by using the [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy) and [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Get-CsOnlineVoicemailPolicy) cmdlets.</span></span>

<span data-ttu-id="032d3-106">組織内のユーザーが受信したボイスメール メッセージは、組織がホストされているMicrosoft 365またはOffice 365に書き起こされます。</span><span class="sxs-lookup"><span data-stu-id="032d3-106">Voicemail messages received by users in your organization are transcribed in the region where your Microsoft 365 or Office 365 organization is hosted.</span></span> <span data-ttu-id="032d3-107">テナントがホストされているリージョンは、ボイスメール メッセージを受信するユーザーが保存されているリージョンと同じではない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="032d3-107">The region where your tenant is hosted might not be the same region where the user receiving the voicemail message is located.</span></span> <span data-ttu-id="032d3-108">テナントがホストされているリージョンを表示するには、[組織プロファイル][](https://go.microsoft.com/fwlink/p/?linkid=2067339)ページに移動し、[データの場所] の横にある [詳細の **表示]\*\*\*\*をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="032d3-108">To view the region where your tenant is hosted, go to the [Organization profile](https://go.microsoft.com/fwlink/p/?linkid=2067339) page and then click **View details** next to **Data location**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="032d3-109">**New-CsOnlineVoiceMailPolicy** コマンドレットを使用して、トランスクリプションおよびトランスクリプション不適切な文字起こしマスク用の新しいポリシー インスタンスを作成したり **、Remove-CsOnlineVoiceMailPolicy** コマンドレットを使用して既存のポリシー インスタンスを削除したりできない。</span><span class="sxs-lookup"><span data-stu-id="032d3-109">You can't create a new policy instance for transcription and transcription profanity masking using the **New-CsOnlineVoiceMailPolicy** cmdlet, and you can't remove an existing policy instance using the **Remove-CsOnlineVoiceMailPolicy** cmdlet.</span></span>

<span data-ttu-id="032d3-110">ボイスメール ポリシーを使用してユーザーのトランスクリプション設定を管理することができます。</span><span class="sxs-lookup"><span data-stu-id="032d3-110">You can manage the transcription settings for your users using voicemail policies.</span></span> <span data-ttu-id="032d3-111">使用可能なすべてのボイスメール ポリシー インスタンスを表示するには [、Get-CsOnlineVoicemailPolicy コマンドレットを使用](/powershell/module/skype/Get-CsOnlineVoicemailPolicy) できます。</span><span class="sxs-lookup"><span data-stu-id="032d3-111">To see all available voicemail policy instances, you can use the [Get-CsOnlineVoicemailPolicy](/powershell/module/skype/Get-CsOnlineVoicemailPolicy) cmdlet.</span></span>

```PowerShell
PS C:\> Get-CsOnlineVoicemailPolicy


Identity                            : Global
EnableTranscription                 : True
ShareData                           : Defer
EnableTranscriptionProfanityMasking : False
EnableEditingCallAnswerRulesSetting : True
MaximumRecordingLength              : 00:05:00
EnableTranscriptionTranslation      : True

Identity                            : Tag:Default
EnableTranscription                 : True
ShareData                           : Defer
EnableTranscriptionProfanityMasking : False
EnableEditingCallAnswerRulesSetting : True
MaximumRecordingLength              : 00:05:00
EnableTranscriptionTranslation      : True

Identity                            : Tag:TranscriptionProfanityMaskingEnabled
EnableTranscription                 : True
ShareData                           : Defer
EnableTranscriptionProfanityMasking : True
EnableEditingCallAnswerRulesSetting : True
MaximumRecordingLength              : 00:05:00
EnableTranscriptionTranslation      : True

Identity                            : Tag:TranscriptionDisabled
EnableTranscription                 : False
ShareData                           : Defer
EnableTranscriptionProfanityMasking : False
EnableEditingCallAnswerRulesSetting : True
MaximumRecordingLength              : 00:05:00
EnableTranscriptionTranslation      : True
```
  
## <a name="turning-off-transcription-for-your-organization"></a><span data-ttu-id="032d3-112">組織のトランスクリプションをオフにする</span><span class="sxs-lookup"><span data-stu-id="032d3-112">Turning off transcription for your organization</span></span>

<span data-ttu-id="032d3-p103">組織のトランスクリプションに関する既定の設定はオンになっており、[Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy) を使用して無効にすることができます。これを行う場合は、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="032d3-p103">Because the default setting for transcription is on for your organization, you may want to disable it by using [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy). To do this, run:</span></span>

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

## <a name="turning-on-transcription-profanity-masking-for-your-organization"></a><span data-ttu-id="032d3-115">組織のトランスクリプション不適切表現マスキングをオンにする。</span><span class="sxs-lookup"><span data-stu-id="032d3-115">Turning on transcription profanity masking for your organization</span></span>

<span data-ttu-id="032d3-116">組織では、トランスクリプション不適切表現マスキングは既定で無効になっています。</span><span class="sxs-lookup"><span data-stu-id="032d3-116">Transcription profanity masking is disabled by default for your organization.</span></span> <span data-ttu-id="032d3-117">マスキングを有効にしなければならないビジネス上の要件がある場合は、[Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy) を使用してトランスクリプション不適切表現マスキングを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="032d3-117">If there is a business requirement to enable it, you can enable transcription profanity masking by using [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy).</span></span> <span data-ttu-id="032d3-118">これを行う場合は、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="032d3-118">To do this, run:</span></span>

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

## <a name="turning-off-transcription-for-a-user"></a><span data-ttu-id="032d3-119">ユーザーのトランスクリプションをオフにする</span><span class="sxs-lookup"><span data-stu-id="032d3-119">Turning off transcription for a user</span></span>

<span data-ttu-id="032d3-120">ユーザー ポリシーは組織の既定の設定より前に評価されます。</span><span class="sxs-lookup"><span data-stu-id="032d3-120">User policies are evaluated before the organizational default settings.</span></span> <span data-ttu-id="032d3-121">たとえば、すべてのユーザーに対してボイスメールトランスクリプションが有効になっている場合 [、Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy) コマンドレットを使用して、特定のユーザーのトランスクリプションを無効にするポリシーを割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="032d3-121">For example, if voicemail transcription is enabled for all of your users, you can assign a policy to disable transcription for a specific user by using the [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy) cmdlet.</span></span>

<span data-ttu-id="032d3-122">単一ユーザーに対するトランスクリプションを無効にするには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="032d3-122">To disable transcription for a single user, run:</span></span>

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

## <a name="turning-on-transcription-profanity-masking-for-a-user"></a><span data-ttu-id="032d3-123">ユーザーのトランスクリプション不適切表現マスキングをオンにします。</span><span class="sxs-lookup"><span data-stu-id="032d3-123">Turning on transcription profanity masking for a user</span></span>

<span data-ttu-id="032d3-124">特定のユーザーに対してトランスクリプション不適切表現マスキングを有効にするには、ポリシーを割り当てて、[Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy) コマンドレットを使用して特定のユーザーに対するトランスクリプション不適切表現マスキングを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="032d3-124">To enable transcription profanity masking for a specific user, you can assign a policy to enable transcription profanity masking for a specific user by using the [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy) cmdlet.</span></span>

<span data-ttu-id="032d3-125">単一ユーザーに対するトランスクリプション不適切表現マスキングを有効にするには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="032d3-125">To enable transcription profanity masking for a single user, run:</span></span>

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> <span data-ttu-id="032d3-126">Microsoft 365 および Office 365ボイスメール サービスは、ボイスメール ポリシーをキャッシュし、6 時間ごとにキャッシュを更新します。</span><span class="sxs-lookup"><span data-stu-id="032d3-126">The voicemail service in Microsoft 365 and Office 365 caches voicemail policies and updates the cache every 6 hours.</span></span> <span data-ttu-id="032d3-127">そのため、ポリシーの変更が適用されるのに最大 6 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="032d3-127">So, policy changes that you make can take up to 6 hours to be applied.</span></span>
