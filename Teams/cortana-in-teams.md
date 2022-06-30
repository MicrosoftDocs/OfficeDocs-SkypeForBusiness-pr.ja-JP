---
title: Microsoft Teams での Cortana 音声アシスタンス
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: akshbhat
search.appverid: MET150
description: Teams で Cortana 音声アシスタンスを使用する方法について説明します
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
ms.openlocfilehash: b3c4ff65fb87bed077e1020764382314d5d15c62
ms.sourcegitcommit: ff783fad2fb5d412e864e3af2ceaa8fedcd9da07
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/30/2022
ms.locfileid: "66562436"
---
# <a name="cortana-voice-assistance-in-teams"></a>Teams での Cortana 音声アシスタンス

> [!NOTE]
> Cortana 音声アシスタンスは、米国、英国、カナダ、インド、オーストラリアのユーザー向けに、iOS および Android および Microsoft Teams 用の Microsoft Teams モバイル アプリでサポートされています。 Windows でのMicrosoft Teams Roomsは、ロケールが en-us に設定されているデバイスでのみサポートされます。 Cortana 音声アシスタンスは、GCC、GCC-High、DoD、および米国以外の EDU テナントでは現在使用できません。 Teams モバイル アプリの Cortana 音声アシスタンスが、en-US の EDU のお客様に提供されるようになりました。 今後のリリースの一環として、追加の言語とリージョンへの拡張が行われます。

Teams モバイル アプリ、Windows 上のMicrosoft Teams Rooms、Microsoft Teams のディスプレイ デバイスでの Cortana 音声アシスタンスを使用すると、Microsoft 365 Enterpriseユーザーは音声自然言語を使用してコミュニケーション、コラボレーション、会議関連のタスクを効率化できます。 ユーザーは、Teams モバイル アプリの右上にあるマイク ボタンを選択するか、Microsoft Teams ルームで "Cortana" と言うか、Microsoft Teams ディスプレイを使用して Cortana と話すことができます。 ハンズフリーで、外出先でチームにすばやく接続するために、ユーザーは "Megan の呼び出し" や "次の会議にメッセージを送信する" などのクエリを言うことができます。 ユーザーは、"次の会議に参加する" と言って会議に参加したり、音声アシスタンスを使用してファイルを共有したり、予定表を確認したりすることもできます。 これらの音声アシスタンス エクスペリエンスは、Office 365のプライバシー、セキュリティ、コンプライアンスの約束に完全に準拠する [Cortana エンタープライズ レベルのサービス](/microsoft-365/admin/misc/cortana-integration)を使用して提供されます[。これは、Online Services 利用規約 (OST)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1&preserve-view=true) に反映されます。

## <a name="admin-control-and-limitations"></a>管理制御と制限事項

Teams の Cortana 音声アシスタンスは、Online Services の利用規約 (OST) に示されているように、Office 365エンタープライズ レベルのプライバシー、セキュリティ、コンプライアンスの約束に完全に準拠するサービスを使用して提供されます。 この機能は、テナントに対して既定で有効になります。

テナント管理者は、ポリシー (TeamsCor cortanPolicy) を使用して、テナント内のだれが Teams で Cortana 音声アシスタンスを使用できるかを制御できます。 このポリシーは、ユーザー アカウント レベルまたはテナント レベルで設定されます。 管理者は、このポリシー コントロール内の CortanaVoiceInvocationMode フィールドを使用して、Cortana が無効になっているか、プッシュ ボタン呼び出しでのみ有効になっているか、ウェイク ワード呼び出しで有効になっているかを判断できます (Microsoft Teams の表示など、それをサポートするデバイスにも適用されます)。

管理者は、次の PowerShell コマンドレットを使用してこのポリシーを管理できます (ポリシーは現在、Microsoft Teams 管理センターでは使用できません)。

