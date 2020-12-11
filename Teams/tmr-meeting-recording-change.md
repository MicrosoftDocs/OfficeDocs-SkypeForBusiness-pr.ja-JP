---
title: OneDrive for Business と SharePoint を使って会議のレコーディングを行う
author: cichur
ms.author: v-cichur
ms.reviewer: hao.moy
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Microsoft Teams で Stream から OneDrive for Business および SharePoint 会議レコーディング ストレージに切り替える方法について説明します。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: ea07079a94e2f76f8833e0854fd0161b4ff9ec09
ms.sourcegitcommit: 6b24c82837ca2c11f450a162ca4fab3dfa4ac8d4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620712"
---
# <a name="use-onedrive-for-business-and-sharepoint-or-stream-for-meeting-recordings"></a>OneDrive for Business と SharePoint または Stream を使って会議のレコーディングを行う

> [!Note]
> Microsoft Stream を使用して OneDrive for Business および Microsoft SharePoint を会議のレコーディングに変更する方法は、段階的なアプローチになります。

|<div style="width:290px">日付&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</div> |イベント&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;                                                                                                                                                                                                                                                                                                             |
|:-----------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|2020 年 10 月 5 日 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;| Teams 会議ポリシーを有効にして、会議の記録を Microsoft Stream (クラシック) ではなく OneDrive for Business と SharePoint に保存することができます。|
|2021 年 1 月 7 日から展開 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|組織の Teams 会議ポリシーを変更し、明示的に Stream に設定してこの変更を遅らせない限り、すべての新しい Teams 会議レコーディングは OneDrive for Business および SharePoint に保存 **されます。** ポリシーレポートを Stream として表示するには十分ではありません。 ポリシー値を Stream に明示的に設定する必要 **があります**。|
|2021 年 1 月 11 日から展開 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**GCC のみ**<br> GCC のお客様は 10 月 5 日からオプトアウトすることができますが、オプトインできません。 この機能は、オプトアウトしない限り、2021 年 1 月 11 日からすべての GCC ユーザーに展開されます。<br>  <br>2021 年 1 月 11 日から、GCC ユーザー向けのすべての新しい Teams 会議レコーディングは、組織の Teams 会議ポリシーを変更し、明示的に Stream に設定してこの変更を遅らせない限り、OneDrive for Business と SharePoint に保存されます。 <br><br>無効にしたが、この機能を有効にする準備ができている場合は、Teams 会議ポリシーを **OneDrive for Business** に明示的に設定して有効にできます。 |
|2021 年 3 月 1 日から展開 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**エンタープライズ & GCC のお客様**<br>新しい会議レコーディングを Microsoft Stream (クラシック) に保存することはできません。Teams の会議ポリシーを Stream に変更した場合でも、すべてのユーザーが会議の記録を **OneDrive for Business** と SharePoint に自動的に保存します。<br><br> この機能は、リリースのタイミングを制御できるよう、この日付より前にロールアウトすることをお勧めします。 |
|2021 年 7 月 7 日から展開 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**教育のお客様**<br>新しい会議レコーディングを Microsoft Stream (クラシック) に保存することはできません。Teams の会議ポリシーを Stream に変更した場合でも、すべてのユーザーが会議の記録を **OneDrive for Business** と SharePoint に自動的に保存します。<br><br> この機能は、リリースのタイミングを制御できるよう、この日付より前にロールアウトすることをお勧めします。 このスケジュールを更新して、学期中に学期を完了する機能を教育のお客様に提供しました。 |

> [!Note]
> エンタープライズおよび教育機関のお客様は、組織の変更をより詳細に制御するために、変更の発生を待つ代わりに、変更に快適に取りかかわるたびにオプトインすることをお勧めします。

