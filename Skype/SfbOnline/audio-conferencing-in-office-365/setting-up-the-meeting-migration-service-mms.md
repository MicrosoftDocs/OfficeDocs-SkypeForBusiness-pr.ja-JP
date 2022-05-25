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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 会議移行サービス (MMS) は、バックグラウンドで実行され、ユーザーの会議のSkype for BusinessとMicrosoft Teamsを自動的に更新するサービスです。
ms.openlocfilehash: a7e917a5b579c60ff84c3e1a5e6468a28f75faff
ms.sourcegitcommit: c53c22069b1babce7a2364de631057ff501ca1c0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/25/2022
ms.locfileid: "65671643"
---
# <a name="using-the-meeting-migration-service-mms"></a>会議移行サービス (MMS) を使用する

会議移行サービス (MMS) は、次のシナリオでユーザーの既存の会議を更新するサービスです。

- ユーザーがオンプレミスからクラウドに移行されたとき。
- 管理者がユーザーの電話会議設定を変更する場合
- オンライン ユーザーがTeamsのみにアップグレードされたとき、または TeamsUpgradePolicy でユーザーのモードが SfBwithTeamsCollabAndMeetings に設定されている場合
- PowerShell を使用する場合

既定では、これらの各ケースで MMS が自動的にトリガーされます。 さらに、管理者は PowerShell コマンドレットを使用して、特定のユーザーの会議の移行を手動でトリガーできます。

**制限事項**: 会議移行サービスは、次のいずれかに該当する場合は使用できません。

- ユーザーのメールボックスは、オンプレミスのExchangeでホストされます。
- ユーザーはクラウドからオンプレミスSkype for Business Serverに移行されています。

## <a name="how-mms-works"></a>MMS のしくみ

特定のユーザーに対して MMS がトリガーされると、そのユーザーの移行要求がキューに配置されます。 競合状態を回避するために、キューに登録された要求は、少なくとも 90 分が経過するまで意図的に処理されません。 MMS によって要求が処理されると、次のタスクが実行されます。

1. そのユーザーが開催し、今後スケジュールされたすべての既存の会議について、そのユーザーのメールボックスを検索します。
2. ユーザーのメールボックスにある情報に基づいて、正確なシナリオに応じて、そのユーザーのTeamsで新しい会議を更新またはスケジュールします。
3. 電子メール メッセージでは、会議の詳細のオンライン会議ブロックが置き換えられます。
4. 会議の開催者に代わって、その会議の更新されたバージョンをすべての会議受信者に送信します。 会議出席依頼者は、更新された会議の座標をメールに含む会議の更新プログラムを受け取ります。

    ![MMS によって更新される会議ブロック。](../images/210a03ee-30c1-46f3-808f-4c2ebdaa3ea1.png)

MMS がトリガーされてから、通常、ユーザーの会議が移行されるまで約 2 時間かかります。 ただし、ユーザーが多数の会議を開催している場合は、時間がかかる場合があります。 MMS は、ユーザーの 1 つ以上の会議を移行中にエラーが発生した場合、24 時間にわたって最大 9 回まで定期的に再試行します。

**注**:

- MMS は会議が移行されるときにオンライン会議の情報ブロックのすべてを置き換えます。 このため、ユーザーがそのブロックを編集した場合は、それらの変更は上書きされます。 オンライン会議の情報ブロック以外の会議の詳細に含まれているコンテンツは影響しません。 つまり、会議出席依頼に添付されているファイルは引き続き含まれます。
- Outlook on the Web で [ **Skype 会議の追加**] ボタンをクリックして、または Outlook 用の Skype 会議アドインを使用してスケジュールされた Skype for Business 会議および Microsoft Teams 会議のみが移行されます。 ユーザーが 1 つの会議から新しい会議にSkypeオンライン会議情報をコピーして貼り付ける場合、元のサービスに会議がないため、その新しい会議は更新されません。
- 会議に作成またはアタッチされた会議コンテンツ (ホワイトボード、投票など) は、MMS の実行後も保持されません。 会議の開催者が事前にコンテンツを会議に添付している場合、そのコンテンツは MMS の動作後に再作成する必要があります。
- 予定表の項目内、および Skype 会議からの共有の会議ノートへのリンクも上書きされます。 OneNoteに格納されている実際の会議ノートは引き続き存在することに注意してください。上書きされるのは共有ノートへのリンクのみです。
- (開催者を含めて) 250 人を超える参加者がいる会議は移行できません。
- 招待の本文の一部の UNICODE 文字が、ï、¿、1/2、.

