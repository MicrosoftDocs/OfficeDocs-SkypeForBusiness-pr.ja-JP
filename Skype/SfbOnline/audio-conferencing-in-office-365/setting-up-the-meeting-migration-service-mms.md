---
title: "会議移行サービス (MM) を設定します。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 031f09c0-9d2a-487a-b6db-b5d4bed6d16a
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
description: "Skype for Business のサービスをバック グラウンドで実行され、自動的に Skype ユーザー向けのビジネスや Microsoft チーム会議の更新プログラムは、会議の移行サービス (MM)。MMS は、会議の移行ツールを実行するユーザーが Skype for Business や Microsoft チームの会議を更新する必要を消すために設計されています。"
ms.openlocfilehash: 0d33efb2f60a06853ba26cd6e525f624114c95a5
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="setting-up-the-meeting-migration-service-mms"></a>会議移行サービス (MM) を設定します。

Skype for Business のサービスをバック グラウンドで実行され、自動的に Skype ユーザー向けのビジネスや Microsoft チーム会議の更新プログラムは、会議の移行サービス (MM)。MMS は、会議の移行ツールを実行するユーザーが Skype for Business や Microsoft チームの会議を更新する必要を消すために設計されています。
  
 **要件**
  
MMS では、会議の開催者に Exchange Online のメールボックスが必要です。
  
 **主なシナリオ**
  
MMS では、次の 2 つの主なシナリオのユーザーの Skype 会議を更新します。
  
- ユーザーが内部設置型の Skype から for Business Server に移行 Skype for Business Online。
    
- ときに管理者は、そのユーザーの会議の電話会議情報を更新が必要となるユーザーの電話会議の設定に変更を加えます。
    
 **一般的なシナリオを MMS を使うことはできません。**
  
