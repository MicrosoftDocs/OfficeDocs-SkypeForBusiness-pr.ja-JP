---
title: 会議移行サービス (MMS) を使用する
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
description: Meeting Migration Service (MMS) は、バックグラウンドで実行され、ユーザーの Skype for Business 会議と Microsoft Teams 会議を自動的に更新するサービスです。 MMS はユーザーが会議移行ツールを実行して Skype for Business および Microsoft Teams 会議を更新しなくても済むように設計されています。
ms.openlocfilehash: 18a36425e842e0c24c5cf6c2837535043e7967a8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51111953"
---
# <a name="using-the-meeting-migration-service-mms"></a>会議移行サービス (MMS) を使用する

Meeting Migration Service (MMS) は、次のシナリオでユーザーの既存の会議を更新するサービスです。

- ユーザーがオンプレミスからクラウドに移行される場合 (Skype for Business Online または TeamsOnly に移行する場合)。
- 管理者がユーザーの電話会議設定を変更した場合 
- オンライン ユーザーが Teams にのみアップグレードされた場合、または TeamsUpgradePolicy のユーザー モードが SfBwithTeamsCollabAndMeetings に設定されている場合
- PowerShell を使用する場合 


既定では、MMS は各ケースで自動的にトリガーされます。ただし、管理者はテナント レベルで無効にできます。 さらに、管理者は PowerShell コマンドレットを使用して、指定したユーザーの会議の移行を手動でトリガーできます。


**制限事項**: 次の条件が適用される場合、会議移行サービスを使用できません。

- ユーザーのメールボックスは、Exchange オンプレミスでホストされます。
- ユーザーはクラウドからオンプレミスの Skype for Business Server に移行されています。

