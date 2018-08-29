---
title: 電話会議ブリッジの電話番号を変更する
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
ms.openlocfilehash: c567c1394c60b0be04cae90865cea14b856f1cd5
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/28/2018
ms.locfileid: "23255713"
---
# <a name="change-the-phone-numbers-on-your-audio-conferencing-bridge"></a>電話会議ブリッジの電話番号を変更する

[] **電話会議**ライセンスをご購入いただく場合、Microsoft はお客様の組織の *電話会議ブリッジ*  をホストします。電話会議ブリッジではさまざまな場所からダイヤルイン電話番号を受け取るため、会議の開催者や参加者はそれらの番号を使用して電話で Skype for Business 会議または Microsoft Teams 会議に参加できます。

ご自分の会議ブリッジに割り当て済みの番号の他に、他の場所から[追加のサービス電話番号を取得](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md) (電話会議に使用される有料・無料電話番号) し、それらの番号を会議ブリッジに割り当ててユーザーが使用する対象範囲を拡大できます。

> [!NOTE]
> 会議ブリッジ用に電話番号を割り当て/割り当て解除できるようにするには、電話番号は '*サービス*' 電話番号である必要があります。 [**音声**]  >  [**電話番号**] に移動して [**番号の種類**] を参照することで番号の種類を確認することができます。 Office 365 のコミュニケーション クレジットは、ユーザーが無料電話番号のブリッジにダイヤルインできるように、最初にセットアップする必要があります。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="steps-when-you-are-assigning-a-new-service-phone-number-to-your-conference-bridge"></a>新しいサービス電話番号を会議ブリッジに割り当てるときの手順

### <a name="step-1---assign-the-new-phone-number-to-your-audio-conferencing-bridge"></a>手順 1 - 新しい電話番号を電話会議ブリッジに割り当てる

1. 自分の職場のアカウントで Office 365 にサインインします。

2. [**Office 365 管理センター**]  >  [**管理センター**]  >  [**Skype for Business**]  >  [**音声**]  >  [**電話番号**] の順に開きます。

3. リストから電話番号を選択し、[操作] ウィンドウで [ **割り当て**] をクリックします。

4. [ **割り当て**] ページで、[ **保存**] をクリックします。

    1 つのサービス有料電話番号のみを会議ブリッジの既定の番号として設定できます。 **サービス無料電話番号は会議ブリッジの既定の番号として設定できません** 。サービス有料電話番号を割り当て、それを電話会議ブリッジの新しい既定の番号として設定する場合は、[ **この番号を既定値として使用**] をオンにします。

    > [!NOTE]
    > 新しい電話番号を割り当てた後その番号が新しい既定の番号になった場合でも、既存ユーザーの既定の番号は変わりません。 開催者の会議の招集に追加する既定の有料または無料電話番号を設定する方法については、「[会議招集に含まれている電話番号を設定する](set-the-phone-numbers-included-on-invites.md)」をご覧ください。



### <a name="step-2---change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users-optional"></a>手順 2 - ユーザーの会議の招集に記載されている既定の電話番号を変更する (オプション)

ユーザーの既定の電話番号は、会議をスケジュールすると会議の招集に記載される番号です。 詳細については、「 [会議招集に含まれる電話番号の設定](set-the-phone-numbers-included-on-invites.md)」を参照してください。

1. 職場または学校のアカウントを使用して、Office 365 にサインインします。

2. [**Office 365 管理センター**]  >  [**管理センター**]  >  [**Skype for Business**]  >  [**電話会議**]  >  [**ユーザー**] の順に開き、リスト内のユーザーを選択します。

3. [操作] ウィンドウで [ **編集**] をクリックします。

4. [ **既定の有料電話番号**] または [ **既定のフリーダイヤル番号**] の下で、リストから番号を選択して [ **保存**] をクリックします。

変更が保存されると、次回新しい会議をスケジュールするときに新しい既定の電話番号が開催者の会議の出席依頼に記載されます。

### <a name="step-3---update-existing-meeting-invites-of-users-using-the-meeting-migration-service-optional"></a>手順 3 - Meeting Migration Service を使用してユーザーの既存の会議の招集を更新する (オプション)

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

## <a name="steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge"></a>会議ブリッジのサービス電話番号の割り当てを解除するときの手順


電話番号を会議ブリッジから割り当て解除すると、ユーザーは今後その電話番号を使用して会議に参加することができなくなります。電話番号が変更されているため、電話会議ブリッジから電話番号が割り当て解除される前に、既定の番号として電話番号を設定しているすべてのユーザーを更新することと、会議の既存の出席依頼を更新することが重要です。

ユーザー、およびユーザーの会議を更新する前に電話番号が削除されると、既存の会議の出席依頼には、会議に参加するために使用できない電話番号が記載されてしまいます。

