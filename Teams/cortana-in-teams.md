---
title: Cortanaでの音声アシスタンスのMicrosoft Teams
author: SerdarSoysal
ms.author: serdars
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
---

# <a name="cortana-voice-assistance-in-teams"></a>Cortanaでの音声アシスタンスのTeams

> [!Note]
> Cortana音声アシスタンスは、iOS および Android および Microsoft Teams ディスプレイ用の Microsoft Teams モバイル アプリで、米国、英国、カナダ、インド、オーストラリアのユーザー向けディスプレイでサポートされています。 Microsoft Teamsの会議室Windowsロケールが en-us に設定されているデバイスでのみサポートされます。 Cortana現在、GCC、GCC-High、DoD、米国以外の EDU テナントでは音声アシスタンスを使用できません。 Cortanaアプリの音声アシスタンスTeams、en-US の EDU のお客様が利用できます。 追加の言語と地域への拡張は、将来のリリースの一環として行う予定です。


Cortana モバイル アプリ、Teams Microsoft Teams Rooms on Windows、Microsoft Teams ディスプレイ デバイスで音声アシスタンスを使用すると、Microsoft 365 Enterprise ユーザーは、話し言葉の自然言語を使用して、コミュニケーション、コラボレーション、会議関連のタスクを効率化できます。 ユーザーは、Teams モバイル アプリの右上にあるマイク ボタンを選択するか、Microsoft Teams Room で "Cortana" と言うか、Microsoft Teams ディスプレイを使用するときに、Cortana と話し合います。 ハンズフリーでチームにすばやく接続するために、ユーザーは "Megan に電話する" や "次の会議にメッセージを送信する" などのクエリを言います。 ユーザーは、"次の会議に参加" と言って会議に参加し、音声アシスタンスを使用してファイルを共有し、予定表を確認することもできます。 これらの音声アシスタンス エクスペリエンスは、[Office 365](/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) のプライバシー、セキュリティ、およびコンプライアンスの約束に完全に準拠する Cortana エンタープライズ レベルのサービスを使用して提供されます 。これは、[Online Services Terms (OST)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1) に反映されます。

## <a name="admin-control-and-limitations"></a>管理者の制御と制限事項

Cortana Teams の音声アシスタンスは、online Services Terms (OST) に反映されている Office 365 エンタープライズ レベルのプライバシー、セキュリティ、コンプライアンスの約束に完全に準拠するサービスを使用して提供されます。 この機能は、テナントに対して既定で有効になります。

テナント管理者は、ポリシー (TeamsCortanaPolicy) を使用して、Cortanaの音声アシスタンスTeamsを使用できるテナントのユーザーを制御できます。 このポリシーは、ユーザー アカウント レベルまたはテナント レベルで設定されます。 管理者は、このポリシー コントロール内の CortanaVoiceInvocationMode フィールドを使用して、Cortana を無効にするか、プッシュ ボタン呼び出しでのみ有効にするか、ウェイク ワード呼び出しで有効にするか (Microsoft Teams ディスプレイなど、それをサポートするデバイスにも適用できます) を判断できます。

管理者は、次の PowerShell コマンドレットを使用してこのポリシーを管理できます (ポリシーは現在、管理センター Microsoft Teamsできません)。

