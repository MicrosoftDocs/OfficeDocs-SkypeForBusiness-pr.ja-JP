---
title: 電話会議ブリッジの電話番号を変更する
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
description: 新しいサービス電話番号を会議ブリッジに割り当てて、ユーザーの利用範囲を広げるために必要な手順について説明します。
ms.openlocfilehash: 233678bd953046eed5e6425e0b1a36c5a39b1061
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780356"
---
# <a name="change-the-phone-numbers-on-your-audio-conferencing-bridge"></a>電話会議ブリッジの電話番号を変更する

**電話会議**ライセンスを購入するときに、Microsoft は組織の電話会議ブリッジをホストしています。 電話会議ブリッジは、さまざまな場所からダイヤルイン電話番号を提供します。これにより、会議の開催者と参加者は、電話を使って Skype for Business または Microsoft Teams の会議に参加することができます。
  
会議ブリッジに既に割り当てられている電話番号に加えて、他の場所から[サービス番号](/microsoftteams/getting-service-phone-numbers)(電話会議に使用されている有料または無料の電話番号) を取得して、ユーザーのために範囲を広げることができます。
  
> [!NOTE]
> 会議ブリッジの電話番号の割り当て/割り当て解除を行うには、電話番号は「*サービス*」番号でなければなりません。 番号の種類は、従来のポータルで [ > **電話番号** **] に移動**し、[番号の**種類**] 列で確認できます。 ユーザーが無料電話番号を使用してブリッジにダイヤルインするためには、Office 365 通信クレジットを最初に設定する必要があります。

## <a name="steps-when-you-are-assigning-a-new-service-phone-number-to-your-conference-bridge"></a>新しいサービス電話番号を電話会議ブリッジに割り当てるときの手順

### <a name="step-1---assign-the-new-phone-number-to-your-audio-conferencing-bridge"></a>手順 1-新しい電話番号を電話会議ブリッジに割り当てる

1. 職場のアカウントを使用して、Office 365 にサインインします。

2. **Microsoft 365 管理センター** > **管理** > **Teams & Skype** > **従来のポータル** > **ボイス** > **電話番号**に移動します。

3. リストから電話番号を選び、操作ウィンドウで [**割り当て**] をクリックします。

4. [**割り当て**] ページで [**保存**] をクリックします。

### <a name="step-2---change-the-default-phone-number-of-your-conference-bridge-optional"></a>手順 2-電話会議ブリッジの既定の電話番号を変更する (オプション)

会議ブリッジの既定の電話番号は、発信時に会議内の参加者または開催者によって発信される場合に使用される発信者番号を定義します。

電話会議ブリッジの既定の番号として設定できるのは、サービスの有料電話番号だけです。**サービスの無料電話番号を電話会議ブリッジの既定の番号として設定することはできません**。 サービスの有料電話番号を割り当てていて、電話会議ブリッジの新しい既定の番号として設定したい場合は、次の手順を実行します。

1. 職場のアカウントを使用して、Office 365 にサインインします。

2. **Microsoft 365 管理センター** > の**管理** > センター**チーム & Skype** > **会議** > **会議ブリッジ**に移動します。

3. 既定として構成するサービスの有料電話番号を強調表示します。

4. [**既定に設定**] を選択します。
 
### <a name="step-3---change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users-optional"></a>手順 3-ユーザーの会議出席依頼に含まれている既定の電話番号を変更する (オプション)

ユーザーの既定の電話番号は、会議のスケジュール時に会議出席依頼に記載されている電話番号です。 新しいユーザーに対して defaul 電話番号を割り当てる方法を含め、詳細については、「 [Microsoft Teams の招待に含まれる電話番号を設定](set-the-phone-numbers-included-on-invites-in-teams.md)する」または「 [Skype for business Online の招待に含まれる電話番号を設定](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)する」を参照してください。
  
1. 職場または学校のアカウントを使用してサインインします。

2. **Microsoft 365 管理センター** > **管理** > センターの**チーム & Skype** > **従来のポータル** > **電話会議** > **ユーザー**に移動して、リストからユーザーを選びます。

3. 操作ウィンドウで [**編集**] をクリックします。

4. [**既定の有料電話番号**] または [**既定の無料電話番号**] の下で、一覧から番号を選び、[**保存**] をクリックします。

変更が保存されると、次回新しい会議をスケジュールするときに新しい既定の電話番号が開催者の会議の出席依頼に含まれます。

### <a name="step-4---update-existing-meeting-invites-of-users-using-the-meeting-migration-service-optional"></a>手順 4-会議移行サービスを使用して、ユーザーの既存の会議出席依頼を更新する (オプション)

次の2つの手順については、Windows PowerShell を起動する必要があります。
  
一部またはすべてのユーザーの会議出席依頼に含まれている既定の電話番号を更新した場合、必要に応じて、会議移行サービスを使用して既定の電話番号を変更する前に、組織内のユーザーに送信された会議出席依頼を更新することができます。 詳細については、「[会議移行サービス (MMS) の](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)セットアップ」を参照してください。
  
