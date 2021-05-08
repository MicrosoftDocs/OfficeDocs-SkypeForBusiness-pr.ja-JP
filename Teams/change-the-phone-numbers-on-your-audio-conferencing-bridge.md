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
description: 新しいサービス電話番号を会議ブリッジに割り当て、ユーザーの対象範囲を拡大するために必要な手順について説明します。
ms.openlocfilehash: f477c583db36e6dee514a84f32de202361d01c11
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102663"
---
# <a name="change-the-phone-numbers-on-your-audio-conferencing-bridge"></a>電話会議ブリッジの電話番号を変更する

電話会議ライセンス **を購入すると** 、Microsoft は組織の電話会議ブリッジをホストしています。 電話会議ブリッジでは、会議の開催者と参加者が電話を使って Skype for Business または Microsoft Teams 会議に参加するために、さまざまな場所からダイヤルイン電話番号を提供します。
  
会議ブリッジに既に割り当てられている電話番号に加えて、他の場所から追加のサービス番号 [(電話](./getting-service-phone-numbers.md) 会議に使用される有料電話番号と無料電話番号) を取得し、会議ブリッジに割り当て、ユーザーの範囲を拡大できます。
  
> [!NOTE]
> 会議ブリッジの電話番号を割り当て/割り当て解除するには、電話番号がサービス ' 番号 *である* 必要があります。 番号の種類を確認するには、Microsoft Teams 管理センターで[Voice 電話 number] に移動し、[数値の種類] 列  >  **を確認** します。 Microsoft 365またはOffice 365通信クレジットは、ユーザーが無料電話番号でブリッジにダイヤルインするために、最初に設定する必要があります。

## <a name="steps-when-you-are-assigning-a-new-service-phone-number-to-your-conference-bridge"></a>会議ブリッジに新しいサービス電話番号を割り当てる手順

### <a name="step-1---assign-the-new-phone-number-to-your-audio-conferencing-bridge"></a>手順 1 - 新しい電話番号を電話会議ブリッジに割り当てる

