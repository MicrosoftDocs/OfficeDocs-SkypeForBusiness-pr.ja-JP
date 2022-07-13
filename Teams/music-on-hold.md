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
ms.custom: ''
description: 電話システムで保留音機能を管理する方法について説明します。
ms.openlocfilehash: 9d8fa247ffdc982c5d41777c68f6b620a92644e3
ms.sourcegitcommit: 8fc2d6a824e1e119f54ea2347bc5c10cc076956d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/13/2022
ms.locfileid: "66773756"
---
# <a name="music-on-hold"></a>保留音

Microsoft Teams ユーザーが着信を保留にすると、呼び出し元は選択した音楽を聞くことができます。

再生される音楽は、Microsoft によって提供される既定の音楽か、アップロードして構成するカスタム 音楽です。 テナント管理者は、Teams の通話ポリシーを作成し、ポリシーを Teams ユーザーに割り当てることで、保留音を使用できるかどうかを構成します。

Microsoft Teams の通話シナリオで提供される既定の音楽には、組織が支払う使用料は無料です。

呼び出し元は、他のシナリオでも保留音を聞くことができることに注意してください。たとえば、クラウド通話キューに呼び出す場合や、Microsoft Teams ユーザーによって通話がパークされている場合などです。 これらのシナリオは、この記事で説明した機能では説明または制御されません。

## <a name="configure-music-on-hold"></a>保留音の構成

保留音を構成するには:

1. Teams 管理センターの左側のナビゲーションで、 **音声>通話ポリシー** に移動します。

2. [ **ポリシーの管理** ] タブで、既存のポリシーのいずれかを選択するか、新しいポリシーを作成します。

3. [ **PSTN 発信者の保留音** ] フィールドで、ドロップダウン メニューで **[有効]** を選択します。

Teams PowerShell モジュールを使用して保留音を構成することもできます。 TeamsCallingPolicy で、MusicOnHoldEnabledType パラメーターを Enabled に変更し、そのポリシー インスタンスを 1 人以上のユーザーに付与します。

Teams ユーザーが保留音が無効に設定された Teams 通話ポリシーを持っている場合、Teams ユーザーが通話を保留にしても、音楽は再生されません。

## <a name="configure-custom-music"></a>カスタム 音楽を構成する

既定の音楽を呼び出し元に再生するだけでなく、音楽やその他のオーディオ コンテンツを含むカスタム オーディオ ファイルをアップロードし、そのオーディオ ファイルを呼び出し元に再生するように構成することもできます。
たとえば、部門や組織が、外部 PSTN 発信者を保留にするときに、カスタムアナウンスやカスタム 音楽を再生したい場合があります。

構成は、通話保留ポリシーを使用して行われます。

> [!NOTE]
> お客様は、Microsoft Teams サービスで音楽またはオーディオ ファイルを使用するために必要なすべての権利とアクセス許可を個別にクリアし、セキュリティで保護する責任があります。 これには、すべての関連する権利保有者からのオーディオ ファイル内の音楽、サウンド エフェクト、オーディオ、ブランド、名前、およびその他のコンテンツの知的財産権およびその他の権利が含まれる場合があります。 所有者には、アーティスト、アクター、パフォーマー、音楽家、曲ライター、作曲家、レコード ラベル、音楽パブリッシャー、ユニオン、ギルド、権利団体、集合管理組織、音楽著作権、サウンド エフェクト、オーディオ、その他の知的財産権を所有、管理、ライセンス供与するその他の当事者が含まれる場合があります。

### <a name="use-the-teams-admin-center"></a>Teams 管理センターを使用する
Teams 管理センターを使用して、通話ホールド ポリシーを作成または編集することで、ユーザーの保留音を構成できます。

新しい保留ポリシーを構成するには:

1. Teams 管理センターで、 **音声** > **通話ホールド ポリシー** に移動します。

2. [ **追加]** タブを選択します。

3. ポリシーに名前と説明を付けます。

4. [ **ファイルのアップロード]** を選択して、カスタム音楽オーディオ ファイルをアップロードします。

5. **[適用]** を選択します。

### <a name="assign-a-custom-call-hold-policy-to-users"></a>ユーザーにカスタム通話保留ポリシーを割り当てる

[!INCLUDE [assign-policy](includes/assign-policy.md)]

### <a name="use-powershell"></a>PowerShell を使用する
保留のカスタムミュージックを構成するには、Teams PowerShell モジュール 3.0.0 以降で PowerShell コマンドレット New/Get/Set/Grant/Remove-CsTeamsCallHoldPolicy と Import/Get/Remove/Export-CsOnlineAudioFile を使用します。

サポートされているオーディオ形式と最大ファイル サイズについては、「[Import-CsOnlineAudioFile](/powershell/module/skype/import-csonlineaudiofile)」を参照してください。

1. Teams の通話ポリシーで、Teams ユーザーが PSTN 発信者の保留音を有効に設定していることを確認します。 

2. カスタム オーディオ ファイルをアップロードします。

3. カスタム オーディオ ファイルを参照する Teams 通話保留ポリシーを作成し、Teams ユーザーに割り当てます。

### <a name="upload-the-custom-audio-file"></a>カスタム オーディオ ファイルをアップロードする

カスタム保留音の構成は、オーディオ ファイルのアップロードから始まります。 この目的のために PowerShell コマンドレット [Import-CsOnlineAudioFile](/powershell/module/skype/import-csonlineaudiofile) を使用します。