## <a name="triggering-mms-for-a-user"></a>ユーザーの MMS のトリガー

このセクションでは、次の各ケースで MMS がトリガーされた場合の動作について説明します。

- ユーザーがオンプレミスからクラウドに移行されたとき
- 管理者がユーザーの電話会議設定を変更する場合
- TeamsUpgradePolicy のユーザー モードが TeamsOnly または SfBWithTeamsCollabAndMeetings に設定されている場合 (Powershell または Teams 管理 ポータルを使用)
- PowerShell コマンドレットを使用する場合は、Start-CsExMeetingMigration

### <a name="updating-meetings-when-you-move-an-on-premises-user-to-the-cloud"></a>オンプレミス ユーザーをクラウドに移動するときの会議の更新

これは、MMS がユーザーのスムーズな移行を作成するのに役立つ最も一般的なシナリオです。 会議の移行を行わなければ、ユーザーがオンラインに移行されると、オンプレミスのユーザーが組織Skype for Business Server既存の会議は機能しなくなります。 そのため、オンプレミスの管理ツール (`Move-CsUser`または管理 コントロール パネル) を使用してユーザーをクラウドに移動すると、既存の会議は自動的にクラウドに移動され、TeamsOnly に変換されます。

クラウドに移動する前にユーザーに電話会議ライセンスが割り当てられている場合は、ダイヤルイン座標を使用して会議が作成されます。 オンプレミスからクラウドにユーザーを移動し、そのユーザーが電話会議を使用する場合は、ユーザーを移動する前に最初に電話会議を割り当てて、会議の移行が 1 つだけトリガーされるようにすることをお勧めします。

### <a name="updating-meetings-when-a-users-audio-conferencing-settings-change"></a>ユーザーの電話会議の設定が変更されるときの会議の更新

次の場合、MMS は既存のSkype for BusinessとMicrosoft Teams会議を更新して、ダイヤルイン座標を追加、削除、または変更します。

- Microsoft 電話会議 サービス ライセンスをユーザーに割り当てたり削除したりしたときに、そのユーザーがサード パーティの電話会議プロバイダーに対して有効になっていない場合。
- ユーザーの電話会議プロバイダーを他のプロバイダーから Microsoft に変更する場合、ユーザーに Microsoft 電話会議 ライセンスが割り当てられている場合。 詳細については、「Microsoft を [電話会議プロバイダーとして割り当てる」を](./assign-microsoft-as-the-audio-conferencing-provider.md)参照してください。 また、サード パーティの電話会議プロバイダー [ACP] のサポートは、 [前に発表したように](../legal-and-regulatory/end-of-integration-with-3rd-party-providers.md)、2019 年 4 月 1 日に終了する予定であることにも注意してください。
- ユーザーの電話会議を有効または無効にする場合。
- パブリック会議を使用するように構成されたユーザーの会議 ID を変更またはリセットする場合。
- ユーザーを新しい電話会議ブリッジに移行する場合
- 電話会議ブリッジの電話番号が割り当てられていない場合。 これは、追加の手順が必要な複雑なシナリオです。 詳細については、「 [電話会議ブリッジの電話番号を変更する」を参照してください](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge)。

ユーザーの電話会議の設定に対する変更の一部は、MMS をトリガーしません。 特に、次の 2 つの変更では、MMS によって会議が更新されません。