![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターを使用する**

1. 左側のナビゲーション ウィンドウで、[Voice電話  >  **に移動します**。

2. 一覧から電話番号を選択し、[編集] を **クリックします**。

3. [編集]**ページの**[割り当て **]** でドロップダウンを展開し、[会議ブリッジの適用 **] を**  >  **選択します**。

### <a name="step-2---change-the-default-phone-number-of-your-conference-bridge-optional"></a>手順 2 - 会議ブリッジの既定の電話番号を変更する (省略可能)

会議ブリッジの既定の電話番号は、会議内から参加者または開催者によって発信通話が行われるときに使用される発信者 ID を定義します。

会議ブリッジの既定の番号として設定できるのは、サービスの有料電話番号のみです。 **サービスの無料電話番号を会議ブリッジの既定の番号として設定できない**。 サービスの有料電話番号を割り当て、それを電話会議ブリッジの新しい既定の番号として設定する場合は、次の手順に従います。

![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターを使用する**

1. 左側のナビゲーション ウィンドウで、[会議会議ブリッジ]  >  **に移動します**。

2. 既定として構成するサービスの有料電話番号を強調表示します。

3. [**既定に設定**] を選択します。
 
### <a name="step-3---change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users-optional"></a>手順 3 - ユーザーの会議出席招待に含まれる既定の電話番号を変更する (省略可能)

ユーザーの既定の電話番号は、会議のスケジュールを設定するときに会議の招待に含まれる電話番号です。 新しいユーザーに既定の電話番号を割り当てる方法など、詳細については[、「Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md)の招待に含まれる電話番号を設定する」または「Skype for Business Online の招待に含まれる電話番号を設定する[」を参照](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)してください。

![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターを使用する**

1. 左側のナビゲーション ウィンドウで、[ユーザー] に **移動** し、一覧で目的のユーザーの [表示名] をクリックします。

2. [電話会議 **] の横にある [** 編集] を **クリックします**。

3. [ **有料電話番号] または** **[無料電話番号**] で、ドロップダウンから番号を選択し、[適用] を **クリックします**。

変更が適用されると、次回新しい会議をスケジュールする場合、新しい既定の電話番号が開催者の会議の招待に含まれます。

### <a name="step-4---update-existing-meeting-invites-of-users-using-the-meeting-migration-service-optional"></a>手順 4 - Meeting Migration Service を使用してユーザーの既存の会議出席招待を更新する (省略可能)

次の 2 つの手順では、次の手順を開始Windows PowerShell。
  
一部またはすべてのユーザーの会議出席招待に含まれる既定の電話番号を更新した場合は、必要に応じて、Meeting Migration Service を使用して既定の電話番号が変更される前に組織内のユーザーに送信された会議出席許可を更新できます。 詳細については [、「Meeting Migration Service (MMS) の設定」を参照してください](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)。
  
- 手順 2 で既定の電話番号を変更したユーザーに対して、Meeting Migration Service (MMS) を実行します。 これを行うには、次のコマンドを実行します。

```PowerShell
    Start-CsExMeetingMigration user@contoso.com
```

- 会議の移行の状態を表示できます。 [保留中] または [進行中] 状態の操作がない場合は、すべての *会議のスケジュール**が変更* されます。

```PowerShell
    Get-CsMeetingMigrationStatus -SummaryOnly
```

## <a name="steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge"></a>会議ブリッジのサービス電話番号の割り当てを解除する手順


会議ブリッジから電話番号の割り当てを解除すると、ユーザーは、その電話番号を使用して会議に参加できなくなります。 電話番号は変更中なので、電話番号が既定の番号 (存在する場合) である可能性があるすべてのユーザーを更新し、電話番号が電話会議ブリッジから割り当て解除される前に、既存の会議出席招待を更新することが重要です。

ユーザーと会議を更新せずに電話番号が削除された場合、既存の会議出席許可には、会議に参加するために機能しない電話番号が含まれている可能性があります。

最初の 3 つの手順では、最初の手順を開始Windows PowerShell。 これを行う方法を確認するには、[管理方法を知りたい] をクリック[Windows PowerShell。](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#about-windows-powershell)

### <a name="step-1---update-users-who-have-the-phone-number-to-be-unassigned-as-one-of-their-default-numbers"></a>手順 1 - 既定の番号の 1 つとして割り当て解除する電話番号を持つユーザーを更新する

既定の番号として割り当てられていない番号を持つすべてのユーザーの既定の有料電話番号または無料電話番号を置き換え、会議のスケジュールを変更するプロセスを開始します。 これを行うには、次のコマンドを実行します。

```PowerShell
Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber <Number to be removed> -ToNumber <Number to be set as new default> -NumberType <"Toll" or "Toll-Free"> -RescheduleMeetings
```
 > [!IMPORTANT] 
 >また、管理センターで既定の有料または無料のユーザー数Microsoft Teams変更できます。 ただし、会議のスケジュールが自動的に変更されるわけではありません。 
 
 詳細については、「Microsoft Teams[](set-the-phone-numbers-included-on-invites-in-teams.md)の招待に含まれる電話番号を設定する」または「Microsoft Teams Online の招待に含まれる電話番号を[設定する」をSkype for Businessしてください](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)。

  > [!NOTE]
  > 組織の規模によっては、完了に時間がかかる場合があります。

### <a name="step-2---view-meeting-migration-status-using-windows-powershell"></a>手順 2 - 会議の移行の状態を表示するには、Windows PowerShell

[保留中] または [進行中] 状態の操作がない場合は、すべての会議 *のスケジュールが変更* されます。

```PowerShell
Get-CsMeetingMigrationStatus -SummaryOnly
```

Meeting Migration Service の詳細については、「Meeting [Migration Service (MMS) の設定」を参照してください](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)。
  
### <a name="step-3---unassign-the-old-phone-number-from-the-audio-conferencing-bridge"></a>手順 3 - 電話会議ブリッジから古い電話番号の割り当てを解除する

![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターを使用する**

1. In the left navigation, go to **Voice** > **Phone numbers**.

2. 電話番号が無料電話番号の場合は、一覧から電話番号を選択し、[リリース] をクリック **します**。 電話番号が有料電話番号の場合は [、Microsoft](/microsoft-365/admin/contact-support-for-business-products) サポートに問い合わせ、電話番号を割り当て解除してください。

3. 電話番号が無料電話番号の場合は、確認ウィンドウで **[は** い] をクリックします。

   > [!IMPORTANT]
   > 電話番号が電話会議ブリッジから割り当て解除された後は、ユーザーが新規または既存の会議に参加するために電話番号を使用できなくなりました。

### <a name="save-time-and-automate"></a>時間を節約して自動化する

このプロセスを自動化して時間を節約するには [、Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) コマンドレットまたは **Set-CsOnlineDialInConferencingUserDefaultNumber** コマンドレットを使用できます。

- 特定ユーザーのデフォルトの有料または無料電話番号を変更するには、[[Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser)] コマンドレットを使用します。

  - ユーザーのデフォルトの無料電話番号を変更するには、次を実行します。

  ```PowerShell
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   80045551234
  ```

- ユーザーの元の既定の電話番号または所在地に基づいて既定の有料または無料電話番号を変更するには、 **Set-CsOnlineDialInConferencingUserDefaultNumber** コマンドレットを使用します。

    > [!NOTE]
    > BridgeID を探すには、 **Get-CsOnlineDialInConferencingBridge** を使用します。

  - 1 人を含めずにすべてのユーザーの既定の無料電話番号を 8005551234 に設定するには、次のコマンドを実行します。

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```

  - 既定のフリーダイヤル番号として 8005551234 を持つすべてのユーザーの既定のフリーダイヤル番号を 8005551239 に変更し、会議のスケジュールを自動的に変更するには、次のコマンドを実行します。

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber 8005551234 -ToNumber 8005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

  - 米国内のすべてのユーザーの既定の無料電話番号を 8005551234 に設定し、会議のスケジュールを自動的に変更するには、次のコマンドを実行します。

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

    > [!NOTE]
    > 上記で使用する場所は、管理センターで設定されているユーザーの連絡先情報と一Microsoft 365必要があります。

## <a name="troubleshooting"></a>トラブルシューティング

**[割り当て解除] ボタンを使用できない**

番号の割り当てを解除するが、ボタンを使用できない場合、その上にマウス ポインターを置くと、サポートに問い合わせにリダイレクトされ、"既定または共有の番号はブリッジから割り当て解除できません。 _専用の有料電話番号の割り当てを解除するには、サポートにお問い合わせください。_

ブリッジの詳細を取得するには、次の Powershell を実行します。
```PowerShell
Get-CsOnlineDialInConferencingBridge -Name "Conference Bridge"
```

結果には、Identity、Name、Region などの他の情報を除き、DefaultServiceNumber も含める必要があります。

**割** り当てを解除する例、DefaultServiceNumber "8005551234"
```PowerShell
Unregister-CsOnlineDialInConferencingServiceNumber -BridgeName "Conference Bridge" -RemoveDefaultServiceNumber 8005551234 
```

## <a name="about-windows-powershell"></a>概要 Windows PowerShell

このWindows PowerShell、ユーザーの管理、ユーザーの操作、または許可されていない操作を管理できます。 Windows PowerShell 1 つの管理ポイントを使用して Microsoft 365 または Office 365 および Skype for Business Online を管理し、毎日の作業を簡略化できます。特に、複数のタスクを実行する必要がある場合に役立ちます。 Windows PowerShell の使用を開始するには、次のトピックを参照してください。

  - [Windows PowerShell と Skype for Business Online の概要](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [Office 365 PowerShell を使用する必要がある理由](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

Windows PowerShell多くのユーザーに対して一度に設定を変更する場合など、Microsoft 365 管理センターを使用する場合に限って、速度、シンプルさ、生産性に多くの利点があります。 次のトピックでこれらの利点について説明します。

  - [アプリを使用してMicrosoft 365またはOffice 365を管理Windows PowerShell](/previous-versions//dn568025(v=technet.10))

  - [Windows PowerShell による Skype for Business Online の管理](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a>関連トピック
[電話会議ブリッジの設定を変更する](change-the-settings-for-an-audio-conferencing-bridge.md)