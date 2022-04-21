---
title: 電話会議ブリッジの電話番号を変更する
ms.author: heidip
author: MicrosoftHeidi
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: 会議ブリッジに新しいサービス電話番号を割り当てて、ユーザーのカバレッジを拡大するために必要な手順について説明します。
ms.openlocfilehash: 25af462ec7e531bdbaec01ee2a8b37c43376a48e
ms.sourcegitcommit: 296fbefe0481c0b8b94aee925118474375cdf138
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2022
ms.locfileid: "65016649"
---
# <a name="change-the-phone-numbers-on-your-audio-conferencing-bridge"></a>電話会議ブリッジの電話番号を変更する

**電話会議ライセンスを** 購入すると、Microsoft は組織の電話会議ブリッジをホストします。 電話会議ブリッジは、会議の開催者や参加者が電話を使用してSkype for Business会議に参加したり、会議をMicrosoft Teamsしたりできるように、さまざまな場所のダイヤルイン電話番号を提供します。
  
会議ブリッジに既に割り当てられている電話番号に加えて、他の場所から [追加のサービス番号](./getting-service-phone-numbers.md) (電話会議に使用される有料電話番号とフリーダイヤル番号) を取得し、会議ブリッジに割り当てて、ユーザーのカバレッジを拡大することができます。
  
> [!NOTE]
> 会議ブリッジの電話番号を割り当て/割り当て解除できるようにするには、電話番号を "*サービス*" 番号にする必要があります。 番号の種類は、Microsoft Teams管理センターで **Voice** > **電話 番号** に移動し、[**数値の種類]** 列を確認することで確認できます。 ユーザーがフリーダイヤル番号でブリッジにダイヤルインするには、Microsoft 365またはOffice 365通信クレジットを最初に設定する必要があります。

## <a name="steps-when-you-are-assigning-a-new-service-phone-number-to-your-conference-bridge"></a>会議ブリッジに新しいサービス電話番号を割り当てる場合の手順

> [!NOTE]
> それ以外の場合に呼び出される場合を除き、これらの手順はすべてMicrosoft Teams管理センターで実行する必要があります。

### <a name="step-1---assign-the-new-phone-number-to-your-audio-conferencing-bridge"></a>手順 1 - 電話会議ブリッジに新しい電話番号を割り当てる

1. 左側のナビゲーション ウィンドウで、[**Voice** > **電話 numbers**] に移動します。

2. 一覧から電話番号を選択し、[編集] をクリック **します**。

3. **[編集]** ページの [**割り当て対象**] でドロップダウンを展開し、**Conference** **bridgeApply** >  を選択します。

### <a name="step-2---change-the-default-phone-number-of-your-conference-bridge-optional"></a>手順 2 - 会議ブリッジの既定の電話番号を変更する (省略可能)

会議ブリッジの既定の電話番号は、参加者または開催者が会議内から発信通話を発信するときに使用される発信者番号を定義します。

会議ブリッジの既定の番号として設定できるのは、サービス料金番号のみです。 **サービスのフリーダイヤル番号を会議ブリッジの既定の番号として設定することはできません**。 サービスの有料電話番号を割り当て、それを電話会議ブリッジの新しい既定の番号として設定する場合は、次の手順を実行します。

1. 左側のナビゲーション ウィンドウで、**MeetingsConference** >  ブリッジに移動します。

2. 既定として構成するサービスの有料電話番号を強調表示します。

3. [**既定に設定**] を選択します。

### <a name="step-3---change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users-optional"></a>手順 3 - ユーザーの会議出席依頼に含まれる既定の電話番号を変更する (省略可能)

「[Microsoft Teamsの招待に含まれる電話番号を設定する](set-the-phone-numbers-included-on-invites-in-teams.md)」を参照してください。

> [!NOTE]
> *TeamsAudioconferencingpolicy* に電話番号を追加し、ポリシーをユーザーに割り当てることで電話番号を設定することもできます。 ポリシーに追加された有料電話番号とフリーダイヤル電話番号は、電話会議設定ウィンドウでユーザーに対して個別に設定された電話番号よりも優先されます。 *Teamsaudioconferencingpolicy* に電話番号が追加されていない場合は、電話会議の設定ウィンドウでユーザーに個別に設定された電話番号が会議出席依頼Microsoft Teamsに表示されます。 [有料電話番号とフリーダイヤル番号の電話会議ポリシー設定](audio-conferencing-toll-free-numbers-policy.md) の詳細については、以下をご覧ください。

