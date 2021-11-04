---
title: Cortanaでの音声アシスタンスのMicrosoft Teams
author: cichur
ms.author: v-mahoffman
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: akshbhat
search.appverid: MET150
description: 音声アシスタンスを使用してCortanaを使用する方法についてTeams
ms.localizationpriority: medium
ms.custom:
- Teams-upgrade-guidance
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1e5869ba286fa28c5bd91b644be59238e6305b77
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60749103"
---
# <a name="cortana-voice-assistance-in-teams"></a>Cortanaでの音声アシスタンスのTeams

> [!Note]
> Cortanaは、iOS および Android 用の Microsoft Teams モバイル アプリと、米国、英国、カナダ、インド、オーストラリアのユーザー向け Microsoft Teams ディスプレイでサポートされています。 Microsoft TeamsWindowsの会議室は、ロケールが en-us に設定されているデバイスでのみサポートされます。 Cortana、GCC GCC-High、DoD、および米国以外の EDU テナントでは、音声アシスタンスは現在使用できません。 Cortanaアプリの音声アシスタンスTeams、en-US の EDU のお客様が利用できます。 追加の言語と地域への拡張は、将来のリリースの一環として行う予定です。


Cortana Teams モバイル アプリ、Windows の Microsoft Teams 会議室、Microsoft Teams ディスプレイ デバイスで音声アシスタンスを使用すると、Microsoft 365 Enterprise ユーザーはコミュニケーション、共同作業、会議関連を効率化できます。話し言葉の自然言語を使用したタスク。 ユーザーは、Teams モバイル アプリの右上にあるマイク ボタンを選択するか、Microsoft Teams Room で &#8220;Cortana&#8221; と言うか、Microsoft Teams ディスプレイを使用して、Cortana と話し合います。 チームにハンズフリーですばやく接続し、移動中に、ユーザーは &#8220;通話 Megan&#8221; や &#8220;などのクエリを言って、次の会議&#8221; にメッセージを送信できます。 ユーザーは、次の会議に参加&#8220;、音声&#8221;を使ってファイルの共有、予定表の確認などと言って会議に参加することもできます。 これらの音声アシスタンス エクスペリエンスは[、Office 365](/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide)のプライバシー、セキュリティ、およびコンプライアンスの約束に完全に準拠する Cortana エンタープライズ レベルのサービスを使用して提供されます 。これは[、Online Services Terms (OST)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1)に反映されます。

## <a name="admin-control-and-limitations"></a>管理者の制御と制限事項

Cortana Teams の音声アシスタンスは、online Services Terms (OST) に反映されている Office 365 エンタープライズ レベルのプライバシー、セキュリティ、コンプライアンスの約束に完全に準拠するサービスを使用して提供されます。 この機能は、テナントに対して既定で有効になります。

テナント管理者は、ポリシー (TeamsCortanaPolicy) を使用して、Cortanaの音声アシスタンスTeamsを使用できるユーザーを制御できます。 このポリシーは、ユーザー アカウント レベルまたはテナント レベルで設定されます。 管理者は、このポリシー コントロール内の CortanaVoiceInvocationMode フィールドを使用して、Cortana を無効にするか、プッシュ ボタン呼び出しでのみ有効にするか、ウェイク ワード呼び出しで有効にするか (Microsoft Teams ディスプレイなど、それをサポートするデバイスにも適用されます) を判断できます。

管理者は、次の PowerShell コマンドレットを使用してこのポリシーを管理できます (ポリシーは現在、管理センター Microsoft Teamsできません)。