- 会議の開催者の SIP アドレスを変更する場合 (SIP ユーザー名または SIP ドメインのいずれか)
- コマンドを使用して `Update-CsTenantMeetingUrl` 組織の会議 URL を変更する場合。

### <a name="updating-meetings-when-assigning-teamsupgradepolicy"></a>TeamsUpgradePolicy を割り当てるときに会議を更新する

既定では、会議の移行は、ユーザー `TeamsUpgradePolicy` `mode=TeamsOnly` に with または `mode= SfBWithTeamsCollabAndMeetings`. これらのモードのいずれかを付与するときに会議を移行しない場合は、(PowerShell を使用している場合) を指定`MigrateMeetingsToTeams $false` `Grant-CsTeamsUpgradePolicy` するか、ボックスをオフにして、ユーザーの共存モードを設定するときに会議を移行します (Teams管理ポータルを使用している場合)。

また、次の点にも注意してください。

- 会議の移行は、特定のユーザーに付与 `TeamsUpgradePolicy` した場合にのみ呼び出されます。 *テナント全体* で`mode=TeamsOnly`許可する場合、または`mode=SfBWithTeamsCollabAndMeetings`テナント全体で付与`TeamsUpgradePolicy`する場合、会議の移行は呼び出されません。
- ユーザーに TeamsOnly モードを付与できるのは、ユーザーがオンラインでホームになっている場合のみです。 オンプレミスに所属しているユーザーは、前述のように移動 `Move-CsUser` する必要があります。
- TeamsOnly または SfBWithTeamsCollabAndMeetings 以外のモードを付与しても、既存のTeams会議はSkype for Business会議に変換されません。

### <a name="trigger-meeting-migration-manually-via-powershell-cmdlet"></a>PowerShell コマンドレットを使用して会議の移行を手動でトリガーする

管理者は、会議の自動移行に加えて、コマンドレット `Start-CsExMeetingMigration`を実行して、ユーザーの会議の移行を手動でトリガーできます。 このコマンドレットは、指定したユーザーの移行要求をキューに入れます。  必要な`Identity`パラメーターに加えて、2 つの省略可能なパラメーターを`TargetMeetingType`受け取り、`SourceMeetingType`会議を移行する方法を指定できます。

**TargetMeetingType:**

- 使用すると`TargetMeetingType Current`、Skype for Business会議は会議Skype for Business残り、Teams会議は会議Teams残ることを指定します。 ただし、電話会議の座標は変更される可能性があり、オンプレミスのSkype for Business会議はすべてSkype for Business Online に移行されます。 これは TargetMeetingType の既定値です。
- [使用] を使用`TargetMeetingType Teams`すると、電話会議の更新が必要かどうかに関係なく、会議がSkype for Businessオンラインまたはオンプレミスで開催されているかどうかに関係なく、既存の会議をTeamsに移行する必要があることを指定します。

**SourceMeetingType:**

- [使用`SourceMeetingType SfB`] は、Skype for Business会議 (オンプレミスかオンラインか) のみを更新する必要があることを示します。
- [使用] `SourceMeetingType Teams` は、Teams会議のみを更新する必要があることを示します。
- 使用は`SourceMeetingType All`、Skype for Business会議とTeams会議の両方を更新する必要があることを示します。 これは SourceMeetingType の既定値です。

次の例は、すべての会議がTeamsに移行されるように、ユーザー ashaw@contoso.com の会議の移行を開始する方法を示しています。

```PowerShell
Start-CsExMeetingMigration -Identity ashaw@contoso.com -TargetMeetingType Teams
```

## <a name="managing-mms"></a>MMS の管理

Windows PowerShellを使用すると、進行中の移行の状態を確認したり、会議の移行を手動でトリガーしたり、移行を完全に無効にしたりできます。

### <a name="check-the-status-of-meeting-migrations"></a>会議の移行の状態を確認する

コマンドレットを `Get-CsMeetingMigrationStatus` 使用して、会議の移行の状態を確認します。 次に例を示します。

