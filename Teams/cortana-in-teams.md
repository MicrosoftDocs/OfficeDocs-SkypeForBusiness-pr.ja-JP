---
title: Microsoft Teams の Cortana 音声アシスタント
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: akshbhat
search.appverid: MET150
description: チームで Cortana の音声アシスタントを使用する方法について説明します。
localization_priority: Normal
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 2db1b5cfbc3a50013872b540521f05a5339dd979
ms.sourcegitcommit: 824c79bd050b0abb576004f6209bb081d5090a8f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/29/2020
ms.locfileid: "46522323"
---
# <a name="cortana-voice-assistance-in-teams"></a>Teams の Cortana 音声アシスタンス

[!INCLUDE [template](includes/preview-feature.md)]

> [!Note]
> Cortana の音声アシスタンスは、米国のユーザーに対してのみ Microsoft Teams iOS および Android モバイルアプリでサポートされています。 現時点では、GCC、GCC-高、DoD、EDU テナントでは利用できません。 今後のリリースの一部として、追加の言語と地域への拡張が行われます。

Teams モバイルアプリの Cortana 音声アシスタンスでは、Microsoft 365 エンタープライズユーザーは、会話、共同作業、会議関連のタスクをスムーズに行うことができます。 ユーザーは、Teams モバイルアプリの右上にある [マイク] ボタンをクリックして Cortana に音声通話を行うことができます。 外出先でも、チームメンバーとすばやく連絡を取るために、ユーザーは "call Megan" や "次の会議にメッセージを送信する" などのクエリを話すことができます。 また、ユーザーは "次の会議に参加する" と読み上げられるため、音声アシスタンスを使用して、ファイルの共有、予定表の確認などを行うことができます。 これらの音声アシスタンスのエクスペリエンスは、[オンラインサービス利用規約 (OST)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1)に反映された、Office 365 のプライバシー、セキュリティ、およびコンプライアンスの保証に完全に準拠する[Cortana のエンタープライズ評価サービス](https://docs.microsoft.com/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide)を使用して提供されます。

この画像は、モバイルデバイスの Cortana でチャットを送信する方法を示しています。

![Cortana のチャットセッションが表示された、モバイル画面の一連の画像](media/cortana-on-teams-mobile.png)

## <a name="admin-control-and-limitations"></a>管理者の制御と制限

Teams での Cortana の音声サポートは、オンラインサービス利用規約 (OST) に反映された Office 365 エンタープライズレベルのプライバシー、セキュリティ、およびコンプライアンスの約束に完全に準拠するサービスを使用して提供されます。 この機能は、テナントに対して既定で有効になります。

テナント管理者は、ポリシー (TeamsCortanaPolicy) を使用してチームで Cortana の音声アシスタンスを使用できるように、テナント内のユーザーを制御することができます。 このポリシーは、ユーザーアカウントレベルまたはテナントレベルで設定できます。 管理者は、このポリシーコントロール内の CortanaVoiceInvocationMode フィールドを使って、Cortana が無効になっているか、プッシュボタンでの呼び出し専用であるか、またはスリープ解除 (サポートされているデバイスに適用可能) であるかを判断することができます。

管理者は、次の PowerShell コマンドレットを使用してこのポリシーを管理できます (ポリシーは現在、Microsoft Teams 管理センターでは利用できません)。

- [新規-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [Get-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [Grant-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [Set-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [Remove-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

たとえば、次のコマンドは、"EmployeeCortanaPolicy" という名前の新しいポリシーを作成します。このポリシーは、Microsoft Teams の Cortana 音声アシスタントが無効になっています。  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

この例では、"EmployeeCortanaPolicy" という名前の既存のポリシーを更新して、Microsoft Teams で Cortana の音声アシスタントを有効にする方法について説明します。 ユーザーは Teams の Cortana マイクボタンをタップして Cortana を呼び出すことができます。 スリープ解除 word ("コルタナ") の呼び出しは無効になります。  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

次の例は、プッシュボタンと word の両方の呼び出しを使って、ポリシーを更新し、Cortana の音声アシスタントを有効にする方法を示しています。

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

> [!Note]
> 英語での Microsoft 365 Enterprise ユーザーの最初のリリースの時点では、Teams モバイルアプリは、word ライセンスのスリープ解除をサポートしていませんが、今後サポートされる予定です。

## <a name="user-control"></a>ユーザーコントロール

個々のユーザーは、[マイク] ボタンをクリックして、Teams のモバイルアプリで Cortana の音声アシスタンスを試すことができます。 また、Teams のモバイルアプリの設定を使用して、自分のデバイスに対して Cortana の Cortana を有効にするかどうかを制御することもできます。

1. Teams モバイルアプリを開きます。

2. [**設定**] に移動します。

3. [ **Cortana**] を選びます。

4. デバイスで Cortana 音声アシスタンスが必要かどうかに応じて、トグルを **[オン**] または [**オフ**] に移動します。
