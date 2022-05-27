---
title: Microsoft Teamsでの音声アシスタンスのCortana
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: akshbhat
search.appverid: MET150
description: Teamsで音声アシスタンスCortana使用する方法について説明します
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
ms.openlocfilehash: b79640b5f9d85b845c8d7c74fa1d6931931a6b50
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/25/2022
ms.locfileid: "65674989"
---
# <a name="cortana-voice-assistance-in-teams"></a>Teamsで音声アシスタンスをCortanaする

> [!NOTE]
> Cortana音声アシスタンスは、米国、英国、カナダ、インド、オーストラリアのユーザー向けのiOSおよびAndroidおよびMicrosoft Teamsディスプレイ用のMicrosoft Teamsモバイル アプリでサポートされています。 WindowsのMicrosoft Teams Roomsは、ロケールが en-us に設定されているデバイスでのみサポートされます。 Cortana音声アシスタンスは、現在、GCC、GCC-High、DoD、および米国以外の EDU テナントでは利用できません。 Teams モバイル アプリの音声サポートCortana、en-US の EDU のお客様が利用できるようになりました。 今後のリリースの一環として、追加の言語とリージョンへの拡張が行われます。

Teams モバイル アプリ、WindowsのMicrosoft Teams Rooms、およびディスプレイ デバイスで音声サポート Microsoft TeamsをCortanaすると、Microsoft 365 Enterprise ユーザーは、音声自然言語を使用してコミュニケーション、コラボレーション、会議関連のタスクを効率化できます。 ユーザーは、Teams モバイル アプリの右上にあるマイク ボタンを選択するか、Microsoft Teams ルームで "Cortana" と言うか、Microsoft Teams ディスプレイを使用して、Cortanaに話しかけることができます。 ハンズフリーで、外出先でチームにすばやく接続するために、ユーザーは "Megan の呼び出し" や "次の会議にメッセージを送信する" などのクエリを言うことができます。 ユーザーは、"次の会議に参加する" と言って会議に参加したり、音声アシスタンスを使用してファイルを共有したり、予定表を確認したりすることもできます。 これらの音声アシスタンス エクスペリエンスは、Office 365のプライバシー、セキュリティ、およびコンプライアンスの約束に完全に準拠する[エンタープライズ レベルのサービス](/microsoft-365/admin/misc/cortana-integration)Cortanaを使用して提供されます[。これは、Online Services Terms (OST)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1&preserve-view=true) に反映されます。

## <a name="admin-control-and-limitations"></a>管理制御と制限事項

TeamsでのCortana音声アシスタンスは、Online Services 利用規約 (OST) に示されているように、Office 365エンタープライズ レベルのプライバシー、セキュリティ、コンプライアンスの約束に完全に準拠するサービスを使用して提供されます。 この機能は、テナントに対して既定で有効になります。

テナント管理者は、テナント内のユーザーがポリシー (TeamsCortanaPolicy) を使用してTeamsでCortana音声アシスタンスを使用できるかを制御できます。 このポリシーは、ユーザー アカウント レベルまたはテナント レベルで設定されます。 管理者は、このポリシー コントロール内の CortanaVoiceInvocationMode フィールドを使用して、Cortanaが無効になっているか、プッシュ ボタン呼び出しでのみ有効になっているか、ウェイク ワード呼び出しで有効にするか (Microsoft Teams表示など、それをサポートするデバイスにも適用できます) を判断できます。

管理者は、次の PowerShell コマンドレットを使用してこのポリシーを管理できます (ポリシーは現在、Microsoft Teams管理センターでは使用できません)。

