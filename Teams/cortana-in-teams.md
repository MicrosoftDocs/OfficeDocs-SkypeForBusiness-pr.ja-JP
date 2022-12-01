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
description: Teams で Cortana 音声アシスタントを使用する方法について説明します
ms.localizationpriority: medium
ms.custom:
- Teams-upgrade-guidance
- chat-teams-channels-revamp
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 502f09891942796a326deba35e29fab234e6548a
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198499"
---
# <a name="cortana-voice-assistance-in-teams"></a>Teams での Cortana 音声アシスタンス

> [!NOTE]
> Cortana 音声アシスタンスは、iOS と Android 用の Microsoft Teams モバイル アプリ、Microsoft Teams ディスプレイ、米国、英国、カナダ、インド、オーストラリアのユーザー向けの Windows でのMicrosoft Teams Roomsでサポートされています。 Teams モバイル アプリの Cortana 音声アシスタントが、en-US の EDU のお客様に提供されるようになりました。 今後のリリースの一環として、追加の言語とリージョンへの拡張が行われる予定です。 Cortana 音声アシスタンスは、GCC、GCC-High、DoD、および米国以外の EDU テナントでは現在利用できません。

Teams モバイル アプリ、Windows Microsoft Teams Rooms、Microsoft Teams ディスプレイ デバイスの Cortana 音声アシスタントを使用すると、Microsoft 365 Enterprise ユーザーは、話し言葉の自然言語を使用して、コミュニケーション、コラボレーション、会議関連のタスクを効率化できます。 ユーザーは、Teams モバイル アプリの右上にあるマイク ボタンを選択するか、Microsoft Teams ルームで "Cortana" と言うか、Microsoft Teams ディスプレイを使用して Cortana と話すことができます。 チームにハンズフリーですばやく接続するために、ユーザーは "通話 Megan" や "次の会議にメッセージを送信する" などのクエリを言うことができます。 ユーザーは、"次の会議に参加する" と言って会議に参加し、音声アシスタントを使用してファイルの共有、予定表の確認などを行うこともできます。 これらの音声アシスタンス エクスペリエンスは、Office 365のプライバシー、セキュリティ、コンプライアンスに関する約束に完全に準拠した [Cortana エンタープライズ レベルのサービス](/microsoft-365/admin/misc/cortana-integration)を使用して提供されます。これは[、オンライン サービス条項 (OST)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1&preserve-view=true) に反映されています。

## <a name="admin-control-and-limitations"></a>管理の制御と制限事項

Teams の Cortana 音声アシスタンスは、オンライン サービス条項 (OST) に反映されているOffice 365エンタープライズ レベルのプライバシー、セキュリティ、コンプライアンスの約束に完全に準拠したサービスを使用して提供されます。 この機能は、テナントに対して既定で有効になります。

テナント管理者は、ポリシー (TeamsCortanaPolicy) を使用して、テナント内で Teams で Cortana 音声アシスタンスを使用できるユーザーを制御できます。 このポリシーは、ユーザー アカウント レベルまたはテナント レベルで設定されます。 管理者は、このポリシー コントロール内の CortanaVoiceInvocationMode フィールドを使用して、Cortana が無効になっているか、プッシュ ボタン呼び出しのみで有効になっているか、ウェイク ワード呼び出し (Microsoft Teams の表示など)もサポートするデバイスに適用されるかを判断できます。

管理者は、次の PowerShell コマンドレットを使用してこのポリシーを管理できます (現在、ポリシーは Teams 管理センター Microsoft使用できません)。

