---
title: 保留音
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
audience: Admin
ms.reviewer: roykuntz
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.custom: Learn how to manage the Music on Hold feature in Phone System.
ms.openlocfilehash: 5e28aa4774d105b687551601ba89657d91a08170
ms.sourcegitcommit: 31da77589ac82c43a89a9c53f2a2de5ab52f93c0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/14/2021
ms.locfileid: "60356555"
---
# <a name="music-on-hold"></a>保留音

ユーザーがMicrosoft Teams公衆交換電話網 (PSTN) からの着信通話を保留にした場合、PSTN 発信者は選択した音楽を聞き取ります。

再生される音楽は、Microsoft が提供する既定の音楽か、アップロードして構成するカスタム音楽のいずれかです。 テナント管理者は、Teams 呼び出し元ポリシーを作成し、そのユーザーにポリシーを割り当てるTeamsします。 

PSTN 発信者は、他のシナリオでも保留音を聞けるので注意してください。たとえば、クラウド通話キューにコールインする場合や、通話がユーザーによってMicrosoft Teamsされます。 これらのシナリオは、この記事で説明する機能によってカバーまたは制御されません。 

## <a name="configure-music-on-hold"></a>保留音の構成

保留音を構成するには:

1.  管理センターの左側のナビゲーションTeams、[音声通話] >**に移動します**。

2.  [ポリシー **の管理] タブ** で、既存のポリシーのいずれかを選択するか、新しいポリシーを作成します。

3.  **[PSTN 発信者の保留音]** フィールドで、ドロップダウン メニューの **[** 有効] を選択します。

PowerShell モジュールの一部を使用して、保留Teams構成できます。 TeamsCallingPolicy で、MusicOnHoldEnabledType パラメーターを Enabled に変更し、そのポリシー インスタンスを 1 人または複数のユーザーに付与します。

Teamsのユーザーが [保留時の音楽] を [無効] に設定した Teams 通話ポリシーを持つ場合、Teams ユーザーが通話を保留にした場合、音楽は再生されません。

## <a name="configure-custom-music"></a>カスタム 音楽を構成する

> [!NOTE]
> この機能は、パブリック プレビュー リリースとして利用できます。

PSTN 呼び出し元に既定の音楽を再生する以外に、音楽や他のオーディオ コンテンツを含むカスタム オーディオ ファイルをアップロードし、そのオーディオ ファイルを PSTN 呼び出し元に再生する構成を行います。
たとえば、部門や組織では、外部 PSTN 発信者が保留にされている場合に、カスタムアナウンスやカスタム 音楽を再生することができます。  

> [!NOTE]
> お客様は、お客様の音楽またはオーディオ ファイルを使用するために必要なすべての権利とアクセス許可を、Microsoft Teamsします。 これには、すべての関連する権利保有者の音楽、サウンド エフェクト、オーディオ、ブランド、名前、およびオーディオ ファイル内のその他のコンテンツに含まれる知的財産などの権利が含まれる場合があります。 所有者には、アーティスト、アクター、パフォーマー、音楽家、曲者、レコード ラベル、音楽パブリッシャー、ユニオン、ギルド、権限保護団体、集合管理組織、音楽著作権、サウンド エフェクト、オーディオ、その他の知的財産権を所有、管理、またはライセンスしているその他の当事者が含まれます。

カスタムの保留音を構成するには、Teams PowerShell モジュール 2.5.0 以降の PowerShell コマンドレット New/Get/Set/Grant/Remove-CsTeamsCallHoldPolicy および Import/Get/Remove-CsOnlineAudioFile を使用します。


1. 通話ポリシーでTeams PSTN 発信者の音楽が [有効] に設定Teams確認します。 

2. アップロード オーディオ ファイルを開く。

3. カスタム オーディオ Teamsを参照する通話ホールド ポリシーを作成し、それをユーザーに割りTeamsします。

### <a name="upload-the-custom-audio-file"></a>アップロード オーディオ ファイルを作成する

保留のカスタムミュージックの構成は、オーディオ ファイルのアップロードから始まります。 この目的には、PowerShell コマンドレットImport-CsOnlineAudioFile使用します。 PowerShell インターフェイスを使用して MP3 オーディオ ファイルをアップロードする例を次に示します。

