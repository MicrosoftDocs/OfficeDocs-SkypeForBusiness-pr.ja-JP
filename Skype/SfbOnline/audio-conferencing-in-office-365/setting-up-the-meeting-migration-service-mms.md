---
title: Meeting Migration Service (MMS) の使用
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 031f09c0-9d2a-487a-b6db-b5d4bed6d16a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 会議移行サービス (MMS) は、バックグラウンドで実行されるサービスで、Skype for Business および Microsoft Teams の会議を自動的に更新します。 MMS はユーザーが会議移行ツールを実行して Skype for Business および Microsoft Teams 会議を更新しなくても済むように設計されています。
ms.openlocfilehash: 9223102ef9c264fdafdb9f52ec74d6edb383f987
ms.sourcegitcommit: 67c686810d37bffda72a6e92155d9c8ec86bfae6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "47765349"
---
# <a name="using-the-meeting-migration-service-mms"></a>Meeting Migration Service (MMS) の使用

会議移行サービス (MMS) は、次のシナリオでユーザーの既存の会議を更新するサービスです。

- ユーザーがオンプレミスからクラウドに移行される場合 (Skype for Business Online か、または teams のみ)。
- 管理者がユーザーの電話会議設定に変更を加えた場合 
- オンラインユーザーが Teams のみにアップグレードされた場合、または TeamsUpgradePolicy のユーザーのモードが SfBwithTeamsCollabAndMeetings に設定されている場合
- PowerShell を使用する場合 


既定では、これらの場合、MMS は各ケースで自動的にトリガーされますが、管理者はテナントレベルで無効にすることができます。 さらに、管理者は PowerShell コマンドレットを使って、特定のユーザーの会議の移行を手動でトリガーすることもできます。


**制限**: 次のいずれかが該当する場合、会議移行サービスは使用できません。

- ユーザーのメールボックスは、オンプレミスの Exchange でホストされています。
- ユーザーはクラウドから Skype for Business Server のオンプレミスに移行されています。

