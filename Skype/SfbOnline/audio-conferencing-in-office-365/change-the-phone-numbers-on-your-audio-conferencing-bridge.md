---
title: オーディオ会議ブリッジの電話番号を変更します。
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6403f6d1-c05a-44ab-a6e0-558000e246f4
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 電話会議ライセンスをご購入いただく場合、Microsoft はお客様の組織の電話会議ブリッジ をホストします。電話会議ブリッジではさまざまな場所からダイヤルイン電話番号を受け取るため、会議の開催者や参加者はそれらの番号を使用して電話で Skype for Business 会議または Microsoft Teams 会議に参加できます。
ms.openlocfilehash: 1801a3501e865ca91081a0e298efc45882a872eb
ms.sourcegitcommit: 527c7dd4c5edc70503ba31e7c689a71d7356b17e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2018
ms.locfileid: "19703650"
---
# <a name="change-the-phone-numbers-on-your-audio-conferencing-bridge"></a>オーディオ会議ブリッジの電話番号を変更します。

[] **電話会議**ライセンスをご購入いただく場合、Microsoft はお客様の組織の *電話会議ブリッジ*  をホストします。電話会議ブリッジではさまざまな場所からダイヤルイン電話番号を受け取るため、会議の開催者や参加者はそれらの番号を使用して電話で Skype for Business 会議または Microsoft Teams 会議に参加できます。
  
[その他のサービス番号を取得](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md)することをだけでなく、会議用ブリッジに既に割り当てられている電話番号、(有料電話番号とフリー ダイヤルの番号を電話会議に使用される) とその他の場所を会議にそれらをブリッジすることができますユーザーのカバレッジを展開します。
  
> [!NOTE]
> 会議用ブリッジ用の電話番号の割り当て/割り当て解除できるようにするには、電話番号は、'*サービス*' の番号をする必要があります。 You can see the type of number it is by navigating to **Voice** > **Phone numbers** and looking in the **Number Type** column. Office 365 の通信のクレジットは、フリー ダイヤルでブリッジにダイヤルするための最初に設定しなければなりません。 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="steps-when-you-are-assigning-a-new-service-phone-number-to-your-conference-bridge"></a>新しいサービス用電話番号を会議ブリッジに割り当てるときの手順

### <a name="step-1---assign-the-new-phone-number-to-your-audio-conferencing-bridge"></a>手順 1 - 新しい電話番号を電話会議ブリッジに割り当てる

1. 自分の職場のアカウントで Office 365 にサインインします。
    
2. Go to the **Office 365 admin center** > **Admin centers** > **Skype for Business** > **Voice** > **Phone numbers**.
    
3. リストから電話番号を選択し、[操作] ウィンドウで [ **割り当て**] をクリックします。
    
4. [ **割り当て**] ページで、[ **保存**] をクリックします。
    
    1 つのサービス有料電話番号のみを会議ブリッジの既定の番号として設定できます。 **サービス無料電話番号は会議ブリッジの既定の番号として設定できません** 。サービス有料電話番号を割り当て、それを電話会議ブリッジの新しい既定の番号として設定する場合は、[ **この番号を既定値として使用**] をオンにします。
    
    > [!NOTE]
    > 新しい電話番号を割り当てた後その番号が新しい既定の番号になった場合でも、既存ユーザーの既定の番号は変わりません。 既定の有料または無料電話の番号を追加するを設定するのには開催者がミーティングへの招待、[携帯電話への招待に含まれている番号の設定](set-the-phone-numbers-included-on-invites.md)を参照してください。 
  


### <a name="step-2---change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users-optional"></a>手順 2 - ユーザーの会議の出席依頼に記載されている既定の電話番号を変更する (オプション)

ユーザーの既定の電話番号は、会議をスケジュールすると会議の出席依頼に記載される番号です。 詳細については、[携帯電話への招待に含まれている番号の設定](set-the-phone-numbers-included-on-invites.md)を参照してください。
  
1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. Go to the **Office 365 admin center** > **Admin centers** > **Skype for Business** > **Audio conferencing** > **Users** and select the users in the list.
    
3. [操作] ウィンドウで [ **編集**] をクリックします。
    