- 手順2で既定の電話番号を変更したユーザーに対して、会議移行サービス (MMS) を実行します。 これを行うには、次のコマンドを実行します。

```PowerShell
    Start-CsExMeetingMigration user@contoso.com
```

- 会議の移行状態を表示することもできます。 [*保留中*] または *[進行*中] の状態で操作が行われなくなると、すべての会議がスケジュールされます。

```PowerShell
    Get-CsMeetingMigrationStatus -SummaryOnly
```

## <a name="steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge"></a>会議ブリッジのサービスの電話番号の割り当てを解除する場合の手順


会議ブリッジから電話番号の割り当てを解除すると、ユーザーはその電話番号を使って会議に参加できなくなります。 電話番号は変更されているため、電話会議ブリッジから電話番号が割り当てられていない場合は、電話番号を既定の番号として (存在する場合) 更新して、既存の会議出席依頼を更新することが重要です。

ユーザーとその会議を更新せずに電話番号が削除された場合、既存の会議出席依頼には、会議に参加するために使用できない電話番号が含まれている可能性があります。

最初の3つの手順では、Windows PowerShell を起動する必要があります。 この方法については、「 [Windows PowerShell で管理する方法](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#bkPowerShell)」を参照してください。

### <a name="step-1---update-users-who-have-the-phone-number-to-be-unassigned-as-one-of-their-default-numbers"></a>手順 1-電話番号が既定の番号の1つとして割り当てられていないユーザーを更新する

番号が既定の番号として割り当てられていないすべてのユーザーの既定の有料電話番号または無料電話番号を変更して、会議の再スケジュール処理を開始します。 これを行うには、次のコマンドを実行します。

```PowerShell
Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber <Number to be removed> -ToNumber <Number to be set as new default> -NumberType <"Toll" or "Toll-Free"> -RescheduleMeetings
```
 > [!IMPORTANT] 
 >Skype for Business 管理センターでは、既定の有料または無料のユーザー数を変更することもできます。 ただし、会議のスケジュールが自動的に再設定されることはありません。 
 
 詳細については、「 [Microsoft Teams の招待に含まれる電話番号を設定する](set-the-phone-numbers-included-on-invites-in-teams.md)」または「 [Skype for business Online の招待に含まれる電話番号を設定](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)する」を参照してください。

  > [!NOTE]
  > 組織の規模によっては、完了までに少し時間がかかる場合があります。

### <a name="step-2---view-meeting-migration-status-using-windows-powershell"></a>手順 2-Windows PowerShell を使用して会議の移行状態を表示する

[*保留中*] または *[進行*中] の状態で操作が行われなくなると、すべての会議がスケジュールされます。

```PowerShell
Get-CsMeetingMigrationStatus -SummaryOnly
```

会議移行サービスの詳細については、「[会議移行サービス (MMS) の](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)セットアップ」を参照してください。
  
### <a name="step-3---unassign-the-old-phone-number-from-the-audio-conferencing-bridge"></a>手順 3-古い電話番号を電話会議ブリッジから割り当て解除する

1. 職場または学校のアカウントを使用してサインインします。

2. **Microsoft 365 管理センター** > **管理** > **Teams & Skype** > **従来のポータル** > **ボイス** > **電話番号**に移動します。

3. 電話番号がフリーダイヤル番号の場合は、一覧から電話番号を選び、操作ウィンドウで [**割り当てを解除**] をクリックします。 電話番号が有料番号の場合は、 [Microsoft サポート](https://go.microsoft.com/fwlink/?linkid=2091806)に連絡して電話番号を割り当てていないことを確認してください。

4. 電話番号が有料 fre 番号の場合は、確認ウィンドウで [**はい]** をクリックします。

   > [!IMPORTANT]
   > 電話会議ブリッジから電話番号の割り当てを解除すると、ユーザーはその電話番号を使用して新規または既存の会議に参加できなくなります。

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Windows PowerShell での管理方法について
<a name="bkPowerShell"> </a>

### <a name="to-verify-that-windows-powershell-is-ready-to-go"></a>Windows PowerShell の準備が整っていることを確認するには

 次の手順では、Windows PowerShell バージョン3.0 以降を実行していることを確認します。

1. 「**スタートメニュー** > **Windows PowerShell**」と入力します。

2. [ **Windows PowerShell** ] ウィンドウで「 _Get Host_ 」と入力して、バージョンを確認します。

3. バージョン 3.0 以降を使用していない場合は、Windows PowerShell の更新プログラムをダウンロードおよびインストールする必要があります。 Windows PowerShell をバージョン4.0 にダウンロードして更新するには、「 [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) 」を参照してください。
メッセージが表示されたら、コンピューターを再起動します。

4. また、skype for business online に接続するリモート Windows PowerShell セッションを作成できるようにする、Skype for Business Online 用の Windows PowerShell モジュールをインストールする必要もあります。 このモジュールは、64ビットのコンピューターでのみサポートされ、 [Skype For Business Online 用の Windows PowerShell モジュール](https://go.microsoft.com/fwlink/?LinkId=294688)で Microsoft ダウンロードセンターからダウンロードできます。
メッセージが表示されたら、コンピューターを再起動します。

詳細については、「[単一の Windows PowerShell ウィンドウですべての Office 365 サービスに接続する](https://technet.microsoft.com/library/dn568015.aspx)」を参照してください。

### <a name="to-start-windows-powershell"></a>Windows PowerShell を起動するには

 **Windows PowerShell セッションを開始する**

1. From the **Start Menu** > **Windows PowerShell**.

2. **Windows PowerShell**ウィンドウで、次を実行して Microsoft 365 または Office 365 に接続します。

>
  ```PowerShell
    Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

> [!NOTE]
> Skype for Business Online Windows PowerShell モジュールを初めて使用するときに、 **Import-Module** コマンドを実行するだけです。
Windows PowerShell の起動の詳細については、「[単一の Windows powershell ウィンドウですべての Office 365 サービスに接続](https://technet.microsoft.com/library/dn568015.aspx)する」または「 [windows powershell を使用して Skype for business Online に](https://technet.microsoft.com/library/dn362795%28v=ocs.15%29.aspx)接続する」を参照してください。

### <a name="save-time-and-automate"></a>時間を節約して自動化する

このプロセスを自動化することで時間を節約するために、 [get-csonlinedialinconferencinguser](https://go.microsoft.com/fwlink/?LinkId=617688)または**set-csonlinedialinconferencinguserdefaultnumber**コマンドレットを使うことができます。

- 特定ユーザーのデフォルトの有料または無料電話番号を変更するには、[[Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688)] コマンドレットを使用します。

  - ユーザーのデフォルトの無料電話番号を変更するには、次を実行します。

  ```PowerShell
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   80045551234
  ```

- ユーザーの元の既定の電話番号または所在地に基づいて既定の有料または無料電話番号を変更するには、 **Set-CsOnlineDialInConferencingUserDefaultNumber** コマンドレットを使用します。

    > [!NOTE]
    > BridgeID を探すには、 **Get-CsOnlineDialInConferencingBridge** を使用します。

  - 既定の無料電話番号がないすべてのユーザーを8005551234に設定するには、次を実行します。

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```

  - 既定の無料電話番号として8005551234を使用しているすべてのユーザーの既定の無料電話番号を8005551239に変更し、自動的に会議のスケジュールを変更するには、次を実行します。

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber 8005551234 -ToNumber 8005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

  - 米国在住のすべてのユーザーの無料電話番号を8005551234に設定して、自動的に会議のスケジュールを再設定するには、次を実行します。

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

    > [!NOTE]
    > 上で使用されている場所は、Microsoft 365 管理センターで設定されているユーザーの連絡先情報と一致する必要があります。

## <a name="troubleshooting"></a>トラブルシューティング

**[割り当て解除] ボタンが淡色表示になっている**

番号の割り当てを解除したいが、ボタンが灰色表示になっていて、それを超えている場合は、次のメッセージが表示され_ます。 "既定または共有の番号は、ブリッジから割り当て解除することができます。́t専用の有料電話番号の割り当てを解除するには、サポートにお問い合わせください。_

ブリッジに関する詳細情報を入手するには、次の Powershell を実行します。
```PowerShell
Get-CsOnlineDialInConferencingBridge -Name "Conference Bridge"
```

その結果、Id、名前、地域などの他の情報にも、DefaultServiceNumber が含まれている必要があります。

割り当て解除する**例**DefaultServiceNumber "8005551234"
```PowerShell
Unregister-CsOnlineDialInConferencingServiceNumber -BridgeName "Conference Bridge" -RemoveDefaultServiceNumber 8005551234 
```

## <a name="about-windows-powershell"></a>Windows PowerShell について

Windows PowerShell を使用すると、ユーザーとその内容の管理を行うことができます。また、ユーザーの操作は許可されません。 Windows PowerShell を使用すると、1つの管理ポイントを使用して Office 365 および Skype for Business Online を管理することができます。特に、複数のタスクがある場合は、日常業務を簡素化できます。 Windows PowerShell の使用を開始するには、次のトピックを参照してください。

  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [Office 365 PowerShell を使用する必要がある理由](https://go.microsoft.com/fwlink/?LinkId=525041)

Windows PowerShell には、多くのユーザーについて同時に設定を変更する場合など、Microsoft 365 管理センターを使用する場合にのみ、速度、シンプルさ、生産性を高めることができます。 次のトピックでこれらの利点について説明します。

  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [Windows PowerShell による Skype for Business Online の管理](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>関連トピック
[電話会議ブリッジの設定を変更する](change-the-settings-for-an-audio-conferencing-bridge.md)
