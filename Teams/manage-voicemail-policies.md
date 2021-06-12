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
# <a name="setting-voicemail-policies-in-your-organization"></a>組織内のボイスメール ポリシーの設定

> [!WARNING]
> 顧客Skype for Business、通話ポリシーを通じてボイスメールを無効Microsoft Teams、ユーザーのボイスメール サービスを無効Skype for Businessがあります。

## <a name="voicemail-organization-defaults-for-all-users"></a>すべてのユーザーのボイスメール組織の既定値
- ボイスメールのトランスクリプションが有効になっています。
- ボイスメールのトランスクリプション不適切なマスクが無効になっています。
- 最大記録時間は 5 分に設定されます。

これらの既定値は [、Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy) コマンドレットと [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Get-CsOnlineVoicemailPolicy) コマンドレットを使用して制御できます。

組織内のユーザーが受信したボイスメール メッセージは、組織がホストされているMicrosoft 365またはOffice 365に書き起こされます。 テナントがホストされているリージョンは、ボイスメール メッセージを受信するユーザーが保存されているリージョンと同じではない可能性があります。 テナントがホストされているリージョンを表示するには、[組織プロファイル][](https://go.microsoft.com/fwlink/p/?linkid=2067339)ページに移動し、[データの場所] の横にある [詳細の **表示]****をクリックします**。

> [!IMPORTANT]
> **New-CsOnlineVoiceMailPolicy** コマンドレットを使用して、トランスクリプションおよびトランスクリプション不適切な文字起こしマスク用の新しいポリシー インスタンスを作成したり **、Remove-CsOnlineVoiceMailPolicy** コマンドレットを使用して既存のポリシー インスタンスを削除したりできない。

ボイスメール ポリシーを使用してユーザーのトランスクリプション設定を管理することができます。 使用可能なすべてのボイスメール ポリシー インスタンスを表示するには [、Get-CsOnlineVoicemailPolicy コマンドレットを使用](/powershell/module/skype/Get-CsOnlineVoicemailPolicy) できます。

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
  
## <a name="turning-off-transcription-for-your-organization"></a>組織のトランスクリプションをオフにする

組織のトランスクリプションに関する既定の設定はオンになっており、[Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy) を使用して無効にすることができます。これを行う場合は、次を実行します。

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

## <a name="turning-on-transcription-profanity-masking-for-your-organization"></a>組織のトランスクリプション不適切表現マスキングをオンにする。

組織では、トランスクリプション不適切表現マスキングは既定で無効になっています。 マスキングを有効にしなければならないビジネス上の要件がある場合は、[Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy) を使用してトランスクリプション不適切表現マスキングを有効にすることができます。 これを行う場合は、次を実行します。

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

## <a name="changing-the-recording-duration-for-your-organization"></a>組織の記録期間を変更する

記録の最大長は、組織の既定で 5 分に設定されます。 記録の最大長を増減するビジネス要件がある場合は [、Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy)を使用して行います。 たとえば、最大記録時間を 60 秒に設定するには、次のコマンドを実行します。

```PowerShell
Set-CsOnlineVoicemailPolicy -MaximumRecordingLength ([TimeSpan]::FromSeconds(60))
```

## <a name="dual-language-system-prompts-for-your-organization"></a>組織の二重言語システムプロンプト

既定では、ボイスメール システムのプロンプトは、ボイスメールの設定時にユーザーが選択した言語で発信者に表示されます。 2 つの言語でボイスメール システムプロンプトを表示するビジネス要件がある場合は [、Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy)を使用して行います。 第 1 言語と第 2 言語を設定する必要があります。同じではない可能性があります。 これを行う場合は、次を実行します。

```PowerShell
Set-CsOnlineVoicemailPolicy -PrimarySystemPromptLanguage en-US -SecondarySystemPromptLanguage es-ES
```

## <a name="turning-off-transcription-for-a-user"></a>ユーザーのトランスクリプションをオフにする

ユーザー ポリシーは組織の既定の設定より前に評価されます。 たとえば、すべてのユーザーに対してボイスメールトランスクリプションが有効になっている場合 [、Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy) コマンドレットを使用して、特定のユーザーのトランスクリプションを無効にするポリシーを割り当てできます。

単一ユーザーに対するトランスクリプションを無効にするには、次を実行します。

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

## <a name="turning-on-transcription-profanity-masking-for-a-user"></a>ユーザーのトランスクリプション不適切表現マスキングをオンにします。

特定のユーザーに対してトランスクリプション不適切表現マスキングを有効にするには、ポリシーを割り当てて、[Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy) コマンドレットを使用して特定のユーザーに対するトランスクリプション不適切表現マスキングを有効にすることができます。

単一ユーザーに対するトランスクリプション不適切表現マスキングを有効にするには、次を実行します。

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

## <a name="changing-the-recording-duration-for-a-user"></a>ユーザーの記録期間を変更する

最初に [、New-CsOnlineVoicemailPolicy コマンドレット](/powershell/module/skype/New-CsOnlineVoicemailPolicy) を使用してカスタム ボイスメール ポリシーを作成する必要があります。 次に示すコマンドは、MaximumRecordingLength が 60 秒に設定され、他のフィールドがテナント レベルのグローバル値に設定された、ユーザーごとのオンライン ボイスメール ポリシー OneMinuteVoicemailPolicy を作成します。

```PowerShell
New-CsOnlineVoicemailPolicy -Identity "OneMinuteVoicemailPolicy" -MaximumRecordingLength ([TimeSpan]::FromSeconds(60))
```

このカスタム ポリシーをユーザーに割り当てるには、次のコマンドを実行します。 

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName OneMinuteVoicemailPolicy -Identity sip:amosmar@contoso.com
```

## <a name="dual-language-system-prompts-for-a-user"></a>ユーザーに対する二重言語システムのプロンプト

最初に [、New-CsOnlineVoicemailPolicy コマンドレット](/powershell/module/skype/New-CsOnlineVoicemailPolicy) を使用してカスタム ボイスメール ポリシーを作成する必要があります。 次に示すコマンドは、PrimarySystemPromptLanguage を en-US (英語 - 米国) に設定し、SecondarySystemPromptLanguage を es-SP (スペイン語 - スペイン) に設定して、ユーザーごとのオンライン ボイスメール ポリシー enUS-esSP-VoicemailPolicy を作成します。

```PowerShell
New-CsOnlineVoicemailPolicy -Identity "enUS-esES-VoicemailPolicy" -PrimarySystemPromptLanguage en-US -SecondarySystemPromptLanguage es-ES
```

このカスタム ポリシーをユーザーに割り当てるには、次のコマンドを実行します。 

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName "enUS-esES-VoicemailPolicy" -Identity sip:amosmar@contoso.com
```

> [!NOTE]
> 現在Get-CsOnlineVoicemailPolicyコマンドレットは、PrimarySystemPromptLanguage と SecondarySystemPromptLanguage の値を返していない。 これらの値を表示するには、次のように コマンドを変更します。
>
> >```PowerShell
> > (Get-CsOnlineVoicemailPolicy -Identity PolicyName).PrimarySystemPromptLanguage or
> > (Get-CsOnlineVoicemailPolicy -Identity PolicyName).SecondarySystemPromptLanguage 
>
> **PolicyName をポリシー** の名前に置き換える。


> [!IMPORTANT]
> Microsoft 365 および Office 365ボイスメール サービスは、ボイスメール ポリシーをキャッシュし、6 時間ごとにキャッシュを更新します。 そのため、ポリシーの変更が適用されるのに最大 6 時間かかる場合があります。
