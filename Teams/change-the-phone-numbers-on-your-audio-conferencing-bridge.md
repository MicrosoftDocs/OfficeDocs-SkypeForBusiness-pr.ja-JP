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
description: オーディオ会議のライセンスを購入すると、Microsoft は、組織の場合は、オーディオ会議ブリッジをホストしています。 オーディオ会議用ブリッジは、ミーティングの開催者と参加者が使用できるようにする Skype に電話を使用するビジネスまたはマイクロソフトのチームの会議に参加するのにはさまざまな場所からのダイヤルに電話番号を提供します。
ms.openlocfilehash: bc26fc64f4b95c1a469908251781c4951c7d0a84
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32211801"
---
# <a name="change-the-phone-numbers-on-your-audio-conferencing-bridge"></a>電話会議ブリッジの電話番号を変更する

**オーディオ会議**のライセンスを購入すると、Microsoft は、組織の場合は、オーディオ会議ブリッジをホストしています。 オーディオ会議用ブリッジは、ミーティングの開催者を別の場所からのダイヤルに電話番号と参加者を使用して Skype に電話を使用するビジネスまたはマイクロソフトのチームの会議に参加します。
  
[その他のサービス番号を取得](/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers)することをだけでなく、会議用ブリッジに既に割り当てられている電話番号、(有料電話番号とフリー ダイヤルの番号を電話会議に使用される) から他の場所、および会議にそれらをブリッジすることができますしの割り当てユーザーのカバレッジを展開します。
  
> [!NOTE]
> 会議用ブリッジ用の電話番号の割り当て/割り当て解除できるようにするには、電話番号は、'*サービス*' の番号をする必要があります。 **音声**に移動することが番号の種類を参照してください > 従来の**番号の種類**] 列で検索し、ポータル内の**電話番号**です。 Office 365 の通信のクレジットは、フリー ダイヤルでブリッジにダイヤルするための最初に設定しなければなりません。

## <a name="steps-when-you-are-assigning-a-new-service-phone-number-to-your-conference-bridge"></a>テレビ会議サービスに新しいサービスの電話番号を割り当てる場合の手順

### <a name="step-1---assign-the-new-phone-number-to-your-audio-conferencing-bridge"></a>手順 1 - 新しい電話番号を割り当てるには、オーディオ会議ブリッジに

1. 勤務先のアカウントで Office 365 にサインインします。

2. **Office 365 管理センター**を参照して > **管理センター** > **チーム & Skype** > **レガシー ポータル** > **音声** > **の電話番号**です。

3. 電話番号を選択します] ボックスの一覧から、操作ウィンドウで、[**割り当て**] をクリックします。

4. [**割り当てる**] ページで [**保存**] をクリックします。

### <a name="step-2---change-the-default-phone-number-of-your-conference-bridge-optional"></a>ステップ 2 - 変更、既定の電話番号 (省略可能)、会議ブリッジ

テレビ会議サービスの既定の電話番号は、発信呼び出しが参加者または開催者から会議内で配置する場合に使用される呼び出し元 ID を定義します。

サービスの有料電話番号だけは、会議用ブリッジは、既定の番号として設定できます。**サービスのフリー ダイヤル番号は、会議用ブリッジ数の既定値として設定できません**。 サービスの有料電話番号を割り当てると、新しい既定の番号、電話会議ブリッジとして設定するには、次の手順に従います。

1. 勤務先のアカウントで Office 365 にサインインします。

2. **Office 365 管理センター**を参照して > **管理センター** > **チーム & Skype** > **会議** > **会議ブリッジ**です。

3. サービスの有料電話番号が既定値として構成することを強調表示します。

4. [**既定に設定**] を選択します。
 
### <a name="step-3---change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users-optional"></a>ステップ 3 - 会議に含まれる既定の電話番号の変更が (省略可能) ユーザーの招待します。

ユーザーの既定の電話番号は、会議をスケジュールするとき、会議に含まれるものへの招待します。 新規ユーザーの既定の電話番号を割り当てる方法を含む詳細について[に含まれている番号は、マイクロソフトのチームで招待の電話を設定](set-the-phone-numbers-included-on-invites-in-teams.md)したり、[オンライン ビジネスの Skype で招待に含まれている番号の電話の設定](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)を参照してください。
  
