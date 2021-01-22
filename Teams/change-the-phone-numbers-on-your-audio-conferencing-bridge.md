---
title: 電話会議ブリッジで電話番号を変更する
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6403f6d1-c05a-44ab-a6e0-558000e246f4
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: 新しいサービス電話番号を会議ブリッジに割り当て、ユーザーの範囲を拡大するために必要な手順について説明します。
ms.openlocfilehash: 7f9efd4289f24b4248cddd732773d7c96e728f0c
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918753"
---
# <a name="change-the-phone-numbers-on-your-audio-conferencing-bridge"></a>電話会議ブリッジの電話番号を変更する

電話会議ライセンス **を購入すると** 、Microsoft は組織の電話会議ブリッジをホストしています。 電話会議ブリッジは、さまざまな場所からダイヤルイン電話番号を提供し、会議の開催者と参加者が電話を使って Skype for Business 会議または Microsoft Teams 会議に参加できます。
  
会議ブリッジに既に割り当てられている電話番号に加えて、他の場所から追加のサービス番号 [(電話](/microsoftteams/getting-service-phone-numbers) 会議に使用される有料電話番号と無料電話番号) を取得し、会議ブリッジに割り当てると、ユーザーの範囲を拡大できます。
  
> [!NOTE]
> 会議ブリッジの電話番号を割り当て/割り当て解除するには、電話番号が ' サービス ' 番号 *である* 必要があります。 Microsoft Teams 管理センターで音声電話番号に移動し、[番号の種類] 列を見て、その番号の種類  >  **を確認** できます。 ユーザーが無料電話番号でブリッジにダイヤルインするには、Microsoft 365 または Office 365 コミュニケーション クレジットを最初に設定する必要があります。

## <a name="steps-when-you-are-assigning-a-new-service-phone-number-to-your-conference-bridge"></a>会議ブリッジに新しいサービス電話番号を割り当てる手順

### <a name="step-1---assign-the-new-phone-number-to-your-audio-conferencing-bridge"></a>手順 1 - 新しい電話番号を電話会議ブリッジに割り当てる

