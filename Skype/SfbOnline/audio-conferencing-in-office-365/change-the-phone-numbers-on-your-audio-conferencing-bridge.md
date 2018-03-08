---
title: "電話番号で電話会議ブリッジを変更します。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 6403f6d1-c05a-44ab-a6e0-558000e246f4
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: "電話会議ライセンスを購入すると、組織の自分の電話会議ブリッジ Microsoft をホストします。会議の開催者と参加者使えるように Skype for Business または Microsoft チーム会議の電話を使用してに参加するさまざまな場所からのダイヤルイン電話番号に電話会議ブリッジを使用できます。"
ms.openlocfilehash: 21603ebc5ea710598a1af70a66fe4388e206cea9
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="change-the-phone-numbers-on-your-audio-conferencing-bridge"></a>電話番号で電話会議ブリッジを変更します。

**電話会議**ライセンスを購入した場合、*電話会議ブリッジ*を組織の Microsoft をホストします。会議の開催者と参加者使えるように Skype for Business または Microsoft チーム会議の電話を使用してに参加するさまざまな場所からのダイヤルイン電話番号に電話会議ブリッジを使用できます。
  
ほかに、会議ブリッジに既に割り当てられている電話番号を実行できます[その他のサービスの番号を取得する](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md)(有料電話番号と電話会議用フリー ダイヤルの番号) から、その他の場所を会議には、従業員同士、することができます。ユーザーの範囲を展開します。
  
> [!NOTE]
> 会議ブリッジの電話番号の割り当て/割り当て解除を行うできるようにするには、電話番号に [*サービス*] の番号ことがあります。**音声**に移動して、番号の種類を確認できます > **電話番号**と、**数値型**] 列で検索します。Office 365 通信クレジットにフリー ダイヤルのブリッジにダイヤルインするための最初に設定する必要があります。 
  
## <a name="steps-when-you-are-assigning-a-new-service-phone-number-to-your-conference-bridge"></a>自分の会議ブリッジに新しいサービスの電話番号を割り当てる場合の手順

### <a name="step-1---assign-the-new-phone-number-to-your-audio-conferencing-bridge"></a>手順 1 -、電話会議ブリッジに新しい電話番号を割り当てる

1. Office 365 の職場のアカウントでサインインします。
    
2. **Office 365 管理センター**に移動 > **管理センター** > **Skype for Business** > **音声** > **電話番号**です。
    
3. 電話番号を選択し、リストから、操作ウィンドウで、[**割り当て**] をクリックします。
    
4. [**割り当て**] ページで、[**保存**] をクリックします。
    
    サービスの有料電話番号だけを会議ブリッジは、既定の番号として設定することができます。**サービスのフリー ダイヤルの番号は、会議ブリッジの既定の数として設定することはできません**。サービス有料電話番号を割り当てる場合は、電話会議ブリッジの新しい既定の番号として設定するには、**この番号を既定の使用**を選択します。
    
    > [!NOTE]
    > 新しい電話番号が割り当てられると、数に新しい既定の番号にようになった場合でも、既存のユーザーの既定の番号は変更されません。開催者が会議に招待既定有料またはフリー ダイヤルの番号に追加されるを設定するの[への招待に含まれる数値の電話の設定](set-the-phone-numbers-included-on-invites.md)を参照してください。 
  
### <a name="step-2---change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users-optional"></a>手順 2 - 会議に含まれている既定の電話番号の変更は、(オプション) ユーザーの招待します。

ユーザーの既定の電話番号が、会議をスケジュールするときに、会議に含まれるものへの招待します。詳細については、[携帯電話への招待に含まれる数値の設定](set-the-phone-numbers-included-on-invites.md)を参照してください。
  
1. 職場または学校のアカウントで Office 365 にサインインします。
    
2. **Office 365 管理センター**に移動 > **管理センター** > **Skype for Business** > **電話会議** > **ユーザー**と、リスト内のユーザーを選択します。
    
3. 操作ウィンドウで、[**編集**] をクリックします。
    