### <a name="step-4---update-existing-meeting-invites-of-users-using-the-meeting-migration-service-optional"></a>手順 4 - Meeting Migration Service を使用してユーザーの既存の会議出席依頼を更新する (省略可能)

次の 2 つの手順では、Windows PowerShellを開始する必要があります。
  
一部またはすべてのユーザーの会議出席依頼に含まれる既定の電話番号を更新した場合は、会議移行サービスを使用して既定の電話番号を変更する前に、組織のユーザーに既に送信されている会議出席依頼を更新することもできます。 詳細については、「 [会議移行サービス (MMS) の設定](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)」を参照してください。
  
- 手順 2. で既定の電話番号を変更したユーザーに対して会議移行サービス (MMS) を実行します。 これを行うには、次のコマンドを実行します。

```PowerShell
    Start-CsExMeetingMigration user@contoso.com
```

- 会議の移行状態を表示することもできます。 *保留中* または *進行中* の状態の操作がない場合、すべての会議は再スケジュールされます。

```PowerShell
    Get-CsMeetingMigrationStatus -SummaryOnly
```

## <a name="steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge"></a>会議ブリッジのサービス電話番号の割り当てを解除するときの手順

会議ブリッジから電話番号の割り当てを解除すると、ユーザーはその電話番号を使用して会議に参加できなくなります。 電話番号は変更されているため、電話番号を既定の番号 (存在する場合) として持つことができるすべてのユーザーを更新し、電話会議ブリッジから電話番号が割り当てられていない前に既存の会議出席依頼を更新することが重要です。

ユーザーとその会議を更新せずに電話番号を削除した場合、既存の会議の招待には、会議に参加できない電話番号が含まれている可能性があります。

