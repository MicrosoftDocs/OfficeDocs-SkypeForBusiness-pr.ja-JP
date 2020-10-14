---
title: 会議の記録に OneDrive と SharePoint を使用する
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
ms.openlocfilehash: 83a7a0628d76a96318081ec51a039d458ea1570f
ms.sourcegitcommit: c48a5aca37220ac6a797ac88b09cf80090b1b7df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "48444233"
---
# <a name="use-onedrive-for-business-and-sharepoint-or-stream-for-meeting-recordings"></a>OneDrive for Business と、会議の記録に SharePoint または Stream を使用する

> [!Note]
> 会議の記録用に Microsoft Stream を使用して OneDrive for Business と Microsoft SharePoint を使用するように変更した場合は、段階的なアプローチとなります。

|||
|---|-----------------|
|日付|イベント|
|初めての Q4 CY20|**OneDrive for Business および SharePoint での Teams 会議の記録は、オプトインまたはオプトアウトで利用できます。**<br> テナント管理者は、OneDrive for Business と SharePoint のオプトインまたは脱退を行うことができます。 PowerShell で Teams ポリシーを設定する|
|第 CY20 四半期中旬|**OneDrive for Business および SharePoint でのチーム会議の記録は、脱退しないテナントの既定として設定されます**<br> これは、ほとんどのお客様に推奨されるパスです。|
Q1 CY21|**Teams 会議の記録を従来のストリームに保存することはできなくなりました**<br>すべてのテナントが、Teams 会議の記録を OneDrive for Business と SharePoint に保存します|
|||

Microsoft Teams には、会議の記録を保存するための新しい方法が用意されています。 従来の Microsoft Stream から [新しいストリーム](https://docs.microsoft.com/stream/streamnew/new-stream)への移行の最初のフェーズとして、このメソッドは microsoft 365 の microsoft OneDrive と SharePoint 上にレコーディングを保存し、多くの利点を提供します。

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

1. Skype For Business Online PowerShell 管理コンソールをインストールします。

    a. [Skype For Business Online PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide)をダウンロードします。

    b. 指示に従ってインストールします。

    c. コンピューターを再起動します。

2. 管理者として PowerShell を起動する

3. SkypeOnline のコネクタをインポートして、Teams の管理者としてログインします。

```PowerShell
  Import-Module SkypeOnlineConnector
  $sfbSession = New-CsOnlineSession
  Import-PSSession $sfbSession
```

4. [Csteamsmeetingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)を使用して、ストリームストレージから odsp に切り替える Teams 会議ポリシーを設定します。

```PowerShell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "OneDriveForBusiness"
```

## <a name="opt-out-of-onedrive-for-business-and-sharepoint-to-continue-using-stream"></a>OneDrive for Business と SharePoint の使用を停止してストリームを継続する

ポリシーで **Stream**に設定されている場合でも、設定されていない可能性があります。 通常、ポリシーが設定されていない場合、既定の設定は **Stream**です。 ただし、この新しい変更では、SharePoint または OneDrive を使用しないようにする場合は、ポリシーを [ **ストリーム** ] にリセットして既定の状態に戻す必要があります。

```PowerShell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "Stream"
```

## <a name="frequently-asked-questions"></a>よく寄せられる質問

**会議のレコーディングはどこに保存されますか?**

- チャネル以外の会議の場合、レコーディングは、会議のレコーディングを開始したユーザーに属している OneDrive の最上位レベルの **レコーディング** という名前のフォルダーに格納されます。 例:

  <i>レコーダーの OneDrive For business</i> /**レコーディング**

- チャネル会議の場合、レコーディングは [ **レコーディング**] という名前のフォルダーにある Teams サイトのドキュメントライブラリに格納されます。 例:

  <i>Teams 名-チャネル名</i> /**ドキュメント** /**レコーディング**

**元従業員のレコーディングを処理する方法を教えてください。**

ビデオは、OneDrive や SharePoint の他のファイルと同様に、従業員が退職した後の所有と保持は、通常の [onedrive と sharepoint のプロセス]( https://docs.microsoft.com/onedrive/retention-and-deletion#the-onedrive-deletion-process)に従います。

**会議のレコーディングを表示する権限を持つユーザー**

- チャネル以外の会議の場合、外部ユーザーを除くすべての会議出席者は、自動的に個別の共有リンクを取得します。 外部ユーザーは、会議の開催者、または会議のレコーディングを開始したユーザーによって、共有リストに明示的に追加される必要があります。

- チャネル会議の場合、アクセス許可はチャネルの所有者とメンバーの一覧から継承されます。

**トランスクリプトを管理する方法を教えてください。**

このプレビューを有効にすると、OneDrive および SharePoint に移行されたチームの会議の記録にクローズドキャプションは表示されません。英語のキャプションから始まり、2020年10月の会議のレコーディングまで、キャプションを追加しています。

[Teams のクラウドレコーディング](cloud-recording.md)で説明されているように、トランスクリプトを許可することを選択しているお客様のために、クローズドキャプションが Teams の会議レコーディングで利用可能になる

キャプションを使用すると、すべてのアビリティーについて包括的なコンテンツを作成することができます。 所有者としては、キャプションを非表示にすることができます。ただし、Teams からキャプションを削除しない限り、そのトランスクリプトはまだ Teams で利用できます。 [会議のレコーディングをオンまたはオフにする方法を確認する](cloud-recording.md#set-up-teams-cloud-meeting-recording-for-users-in-your-organization)

クローズドキャプションは、会議が記録された時点からの、60日間の Teams 会議レコーディングでサポートされています。

**記憶域のクォータにどのように影響が及ぶか**

Teams 会議のレコーディングファイルは、OneDrive for Business と SharePoint に保存されており、これらのサービスのクォータに含まれています。 [SharePoint のクォータ](https://docs.microsoft.com/sharepoint/sites/plan-site-maintenance-and-management#quotas)と [OneDrive for business のクォータ] () を参照してください https://docs.microsoft.com/onedrive/set-default-storage-space) 。

**Teams 会議のレコーディングを再生するにはどうすればよいですか?**

ビデオは、ファイルにアクセスした場所に応じて、OneDrive for Business または SharePoint のビデオプレーヤーで再生されます。

**おけるをストリームに追加する予定の場合、既存のビデオはそのままで、どれだけの時間がかかりますか?**

近い将来、プラットフォームとしてのストリームは廃止されることはありません。 現在ストリーム内に存在するビデオは、移行を開始するまでそのまま残ります。 これらのビデオは、移行時にも ODSP に移行されます。 詳細について [は、ここ](https://docs.microsoft.com/stream/streamnew/classic-migration) を確認してください。