4. [**既定の電話番号**または**フリー ダイヤル番号を既定**では、リストの番号を選択し、[**保存**] をクリックします。
    
変更を保存すると、番号、会議に含める、新しい既定の電話番号への招待の開催者の次回新しい会議をスケジュールします。
  
### <a name="step-3---update-existing-meeting-invites-of-users-using-the-meeting-migration-service-optional"></a>手順 3 - 既存の会議の出席依頼、会議移行サービス (オプション) を使用しているユーザーの更新

次の 2 つの手順では、Windows PowerShell を起動する必要があります。
  
会議の移行サービスを使用して、既定の電話番号を変更する前に、組織のユーザーに既に送信された会議出席依頼を必要に応じて更新できます。詳細については、[設定会議の移行サービス (MM) を](setting-up-the-meeting-migration-service-mms.md)参照してください。
  
- 手順 2 で変更の既定の電話番号を持っているユーザーの会議移行サービス (MM) を実行します。これを行うには、次のコマンドを実行します。
    
```
    Start-CsExMeetingMigration user@contoso.com

```

- 会議を表示することもできます。 移行の状況を報告します。*保留中*または*作業中*の状態での操作がないと、すべての会議をスケジュールとします。
    
```
    Get-CsMeetingMigrationStatus -SummaryOnly
```

## <a name="steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge"></a>サービスの電話番号を会議ブリッジの割り当てを解除する場合の手順


会議ブリッジからの電話番号の割り当てを解除するときに、ユーザーができるようになったその電話番号を使用して、会議に参加できません。重要なは、(設定されている場合)、既定の番号に電話番号を可能性があるすべてのユーザーを更新して、既存の電話番号に電話会議ブリッジの割り当ては前に会議の出席依頼を更新するのには、電話番号を変更すると、いるため。 
  
ユーザーとの会議を更新せず、電話番号を削除する場合、既存の会議の出席依頼で、電話番号、会議への参加をなったは動作しませんを含めることができます。
  
最初の 3 つの手順では、Windows PowerShell を起動する必要があります。これを行う方法を表示するには、クリックして[Windows PowerShell で管理する方法を知りたいですか?](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#bkPowerShell)
  
### <a name="step-1---update-users-that-have-the-phone-number-to-be-unassigned-as-one-of-their-default-numbers"></a>手順 1 - 電話番号に、既定の番号のいずれかで割り当てを解除するユーザーの更新

既定の有料またはフリー ダイヤルの番号を既定の数値で割り当てを解除して、会議のスケジュールを変更するプロセスを開始する番号を持つすべてのユーザーに置き換えます。これを行うには、次のコマンドを実行します。
  
```
Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber <Number to be removed> -ToNumber <Number to be set as new default> -NumberType <"Toll" or "Toll-Free"> -RescheduleMeetings
```
 > [!IMPORTANT] 
 >既定の有料または Skype for Business 管理センターのユーザーのフリー ダイヤルの番号を変更することもできます。ただしの会議を自動的に再スケジュールこのされません。 
 
 詳細については、[携帯電話への招待に含まれる数値の設定](set-the-phone-numbers-included-on-invites.md)を参照してください。

  > [!NOTE]
  > によっては、組織のサイズを完了するには、少し時間がかかります。 
  
### <a name="step-2---view-meeting-migration-status-using-windows-powershell"></a>手順 2 - 移行状態の Windows PowerShell を使用して会議を表示します。

*保留中*または*作業中*の状態での操作がないと、すべての会議を再スケジュールされます。
  
```
Get-CsMeetingMigrationStatus -SummaryOnly
```

会議の移行サービスの詳細については、[会議の移行サービス (MM) の設定](setting-up-the-meeting-migration-service-mms.md)を参照してください。
  
### <a name="step-3---unassign-the-old-phone-number-from-the-audio-conferencing-bridge"></a>手順 3 - 電話会議ブリッジから古い電話番号割り当て解除を行う

1. 職場または学校のアカウントで Office 365 にサインインします。
    
2. **Office 365 管理センター**に移動 > **管理センター** > **Skype for Business** > **音声** > **電話番号**です。
    
3. 電話番号を選択し、リストから、操作ウィンドウで、[**割り当ての解除**] をクリックします。
    
4. 確認ウィンドウで、[**はい**] をクリックします。
    
  > [!IMPORTANT]
  > 電話番号は、電話会議ブリッジの割り当てられているが、電話番号しなくなる新規または既存の会議に参加するユーザーは利用できません。 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Windows PowerShell で管理する方法を知りたいとしていますか。
<a name="bkPowerShell"> </a>

### <a name="to-verify-that-windows-powershell-is-ready-to-go"></a>Windows PowerShell を移動する準備ができていることを確認するには

 **3.0 以降のバージョンの Windows PowerShell が実行していることを確認します。**
  
1. 3.0 以降のバージョンが実行していることを確認する: **[スタート] メニュー** > **Windows PowerShell**します。
    
2. **Windows PowerShell**のウィンドウで_ホストの取得_を入力して、バージョンを確認してください。
    
3. バージョン 3.0 以降をお持ちでない場合は、ダウンロードして、Windows PowerShell への更新プログラムをインストールする必要があります。[Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845)をダウンロードして 4.0 への Windows PowerShell を更新するを参照してください。表示されたら、お使いのコンピューターを再起動します。
    
4. Skype for Business Online できるようにする Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成するのには、Windows PowerShell モジュールをインストールする必要もします。このモジュールでは、64 ビット版コンピューターにのみサポートされているが、 [Skype for Business Online 用の Windows PowerShell モジュール](https://go.microsoft.com/fwlink/?LinkId=294688)では、Microsoft ダウンロード センターからダウンロードできます。求められた場合は、お使いのコンピューターを再起動します。
    
さらに詳しく調べ必要がある場合は、[単一の Windows PowerShell ウィンドウ内のすべての Office 365 サービスへの接続](https://technet.microsoft.com/EN-US/library/dn568015.aspx)を参照してください。
  
### <a name="to-start-windows-powershell"></a>Windows PowerShell を開始するには

 **Windows PowerShell セッションを開始します。**
  
1. **[スタート] メニュー**から > **Windows PowerShell**します。
    
2. **Windows PowerShell**ウィンドウで、実行して、Office 365 の組織に接続します。
    
    > [!NOTE]
    > Skype for Business Online の Windows PowerShell モジュールに使用する**インポート モジュール**の最初のレコード] コマンドの実行にのみがあります。
  
> 
  ```
    Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

詳細については、Windows PowerShell を開始する場合は、[単一の Windows PowerShell ウィンドウ内のすべての Office 365 サービスに接続する](https://technet.microsoft.com/EN-US/library/dn568015.aspx)」または「 [Skype for Business Online Windows PowerShell を使用してへ接続](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx)を参照してください。
  
### <a name="save-time-or-automate"></a>時間を節約したり、自動化したり

時間を節約またはこのプロセスを自動化する、[セット CsOnlineDialInConferencingUser](http://go.microsoft.com/fwlink/?LinkId=617688)または**セット CsOnlineDialInConferencingUserDefaultNumber**コマンドレットを使用することができます。
  
- 既定の有料またはフリー ダイヤルの番号を特定のユーザーを変更するのにには、[セット CsOnlineDialInConferencingUser](http://go.microsoft.com/fwlink/?LinkId=617688)コマンドレットを使用します。
    
  - ユーザーの既定のフリー ダイヤル番号を変更するには、次のコマンドを実行します。
    
  ```
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   80045551234
  ```

- 既定の有料またはフリー ダイヤルの元の既定の番号またはその場所に基づくユーザー数を変更するのには、**セット CsOnlineDialInConferencingUserDefaultNumber**コマンドレットを使用します。
    
    > [!NOTE]
    > [BridgeID を検索するには、 **Get CsOnlineDialInConferencingBridge**を使用します。
  
  - 既定のフリー ダイヤル番号を設定するには、1 つに 8005551234 せずにすべてのユーザーに実行します。
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id>  
  ```

  - 8005551239 に、既定のフリー ダイヤル番号として 8005551234 があり、会議のスケジュールを自動的に変更するすべてのユーザーの既定のフリー ダイヤル番号を変更するには、次のコマンドを実行します。
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber 8005551234 -ToNumber 8005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

  - 8005551234 米国内にあるすべてのユーザーの既定のフリー ダイヤル番号を設定、会議のスケジュールを自動的に変更は、次のコマンドを実行します。
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

    > [!NOTE]
    > ニーズ上にある Office 365 管理センターで設定されているユーザーの連絡先情報に一致するように使用される場所です。 
  
## <a name="about-windows-powershell"></a>Windows PowerShell について

Windows powershell となるはすべてを管理するユーザーとユーザーの許可または使用できません。Windows PowerShell で Office 365 と Skype for Business Online の複数のタスクを実行するがある場合、日常業務を簡素化する管理の 1 つのポイントを使用して管理できます。Windows PowerShell で開始するには、次のトピックを参照してください。
    
  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Office 365 PowerShell を使用する必要がある理由](https://go.microsoft.com/fwlink/?LinkId=525041)
    
Windows PowerShell では多くの利点速度、わかりやすいように、および生産性でのみ実行しようとする設定の変更、多くのユーザーに一度になどの Office 365 管理センターを使用します。次のトピックでこれらの利点について学習します。
    
  - [Windows PowerShell で Office 365 を管理する最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Windows PowerShell を使用して、Skype for Business Online の管理するには](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell を使用して、共通の Skype for Business Online の管理タスクを実行するには](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>関連トピック
[電話会議ブリッジの設定を変更します。](change-the-settings-for-an-audio-conferencing-bridge.md)
  