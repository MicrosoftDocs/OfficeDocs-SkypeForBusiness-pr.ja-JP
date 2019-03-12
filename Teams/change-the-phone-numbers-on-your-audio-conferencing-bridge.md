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
- Teams_ITAdmin_Help
- M365-voice
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 電話会議ライセンスをご購入いただく場合、Microsoft はお客様の組織の電話会議ブリッジ をホストします。電話会議ブリッジではさまざまな場所からダイヤルイン電話番号を受け取るため、会議の開催者や参加者はそれらの番号を使用して電話で Skype for Business 会議または Microsoft Teams 会議に参加できます。
ms.openlocfilehash: bc26fc64f4b95c1a469908251781c4951c7d0a84
ms.sourcegitcommit: 70d4d02a3cc894f2f197aeea459ac079cde63877
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/11/2019
ms.locfileid: "30542105"
---
# <a name="change-the-phone-numbers-on-your-audio-conferencing-bridge"></a>電話会議ブリッジの電話番号を変更する

**オーディオ会議**のライセンスを購入すると、Microsoft は、組織の場合は、オーディオ会議ブリッジをホストしています。 オーディオ会議用ブリッジは、ミーティングの開催者を別の場所からのダイヤルに電話番号と参加者を使用して Skype に電話を使用するビジネスまたはマイクロソフトのチームの会議に参加します。
  
[その他のサービス番号を取得](/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers)することをだけでなく、会議用ブリッジに既に割り当てられている電話番号、(有料電話番号とフリー ダイヤルの番号を電話会議に使用される) から他の場所、および会議にそれらをブリッジすることができますしの割り当てユーザーのカバレッジを展開します。
  
> [!NOTE]
> 会議用ブリッジ用の電話番号の割り当て/割り当て解除できるようにするには、電話番号は、'*サービス*' の番号をする必要があります。 **音声**に移動することが番号の種類を参照してください > 従来の**番号の種類**] 列で検索し、ポータル内の**電話番号**です。 Office 365 のコミュニケーション クレジットは、ユーザーが無料電話番号のブリッジにダイヤルインできるように、最初にセットアップする必要があります。

## <a name="steps-when-you-are-assigning-a-new-service-phone-number-to-your-conference-bridge"></a>新しいサービス用電話番号を会議ブリッジに割り当てるときの手順

### <a name="step-1---assign-the-new-phone-number-to-your-audio-conferencing-bridge"></a>手順 1 - 新しい電話番号を電話会議ブリッジに割り当てる

1. 自分の職場のアカウントで Office 365 にサインインします。

2. **Office 365 管理センター**を参照して > **管理センター** > **チーム & Skype** > **レガシー ポータル** > **音声** > **の電話番号**です。

3. リストから電話番号を選択し、[操作] ウィンドウで [ **割り当て**] をクリックします。

4. [ **割り当て**] ページで、[ **保存**] をクリックします。

### <a name="step-2---change-the-default-phone-number-of-your-conference-bridge-optional"></a>ステップ 2 - 変更、既定の電話番号 (省略可能)、会議ブリッジ

テレビ会議サービスの既定の電話番号は、発信呼び出しが参加者または開催者から会議内で配置する場合に使用される呼び出し元 ID を定義します。

サービスの有料電話番号だけは、会議用ブリッジは、既定の番号として設定できます。**サービスのフリー ダイヤル番号は、会議用ブリッジ数の既定値として設定できません**。 サービスの有料電話番号を割り当てると、新しい既定の番号、電話会議ブリッジとして設定するには、次の手順に従います。

1. 自分の職場のアカウントで Office 365 にサインインします。

2. **Office 365 管理センター**を参照して > **管理センター** > **チーム & Skype** > **会議** > **会議ブリッジ**です。

3. サービスの有料電話番号が既定値として構成することを強調表示します。

4. [**既定に設定**] を選択します。
 
### <a name="step-3---change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users-optional"></a>ステップ 3 - 会議に含まれる既定の電話番号の変更が (省略可能) ユーザーの招待します。

ユーザーの既定の電話番号は、会議をスケジュールするとき、会議に含まれるものへの招待します。 新規ユーザーの既定の電話番号を割り当てる方法を含む詳細について[に含まれている番号は、マイクロソフトのチームで招待の電話を設定](set-the-phone-numbers-included-on-invites-in-teams.md)したり、[オンライン ビジネスの Skype で招待に含まれている番号の電話の設定](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)を参照してください。
  
1. 職場または学校のアカウントを使用して、Office 365 にサインインします。

2. **Office 365 管理センター**を参照して > **管理センター** > **チーム & Skype** > **レガシー ポータル** > **電話会議** > **ユーザー**、および、リスト上のユーザーを選択します。

3. [操作] ウィンドウで [ **編集**] をクリックします。

4. [ **既定の有料電話番号**] または [ **既定のフリーダイヤル番号**] の下で、リストから番号を選択して [ **保存**] をクリックします。

変更が保存されると、次回新しい会議をスケジュールするときに新しい既定の電話番号が開催者の会議の出席依頼に記載されます。

