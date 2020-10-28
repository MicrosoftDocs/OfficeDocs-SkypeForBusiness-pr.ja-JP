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
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0e57587ea428d8395b65553fc05d1964daa5fb61
ms.sourcegitcommit: a1524afb546fde9844f53390fab85e7073da8cb2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/28/2020
ms.locfileid: "48778860"
---
# <a name="use-onedrive-for-business-and-sharepoint-or-stream-for-meeting-recordings"></a>OneDrive for Business と、会議の記録に SharePoint または Stream を使用する

> [!Note]
> 会議の記録用に Microsoft Stream を使用して OneDrive for Business と Microsoft SharePoint を使用するように変更した場合は、段階的なアプローチとなります。


|日付|イベント|
|---|-----------------|
|初めての Q4 CY20|**OneDrive for Business および SharePoint での Teams 会議の記録は、オプトインまたはオプトアウトで利用できます。**<br> テナント管理者は、OneDrive for Business と SharePoint のオプトインまたは脱退を行うことができます。 PowerShell で Teams ポリシーを設定する|
|第 CY20 四半期中旬|**OneDrive for Business および SharePoint でのチーム会議の記録は、脱退しないテナントの既定として設定されます**<br> これは、ほとんどのお客様に推奨されるパスです。|
|Q1 CY21|**Teams 会議の記録を従来のストリームに保存することはできなくなりました**<br>すべてのテナントが、Teams 会議の記録を OneDrive for Business と SharePoint に保存します|

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

> [!Note]
> [会議レコーディング] オプションは、Teams のポリシーレベルで設定します。 次の例は、グローバルポリシーを設定する方法を示しています。 ユーザーに割り当てたポリシーの [会議レコーディング] オプションが設定されていることを確認してください。
> Teams の会議ポリシーの変更は、反映されるまでしばらくかかります。 設定が完了したら、もう一度サインアウトしてから、もう一度サインインします。

1. Skype For Business Online PowerShell をインストールします。
**注** : Skype For Business Online Connector は現在、最新の Teams PowerShell モジュールに含まれています。 最新の Teams PowerShell パブリックリリースを使用している場合は、Skype for Business Online Connector をインストールする必要はありません。 「 [PowerShell を使用して Skype For Business Online を管理する」を](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide&preserve-view=true)参照してください。

    a. [Skype For Business Online PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide&preserve-view=true)をダウンロードします。

    b. 指示に従ってインストールします。

    c. コンピューターを再起動します。

2. 管理者として PowerShell を起動する

3. SkypeOnline のコネクタをインポートして、Teams の管理者としてログインします。

   ```powershell
   Import-Module SkypeOnlineConnector
   $sfbSession = New-CsOnlineSession
   Import-PSSession $sfbSession
   ```

4. [Csteamsmeetingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps&preserve-view=true)を使用して、ストリームストレージから OneDrive for Business および SharePoint に切り替えるようにチーム会議ポリシーを設定します。

   ```powershell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "OneDriveForBusiness"
   ```

## <a name="opt-out-of-onedrive-for-business-and-sharepoint-to-continue-using-stream"></a>OneDrive for Business と SharePoint の使用を停止してストリームを継続する

