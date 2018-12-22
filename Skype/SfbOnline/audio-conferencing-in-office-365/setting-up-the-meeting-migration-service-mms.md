---
title: 会議の移行サービス (MMS) を使用してください。
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
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 会議の移行サービス (MMS) は、バック グラウンドで実行され、ユーザーのビジネスおよびマイクロソフトのチームの会議に Skype が自動的に更新するサービスです。 MMS はユーザーが会議移行ツールを実行して Skype for Business および Microsoft Teams 会議を更新しなくても済むように設計されています。
ms.openlocfilehash: 5b01dfc0c50ecb742e049905c81a418007ea3600
ms.sourcegitcommit: d00b85ace80af0403efb85b71e5bcc66e76f837b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2018
ms.locfileid: "27411117"
---
# <a name="using-the-meeting-migration-service-mms"></a>会議の移行サービス (MMS) を使用してください。

会議の移行サービス (MMS) は、次のシナリオで、ユーザーの既存の会議を更新するサービスです。

- ユーザーを移行するとき、オンプレミス (Skype のビジネスをオンラインにするか TeamsOnly) クラウドに移行します。
- 管理者がユーザーの電話会議の設定に変更を行う場合 
- TeamsOnly モード (技術導入プログラム [タップ] のお客様のみ) にユーザーをアップグレードするとき

既定では、MMS 自動的にトリガーのような場合、管理者が無効にする、テナントのレベルがされます。 さらに、管理者は、手動で特定のユーザーの会議の移行を開始するのに PowerShell コマンドレットを使用することができます。

> [!NOTE]
> チームの会議に会議の Skype を変換する機能と電話会議の設定を変更するのには既存のチーム ミーティングを更新する機能は、タップのお客様のみに制限されて。

**制限**: 会議次のいずれかの場合、移行サービスを使用できません。