### <a name="step-4---update-existing-meeting-invites-of-users-using-the-meeting-migration-service-optional"></a>手順 4 - 既存の会議の会議の移行サービス (オプション) を使用してユーザーの招待を更新

次の 2 つの手順では、Windows PowerShell を開始することが必要になります。
  
既定電話番号、およびこの会議の一部またはすべてのユーザーへの招待を更新する場合を使用して、既定の電話番号が変更された前に、組織内のユーザーに既に送信された会議の招待を必要に応じて更新できます、会議の移行サービスです。 詳細については、「[Meeting Migration Service (MMS) のセットアップ](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)」をご覧ください。
  
- 手順 2 で既定の電話番号を変更したユーザーに対して、Meeting Migration Service (MMS) を実行します。これを実行するには、次のコマンドを実行します。

```
    Start-CsExMeetingMigration user@contoso.com
```

- 会議の移行の状態を確認することもできます。[ *保留*  ] または [ *進行中*  ] の状態で操作が行われなくなると、すべての会議のスケジュールが変更されることがあります。

```
    Get-CsMeetingMigrationStatus -SummaryOnly
```

## <a name="steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge"></a>会議ブリッジのサービス用電話番号の割り当てを解除するときの手順


電話番号を会議ブリッジから割り当て解除すると、ユーザーは今後その電話番号を使用して会議に参加することができなくなります。 電話番号を変更するための可能性があります (存在する場合) の既定の番号として電話番号を持っているすべてのユーザーを更新して、既存の電話番号は、オーディオ会議ブリッジから割り当てられた前に会議の招待を更新するのには重要です。

ユーザーとの会議を更新せず、電話番号を削除する場合、既存の会議の招待が含まれますがミーティングに参加するために動作しない電話番号には。