- すべての MMS 移行の概要状態を取得するには、すべての移行状態を表形式で表示する次のコマンドを実行します。

    ```PowerShell
    Get-CsMeetingMigrationStatus -SummaryOnly

    State      UserCount
    ------     ---------
    Pending      21
    InProgress    6
    Failed        2
    Succeeded   131
    ```

- 特定の期間内のすべての移行の詳細を取得するには、パラメーターと`EndTime`パラメーターを`StartTime`使用します。 たとえば、次のコマンドは、2018 年 10 月 1 日から 2018 年 10 月 8 日に発生したすべての移行の詳細を返します。

    ```PowerShell
    Get-CsMeetingMigrationStatus -StartTime "10/1/2018" -EndTime "10/8/2018"
    ```

- 特定のユーザーの移行の状態を確認するには、パラメーターを `Identity` 使用します。 たとえば、次のコマンドは、ユーザー ashaw@contoso.com の状態を返します。

    ```PowerShell
    Get-CsMeetingMigrationStatus -Identity ashaw@contoso.com
    ```

失敗した移行が発生した場合は、解決するまでユーザーが開催した会議にダイヤルインできないため、できるだけ早くこれらの問題を解決するためのアクションを実行します。 失敗した状態の移行が表示される場合 `Get-CsMeetingMigrationStatus` は、次の手順を実行します。

1. 影響を受けているユーザーを特定します。 次のコマンドを実行して、影響を受けているユーザーと、報告された特定のエラーのリストを取得します。

    ```PowerShell
    Get-CsMeetingMigrationStatus| Where {$_.State -eq "Failed"}| Format-Table UserPrincipalName, LastMessage
    ```

2. 影響を受けるユーザーごとに、LastMessage プロパティの値を確認して、会議の移行に失敗した理由と、実行する修正アクションを確認します。 修正アクションが実行されたら、上記のように PowerShell cmldet を使用して、影響を受けるユーザーの `Start-CsExMeetingMigration` 会議の移行を再度トリガーします。

3. 移行がまだ機能しない場合は、次の 2 つのオプションがあります。

    - ユーザーに新しい Skype 会議を作成してもらいます。
    - [サポートに問い合わせます](/microsoft-365/Admin/contact-support-for-business-products)。

この `Get-CsMeetingMigrationStatus` コマンドレットを使用すると、過去 150 日以内にトリガーされた移行の状態を取得できます。 150 日より前の移行のレコードは、システムから削除されます。

### <a name="enabling-and-disabling-mms"></a>MMS の有効化と無効化

MMS はすべての組織で既定で有効になっていますが、次のように無効にすることができます。

- テナントに対して完全に無効にします。
- 電話会議に関連する変更に対してのみ無効にします。 この場合、ユーザーがオンプレミスからクラウドに移行されたとき、または TeamsOnly モードまたは SfBWithTeamsCollabAndMeetings `TeamsUpgradePolicy`モードを許可した場合でも、MMS は引き続き実行されます。

たとえば、組織の電話会議設定を大幅に変更しながら、すべての会議を手動で移行したり、MMS を一時的に無効にしたりできます。

組織で MMS が有効になっているかどうかを確認するには、次のコマンドを実行します。 パラメーター`$true`が .`MeetingMigrationEnabled`

```PowerShell
Get-CsTenantMigrationConfiguration
```

組織内で MMS が有効になっていて、電話会議の更新が有効になっているかどうかを確認する場合は、出力`Get-CsOnlineDialInConferencingTenantSettings`のパラメーターの`AutomaticallyMigrateUserMeetings`値を確認します。 電話会議の MMS を有効または無効にするには、 `Set-CsOnlineDialInConferencingTenantSettings`. たとえば、電話会議の MMS を無効にするには、次のコマンドを実行します。

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings  -AutomaticallyMigrateUserMeetings $false
```

## <a name="related-topics"></a>関連項目

[Microsoft 365またはOffice 365で電話会議を試すか購入する](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

[オンプレミスとクラウドの間でユーザーを移動する](../../SfbHybrid/hybrid/move-users-between-on-premises-and-cloud.md)
