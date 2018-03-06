---
title: "電話会議ブリッジの有料または無料の電話番号を変更する"
ms.author: tonysmit
author: tonysmit
ms.date: 11/29/2017
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.lync.lac.PSTNConferencingRemovePhoneNumberFromBridge
ms.prod: office-online-server
localization_priority: Normal
ms.custom: Strat_SB_PSTN
ms.assetid: 6403f6d1-c05a-44ab-a6e0-558000e246f4
description: "電話会議ライセンスをご購入いただく場合、Microsoft はお客様の組織の電話会議ブリッジ をホストします。電話会議ブリッジではさまざまな場所からダイヤルイン電話番号を受け取るため、会議の開催者や参加者はそれらの番号を使用して電話で Skype for Business 会議または Microsoft Teams 会議に参加できます。"
---

# 電話会議ブリッジの有料または無料の電話番号を変更する

 **電話会議**ライセンスをご購入いただく場合、Microsoft はお客様の組織の *電話会議ブリッジ*  をホストします。電話会議ブリッジではさまざまな場所からダイヤルイン電話番号を受け取るため、会議の開催者や参加者はそれらの番号を使用して電話で Skype for Business 会議または Microsoft Teams 会議に参加できます。
  
自分の会議ブリッジに割り当て済みの電話番号の他に、[Skype for Business サービスの電話番号を取得する](../what-is-phone-system-in-office-365/getting-service-phone-numbers-for-skype-for-business-and-microsoft-teams.md) (電話会議に使用する有料と無料の電話番号) を他の場所から取得してそれを会議ブリッジに割り当てることができるので、ユーザーが使用する対象範囲を拡大できます。
  
> [!NOTE]
> 会議ブリッジの電話番号を割り当て/割り当てを解除するには、電話番号が「 *サービス*  」番号である必要があります。その番号がどのタイプかは、[ **音声**] > [ **電話番号**] に移動して、[ **番号の種類**] 列から確認できます。 
  
## 新しいサービス用電話番号を会議ブリッジに割り当てるときの手順

### 手順 1 - 新しい電話番号を電話会議ブリッジに割り当てる

1. 自分の職場のアカウントで Office 365 にサインインします。
    
2. **Office 365 管理センター**、[ **管理センター**]、[ **Skype for Business**]、[ **音声**]、[ **電話番号**] の順に移動します。
    
3. リストから電話番号を選択し、[操作] ウィンドウで [ **割り当て**] をクリックします。
    
4. [ **割り当て**] ページで、[ **保存**] をクリックします。
    
    1 つのサービス有料電話番号のみを会議ブリッジの既定の番号として設定できます。 **サービス無料電話番号は会議ブリッジの既定の番号として設定できません** 。サービス有料電話番号を割り当て、それを電話会議ブリッジの新しい既定の番号として設定する場合は、[ **この番号を既定値として使用**] をオンにします。
    
    > [!NOTE]
    > 新しい電話番号を割り当てた後その番号が新しい既定の番号になった場合でも、既存ユーザーの既定の番号は変わりません。開催者の会議の出席依頼に追加する既定の有料または無料電話番号を設定する方法については、「[出席依頼に含まれている会議の開催者のために電話会議の電話番号を設定する](set-the-audio-conferencing-phone-numbers-for-meeting-organizers-that-are-include.md)」をご覧ください。 
  
### 手順 2 - ユーザーの会議の出席依頼に記載されている既定の電話番号を変更する (オプション)

ユーザーの既定の電話番号は、会議をスケジュールすると会議の出席依頼に記載される番号です。詳細については、「[出席依頼に含まれている会議の開催者のために電話会議の電話番号を設定する](set-the-audio-conferencing-phone-numbers-for-meeting-organizers-that-are-include.md)」をご覧ください。
  
1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. **Office 365 管理センター**、[ **管理センター**]、[ **Skype for Business**]、[ **電話会議**]、[ **ユーザー**] の順に移動し、リストからユーザーを選択します。
    
3. [操作] ウィンドウで [ **編集**] をクリックします。
    
4. [ **既定の有料電話番号**] または [ **既定のフリーダイヤル番号**] の下で、リストから番号を選択して [ **保存**] をクリックします。
    