4. [ **既定の有料電話番号**] または [ **既定のフリーダイヤル番号**] の下で、リストから番号を選択して [ **保存**] をクリックします。
    
変更が保存されると、次回新しい会議をスケジュールするときに新しい既定の電話番号が開催者の会議の出席依頼に記載されます。
  
### <a name="step-3---update-existing-meeting-invites-of-users-using-the-meeting-migration-service-optional"></a>手順 3 - Meeting Migration Service を使用してユーザーの既存の会議の出席依頼を更新する (オプション)

次の 2 つの手順では、Windows PowerShell を開始することが必要になります。
  
Meeting Migration Service を使用して、ユーザーの既定の電話番号が変更される前に、組織内のユーザーに送信済みの会議の出席依頼をオプションで更新できます。詳細については、「[Meeting Migration Service (MMS) のセットアップ](setting-up-the-meeting-migration-service-mms.md)」をご覧ください。
  
- 手順 2 で既定の電話番号を変更したユーザーに対して、Meeting Migration Service (MMS) を実行します。これを実行するには、次のコマンドを実行します。
    
```
    Start-CsExMeetingMigration user@contoso.com
```

- 会議の移行の状態を確認することもできます。[ *保留*  ] または [ *進行中*  ] の状態で操作が行われなくなると、すべての会議のスケジュールが変更されることがあります。
    
```
    Get-CsMeetingMigrationStatus -SummaryOnly
```

## <a name="steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge"></a>会議ブリッジのサービス用電話番号の割り当てを解除するときの手順


電話番号を会議ブリッジから割り当て解除すると、ユーザーは今後その電話番号を使用して会議に参加することができなくなります。電話番号が変更されているため、電話会議ブリッジから電話番号が割り当て解除される前に、既定の番号として電話番号を設定しているすべてのユーザーを更新することと、会議の既存の出席依頼を更新することが重要です。 
  
ユーザー、およびユーザーの会議を更新する前に電話番号が削除されると、既存の会議の出席依頼には、会議に参加するために使用できない電話番号が記載されてしまいます。
  