このような場合、エンド ユーザーは会議移行ツールを [使用して、](https://www.microsoft.com/download/details.aspx?id=51659) 代わりに自分の会議を移行できます。

## <a name="how-mms-works"></a>MMS のしくみ

特定のユーザーに対して MMS がトリガーされると、そのユーザーに対する移行要求がキューに配置されます。 レース状態を回避するために、キューに入った要求は、少なくとも 90 分が過ぎるまで意図的に処理されません。 MMS が要求を処理すると、次のタスクが実行されます。

1. そのユーザーのメールボックスを検索し、そのユーザーが開催し、将来スケジュールされた既存のすべての会議を検索します。
2. ユーザーのメールボックスで見つかった情報に基づいて、正確なシナリオに応じて、そのユーザーの Teams または Skype for Business Online で新しい会議を更新またはスケジュールします。
3. メール メッセージでは、会議の詳細のオンライン会議ブロックが置き換されます。
4. 更新されたバージョンの会議が、会議の開催者の代わりにすべての会議の受信者に送信されます。 会議の招待者は、更新された会議の調整をメールに含む会議の更新を受信します。 

    ![MMS で更新される会議ブロック。](../images/210a03ee-30c1-46f3-808f-4c2ebdaa3ea1.png)

MMS がトリガーされるまで、通常、ユーザーの会議が移行されるまでに約 2 時間かかります。 ただし、ユーザーの会議の数が多い場合は、時間がかかる場合があります。 MMS でユーザーの 1 つ以上の会議の移行でエラーが発生した場合は、24 時間の間に最大 9 回、定期的に再試行されます。

**注**:

- MMS は会議が移行されるときにオンライン会議の情報ブロックのすべてを置き換えます。 このため、ユーザーがそのブロックを編集した場合は、それらの変更は上書きされます。 オンライン会議の情報ブロック以外の会議の詳細に含まれているコンテンツは影響しません。 つまり、会議出席招待に添付されているファイルは引き続き含まれます。 
- Outlook on the Web で [ **Skype 会議の追加**] ボタンをクリックして、または Outlook 用の Skype 会議アドインを使用してスケジュールされた Skype for Business 会議および Microsoft Teams 会議のみが移行されます。 ユーザーが Skype オンライン会議の情報をコピーして、1 つの会議から新しい会議に貼り付ける場合、元のサービスに会議が存在しなた場合、その新しい会議は更新されません。
- 作成または会議に添付された会議コンテンツ (ホワイトボード、投票など) は、MMS の実行後も保持されません。 会議の開催者が事前にコンテンツを会議に添付している場合、そのコンテンツは MMS の動作後に再作成する必要があります。
- 予定表の項目内、および Skype 会議からの共有の会議ノートへのリンクも上書きされます。 OneNote に保存されている実際の会議ノートは引き続き保存されます。上書きされるのは共有ノートへのリンクのみです。
- (開催者を含めて) 250 人を超える参加者がいる会議は移行できません。
- 招待の本文の UNICODE 文字の一部が、ï、ï、1/2、.

## <a name="triggering-mms-for-a-user"></a>ユーザーの MMS のトリガー

このセクションでは、次の各ケースで MMS がトリガーされた場合の動作について説明します。

- ユーザーがオンプレミスからクラウドに移行される場合
- 管理者がユーザーの電話会議設定を変更した場合 
- TeamsUpgradePolicy でユーザーのモードが TeamsOnly または SfBWithTeamsCollabAndMeetings に設定されている場合 (Powershell または Teams 管理ポータルを使用)
- PowerShell コマンドレットを使用する場合はStart-CsExMeetingMigration

### <a name="updating-meetings-when-you-move-an-on-premises-user-to-the-cloud"></a>オンプレミス ユーザーをクラウドに移動するときに会議を更新する

これは、MMS がユーザーのスムーズな移行を作成するのに役立つ最も一般的なシナリオです。 会議の移行がない場合、ユーザーがオンラインに移行すると、オンプレミスの Skype for Business Server でユーザーが開催した既存の会議は機能しなくなりました。 そのため、オンプレミスの管理ツール (または管理者コントロール パネル) を使用してユーザーをクラウドに移動すると、既存の会議は次のように自動的にクラウド `Move-CsUser` に移動されます。

- 切 `MoveToTeams` り替えの設定が指定されている場合、会議は Teams に直接移行され、ユーザーは `Move-CsUser` TeamsOnly モードになります。 このスイッチを使用するには、CU8 以降の Skype for Business Server 2015 が必要です。 これらのユーザーは、Skype for Business クライアントまたは Skype 会議アプリを使用して、招待される可能性がある Skype for Business 会議に引き続き参加できます。
- それ以外の場合、会議は Skype for Business Online に移行されます。

いずれの場合も、クラウドに移動する前にユーザーに電話会議ライセンスが割り当てられている場合、会議はダイヤルイン座標で作成されます。 ユーザーをオンプレミスからクラウドに移行し、そのユーザーが電話会議を使用する場合は、まず電話会議を割り当てしてからユーザーを移動し、1 回の会議移行のみをトリガーすることをお勧めします。


### <a name="updating-meetings-when-a-users-audio-conferencing-settings-change"></a>ユーザーの電話会議の設定が変更されるときの会議の更新

次の場合、MMS は既存の Skype for Business 会議と Microsoft Teams 会議を更新して、ダイヤルイン座標を追加、削除、または変更します。

- Microsoft 電話会議サービス のライセンスをユーザーに割り当てまたは削除した場合、そのユーザーがサードパーティの電話会議プロバイダーに対して有効になっていない。
- ユーザーの電話会議プロバイダーを他のプロバイダーから Microsoft に変更する場合 (ユーザーに Microsoft 電話会議ライセンスが割り当てられている場合)。 詳細については、「Microsoft を電話会議 [プロバイダーとして割り当てる」を参照してください](./assign-microsoft-as-the-audio-conferencing-provider.md)。 また、サードパーティ電話会議プロバイダー (ACP) のサポートは、前に発表された 2019 年 4 月 1 日にサポートが終了する予定[です。](../legal-and-regulatory/end-of-integration-with-3rd-party-providers.md)
- ユーザーの電話会議を有効または無効にする場合。
- パブリック会議を使用するように構成されたユーザーの会議 ID を変更またはリセットする場合。
- ユーザーを新しい電話会議ブリッジに移行する場合
- 電話会議ブリッジからの電話番号が割り当てられていない場合。 これは、追加の手順が必要な複雑なシナリオです。 詳細については、「電話会議 [ブリッジの電話番号を変更する」を参照してください](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge)。

ユーザーの電話会議の設定に対する変更の一部は、MMS をトリガーしません。特に、次の 2 つの変更では、MMS によって会議が更新されません。

- 会議の開催者の SIP アドレスを変更する場合 (SIP ユーザー名または SIP ドメインのいずれか)
- コマンドを使用して組織の会議 URL を変更 `Update-CsTenantMeetingUrl` する場合。


### <a name="updating-meetings-when-assigning-teamsupgradepolicy"></a>TeamsUpgradePolicy を割り当てるときに会議を更新する

既定では、ユーザーに次のインスタンスが付与されると、会議の移行が自動的に `TeamsUpgradePolicy` `mode=TeamsOnly` トリガーされます `mode= SfBWithTeamsCollabAndMeetings` 。 これらのモードのいずれかを付与するときに会議を移行しない場合は、(PowerShell を使用している場合) で指定するか、ユーザーの共存モードを設定するときに会議を移行するボックス `MigrateMeetingsToTeams $false` をオフにします (Teams 管理ポータルを使用している場合 `Grant-CsTeamsUpgradePolicy` )。

また、次の点に注意してください。

- 会議の移行は、特定のユーザーに付与した `TeamsUpgradePolicy` 場合にのみ呼び出されます。 テナント全体で付与した場合、またはテナント全体で付与した場合 `TeamsUpgradePolicy` `mode=TeamsOnly` `mode=SfBWithTeamsCollabAndMeetings` 、会議の移行は呼び出されません。 
- ユーザーが TeamsOnly モードを付与できるのは、ユーザーがオンラインで自宅にいる場合のみです。 オンプレミスに自宅を持つユーザーは、前に説明したように移動 `Move-CsUser` する必要があります。
- TeamsOnly または SfBWithTeamsCollabAndMeetings 以外のモードを付与しても、既存の Teams 会議は Skype for Business 会議に変換されません。

### <a name="trigger-meeting-migration-manually-via-powershell-cmdlet"></a>PowerShell コマンドレットを使用して手動で会議移行をトリガーする

管理者は、会議の自動移行に加えて、コマンドレットを実行してユーザーの会議の移行を手動でトリガーできます `Start-CsExMeetingMigration` 。 このコマンドレットは、指定したユーザーの移行要求をキューに入れします。  必須のパラメーターに加えて、2 つのオプションのパラメーターを受け取り、会議の移行 `Identity` `SourceMeetingType` `TargetMeetingType` 方法を指定できます。

**TargetMeetingType:**

- 使用 `TargetMeetingType Current` すると、Skype for Business 会議は Skype for Business 会議のままで、Teams 会議は Teams 会議のままです。 ただし、電話会議の調整が変更され、オンプレミスの Skype for Business 会議は Skype for Business Online に移行されます。 これは TargetMeetingType の既定値です。
- 会議が Skype for Business Online またはオンプレミスでホストされているかどうか、および電話会議の更新が必要かどうかに関係なく、既存の会議を Teams に移行する必要があるという指定を使用します。 `TargetMeetingType Teams` 

**SourceMeetingType:**
- 使用すると、Skype for Business 会議 (オンプレミスかオンラインか) のみを更新 `SourceMeetingType SfB` する必要があります。
- 使用 `SourceMeetingType Teams` すると、Teams 会議のみを更新する必要があります。
- 使用 `SourceMeetingType All` すると、Skype for Business 会議と Teams 会議の両方を更新する必要があります。 これは SourceMeetingType の既定値です。
    

次の例は、すべての会議が Teams に移行されるユーザー ashaw@contoso.com 会議の移行を開始する方法を示しています。

```PowerShell
Start-CsExMeetingMigration -Identity ashaw@contoso.com -TargetMeetingType Teams
```



## <a name="managing-mms"></a>MMS の管理

このWindows PowerShell、進行中の移行の状態を確認し、会議の移行を手動でトリガーし、移行を完全に無効にすることができます。 

### <a name="check-the-status-of-meeting-migrations"></a>会議の移行の状態を確認する

コマンドレットを使用 `Get-CsMeetingMigrationStatus` して、会議の移行の状態を確認します。 次に例を示します。

- すべての MMS 移行の概要ステータスを取得するには、次のコマンドを実行して、すべての移行状態を表形式で表示します。

    ```PowerShell
    Get-CsMeetingMigrationStatus -SummaryOnly

    State      UserCount
    ------     ---------
    Pending      21
    InProgress    6
    Failed            2 
    Succeeded   131
    ```
- 特定の期間内のすべての移行の詳細を取得するには、パラメーター `StartTime` を使用 `EndTime` します。 たとえば、次のコマンドは、2018 年 10 月 1 日から 2018 年 10 月 8 日に発生したすべての移行の詳細を返します。

    ```PowerShell
    Get-CsMeetingMigrationStatus -StartTime "10/1/2018" -EndTime "10/8/2018"
    ```
- 特定のユーザーの移行の状態を確認するには、パラメーターを使用 `Identity` します。 たとえば、次のコマンドを実行すると、そのユーザーの状態が返 ashaw@contoso.com。

    ```PowerShell
    Get-CsMeetingMigrationStatus -Identity ashaw@contoso.com
    ```
移行に失敗した場合は、ユーザーが解決するまで、それらのユーザーが開催した会議にダイヤルインできないので、これらの問題をできるだけ早く解決するアクションを実行します。 失敗 `Get-CsMeetingMigrationStatus` した状態で移行が表示された場合は、次の手順を実行します。
 
1. 影響を受けているユーザーを特定します。 次のコマンドを実行して、影響を受けているユーザーと、報告された特定のエラーのリストを取得します。

    ```PowerShell
    Get-CsMeetingMigrationStatus| Where {$_.State -eq "Failed"}| Format-Table UserPrincipalName, LastMessage
    ```
2. 影響を受ける各ユーザーについて、会議移行ツールを実行して、手動で会議を移行します。

3. 会議移行ツールを使用しても移行が機能しない場合には、次の 2 つのオプションがあります。

    - ユーザーに新しい Skype 会議を作成してもらいます。
    - [サポートに問い合わせます](/microsoft-365/Admin/contact-support-for-business-products)。


### <a name="enabling-and-disabling-mms"></a>MMS の有効化と無効化

MMS は、すべての組織で既定で有効になっていますが、次のように無効にすることができます。

- テナントに対して完全に無効にします。 
- 電話会議に関連する変更の場合のみ無効にします。 この場合、ユーザーがオンプレミスからクラウドに移行された場合、または TeamsOnly モードまたは SfBWithTeamsCollabAndMeetings モードを付与した場合、MMS は引き続き実行されます。 `TeamsUpgradePolicy`

たとえば、組織の電話会議設定を大幅に変更しながら、すべての会議を手動で移行したり、MMS を一時的に無効にしたりしたい場合があります。

組織で MMS が有効になっているか確認するには、次のコマンドを実行します。 MMS は、パラメーターが有効 `MeetingMigrationEnabled` な場合に有効になります `$true` 。
```PowerShell
Get-CsTenantMigrationConfiguration
```
MMS 全体を有効または無効にするには、コマンドを使用 `Set-CsTenantMigrationConfiguration` します。 たとえば、MMS を無効にするには、次のコマンドを実行します。

```PowerShell
Set-CsTenantMigrationConfiguration -MeetingMigrationEnabled $false
```
組織で MMS が有効であり、電話会議の更新が有効になっているか確認する場合は、出力のパラメーターの値 `AutomaticallyMigrateUserMeetings` を確認します `Get-CsOnlineDialInConferencingTenantSettings` 。 電話会議で MMS を有効または無効にするには、次を使用します `Set-CsOnlineDialInConferencingTenantSettings` 。 たとえば、電話会議で MMS を無効にするには、次のコマンドを実行します。

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings  -AutomaticallyMigrateUserMeetings $false
```

## <a name="related-topics"></a>関連項目

[Microsoft 365 または Office 365 で電話会議を試用または購入する](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

[オンプレミスとクラウドの間でユーザーを移動する](../../SfbHybrid/hybrid/move-users-between-on-premises-and-cloud.md)