変更が保存されると、次回新しい会議をスケジュールするときに新しい既定の電話番号が開催者の会議の出席依頼に記載されます。
  
### 手順 3 - Meeting Migration Service を使用してユーザーの既存の会議の出席依頼を更新する (オプション)

次の 2 つの手順では、Windows PowerShell を開始することが必要になります。その方法を確認するには、[Windows PowerShell で管理する方法](change-the-toll-or-toll-free-numbers-on-your-audio-conferencing-bridge.md#bk_PowerShell)をクリックします。
  
Meeting Migration Service を使用して、ユーザーの既定の電話番号が変更される前に、組織内のユーザーに送信済みの会議の出席依頼をオプションで更新できます。詳細については、「[Meeting Migration Service (MMS) のセットアップ](setting-up-the-meeting-migration-service-mms.md)」をご覧ください。
  
- 手順 2 で既定の電話番号を変更したユーザーに対して、Meeting Migration Service (MMS) を実行します。これを実行するには、次のコマンドを実行します。
    
```
	Start-CsExMeetingMigration user@contoso.com

```

- 会議の移行の状態を確認することもできます。[ *保留*  ] または [ *進行中*  ] の状態で操作が行われなくなると、すべての会議のスケジュールが変更されることがあります。
    
```
	Get-CsMeetingMigrationStatus -SummaryOnly
```

## 会議ブリッジのサービス用電話番号の割り当てを解除するときの手順
<a name="bk_StartPowerShell"> </a>

電話番号を会議ブリッジから割り当て解除すると、ユーザーは今後その電話番号を使用して会議に参加することができなくなります。電話番号が変更されているため、電話会議ブリッジから電話番号が割り当て解除される前に、既定の番号として電話番号を設定しているすべてのユーザーを更新することと、会議の既存の出席依頼を更新することが重要です。
  
ユーザー、およびユーザーの会議を更新する前に電話番号が削除されると、既存の会議の出席依頼には、会議に参加するために使用できない電話番号が記載されてしまいます。
  
最初の 3 つの手順では、Windows PowerShell を開始することが必要になります。その方法を確認するには、[Windows PowerShell で管理する方法](change-the-toll-or-toll-free-numbers-on-your-audio-conferencing-bridge.md#bk_PowerShell)をクリックします。
  
### 手順 1 - 既定の番号の 1 つとしての割り当てが解除される電話番号があるユーザーを更新する

既定の番号としての割り当てが解除される番号があるすべてのユーザーについて、既定の有料または無料電話番号を置き換えて、会議のスケジュール変更のプロセスを開始します。これを実行するには、次のコマンドを実行します。
  
```
Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber <Number to be removed> -ToNumber <Number to be set as new default> -NumberType <"Toll" or "Toll-Free"> -RescheduleMeetings
```

> [!NOTE]
> 所属する組織の規模に応じて、完了するまで時間がかかる場合があります。 
  
 **Skype for Business 管理センターでユーザーの既定の有料または無料電話番号を変更することもできます。ただし、これにより自動的に会議のスケジュールが変更されることはありません** 。詳細については、「[出席依頼に含まれている会議の開催者のために電話会議の電話番号を設定する](set-the-audio-conferencing-phone-numbers-for-meeting-organizers-that-are-include.md)」をご覧ください。
  
### 手順 2 - Windows PowerShell を使用して会議の移行状態を表示する

[ *保留*  ] または [ *進行中*  ] の状態で操作が行われなくなると、すべての会議のスケジュールが変更されます。
  
```
Get-CsMeetingMigrationStatus -SummaryOnly
```

Meeting Migration Service の詳細については、「 [Meeting Migration Service (MMS) のセットアップ](setting-up-the-meeting-migration-service-mms.md)」をご覧ください。
  
### 手順 3 - 古い電話番号を電話会議ブリッジから割り当て解除する

1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. **Office 365 管理センター**、[ **管理センター**]、[ **Skype for Business**]、[ **音声**]、[ **電話番号**] の順に移動します。
    
3. リストから電話番号を選択し、[操作] ウィンドウで [ **割り当てを解除**] をクリックします。
    
4. 確認ウィンドウで、[ **はい**] をクリックします。
    
> [!IMPORTANT]
> 電話会議ブリッジから電話番号の割り当てを解除すると、ユーザーはその電話番号を使用して新規または既存の会議に参加できなくなります。 
  
## Windows PowerShell で管理する方法
<a name="bk_PowerShell"> </a>

### Windows PowerShell が使用できる状態かを確認する場合

 **Windows PowerShell バージョン 3.0 以降を実行していることを確認する**
  
1. バージョン 3.0 以降を実行していることを確認するには [ **スタート**] メニューから [ **Windows PowerShell**] を選びます。
    
2. [ **Windows PowerShell**] ウィンドウに「 _Get-Host_」と入力して、バージョンを確認します。
    
3. バージョン 3.0 以降を使用していない場合は、Windows PowerShell の更新プログラムをダウンロードおよびインストールする必要があります。Windows PowerShell をダウンロードして、バージョン 4.0 に更新するには、「[Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845)」を参照してください。メッセージが表示されたら、コンピューターを再起動します。
    
4. Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成できるように、Skype for Business Online の Windows PowerShell モジュールもインストールする必要があります。このモジュールは、64 ビット版のコンピューターでのみサポートされており、「[Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688)」の Microsoft ダウンロード センターからダウンロードできます。メッセージが表示されたら、コンピューターを再起動します。
    
詳細については、「[単一の Windows PowerShell ウィンドウですべての Office 365 サービスに接続する](https://technet.microsoft.com/library/dn568015.aspx)」を参照してください。
  
### Windows PowerShell を開始する場合

 **Windows PowerShell セッションを開始する**
  
1. [ **スタート**] メニューで [ **Windows PowerShell**] を選びます。
    
2. [ **Windows PowerShell**] ウィンドウで、次を実行して、Office 365 の組織に接続します。
    
    > [!NOTE]
    > Skype for Business Online Windows PowerShell モジュールを初めて使用するときに、 **Import-Module** コマンドを実行するだけです。
  
> 
  ```
  Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
  ```

> 
  ```
  $credential = Get-Credential
  ```

> 
  ```
  $session = New-CsOnlineSession -Credential $credential
  ```

> 
  ```
  Import-PSSession $session
  ```

Windows PowerShell の起動の詳細については、「[単一の Windows PowerShell ウィンドウですべての Office 365 サービスに接続する](https://technet.microsoft.com/library/dn568015.aspx)」または「[Windows PowerShell を使用した Lync Online への接続](https://technet.microsoft.com/library/dn362795%28v=ocs.15%29.aspx)」を参照してください。
  
### 時間の節約または自動化

時間を節約したり、処理を自動化したりするには、[Set-CsOnlineDialInConferencingUser](http://go.microsoft.com/fwlink/?LinkId=617688) または **Set-CsOnlineDialInConferencingUserDefaultNumber** コマンドレットを使用できます。
  
- 特定ユーザーのデフォルトの有料または無料電話番号を変更するには、[[Set-CsOnlineDialInConferencingUser](http://go.microsoft.com/fwlink/?LinkId=617688)] コマンドレットを使用します。
    
  - ユーザーのデフォルトの無料電話番号を変更するには、次を実行します。
    
  ```
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   80045551234
  ```

- ユーザーの元の既定の電話番号または所在地に基づいて既定の有料または無料電話番号を変更するには、 **Set-CsOnlineDialInConferencingUserDefaultNumber** コマンドレットを使用します。
    
    > [!NOTE]
    > 注: BridgeID を探すには、 **Get-CsOnlineDialInConferencingBridge** を使用します。
  
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
  
### 詳細情報

- Windows PowerShell で行うのは、ユーザーを管理し、ユーザーに何を許可して何を禁止するかを管理することです。Windows PowerShell を利用すると、Office 365 と Skype for Business Online の管理を 1 か所で行うことができるので、複数のタスクを担当する管理者の日常業務を単純化できます。Windows PowerShell の使用を開始するには、次のトピックを参照してください。
    
  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Office 365 PowerShell を使用する必要がある理由](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell には、ただ Office 365 管理センターを使用するだけではなく、速度、単純さ、生産性において多くの利点があります。次のトピックでこれらの利点について説明します。
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Windows PowerShell による Skype for Business Online の管理](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)
    