```PowerShell
C:\> $content = Get-Content "C:\tmp\customMoH1.mp3" -Encoding byte -ReadCount 0
C:\> $AudioFile = Import-CsOnlineAudioFile -FileName "customMoH1.mp3" -Content $content
C:\> $AudioFile
Id            : 56a56961f2794f098a359885ec1454a1
FileName      : customMoH1.mp3
ApplicationId : TenantGlobal
```

### <a name="reference-the-audio-file-in-a-teams-call-hold-policy"></a>通話ホールド ポリシーでオーディオ Teamsを参照する

オーディオ ファイルをアップロードしたら、Teams 通話ホールド ポリシーを作成または設定するときに、ファイルの Teams ID を使用して Teams 通話ホールド ポリシー内のファイルを参照する必要があります。 次に例を示します。

```PowerShell
C:\> New-CsTeamsCallHoldPolicy -Identity "CustomMoH1" -Description "Custom MoH using CustomMoH1.mp3" -AudioFileId $AudioFile.Id
```

新しい通話ホールド ポリシーをTeamsしたら、次の方法でユーザーにGrant-CsTeamsCallHoldPolicyできます。

```PowerShell
C:\> Grant-CsTeamsCallHoldPolicy -PolicyName "CustomMoH1" -Identity user1@contoso.com
```

アップロードしたオーディオ ファイルに関する情報を取得するには、次のコマンドレットGet-CsOnlineAudioFileします。

アップロードしたオーディオ ファイルを削除するには、次のコマンドレットRemove-CsOnlineAudioFileします。 オーディオ ファイルを削除する前に、TeamsCallHoldPolicy でオーディオ ファイルを使用していないか確認してください。

## <a name="feature-availability"></a>機能の可用性

次の表は、保留時の音楽と保留音のカスタム音楽をサポートするクライアントとデバイスの機能を示しています。 Microsoft では引き続き機能のサポートが追加されています。そのため、頻繁に追加の可用性を確認してください。


| 機能 | デスクトップ <br> Windows/Mac OS | ブラウザー | モバイル <br> iOS | モバイル <br> Android | Teams 電話 |
| :------------| :------- | :------- | :------- | :------- | :------- |
| 1 対 1 の PSTN 通話を保留する | -保留音<br>-Custom Music on Hold | -保留音<br>-Custom Music on Hold | -保留音<br>-Custom Music on Hold | 保留音 | 保留音 |
| 1 対 1 PSTN 通話でコンサルティング転送を保留する |-保留音<br>-Custom Music on Hold | | | | |

## <a name="restrictions"></a>制限

- 保留音は商用クラウドでのみ利用できます。

- 保留音は、ユーザーが TeamsOnly モードの場合にのみ使用できます。

- 呼び出されたユーザー Teamsルーティングが有効Location-Based場合、保留音を呼び出し元に再生することはできません。

- アップロード後にオーディオ ファイルをエクスポートできません。削除できるのは削除のみです。

- Custom Music on Hold は、共有行の外観 (委任) 用に構成されたユーザーと、Call Park が使用されている場合は使用できません。 標準の保留音が再生されます。

- 一部のシナリオでは、ダイレクト ルーティング メディア バイパス呼び出しは、保留時の音楽を再生するためにメディア以外のバイパスに変換され、通話が終了するまで非メディア バイパスとして保持されます。


## <a name="related-topics"></a>関連項目

- [ユーザーにポリシーを割り当てる](assign-policies.md)

- [Get-CsTeamsCallingPolicy](/powershell/module/skype/get-csteamscallingpolicy?view=skype-ps)

- [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)

- [Get-CsOnlineAudioFile](/powershell/module/skype/get-csonlineaudiofile?view=skype-ps)

- [Remove-CsOnlineAudioFile](/powershell/module/skype/remove-csonlineaudiofile?view=skype-ps)

- [New-CsTeamsCallHoldPolicy](/powershell/module/skype/new-csteamscallholdpolicy?view=skype-ps)

- [Get-CsTeamsCallHoldPolicy](/powershell/module/skype/get-csteamscallholdpolicy?view=skype-ps)

- [Grant-CsTeamsCallHoldPolicy](/powershell/module/skype/grant-csteamscallholdpolicy?view=skype-ps)

- [Remove-CsTeamsCallHoldPolicy](/powershell/module/skype/remove-csteamscallholdpolicy?view=skype-ps)

- [Import-CsOnlineAudioFile](/powershell/module/skype/import-csonlineaudiofile?view=skype-ps)





