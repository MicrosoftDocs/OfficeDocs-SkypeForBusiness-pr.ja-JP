---
title: Cortanaでの音声アシスタンスのMicrosoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: akshbhat
search.appverid: MET150
description: 音声サポートを使用してCortanaする方法についてTeams
localization_priority: Normal
ms.custom:
- Teams-upgrade-guidance
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0b343a3f69d2b0f97f9d7d3054951719da2e9e43
ms.sourcegitcommit: b7da2655607a17cde9537ed9e00db29b4c1a68df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/30/2021
ms.locfileid: "53219144"
---
# <a name="cortana-voice-assistance-in-teams"></a>Cortanaでの音声アシスタンスのTeams

> [!Note]
> Cortanaは、iOS および Android 用の Microsoft Teams モバイル アプリと、米国、英国、カナダ、インド、オーストラリアのユーザー向け Microsoft Teams ディスプレイでサポートされています。 Microsoft Teams ミーティングのWindowsは、米国内のユーザーに対してのみサポートされます。 Cortana、GCC GCC-High、DoD、および米国以外の EDU テナントでは、音声アシスタンスは現在使用できません。 Cortanaアプリの音声アシスタンスTeams、en-US の EDU のお客様が利用できます。 追加の言語と地域への拡張は、将来のリリースの一環として行う予定です。

> [!Note]
> Cortanaでの音声アシスタンスMicrosoft Teams ミーティングプレビューの下でリリースされます。 プレビュー リリースではCortana Rally マイクを接続しているデバイスでは、言語 EN-US を使用する米国でのみサポートされています。

Cortana Teams モバイル アプリ、Windows の Microsoft Teams ミーティング、Microsoft Teams ディスプレイ デバイスで音声アシスタンスを使用すると、Microsoft 365 Enterprise ユーザーは話し言葉の自然言語を使用して、コミュニケーション、コラボレーション、会議関連のタスクを効率化できます。 ユーザーは、Teams モバイル アプリの右上にあるマイク ボタンを選択するか、Microsoft Teams Room で &#8220;Cortana&#8221; と言うか、Microsoft Teams ディスプレイを使用するときに、Cortana と話し合います。 チームにハンズフリーですばやく接続し、移動中に、ユーザーは &#8220;通話 Megan&#8221; や &#8220;などのクエリを言って、次の会議&#8221; にメッセージを送信できます。 ユーザーは、次の会議に参加&#8220;、音声&#8221;を使ってファイルの共有、予定表の確認などと言って会議に参加することもできます。 これらの音声アシスタンス エクスペリエンスは[、Office 365](/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide)のプライバシー、セキュリティ、およびコンプライアンスの約束に完全に準拠する Cortana エンタープライズ レベルのサービスを使用して提供されます 。これは[、Online Services Terms (OST)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1)に反映されます。

この画像は、モバイル デバイス上のCortanaを使用してチャットを送信する場合を示しています。

![一連のモバイル画面で、チャット セッションCortana表示](media/cortana-on-teams-mobile.png)

## <a name="admin-control-and-limitations"></a>管理者の制御と制限事項

Cortana Teams の音声アシスタンスは、online Services Terms (OST) に反映されている Office 365 エンタープライズ レベルのプライバシー、セキュリティ、コンプライアンスの約束に完全に準拠するサービスを使用して提供されます。 この機能は、テナントに対して既定で有効になります。

テナント管理者は、ポリシー (TeamsCortanaPolicy) を使用して、Cortanaの音声Teamsを使用できるユーザーを制御できます。 このポリシーは、ユーザー アカウント レベルまたはテナント レベルで設定されます。 管理者は、このポリシー コントロール内の CortanaVoiceInvocationMode フィールドを使用して、Cortana を無効にするか、プッシュ ボタン呼び出しでのみ有効にするか、ウェイク ワード呼び出しで有効にするか (Microsoft Teams ディスプレイなど、それをサポートするデバイスにも適用されます) を判断できます。

管理者は、次の PowerShell コマンドレットを使用してこのポリシーを管理できます (ポリシーは現在、管理センター Microsoft Teamsできません)。

- [New-CsTeamsCortanaPolicy](/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [Get-CsTeamsCortanaPolicy](/powershell/module/skype/Get-CsTeamsCortanaPolicy)

- [Grant-CsTeamsCortanaPolicy](/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [Set-CsTeamsCortanaPolicy](/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [Remove-CsTeamsCortanaPolicy](/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

たとえば、次のコマンドでは、employeeCortanaPolicy &#8220;という名前の新しいポリシーが作成&#8221;、Cortana での音声アシスタンスMicrosoft Teams無効になります。  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

この例では、&#8220;employeeCortanaPolicy&#8221; という名前の既存のポリシーを更新し、プッシュ ボタン呼び出しのみを使用して Microsoft Teams で Cortana 音声アシスタンスを有効にする方法を示します。 ユーザーは、アプリの [マイク] Cortanaを選択してCortanaを呼び出Teams。 ウェイク ワード (&#8220;Hey Cortana&#8221; または &#8220;Cortana&#8221;) 呼び出しは無効になります。  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

この例では、ポリシーを更新し、プッシュ ボタンとウェイク Cortanaの両方で音声アシスタンスを有効にする方法を示します。

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

現在、英語で米国内のユーザー Microsoft 365 Enterpriseの最初のリリースでは、次の機能を使用できます。

- モバイル Teamsウェイク ワードのアクティブ化はサポートされませんが、今後サポートされる予定です。  

- Microsoft Teams ミーティングデバイスWindowsおよびMicrosoft Teamsデバイスでは、ウェイク ワードのアクティブ化がサポートされます。

## <a name="user-control"></a>ユーザー コントロール

個々のユーザーは、さまざまなデバイスCortana音声アシスタンスを試用できます。

- モバイル アプリのマイク ボタンTeams選択します。

- [マイク] ボタンを選択するか、または [Cortana] とMicrosoft Teams ミーティング。

- デバイスを表示Cortana "Microsoft Teams" と言います。

デバイスの設定をCortanaをTeamsデバイスで有効にするかどうかを制御できます。

### <a name="teams-mobile-app-or-the-microsoft-teams-display"></a>TeamsアプリまたはディスプレイMicrosoft Teams表示

  1. モバイル アプリTeams開きます。

  2. [設定 **Cortana]**  >  **を選択します**。

  3. トグルを [オン] **または [オフ]** に **移動します**。

### <a name="microsoft-teams-display"></a>Microsoft Teams表示

  1. 画面の周囲 (ホーム) 画面に移動Microsoft Teamsします。

  2. ユーザーのアバターを選択し、[] を **設定。** 有効Cortana場合は、"Cortana に移動設定。

  3. トグルを [オン] **または [オフ]** に **移動します**。
  
### <a name="microsoft-teams-rooms-on-windows"></a>Microsoft Teams ミーティングのWindows

デバイス レベルで変更を行う方法は、テナント Cortanaで有効になっている場合に使用できます。 Cortanaは既定でオフにリリースされます。

デバイス レベルCortanaを有効にするには、次の XML 属性を SkypeSettings XML ファイルに追加する必要があります。

```xml
<SkypeSettings>  

        <CortanaEnabled>true</CortanaEnabled>  

        <CortanaWakewordEnabled>true</CortanaWakewordEnabled>  

</SkypeSettings> 
```

会議レベルで変更を行う方法は、デバイス Cortana有効になっている場合に使用できます。

会議中Cortana音声アシスタンスを有効にするには、[オン] または [オフ]**を****切り替えます**。 会議が終了すると、Cortana設定に戻ります。