- ユーザーのメールボックスは、Exchange、オンプレミスでホストされています。
- サード ・ パーティ製のオーディオ会議プロバイダーを使用するユーザーを構成します。 オーディオ会議プロバイダー [ACP] サポートで予定されているライフの最後に、2019 年 4 月 1日として[発表されていた](https://docs.microsoft.com/skypeforbusiness/legal-and-regulatory/end-of-integration-with-3rd-party-providers)注意してください。
- ユーザー クラウドからに移行 Skype ビジネス サーバー設置型です。

このような場合は、エンド ・ ユーザーは、独自の会議を移行するのには[会議の移行ツール](https://www.microsoft.com/en-us/download/details.aspx?id=51659)を使用できます代わりにします。

## <a name="how-mms-works"></a>MMS のしくみ

MMS がユーザーごとにトリガーされると、そのユーザーの移行要求はキューに配置されます。 任意の競合状態を避けるためには、90 分以上が経過するまでは意図的に、キューに入れられた要求が処理されます。 MMS では、要求を処理すると、次のタスクを実行します。

1. ユーザーごとに編成され、今後予定されているすべての既存の会議のユーザーのメールボックスを検索します。
2. ユーザーのメールボックス内の情報に基づき、いずれかを更新または実際の状況によって、そのユーザーのオンライン ビジネスのチームまたは Skype のいずれかで新しい会議をスケジュールします。
3. 電子メール メッセージでは、[ミーティングの詳細、オンライン会議のブロックに置き換えられます。
4. その会議の更新されたバージョンを会議の開催者の代理として会議のすべての受信者に送信します。 会議出席者に電子メールで更新された会議出席の座標を使用して会議の更新が表示されます。 

    ![MMS で更新される会議ブロック。](../images/210a03ee-30c1-46f3-808f-4c2ebdaa3ea1.png)

MMS がトリガーされた場合、通常かかるユーザーの会議は、移行するまで、約 2 時間です。 ただし、ユーザーが会議の数が多い場合、長くかかる場合があります。 MMS では、ユーザーの会議を 1 つまたは複数の移行エラーが発生すると、それによって定期的に再試行最大 9 倍 24 時間の範囲で。

**メモ**:

- MMS は会議が移行されるときにオンライン会議の情報ブロックのすべてを置き換えます。このため、ユーザーがそのブロックを編集した場合は、それらの変更は上書きされます。オンライン会議の情報ブロック以外の会議の詳細に含まれているコンテンツは影響しません。
- Outlook on the Web で [ **Skype 会議の追加**] ボタンをクリックして、または Outlook 用の Skype 会議アドインを使用してスケジュールされた Skype for Business 会議および Microsoft Teams 会議のみが移行されます。 ユーザーは、コピーし、新しい会議を 1 つの会議から Skype のオンライン会議の情報を貼り付けます、会議サービスではないのでその他の会議は更新されません。
- MMS を実行した後、会議の作成または会議 (ホワイト ボードや投票など) に接続されているコンテンツは保持されません。 会議の開催者が事前にコンテンツを会議に添付している場合、そのコンテンツは MMS の動作後に再作成する必要があります。
- 予定表の項目内、および Skype 会議からの共有の会議ノートへのリンクも上書きされます。 OneNote に保存されている実際の会議の記録があることに注意があります。上書きされる共有のノートにリンクだけすることをお勧めします。
- (開催者を含めて) 250 人を超える参加者がいる会議は移行できません。
- 招待状の本文にいくつかの UNICODE 文字がありますが正しく更新されません次の特殊文字のいずれかに: ï、¿、½、します。

## <a name="triggering-mms-for-a-user"></a>ユーザーが MMS をトリガーします。

このセクションでは、次の場合のそれぞれで MMS がトリガーされたときの動作について説明します。

- クラウドへの設置からユーザーが移行されるとき
- 管理者がユーザーの電話会議の設定に変更を行う場合 
- TeamsOnly モード (タップのお客様のみ) にユーザーをアップグレードするとき
- PowerShell を使用する場合 

### <a name="updating-meetings-when-you-move-an-on-premises-user-to-the-cloud"></a>オンプレミスのユーザーをクラウドに移行するときに、会議を更新

これは、MMS により、ユーザーのスムーズなトランジションを作成する最も一般的なシナリオです。 会議の移行せずユーザーがオンラインに移動すると Skype のビジネス サーバー設置型のユーザーが既存のミーティングは動作しなく。 したがって、設置型の管理ツールを使用する (か、`Move-CsUser`またはコントロール パネルの [管理者) ユーザーをクラウドに移動するに既存の会議は自動的に移動、クラウドに次のように。

- 場合、`MoveToTeams`でスイッチを`Move-CsUser`が指定されている会議は、チームに直接移行できます。 このスイッチを使用するには、CU8 を持つサーバーをビジネスの Skype が必要です。
- それ以外の場合の会議は、ビジネス オンラインの Skype に移行されます。

どちらの場合も、[ユーザー割り当てられている場合、オーディオ会議のライセンスをクラウドに移動する前に、会議は、ダイヤルインの座標を使用して作成されます。 オンプレミスからクラウドに移行するユーザーを移動すると、そのユーザーの音声会議を使用する、1 つだけの会議の移行をトリガーするためにユーザーを移動する前にまず、オーディオ会議を割り当てることをお勧めします。

> [!NOTE]
> 現在の会議を MoveToTeams スイッチを使用してチームに直接移行することは、タップでできるだけです。 タップのお客様が、MoveToTeams スイッチを指定する場合は、ユーザーは、TeamsOnly モードに移動されますが、会議は、ビジネス オンラインの Skype に移動されます。 場合でも、ユーザーは、TeamsOnly モードに参加できますビジネス会議のため、Skype。

### <a name="updating-meetings-when-a-users-audio-conferencing-settings-change"></a>ユーザーの電話会議の設定が変更されるときの会議の更新

MMS では以下の場合では、ビジネスおよびマイクロソフトのチーム会議の追加、削除、またはダイヤルインの座標を変更する既存の Skype が更新されます。

- 割り当てるまたは、ビジネスの Skype のサード ・ パーティ製のオーディオ会議プロバイダーとの統合を有効にしていないユーザーの Microsoft オーディオ会議サービス ライセンスを削除します。
- マイクロソフトに、他のプロバイダーから割り当てられているマイクロソフトの電話会議サービスのライセンスを持っているユーザーのオーディオ会議プロバイダーを変更するとします。
- 有効または無効にするユーザーの電話会議。
- 変更するか、パブリック ・ ミーティングを使用するように構成するユーザーの会議 ID をリセットします。
- ユーザーを新しい電話会議ブリッジに移行する場合
- オーディオ会議ブリッジからの電話番号が割り当てられていません。 これは、追加の手順を必要とする複雑なシナリオです。 詳細については、[変更オーディオ会議ブリッジの電話番号](https://docs.microsoft.com/en-us/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge)を参照してください。

ユーザーの電話会議の設定に対する変更の一部は、MMS をトリガーしません。特に、次の 2 つの変更では、MMS によって会議が更新されません。

- 会議の開催者の SIP アドレスを変更する場合 (SIP ユーザー名または SIP ドメインのいずれか)
- 組織の URL を使用しての会議を変更すると、`Update-CsTenantMeetingUrl`コマンドです。

> [!NOTE]
> サード ・ パーティ製の ACP のユーザーが有効になっている場合は、MMS は発生しません。 ACP は、[発表されていた](https://docs.microsoft.com/en-us/skypeforbusiness/legal-and-regulatory/end-of-integration-with-3rd-party-providers)として、2019 年 4 月 1 日の寿命の最後の予定です。 MMS のユーザーの会議を移行する場合は、ユーザーはまず ACP を無効にします。

### <a name="updating-meetings-when-assigning-teamsupgradepolicy"></a>TeamsUpgradePolicy を割り当てる場合は、会議を更新

> [!NOTE]
> このセクションでは、最初に使用可能になるタップのお客様に今後の機能について説明します。

既定では、会議の移行は、自動的に起動のインスタンスがユーザーに付与されると`TeamsUpgradePolicy`と`mode=TeamsOnly`または`mode= SfBWithTeamsCollabAndMeetings`。 これらのモードのいずれかを付与する場合は、会議を移行し、指定しない場合は、`MigrateMeetingsToTeams $false`の`Grant-CsTeamsUpgradePolicy`。

また、次の点を注意してください。

- 会議の移行のみ呼び出されるを与えるときに`TeamsUpgradePolicy`の特定のユーザーです。 付与する場合は`TeamsUpgradePolicy`と`mode=TeamsOnly`または`mode=SfBWithTeamsCollabAndMeetings`テナント単位で会議の移行は呼び出されません。
- ユーザーことができますだけに付与する TeamsOnly モードの場合は、ユーザーのオンライン ホームします。 使用してホーム設置型ではユーザーを移動する必要があります`Move-CsUser`、上記のとおりです。
- TeamsOnly または SfBWithTeamsCollabAndMeetings 以外のモードを許可する変換されません既存のチーム ミーティング Skype をビジネス ・ ミーティングの。

## <a name="managing-mms"></a>MMS の管理

Windows PowerShell を使用すると、継続的な移行の状態を確認して、手動で会議の移行をトリガーして移行を完全に無効にできます。 

### <a name="check-the-status-of-meeting-migrations"></a>会議の移行の状態を確認します。

使用する、`Get-CsMeetingMigrationStatus`会議の移行の状態を確認するコマンドレットです。 次に例を示します。

- MMS のすべてのマイグレーション処理のステータスの概要を取得するには、移行の状態のすべての表形式のビューを提供する次のコマンドを実行します。

    ```
    Get-CsMeetingMigrationStatus -SummaryOnly

    State      UserCount
    ------     ---------
    Pending      21
    InProgress    6
    Failed            2 
    Succeeded   131
    ```
- 特定の期間内ですべての移行の完全な詳細情報を取得するには、`StartTime`と`EndTime`のパラメーター。 などの次のコマンドは完全な詳細情報が発生したすべての移行で、2018 年 10 月 1 日からに戻る 2018 年 10 月 8日

    ```
    Get-CsMeetingMigrationStatus -StartTime "10/1/2018" -EndTime "10/8/2018"
    ```
- 特定のユーザーの移行の状態を確認するを使用して、`Identity`のパラメーターです。 たとえば、次のコマンドには、ユーザー ashaw@contoso.com のステータスが返されます。

    ```
    Get-CsMeetingMigrationStatus -Identity ashaw@contoso.com
    ```
移行に失敗した場合は、人々 はそれらを解決するまでは、ユーザーが開催する会議にダイヤルインすることができませんので、できるだけ早く、これらの問題を解決するのにはアクションを実行します。 場合`Get-CsMeetingMigrationStatus`の移行を示しています。 障害が発生した状態でこれらの手順に従います。
 
1. 影響を受けているユーザーを特定します。 次のコマンドを実行して、影響を受けているユーザーと、報告された特定のエラーのリストを取得します。

    ```
    Get-CsMeetingMigrationStatus| Where {$_.State -eq "Failed"}| Format-Table Identity, LastMessage
    ```
2. 、影響を受けるユーザーごとに、会議を手動で移行するのには会議の移行ツールを実行します。

3. 会議移行ツールを使用しても移行が機能しない場合には、次の 2 つのオプションがあります。

    - ユーザーに新しい Skype 会議を作成してもらいます。
    - [サポートに問い合わせます](https://go.microsoft.com/fwlink/p/?LinkID=518322)。

### <a name="trigger-meeting-migration-manually-for-a-user"></a>ユーザーは手動でトリガー会議の移行

会議予定の自動移行の場合、だけでなく管理者手動でトリガーできますユーザーの会議の移行コマンドレットを実行して`Start-CsExMeetingMigration`。 このコマンドレットは、指定したユーザーの移行要求をキューします。 `TargetMeetingType`パラメーターでは、会議を移行する方法を指定することができます。 

- 使用して`TargetMeetingType Current`、ビジネス会議のための Skype は、ビジネス ・ ミーティングの Skype を維持され、チームの会議のチーム会議を維持するを指定します。 ただしオーディオ会議の調整を変更する可能性があり、ビジネス会議のため、設置型の Skype は、ビジネス オンラインの Skype に移行するとします。
- 使用して`TargetMeetingType Teams`のチームに、既存の会議を移行する必要がある、オンライン ビジネスの設置、Skype で会議がホストされるかどうかに関係なくとかどうかに関係なく、オーディオ会議の更新プログラムは、必要を指定します。 

次の例は、すべての会議は、チームに移行できるように、ユーザーの ashaw@contoso.com の会議の移行を開始する方法を示しています。

```
Start-CsExMeetingMigration -Identity ashaw@contoso.com -TargetMeetingType Teams
```
### <a name="enabling-and-disabling-mms"></a>MMS の有効化と無効化

MMS がすべての組織では、既定で有効になっているが、次のように無効にすることができます。

- テナントのすべてを無効にします。 
- 音声会議に関連する変更だけを無効にします。 MMS をクラウドに移行する、または TeamsOnly モードで SfBWithTeamsCollabAndMeetings モードを付与する設置型からユーザーを移行するとき実行もここでは、 `TeamsUpgradePolicy`。

などを手動ですべての会議を移行または組織の電話会議の設定に大幅な変更を加えるときに、MMS を一時的に無効にすることがあります。

MMS が組織で有効になっているかどうかを表示するには、次のコマンドを実行します。 MMS を有効にすると、場合は、`MeetingMigrationEnabled`のパラメーターは、 `$true`。
```
Get-CsTenantMigrationConfiguration
```
有効にするか、MMS を完全に無効にするには、`Set-CsTenantMigrationConfiguration`コマンドです。 たとえば、MMS を無効にするには、次のコマンドを実行します。

```
Set-CsTenantMigrationConfiguration -MeetingMigrationEnabled $false
```
MMS が組織で有効になっている、オーディオ会議の更新が有効なかどうかを確認する場合は、値を確認して、`AutomaticallyMigrateUserMeetings`からの出力パラメーター `Get-CsOnlineDialInConferencingTenantSettings`。 オーディオ会議の MMS を無効にするを有効またはを使用して、 `Set-CsOnlineDialInConferencingTenantSettings`。 たとえば、オーディオ会議のための MMS を無効にするするには、次のコマンドを実行します。

```
Set-CsOnlineDialInConferencingTenantSettings  -AutomaticallyMigrateUserMeetings $false
```

## <a name="related-topics"></a>関連トピック

[Office 365 での電話会議を使用または購入する](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

[オンプレミスとクラウドの間でユーザーの移動](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)