最初の 3 つの手順では、Windows PowerShell を開始することが必要になります。 これを行う方法を表示するをクリックして[Windows PowerShell を使用して管理する方法を知りたいのですか?](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#bkPowerShell)

### <a name="step-1---update-users-who-have-the-phone-number-to-be-unassigned-as-one-of-their-default-numbers"></a>ステップ 1 - として、既定の番号のいずれかの割り当てを解除する電話番号を持つユーザーを更新

既定の有料または無料電話番号が既定値として割り当てを解除して、会議の予定変更のプロセスを開始する番号を持つすべてのユーザーを交換してください。 これを実行するには、次のコマンドを実行します。

```
Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber <Number to be removed> -ToNumber <Number to be set as new default> -NumberType <"Toll" or "Toll-Free"> -RescheduleMeetings
```
 > [!IMPORTANT] 
 >Skype for Business 管理センターでユーザーの既定の有料または無料電話番号を変更することもできます。ただし、これにより自動的に会議のスケジュールが変更されることはありません 。 
 
 詳細については、[携帯電話に含まれている番号は、マイクロソフトのチームで招待を設定](set-the-phone-numbers-included-on-invites-in-teams.md)したり、[オンライン ビジネスの Skype で招待に含まれている番号の電話の設定](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)を参照してください。

  > [!NOTE]
  > 所属する組織の規模に応じて、完了するまで時間がかかる場合があります。

### <a name="step-2---view-meeting-migration-status-using-windows-powershell"></a>手順 2 - Windows PowerShell を使用して会議の移行状態を表示する

*保留中*または*実行中*の状態にする工程がないと、すべての会議を再スケジュールされます。

```
Get-CsMeetingMigrationStatus -SummaryOnly
```

Meeting Migration Service の詳細については、「 [Meeting Migration Service (MMS) のセットアップ](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)」をご覧ください。
  
### <a name="step-3---unassign-the-old-phone-number-from-the-audio-conferencing-bridge"></a>手順 3 - 古い電話番号を電話会議ブリッジから割り当て解除する

1. 職場または学校のアカウントを使用して、Office 365 にサインインします。

2. **Office 365 管理センター**を参照して > **管理センター** > **チーム & Skype** > **レガシー ポータル** > **音声** > **の電話番号**です。

3. リストから電話番号を選択し、[操作] ウィンドウで [ **割り当てを解除**] をクリックします。

4. 確認ウィンドウで、[ **はい**] をクリックします。

   > [!IMPORTANT]
   > 電話会議ブリッジから電話番号の割り当てを解除すると、ユーザーはその電話番号を使用して新規または既存の会議に参加できなくなります。

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Windows PowerShell で管理する方法
<a name="bkPowerShell"> </a>

### <a name="to-verify-that-windows-powershell-is-ready-to-go"></a>Windows PowerShell が使用できる状態かを確認する場合

 次の手順では、3.0 またはそれ以降のバージョンの Windows PowerShell が実行していることを確認します。

1. [**スタート メニュー**]  >  [**Windows PowerShell**] と入力します。

2. **Windows PowerShell** のウィンドウで _Get-Host_ と入力し、バージョンを確認します。

3. バージョン 3.0 以降を使用していない場合は、Windows PowerShell の更新プログラムをダウンロードおよびインストールする必要があります。Windows PowerShell をダウンロードして、バージョン 4.0 に更新するには、「[Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845)」を参照してください。メッセージが表示されたら、コンピューターを再起動します。

4. また、Skype のビジネス オンライン ビジネス オンラインの Skype に接続するリモートの Windows PowerShell セッションを作成することを可能にするため Windows PowerShell モジュールをインストールする必要があります。 このモジュールでは、64 ビット コンピューターでのみサポートされ、[オンライン ビジネスの Skype のモジュールを Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=294688)に Microsoft ダウンロード センターからダウンロードすることができます。
メッセージが表示されたら、コンピューターを再起動します。

詳細については、「[単一の Windows PowerShell ウィンドウですべての Office 365 サービスに接続する](https://technet.microsoft.com/library/dn568015.aspx)」を参照してください。

### <a name="to-start-windows-powershell"></a>Windows PowerShell を開始する場合

 **Windows PowerShell セッションを開始する**

1. From the **Start Menu** > **Windows PowerShell**.

2. [ **Windows PowerShell**] ウィンドウで、次を実行して、Office 365 の組織に接続します。

>
  ```
    Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

> [!NOTE]
> Skype for Business Online Windows PowerShell モジュールを初めて使用するときに、 **Import-Module** コマンドを実行するだけです。
Windows PowerShell を開始する方法の詳細を設定する場合は、 [1 つの Windows PowerShell のウィンドウ内のすべての Office 365 サービスに接続する](https://technet.microsoft.com/library/dn568015.aspx)か、 [Windows PowerShell を使用して、オンライン ビジネスの Skype への接続](https://technet.microsoft.com/library/dn362795%28v=ocs.15%29.aspx)を参照してください。

### <a name="save-time-and-automate"></a>自動化して時間を節約

このプロセスを自動化することにより時間を節約するには、[セット CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688)または**セット CsOnlineDialInConferencingUserDefaultNumber**コマンドレットを使用できます。

- 特定ユーザーのデフォルトの有料または無料電話番号を変更するには、[[Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688)] コマンドレットを使用します。

  - ユーザーのデフォルトの無料電話番号を変更するには、次を実行します。

  ```
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   80045551234
  ```

- ユーザーの元の既定の電話番号または所在地に基づいて既定の有料または無料電話番号を変更するには、 **Set-CsOnlineDialInConferencingUserDefaultNumber** コマンドレットを使用します。

    > [!NOTE]
    > BridgeID を探すには、 **Get-CsOnlineDialInConferencingBridge** を使用します。

  - デフォルトの無料電話番号がないユーザー全員のデフォルト無料電話番号を 8005551234 に設定するには、次を実行します。

  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```

  - デフォルトの無料電話番号が 8005551234 のユーザー全員のデフォルト無料電話番号を 8005551239 に変更し、会議のスケジュールを自動的に変更するには、次を実行します。

  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber 8005551234 -ToNumber 8005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

  - 所在地が米国内のユーザー全員のデフォルト無料電話番号を 8005551234 に設定し、会議のスケジュールを自動的に変更するには、次を実行します。

  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

    > [!NOTE]
    > 上記で使用される場所は、Office 365 管理センターに設定されているユーザーの連絡先情報と一致する必要があります。

## <a name="troubleshooting"></a>トラブルシューティング

**割り当てを解除] ボタンは、淡色**

番号の割り当てを解除するが、ボタンは、淡色と次のメッセージ"既定のブリッジから割り当てを解除する共有番号 can´t、_でサポートに連絡する場合しているときに上に hoovering、リダイレクトされます。専用の有料電話番号の割り当てを解除するのにはサポートに連絡してください。_」です。

繰り下げについての詳しい情報を入手するには、次の Powershell を実行します。
```
Get-CsOnlineDialInConferencingBridge -Name "Conference Bridge"
```

結果、Id、名、および領域のような他の確保については、DefaultServiceNumber を含める必要があります。

**例**割り当てを解除する DefaultServiceNumber「8005551234」
```
Unregister-CsOnlineDialInConferencingServiceNumber -BridgeName “Conference Bridge” -RemoveDefaultServiceNumber 8005551234 
```

## <a name="about-windows-powershell"></a>Windows PowerShell について

Windows PowerShell では、ユーザーと、ユーザーに許可されていることと許可されていないことを管理します。 Windows PowerShell では、ビジネス オンラインを行う複数のタスクがあれば、特に、日常的な作業を簡素化する管理の単一ポイントを使用して Office 365 と Skype を管理できます。 Windows PowerShell の使用を開始するには、次のトピックを参照してください。

  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525041)

Windows PowerShell には、ただ Office 365 管理センターを使用するだけではなく、速度、単純さ、生産性において多くの利点があります。次のトピックでこれらの利点について説明します。

  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [Windows PowerShell による Skype for Business Online の管理](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>See also
[電話会議ブリッジの設定を変更する](change-the-settings-for-an-audio-conferencing-bridge.md)
