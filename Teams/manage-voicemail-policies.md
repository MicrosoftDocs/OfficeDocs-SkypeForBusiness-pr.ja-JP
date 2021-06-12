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
ms.openlocfilehash: aa6b08cba7118a5e43f7f2bd3baea7fb3bc7f158
ms.sourcegitcommit: 2419348e964cfe97b72d533f267c5d7055d5366f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2021
ms.locfileid: "52910059"
---
# <a name="setting-voicemail-policies-in-your-organization"></a><span data-ttu-id="88170-103">組織内のボイスメール ポリシーの設定</span><span class="sxs-lookup"><span data-stu-id="88170-103">Setting voicemail policies in your organization</span></span>

> [!WARNING]
> <span data-ttu-id="88170-104">顧客Skype for Business、通話ポリシーを通じてボイスメールを無効Microsoft Teams、ユーザーのボイスメール サービスを無効Skype for Businessがあります。</span><span class="sxs-lookup"><span data-stu-id="88170-104">For Skype for Business customers, disabling voicemail through a Microsoft Teams calling policy might also disable the voicemail service for your Skype for Business users.</span></span>

## <a name="voicemail-organization-defaults-for-all-users"></a><span data-ttu-id="88170-105">すべてのユーザーのボイスメール組織の既定値</span><span class="sxs-lookup"><span data-stu-id="88170-105">Voicemail organization defaults for all users</span></span>
- <span data-ttu-id="88170-106">ボイスメールのトランスクリプションが有効になっています。</span><span class="sxs-lookup"><span data-stu-id="88170-106">Voicemail transcription is enabled.</span></span>
- <span data-ttu-id="88170-107">ボイスメールのトランスクリプション不適切なマスクが無効になっています。</span><span class="sxs-lookup"><span data-stu-id="88170-107">Voicemail transcription profanity masking is disabled.</span></span>
- <span data-ttu-id="88170-108">最大記録時間は 5 分に設定されます。</span><span class="sxs-lookup"><span data-stu-id="88170-108">The maximum recording duration is set to five minutes.</span></span>

<span data-ttu-id="88170-109">これらの既定値は [、Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy) コマンドレットと [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Get-CsOnlineVoicemailPolicy) コマンドレットを使用して制御できます。</span><span class="sxs-lookup"><span data-stu-id="88170-109">You can control these defaults by using the [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy) and [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Get-CsOnlineVoicemailPolicy) cmdlets.</span></span>