最初の 3 つの手順では、Windows PowerShellを開始する必要があります。 これを行う方法を確認するには、[[Windows PowerShellで管理する方法を知りたい場合](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#about-windows-powershell)は] をクリックします。

### <a name="step-1---update-users-who-have-the-phone-number-to-be-unassigned-as-one-of-their-default-numbers"></a>手順 1 - 電話番号を割り当てられていないユーザーを既定の番号の 1 つとして更新する

既定の電話番号として割り当てられていない番号を持つすべてのユーザーの既定の有料電話番号またはフリーダイヤル番号を置き換え、会議のスケジュールを変更するプロセスを開始します。 これを行うには、次のコマンドを実行します。

```PowerShell
Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber <Number to be removed> -ToNumber <Number to be set as new default> -NumberType <"Toll" or "Toll-Free"> -RescheduleMeetings
```

 > [!IMPORTANT]
 >Microsoft Teams管理センターで、既定の有料またはフリーダイヤルのユーザー数を変更することもできます。 ただし、これにより、会議のスケジュールが自動的に変更されることはありません。

 詳細については、「Microsoft Teamsの[招待に含まれる電話番号を設定](set-the-phone-numbers-included-on-invites-in-teams.md)する」または「[Skype for Business Online の招待に含まれる電話番号を設定する」を](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)参照してください。

  > [!NOTE]
  > 組織の規模によっては、完了に時間がかかる場合があります。

### <a name="step-2---view-meeting-migration-status-using-windows-powershell"></a>手順 2 - Windows PowerShellを使用して会議の移行状態を表示する

*保留中* または *進行中* の状態の操作がない場合、すべての会議は再スケジュールされます。

```PowerShell
Get-CsMeetingMigrationStatus -SummaryOnly
```

会議移行サービスの詳細については、「 [会議移行サービス (MMS) のセットアップ](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)」を参照してください。
  
### <a name="step-3---unassign-the-old-phone-number-from-the-audio-conferencing-bridge"></a>手順 3 - 電話会議ブリッジから古い電話番号の割り当てを解除する

Unregister-CsOnlineDialInConferencingServiceNumber コマンドレットを使用して、会議ブリッジから有料または無料の電話番号の登録を解除する

```PowerShell
Unregister-CsOnlineDialInConferencingServiceNumber -identity "toll number to be removed" -bridgeId "Conference Bridge ID"
Unregister-CsOnlineDialInConferencingServiceNumber -identity "toll free number to be removed" -bridgeId "Conference Bridge ID"
```

注: Conference Bridge ID を見つけるには、次の PowerShell を実行します。Get-CsOnlineDialInConferencingBridge。

   > [!IMPORTANT]
   > 電話会議ブリッジから電話番号が割り当てられていないと、ユーザーが新規または既存の会議に参加できなくなります。

### <a name="save-time-and-automate"></a>時間を節約し、自動化する

このプロセスを自動化することで時間を節約するために、 [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) または **Set-CsOnlineDialInConferencingUserDefaultNumber コマンドレットを** 使用できます。

- 特定ユーザーのデフォルトの有料または無料電話番号を変更するには、[[Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser)] コマンドレットを使用します。

  - ユーザーのデフォルトの無料電話番号を変更するには、次を実行します。

  ```PowerShell
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   80045551234
  ```

- ユーザーの元の既定の電話番号または所在地に基づいて既定の有料または無料電話番号を変更するには、 **Set-CsOnlineDialInConferencingUserDefaultNumber** コマンドレットを使用します。

    > [!NOTE]
    > BridgeID を探すには、 **Get-CsOnlineDialInConferencingBridge** を使用します。

  - 1 つを含まないすべてのユーザーの既定のフリーダイヤル番号を8005551234に設定するには、次のコマンドを実行します。

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```

  - 既定のフリーダイヤル番号として8005551234を持つすべてのユーザーの既定のフリーダイヤル番号を8005551239に変更し、会議のスケジュールを自動的に変更するには、次のコマンドを実行します。

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber 8005551234 -ToNumber 8005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

  - 米国内のすべてのユーザーの既定のフリーダイヤル番号を8005551234に設定し、会議のスケジュールを自動的に変更するには、次のコマンドを実行します。

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

    > [!NOTE]
    > 上記で使用する場所は、Microsoft 365 管理センターに設定されているユーザーの連絡先情報と一致している必要があります。

## <a name="troubleshooting"></a>トラブルシューティング

### <a name="the-unassign-button-isnt-available"></a>[割り当て解除] ボタンは使用できません

番号の割り当てを解除するが、ボタンを使用できず、マウス ポインターをポイントすると、次のメッセージをサポートに問い合わせるためにリダイレクトされます。"既定値または共有番号はブリッジから割り当て解除できません。 専用の有料電話番号の割り当てを解除するには、サポートにお問い合わせください。."

ブリッジの詳細を取得するには、次の Powershell を実行します。

```PowerShell
Get-CsOnlineDialInConferencingBridge -Name "Conference Bridge"
```

結果には、Identity、Name、Region などの他の情報を除き、DefaultServiceNumber も含まれている必要があります。

**たとえば**、割り当てを解除するには、DefaultServiceNumber "8005551234"

```PowerShell
Unregister-CsOnlineDialInConferencingServiceNumber -BridgeName "Conference Bridge" -RemoveDefaultServiceNumber 8005551234 
```

## <a name="about-windows-powershell"></a>Windows PowerShellについて

Windows PowerShellを使用すると、ユーザーとそのユーザーの操作を管理できます。 Windows PowerShellは、Microsoft 365やOffice 365を管理し、オンラインをSkype for Businessするのに役立ちます。これは、特に複数のタスクがある場合に、毎日の作業を簡素化できる単一の管理ポイントを使用します。 Windows PowerShell の使用を開始するには、次のトピックを参照してください。

- [Windows PowerShell と Skype for Business Online の概要](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

- [Office 365 PowerShell を使用する必要がある理由](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

Windows PowerShellには、多くのユーザーに対して一度に設定を変更する場合など、Microsoft 365 管理センターのみを使用するよりも、速度、シンプルさ、生産性に多くの利点があります。 次のトピックでこれらの利点について説明します。

- [Windows PowerShell で Microsoft 365 または Office 365 を管理するための最善の方法](/previous-versions//dn568025(v=technet.10))

- [Windows PowerShell による Skype for Business Online の管理](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

- [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a>関連項目

[電話会議ブリッジの設定を変更する](change-the-settings-for-an-audio-conferencing-bridge.md)