最初の 3 つの手順では、Windows PowerShell を開始することが必要になります。 これを行う方法を表示するをクリックして[Windows PowerShell を使用して管理する方法を知りたいのですか?](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#bkPowerShell)
  
### <a name="step-1---update-users-that-have-the-phone-number-to-be-unassigned-as-one-of-their-default-numbers"></a>手順 1 - 既定の番号の 1 つとしての割り当てが解除される電話番号があるユーザーを更新する

既定の番号としての割り当てが解除される番号があるすべてのユーザーについて、既定の有料または無料電話番号を置き換えて、会議のスケジュール変更のプロセスを開始します。これを実行するには、次のコマンドを実行します。
  
```
Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber <Number to be removed> -ToNumber <Number to be set as new default> -NumberType <"Toll" or "Toll-Free"> -RescheduleMeetings
```
 > [!IMPORTANT] 
 >既定の有料または無料電話番号が、Skype のビジネス管理センター内のユーザーを変更することもできます。 ただし、これも自動的にスケジュールを変更、会議。 
 
 詳細については、[携帯電話への招待に含まれている番号の設定](set-the-phone-numbers-included-on-invites.md)を参照してください。

  > [!NOTE]
  > 所属する組織の規模に応じて、完了するまで時間がかかる場合があります。 
  
### <a name="step-2---view-meeting-migration-status-using-windows-powershell"></a>手順 2 - Windows PowerShell を使用して会議の移行状態を表示する

*保留中*または*実行中*の状態にする工程がないと、すべての会議を再スケジュールされます。
  
```
Get-CsMeetingMigrationStatus -SummaryOnly
```

Meeting Migration Service の詳細については、「 [Meeting Migration Service (MMS) のセットアップ](setting-up-the-meeting-migration-service-mms.md)」をご覧ください。
  
### <a name="step-3---unassign-the-old-phone-number-from-the-audio-conferencing-bridge"></a>手順 3 - 古い電話番号を電話会議ブリッジから割り当て解除する

1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. Go to the **Office 365 admin center** > **Admin centers** > **Skype for Business** > **Voice** > **Phone numbers**.
    
3. リストから電話番号を選択し、[操作] ウィンドウで [ **割り当てを解除**] をクリックします。
    
4. 確認ウィンドウで、[ **はい**] をクリックします。
    
  > [!IMPORTANT]
  > 電話会議ブリッジから電話番号の割り当てを解除すると、ユーザーはその電話番号を使用して新規または既存の会議に参加できなくなります。 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Windows PowerShell で管理する方法
<a name="bkPowerShell"> </a>

### <a name="to-verify-that-windows-powershell-is-ready-to-go"></a>Windows PowerShell が使用できる状態かを確認する場合

 次の手順では、3.0 またはそれ以降のバージョンの Windows PowerShell が実行していることを確認します。
  
1. **[スタート] メニュー**を入力 > **Windows PowerShell**。
    
2. バージョンを確認するのには**Windows PowerShell の**ウィンドウで_ホストの取得_を入力します。
    
3. バージョン 3.0 以降を使用していない場合は、Windows PowerShell の更新プログラムをダウンロードおよびインストールする必要があります。Windows PowerShell をダウンロードして、バージョン 4.0 に更新するには、「[Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845)」を参照してください。メッセージが表示されたら、コンピューターを再起動します。
    
4. また、Skype のビジネス オンライン ビジネス オンラインの Skype に接続するリモートの Windows PowerShell セッションを作成することを可能にするため Windows PowerShell モジュールをインストールする必要があります。 このモジュールでは、64 ビット コンピューターでのみサポートされ、[オンライン ビジネスの Skype のモジュールを Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=294688)に Microsoft ダウンロード センターからダウンロードすることができます。 メッセージが表示されたら、コンピューターを再起動します。
    
詳細については、「[単一の Windows PowerShell ウィンドウですべての Office 365 サービスに接続する](https://technet.microsoft.com/EN-US/library/dn568015.aspx)」を参照してください。
  
### <a name="to-start-windows-powershell"></a>Windows PowerShell を開始する場合

 **Windows PowerShell セッションを開始する**
  
1. From the **Start Menu** > **Windows PowerShell**.
    
2. [ **Windows PowerShell**] ウィンドウで、次を実行して、Office 365 の組織に接続します。
    
    > [!NOTE]
    > Skype for Business Online Windows PowerShell モジュールを初めて使用するときに、 **Import-Module** コマンドを実行するだけです。
  
> 
  ```
    Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

Windows PowerShell を開始する方法の詳細を設定する場合は、 [1 つの Windows PowerShell のウィンドウ内のすべての Office 365 サービスに接続する](https://technet.microsoft.com/EN-US/library/dn568015.aspx)か、 [Windows PowerShell を使用して、オンライン ビジネスの Skype への接続](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx)を参照してください。
  
### <a name="save-time-and-automate"></a>自動化して時間を節約

このプロセスを自動化することにより時間を節約するには、[セット CsOnlineDialInConferencingUser](http://go.microsoft.com/fwlink/?LinkId=617688)または**セット CsOnlineDialInConferencingUserDefaultNumber**コマンドレットを使用できます。
  
- 特定ユーザーのデフォルトの有料または無料電話番号を変更するには、[[Set-CsOnlineDialInConferencingUser](http://go.microsoft.com/fwlink/?LinkId=617688)] コマンドレットを使用します。
    
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
  
## <a name="about-windows-powershell"></a>Windows PowerShell について

Windows PowerShell では、ユーザー、または、実行することはできませんを管理できます。 Windows PowerShell では、ビジネス オンラインを行う複数のタスクがあれば、特に、日常的な作業を簡素化する管理の単一ポイントを使用して Office 365 と Skype を管理できます。 Windows PowerShell の使用を開始するには、次のトピックを参照してください。
    
  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525041)
    
Windows PowerShell には、ただ Office 365 管理センターを使用するだけではなく、速度、単純さ、生産性において多くの利点があります。次のトピックでこれらの利点について説明します。
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Windows PowerShell による Skype for Business Online の管理](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [クイック リファレンス: Windows PowerShell を使用した一般的な Lync Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>See also
[電話会議ブリッジの設定を変更する](change-the-settings-for-an-audio-conferencing-bridge.md)