最初の 3 つの手順では、Windows PowerShell を開始することが必要になります。 その方法を確認するには、「[Windows PowerShell で管理する方法](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#bkPowerShell)」をクリックします。

### <a name="step-1---update-users-that-have-the-phone-number-to-be-unassigned-as-one-of-their-default-numbers"></a>手順 1 - 既定の番号の 1 つとしての割り当てが解除される電話番号があるユーザーを更新する

既定の番号としての割り当てが解除される番号があるすべてのユーザーについて、既定の有料または無料電話番号を置き換えて、会議のスケジュール変更のプロセスを開始します。これを実行するには、次のコマンドを実行します。

```
Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber <Number to be removed> -ToNumber <Number to be set as new default> -NumberType <"Toll" or "Toll-Free"> -RescheduleMeetings
```
 > [!IMPORTANT]
 >Skype for Business 管理センターでユーザーの既定の有料または無料電話番号を変更することもできます。ただし、これにより自動的に会議のスケジュールが変更されることはありません 。

 詳細については、「 [会議招集に含まれる電話番号の設定](set-the-phone-numbers-included-on-invites.md)」を参照してください。

  > [!NOTE]
  > 所属する組織の規模に応じて、完了するまで時間がかかる場合があります。

### <a name="step-2---view-meeting-migration-status-using-windows-powershell"></a>手順 2 - Windows PowerShell を使用して会議の移行状態を表示する

[*保留*] または [*進行中*] の状態で操作が行われなくなると、すべての会議のスケジュールが変更されます。

```
Get-CsMeetingMigrationStatus -SummaryOnly
```

Meeting Migration Service の詳細については、「 [Meeting Migration Service (MMS) のセットアップ](setting-up-the-meeting-migration-service-mms.md)」をご覧ください。

### <a name="step-3---unassign-the-old-phone-number-from-the-audio-conferencing-bridge"></a>手順 3 - 古い電話番号を電話会議ブリッジから割り当て解除する

1. 職場または学校のアカウントを使用して、Office 365 にサインインします。

2. [**Office 365 管理センター**]  >  [**管理センター**]  >  [**Skype for Business**]  >  [**音声**]  >  [**電話番号**] の順に開きます。

3. リストから電話番号を選択し、[操作] ウィンドウで [ **割り当てを解除**] をクリックします。

4. 確認ウィンドウで、[ **はい**] をクリックします。

  > [!IMPORTANT]
  > 電話会議ブリッジから電話番号の割り当てを解除すると、ユーザーはその電話番号を使用して新規または既存の会議に参加できなくなります。

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Windows PowerShell で管理する方法
<a name="bkPowerShell"> </a>

### <a name="to-verify-that-windows-powershell-is-ready-to-go"></a>Windows PowerShell が使用できる状態かを確認するには

 これらの手順では、Windows PowerShell バージョン 3.0 かそれ以降を実行していることを確認します。

1. [**スタート メニュー**]  >  [**Windows PowerShell**] と入力します。

2. **Windows PowerShell** のウィンドウで _Get-Host_ と入力し、バージョンを確認します。

3. バージョン 3.0 以降を使用していない場合は、Windows PowerShell の更新プログラムをダウンロードおよびインストールする必要があります。Windows PowerShell をダウンロードして、バージョン 4.0 に更新するには、「[Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845)」を参照してください。メッセージが表示されたら、コンピューターを再起動します。

4. Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成できるように、Skype for Business Online の Windows PowerShell モジュールもインストールする必要があります。 このモジュールは、64 ビットのコンピューターでのみサポートされており、Microsoft ダウンロード センターの「[Skype for Business Online 用 Windows PowerShell モジュール](https://go.microsoft.com/fwlink/?LinkId=294688)」からダウンロードできます。
メッセージが表示されたら、コンピューターを再起動します。

詳細については、「[単一の Windows PowerShell ウィンドウですべての Office 365 サービスに接続する](https://technet.microsoft.com/EN-US/library/dn568015.aspx)」を参照してください。

### <a name="to-start-windows-powershell"></a>Windows PowerShell を開始する場合

 **Windows PowerShell セッションを開始する**

1. [**スタート メニュー**]  >  [**Windows PowerShell**] から開きます。

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

Windows PowerShell の起動の詳細については、「[単一の Windows PowerShell ウィンドウですべての Office 365 サービスに接続する](https://technet.microsoft.com/EN-US/library/dn568015.aspx)」または「[Windows PowerShell を使用した Skype for Business  への接続](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx)」を参照してください。

### <a name="save-time-and-automate"></a>時間の節約と自動化

プロセスを自動化して時間を節約するために、[Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) または **Set-CsOnlineDialInConferencingUserDefaultNumber** コマンドレットを使用できます。

- 特定ユーザーの既定の有料または無料電話番号を変更するには、[[Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688)] コマンドレットを使用します。

  - ユーザーのデフォルトの無料電話番号を変更するには、次を実行します。

  ```
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   80045551234
  ```

- ユーザーの元の既定の電話番号または所在地に基づいて既定の有料または無料電話番号を変更するには、 **Set-CsOnlineDialInConferencingUserDefaultNumber** コマンドレットを使用します。

    > [!NOTE]
    > BridgeID を探すには、 **Get-CsOnlineDialInConferencingBridge** を使用します。

  - 既定の無料電話番号がないユーザー全員の無料電話番号を 8005551234 に設定するには、次を実行します。

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

Windows PowerShell では、ユーザーと、ユーザーに許可されていることと許可されていないことを管理します。 Windows PowerShell を利用すると、Office 365 と Skype for Business Online の管理を 1 か所で行うことができるので、複数のタスクを担当する管理者の日常業務を単純化できます。 Windows PowerShell の使用を開始するには、次のトピックを参照してください。

  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [Office 365 PowerShell を使用しなければならない理由](https://go.microsoft.com/fwlink/?LinkId=525041)

Windows PowerShell には、ただ Office 365 管理センターを使用するだけではなく、速度、単純さ、生産性において多くの利点があります。次のトピックでこれらの利点について説明します。

  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [Windows PowerShell による Skype for Business Online の管理](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [クイック リファレンス: Windows PowerShell を使用した一般的な Lync Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>関連トピック
[電話会議ブリッジの設定を変更する](change-the-settings-for-an-audio-conferencing-bridge.md)
