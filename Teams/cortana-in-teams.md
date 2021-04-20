---
title: Microsoft Teams での Cortana 音声アシスタンス
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: akshbhat
search.appverid: MET150
description: Teams で Cortana 音声アシスタンスを使用する方法について
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
# <a name="cortana-voice-assistance-in-teams"></a>Teams での Cortana の音声アシスタンス

> [!Note]
> Cortana の音声アシスタントは、iOS および Android 用の Microsoft Teams モバイル アプリでサポートされ、Microsoft Teams の表示は米国、英国、カナダ、インド、およびオーストラリアのユーザー向けです。  Windows 上の Microsoft Teams の会議室は、米国内のユーザーにのみサポートされます。 Cortana の音声アシスタンスは現在、GCC、GCC-High、DoD、EDU テナントでは利用できません。 追加の言語と地域への拡張は、将来のリリースの一環として行います。

> [!Note]
> Microsoft Teams Rooms の Cortana 音声アシスタンスは、プレビューでリリースされます。 プレビュー 版リリースでは、Cortana は米国でのみサポートされています。Cortana は、Cortana マイクを接続しているデバイスで EN-US の言語を使用しています。

Microsoft 365 Enterprise ユーザーは、Teams モバイル アプリ、Windows の Microsoft Teams 会議室、および Microsoft Teams ディスプレイ デバイスで Cortana の音声アシスタンスを使用して、音声自然言語を使用して、コミュニケーション、コラボレーション、会議関連のタスクを合理化できます。 ユーザーは、Teams モバイル アプリの右上にあるマイク ボタンを選択するか、Microsoft Teams Room で &#8220;Cortana&#8221; と言うか、Microsoft Teams のディスプレイを使用して Cortana と話します。 チームとハンズフリーで簡単につながって、移動中に、ユーザーは &#8220;通話メーガン&#8221; や &#8220;などのクエリを言って、次の会議&#8221; にメッセージを送信できます。 ユーザーは、次の会議に参加&#8220;、音声&#8221;を使用してファイルの共有、予定表の確認などについて話し合って、会議に参加することもできます。 これらの音声アシスタンスエクスペリエンスは、オンライン サービス規約[(OST)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1)に反映される Office 365 のプライバシー、セキュリティ、コンプライアンスの約束に完全に準拠する[、Cortana](/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide)のエンタープライズ レベルのサービスを使用して配信されます。

画像は、モバイル デバイスで Cortana を使用してチャットを送信する場合を示しています。

![Cortana チャット セッションを表示する一連のモバイル画面](media/cortana-on-teams-mobile.png)

## <a name="admin-control-and-limitations"></a>管理者の制御と制限事項

Teams の Cortana 音声アシスタンスは、オンライン サービス規約 (OST) に反映される Office 365 エンタープライズ レベルのプライバシー、セキュリティ、コンプライアンスの約束に完全に準拠したサービスを使用して配信されます。 この機能は、テナントに対して既定で有効になります。

テナント管理者は、ポリシー (TeamsCortanaPolicy) を使用して、テナント内のユーザーが Teams で Cortana 音声アシスタンスを使用できるユーザーを制御できます。 このポリシーは、ユーザー アカウント レベルまたはテナント レベルで設定できます。 管理者は、このポリシー コントロール内の CortanaVoiceInvocationMode フィールドを使用して、Cortana が無効になっているか、プッシュ ボタン呼び出しでのみ有効になっているか、スリープ解除の単語呼び出しを有効にするか (Microsoft Teams の表示など、サポートしているデバイスに適用されます) を判断できます。

管理者は、次の PowerShell コマンドレットを使用してこのポリシーを管理できます (ポリシーは現在、Microsoft Teams 管理センターでは使用できません)。

- [New-CsTeamsCortanaPolicy](/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [Get-CsTeamsCortanaPolicy](/powershell/module/skype/Get-CsTeamsCortanaPolicy)

- [Grant-CsTeamsCortanaPolicy](/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [Set-CsTeamsCortanaPolicy](/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [Remove-CsTeamsCortanaPolicy](/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

たとえば、次のコマンドを実行すると、Microsoft Teams の Cortana 音声アシスタンスが無効&#8220;EmployeeCortanaPolicy&#8221; という名前の新しいポリシーが作成されます。  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

この例では、名前 &#8220;EmployeeCortanaPolicy&#8221; を使用して既存のポリシーを更新し、プッシュ ボタン呼び出しのみを使用して Microsoft Teams で Cortana 音声アシスタンスを有効にしています。 ユーザーは、Teams で Cortana のマイク ボタンを選択して Cortana を起動できます。 単語を覚ます (&#8220;Cortana&#8221; または cortana &#8220;&#8221;) 呼び出しは無効になります。  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

この例では、ポリシーを更新し、プッシュ ボタンとスリープ解除の両方の単語呼び出しで Cortana 音声アシスタンスを有効にしています。

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

米国英語の Microsoft 365 Enterprise ユーザー向け最初のリリースでは、次の機能を利用できます。

- Teams モバイル アプリではスリープ解除の単語のアクティブ化はサポートされませんが、今後サポートされる予定です。  

- Windows および Microsoft Teams の表示デバイス上の Microsoft Teams の会議室は、スリープ解除の単語のアクティブ化をサポートします。

## <a name="user-control"></a>ユーザー コントロール

個々のユーザーは、さまざまなデバイスで Cortana 音声アシスタンスを試しに行えます。

- Teams モバイル アプリでマイク ボタンを選択します。

- Microsoft Teams の会議室でマイク ボタンを選択するか、"Cortana" と言います。

- Microsoft Teams のディスプレイ デバイスで 「Cortana」と言います。

デバイスの設定を使用して、Teams の Cortana をデバイスで有効にするかどうかを制御できます。

### <a name="teams-mobile-app-or-the-microsoft-teams-display"></a>Teams モバイル アプリまたは Microsoft Teams の表示

  1. Teams モバイル アプリを開きます。

  2. [設定  >  **] Cortana を選択します**。

  3. [オン] または [ **オフ] を** 切り **替えます**。

### <a name="microsoft-teams-display"></a>Microsoft Teams の表示

  1. Microsoft Teams ディスプレイの環境 (ホーム) 画面に移動します。

  2. ユーザー アバターを選択し、[設定] を **選択します**。 Cortana が有効になっている場合は、"Cortana、設定に移動" と言います。

  3. [オン] または [ **オフ] を** 切り **替えます**。
  
### <a name="microsoft-teams-rooms-on-windows"></a>Windows 上の Microsoft Teams の会議室

デバイス レベルでの変更は、テナント レベルで Cortana が有効になっている場合に使用できます。 Cortana は既定でオフにリリースされます。

デバイス レベルで Cortana を有効にするには、次の XML 属性を SkypeSettings XML ファイルに追加する必要があります。

```xml
<SkypeSettings>  

        <CortanaEnabled>true</CortanaEnabled>  

        <CortanaWakewordEnabled>true</CortanaWakewordEnabled>  

</SkypeSettings> 
```

デバイス レベルで Cortana が有効になっている場合は、会議レベルで変更を行います。

会議中に Cortana の音声アシスタンスを有効にするには、[オン] または [オフ] を **切り** 替 **えます**。 会議が終了すると、Cortana はデバイス レベルの設定セットに戻ります。