<span data-ttu-id="88170-110">組織内のユーザーが受信したボイスメール メッセージは、組織がホストされているMicrosoft 365またはOffice 365に書き起こされます。</span><span class="sxs-lookup"><span data-stu-id="88170-110">Voicemail messages received by users in your organization are transcribed in the region where your Microsoft 365 or Office 365 organization is hosted.</span></span> <span data-ttu-id="88170-111">テナントがホストされているリージョンは、ボイスメール メッセージを受信するユーザーが保存されているリージョンと同じではない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="88170-111">The region where your tenant is hosted might not be the same region where the user receiving the voicemail message is located.</span></span> <span data-ttu-id="88170-112">テナントがホストされているリージョンを表示するには、[組織プロファイル][](https://go.microsoft.com/fwlink/p/?linkid=2067339)ページに移動し、[データの場所] の横にある [詳細の **表示]\*\*\*\*をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="88170-112">To view the region where your tenant is hosted, go to the [Organization profile](https://go.microsoft.com/fwlink/p/?linkid=2067339) page and then click **View details** next to **Data location**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="88170-113">**New-CsOnlineVoiceMailPolicy** コマンドレットを使用して、トランスクリプションおよびトランスクリプション不適切な文字起こしマスク用の新しいポリシー インスタンスを作成したり **、Remove-CsOnlineVoiceMailPolicy** コマンドレットを使用して既存のポリシー インスタンスを削除したりできない。</span><span class="sxs-lookup"><span data-stu-id="88170-113">You can't create a new policy instance for transcription and transcription profanity masking using the **New-CsOnlineVoiceMailPolicy** cmdlet, and you can't remove an existing policy instance using the **Remove-CsOnlineVoiceMailPolicy** cmdlet.</span></span>

<span data-ttu-id="88170-114">ボイスメール ポリシーを使用してユーザーのトランスクリプション設定を管理することができます。</span><span class="sxs-lookup"><span data-stu-id="88170-114">You can manage the transcription settings for your users using voicemail policies.</span></span> <span data-ttu-id="88170-115">使用可能なすべてのボイスメール ポリシー インスタンスを表示するには [、Get-CsOnlineVoicemailPolicy コマンドレットを使用](/powershell/module/skype/Get-CsOnlineVoicemailPolicy) できます。</span><span class="sxs-lookup"><span data-stu-id="88170-115">To see all available voicemail policy instances, you can use the [Get-CsOnlineVoicemailPolicy](/powershell/module/skype/Get-CsOnlineVoicemailPolicy) cmdlet.</span></span>

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
  
## <a name="turning-off-transcription-for-your-organization"></a><span data-ttu-id="88170-116">組織のトランスクリプションをオフにする</span><span class="sxs-lookup"><span data-stu-id="88170-116">Turning off transcription for your organization</span></span>

<span data-ttu-id="88170-p103">組織のトランスクリプションに関する既定の設定はオンになっており、[Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy) を使用して無効にすることができます。これを行う場合は、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="88170-p103">Because the default setting for transcription is on for your organization, you may want to disable it by using [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy). To do this, run:</span></span>

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

## <a name="turning-on-transcription-profanity-masking-for-your-organization"></a><span data-ttu-id="88170-119">組織のトランスクリプション不適切表現マスキングをオンにする。</span><span class="sxs-lookup"><span data-stu-id="88170-119">Turning on transcription profanity masking for your organization</span></span>

<span data-ttu-id="88170-120">組織では、トランスクリプション不適切表現マスキングは既定で無効になっています。</span><span class="sxs-lookup"><span data-stu-id="88170-120">Transcription profanity masking is disabled by default for your organization.</span></span> <span data-ttu-id="88170-121">マスキングを有効にしなければならないビジネス上の要件がある場合は、[Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy) を使用してトランスクリプション不適切表現マスキングを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="88170-121">If there is a business requirement to enable it, you can enable transcription profanity masking by using [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy).</span></span> <span data-ttu-id="88170-122">これを行う場合は、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="88170-122">To do this, run:</span></span>

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

## <a name="changing-the-recording-duration-for-your-organization"></a><span data-ttu-id="88170-123">組織の記録期間を変更する</span><span class="sxs-lookup"><span data-stu-id="88170-123">Changing the recording duration for your organization</span></span>

<span data-ttu-id="88170-124">記録の最大長は、組織の既定で 5 分に設定されます。</span><span class="sxs-lookup"><span data-stu-id="88170-124">The maximum recording length is set to five minutes by default for your organization.</span></span> <span data-ttu-id="88170-125">記録の最大長を増減するビジネス要件がある場合は [、Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy)を使用して行います。</span><span class="sxs-lookup"><span data-stu-id="88170-125">If there is a business requirement to increase or decrease the maximum recording length, this can be done by using [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy).</span></span> <span data-ttu-id="88170-126">たとえば、最大記録時間を 60 秒に設定するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="88170-126">For example, to set the maximum recording time to 60 seconds,  run:</span></span>

```PowerShell
Set-CsOnlineVoicemailPolicy -MaximumRecordingLength ([TimeSpan]::FromSeconds(60))
```

## <a name="dual-language-system-prompts-for-your-organization"></a><span data-ttu-id="88170-127">組織の二重言語システムプロンプト</span><span class="sxs-lookup"><span data-stu-id="88170-127">Dual language system prompts for your organization</span></span>

<span data-ttu-id="88170-128">既定では、ボイスメール システムのプロンプトは、ボイスメールの設定時にユーザーが選択した言語で発信者に表示されます。</span><span class="sxs-lookup"><span data-stu-id="88170-128">By default, the voicemail system prompts are presented to callers in the language selected by the user when setting up their voicemail.</span></span> <span data-ttu-id="88170-129">2 つの言語でボイスメール システムプロンプトを表示するビジネス要件がある場合は [、Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy)を使用して行います。</span><span class="sxs-lookup"><span data-stu-id="88170-129">If there is a business requirement to have the voicemail system prompts presented in two languages, this can be done by using [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy).</span></span> <span data-ttu-id="88170-130">第 1 言語と第 2 言語を設定する必要があります。同じではない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="88170-130">A primary and secondary language must be set and may not be the same.</span></span> <span data-ttu-id="88170-131">これを行う場合は、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="88170-131">To do this, run:</span></span>

```PowerShell
Set-CsOnlineVoicemailPolicy -PrimarySystemPromptLanguage en-US -SecondarySystemPromptLanguage es-ES
```

## <a name="turning-off-transcription-for-a-user"></a><span data-ttu-id="88170-132">ユーザーのトランスクリプションをオフにする</span><span class="sxs-lookup"><span data-stu-id="88170-132">Turning off transcription for a user</span></span>

<span data-ttu-id="88170-133">ユーザー ポリシーは組織の既定の設定より前に評価されます。</span><span class="sxs-lookup"><span data-stu-id="88170-133">User policies are evaluated before the organizational default settings.</span></span> <span data-ttu-id="88170-134">たとえば、すべてのユーザーに対してボイスメールトランスクリプションが有効になっている場合 [、Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy) コマンドレットを使用して、特定のユーザーのトランスクリプションを無効にするポリシーを割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="88170-134">For example, if voicemail transcription is enabled for all of your users, you can assign a policy to disable transcription for a specific user by using the [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy) cmdlet.</span></span>

<span data-ttu-id="88170-135">単一ユーザーに対するトランスクリプションを無効にするには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="88170-135">To disable transcription for a single user, run:</span></span>

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

## <a name="turning-on-transcription-profanity-masking-for-a-user"></a><span data-ttu-id="88170-136">ユーザーのトランスクリプション不適切表現マスキングをオンにします。</span><span class="sxs-lookup"><span data-stu-id="88170-136">Turning on transcription profanity masking for a user</span></span>

<span data-ttu-id="88170-137">特定のユーザーに対してトランスクリプション不適切表現マスキングを有効にするには、ポリシーを割り当てて、[Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy) コマンドレットを使用して特定のユーザーに対するトランスクリプション不適切表現マスキングを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="88170-137">To enable transcription profanity masking for a specific user, you can assign a policy to enable transcription profanity masking for a specific user by using the [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy) cmdlet.</span></span>

<span data-ttu-id="88170-138">単一ユーザーに対するトランスクリプション不適切表現マスキングを有効にするには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="88170-138">To enable transcription profanity masking for a single user, run:</span></span>

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

## <a name="changing-the-recording-duration-for-a-user"></a><span data-ttu-id="88170-139">ユーザーの記録期間を変更する</span><span class="sxs-lookup"><span data-stu-id="88170-139">Changing the recording duration for a user</span></span>

<span data-ttu-id="88170-140">最初に [、New-CsOnlineVoicemailPolicy コマンドレット](/powershell/module/skype/New-CsOnlineVoicemailPolicy) を使用してカスタム ボイスメール ポリシーを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="88170-140">You must first create a custom voicemail policy using the [New-CsOnlineVoicemailPolicy](/powershell/module/skype/New-CsOnlineVoicemailPolicy) cmdlet.</span></span> <span data-ttu-id="88170-141">次に示すコマンドは、MaximumRecordingLength が 60 秒に設定され、他のフィールドがテナント レベルのグローバル値に設定された、ユーザーごとのオンライン ボイスメール ポリシー OneMinuteVoicemailPolicy を作成します。</span><span class="sxs-lookup"><span data-stu-id="88170-141">The command shown below creates a per-user online voicemail policy OneMinuteVoicemailPolicy with MaximumRecordingLength set to 60 seconds and other fields set to tenant level global value.</span></span>

```PowerShell
New-CsOnlineVoicemailPolicy -Identity "OneMinuteVoicemailPolicy" -MaximumRecordingLength ([TimeSpan]::FromSeconds(60))
```

<span data-ttu-id="88170-142">このカスタム ポリシーをユーザーに割り当てるには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="88170-142">To assign this custom policy to a user, run:</span></span> 

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName OneMinuteVoicemailPolicy -Identity sip:amosmar@contoso.com
```

## <a name="dual-language-system-prompts-for-a-user"></a><span data-ttu-id="88170-143">ユーザーに対する二重言語システムのプロンプト</span><span class="sxs-lookup"><span data-stu-id="88170-143">Dual language system prompts for a user</span></span>

<span data-ttu-id="88170-144">最初に [、New-CsOnlineVoicemailPolicy コマンドレット](/powershell/module/skype/New-CsOnlineVoicemailPolicy) を使用してカスタム ボイスメール ポリシーを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="88170-144">You must first create a custom voicemail policy using the [New-CsOnlineVoicemailPolicy](/powershell/module/skype/New-CsOnlineVoicemailPolicy) cmdlet.</span></span> <span data-ttu-id="88170-145">次に示すコマンドは、PrimarySystemPromptLanguage を en-US (英語 - 米国) に設定し、SecondarySystemPromptLanguage を es-SP (スペイン語 - スペイン) に設定して、ユーザーごとのオンライン ボイスメール ポリシー enUS-esSP-VoicemailPolicy を作成します。</span><span class="sxs-lookup"><span data-stu-id="88170-145">The command shown below creates a per-user online voicemail policy enUS-esSP-VoicemailPolicy with the PrimarySystemPromptLanguage set to en-US (English - United States) and the SecondarySystemPromptLanguage set to es-SP (Spanish - Spain).</span></span>

```PowerShell
New-CsOnlineVoicemailPolicy -Identity "enUS-esES-VoicemailPolicy" -PrimarySystemPromptLanguage en-US -SecondarySystemPromptLanguage es-ES
```

<span data-ttu-id="88170-146">このカスタム ポリシーをユーザーに割り当てるには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="88170-146">To assign this custom policy to a user, run:</span></span> 

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName "enUS-esES-VoicemailPolicy" -Identity sip:amosmar@contoso.com
```

> [!NOTE]
> <span data-ttu-id="88170-147">現在Get-CsOnlineVoicemailPolicyコマンドレットは、PrimarySystemPromptLanguage と SecondarySystemPromptLanguage の値を返していない。</span><span class="sxs-lookup"><span data-stu-id="88170-147">The Get-CsOnlineVoicemailPolicy cmdlet is not currently returning the values for PrimarySystemPromptLanguage and SecondarySystemPromptLanguage.</span></span> <span data-ttu-id="88170-148">これらの値を表示するには、次のように コマンドを変更します。</span><span class="sxs-lookup"><span data-stu-id="88170-148">To see these values modify the command as follows:</span></span>
>
> >```PowerShell
> > (Get-CsOnlineVoicemailPolicy -Identity PolicyName).PrimarySystemPromptLanguage or
> > (Get-CsOnlineVoicemailPolicy -Identity PolicyName).SecondarySystemPromptLanguage 
>
> <span data-ttu-id="88170-149">**PolicyName をポリシー** の名前に置き換える。</span><span class="sxs-lookup"><span data-stu-id="88170-149">Replace **PolicyName** with the name of the policy.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="88170-150">Microsoft 365 および Office 365ボイスメール サービスは、ボイスメール ポリシーをキャッシュし、6 時間ごとにキャッシュを更新します。</span><span class="sxs-lookup"><span data-stu-id="88170-150">The voicemail service in Microsoft 365 and Office 365 caches voicemail policies and updates the cache every 6 hours.</span></span> <span data-ttu-id="88170-151">そのため、ポリシーの変更が適用されるのに最大 6 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="88170-151">So, policy changes that you make can take up to 6 hours to be applied.</span></span>
