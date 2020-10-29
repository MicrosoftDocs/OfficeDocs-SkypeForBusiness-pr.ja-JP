---
title: Microsoft Teams の Cortana の音声サポート
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: akshbhat
search.appverid: MET150
description: Teams で Cortana の音声アシスタンスを使用する方法について説明します。
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
ms.openlocfilehash: b93ac825d25e7fdb619c2e949fbef0ba517a3fe9
ms.sourcegitcommit: 5a27802a533db13429813a02626de458f4011780
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/28/2020
ms.locfileid: "48785391"
---
# <a name="cortana-voice-assistance-in-teams"></a>Teams の Cortana 音声アシスタンス

> [!Note]
> Cortana の音声アシスタンスは、Microsoft Teams iOS および Android モバイルアプリでサポートされています。また、Microsoft Teams では、米国のユーザーに対してのみ表示されます。 現時点では、GCC、GCC-高、DoD、EDU テナントでは利用できません。 今後のリリースの一部として、追加の言語と地域への拡張が行われます。

Teams のモバイルアプリおよび Microsoft Teams の表示デバイスでの Cortana の音声サポート Microsoft 365 Enterprise ユーザーは、音声読み上げの言語を使用して、コミュニケーション、共同作業、会議関連のタスクを効率化できます。 ユーザーは、Teams のモバイルアプリの右上にある [マイク] ボタンを選択するか、または Microsoft Teams のディスプレイで Cortana&#8221; &#8220;と言って、Cortana と話すことができます。 ユーザーは、自分のチームと簡単に連絡を取ることができます。外出先でも、&#8220;call Megan&#8221;、または次の会議&#8221; へのメッセージの送信 &#8220;などのクエリを使用できます。 また、ユーザーは次の&#8221; 会議に参加することを &#8220;指示して、音声アシスタンスを使用してファイルを共有したり、予定表を確認したりすることで会議に参加することもできます。 これらの音声アシスタンスのエクスペリエンスは、[オンラインサービス利用規約 (OST)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1)に反映された、Office 365 のプライバシー、セキュリティ、およびコンプライアンスの保証に完全に準拠する[Cortana のエンタープライズ評価サービス](https://docs.microsoft.com/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide)を使用して提供されます。

この画像は、モバイルデバイスで Cortana を使ってチャットを送信する方法を示しています。

![Cortana のチャットセッションが表示された、モバイル画面の一連の画像](media/cortana-on-teams-mobile.png)

## <a name="admin-control-and-limitations"></a>管理者の制御と制限

Teams での Cortana の音声サポートは、オンラインサービス利用規約 (OST) に反映された Office 365 エンタープライズレベルのプライバシー、セキュリティ、およびコンプライアンスの約束に完全に準拠するサービスを使用して提供されます。 この機能は、テナントに対して既定で有効になります。

テナント管理者は、ポリシー (TeamsCortanaPolicy) を使用してチームで Cortana の音声アシスタンスを使用できるように、テナント内のユーザーを制御することができます。 このポリシーは、ユーザーアカウントレベルまたはテナントレベルで設定できます。 管理者は、このポリシーコントロール内で CortanaVoiceInvocationMode フィールドを使って、Cortana が無効になっているか、プッシュボタンでの呼び出しのみで有効になっているか、またはスリープ解除 (Microsoft Teams の表示などのデバイスに適用可能) であるかを確認できます。

管理者は、次の PowerShell コマンドレットを使用してこのポリシーを管理できます (ポリシーは現在、Microsoft Teams 管理センターでは利用できません)。

- [新規-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [Get-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [Grant-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [Set-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [Remove-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

たとえば、次のコマンドは、Microsoft Teams の Cortana 音声アシスタンスが無効になっている &#8220;EmployeeCortanaPolicy&#8221; という名前の新しいポリシーを作成します。  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

この例では、&#8220;EmployeeCortanaPolicy&#8221; という名前の既存のポリシーを更新して、Microsoft Teams で Cortana の音声サポートを有効にして、プッシュボタン呼び出しのみを有効にしています。 ユーザーは Teams で Cortana マイクボタンを選択して Cortana を呼び出すことができます。 Word のスリープ解除 (&#8220;Cortana の&#8221; または &#8220;Cortana&#8221;) の呼び出しは無効になります。  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

次の例では、ポリシーを更新し、プッシュボタンとスリープ解除の両方の呼び出しで Cortana 音声アシスタンスを有効にする方法を示します。

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

> [!Note]
> 英語での Microsoft 365 Enterprise ユーザーの最初のリリースの時点では、Teams モバイルアプリは、word ライセンスのスリープ解除をサポートしていませんが、今後サポートされる予定です。 Word のスリープ解除は、Microsoft Teams の最初のリリースでの表示デバイスで動作します。

## <a name="user-control"></a>ユーザーコントロール

個々のユーザーは、[マイク] ボタンを選択して、Teams のモバイルアプリで Cortana の音声アシスタンスを試すことができます。 Microsoft Teams で Cortana の音声サポートを試すには、「Cortana &#8220;を言ってください。 &#8221;、Teams のモバイルアプリまたは Microsoft Teams のディスプレイの設定を使って、自分のデバイスに対して Cortana の Cortana が有効になっているかどうかを制御することもできます。

1. Teams モバイルアプリを開くか、Microsoft Teams ディスプレイの [環境 (ホーム)] 画面に移動します。

2. Teams モバイルアプリで、[ **設定** ] に移動します。 Microsoft Teams の表示で、ユーザーアバターを選択し、[設定] を選択します。 Cortana が有効になっている場合は、Cortana &#8220;、[設定] に移動し &#8221;

3. [ **Cortana** ] を選びます。

4. デバイスで Cortana 音声アシスタンスが必要かどうかに応じて、トグルを **[オン** ] または [ **オフ** ] に移動します。