- [New-CsTeamsCortanaPolicy](/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [Get-CsTeamsCortanaPolicy](/powershell/module/skype/Get-CsTeamsCortanaPolicy)

- [Grant-CsTeamsCortanaPolicy](/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [Set-CsTeamsCortanaPolicy](/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [Remove-CsTeamsCortanaPolicy](/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

たとえば、次のコマンドを実行すると、"EmployeeCortanaPolicy" という名前の新しいポリシーが作成されます。ここで、Cortanaの音声アシスタンスMicrosoft Teams無効になります。  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

この例では、"EmployeeCortanaPolicy" という名前の既存のポリシーを更新し、プッシュ ボタン呼び出しのみを使用して Microsoft Teams で Cortana 音声アシスタンスを有効にしています。 ユーザーは、アプリの [マイク] Cortanaを選択してCortanaを呼び出Teams。 ウェイク ワード ("Hey Cortana" または "Cortana") 呼び出しは無効になります。  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

この例では、ポリシーを更新し、プッシュ ボタンCortanaウェイク ワード呼び出しの両方で音声アシスタンスを有効にする方法を示します。

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

英語で米国内のユーザーをMicrosoft 365 Enterpriseリリース時点で、次の機能を使用できます。

- モバイル Teamsウェイク ワードのアクティブ化はサポートされませんが、今後サポートされる予定です。  

- Microsoft Teamsの会議室とWindowsデバイスMicrosoft Teamsデバイスでは、ウェイク ワードのアクティブ化がサポートされます。

## <a name="user-control"></a>ユーザー コントロール

個々のユーザーは、さまざまなデバイスCortana音声アシスタンスを試用できます。

- モバイル アプリの [マイク] Teams選択します。

- [会議室] でマイク ボタンを選択するかCortanaをMicrosoft Teamsします。

- デバイスを表示Cortana "Microsoft Teams" と言います。

デバイスの設定をCortanaをTeamsデバイスで有効にするかどうかを制御できます。

![を有効にした場合のモバイル ウィンドウの進行状況Cortana。](media/cortana-mobile-sequence.png)

### <a name="microsoft-teams-rooms-on-windows"></a>Microsoft Teamsの会議室Windows

デバイス レベルでの変更は、テナント レベルでCortana有効になっている場合にのみ使用できます。 

デバイス レベルでは、2 つの異なる方法Cortanaデバイスを構成できます。 オプションまたは両方を同時に有効にできます。 
- [プッシュして話す] と呼ばれるCortana _をタップする_
- "Hey, Cortana" と言って、音声Cortana _呼び出されます_

Cortana 、en-au (オーストラリア)、en-ca (カナダ)、en-gb (英国)、en-in (インド)、en-us (米国) の言語で部屋が設定されている場合、プッシュして話す機能は既定で有効になります。  [詳細情報。](/MicrosoftTeams/rooms/console#to-apply-your-desired-language) Cortanaアイコンをクリックすると、[詳細 _._..] の下にある [発表] _ボタンが置き換わります。_ を Teams選びます。 [プッシュしてCortana _を無効にするには、_ PowerShell を使用します。[詳細情報。](/powershell/module/skype/new-csteamscortanapolicy?view=skype-ps#example-1)

音声のCortana _を有効にするには_、次の条件を満たしている必要があります。
- 認定Cortanaデバイスは、お使いの Teams Room に接続されている必要があります。 認定デバイスの一覧は、この記事の最後で確認できます。
- Teams Room は、en-au (オーストラリア)、en-ca (カナダ)、en-gb (英国)、en-in (インド)、en-us (米国) の言語で設定する必要があります。 その他の言語は、後日提供される予定です。
- 次のいずれかの構成変更を行う必要があります。
  - 管理センターで機能を有効Teams詳細[を確認してください。](/microsoftteams/rooms/rooms-manage)
  - SkypeSettings XML ファイルに次の XML 属性を追加します。

    ```xml
    <SkypeSettings>  
        <CortanaWakewordEnabled>true</CortanaWakewordEnabled>  
    </SkypeSettings> 
    ```
    
会議レベルでは、デバイス レベルで [音声のアクティブ化] Cortana _有効_ になっている場合にのみ、変更を行えます。  会議中にCortana _を_ 有効にするには、[オン] または [オフ] を切 **り替え、** 無効にします。 会議が終了すると、Cortana設定に戻ります。


会議レベルで変更を行う方法は、Cortanaレベルで有効になっている場合に使用できます。

会議中にCortana _を有効_ にするには、[オン] または [オフ] を **切** り替 **えます**。 会議が終了すると、Cortana設定に戻ります。


## <a name="cortana-certified-devices-for-teams-rooms"></a>Cortana会議室の認定デバイスTeamsする
Cortana 500  を使用している場合、またはこれらのデバイスを部屋に接続している場合は、音声のアクティブ化を有効にできます。
- Jabra Panacast 50 
- Rally microphones
- Bose Video Bar VB1