- [New-CsTeamsCortanaPolicy](/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [Get-CsTeamsCortanaPolicy](/powershell/module/skype/Get-CsTeamsCortanaPolicy)

- [Grant-CsTeamsCortanaPolicy](/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [Set-CsTeamsCortanaPolicy](/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [Remove-CsTeamsCortanaPolicy](/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

たとえば、次のコマンドを実行すると、"EmployeeCortanaPolicy" という名前の新しいポリシーが作成されます。ここで、Microsoft Teams の Cortana 音声アシスタンスは無効になっています。

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

この例では、"EmployeeCortanaPolicy" という名前の既存のポリシーを更新し、プッシュ ボタン呼び出しのみでMicrosoft Teams で Cortana 音声アシスタンスを有効にする方法を示します。 ユーザーは、Teams で [Cortana マイク] ボタンを選択することで Cortana を呼び出すことができます。 ウェイク ワード ("コルタナさん" または "Cortana") の呼び出しは無効になります。

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

この例では、ポリシーを更新し、プッシュ ボタンとウェイク ワード呼び出しの両方で Cortana 音声アシスタンスを有効にする方法を示します。

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

現時点では、米国のMicrosoft 365 Enterpriseユーザー向けの初期リリースの英語では、次の関数を使用できます。

- Teams モバイル アプリではウェイク ワードのアクティブ化はサポートされませんが、今後サポートされる予定です。

- Windows および Microsoft Teams ディスプレイ デバイスのMicrosoft Teams Roomsでは、ウェイク ワードのアクティブ化がサポートされます。

## <a name="user-control"></a>ユーザー コントロール

個々のユーザーは、さまざまなデバイスで Cortana 音声アシスタンスを試すことができます。

- Teams モバイル アプリでマイク ボタンを選択します。

- Microsoft Teams Roomsでマイク ボタンを選択するか、"Cortana" と言います。

- Teams でデバイスが表示Microsoft「Cortana」と言います。

Teams の Cortana をデバイスで有効にするかどうかを制御するには、デバイスの設定を使用します。

![は、Cortana を有効にしたときのモバイル ウィンドウの進行状況を示します。](media/cortana-mobile-sequence.png)

### <a name="microsoft-teams-rooms-on-windows"></a>Windows でのMicrosoft Teams Rooms

デバイス レベルでの変更は、Cortana がテナント レベルで有効になっている場合にのみ使用できます。

デバイス レベルでは、Cortana を 2 つの異なる方法で使用するように構成できます。 オプションまたは両方を同時に有効にすることができます。

- マイクをタップすると、Cortana Push と呼ばれ _、会話が行われる_
- _Cortana 音声ライセンス認証_ と呼ばれる "Hey,Cortana" と言います

Cortana _Push to talk_ は、お部屋が次のいずれかの言語で設定されている場合、既定で有効になります。en-au (オーストラリア)、en-ca (カナダ)、en-gb (英国)、en-in (インド)、en-us (米国)。 [詳細情報。](/MicrosoftTeams/rooms/console#to-apply-your-desired-language) Cortana アイコンは、Teams Room コンソールの [_その他] メニュー_ の [_表示_] ボタンを置き換えます。 Cortana _Push to talk を_ 無効にするには、PowerShell を使用します。[詳細情報。](/powershell/module/skype/new-csteamscortanapolicy?view=skype-ps#example-1&preserve-view=true)

Cortana _音声ライセンス認証_ を有効にするには、次の条件を満たす必要があります。

- Cortana 認定デバイスを Teams Room に接続する必要があります。 認定デバイスの一覧については、この記事の最後に説明します。
- Teams Room は、en-au (オーストラリア)、en-ca (カナダ)、en-gb (英国)、エンイン (インド)、en-us (米国) のいずれかの言語で設定する必要があります。 後日より多くの言語が利用できるようになります。
- 次のいずれかの構成変更を行う必要があります。
  - Teams 管理センターで機能を有効にする [詳細情報。](/microsoftteams/rooms/rooms-manage)
  - SkypeSettings XML ファイルに次の XML 属性を追加します。

    ```xml
    <SkypeSettings>
        <CortanaWakewordEnabled>true</CortanaWakewordEnabled>
    </SkypeSettings>
    ```

会議レベルでは、Cortana _音声ライセンス認証_ がデバイス レベルで有効になっている場合にのみ、変更を行うことができます。  会議中に Cortana _音声ライセンス認証_ を有効にするには、[ **オン]** または **[オフ]** を切り替えて無効にします。 会議が終了すると、Cortana はデバイス レベルの設定に戻ります。

Cortana がデバイス レベルで有効になっている場合は、会議レベルで変更を行うことができます。

会議中に Cortana _音声のアクティブ化_ を有効にするには、[ **オン]** または **[オフ**] の切り替えを移動します。 会議が終了すると、Cortana はデバイス レベルの設定に戻ります。

## <a name="cortana-certified-devices-for-teams-rooms"></a>Teams Rooms用の Cortana 認定デバイス

Cortana _音声ライセンス認証_ は、Lenovo Hub 500 を使用している場合、またはこれらのデバイスのいずれかが会議室に接続されている場合に有効にすることができます。

- Jabra Panacast 50
- Logi Rally Plus 会議システム
- Bose Video Bar VB1
- EPOS EXPAND Capture 5
- Yealink MSpeech
