---
title: ボイスメール ポリシーを管理する
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
description: ユーザーのボイスメール ポリシーを管理します。
ms.openlocfilehash: 275c67cef3a318d15f030f26aa50a74a15748c03
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58604426"
---
# <a name="setting-voicemail-policies-in-your-organization"></a>組織内のボイスメール ポリシーの設定

> [!WARNING]
> Skype for Business顧客の場合、Microsoft Teams通話ポリシーを使用してボイスメールを無効にすると、Skype for Business ユーザーのボイスメール サービスも無効になる可能性があります。

## <a name="voicemail-organization-defaults-for-all-users"></a>すべてのユーザーのボイスメール組織の既定値
- ボイスメールの文字起こしが有効になっている。
- ボイスメール文字起こしの不適切なマスクは無効です。
- 最大記録時間は 5 分に設定されます。

[Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy) コマンドレットと [Grant-CsOnlineVoicemailPolicy コマンドレットを](/powershell/module/skype/Get-CsOnlineVoicemailPolicy)使用して、これらの既定値を制御できます。

組織内のユーザーが受信したボイスメール メッセージは、Microsoft 365またはOffice 365組織がホストされているリージョンで文字起こしされます。 テナントがホストされているリージョンが、ボイスメール メッセージを受信しているユーザーが配置されているリージョンと同じではない可能性があります。 テナントがホストされているリージョンを表示するには、[[組織プロファイル](https://go.microsoft.com/fwlink/p/?linkid=2067339)] ページに移動し、[**データの場所**] の横にある **[詳細の表示**] をクリックします。

> [!IMPORTANT]
> **New-CsOnlineVoiceMailPolicy** コマンドレットを使用して、文字起こしと文字起こしの不適切な表現をマスクするための新しいポリシー インスタンスを作成することはできません。また、**Remove-CsOnlineVoiceMailPolicy** コマンドレットを使用して既存のポリシー インスタンスを削除することはできません。

ボイスメール ポリシーを使用してユーザーのトランスクリプション設定を管理することができます。 使用可能なすべてのボイスメール ポリシー インスタンスを表示するには、 [Get-CsOnlineVoicemailPolicy](/powershell/module/skype/Get-CsOnlineVoicemailPolicy) コマンドレットを使用します。

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

組織では、記録の最大長は既定で 5 分に設定されます。 最大記録長を増減するビジネス要件がある場合は、 [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy) を使用して行うことができます。 たとえば、最大記録時間を 60 秒に設定するには、次のコマンドを実行します。

```PowerShell
Set-CsOnlineVoicemailPolicy -MaximumRecordingLength ([TimeSpan]::FromSeconds(60))
```

## <a name="dual-language-system-prompts-for-your-organization"></a>組織に対するデュアル言語システムのプロンプト

既定では、ボイスメール システムのプロンプトは、ボイスメールの設定時にユーザーが選択した言語で発信者に表示されます。 ボイスメール システムプロンプトを 2 つの言語で表示する必要がある場合は、 [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy) を使用して行うことができます。 プライマリ言語とセカンダリ言語を設定する必要があり、同じでない場合があります。 これを行う場合は、次を実行します。

```PowerShell
Set-CsOnlineVoicemailPolicy -PrimarySystemPromptLanguage en-US -SecondarySystemPromptLanguage es-ES
```

## <a name="turning-off-transcription-for-a-user"></a>ユーザーのトランスクリプションをオフにする

ユーザー ポリシーは組織の既定の設定より前に評価されます。 たとえば、すべてのユーザーに対してボイスメール文字起こしが有効になっている場合、 [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy) コマンドレットを使用して、特定のユーザーの文字起こしを無効にするポリシーを割り当てることができます。

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

まず [、New-CsOnlineVoicemailPolicy](/powershell/module/skype/New-CsOnlineVoicemailPolicy) コマンドレットを使用してカスタム ボイスメール ポリシーを作成する必要があります。 次に示すコマンドは、MaximumRecordingLength が 60 秒に設定され、その他のフィールドがテナント レベルのグローバル値に設定された、ユーザーごとのオンライン ボイスメール ポリシー OneMinuteVoicemailPolicy を作成します。

```PowerShell
New-CsOnlineVoicemailPolicy -Identity "OneMinuteVoicemailPolicy" -MaximumRecordingLength ([TimeSpan]::FromSeconds(60))
```

このカスタム ポリシーをユーザーに割り当てるには、次を実行します。 

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName OneMinuteVoicemailPolicy -Identity sip:amosmar@contoso.com
```

## <a name="dual-language-system-prompts-for-a-user"></a>デュアル言語システムでユーザーの入力を求めるメッセージが表示される

まず [、New-CsOnlineVoicemailPolicy](/powershell/module/skype/New-CsOnlineVoicemailPolicy) コマンドレットを使用してカスタム ボイスメール ポリシーを作成する必要があります。 次に示すコマンドは、PrimarySystemPromptLanguage が en-US (英語 - 米国) に設定され、SecondarySystemPromptLanguage が es-SP (スペイン語 - スペイン) に設定された、ユーザーごとのオンライン ボイスメール ポリシー enUS-esSP-VoicemailPolicy を作成します。

```PowerShell
New-CsOnlineVoicemailPolicy -Identity "enUS-esES-VoicemailPolicy" -PrimarySystemPromptLanguage en-US -SecondarySystemPromptLanguage es-ES
```

このカスタム ポリシーをユーザーに割り当てるには、次を実行します。 

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName "enUS-esES-VoicemailPolicy" -Identity sip:amosmar@contoso.com
```

> [!NOTE]
> Get-CsOnlineVoicemailPolicy コマンドレットは現在、PrimarySystemPromptLanguage と SecondarySystemPromptLanguage の値を返していません。 これらの値を確認するには、次のようにコマンドを変更します。
>
> >```PowerShell
> > (Get-CsOnlineVoicemailPolicy -Identity PolicyName).PrimarySystemPromptLanguage or
> > (Get-CsOnlineVoicemailPolicy -Identity PolicyName).SecondarySystemPromptLanguage 
>
> **PolicyName をポリシー** の名前に置き換えます。


> [!IMPORTANT]
> Microsoft 365およびOffice 365のボイスメール サービスは、ボイスメール ポリシーをキャッシュし、6 時間ごとにキャッシュを更新します。 そのため、ポリシーの変更が適用されるまでに最大で 6 時間かかる場合があります。