- [New-CsTeamsCortanaPolicy](/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [Get-CsTeamsCortanaPolicy](/powershell/module/skype/Get-CsTeamsCortanaPolicy)

- [Grant-CsTeamsCortanaPolicy](/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [Set-CsTeamsCortanaPolicy](/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [Remove-CsTeamsCortanaPolicy](/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

たとえば、次のコマンドでは、Microsoft Teams の Cortana 音声アシスタンスが無効になっている "EmployeeCor cortanpolicy" という名前の新しいポリシーが作成されます。

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

この例では、"EmployeeCor cortanPolicy" という名前の既存のポリシーを更新し、プッシュ ボタンの呼び出しのみで Microsoft Teams で Cortana 音声アシスタンスを有効にする方法を示します。 ユーザーは、Teams の [Cortana mic] ボタンを選択して Cortana を呼び出すことができます。 ウェイク ワード ("Cortana さん" または "Cortana") の呼び出しは無効になります。

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

この例では、ポリシーを更新し、プッシュ ボタンとウェイク ワード呼び出しの両方で Cortana 音声アシスタンスを有効にする方法を示します。

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

米国のMicrosoft 365 Enterprise ユーザー向けの初期リリースの時点では、次の機能を使用できます。

- Teams モバイル アプリではウェイク ワードのアクティブ化はサポートされませんが、今後サポートされる予定です。

- Windows および Microsoft Teams ディスプレイ デバイスのMicrosoft Teams Roomsでは、ウェイク ワードのアクティブ化がサポートされます。

## <a name="user-control"></a>ユーザー コントロール

個々のユーザーは、さまざまなデバイスで Cortana 音声アシスタンスを試すことができます。

- Teams モバイル アプリでマイク ボタンを選択します。

- マイク ボタンを選択するか、Microsoft Teams Roomsで "Cortana" と入力します。

- Microsoft Teams で "Cortana" と言うと、デバイスが表示されます。

デバイスの設定を使用して、Teams の Cortana をデバイスに対して有効にするかどうかを制御できます。

![は、Cortana を有効にしたときのモバイル ウィンドウの進行を示します。](media/cortana-mobile-sequence.png)

### <a name="microsoft-teams-rooms-on-windows"></a>Windows でのMicrosoft Teams Rooms

デバイス レベルでの変更は、Cortana がテナント レベルで有効になっている場合にのみ使用できます。

デバイス レベルでは、2 つの異なる方法で使用するように Cortana を構成できます。 次のいずれかのオプションを有効にすることも、両方を同時に有効にすることもできます。

- Cortana Push と呼ばれるマイクをタップして _話す_
- "ねえ、Cortana"と言うことで、_Cortana Voice Activation_ と呼ばれます。

cortana _Push to talk_ は、お使いの部屋が次のいずれかの言語で設定されている場合、既定で有効になります。en-au (オーストラリア)、en-ca (カナダ)、en-gb (イギリス)、en-in (インド)、en-us (米国)。 [詳細情報。](/MicrosoftTeams/rooms/console#to-apply-your-desired-language) Cortana アイコンは、Teams Room コンソールの [_その他]..._ メニューの [_現在_] ボタンを置き換えます。 Cortana _Push を無効にして話すには_ 、PowerShell を使用します。[詳細情報。](/powershell/module/skype/new-csteamscortanapolicy?view=skype-ps#example-1)

Cortana _音声アクティブ化_ を有効にするには、次の条件を満たす必要があります。

- Cortana 認定デバイスが Teams ルームに接続されている必要があります。 認定されたデバイスの一覧は、この記事の最後にあります。
- Teams Room は、en-au (オーストラリア)、en-ca (カナダ)、en-gb (イギリス)、en-in (インド)、en-us (米国) のいずれかで設定する必要があります。 その他の言語は後日利用可能になります。
- 次のいずれかの構成変更を行う必要があります。
  - Teams 管理センターの機能を有効にします [。詳細については、こちらを参照してください。](/microsoftteams/rooms/rooms-manage)
  - 次の XML 属性を SkypeSettings XML ファイルに追加します。

    ```xml
    <SkypeSettings>
        <CortanaWakewordEnabled>true</CortanaWakewordEnabled>
    </SkypeSettings>
    ```

会議レベルでは、Cortana _Voice Activation_ がデバイス レベルで有効になっている場合にのみ、変更を行うことができます。  会議中に Cortana _Voice Activation を_ 有効にするには、トグルを **[オン]** または **[オフ]** に移動して無効にします。 会議が終了すると、Cortana はデバイス レベルの設定セットに戻ります。

デバイス レベルで Cortana が有効になっている場合は、会議レベルで変更を行えます。

会議中に Cortana _音声アクティブ化_ を有効にするには **、オンまたは** オフのトグルを移動 **します**。 会議が終了すると、Cortana はデバイス レベルの設定セットに戻ります。

## <a name="cortana-certified-devices-for-teams-rooms"></a>Teams Rooms用 Cortana 認定デバイス

Cortana _Voice Activation_ は、Lenovo Hub 500 を使用している場合、またはお使いの部屋に接続されているデバイスがある場合に有効にすることができます。

- Jabra Panacast 50
- Rally マイク
- Bose ビデオ バー VB1
- エポポス EXPAND Capture 5
- Yealink MSpeech
