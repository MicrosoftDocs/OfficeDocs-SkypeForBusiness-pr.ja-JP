---
title: Meeting Migration Service (MMS) のセットアップ
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 031f09c0-9d2a-487a-b6db-b5d4bed6d16a
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
description: Meeting Migration Service (MMS) は Skype for Business サービスの 1 つで、バックグラウンドで動作して、ユーザーのために Skype for Business および Microsoft Teams 会議を自動的に更新します。MMS はユーザーが会議移行ツールを実行して Skype for Business および Microsoft Teams 会議を更新しなくても済むように設計されています。
ms.openlocfilehash: 820726451c1ed9a28d29882903348f231ee4ce16
ms.sourcegitcommit: 527c7dd4c5edc70503ba31e7c689a71d7356b17e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2018
ms.locfileid: "19703810"
---
# <a name="setting-up-the-meeting-migration-service-mms"></a>Meeting Migration Service (MMS) のセットアップ

Meeting Migration Service (MMS) は Skype for Business サービスの 1 つで、バックグラウンドで動作して、ユーザーのために Skype for Business および Microsoft Teams 会議を自動的に更新します。 MMS はユーザーが会議移行ツールを実行して Skype for Business および Microsoft Teams 会議を更新しなくても済むように設計されています。  このツールは、マイクロソフトのチーム ミーティングにビジネス会議のため Skype を移行しません。  
  
 **要件**
  
MMS では、会議の開催者のメールボックスを Exchange Online で利用できるようにする必要があります。
  
 **主要シナリオ**
  
MMS は次の 2 つの主要シナリオでユーザーのために Skype 会議を更新します。
  
- ユーザーがオンプレミスの Skype for Business Server から Skype for Business Online に移行される場合。
    
- 管理者が、ユーザーの会議内の電話会議情報を更新する必要が生じる変更を、ユーザーの電話会議設定に対して行う場合。
    
 **MMS を使用できない一般的なシナリオ**
  
