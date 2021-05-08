---
title: Cortana の音声アシスタンス (Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: akshbhat
search.appverid: MET150
description: Cortana 音声アシスタンスを使用して音声サポートを使用する方法についてTeams
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
ms.openlocfilehash: 2f8e24bd9035d45639ac4211435355fe7b792a2d
ms.sourcegitcommit: b782ca2ef946ae25e847c2d1847a89993a8edef8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2021
ms.locfileid: "51886736"
---
# <a name="cortana-voice-assistance-in-teams"></a>Cortana の音声アシスタンス (Teams

> [!Note]
> Cortana 音声アシスタンスは、iOS および Android 用の Microsoft Teams モバイル アプリおよび米国、英国、カナダ、インド、オーストラリアのユーザー向け Microsoft Teams ディスプレイでサポートされています。  Microsoft Teams ミーティングのWindowsは、米国内のユーザーに対してのみサポートされます。 Cortana 音声アシスタンスは現在、GCC、GCC-High、DoD、EDU テナントでは利用できません。 追加の言語と地域への拡張は、将来のリリースの一環として行う予定です。

> [!Note]
> Microsoft Teams Rooms の Cortana 音声アシスタンスは、プレビューの下でリリースされます。 プレビュー リリースでは、Cortana は Rally マイクを接続しているデバイスでは、米国でのみ言語 EN-US でサポートされています。

Teams モバイル アプリ、Windows の Microsoft Teams ミーティング、Microsoft Teams ディスプレイ デバイスでの Cortana 音声アシスタンスにより、Microsoft 365 Enterprise ユーザーは、話し言葉の自然言語を使用して、コミュニケーション、コラボレーション、会議関連のタスクを効率化できます。 ユーザーは、Teams モバイル アプリの右上にあるマイク ボタンを選択するか、Microsoft Teams Room で &#8220;Cortana&#8221; と言うか、Microsoft Teams ディスプレイを使用するときに Cortana と話します。 チームにハンズフリーですばやく接続し、移動中に、ユーザーは &#8220;通話 Megan&#8221; や &#8220;などのクエリを言って、次の会議&#8221; にメッセージを送信できます。 ユーザーは、次の会議に参加&#8220;、音声&#8221;を使ってファイルの共有、予定表の確認などと言って会議に参加することもできます。 これらの音声アシスタンス エクスペリエンスは[、Office 365](/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide)のプライバシー、セキュリティ、およびコンプライアンスの約束に完全に準拠する Cortana エンタープライズ レベルのサービスを使用して提供されます 。これは[、Online Services Terms (OST)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1)に反映されます。

画像は、モバイル デバイスで Cortana を使用してチャットを送信する方法を示しています。

![Cortana チャット セッションを示す一連のモバイル画面](media/cortana-on-teams-mobile.png)

## <a name="admin-control-and-limitations"></a>管理者の制御と制限事項

Teams の Cortana 音声アシスタンスは、Office 365 エンタープライズ レベルのプライバシー、セキュリティ、およびコンプライアンスの約束に完全に準拠するサービスを使用して配信されます。これは、Online Services Terms (OST) に反映されます。 この機能は、テナントに対して既定で有効になります。

テナント管理者は、ポリシー (TeamsCortanaPolicy) を使用して、テナント内Teams Cortana 音声アシスタンスを使用できるユーザーを制御できます。 このポリシーは、ユーザー アカウント レベルまたはテナント レベルで設定できます。 管理者は、このポリシー コントロール内の CortanaVoiceInvocationMode フィールドを使用して、Cortana が無効になっているか、プッシュ ボタン呼び出しでのみ有効になっているか、ウェイク ワード呼び出しでのみ有効になっているかを判断できます (Microsoft Teams ディスプレイなど、それをサポートするデバイスにも適用されます)。

管理者は、次の PowerShell コマンドレットを使用してこのポリシーを管理できます (ポリシーは現在、管理センター Microsoft Teamsできません)。

- [New-CsTeamsCortanaPolicy](/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [Get-CsTeamsCortanaPolicy](/powershell/module/skype/Get-CsTeamsCortanaPolicy)

- [Grant-CsTeamsCortanaPolicy](/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [Set-CsTeamsCortanaPolicy](/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [Remove-CsTeamsCortanaPolicy](/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

たとえば、次のコマンドを実行すると、EmployeeCortanaPolicy &#8220;という名前の新しいポリシーが&#8221;作成されます。ここで、Microsoft Teams の Cortana 音声アシスタンスは無効になります。  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

この例では、&#8220;employeeCortanaPolicy&#8221; という名前の既存のポリシーを更新し、プッシュ ボタン呼び出しのみを使用して Microsoft Teams で Cortana 音声アシスタンスを有効にする方法を示します。 ユーザーは、Cortana の [Cortana マイク] ボタンを選択して Cortana を呼び出Teams。 ウェイク ワード (&#8220;Cortana&#8221; または Cortana &#8220;) の呼び&#8221;呼び出しは無効になります。  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

この例では、ポリシーを更新し、プッシュ ボタンとウェイク ワード呼び出しの両方で Cortana 音声アシスタンスを有効にしています。

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

現在、英語で米国内のユーザー Microsoft 365 Enterpriseの最初のリリースでは、次の機能を使用できます。

- モバイル Teamsウェイク ワードのアクティブ化はサポートされませんが、今後サポートされる予定です。  

- Microsoft Teams ミーティングデバイスWindowsおよびMicrosoft Teamsデバイスでは、ウェイク ワードのアクティブ化がサポートされます。

## <a name="user-control"></a>ユーザー コントロール

個々のユーザーは、さまざまなデバイスで Cortana 音声アシスタンスを試用できます。

- モバイル アプリのマイク ボタンTeams選択します。

- [マイク] ボタンを選択するか、[Cortana] と音声をMicrosoft Teams ミーティング。

- ディスプレイ デバイスで "Cortana" Microsoft Teamsします。

デバイスの設定を使用して、Teamsの Cortana を有効にするかどうかを制御できます。

### <a name="teams-mobile-app-or-the-microsoft-teams-display"></a>TeamsアプリまたはディスプレイMicrosoft Teams表示

  1. モバイル アプリTeams開きます。

  2.   >  **[Cortana 設定] を選択します**。

  3. トグルを [オン] **または [オフ]** に **移動します**。

### <a name="microsoft-teams-display"></a>Microsoft Teams表示

  1. 画面の周囲 (ホーム) 画面に移動Microsoft Teamsします。

  2. ユーザーのアバターを選択し、[] を **設定。** Cortana が有効になっている場合は、"Cortana、設定" と言います。

  3. トグルを [オン] **または [オフ]** に **移動します**。
  
### <a name="microsoft-teams-rooms-on-windows"></a>Microsoft Teams ミーティングのWindows

デバイス レベルで変更を行う場合は、Cortana がテナント レベルで有効になっている場合に使用できます。 Cortana は既定でオフにリリースされます。

デバイス レベルで Cortana を有効にするには、次の XML 属性を SkypeSettings XML ファイルに追加する必要があります。

```xml
<SkypeSettings>  

        <CortanaEnabled>true</CortanaEnabled>  

        <CortanaWakewordEnabled>true</CortanaWakewordEnabled>  

</SkypeSettings> 
```

Cortana がデバイス レベルで有効になっている場合は、会議レベルで変更を行います。

会議中に Cortana 音声アシスタンスを有効にするには、[オン] または [オフ] の切り替 **えスイッチを****移動します**。 会議が終了すると、Cortana はデバイス レベルの設定セットに戻ります。