Windows PowerShell 5.1 を使用して MP3 オーディオ ファイルをアップロードする例を次に示します。 その他の例については、「 [Import-CsOnlineAudioFile](/powershell/module/skype/import-csonlineaudiofile)」を参照してください。

```PowerShell
C:\> $content = Get-Content "C:\tmp\customMoH1.mp3" -Encoding byte -ReadCount 0
C:\> $AudioFile = Import-CsOnlineAudioFile -FileName "customMoH1.mp3" -Content $content
C:\> $AudioFile
Id            : 56a56961f2794f098a359885ec1454a1
FileName      : customMoH1.mp3
ApplicationId : TenantGlobal
```

### <a name="reference-the-audio-file-in-a-teams-call-hold-policy"></a>Teams 通話ホールド ポリシーでオーディオ ファイルを参照する

オーディオ ファイルをアップロードしたら、Teams 通話保持ポリシーを作成または設定するときに、ファイルの ID を使用して Teams 通話保持ポリシー内のファイルを参照する必要があります。 次に例を示します。

```PowerShell
C:\> New-CsTeamsCallHoldPolicy -Identity "CustomMoH1" -Description "Custom MoH using CustomMoH1.mp3" -AudioFileId $AudioFile.Id
```

新しい Teams 通話保留ポリシーを作成したら、次のようにGrant-CsTeamsCallHoldPolicyを使用してユーザーに付与できます。

```PowerShell
C:\> Grant-CsTeamsCallHoldPolicy -PolicyName "CustomMoH1" -Identity user1@contoso.com
```

アップロードしたオーディオ ファイルに関する情報を取得するには、Get-CsOnlineAudioFile コマンドレットを使用します。

アップロードしたオーディオ ファイルを削除するには、Remove-CsOnlineAudioFile コマンドレットを使用します。 オーディオ ファイルを削除する前に、TeamsCallHoldPolicy でそのオーディオ ファイルを使用していないかどうかを確認します。

アップロードしたオーディオ ファイルをエクスポートするには、Export-CsOnlineAudioFile コマンドレットを使用します。

## <a name="feature-availability"></a>機能の可用性

次の表は、保留音と保留音のカスタム音楽をサポートするクライアントとデバイスの機能を示しています。 Microsoft は引き続き機能サポートを追加しているため、多くの場合、追加の可用性を確認してください。

| 機能 | デスクトップ <br> Windows/Mac OS | ブラウザー | モバイル <br> iOS | モバイル <br> Android | Teams Phone |
| :------------| :------- | :------- | :------- | :------- | :------- |
| 1:1 PSTN 通話を保留する | -保留音<br>-Custom Music on Hold | -保留音<br>-Custom Music on Hold | -保留音<br>-Custom Music on Hold | -保留音<br>-Custom Music on Hold | -保留音<br>-Custom Music on Hold |
| 1:1 Teams 通話を保留する | -保留音<br>-Custom Music on Hold | -保留音<br>-Custom Music on Hold | -保留音<br>-Custom Music on Hold | -保留音<br>-Custom Music on Hold | -保留音<br>-Custom Music on Hold |
| 1:1 PSTN 通話でコンサルティング転送を保留する |-保留音<br>-Custom Music on Hold || -保留音<br>-Custom Music on Hold | -保留音<br>-Custom Music on Hold | -保留音<br>-Custom Music on Hold |
| 1:1 Teams の通話でコンサルティング転送を保留する |-保留音<br>-Custom Music on Hold || -保留音<br>-Custom Music on Hold | -保留音<br>-Custom Music on Hold | -保留音<br>-Custom Music on Hold |

## <a name="restrictions"></a>制限

- 保留音は、商用および GCC クラウド インスタンスでのみ使用できます。

- 保留音は、ユーザーが TeamsOnly モードの場合にのみ使用できます。

- 呼び出された Teams ユーザーがLocation-Basedルーティングを有効にしている場合、保留音は呼び出し元に再生できません。

- 共有行の外観 (委任) 用に構成されたユーザーと、コール パークが使用されている場合、保留状態のカスタム 音楽は使用できません。 標準の保留音が再生されます。

- 一部のシナリオでは、保留音を再生するためにダイレクト ルーティング メディア バイパス呼び出しが非メディア バイパスに変換され、通話が終了するまで、通話はメディア以外のバイパスのままになります。

## <a name="related-topics"></a>関連項目

- [ユーザーにポリシーを割り当てる](policy-assignment-overview.md)

- [Get-CsTeamsCallingPolicy](/powershell/module/skype/get-csteamscallingpolicy)

- [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)

- [Import-CsOnlineAudioFile](/powershell/module/skype/import-csonlineaudiofile)

- [Export-CsOnlineAudioFile](/powershell/module/skype/export-csonlineaudiofile)

- [Get-CsOnlineAudioFile](/powershell/module/skype/get-csonlineaudiofile)

- [Remove-CsOnlineAudioFile](/powershell/module/skype/remove-csonlineaudiofile)

- [New-CsTeamsCallHoldPolicy](/powershell/module/skype/new-csteamscallholdpolicy)

- [Get-CsTeamsCallHoldPolicy](/powershell/module/skype/get-csteamscallholdpolicy)

- [Grant-CsTeamsCallHoldPolicy](/powershell/module/skype/grant-csteamscallholdpolicy)

- [Remove-CsTeamsCallHoldPolicy](/powershell/module/skype/remove-csteamscallholdpolicy)