該当する可能性のある一般的なシナリオを次に示します。これらのシナリオはすべて移行でサポートされます。ただし、MMS はこれらのシナリオでは動作せず、代わりに [Meeting Migration Tool](https://go.microsoft.com/fwlink/p/?linkid=626047) を使用する必要があります。
  
- ユーザーのメールボックスが Exchange Server のオンプレミスにある
    
- サードパーティ電話会議プロバイダーを使用する
    
- Skype for Business Online からオンプレミスの Skype Server に移行する
    
## <a name="updating-meetings-when-an-on-premises-user-is-migrated-to-skype-for-business-online"></a>オンプレミスのユーザーが Skype for Business Online に移行されるときに会議を更新する

これは、MMS がユーザーのスムーズな移行に役立つ、最も一般的なシナリオです。ユーザーがオンプレミスの Skype for Business Server から Skype for Business Online に移行されるときに、MMS は新しいユーザーを検出してそのユーザーの予定表に Skype for Business 会議と Microsoft Teams 会議がないかスキャンします。今後の会議はすべて、そのユーザーの新しい情報で更新されます。
  
### <a name="if-youre-currently-using-skype-server-2015-for-audio-conferencing"></a>現在 Skype Server 2015 を電話議で使用している場合

このシナリオでは、MMS による最高のエクスペリエンスを得るために下記のベスト プラクティスに従うことをお勧めします。
  
- MMS ではユーザーのメールボックスを Exchange Online で利用できる状態にする必要があるため、オンプレミスの Exchange Server からの移行も実行している場合は、先にユーザーのメールボックスを Exchange Online に移動します。
    
- Assign the **Audio Conferencing** license to the user before you run the `Move-CSUser` cmdlet to migrate the user. This is because MMS also updates meetings when audio conferencing settings are changed for a user. If you don't assign the license first, MMS will update all meetings again when you assign the license.
    
### <a name="if-youre-currently-using-a-third-party-audio-conferencing-provider-acp"></a>現在サードパーティの音声会議プロバイダー (ACP) を使用している場合

サードパーティの ACP では、MMS が動作するかしないかは所属する組織のダイヤルイン会議設定に応じて変わります。 **電話会議**ライセンスをユーザーに割り当てるときに、自動的に ACP からのダイヤルイン番号を置き換えることを選べます。一方、そのようにせずに、ダイヤルイン番号を ACP からのダイヤルイン番号を保持する必要がある場合もあります。所属する組織の設定を確認するには、次の Windows PowerShell コマンドを実行して、パラメーター  `AutomaticallyReplaceAcpProvider` の値を確認します。PowerShell についてサポートが必要な場合は、この記事の終わりにある「[PowerShell を使用した Skype for Business の組織の管理](setting-up-the-meeting-migration-service-mms.md#WPSInfo)」セクションをご覧ください。
  
```
Get-CsOnlineDialInConferencingTenantSettings
```

- このパラメーターの値が $true の場合、MMS はユーザーに **電話会議**ライセンスが割り当てられるときに動作して、会議を更新します。 **電話会議**ライセンスが割り当てられるまで、ACP からのダイヤルイン番号は保持されます。
    
- このパラメーターの値が $false の場合、ユーザーに **電話会議**ライセンスが割り当てられても MMS は会議を更新しません。ユーザーが Skype for Business 管理センターで、または Windows PowerShell を使用して電話会議に対して手動でプロビジョニングされるまで、ACP からのダイヤルイン番号は保持されます。
    
## <a name="updating-meetings-when-a-users-audio-conferencing-settings-change"></a>ユーザーの電話会議の設定が変更されるときの会議の更新

MMS は次の場合に既存の Skype for Business Online および Microsoft Teams の会議を更新します。
  
- **電話会議**ライセンスを割り当てる、または削除する場合
    
- 電話会議を有効または無効にする場合
    
- パブリック会議を使用するよう構成されたユーザーの会議 ID を変更またはリセットする場合
    
- ユーザーを新しい電話会議ブリッジに移行する場合
    
- 電話番号が電話会議ブリッジから割り当てられていない場合。これは複雑なシナリオで、追加手順を必要とします。詳細については、「[電話会議ブリッジの有料または無料の電話番号を変更する](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)」をご覧ください。
    
> [!IMPORTANT]
> Microsoft ブリッジを使用している場合、MMS は会議の更新のみを行います。サードパーティの電話会議プロバイダーを使用している場合、ユーザーは会議を手動で更新する必要があります。この場合、[Meeting Migration Tool](https://go.microsoft.com/fwlink/p/?linkid=626047) を使用できます。 
  
ユーザーの電話会議の設定に対する変更の一部は、MMS をトリガーしません。特に、次の 2 つの変更では、MMS によって会議が更新されません。
  
- 会議の開催者の SIP アドレスを変更する場合 (SIP ユーザー名または SIP ドメインのいずれか)
    
- [Update-CsTenantMeetingUrl](https://go.microsoft.com/fwlink/p/?linkid=836442) コマンドを使用して組織の会議 URL を変更する場合。
    
## <a name="what-happens-when-mms-updates-meetings"></a>MMS が会議を更新するときに発生すること

MMS がユーザーの会議を更新する必要があることを検出すると、次の操作が行われます。
  
1. ユーザーが今後にスケジュールしたすべての Skype for Business 会議および Microsoft Teams 会議を識別する
    
  - MMS が動作する前に発生したすべての Skype for Business 会議および Microsoft Teams 会議がスキップされる
    
  - ユーザーが開催者である会議のみが更新される
    
2. 会議の詳細のオンライン会議の情報ブロックを置き換える
    
3. 会議の開催者に代わって、更新内容をすべての会議出席依頼の受信者に送信する
    
 **MMS が動作するまでにかかる時間**
  
MMS が会議を移行するのにかかる時間の量は、影響するユーザーの数、各ユーザーが予定表に抱えている Skype for Business 会議および Microsoft Teams 会議の合計数によって変わります。少なくとも、動作するのに 10 分はかかります。一部の大規模な移行は最大 12 時間かかりますが、多くの移行は 1 時間で完了します。
  
 **制限事項と潜在的な問題**
  
- Outlook on the Web で [ **Skype 会議の追加**] ボタンをクリックして、または Outlook 用の Skype 会議アドインを使用してスケジュールされた Skype for Business 会議および Microsoft Teams 会議のみが移行されます。このため、ユーザーがある会議から新しい会議に Skype オンライン会議の情報をコピーして貼り付ける場合は、その新しい会議は更新されません。
    
- MMS は会議が移行されるときにオンライン会議の情報ブロックのすべてを置き換えます。このため、ユーザーがそのブロックを編集した場合は、それらの変更は上書きされます。オンライン会議の情報ブロック以外の会議の詳細に含まれているコンテンツは影響しません。
    
     ![The meeting block that gets updated by MMS](../images/210a03ee-30c1-46f3-808f-4c2ebdaa3ea1.png)
  
- 作成された、または会議に添付された会議コンテンツ (ホワイトボード、投票など) は、MMS が動作すると保持されません。会議の開催者が事前にコンテンツを会議に添付している場合、そのコンテンツは MMS の動作後に再作成する必要があります。
    
- 予定表の項目内、および Skype 会議からの共有の会議ノートへのリンクも上書きされます。OneNote に保存される実際の会議ノートは引き続きその場所に存在し、共有のノートへのリンクのみが上書きされます。
    
- (開催者を含めて) 250 人を超える参加者がいる会議は移行できません。
    
- 会議出席依頼の本文の UNICODE 文字の一部が間違って特殊文字 ï、¿、½、� に置き換えられる場合があります。
    
### <a name="what-will-the-users-see-when-mms-updates-their-meetings"></a>MMS によって会議が更新されるときにユーザーには何が表示されますか。

会議移行ツールと同様に、MMS はユーザーに代わって会議の更新を送信します。このため、ユーザーに表示されるのは、別の機会の会議承諾通知のみになります。これはユーザーにとって分かりにくい可能性があるため、ユーザーをオンプレミスから Skype for Business Online に移行するときだけではなく、MMS をトリガーする電話会議の変更を行うときにも、ユーザーに事前に通知することをお勧めします。
  
## <a name="managing-mms"></a>MMS の管理

Windows PowerShell を使用して MMS を管理し、継続的な移行の状態を確認する必要があります。 このセクションの情報は、PowerShell を使用した Skype for Business の組織の管理に慣れていることを前提としています。 PowerShell を初めて使用する場合は、この資料の最後に[、Skype をビジネスの組織を管理するために PowerShell を使用する](setting-up-the-meeting-migration-service-mms.md#WPSInfo)を参照してください。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
### <a name="how-do-i-check-the-status-of-meeting-migrations"></a>会議の移行のステータスを確認する方法を教えてください。

`Get-CsMeetingMigrationStatus` コマンドレットを使用して、会議の移行のステータスを確認します。次に例を示します。
  
すべての MMS の移行に関する概要ステータスを取得するには、次のコマンドを実行します。
  
```
Get-CsMeetingMigrationStatus -SummaryOnly
```

これによって、すべての移行状態が次のように表形式で表示されます。
  
UserCount の状態--<br/> 保留中の 21<br/>InProgress 6<br/> 失敗 2 <br/> 成功 131
> [!IMPORTANT]
> 移行が失敗したことを確認した場合は、それらの問題を解決する措置をできるだけ早く行います。問題に対処するまで、これらのユーザーによって開催される会議にダイヤルインすることはできません。詳細については、「[エラーが発生した場合の対処方法を教えてください。](setting-up-the-meeting-migration-service-mms.md#Troubleshooting)」セクションをご覧ください。
  
特定の期間内におけるすべての移行の詳細を取得する場合に、 `StartTime` および `EndTime` パラメーターを使用できます。たとえば、次のコマンドを実行すると、2016 年 10 月 1 日から 2016 年 10 月 8 日に発生したすべての移行の詳細が返されます。
  
```
Get-CsMeetingMigrationStatus -StartTime "10/1/2016" -EndTime "10/8/2016"
```

特定のユーザーに関する移行のステータスを確認することもできます。この場合は  `UserId` パラメーターを使用できます。たとえば、次のコマンドを実行すると、ユーザー ashaw@contoso.com に関するステータスが返されます。
  
```
Get-CsMeetingMigrationStatus -UserId "ashaw@contoso.com"
```

### <a name="what-do-i-do-if-there-is-an-error"></a>エラーが発生した場合の対処方法を教えてください。
<a name="Troubleshooting"> </a>

`Get-CsMeetingMigrationStatus` コマンドレットを実行して概要ビューを表示すると、状態が 失敗となっている移行が確認される場合があります。対処方法は次のとおりです。
  
1. 影響を受けているユーザーを特定します。次のコマンドを実行して、影響を受けているユーザーと、報告された特定のエラーのリストを取得します。
    
  ```
  Get-CsMeetingMigrationStatus | Where {$_.State -eq "Failed"} | Format-Table UserId,LastErrorMessage
  ```

2. これらのユーザーそれぞれに対して、[会議移行ツール](https://go.microsoft.com/fwlink/p/?linkid=626047)を実行して、手動で会議を移行します。
    
3. 会議移行ツールを使用しても移行が機能しない場合には、次の 2 つのオプションがあります。
    
  - ユーザーに新しい Skype 会議を作成してもらいます。
    
  - [サポートに問い合わせます](https://go.microsoft.com/fwlink/p/?LinkID=518322)。
    
### <a name="enabling-and-disabling-mms"></a>MMS の有効化と無効化
<a name="Troubleshooting"> </a>

MMS は既定ではすべての組織で有効になっていますが、必要に応じて無効にすることができます。たとえば、すべての会議を手動で移行する場合や、サードパーティ電話会議プロバイダーを使用する場合は、MMS の動作は必要ありません。また、MMS を一時的に無効にすることがあります。たとえば、組織の電話会議の設定に多数の変更を加える場合で、すべての変更作業が完了するまで MMS を動作させないようにするときがこれに該当します。
  
所属する組織で MMS が有効になっているかどうかを確認するには、次のコマンドを実行して、 `MeetingMigrationEnabled` パラメーターの値を確認します。このパラメーターが$true に設定されている場合、MMS が有効になっています。
  
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

### <a name="enabling-and-disabling-mms-only-for-audio-conferencing-changes"></a>電話会議の変更に対して限定した MMS の有効化と無効化
<a name="Troubleshooting"> </a>

電話会議の変更に対してのみ、MMS を無効にすることもできます。これは、ユーザーがオンプレミスの Skype for Business から Skype for Business Online に移行した場合でも引き続き実行されます。電話会議の更新に関する現在の MMS の状態を確認するには、次のコマンドを実行して、 `AutomaticallyMigrateUserMeetings` パラメーターの値を確認します。このパラメーターが$true に設定されている場合は、MMS は電話会議の設定が変更された場合にユーザー会議を更新するように設定されています。
  
```
Get-CsOnlineDialInConferencingTenantSettings
```

電話会議に関して MMS を無効にするには、次のコマンドを実行します。
  
```
Set-CsOnlineDialInConferencingTenantSettings -AutomaticallyMigrateUserMeetings $false
```

電話会議に関して MMS を有効にするには、次のコマンドを実行します。
  
```
Set-CsOnlineDialInConferencingTenantSettings  -AutomaticallyMigrateUserMeetings $true
```

### <a name="how-do-i-run-meeting-migration-manually-for-a-user"></a>ユーザーのために手動で会議移行を実行する方法を教えてください。
<a name="Troubleshooting"> </a>

自動的な会議移行の他に、コマンドレット **Start-CsExMeetingMigration** を実行することによって、ユーザーのために手動で会議移行を実行することもできます。このコマンドレットはユーザーを会議移行キューに追加します。Meeting Migration Service (MMS) はユーザー リクエストを読み取り、会議を移行します。コマンドレット **Get-CsMeetingMigrationStatus** で会議移行の状態を確認できます。
  
ユーザー ashaw@contoso.com のために会議移行を開始する場合の例を次に示します。
  
```
Start-CsExMeetingMigration -Identity ashaw@contoso.com
```

## <a name="using-powershell-to-manage-your-skype-for-business-organization"></a>PowerShell を使用した Skype for Business の組織の管理
<a name="WPSInfo"> </a>

 **Windows PowerShell バージョン 3.0 以降を実行していることを確認する**
  
1. To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.
    
2. [ _Windows PowerShell_] ウィンドウに「 **Get-Host**」と入力して、バージョンを確認します。
    
3. バージョン 3.0 以降を使用していない場合は、Windows PowerShell の更新プログラムをダウンロードおよびインストールする必要があります。Windows PowerShell をダウンロードして、バージョン 4.0 に更新するには、「[Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845)」を参照してください。メッセージが表示されたら、コンピューターを再起動します。
    
4. Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成できるように、Skype for Business Online の Windows PowerShell モジュールもインストールする必要があります。このモジュールは、64 ビット版のコンピューターでのみサポートされており、「[Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688)」の Microsoft ダウンロード センターからダウンロードできます。メッセージが表示されたら、コンピューターを再起動します。
    
詳細については、「[単一の Windows PowerShell ウィンドウですべての Office 365 サービスに接続する](https://technet.microsoft.com/EN-US/library/dn568015.aspx)」を参照してください。
  
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
Windows PowerShell の起動の詳細については、「[単一の Windows PowerShell ウィンドウですべての Office 365 サービスに接続する](https://technet.microsoft.com/EN-US/library/dn568015.aspx)」または「[Windows PowerShell を使用した Lync Online への接続](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx)」を参照してください。
  
- Windows PowerShell で行うのは、ユーザーを管理し、ユーザーに何を許可して何を禁止するかを管理することです。Windows PowerShell を利用すると、Office 365 と Skype for Business Online の管理を 1 か所で行うことができるので、複数のタスクを担当する管理者の日常業務を単純化できます。Windows PowerShell の使用を開始するには、次のトピックを参照してください。
    
  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell には、ただ Office 365 管理センターを使用するだけではなく、速度、単純さ、生産性において多くの利点があります。次のトピックでこれらの利点について説明します。
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Windows PowerShell による Skype for Business Online の管理](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [クイック リファレンス: Windows PowerShell を使用した一般的な Lync Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>See also

[Office 365 での電話会議を使用または購入する](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