Microsoft Teams には、会議の記録を保存する新しい方法があります。 従来の Microsoft Stream から新しい [Stream](https://docs.microsoft.com/stream/streamnew/new-stream)への移行の第 1 フェーズとして、この方法では Microsoft 365 の Microsoft OneDrive for Business と SharePoint にレコーディングが保存され、多くの利点があります。

OneDrive for Business と SharePoint を使用してレコーディングを保存する利点は次のとおりです。

- Teams 会議レコーディング (TMR) のアイテム保持ポリシー (S + C E5 自動送信ラベル)
- OneDrive for Business と SharePoint の情報ガバナンスの利点
- 簡単にアクセス許可と共有を設定する
- 明示的な共有のみを使用してゲスト (外部ユーザー) とレコーディングを共有する
- アクセス フローを要求する
- OneDrive for Business と SharePoint の共有リンクを提供する
- クォータの増加
- 会議の記録が速く利用できる
- **ローカル テナントの** サポートに移動する
- 複数地域のサポート – レコーディングは、そのユーザーに固有の地域に保存されます。
- 独自のキー (BYOK) のサポートを利用する
- トランスクリプトの品質とスピーカー属性の改善

次のような制限事項を考慮する必要があります。

- 英語専用のクローズド キャプションとトランスクリプトがあります。
- トランスクリプトやコンテンツを検索できない。
- トランスクリプトを編集できないが、キャプションのオン/オフを切り替える。
- 記録を共有する相手を制御できますが、共有アクセス権を持つユーザーによるレコーディングのダウンロードをブロックする機能は使用できます。
- 記録の保存が完了するとメールは送信されませんが、記録が完了すると会議チャットに表示されます。 これは以前の Stream よりも早く発生します

詳細については、「会議の記録」を参照してください。

> [!VIDEO https://www.youtube.com/embed/8iol0KfCeL8]

## <a name="set-up-the-meeting-recording-option-for-onedrive-for-business-and-sharepoint"></a>OneDrive for Business と SharePoint の会議レコーディング オプションを設定する

会議の記録オプションは、Teams ポリシー レベルでの設定です。 次の例は、グローバル ポリシーを設定する方法を示しています。 ユーザーに割り当てたポリシーの会議レコーディング オプションを設定してください。

> [!Note]
> Teams 会議ポリシーの変更が反映されるには、しばらく時間がかかる。 数時間の設定後にもう一度確認し、サインアウトしてもう一度サインインします。

1. Skype for Business Online PowerShell をインストールします。
**注**: Skype for Business Online Connector は現在、最新の Teams PowerShell モジュールの一部です。 最新の Teams PowerShell パブリック リリースを使用している場合は、Skype for Business Online Connector をインストールする必要があります。 [「PowerShell で Skype for Business Online を管理する」を参照してください](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide&preserve-view=true)。

    a. [Skype for Business Online PowerShell をダウンロードします](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide&preserve-view=true)。

    b. 画面の指示に従ってインストールします。

    c. コンピューターを再起動します。

2. 管理者として PowerShell を起動する

3. SkypeOnline Connector をインポートし、Teams 管理者としてサインインします。

   ```powershell
   Import-Module SkypeOnlineConnector
   $sfbSession = New-CsOnlineSession
   Import-PSSession $sfbSession
   ```

4. [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)を使用して、Stream ストレージから OneDrive for Business および SharePoint に移行する Teams 会議ポリシーを設定します。

   ```powershell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "OneDriveForBusiness"
   ```

> [!Note]
> 一部のユーザーが開催者ごとのポリシーまたはユーザーごとのポリシーを割り当てている場合、会議の記録を OneDrive for Business と SharePoint にも保存する場合は、このポリシーでこの設定を設定する必要があります。 詳細については [、「Teams で会議ポリシーを管理する」を参照してください](meeting-policies-in-teams.md)。

## <a name="opt-out-of-onedrive-for-business-and-sharepoint-to-continue-using-stream"></a>引き続き Stream を使用するには、OneDrive for Business と SharePoint をオプトアウトする

ポリシーで Stream に設定されている場合でも、設定されていない可能性があります。 通常、ポリシーが設定されていない場合、既定の設定は **Stream です**。 ただし、この新しい変更により、SharePoint または OneDrive for Business の使用をオプトアウトする場合は、Stream が既定のポリシーにリセットされる必要があります。

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "Stream"
```

## <a name="permissions-or-role-based-access"></a>アクセス許可またはロール ベースのアクセス

> [!Note]
> Teams 会議レコーディングを共有する場合は、受信者がログインしているユーザーである必要があります。 SharePoint **のファイルまたはフォルダーに** ドキュメントとしてファイルを共有する場合は、[組織内のユーザー] [オプションを選択します](https://support.microsoft.com/office/share-sharepoint-files-or-folders-1fe37332-0f9a-4719-970e-d2578da4941c?redirectSourcePath=%25252fen-US%25252farticle%25252fShare-sites-or-documents-with-people-outside-your-organization-80E49744-E30F-44DB-8D51-16661B1D4232&ui=en-US&rs=en-US&ad=US)。 外部共有は、サイズの大きいファイルや大量のファイルを配布するようには設計されていない。 詐欺や悪用のシナリオを防ぐために、大量のデータを外部ユーザーと共有するときに問題が発生する場合があります。

|会議の種類                               | [レコード] をクリックしたユーザー| 記録はどこに保存されますか?                               |アクセス権を持つユーザー R/W、R、または共有                                                                                                                                                                                                                                                     |
|-------------------------------------------|-----------------------|--------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|内部関係者との 1 対 1 の通話             |[発信者]                 |発信者の OneDrive for Business アカウント                        |呼び出し元は所有者であり、完全な権限を持っています。 <br /><br />呼び出し先 (同じテナント内の場合) には読み取り専用アクセス権があります。 共有アクセスなし。 <br /><br /> 呼び出し先 (別のテナントの場合) にはアクセス権はありません。 発信者は呼び出し先と共有する必要があります。|
|内部関係者との 1 対 1 の通話             |[呼び出し先]                 |呼び出し先の OneDrive for Business アカウント                        |呼び出し先は所有者であり、完全な権限を持っています。 <br /><br />呼び出し元 (同じテナント内に読み取り専用アクセス権がある場合)。 共有アクセスなし。 <br /><br />呼び出し元 (別のテナントの場合) にアクセス権がない。 呼び出し先は発信者と共有する必要があります。|
|外部通話での 1 対 1 の通話             |[発信者]                 |発信者の OneDrive for Business アカウント                        |呼び出し元は所有者であり、完全な権限を持っています。<br /> <br />呼び出し先にはアクセス権はありません。 発信者は呼び出し先と共有する必要があります。|
|外部通話での 1 対 1 の通話             |[呼び出し先]                 |呼び出し先の OneDrive for Business アカウント                        |呼び出し先は所有者であり、完全な権限を持っています。<br /><br />呼び出し元にはアクセス権はありません。 呼び出し先は発信者と共有する必要があります。|
|グループ通話                                 |通話の任意のメンバー |レコードの OneDrive for Business アカウントをクリックしたメンバー  |[レコード] をクリックしたメンバーには、完全な権限があります。 <br /><br /> 同じテナントの他のメンバーには読み取り権限があります。 <br /><br /> 異なるテナントの他のメンバーには、その権限はありません。|
|Adhoc/スケジュールされた会議                    |[開催者]              |開催者の OneDrive for Business アカウント                     |開催者には、記録に対する完全な権限があります。 <br /><br /> 会議の他のすべてのメンバーは読み取りアクセス権を持っています。|
|Adhoc/スケジュールされた会議                    |他の会議メンバー   |[レコード] をクリックしたメンバー                                  |[レコード] をクリックしたメンバーには、記録に対する完全な権限があります。 <br /><br />開催者は編集権限を持ち、共有できます。<br /><br /> 他のすべてのメンバーは読み取りアクセス権を持っています。|
|Adhoc/外部ユーザーとのスケジュールされた会議|[開催者]              |開催者の OneDrive for Business アカウント                     |開催者には、記録に対する完全な権限があります。<br /> <br /> 開催者と同じテナントの会議の他のすべてのメンバーは、読み取りアクセス権を持っています。 <br /><br /> 他のすべての外部メンバーはアクセス権を持たず、開催者がアクセス権を共有する必要があります。|
|Adhoc/外部ユーザーとのスケジュールされた会議|他の会議メンバー   |[レコード] をクリックしたメンバー                                  |[レコード] をクリックしたメンバーには、記録に対する完全な権限があります。 開催者は編集権限を持ち、共有できます。 <br /><br /> 開催者と同じテナントの会議の他のすべてのメンバーは、読み取りアクセス権を持っています。 <br /><br />他のすべての外部メンバーはアクセス権を持たず、開催者がアクセス権を共有する必要があります。|
|チャネル会議                            |チャネル メンバー         |そのチャネルの Teams の SharePoint の場所                   |[レコード] をクリックしたメンバーには、記録に対する編集権限があります。 <br /> <br />他のすべてのメンバーの権限は、Channel SharePoint の権限に基づいて設定されます。|

## <a name="frequently-asked-questions"></a>よく寄せられる質問

**会議の記録はどこに保存されますか?**

- 非チャネル会議の場合、レコーディングは、会議のレコーディングを開始したユーザーに属する OneDrive for Business のトップ レベルにある [レコーディング] という名前のフォルダーに保存されます。 例:

  <i>recorder の OneDrive for Business</i> /**レコーディング**

- チャネル会議の場合、レコーディングは[レコーディング] という名前のフォルダーの Teams サイト ドキュメント ライブラリ **に保存されます**。 例:

  <i>チーム名 - チャネル名</i> /**ドキュメント** /**レコーディング**

**元従業員からのレコーディングを処理する方法**

ビデオは OneDrive for Business および SharePoint の他のファイルと同じ機能を持つので、従業員の離れ後の所有権と保持の処理は、通常の [OneDrive for Business]( https://docs.microsoft.com/onedrive/retention-and-deletion#the-onedrive-deletion-process)と SharePoint のプロセスに従います。

**会議の記録を表示する権限を持っているユーザー**

- チャネル以外の会議の場合、外部ユーザーを除くすべての会議の招待者は、自動的に個人用共有リンクを取得します。 外部ユーザーは、会議の開催者または会議の記録を開始したユーザーが共有リストに明示的に追加する必要があります。

- チャネル会議の場合、アクセス許可はチャネルの所有者とメンバーのリストから継承されます。

**トランスクリプトを管理する方法**

このプレビューに参加しているお客様は、OneDrive for Business および SharePoint に移行される Teams 会議レコーディングでクローズド キャプションを利用できません。Q4 CY2020 の会議のレコーディングには、英語のクローズド キャプションから始まるキャプションを追加する作業を行っています。

クローズド キャプションは、Teams クラウドレコーディングの説明に従ってトランスクリプトを許可することを選択したお客様のために、Teams 会議レコーディングで [利用できます](cloud-recording.md)。

キャプションは、すべての能力の閲覧者に包括的なコンテンツを作成するのに役立ちます。 所有者はキャプションを非表示にできます。ただし、Teams からキャプションを削除しない限り、トランスクリプトは Teams で引き続き使用できます。 会議 [のレコーディングをオンまたはオフにする方法をご覧ください](cloud-recording.md#set-up-teams-cloud-meeting-recording-for-users-in-your-organization)。

クローズド キャプションは、会議が記録された後 60 日間、Teams 会議のレコーディングでサポートされます。

Teams 会議レコーディングが OneDrive for Business または SharePoint 上の元の場所から移動またはコピーされた場合、クローズド キャプションは完全にはサポートされません。

**記憶域のクォータに与える影響**

Teams 会議のレコーディング ファイルは OneDrive for Business と SharePoint に保存され、それらのサービスのクォータに含まれます。 [SharePoint のクォータと](https://docs.microsoft.com/sharepoint/sites/plan-site-maintenance-and-management#quotas)OneDrive for Business のクォータ[を参照してください](https://docs.microsoft.com/onedrive/set-default-storage-space)。

[OneDrive for Business を使用すると、Stream と比較](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)してストレージを追加し、SharePoint を使用してより手ごたえのあるストレージを取得できます。

**Teams 会議の記録を再生する方法**

ファイルにアクセスする場所に応じて、OneDrive for Business または SharePoint のビデオ プレーヤーでビデオが再生されます。

**Stream への追加を廃止する予定の場合、既存のビデオは現在とどのくらいの期間残りますか?**

プラットフォームとしてのストリームは、近い将来廃止される予定です。 現在 Stream に保存されているビデオは、移行を開始するまでそこに残ります。 移行時には、これらのビデオも OneDrive for Business または SharePoint に移行されます。 詳細については [、Stream クラシック移行](https://docs.microsoft.com/stream/streamnew/classic-migration) を確認してください。

**保持ラベルを適用する方法**

アイテム [保持ラベルを自動適用する方法を参照してください](https://docs.microsoft.com/microsoft-365/compliance/apply-retention-labels-automatically?view=o365-worldwide#microsoft-teams-meeting-recordings)。

**Microsoft Teams のユーザーにポリシーを割り当て、どのポリシーが優先されるのか**

どの [ポリシーが優先されるのか確認してください](https://docs.microsoft.com/MicrosoftTeams/assign-policies#which-policy-takes-precedence)。