- [New-CsTeamsCortanaPolicy](/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [Get-CsTeamsCortanaPolicy](/powershell/module/skype/Get-CsTeamsCortanaPolicy)

- [Grant-CsTeamsCortanaPolicy](/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [Set-CsTeamsCortanaPolicy](/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [Remove-CsTeamsCortanaPolicy](/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

たとえば、次のコマンドを実行すると、employeeCortanaPolicy &#8220;という名前の新しいポリシーが作成&#8221;、Microsoft Teams での音声アシスタンスCortanaが無効になります。  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

この例では、&#8220;employeeCortanaPolicy&#8221; という名前の既存のポリシーを更新し、プッシュ ボタン呼び出しのみを使用して Microsoft Teams で Cortana 音声アシスタンスを有効にする方法を示します。 ユーザーは、アプリの [マイク] Cortanaを選択してCortanaを呼び出Teams。 ウェイク ワード (&#8220;Hey Cortana&#8221; または &#8220;Cortana&#8221;) 呼び出しは無効になります。  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

この例では、プッシュ ボタンとウェイク ワード呼び出Cortanaを使用して、ポリシーの更新と音声アシスタンスの有効化を示します。

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

英語で米国内のユーザー向Microsoft 365 Enterpriseリリース時点で、次の機能を使用できます。

- モバイル Teamsウェイク ワードのアクティブ化はサポートされませんが、今後サポートされる予定です。  

- Microsoft TeamsデバイスとWindowsデバイスMicrosoft Teamsの会議室では、ウェイク ワードのアクティブ化がサポートされます。

## <a name="user-control"></a>ユーザー コントロール

個々のユーザーは、さまざまなデバイスCortana音声アシスタンスを試用できます。

- モバイル アプリの [マイク] Teams選択します。

- [会議室] でマイク ボタンを選択するかCortanaをMicrosoft Teamsします。

- デバイスを表示Cortana "Microsoft Teams" と言います。

デバイスの設定をCortanaをTeamsデバイスで有効にするかどうかを制御できます。

![を有効にした場合のモバイル ウィンドウの進行状況Cortana。](media/cortana-mobile-sequence.png)

### <a name="microsoft-teams-rooms-on-windows"></a>Microsoft Teams会議室 (Windows

デバイス レベルでの変更は、テナント レベルでCortana有効になっている場合にのみ使用できます。 

デバイス レベルでは、2 つの異なる方法Cortanaを構成できます。 オプションまたは両方を同時に有効にできます。 
- マイクをタップします。このマイクは、[プッシュしてCortana _と呼ばれる)_
- "Hey, Cortana" と言います。これは音声Cortana _呼び出されます_

Cortana _デバイスがロケール en-us_ を使用するために設定されている場合、プッシュして話す機能は既定で有効になります。 [詳細情報。](/MicrosoftTeams/rooms/console#to-apply-your-desired-language)  Cortanaアイコンをクリックすると、[詳細...] の _[発表_]_ボタンが置き換わります。_ メニュー Teams表示されます。 [プッシュしてCortana _を無効にするには、PowerShell_ を使用します。[詳細については、次を参照してください。](/powershell/module/skype/new-csteamscortanapolicy?view=skype-ps#example-1)

音声アクティベーションをCortana _するには、_ 次の条件を満たしている必要があります。
- 認定Cortanaデバイスが、お使いの Teamsに接続されている必要があります。 認定デバイスの一覧は、この記事の最後で確認できます。
- ロケール Teamsを使用するには、そのルームをセットアップする必要があります。 その他の言語は、後日提供される予定です。
- 次のいずれかの構成変更を行う必要があります。
  - 管理センターで機能を有効Teams詳細[を確認してください。](/microsoftteams/rooms/rooms-manage)
  - SkypeSettings XML ファイルに次の XML 属性を追加します。
```xml
<SkypeSettings>  
        <CortanaWakewordEnabled>true</CortanaWakewordEnabled>  
</SkypeSettings> 
```
会議レベルでは、変更を加えるのは、デバイス Cortana _で_[音声のアクティブ化] が有効になっている場合のみです。  会議中にCortana _を有効_ にするには、[オン] または[オフ] を切 **り替え、無効** にします。 会議が終了すると、Cortana設定に戻ります。


会議レベルで変更を行う方法は、デバイス Cortana有効になっている場合に使用できます。

会議中にCortana _を有効_ にするには、[オン] または [オフ] の切り替 **えスイッチを****移動します**。 会議が終了すると、Cortana設定に戻ります。


## <a name="cortana-certified-devices-for-teams-rooms"></a>Cortana会議室の認定デバイスTeamsする
Cortana _500_ を使用している場合、またはこれらのデバイスを部屋に接続している場合は、音声のアクティブ化を有効にできます。
- Jabra Panacast 50 
- Rally microphones
- Bose Video Bar VB1 __