- [New-CsTeamsCortanaPolicy](/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [Get-CsTeamsCortanaPolicy](/powershell/module/skype/Get-CsTeamsCortanaPolicy)

- [Grant-CsTeamsCortanaPolicy](/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [Set-CsTeamsCortanaPolicy](/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [Remove-CsTeamsCortanaPolicy](/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

たとえば、次のコマンドでは、"EmployeeCortanaPolicy" という名前の新しいポリシーが作成され、Microsoft Teamsの音声アシスタンスCortana無効になります。

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

この例では、"EmployeeCortanaPolicy" という名前の既存のポリシーを更新し、プッシュ ボタン呼び出しのみでMicrosoft Teamsで音声アシスタンスCortana有効にする方法を示します。 ユーザーは、TeamsでCortanaマイク ボタンを選択することで、Cortanaを呼び出すことができます。 ウェイク ワード ("Hey Cortana" または "Cortana") の呼び出しは無効になります。

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

この例では、ポリシーを更新し、プッシュ ボタンとウェイク ワード呼び出しの両方で音声アシスタンスCortana有効にする方法を示します。

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

米国のMicrosoft 365 Enterprise ユーザー向けの初期リリースの時点では、次の機能を使用できます。

- Teamsモバイル アプリではウェイク ワードのアクティブ化はサポートされませんが、今後サポートされる予定です。

- WindowsおよびMicrosoft Teamsディスプレイ デバイスのMicrosoft Teams Roomsでは、ウェイク ワードのアクティブ化がサポートされます。

## <a name="user-control"></a>ユーザー コントロール

個々のユーザーは、さまざまなデバイスで音声アシスタンスCortana試すことができます。

- Teamsモバイル アプリでマイク ボタンを選択します。

- マイク ボタンを選択するか、Microsoft Teams Roomsで "Cortana" と入力します。

- デバイスを表示Microsoft Teamsで"Cortana" と言います。

デバイスの設定を使用して、TeamsのCortanaをデバイスに対して有効にするかどうかを制御できます。

![は、Cortanaを有効にしたときのモバイル ウィンドウの進行状況を示します。](media/cortana-mobile-sequence.png)

### <a name="microsoft-teams-rooms-on-windows"></a>WindowsのMicrosoft Teams Rooms

デバイス レベルでの変更は、テナント レベルでCortanaが有効になっている場合にのみ使用できます。

デバイス レベルでは、2 つの異なる方法で使用するCortanaを構成できます。 次のいずれかのオプションを有効にすることも、両方を同時に有効にすることもできます。

- マイクをタップすると、Cortana _Push to talk_ と呼ばれます。
- _音声アクティブ化_ と呼ばれる "hey, Cortana" と言Cortana

Cortana _Push to talk_ は、en-au (オーストラリア)、en-ca (カナダ)、en-gb (イギリス)、en-in (インド)、en-us (米国) のいずれかの言語で設定されている場合、既定で有効になっています。 [詳細情報。](/MicrosoftTeams/rooms/console#to-apply-your-desired-language) Cortanaアイコンをクリックすると、Teams Room コンソールの [_その他]..._ メニューの [_現在_] ボタンが置き換えられます。 _プッシュして話_ すCortana無効にするには、PowerShell を使用します。[詳細情報。](/powershell/module/skype/new-csteamscortanapolicy?view=skype-ps#example-1)

_音声アクティブ化_ Cortana有効にするには、次の条件を満たす必要があります。

- Cortana認定されたデバイスは、Teams ルームに接続されている必要があります。 認定されたデバイスの一覧は、この記事の最後にあります。
- Teamsルームは、en-au (オーストラリア)、en-ca (カナダ)、en-gb (イギリス)、en-in (インド)、en-us (米国) のいずれかで設定する必要があります。 その他の言語は後日利用可能になります。
- 次のいずれかの構成変更を行う必要があります。
  - 管理センターの機能Teamsオンにします[。詳細については、こちらを参照してください。](/microsoftteams/rooms/rooms-manage)
  - 次の XML 属性を SkypeSettings XML ファイルに追加します。

    ```xml
    <SkypeSettings>
        <CortanaWakewordEnabled>true</CortanaWakewordEnabled>
    </SkypeSettings>
    ```

会議レベルでは、デバイス レベルで _音声アクティブ化_ Cortana有効になっている場合にのみ、変更を行うことができます。  会議中Cortana _音声アクティブ化_ を有効にするには、トグルを **オン** にするか **、オフ** に切り替えて無効にします。 会議が終了すると、Cortanaはデバイス レベルの設定セットに戻ります。

デバイス レベルでCortanaが有効になっている場合は、会議レベルで変更を行えます。

会議中Cortana _音声アクティブ化_ を有効にするには、トグル **をオン** または **オフに** 切り替えます。 会議が終了すると、Cortanaはデバイス レベルの設定セットに戻ります。

## <a name="cortana-certified-devices-for-teams-rooms"></a>Teams Rooms用に認定されたデバイスをCortanaする

Lenovo Hub 500 を使用している場合、または次のいずれかのデバイスをルームに接続している場合は、_音声アクティブ化_ を有効にCortanaできます。

- Jabra Panacast 50
- Rally マイク
- Bose ビデオ バー VB1
- エポポス EXPAND Capture 5
- Yealink MSpeech