1. 職場または学校のアカウントを使用して、Office 365 にサインインします。

2. **Office 365 管理センター**を参照して > **管理センター** > **チーム & Skype** > **レガシー ポータル** > **電話会議** > **ユーザー**、および、リスト上のユーザーを選択します。

3. 操作ウィンドウで [**編集**] をクリックします。

4. **既定の電話番号**や**フリー ダイヤル番号を既定値**、[リストの番号を選択し、[**保存**] をクリックします。

変更を保存すると、番号は、会議に含まれます、新しい既定の電話番号への招待の開催者の次に新しい会議をスケジュールするとき。

### <a name="step-4---update-existing-meeting-invites-of-users-using-the-meeting-migration-service-optional"></a>手順 4 - 既存の会議の会議の移行サービス (オプション) を使用してユーザーの招待を更新

次の 2 つの手順では、Windows PowerShell を開始する必要があります。
  
既定電話番号、およびこの会議の一部またはすべてのユーザーへの招待を更新する場合を使用して、既定の電話番号が変更された前に、組織内のユーザーに既に送信された会議の招待を必要に応じて更新できます、会議の移行サービスです。 詳細については、[会議の移行サービス (MMS) の設定](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)を参照してください。
  
- 手順 2 で変更された、既定の電話番号を持っているユーザーの移行会議サービス (MMS) を実行します。 これを行うには、次のコマンドを実行します。

```
    Start-CsExMeetingMigration user@contoso.com
```

- 会議を表示することもできます。 移行の状態。 *保留中*または*実行中*の状態にする工程がないと、すべての会議のスケジュールを変更がします。

```
    Get-CsMeetingMigrationStatus -SummaryOnly
```

## <a name="steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge"></a>会議用ブリッジのサービスの電話番号の割り当てを解除する場合の手順


会議用ブリッジからの電話番号の割り当てを解除すると、ユーザーは同じもうその電話番号を使用しているミーティングに参加することができません。 電話番号を変更するための可能性があります (存在する場合) の既定の番号として電話番号を持っているすべてのユーザーを更新して、既存の電話番号は、オーディオ会議ブリッジから割り当てられた前に会議の招待を更新するのには重要です。

ユーザーとの会議を更新せず、電話番号を削除する場合、既存の会議の招待が含まれますがミーティングに参加するために動作しない電話番号には。

最初の 3 つの手順では、Windows PowerShell を開始する必要があります。 これを行う方法を表示するをクリックして[Windows PowerShell を使用して管理する方法を知りたいのですか?](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#bkPowerShell)

### <a name="step-1---update-users-who-have-the-phone-number-to-be-unassigned-as-one-of-their-default-numbers"></a>ステップ 1 - として、既定の番号のいずれかの割り当てを解除する電話番号を持つユーザーを更新

既定の有料または無料電話番号が既定値として割り当てを解除して、会議の予定変更のプロセスを開始する番号を持つすべてのユーザーを交換してください。 これを行うには、次のコマンドを実行します。

```
Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber <Number to be removed> -ToNumber <Number to be set as new default> -NumberType <"Toll" or "Toll-Free"> -RescheduleMeetings
```
 > [!IMPORTANT] 
 >既定の有料または無料電話番号が、Skype のビジネス管理センター内のユーザーを変更することもできます。 ただし、これも自動的にスケジュールを変更、会議。 
 
 詳細については、[携帯電話に含まれている番号は、マイクロソフトのチームで招待を設定](set-the-phone-numbers-included-on-invites-in-teams.md)したり、[オンライン ビジネスの Skype で招待に含まれている番号の電話の設定](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)を参照してください。

  > [!NOTE]
  > サイズによっては、組織の完了に時間がかかります。

### <a name="step-2---view-meeting-migration-status-using-windows-powershell"></a>ステップ 2 - 会議 Windows PowerShell を使用して移行のステータスを表示

*保留中*または*実行中*の状態にする工程がないと、すべての会議を再スケジュールされます。

```
Get-CsMeetingMigrationStatus -SummaryOnly
```

会議の移行サービスの詳細については、[会議の移行サービス (MMS) の設定](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)を参照してください。
  
### <a name="step-3---unassign-the-old-phone-number-from-the-audio-conferencing-bridge"></a>手順 3 - オーディオ会議ブリッジから以前の電話番号の割り当てを解除

1. 職場または学校のアカウントを使用して、Office 365 にサインインします。

2. **Office 365 管理センター**を参照して > **管理センター** > **チーム & Skype** > **レガシー ポータル** > **音声** > **の電話番号**です。

3. 電話番号を選択します] ボックスの一覧から、操作ウィンドウで、[**割り当ての解除**] をクリックします。

4. [確認] ウィンドウで、[**はい**] をクリックします。

   > [!IMPORTANT]
   > 電話番号は、オーディオ会議ブリッジから割り当てられているが、電話番号は新規または既存の会議に参加するユーザーの利用できなきます。

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Windows PowerShell での管理方法について
<a name="bkPowerShell"> </a>

### <a name="to-verify-that-windows-powershell-is-ready-to-go"></a>Windows PowerShell が移動する準備ができていることを確認するのには

 次の手順では、3.0 またはそれ以降のバージョンの Windows PowerShell が実行していることを確認します。

1. **[スタート] メニュー**を入力 > **Windows PowerShell**。

2. バージョンを確認するのには**Windows PowerShell の**ウィンドウで_ホストの取得_を入力します。

3. バージョン 3.0 以降を使用していない場合は、Windows PowerShell の更新プログラムをダウンロードおよびインストールする必要があります。Windows PowerShell をダウンロードして、バージョン 4.0 に更新するには、「[Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845)」を参照してください。メッセージが表示されたら、コンピューターを再起動します。

4. また、Skype のビジネス オンライン ビジネス オンラインの Skype に接続するリモートの Windows PowerShell セッションを作成することを可能にするため Windows PowerShell モジュールをインストールする必要があります。 このモジュールでは、64 ビット コンピューターでのみサポートされ、[オンライン ビジネスの Skype のモジュールを Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=294688)に Microsoft ダウンロード センターからダウンロードすることができます。
メッセージが表示されたら、コンピューターを再起動します。

詳細については、「[単一の Windows PowerShell ウィンドウですべての Office 365 サービスに接続する](https://technet.microsoft.com/library/dn568015.aspx)」を参照してください。

### <a name="to-start-windows-powershell"></a>Windows PowerShell を開始するには

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

  - 1 つを 8005551234 ことがなく、すべてのユーザーの既定のフリー ダイヤル番号を設定するのには次のコマンドを実行します。

  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```

  - 8005551239 に、既定のフリー ダイヤル番号として 8005551234 があり、自動的に、会議のスケジュールを変更するすべてのユーザーの既定のフリー ダイヤル番号を変更するには、次のコマンドを実行します。

  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber 8005551234 -ToNumber 8005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

  - 無料電話番号が 8005551234 に米国内にあるすべてのユーザーの既定の設定を自動的に、会議のスケジュールを変更は、次のコマンドを実行します。

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

Windows PowerShell では、ユーザー、または、実行することはできませんを管理できます。 Windows PowerShell では、ビジネス オンラインを行う複数のタスクがあれば、特に、日常的な作業を簡素化する管理の単一ポイントを使用して Office 365 と Skype を管理できます。 Windows PowerShell の使用を開始するには、次のトピックを参照してください。

  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [Office 365 PowerShell を使用する必要がある理由](https://go.microsoft.com/fwlink/?LinkId=525041)

Windows PowerShell には、ただ Office 365 管理センターを使用するだけではなく、速度、単純さ、生産性において多くの利点があります。次のトピックでこれらの利点について説明します。

  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [Windows PowerShell による Skype for Business Online の管理](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>関連トピック
[電話会議ブリッジの設定を変更する](change-the-settings-for-an-audio-conferencing-bridge.md)