![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターを使用する**

1. 左側のナビゲーション ウィンドウで、[音声電話番号 **] に**  >  **移動します**。

2. 一覧から電話番号を選び、[編集] をクリック **します**。

3. [編集]**ページの [** 割り当 **て済み**] で、ドロップダウンを展開し、[会議ブリッジ **の適用] を選択**  >  **します**。

### <a name="step-2---change-the-default-phone-number-of-your-conference-bridge-optional"></a>手順 2 - 会議ブリッジの既定の電話番号を変更する (オプション)

会議ブリッジの既定の電話番号は、会議内から発信通話が参加者または開催者によって発信された場合に使用される発信者番号を定義します。

会議ブリッジの既定の番号として設定できるのはサービス有料電話番号のみです。 **サービスの無料電話番号を** 会議ブリッジの既定の番号として設定できない。 サービス有料電話番号を割り当て、それを電話会議ブリッジの新しい既定の番号として設定する場合は、次の手順を実行します。

![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターを使用する**

1. 左側のナビゲーション ウィンドウで、[会議会議ブリッジ **]**  >  **に移動します**。

2. 既定として構成するサービス有料電話番号を強調表示します。

3. [**既定に設定**] を選択します。
 
### <a name="step-3---change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users-optional"></a>手順 3 - ユーザーの会議出席招待に含まれる既定の電話番号を変更する (オプション)

ユーザーの既定の電話番号は、会議のスケジュールを設定するときに会議の招待に含まれます。 新しいユーザーに既定の電話番号を割り当てる方法など、詳細については [、「Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) の招待に含まれる電話番号を設定する」または [「Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)の招待に含まれる電話番号を設定する」を参照してください。

![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターを使用する**

1. 左側のナビゲーション ウィンドウで、[ユーザー  ] に移動し、一覧で目的のユーザーの表示名をクリックします。

2. 電話会議の **横にある [編集**] を **クリックします**。

3. [ **有料電話番号] または** **[フリーダイヤル番号**] で、ドロップダウンから番号を選び、[適用] を **クリックします**。

変更が適用されると、次回新しい会議をスケジュールする場合、新しい既定の電話番号が開催者の会議の招待に含まれます。

### <a name="step-4---update-existing-meeting-invites-of-users-using-the-meeting-migration-service-optional"></a>手順 4 - Meeting Migration Service を使用してユーザーの既存の会議出席招待を更新する (オプション)

次の 2 つの手順では、次の手順をWindows PowerShell。
  
一部またはすべてのユーザーの会議出席招待に含まれる既定の電話番号を更新した場合は、必要に応じて、Meeting Migration Service を使用して既定の電話番号を変更する前に組織内のユーザーに送信された会議出席招待を更新できます。 詳細については [、「Meeting Migration Service (MMS) のセットアップ」を参照してください](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)。
  
- 手順 2 で既定の電話番号を変更したユーザーの Meeting Migration Service (MMS) を実行します。 これを行うには、次のコマンドを実行します。

```PowerShell
    Start-CsExMeetingMigration user@contoso.com
```

- 会議の移行の状態を表示できます。 保留中または進行中の状態で操作がない場合、すべての会議のスケジュール *が変更* されます。 

```PowerShell
    Get-CsMeetingMigrationStatus -SummaryOnly
```

## <a name="steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge"></a>会議ブリッジのサービス電話番号の割り当てを解除する場合の手順


電話会議ブリッジから電話番号の割り当てを解除すると、ユーザーは、その電話番号を使用して会議に参加できなくなります。 電話番号は変更中なので、電話番号が電話会議ブリッジから割り当て解除される前に、電話番号を既定の番号 (存在する場合) として持つ可能性があるすべてのユーザーを更新し、既存の会議出席招待を更新することが重要です。

ユーザーと会議を更新せずに電話番号が削除された場合、既存の会議の招待には、会議に参加できない電話番号が含まれている可能性があります。

最初の 3 つの手順では、次の手順をWindows PowerShell。 この方法を確認するには、[管理方法を知りたい場合] をクリック [Windows PowerShell。](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#bkPowerShell)

### <a name="step-1---update-users-who-have-the-phone-number-to-be-unassigned-as-one-of-their-default-numbers"></a>手順 1 - 既定の番号の 1 つとして割り当てられていない電話番号を持つユーザーを更新する

既定の番号として割り当て解除する番号を持つすべてのユーザーの既定の有料電話番号または無料電話番号を置き換え、会議のスケジュールを変更するプロセスを開始します。 これを行うには、次のコマンドを実行します。

```PowerShell
Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber <Number to be removed> -ToNumber <Number to be set as new default> -NumberType <"Toll" or "Toll-Free"> -RescheduleMeetings
```
 > [!IMPORTANT] 
 >Microsoft Teams 管理センターで、既定の有料または無料のユーザー数を変更できます。 ただし、これにより自動的に会議のスケジュールが変更されるわけではありません。 
 
 詳細については [、「Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) の招待に含まれる電話番号を設定する」または「Skype for Business Online の招待に含まれる電話番号 [を設定する」を参照してください](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)。

  > [!NOTE]
  > 組織の規模によっては、完了に時間がかかる場合があります。

### <a name="step-2---view-meeting-migration-status-using-windows-powershell"></a>手順 2 - 会議の移行の状態を次の手順でWindows PowerShell

保留中または進行中の状態で操作が行えな場合、すべての会議のスケジュール *が変更* されます。

```PowerShell
Get-CsMeetingMigrationStatus -SummaryOnly
```

Meeting Migration Service の詳細については、「Meeting Migration [Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)をセットアップする」を参照してください。
  
### <a name="step-3---unassign-the-old-phone-number-from-the-audio-conferencing-bridge"></a>手順 3 - 電話会議ブリッジから古い電話番号の割り当てを解除する

![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターを使用する**

1. In the left navigation, go to **Voice** > **Phone numbers**.

2. 電話番号がフリーダイヤル番号の場合は、一覧から電話番号を選び、[リリース] をクリック **します**。 電話番号が有料電話番号の場合は [、Microsoft](https://go.microsoft.com/fwlink/?linkid=2091806) サポートに問い合わせ、電話番号を割り当て解除してください。

3. 電話番号がフリーダイヤル番号の場合は、確認ウィンドウで **[** はい] をクリックします。

   > [!IMPORTANT]
   > 電話番号が電話会議ブリッジから割り当て解除された後、ユーザーは電話番号を使用して新規または既存の会議に参加できなくなりました。

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Windows PowerShell での管理方法について
<a name="bkPowerShell"> </a>

### <a name="to-verify-that-windows-powershell-is-ready-to-go"></a>準備がWindows PowerShell確認するには

 次の手順は、バージョン 3.0 Windows PowerShell実行している状態を確認します。

1. 「スタート **メニュー」と入力**  >  **Windows PowerShell。**

2. バージョンを確認するには、Windows PowerShell **ウィンドウに**_「Get-Host」_ と入力します。

3. バージョン 3.0 以降を使用していない場合は、Windows PowerShell の更新プログラムをダウンロードおよびインストールする必要があります。 バージョン [4.0 Windows Management Frameworkダウンロード](https://go.microsoft.com/fwlink/?LinkId=716845) して更新するには、Windows PowerShell 4.0 を参照してください。
メッセージが表示されたら、コンピューターを再起動します。

4. また、Skype for Business Online に接続するリモート Windows PowerShell セッションを作成できる skype for Business Online の Windows PowerShell モジュールをインストールする必要があります。 このモジュールは 64 ビットコンピューターでのみサポートされ [、Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688)の Windows PowerShell モジュールにある Microsoft ダウンロード センターからダウンロードできます。
メッセージが表示されたら、コンピューターを再起動します。

詳細については、1 つのウィンドウですべての [Microsoft 365 または Office 365](https://technet.microsoft.com/library/dn568015.aspx)サービスに接続するWindows PowerShellしてください。

### <a name="to-start-windows-powershell"></a>使用を開始Windows PowerShell

 **Windows PowerShell セッションを開始する**

1. From the **Start Menu** > **Windows PowerShell**.

2. このウィンドウ **Windows PowerShell、** 次を実行して Microsoft 365 または Office 365 に接続します。

> [!NOTE]
> Skype for Business Online Connector は現在、最新の Teams PowerShell モジュールに含まれています。
>
> 最新の [Teams PowerShell パブリック リリース](https://www.powershellgallery.com/packages/MicrosoftTeams/)をご利用の場合は、Skype for Business Online Connector をインストールする必要はありません。

>
  ```PowerShell
    Import-Module -Name MicrosoftTeams
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

> [!NOTE]
> Skype for Business Online Windows PowerShell モジュールを初めて使用するときに、 **Import-Module** コマンドを実行するだけです。
Windows PowerShell の起動の詳細については、1 つの Windows PowerShell ウィンドウで [すべての Microsoft 365 または Office 365](https://technet.microsoft.com/library/dn568015.aspx) サービスに接続する、または Windows PowerShell を使用して [Skype for Business Online](https://technet.microsoft.com/library/dn362795%28v=ocs.15%29.aspx)に接続するを参照してください。

### <a name="save-time-and-automate"></a>時間を節約して自動化する

このプロセスを自動化して時間を節約するために [、Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) または **Set-CsOnlineDialInConferencingUserDefaultNumber** コマンドレットを使用できます。

- 特定ユーザーのデフォルトの有料または無料電話番号を変更するには、[[Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688)] コマンドレットを使用します。

  - ユーザーのデフォルトの無料電話番号を変更するには、次を実行します。

  ```PowerShell
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   80045551234
  ```

- ユーザーの元の既定の電話番号または所在地に基づいて既定の有料または無料電話番号を変更するには、 **Set-CsOnlineDialInConferencingUserDefaultNumber** コマンドレットを使用します。

    > [!NOTE]
    > BridgeID を探すには、 **Get-CsOnlineDialInConferencingBridge** を使用します。

  - 既定の無料電話番号を 8005551234 に設定するには、次を実行します。

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```

  - 既定の無料電話番号が 8005551234 であるすべてのユーザーの既定の無料電話番号を 8005551239 に変更し、会議のスケジュールを自動的に変更するには、次を実行します。

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber 8005551234 -ToNumber 8005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

  - 米国内のすべてのユーザーの既定の無料電話番号を 8005551234 に設定し、会議のスケジュールを自動的に変更するには、次を実行します。

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

    > [!NOTE]
    > 上記で使用する場所は、Microsoft 365 管理センターで設定されているユーザーの連絡先情報と一致している必要があります。

## <a name="troubleshooting"></a>トラブルシューティング

**[割り当て解除] ボタンが使用できない**

番号の割り当てを解除したいが、ボタンを使用できない場合、その上にマウス ポインターを置くと、サポートに連絡するためにリダイレクトされ、次のメッセージが表示されます。"既定の番号または共有番号はブリッジから割り当て解除できません。 _専用の有料電話番号の割り当てを解除するには、サポートにお問い合わせください。_

ブリッジの詳細を取得するには、次の PowerShell を実行します。
```PowerShell
Get-CsOnlineDialInConferencingBridge -Name "Conference Bridge"
```

結果には、Identity、Name、Region などの他の情報を除いて、DefaultServiceNumber も含める必要があります。

**DefaultServiceNumber**"8005551234" の割り当てを解除する例
```PowerShell
Unregister-CsOnlineDialInConferencingServiceNumber -BridgeName "Conference Bridge" -RemoveDefaultServiceNumber 8005551234 
```

## <a name="about-windows-powershell"></a>概要Windows PowerShell

ユーザー Windows PowerShell、ユーザーの管理や許可されていない操作を管理できます。 Windows PowerShellは、1 つの管理ポイントを使用して Microsoft 365 または Office 365 と Skype for Business Online を管理し、毎日の作業を簡素化することができます。特に、複数のタスクを実行する必要がある場合に役立ちます。 Windows PowerShell の使用を開始するには、次のトピックを参照してください。

  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [Office 365 PowerShell を使用する必要がある理由](https://go.microsoft.com/fwlink/?LinkId=525041)

Windows PowerShell多くのユーザーに対して同時に設定変更を行う場合など、Microsoft 365 管理センターのみを使用する場合と同様に、速度、シンプルさ、生産性に多くの利点があります。 次のトピックでこれらの利点について説明します。

  - [Microsoft 365 または Office 365 を他のユーザーとWindows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [Windows PowerShell による Skype for Business Online の管理](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>関連項目
[電話会議ブリッジの設定を変更する](change-the-settings-for-an-audio-conferencing-bridge.md)
