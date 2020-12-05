---
title: OneDrive for Business および SharePoint で会議の記録を使用する
author: cichur
ms.author: v-cichur
ms.reviewer: hao.moy
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Microsoft Teams でストリームから OneDrive for business および SharePoint 会議のレコーディングストレージに切り替える方法について説明します。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 46d3b53f62a3bb497f173c9efd418b7ed88444c7
ms.sourcegitcommit: 1e16c6c7112bdde03209c12468b5705ddd116a62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2020
ms.locfileid: "49578510"
---
# <a name="use-onedrive-for-business-and-sharepoint-or-stream-for-meeting-recordings"></a>OneDrive for Business と、会議の記録に SharePoint または Stream を使用する

> [!Note]
> 会議の記録用に Microsoft Stream を使用して OneDrive for Business と Microsoft SharePoint を使用するように変更した場合は、段階的なアプローチとなります。

|<div style="width:290px">期日&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</div> |イベント&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;                                                                                                                                                                                                                                                                                                             |
|:-----------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|2020年10月5日 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;| チーム会議ポリシーを有効にして、Microsoft Stream ではなく、OneDrive for Business および SharePoint に会議のレコーディングを保存することができます (クラシック)|
|2021年1月11日からロールアウトする &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|この変更は、組織の Teams 会議ポリシーを変更して、明示的に **ストリーム** に設定することで、OneDrive for Business および SharePoint に保存されます。 ストリームとしてのポリシーレポートは、十分なものではありません。 ポリシー値を **ストリーム** に明示的に設定する必要があります。|
|2021年3月1日からのロールアウト &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**企業のお客様**<br>Microsoft Stream (クラシック) に新しい会議の記録を保存することはできません。すべてのユーザーには、チームの会議のポリシーを **ストリーミング** に変更した場合でも、OneDrive for Business および SharePoint に保存された会議のレコーディングが自動的に保存されます。 この機能の前にこの機能をロールして、リリースのタイミングを制御できるようにすることをお勧めします。 |
|2021年7月7日からロールアウトする &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**教育機関向けのお客様**<br>Microsoft Stream (クラシック) に新しい会議の記録を保存することはできません。すべてのユーザーには、チームの会議のポリシーを **ストリーミング** に変更した場合でも、OneDrive for Business および SharePoint に保存された会議のレコーディングが自動的に保存されます。 この機能の前にこの機能をロールして、リリースのタイミングを制御できるようにすることをお勧めします。 このスケジュールを更新して、教育機関のお客様が進行中の semesters を完了できるようにしました。 |

> [!Note]
> 企業および教育機関のお客様は、組織の変更をより適切に管理することをお勧めします。発生するのを待つのではなく、いつでも変更を許可することをお勧めします。