このような場合、エンドユーザーは [会議移行ツール](https://www.microsoft.com/download/details.aspx?id=51659) を使用して、代わりに自分の会議を移行することができます。

## <a name="how-mms-works"></a>MMS のしくみ

特定のユーザーに対して MMS がトリガーされると、そのユーザーへの移行要求がキューに格納されます。 競合状態を回避するために、キュー要求は、少なくとも90分が経過するまで処理されません。 MMS は、要求を処理すると、次のタスクを実行します。

1. ユーザーのメールボックスが、そのユーザーによって開催され、今後スケジュールされているすべての既存の会議に対して検索されます。
2. ユーザーのメールボックスに記載されている情報に基づいて、そのユーザーのチームまたは Skype for Business Online の新しい会議を更新またはスケジュールします。
3. メールメッセージで、会議の詳細のオンライン会議ブロックを置き換えます。
4. その会議の更新されたバージョンは、会議の開催者の代理としてすべての会議の受信者に送信されます。 会議の出席者は、更新された会議の座標をメールで受け取ります。 

    ![MMS で更新される会議ブロック。](../images/210a03ee-30c1-46f3-808f-4c2ebdaa3ea1.png)

MMS がトリガーされた時点では、通常、ユーザーの会議が移行されるまでに約2時間かかります。 ただし、ユーザーの会議数が多い場合は、時間がかかることがあります。 MMS でユーザーの会議の移行中にエラーが発生した場合、24時間の間に、定期的に最大9回再試行されます。

**注**:

- MMS は会議が移行されるときにオンライン会議の情報ブロックのすべてを置き換えます。 このため、ユーザーがそのブロックを編集した場合は、それらの変更は上書きされます。 オンライン会議の情報ブロック以外の会議の詳細に含まれているコンテンツは影響しません。 つまり、会議の出席依頼に添付されたファイルは、すべて含まれています。 
- Outlook on the Web で [ **Skype 会議の追加**] ボタンをクリックして、または Outlook 用の Skype 会議アドインを使用してスケジュールされた Skype for Business 会議および Microsoft Teams 会議のみが移行されます。 ある会議から新しい会議に Skype オンライン会議の情報をコピーして貼り付けると、元のサービスに会議がないため、新しい会議は更新されません。
- 会議に作成または添付された会議コンテンツ (ホワイトボード、投票など) は、MMS の実行後も保持されません。 会議の開催者が事前にコンテンツを会議に添付している場合、そのコンテンツは MMS の動作後に再作成する必要があります。
- 予定表の項目内、および Skype 会議からの共有の会議ノートへのリンクも上書きされます。 OneNote に保存されている実際の会議ノートはそのまま残ります。これは、上書きされた共有ノートへのリンクにすぎません。
- (開催者を含めて) 250 人を超える参加者がいる会議は移行できません。
- 招待状の本文に含まれる一部の UNICODE 文字が誤って、ï、¿、1/2、のいずれかの特殊文字に更新されている可能性があります。

## <a name="triggering-mms-for-a-user"></a>ユーザー向けの MMS のトリガー

このセクションでは、次のいずれかの場合に MMS がトリガーされた場合の動作について説明します。

- ユーザーがオンプレミスからクラウドに移行される場合
- 管理者がユーザーの電話会議設定に変更を加えた場合 
- TeamsUpgradePolicy でユーザーのモードが TeamsOnly または SfBWithTeamsCollabAndMeetings (Powershell または Teams 管理ポータルを使って) に設定されている場合
- PowerShell コマンドレットを使用する場合は、スタート-Csexmigration の移行

### <a name="updating-meetings-when-you-move-an-on-premises-user-to-the-cloud"></a>オンプレミスユーザーをクラウドに移行したときの会議の更新

これは、MMS がユーザーにより円滑な切り替えを作成できる最も一般的なシナリオです。 会議の移行を行わなければ、オンプレミスの Skype for Business Server のユーザーによって開催された既存の会議は、ユーザーがオンラインに移行した後は機能しなくなります。 そのため、オンプレミスの管理ツール ( `Move-CsUser` または [管理者] コントロールパネル) を使用してユーザーをクラウドに移動すると、既存の会議は次のように自動的にクラウドに移動されます。

- `MoveToTeams`スイッチが指定されている場合 `Move-CsUser` 、会議はチームに直接移行され、ユーザーは Teams の唯一のモードになります。 このスイッチを使用するには、CU8 以降の Skype for Business Server 2015 が必要です。 これらのユーザーは、skype for business クライアントまたは Skype 会議アプリを使用して、招待されている可能性のある Skype for Business 会議に引き続き参加できます。
- それ以外の場合、会議は Skype for Business Online に移行されます。

どちらの場合も、ユーザーに電話会議ライセンスが割り当てられてからクラウドに移動された場合、会議はダイヤルイン座標で作成されます。 ユーザーをオンプレミスからクラウドに移動し、そのユーザーが電話会議を使用するようにする場合は、最初に電話会議を割り当てることをお勧めします。これにより、1つの会議の移行のみが開始されるようになります。


### <a name="updating-meetings-when-a-users-audio-conferencing-settings-change"></a>ユーザーの電話会議の設定が変更されるときの会議の更新

次のような場合、MMS は既存の Skype for Business および Microsoft Teams の会議を更新して、ダイヤルインの調整を追加、削除、または変更します。

- Microsoft 電話会議サービスライセンスをユーザーに割り当てたり、削除したりする場合、そのユーザーはサードパーティの電話会議プロバイダーに対して有効になっていません。
- ユーザーの電話会議プロバイダーを他のプロバイダーから Microsoft に変更すると、そのユーザーに Microsoft 電話会議ライセンスが割り当てられます。 詳細については、「 [Microsoft を電話会議プロバイダーとして割り当てる](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider)」を参照してください。 また、サードパーティの電話会議プロバイダー (ACP) のサポートは、 [前に発表](https://docs.microsoft.com/skypeforbusiness/legal-and-regulatory/end-of-integration-with-3rd-party-providers)した2019年4月1日に終了する予定です。
- ユーザーの電話会議を有効または無効にする場合。
- パブリック会議を使用するように構成されたユーザーの会議 ID を変更またはリセットする場合。
- ユーザーを新しい電話会議ブリッジに移行する場合
- 電話会議ブリッジの電話番号が割り当てられていない場合。 これは、追加の手順が必要な複雑なシナリオです。 詳細については、「 [電話会議ブリッジの電話番号を変更](https://docs.microsoft.com/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge)する」を参照してください。

ユーザーの電話会議の設定に対する変更の一部は、MMS をトリガーしません。特に、次の 2 つの変更では、MMS によって会議が更新されません。

- 会議の開催者の SIP アドレスを変更する場合 (SIP ユーザー名または SIP ドメインのいずれか)
- コマンドを使用して組織の会議 URL を変更した場合 `Update-CsTenantMeetingUrl` 。


### <a name="updating-meetings-when-assigning-teamsupgradepolicy"></a>TeamsUpgradePolicy を割り当てたときの会議の更新

既定では、ユーザーに with またはのインスタンスが付与されると、会議の移行が自動的にトリガーされ `TeamsUpgradePolicy` `mode=TeamsOnly` `mode= SfBWithTeamsCollabAndMeetings` ます。 これらのモードのいずれかを使用して会議を移行したくない場合は、 `MigrateMeetingsToTeams $false` `Grant-CsTeamsUpgradePolicy` (PowerShell を使用する場合) を指定するか、ユーザーの共存モード (Teams 管理ポータルを使用している場合) を設定するときに [会議を移行する] チェックボックスをオフにします。

次の点にも注意してください。

- 会議の移行は `TeamsUpgradePolicy` 、特定のユーザーに付与した場合にのみ呼び出されます。 テナント全体に対して付与した場合 `TeamsUpgradePolicy` `mode=TeamsOnly` `mode=SfBWithTeamsCollabAndMeetings` 、会議の移行は呼び出されません。 *tenant-wide*
- ユーザーは、ユーザーがオンラインになっている場合にのみ、teams Sonly モードを許可されます。 ホームオンプレミスのユーザーは、前の説明に従って移動する必要があり `Move-CsUser` ます。
- TeamsOnly または SfBWithTeamsCollabAndMeetings 以外のモードを付与しても、既存の Teams 会議を Skype for Business 会議に変換することはできません。

### <a name="trigger-meeting-migration-manually-via-powershell-cmdlet"></a>PowerShell コマンドレットを使用して手動で会議移行を開始する

自動会議の移行に加えて、管理者は、コマンドレットを実行することで、ユーザーの会議の移行を手動でトリガーすることができ `Start-CsExMeetingMigration` ます。 このコマンドレットは、指定したユーザーの移行要求をキューに出します。  必須のパラメーターに加えて、次の2つのパラメーターを指定する必要があります。これに `Identity` `SourceMeetingType` `TargetMeetingType` より、会議の移行方法を指定することができます。

**Target会議の種類:**

- を使用 `TargetMeetingType Current` すると、skype For business 会議は skype For business 会議のままであり、teams 会議も teams 会議のままになります。 ただし、電話会議の座標が変更され、オンプレミスの Skype for Business 会議が Skype for Business Online に移行される場合があります。 これは、Target会議の種類の既定値です。
- [使用] では、 `TargetMeetingType Teams` 会議が Skype For business online とオンプレミスのどちらでホストされているかにかかわらず、どの電話会議の更新が必要かに関係なく、既存の会議を Teams に移行する必要があることを指定します。 

**SourceMeetingType:**
- [使用] は、 `SourceMeetingType SfB` Skype For business 会議 (オンプレミスまたはオンライン) のみを更新する必要があることを示します。
- `SourceMeetingType Teams`は、Teams 会議のみを更新する必要があることを示します。
- [使用] は `SourceMeetingType All` 、Skype For business 会議と Teams 会議の両方を更新する必要があることを示します。 これは、SourceMeetingType の既定値です。
    

次の例は、ユーザー ashaw@contoso.com の会議の移行を開始して、すべての会議を Teams に移行できるようにする方法を示しています。

```PowerShell
Start-CsExMeetingMigration -Identity ashaw@contoso.com -TargetMeetingType Teams
```



## <a name="managing-mms"></a>MMS の管理

Windows PowerShell を使用すると、進行中の移行の状態を確認し、会議の移行を手動でトリガーして、移行を完全に無効にすることができます。 

### <a name="check-the-status-of-meeting-migrations"></a>会議の移行の状態を確認する

このコマンドレットを使用して、 `Get-CsMeetingMigrationStatus` 会議の移行の状態を確認します。 次に例を示します。

- すべての MMS の移行の概要ステータスを取得するには、次のコマンドを実行して、すべての移行状態を示す表形式のビューを提供します。

    ```PowerShell
    Get-CsMeetingMigrationStatus -SummaryOnly

    State      UserCount
    ------     ---------
    Pending      21
    InProgress    6
    Failed            2 
    Succeeded   131
    ```
- 指定した期間内のすべての移行の詳細情報を取得するには、and パラメーターを使用し `StartTime` `EndTime` ます。 たとえば、次のコマンドは、2018年10月1日から2018年10月8日までに発生したすべての移行に関する完全な詳細情報を返します。

    ```PowerShell
    Get-CsMeetingMigrationStatus -StartTime "10/1/2018" -EndTime "10/8/2018"
    ```
- 特定のユーザーの移行の状態を確認するには、パラメーターを使用し `Identity` ます。 たとえば、次のコマンドは、ユーザー ashaw@contoso.com の状態を返します。

    ```PowerShell
    Get-CsMeetingMigrationStatus -Identity ashaw@contoso.com
    ```
失敗した移行が表示される場合は、問題を解決するまで、ユーザーが開催した会議にダイヤルインできないため、できるだけ早くこの問題を解決する必要があります。 失敗状態の移行が表示された場合は `Get-CsMeetingMigrationStatus` 、次の手順を実行します。
 
1. 影響を受けているユーザーを特定します。 次のコマンドを実行して、影響を受けているユーザーと、報告された特定のエラーのリストを取得します。

    ```PowerShell
    Get-CsMeetingMigrationStatus| Where {$_.State -eq "Failed"}| Format-Table UserPrincipalName, LastMessage
    ```
2. 影響を受けるユーザーごとに、会議移行ツールを実行して、手動で会議を移行します。

3. 会議移行ツールを使用しても移行が機能しない場合には、次の 2 つのオプションがあります。

    - ユーザーに新しい Skype 会議を作成してもらいます。
    - [サポートに問い合わせます](https://go.microsoft.com/fwlink/p/?LinkID=518322)。


### <a name="enabling-and-disabling-mms"></a>MMS の有効化と無効化

MMS は、すべての組織に対して既定で有効になっていますが、次の方法で無効にすることができます。

- テナントに対して完全に無効にします。 
- 電話会議に関連する変更についてのみ無効にします。 この場合でも、ユーザーがオンプレミスからクラウドに移行された場合、またはで teams Sonly モードまたは SfBWithTeamsCollabAndMeetings モードを許可している場合は、MMS が実行され `TeamsUpgradePolicy` ます。

たとえば、組織の電話会議の設定に大幅な変更を加えながら、すべての会議を手動で移行するか、または MMS を一時的に無効にすることができます。

組織で MMS が有効になっているかどうかを確認するには、次のコマンドを実行します。 パラメーターがの場合は、MMS が有効になり `MeetingMigrationEnabled` `$true` ます。
```PowerShell
Get-CsTenantMigrationConfiguration
```
MMS を有効または無効にするには、コマンドを使用し `Set-CsTenantMigrationConfiguration` ます。 たとえば、MMS を無効にするには、次のコマンドを実行します。

```PowerShell
Set-CsTenantMigrationConfiguration -MeetingMigrationEnabled $false
```
組織で MMS が有効になっていて、電話会議の更新プログラムが有効になっているかどうかを確認する場合は、[出力元] のパラメーターの値を確認し `AutomaticallyMigrateUserMeetings` `Get-CsOnlineDialInConferencingTenantSettings` ます。 電話会議の MMS を有効または無効にするには、を使用 `Set-CsOnlineDialInConferencingTenantSettings` します。 たとえば、電話会議の MMS を無効にするには、次のコマンドを実行します。

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings  -AutomaticallyMigrateUserMeetings $false
```

## <a name="related-topics"></a>関連トピック

[Microsoft 365 または Office 365 で電話会議を試用または購入する](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

[オンプレミスとクラウドの間でユーザーを移動する](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)