ポリシーで **Stream** に設定されている場合でも、設定されていない可能性があります。 通常、ポリシーが設定されていない場合、既定の設定は **Stream** です。 ただし、この新しい変更では、SharePoint または OneDrive for Business を使用しないようにしたい場合は、ポリシーを [ **ストリーム** ] にリセットして既定の状態にしておく必要があります。

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "Stream"
```

## <a name="permissions-or-role-based-access"></a>権限またはロールベースのアクセス

|会議の種類                               | レコードをクリックしたユーザー| 記録はどこにありますか?                               |アクセス権を持つユーザー R/W、R、または共有                                                                                                                                                                                                                                                     |
|-------------------------------------------|-----------------------|--------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|社内関係者との1:1 通話             |[発信者]                 |発信者の OneDrive for business アカウント                        |発信者が所有者であり、完全な権限を持っている <br /><br />呼び出し元 (同じテナント内の場合) は読み取り専用アクセス権を持ち、共有アクセスはありません。 <br /><br /> 呼び出し先 (別のテナントの場合) にはアクセスできません。 呼び出し元は呼び出し元に共有する必要があります|
|社内関係者との1:1 通話             |[呼び出し先]                 |呼び出し先の OneDrive for business アカウント                        |呼び出し先が所有者であり、完全な権限を持つ <br /><br />発信者 (同じテナント内の読み取り専用のアクセス権を持っている場合は、共有アクセス権がありません) <br /><br />発信者 (別のテナントの場合) にアクセスできません。 呼び出し先は呼び出し先に共有する必要があります|
|外部通話での1:1 通話             |[発信者]                 |発信者の OneDrive for business アカウント                        |発信者が所有者であり、完全な権限を持っている<br /> <br />呼び出し先にアクセスできません。 呼び出し元は呼び出し元に共有する必要があります|
|外部通話での1:1 通話             |[呼び出し先]                 |発信者の OneDrive for business アカウント                        | 呼び出し先が所有者であり、完全な権限を持つ<br /><br />発信者にはアクセスできません。 呼び出し元は呼び出し元に共有する必要があります|
|グループ通話                                 |通話の任意のメンバー |レコードの OneDrive for Business アカウントをクリックしたメンバー  |レコードをクリックしたメンバーがすべての権限を持っているメンバー <br /><br /> 同じテナントの他のメンバーには読み取り権限があります <br /><br /> 別のテナントの他のメンバーには、権限がありません。|
|アドホック/スケジュールされた会議                    |[開催者]              |開催者の OneDrive for business アカウント                     | 開催者はレコーディングへのフル権限を持っています <br /><br /> 会議の他のすべてのメンバーが読み取りアクセス権を持っている|
|アドホック/スケジュールされた会議                    |その他の会議メンバー   |レコードをクリックしたメンバー                                  | レコードをクリックしたメンバーがレコーディングに対するフル権限を持っている <br />開催者は編集権限を持ち、共有できます <br /><br /> 他のすべてのメンバーには読み取りアクセス権がある|
|外部ユーザーとのアドホック/スケジュールされた会議|[開催者]              |開催者の OneDrive for business アカウント                     |開催者はレコーディングへのフル権限を持っています<br /> <br /> 開催者と同じテナントの他のすべてのメンバーが読み取りアクセス権を持っている <br /><br /> 他のすべての外部メンバーにはアクセスできません。開催者はそれらを共有する必要があります。|
|外部ユーザーとのアドホック/スケジュールされた会議|その他の会議メンバー   |レコードをクリックしたメンバー                                  | レコードをクリックしたメンバーは、レコーディングの編集権限を持ち、共有することができます。 <br /><br /> 開催者と同じテナントの他のすべてのメンバーが読み取りアクセス権を持っている <br /><br />他のすべての外部メンバーにはアクセスできません。開催者はそれらを共有する必要があります。|
|チャネル会議                            |チャネルメンバー         |そのチャネル用の Teams の SharePoint の場所                   | レコードをクリックしたメンバーには、レコーディングの編集権限があります <br /> <br />他のすべてのメンバーのアクセス許可は、チャネルの SharePoint アクセス許可に基づく|


## <a name="frequently-asked-questions"></a>よく寄せられる質問

**会議のレコーディングはどこに保存されますか?**

- チャネル以外の会議の場合、レコーディングは、会議のレコーディングを開始したユーザーに属している OneDrive for Business の最上位レベルの **レコーディング** という名前のフォルダーに格納されます。 例:

  <i>レコーダーの OneDrive For business</i> /**レコーディング**

- チャネル会議の場合、レコーディングは [ **レコーディング** ] という名前のフォルダーにある Teams サイトのドキュメントライブラリに格納されます。 例:

  <i>Teams 名-チャネル名</i> /**ドキュメント** /**レコーディング**

**元従業員のレコーディングを処理する方法を教えてください。**

ビデオは、OneDrive for Business および SharePoint の他のファイルと同様に、従業員が退職した後の所有と保持は、通常の [onedrive for business と sharepoint のプロセス]( https://docs.microsoft.com/onedrive/retention-and-deletion#the-onedrive-deletion-process)に従っています。

**会議のレコーディングを表示する権限を持つユーザー**

- チャネル以外の会議の場合、外部ユーザーを除くすべての会議出席者は、自動的に個別の共有リンクを取得します。 外部ユーザーは、会議の開催者、または会議のレコーディングを開始したユーザーによって、共有リストに明示的に追加される必要があります。

- チャネル会議の場合、アクセス許可はチャネルの所有者とメンバーの一覧から継承されます。

**トランスクリプトを管理する方法を教えてください。**

このプレビューを有効にすると、OneDrive for Business および SharePoint に移行された、チーム会議のレコーディングで利用可能なクローズドキャプションは表示されません。英語のキャプションから始まり、2020年10月の会議のレコーディングまで、キャプションを追加しています。

[Teams のクラウドレコーディング](cloud-recording.md)で説明されているように、トランスクリプトを許可することを選択しているお客様のために、クローズドキャプションが Teams の会議レコーディングで利用可能になる

キャプションを使用すると、すべてのアビリティーについて包括的なコンテンツを作成することができます。 所有者としては、キャプションを非表示にすることができます。ただし、Teams からキャプションを削除しない限り、そのトランスクリプトはまだ Teams で利用できます。 [会議のレコーディングをオンまたはオフにする方法を確認する](cloud-recording.md#set-up-teams-cloud-meeting-recording-for-users-in-your-organization)

クローズドキャプションは、会議が記録された時点からの、60日間の Teams 会議レコーディングでサポートされています。

OneDrive for Business または SharePoint 上の元の場所から Teams 会議のレコーディングが移動またはコピーされている場合、クローズドキャプションは完全にサポートされません。

**記憶域のクォータにどのように影響が及ぶか**

Teams 会議のレコーディングファイルは、OneDrive for Business と SharePoint に保存されており、これらのサービスのクォータに含まれています。 [SharePoint のクォータ](https://docs.microsoft.com/sharepoint/sites/plan-site-maintenance-and-management#quotas)と [OneDrive for business のクォータ] () を参照してください https://docs.microsoft.com/onedrive/set-default-storage-space) 。

**Teams 会議のレコーディングを再生するにはどうすればよいですか?**

ビデオは、ファイルにアクセスした場所に応じて、OneDrive for Business または SharePoint のビデオプレーヤーで再生されます。

**おけるをストリームに追加する予定の場合、既存のビデオはそのままで、どれだけの時間がかかりますか?**

近い将来、プラットフォームとしてのストリームは廃止されることはありません。 現在ストリーム内に存在するビデオは、移行を開始するまでそのまま残ります。 これらのビデオは、移行時に OneDrive for Business または SharePoint にも移行されます。 詳細について [は、ここ](https://docs.microsoft.com/stream/streamnew/classic-migration) を確認してください。

**保持ラベルを適用する方法を教えてください。**

[保持ラベルを自動適用する方法に](https://docs.microsoft.com/microsoft-365/compliance/apply-retention-labels-automatically?view=o365-worldwide#microsoft-teams-meeting-recordings)ついて説明します。