Microsoft Teams には、会議の記録を保存するための新しい方法が用意されています。 従来の Microsoft Stream から [新しいストリーム](https://docs.microsoft.com/stream/streamnew/new-stream)への移行の最初のフェーズとして、このメソッドは microsoft 365 の microsoft OneDrive for Business と SharePoint にレコーディングを保存し、多くの利点を提供します。

OneDrive for Business と SharePoint を使ったレコーディングの保存には、次のような利点があります。

- Teams 会議レコーディングのアイテム保持ポリシー (TMR) (S + C E5 autoretention ラベル)
- OneDrive for Business と SharePoint の情報ガバナンスの利点
- 簡単にアクセス許可と共有を設定する
- 明確な共有のみを使用して、ゲスト (外部ユーザー) とのレコーディングを共有する
- アクセスフローを要求する
- OneDrive for Business と SharePoint の共有リンクを提供する
- クォータの増加
- 会議のレコーディングは、より高速に使用できます
- **ローカル** テナントのサポートに移動する
- 複数地域のサポート–レコーディングは、そのユーザーに固有の地域に保存されます。
- 独自のキー (BYOK) のサポートを利用する
- 議事録の品質とスピーカーの属性を改善しました

次の点について考慮する必要があります。

- 英語専用のクローズドキャプションとトランスクリプトが表示されます。
- トランスクリプトまたはコンテンツを検索することはできません。
- トランスクリプトを編集することはできませんが、字幕のオン/オフを切り替えることができます。
- レコーディングを共有している相手を管理することはできますが、共有アクセス権を持つユーザーがレコーディングをダウンロードするのをブロックすることはできません。
- レコーディングの保存が完了したときにメールを受け取ることはありませんが、レコーディングが完了したら会議のチャットに表示されます。 これは、以前のストリームで行ったよりもはるかに短時間で行われます

詳細については、「会議の記録」をご覧ください。

> [!VIDEO https://www.youtube.com/embed/8iol0KfCeL8]

## <a name="set-up-the-meeting-recording-option-for-onedrive-for-business-and-sharepoint"></a>OneDrive for Business と SharePoint の会議のレコーディングオプションを設定する

[会議レコーディング] オプションは、Teams のポリシーレベルで設定します。 次の例は、グローバルポリシーを設定する方法を示しています。 ユーザーに割り当てたポリシーの [会議レコーディング] オプションが設定されていることを確認してください。

> [!Note]
> Teams の会議ポリシーの変更は、反映されるまでしばらくかかります。 設定が完了したら、もう一度サインアウトしてから、もう一度サインインします。

1. Skype For Business Online PowerShell をインストールします。
**注**: Skype For Business Online Connector は現在、最新の Teams PowerShell モジュールに含まれています。 最新の Teams PowerShell パブリックリリースを使用している場合は、Skype for Business Online Connector をインストールする必要はありません。 「 [PowerShell を使用して Skype For Business Online を管理する」を](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide&preserve-view=true)参照してください。

    a. [Skype For Business Online PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide&preserve-view=true)をダウンロードします。

    b. 指示に従ってインストールします。

    c. コンピューターを再起動します。

2. 管理者として PowerShell を起動する

3. SkypeOnline のコネクタをインポートして、Teams の管理者としてサインインします。

   ```powershell
   Import-Module SkypeOnlineConnector
   $sfbSession = New-CsOnlineSession
   Import-PSSession $sfbSession
   ```

4. [CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)を使用して、ストリームストレージから OneDrive for Business および SharePoint に切り替えるようにチーム会議ポリシーを設定します。

   ```powershell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "OneDriveForBusiness"
   ```

> [!Note]
> ユーザーに、開催者ごとまたはユーザーごとのポリシーが割り当てられている場合は、このポリシーに対してこの設定を設定して、OneDrive for Business および SharePoint で会議のレコーディングも保存する必要があります。 詳細については、「 [Teams の会議ポリシーを管理](meeting-policies-in-teams.md)する」を参照してください。

## <a name="opt-out-of-onedrive-for-business-and-sharepoint-to-continue-using-stream"></a>OneDrive for Business と SharePoint の使用を停止してストリームを継続する

ポリシーで **Stream** に設定されている場合でも、設定されていない可能性があります。 通常、ポリシーが設定されていない場合、既定の設定は **Stream** です。 ただし、この新しい変更では、SharePoint または OneDrive for Business を使用しないようにしたい場合は、ポリシーを [ **ストリーム** ] にリセットして既定の状態にしておく必要があります。

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "Stream"
```

## <a name="permissions-or-role-based-access"></a>権限またはロールベースのアクセス

> [!Note]
> チームの会議の記録を共有する場合、受信者はログインしているユーザーである必要があることをお勧めします。 これを行うには、「 [SharePoint のファイルまたはフォルダーを共有](https://support.microsoft.com/office/share-sharepoint-files-or-folders-1fe37332-0f9a-4719-970e-d2578da4941c?redirectSourcePath=%25252fen-US%25252farticle%25252fShare-sites-or-documents-with-people-outside-your-organization-80E49744-E30F-44DB-8D51-16661B1D4232&ui=en-US&rs=en-US&ad=US)する」の説明に従ってファイルを共有するときに、[**自分の所属するメンバー** ] オプションを選択します。 外部共有は、大きなファイルまたは多数のファイルの配布を目的として設計されていません。 不正使用や不正使用のシナリオを防ぐため、大量のデータを外部ユーザーに共有するときに問題が発生する可能性があります。

|会議の種類                               | レコードをクリックしたユーザー| 記録はどこにありますか?                               |アクセス権を持つユーザー R/W、R、または共有                                                                                                                                                                                                                                                     |
|-------------------------------------------|-----------------------|--------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|社内関係者との1:1 通話             |[発信者]                 |発信者の OneDrive for business アカウント                        |発信者は所有者であり、すべての権限が与えられています。 <br /><br />呼び出し先 (同じテナント内の場合) には読み取り専用のアクセス権があります。 共有アクセスはありません。 <br /><br /> 呼び出し先 (別のテナントの場合) にはアクセスできません。 呼び出し元は呼び出し元に共有する必要があります。|
|社内関係者との1:1 通話             |[呼び出し先]                 |呼び出し先の OneDrive for business アカウント                        |呼び出し先は所有者であり、完全な権限を持ちます。 <br /><br />発信者 (同じテナント内の場合は読み取り専用アクセス権を持ちます。 共有アクセスはありません。 <br /><br />発信者 (別のテナントの場合) にアクセスできません。 呼び出し元は呼び出し元に共有する必要があります。|
|外部通話での1:1 通話             |[発信者]                 |発信者の OneDrive for business アカウント                        |発信者は所有者であり、すべての権限が与えられています。<br /> <br />呼び出し先にアクセスできません。 呼び出し元は呼び出し元に共有する必要があります。|
|外部通話での1:1 通話             |[呼び出し先]                 |呼び出し先の OneDrive for business アカウント                        |呼び出し先は所有者であり、完全な権限を持ちます。<br /><br />発信者にはアクセスできません。 呼び出し元は呼び出し元に共有する必要があります。|
|グループ通話                                 |通話の任意のメンバー |レコードの OneDrive for Business アカウントをクリックしたメンバー  |レコードをクリックしたメンバーには、すべての権限があります。 <br /><br /> 同じテナントの他のメンバーには読み取り権限があります。 <br /><br /> 別のテナントの他のメンバーには、権限がありません。|
|アドホック/スケジュールされた会議                    |[開催者]              |開催者の OneDrive for business アカウント                     |開催者はレコーディングへのフル権限を持っています。 <br /><br /> 会議の他のすべてのメンバーには、読み取りアクセス権があります。|
|アドホック/スケジュールされた会議                    |その他の会議メンバー   |レコードをクリックしたメンバー                                  |レコードをクリックしたメンバーには、レコーディングへのフル権限があります。 <br /><br />開催者は編集権限を持ち、共有できます。<br /><br /> 他のすべてのメンバーには読み取りアクセス権があります。|
|外部ユーザーとのアドホック/スケジュールされた会議|[開催者]              |開催者の OneDrive for business アカウント                     |開催者はレコーディングへのフル権限を持っています。<br /> <br /> 開催者と同じテナントの他のすべてのメンバーが、読み取りアクセス権を持っている。 <br /><br /> 他のすべての外部メンバーにはアクセス権がなく、開催者はそれらを共有する必要があります。|
|外部ユーザーとのアドホック/スケジュールされた会議|その他の会議メンバー   |レコードをクリックしたメンバー                                  |レコードをクリックしたメンバーには、レコーディングへのフル権限があります。 開催者は編集権限を持ち、共有できます。 <br /><br /> 開催者と同じテナントの他のすべてのメンバーが、読み取りアクセス権を持っている。 <br /><br />他のすべての外部メンバーにはアクセス権がなく、開催者はそれらを共有する必要があります。|
|チャネル会議                            |チャネルメンバー         |そのチャネル用の Teams の SharePoint の場所                   |レコードをクリックしたメンバーには、レコーディングの編集権限があります。 <br /> <br />他のすべてのメンバーのアクセス許可は、チャネルの SharePoint アクセス許可に基づいています。|

## <a name="frequently-asked-questions"></a>よく寄せられる質問

**会議のレコーディングはどこに保存されますか?**

- チャネル以外の会議の場合、レコーディングは、会議のレコーディングを開始したユーザーに属している OneDrive for Business の最上位レベルの **レコーディング** という名前のフォルダーに格納されます。 例:

  <i>レコーダーの OneDrive For business</i> /**レコーディング**

- チャネル会議の場合、レコーディングは [ **レコーディング**] という名前のフォルダーにある Teams サイトのドキュメントライブラリに格納されます。 例:

  <i>Teams 名-チャネル名</i> /**ドキュメント** /**レコーディング**

**元従業員のレコーディングを処理する方法を教えてください。**

ビデオは、OneDrive for Business および SharePoint の他のファイルと同様に、従業員が退職した後の所有と保持は、通常の [onedrive for business と sharepoint のプロセス]( https://docs.microsoft.com/onedrive/retention-and-deletion#the-onedrive-deletion-process)に従っています。

**会議のレコーディングを表示する権限を持つユーザー**

- チャネル以外の会議の場合、外部ユーザーを除くすべての会議出席者は、自動的に個別の共有リンクを取得します。 外部ユーザーは、会議の開催者、または会議のレコーディングを開始したユーザーによって、共有リストに明示的に追加される必要があります。

- チャネル会議の場合、アクセス許可はチャネルの所有者とメンバーの一覧から継承されます。

**トランスクリプトを管理する方法を教えてください。**

このプレビューを有効にすると、OneDrive for Business および SharePoint に移行された、チーム会議のレコーディングで利用可能なクローズドキャプションは表示されません。英語のキャプションから、第4四半期の CY2020 での会議のレコーディングまで、キャプションを追加するための作業を行っています。

[Teams のクラウドレコーディング](cloud-recording.md)で説明されているように、トランスクリプトを許可することを選択しているお客様のために、クローズドキャプションが Teams の会議レコーディングで利用可能になる

キャプションを使用すると、すべてのアビリティーについて包括的なコンテンツを作成することができます。 所有者としては、キャプションを非表示にすることができます。ただし、Teams からキャプションを削除しない限り、そのトランスクリプトはまだ Teams で利用できます。 [会議のレコーディングをオンまたはオフにする方法を確認する](cloud-recording.md#set-up-teams-cloud-meeting-recording-for-users-in-your-organization)

クローズドキャプションは、会議が記録された時点からの、60日間の Teams 会議レコーディングでサポートされています。

OneDrive for Business または SharePoint 上の元の場所から Teams 会議のレコーディングが移動またはコピーされている場合、クローズドキャプションは完全にサポートされません。

**記憶域のクォータはどのように影響されますか?**

Teams 会議のレコーディングファイルは、OneDrive for Business と SharePoint に保存されており、これらのサービスのクォータに含まれています。 「 [SharePoint クォータ](https://docs.microsoft.com/sharepoint/sites/plan-site-maintenance-and-management#quotas) と [OneDrive for business のクォータ](https://docs.microsoft.com/onedrive/set-default-storage-space)」を参照してください。

SharePoint では、Stream とより多くの fungible ストレージを使用して、 [OneDrive For business](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits) でさらに多くの記憶域を利用できます。

**Teams 会議のレコーディングを再生するにはどうすればよいですか?**

ビデオは、ファイルにアクセスした場所に応じて、OneDrive for Business または SharePoint のビデオプレーヤーで再生されます。

**おけるをストリームに追加する予定の場合、既存のビデオはそのままで、どれだけの時間がかかりますか?**

近い将来、プラットフォームとしてのストリームは廃止されることはありません。 現在ストリーム内に存在するビデオは、移行を開始するまでそのまま残ります。 これらのビデオは、移行時に OneDrive for Business または SharePoint にも移行されます。 詳細について [は、ここ](https://docs.microsoft.com/stream/streamnew/classic-migration) を確認してください。

**保持ラベルを適用する方法を教えてください。**

[保持ラベルを自動適用する方法に](https://docs.microsoft.com/microsoft-365/compliance/apply-retention-labels-automatically?view=o365-worldwide#microsoft-teams-meeting-recordings)ついて説明します。

**Microsoft Teams でユーザーにポリシーを割り当てる方法と、どのポリシーが優先されるか**

[どのポリシーが優先されるかを](https://docs.microsoft.com/MicrosoftTeams/assign-policies#which-policy-takes-precedence)確認します。