ここでは、いくつかの一般的なシナリオに適用することがあります。移行のサポートされているすべてのシナリオです。ただし、MMS は、次のシナリオで実行できないため、代わりに、[会議の移行ツール](https://go.microsoft.com/fwlink/p/?linkid=626047)を使用する必要があります。
  
- ユーザーのメールボックスが Exchange Server を自
    
- サードパーティ電話会議プロバイダーを使用します。
    
- Skype for Business Online から内部設置型の Skype サーバーにユーザーを移行
    
## <a name="updating-meetings-when-an-on-premises-user-is-migrated-to-skype-for-business-online"></a>オンプレミスのユーザーを移行 Skype for Business Online ときに、会議を更新

これは、場所 MMS に役立つ滑らかなユーザーの画面切り替えを作成する最も一般的なシナリオです。ユーザーから移行されるを内部設置型の Skype for Business Server skype for Business Online、MMS は、新しいユーザーを検出し、Skype for Business と Microsoft チーム会議のユーザーの予定表をスキャンします。今後のすべての会議は、そのユーザーの新しい情報で更新されます。
  
### <a name="if-youre-currently-using-skype-server-2015-for-audio-conferencing"></a>現在、電話会議に Skype Server 2015 を使用している場合

このシナリオで MMS に最適な操作性の下にあるベスト プラクティスに従うことをお勧めします。
  
- MMS には、Exchange Online では、上にも、オンプレミスの Exchange Server にもから移行する場合は、ユーザーのメールボックスが必要であるために、最初に Exchange Online にユーザーのメールボックスを移動します。
    
- 実行する前に、ユーザーに**電話会議**ライセンスを割り当てて、`Move-CSUser`コマンドレット ユーザーを移行します。MMS は、ユーザーの電話会議の設定が変更されたときにも会議を更新するためです。最初にライセンスを割り当ててしない、MMS が更新のすべての会議もう一度ライセンスを割り当てるとされます。
    
### <a name="if-youre-currently-using-a-third-party-audio-conferencing-provider-acp"></a>現在、サードパーティ電話会議プロバイダー (ACP) を使用している場合

サードパーティ acp を MMS を実行するかどうかは、組織の電話会議の設定に依存します。**電話会議**ライセンスをユーザーに割り当てるときに、ACP からダイヤルイン番号が自動的に置き換えることができます。その一方で、しまわないようにし、ACP からダイヤルイン番号を保持する必要があります。組織の設定を表示するには、次の Windows PowerShell コマンドを実行して、パラメーターの値をチェック`AutomaticallyReplaceAcpProvider`します。PowerShell でヘルプを必要がある場合は、この記事の最後にある [ [PowerShell による Skype for Business の組織の管理](setting-up-the-meeting-migration-service-mms.md#WPSInfo)] セクションを参照してください。
  
```
Get-CsOnlineDialInConferencingTenantSettings
```

- このパラメーターの値が $true の場合は、MMS がユーザーには、**電話会議**のライセンスが割り当てられているときに実行し、会議を更新します。**電話会議**のライセンスが割り当てられるまで、ACP からダイヤルイン番号が保持されます。
    
- このパラメーターの値が $false の場合は、[MMS を更新しません会議場合でも、ユーザーには、**電話会議**には、ライセンスが割り当てられています。ユーザーが手動で自動的にプロビジョニング Business 管理センター」または「Windows PowerShell を使用するため Skype で電話会議になるまで ACP からダイヤルイン番号が保持されます。
    
## <a name="updating-meetings-when-a-users-audio-conferencing-settings-change"></a>ユーザーの電話会議の設定を変更するときに、会議を更新

次のような場合、ビジネスや Microsoft チーム会議の既存の Skype MMS が更新されます。
  
- ときに、割り当てるか、**音声会議**ライセンスを削除します。
    
- 有効にすると、または電話会議を無効にします。
    
- 変更するか、一般向けの会議を使うように構成するユーザーの会議 ID をリセットします。
    
- ユーザーを新しい電話会議ブリッジに移動するとします。
    
- 電話番号では、電話会議ブリッジの割り当てはできません。これは、複雑な状況で、追加の手順が必要です。詳細については、[変更の有料またはフリー ダイヤルの無料番号で電話会議ブリッジ](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)を参照してください。
    
> [!IMPORTANT]
> MMS では、Microsoft ブリッジを使用している場合に会議を更新のみです。ユーザーが自分の会議を更新する必要がありますサードパーティ電話会議プロバイダーを使用している場合は、手動でします。この例では、[会議の移行ツール](https://go.microsoft.com/fwlink/p/?linkid=626047)を使用することができます。 
  
ユーザーの電話会議の設定をすべての変更は、MMS を開始します。具体的には、次の 2 つの変更は、会議の更新 MMS で発生するされません。
  
- (SIP ユーザー名またはドメインの) 会議の開催者の SIP アドレスを変更します。
    
- [更新 CsTenantMeetingUrl](https://go.microsoft.com/fwlink/p/?linkid=836442)コマンドを使用して、組織の会議 URL を変更するとします。
    
## <a name="what-happens-when-mms-updates-meetings"></a>MMS 会議を更新するときの動作

MMS では、ユーザーの会議を更新する必要があることを検出すると、次の操作を行いますが。
  
1. すべての Skype for Business および Microsoft チームの会議をユーザーは、今後のスケジュールを特定します。
    
  - MMS の実行時に、前に発生した Business または Microsoft チーム会議の Skype をスキップします。
    
  - 開催者である会議のみの更新します。
    
2. 置換、オンライン会議で、会議の詳細情報のブロック
    
3. 会議の開催者の代わりに会議のすべての受信者に更新を送信します。
    
 **MMS を実行するはどのくらい時間がかかりますか。**
  
会議を移行する MMS にかかる時間は、ユーザーの数が影響を受けると Business または Microsoft チーム会議の各ユーザーには、予定表での Skype の合計数によって異なります。最低でも、そのを実行する 10 分しか時間がかかります。大規模ないくつかの移行には、最大 12 時間がかかる場合も、中には、"1 hour"内にほとんどの移行が完了する必要があります。
  
 **制限と潜在的な問題**
  
- [Skype for Business または Microsoft チームの会議がスケジュールされているは、Web 版 Outlook に**追加する Skype 会議**] をクリックして、または Outlook で Skype 会議アドインを使用しているのみは移行されます。つまり、ユーザーは、コピーし、新しい会議を 1 つの会議から Skype のオンライン会議の情報を貼り付けます、その他の会議が更新されません。
    
- オンライン会議の情報をすべてブロックする会議を移行する場合 MMS 置き換えます。このため、ユーザーがそのブロックを編集した場合、変更内容が上書きされます。会議の詳細であるすべての内容をオンライン会議の情報の外部でブロックは影響されません。
    
     ![会議のブロック MMS によって更新を取得します。](../images/210a03ee-30c1-46f3-808f-4c2ebdaa3ea1.png)
  
- MMS を実行した後、会議を作成または (ホワイト ボード、ポーリングなど)、会議に添付されたコンテンツは保持されません。会議の開催者、会議には、コンテンツを事前に接続された、コンテンツは MMS の実行後に再作成する必要があります。
    
- 予定表のアイテムでメモの共有の会議へのリンクもから内での Skype 会議もは上書きされます。実際の会議のメモを OneNote に保存されている場合でもはあるメモには、共有のノートには上書きされますリンクのみです。
    
- 会議出席者は 250 を超える (開催者を含む) は移行されません。
    
- 招待状の本文に UNICODE 文字の一部可能性がありますが正しく更新されない次の特殊文字のいずれかに: ï、¿、½、します。
    
### <a name="what-will-the-users-see-when-mms-updates-their-meetings"></a>ユーザーに表示 MMS が、会議を更新するとよいですか。

MMS を会議の移行ツールと同じようには、ユーザーの代理として会議の更新を送信します。このためはの会議の会議の通知を承諾] が表示だけです。変更を行った場合電話会議をトリガー MMS に移行したオンプレミスから Skype for Business Online や場合だけでなく事前にユーザーに通知することをお勧めように、ユーザーは、混乱を招く可能性があります。
  
## <a name="managing-mms"></a>MMS を管理します。

Windows PowerShell を使用して MMS を管理し、継続的な移行の状態を確認する必要があります。このセクションの情報は、使い慣れた PowerShell を使用して、Skype for Business の組織を管理するものとします。新しい PowerShell 場合は、この記事の最後にある [ [PowerShell による Skype for Business の組織の管理](setting-up-the-meeting-migration-service-mms.md#WPSInfo)] セクションを参照してください。
  
### <a name="how-do-i-check-the-status-of-meeting-migrations"></a>会議の移行の状態を確認する方法は?

使用する、`Get-CsMeetingMigrationStatus`コマンドレットに移行する場合に会議の状態を確認します。以下は、いくつかの例です。
  
すべての MMS 移行のステータスの概要を移動するには、次のコマンドを実行します。
  
```
Get-CsMeetingMigrationStatus -SummaryOnly
```

これにより、次のようなすべての移行の状態の表形式で表示します。
  
状態 UserCount--<br/> 保留中の 21<br/>InProgress 6<br/> 失敗 2 <br/> 成功 131
> [!IMPORTANT]
> 任意の移行に失敗した場合は、可能な限り早くこれらの問題を解決するのには処理します。ユーザーはこれらに対処するまでは、それらのユーザーが開催する会議にダイヤルインすることはできません。参照してください、[エラーが発生する場合は何ですか?](setting-up-the-meeting-migration-service-mms.md#Troubleshooting)詳細についてはします。
  
すべての移行の完全な詳細情報を移動するには、特定の期間内で、使用することができます、`StartTime`と`EndTime`パラメーターします。たとえば、次のコマンド完全な詳細情報が発生したすべての移行に 2016 年 10 月 1 日からに戻ります 2016 年 10 月 8 日。
  
```
Get-CsMeetingMigrationStatus -StartTime "10/1/2016" -EndTime "10/8/2016"
```

するには、特定のユーザーの移行の状態を確認し、使用することができます、`UserId`そのパラメーターします。たとえば、次のコマンドでは、ユーザー ashaw@contoso.com の状態が返されます。
  
```
Get-CsMeetingMigrationStatus -UserId "ashaw@contoso.com"
```

### <a name="what-do-i-do-if-there-is-an-error"></a>エラーがある場合は、どうすればよいですか。
<a name="Troubleshooting"> </a>

実行すると、`Get-CsMeetingMigrationStatus`コマンドレットをサマリー ビューを取得し、失敗状態に移行する場合がありますが、実行する必要があるかを示します。
  
1. どのユーザーには影響を確認します。影響を受けるユーザー] の一覧と特定のエラーが報告されたにアクセスするのには、次のコマンドを実行します。
    
  ```
  Get-CsMeetingMigrationStatus | Where {$_.State -eq "Failed"} | Format-Table UserId,LastErrorMessage
  ```

2. これらのユーザーごとに、自分の会議を手動で移行するのには、[会議の移行ツール](https://go.microsoft.com/fwlink/p/?linkid=626047)を実行します。
    
3. 移行を会議の移行ツールを使用して解消されない場合は、次の 2 つのオプションがあります。
    
  - 新しい Skype 会議を作成するユーザーが存在します。
    
  - [連絡先をサポート](https://go.microsoft.com/fwlink/p/?LinkID=518322)します。
    
### <a name="enabling-and-disabling-mms"></a>有効にして、MMS を無効にします。
<a name="Troubleshooting"> </a>

MMS が既定では、組織全体で有効になっているが、必要に応じて、無効にできます。たとえば、すべての会議を手動で移行する場合、またはサードパーティ電話会議プロバイダーを使っている場合を実行している MMS いない必要があります。また、MMS を一時的に無効にすることもできます。たとえば、することがあるよりも大幅変更電話会議の設定] を組織のおよび操作 MMS にすべての変更が完了するまで動作しません。
  
表示する、組織の MMS が有効になっているかどうかは、次のコマンドを実行しの値を確認、`MeetingMigrationEnabled`パラメーターします。このパラメーターが $true に設定されている場合は、MMS が有効になります。
  
```
Get-CsTenantMigrationConfiguration
```

MMS を無効にするには、次のコマンドを実行します。
  
```
Set-CsTenantMigrationConfiguration -MeetingMigrationEnabled $false
```

MMS を有効にするには、次のコマンドを実行します。
  
```
Set-CsTenantMigrationConfiguration -MeetingMigrationEnabled $true
```

### <a name="enabling-and-disabling-mms-only-for-audio-conferencing-changes"></a>有効にして、電話会議の変更に関するのみ MMS を無効にします。
<a name="Troubleshooting"> </a>

電話会議の変更に関するのみ MMS 無効にすることもできます。ユーザーから移行される Skype ビジネス オンプレミス用 skype for Business Online ときも実行されます。電話会議の更新プログラムの現在の MMS 状態を確認するには、次のコマンドを実行しての値を確認、`AutomaticallyMigrateUserMeetings`パラメーターします。このパラメーターが $true に設定されている場合は、MMS が電話会議の設定が変更されたときに、ユーザーの会議を更新する設定されています。
  
```
Get-CsOnlineDialInConferencingTenantSettings
```

電話会議を MMS を無効にするには、次のコマンドを実行します。
  
```
Set-CsOnlineDialInConferencingTenantSettings -AutomaticallyMigrateUserMeetings $false
```

電話会議を MMS を有効にするには、次のコマンドを実行します。
  
```
Set-CsOnlineDialInConferencingTenantSettings  -AutomaticallyMigrateUserMeetings $true
```

### <a name="how-do-i-run-meeting-migration-manually-for-a-user"></a>実行方法会議移行手動で特定のユーザーのですか。
<a name="Troubleshooting"> </a>

に加えて、会議の自動移行する場合、**開始 CsExMeetingMigration**コマンドレットを実行して手動で特定のユーザーの会議の移行を実行することもできます。このコマンドレットでは、会議の移行キュー内のユーザーを追加します。移行サービスの会議、ユーザー リクエストし、会議を移行します。コマンドレット**Get CsMeetingMigrationStatus**移行を会議の状態を確認することができます。
  
ユーザー ashaw@contoso.com の会議の移行を開始する例を示します。
  
```
Start-CsExMeetingMigration -Identity ashaw@contoso.com
```

## <a name="using-powershell-to-manage-your-skype-for-business-organization"></a>PowerShell を使用して、Skype for Business の組織を管理するには
<a name="WPSInfo"> </a>

 **3.0 以降のバージョンの Windows PowerShell が実行していることを確認します。**
  
1. 3.0 以降のバージョンが実行していることを確認する: **[スタート] メニュー** > **Windows PowerShell**します。
    
2. **Windows PowerShell**のウィンドウで_ホストの取得_を入力して、バージョンを確認してください。
    
3. バージョン 3.0 以降をお持ちでない場合は、ダウンロードして、Windows PowerShell への更新プログラムをインストールする必要があります。[Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845)をダウンロードして 4.0 への Windows PowerShell を更新するを参照してください。表示されたら、お使いのコンピューターを再起動します。
    
4. Skype for Business Online できるようにする Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成するのには、Windows PowerShell モジュールをインストールする必要もします。このモジュールでは、64 ビット版コンピューターにのみサポートされているが、 [Skype for Business Online 用の Windows PowerShell モジュール](https://go.microsoft.com/fwlink/?LinkId=294688)では、Microsoft ダウンロード センターからダウンロードできます。求められた場合は、お使いのコンピューターを再起動します。
    
さらに詳しく調べ必要がある場合は、[単一の Windows PowerShell ウィンドウ内のすべての Office 365 サービスへの接続](https://technet.microsoft.com/EN-US/library/dn568015.aspx)を参照してください。
  
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
詳細については、Windows PowerShell を開始する場合は、[単一の Windows PowerShell ウィンドウ内のすべての Office 365 サービスに接続する](https://technet.microsoft.com/EN-US/library/dn568015.aspx)」または「[Skype for Business Online Windows PowerShell を使用してへ接続](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx)を参照してください。
  
- Windows powershell となるはすべてを管理するユーザーとユーザーの許可または使用できません。Windows PowerShell で Office 365 と Skype for Business Online の複数のタスクを実行するがある場合、日常業務を簡素化する管理の 1 つのポイントを使用して管理できます。Windows PowerShell で開始するには、次のトピックを参照してください。
    
  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Office 365 PowerShell を使用する必要がある理由](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell では多くの利点速度、わかりやすいように、および生産性でのみ実行しようとする設定の変更、多くのユーザーに一度になどの Office 365 管理センターを使用します。次のトピックでこれらの利点について学習します。
    
  - [Windows PowerShell で Office 365 を管理する最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Windows PowerShell を使用して、Skype for Business Online の管理するには](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell を使用して、共通の Skype for Business Online の管理タスクを実行するには](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>関連トピック

[Skype for Business とチームの Microsoft の音声会議をセットアップする設定します。](set-up-audio-conferencing.md)
