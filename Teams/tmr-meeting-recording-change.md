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
ms.openlocfilehash: d1072f86d019415dbc97d0507ff9d76b2cbdc6e6
ms.sourcegitcommit: 5c232ab2dfe4374ac69701241e55b05b8de8eb3e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2020
ms.locfileid: "48269641"
---
# <a name="use-onedrive-for-business-and-sharepoint-or-stream-for-meeting-recordings"></a>OneDrive for Business と、会議の記録に SharePoint または Stream を使用する

> [!Note]
> Microsoft Stream の使用から 会議の記録用の OneDrive for Business および SharePoint への変更は段階的なアプローチになります。 テナント管理者は、起動時にこの新しいワークフローオプションを今すぐ選ぶことができます。また、2020年10月に OneDrive for Business と SharePoint に自動アップロードされます。 11月では、Stream の使用を続けたい場合と、2021の初期段階では、すべてのユーザーが OneDrive for Business と SharePoint を使って新しい会議のレコーディングを使用する必要があります。

Microsoft Teams には、会議の記録を保存するための新しい方法が用意されています。 ストリームからの出発として、このメソッドは microsoft 365 の Microsoft OneDrive と SharePoint を使用し、多くの利点を提供します。

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

    a. [Skype For Business Online Powershell](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide)をダウンロードします。

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

ポリシーで既に **Stream**に設定されている場合でも、設定されていない可能性があります。 Nothing に設定されている場合、既定値は Stream です。 除外する場合は、ストリームが既定値になるように、ポリシーを**ストリーム**にリセットする**必要があり**ます。

```PowerShell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "Stream"
```

## <a name="frequently-asked-questions"></a>よく寄せられる質問

**会議のレコーディングはどこに保存されますか?**

- チャネル以外の会議の場合、レコーディングはという名前のフォルダーに格納されます。 レコーディング * * は、会議のレコーディングを開始したユーザーに属している OneDrive の最上位レベルにあります。 例:

  <i>レコーダーの OneDrive For business</i> /**レコーディング**

- チャネル会議の場合、レコーディングは [ **レコーディング**] という名前のフォルダーにある Teams サイトのドキュメントライブラリに格納されます。 例:

  <i>Teams 名-チャネル名</i> /**ドキュメント** /**レコーディング**

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
