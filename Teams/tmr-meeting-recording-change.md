---
title: OneDrive for Business と SharePoint を使用して会議の記録を行う
author: cichur
ms.author: v-cichur
ms.reviewer: hao.moy
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Microsoft Teams で Stream から OneDrive for Business および SharePoint meeting の記録ストレージに切り替える方法について説明します。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: d18f6b5ef5b4668324a68b4456cd3ad5aa4b7364
ms.sourcegitcommit: 113f587a1c09d42b7394ba1195c32cb054bdf31c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2021
ms.locfileid: "50507980"
---
# <a name="use-onedrive-for-business-and-sharepoint-or-stream-for-meeting-recordings"></a>OneDrive for Business と SharePoint または Stream を使用して会議の記録を行う

> [!Note]
> Microsoft Stream から 会議の記録用の OneDrive for Business および Microsoft SharePoint への変更は段階的なアプローチになります。

|<div style="width:290px">日付&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</div> |イベント&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;                                                                                                                                                                                                                                                                                                             |
|:-----------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|2020 年 10 月 5 日<br> <br>*(完了)*&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;| Teams 会議ポリシーを有効にして、Microsoft Stream (クラシック) の代わりに OneDrive for Business と SharePoint に会議の記録を保存する|
|2021年1月7日より開始 <br> <br>*(完了)*&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|組織の Teams 会議ポリシーを変更し、それを明示的に **Stream** に設定することで、この変更を後回しにしない限り、すべての新しい Teams 会議の記録を OneDrive for Business と SharePoint に保存します。 Stream をポリシーで報告するだけでは十分ではありません。 ポリシー値を明示的に **Stream** に設定する必要があります。|
|2021年1月11日より開始 <br> <br>*(完了)*&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**GCC のみ**<br> GCC をご利用のお客様は、10 月 5 日からオプトアウトすることはできますが、オプト インすることはできません。 この機能は、(オプトアウト) を使用していない場合、2021 年 1 月 11 日以降のすべての GCC ユーザーにロールアウトされます。<br>  <br>2021 年 1 月 11 日から、GCC をご利用のお客様は、組織の Teams 会議ポリシーを変更し、それを明示的に **Stream** に設定することによって、この変更を遅らせない限りは、Teams の会議記録はすべて OneDrive for Business と SharePoint に保存されます。 <br><br>オプトアウトしても、この機能を有効にする準備ができたら、Teams の会議ポリシーを明示的に **OneDrive for Business** に設定することで、この機能を有効にすることができます。 |
|2021 年 3 月 1 日からロールアウト開始 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**GCC-High および DoD のみ**<br> お客様は、Microsoft Teams で初めてクラウド会議の記録を有効にすすむ機能が追加されています。 これらのレコーディングは、既定で OneDrive と SharePoint に保存および再生されます。 |
|2021 年 7 月 7 日から段階的に展開する &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**すべてのお客様 (エンタープライズ、教育、GCC)**<br>**Microsoft Stream (クラシック) には、新しい会議の記録を保存できません。ユーザーがをチームの会議ポリシーを Stream に変更した場合でも、すべての顧客の会議記録は、OneDrive for Business と SharePoint に自動的に保存されます。**<br><br> ユーザーがリリースのタイミングを制御できるように、この日付より前にこの機能のロール アウトをすることをお勧めします。 |

> [!Note]
> エンタープライズおよび教育機関のお客様は、組織の変化をより効果的に管理するために、変更が可能になるまで待つよりも、変更するのが都合が良いタイミングでオプト インすることをお薦めします。

Microsoft Teams には、会議の記録を保存するための新しい方法があります。 従来の Microsoft Stream から[新しい Stream](https://docs.microsoft.com/stream/streamnew/new-stream) への移行の最初のフェーズとして、このメソッドは Microsoft 365 の Microsoft OneDrive for Business と SharePoint に記録を保存し、多くの利点を提供します。

記録の保存に OneDrive for Business と SharePoint を使用すると、次のような利点があります。

- Teams 会議記録 (TMR) (S + C E5 自動保持ラベル) 用アイテム保持ポリシー
- OneDrive for Business と SharePoint information ガバナンスの恩恵を受ける
- アクセス許可と共有を簡単に設定
- 明示的な共有のみを使用してゲスト (外部ユーザー) とレコーディング を共有する
- アクセス フローを要求する
- OneDrive for Business と SharePoint 共有リンクを提供する
- 会議の記録をより早く使用できるようにする
- **ローカルにする** テナントへのサポート
- 複数地域のサポート – 記録はそのユーザーに固有の地域に格納されます。
- 独自のキー (BYOK) サポートを利用する

サービスにはいくつかの制約事項があります。

- 英語専用のクローズド キャプションが表示され、キャプションをオフ/オンに切り替えできます。
- 完全な *トランスクリプトの* 表示、編集、検索は、最初は行えなっていません (ただし、この機能の追加は間もなく行っています)。
- トランスクリプトは編集できませんが、キャプションのオン/オフを切り替えることができます。
- 記録を共有するユーザーを制御することはできますが、共有アクセス権を持つユーザーが記録をダウンロードできないようにすることはできません。
- 記録の保存が完了しても、メールは送信されません。完了したレコーディングは、会議のチャットに表示されます。 以前の Stream と比べてはるかに早くなります。

詳細については、「会議の記録」を参照してください。

> [!VIDEO https://www.youtube.com/embed/8iol0KfCeL8]

## <a name="set-up-the-meeting-recording-option-for-onedrive-for-business-and-sharepoint"></a>OneDrive for Business および SharePoint の会議の記録オプションをセットアップする

[会議の記録] オプションは、チーム ポリシー レベルの設定です。 次の例では、グローバル ポリシーの設定方法を示しています。 ユーザーに割り当てたポリシーに対して、[会議の記録] オプションが設定されていることを確認します。

> [!Note]
> Teams の会議ポリシー変更の反映にはしばらく時間がかかります。 設定して数時間後に確認してください。もう一度サインアウトしてサインインし直してください。

1. Skype for Business Online PowerShell のインストール

   > [!NOTE]
   > Skype for Business Online Connector は現在、最新の Teams PowerShell モジュールに含まれています。 最新の Teams PowerShell パブリック リリースをご利用の場合は、Skype for Business Online Connector をインストールする必要はありません。 「[PowerShell を使用する Skype for Business Online を管理する](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide&preserve-view=true)」を参照してください。

    1. [Skype for Business Online PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide&preserve-view=true)をダウンローします。

    1. 指示に従ってインストールします。

    1. コンピューターを再起動する

2. 管理者として PowerShell を起動します。

3. SkypeOnline Connector をインポートし、Teams 管理者としてサインインします。

   ```powershell
   Import-Module MicrosoftTeams
   $sfbSession = New-CsOnlineSession
   Import-PSSession $sfbSession
   ```

4. [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) を使用して、Teams 会議ポリシーを設定し、Stream ストレージから OneDrive for Business と SharePoint に切り替えます。

   ```powershell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "OneDriveForBusiness"
   ```

> [!Note]
> ユーザーの中に、開催者単位またはユーザー単位のポリシーが割り当てられているユーザーがいる場合は、ポリシーのこの設定を設定して、OneDrive for Business と SharePoint で会議の記録を保存できるようにする必要があります。 詳細については、「[Teams での会議ポリシーを管理する](meeting-policies-in-teams.md)」を参照してください。

## <a name="opt-out-of-onedrive-for-business-and-sharepoint-to-continue-using-stream"></a>OneDrive for Business と SharePoint をオプトアウトして Stream の使用を継続する

ポリシーによって **Stream** に設定されているはずの場合でも、設定されていない可能性があります。 通常、ポリシーが設定されていない場合、既定の設定は **Stream** です。 ただし、この新しい変更では、SharePoint や OneDrive for business の使用をオプト アウトする場合は、**stream** が既定であることを確認するために、ポリシーを **Stream** に再設定する必要があります。

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "Stream"
```

## <a name="permissions-or-role-based-access"></a>アクセス許可とロール ベースのアクセス

> [!Note]
> Teams 会議の記録を共有する場合は、受信者がログインしている状態にすることをお勧めします。 「[SharePoint ファイルまたはフォルダーを共有する](https://support.microsoft.com/office/share-sharepoint-files-or-folders-1fe37332-0f9a-4719-970e-d2578da4941c?redirectSourcePath=%25252fen-US%25252farticle%25252fShare-sites-or-documents-with-people-outside-your-organization-80E49744-E30F-44DB-8D51-16661B1D4232&ui=en-US&rs=en-US&ad=US)」 に記載されているようにファイルを共有するときは、[**ユーザー (所属組織内)**] オプションを選択します。 外部共有は、サイズの大きいファイルや大量のファイルを配布するためのものではありません。 外部ユーザーに大量のデータを共有するときに詐欺と悪用のシナリオを防ぐ関連で、問題が発生することがあります。

|会議の種類                               | レコードをクリックしたのは誰ですか?| 記録はどこにありますか?                               |誰にアクセス権が与えられるか? R/W、R、または共有                                                                                                                                                                                                                                                     |
|-------------------------------------------|-----------------------|--------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|社内関係者との １ 対 １ の通話             |発信者                 |発信者の OneDrive for Business アカウントです。                        |発信者は所有者であり、完全なアクセス権限を持っています。 <br /><br />(同じテナント内の) 受信者には読み取り専用アクセス権が与えられます。 共有アクセスはありません。 <br /><br /> (別のテナントの場合) 受信者にはアクセス権がありません。 発信者は受信者にそれを共有する必要があります。|
|社内関係者との １ 対 １ の通話             |受信者                 |受信者の OneDrive for Business アカウントです。                        |受信者は所有者であり、完全なアクセス権限を持っています。 <br /><br />発信者 (同じテナントの場合は読み取り専用アクセス権がある場合)。 共有アクセスはありません。 <br /><br />(別のテナントの場合) 発信者はアクセス権を持っていません。 発信者に共有する必要があります。|
|外部通話を使用した １ 対 １ の通話             |発信者                 |発信者の OneDrive for Business アカウントです。                        |発信者は所有者であり、完全なアクセス権限を持っています。<br /> <br />受信者にはアクセス権がありません。 発信者は受信者にそれを共有する必要があります。|
|外部通話を使用した １ 対 １ の通話             |受信者                 |受信者の OneDrive for Business アカウントです。                        |受信者は所有者であり、完全なアクセス権限を持っています。<br /><br />発信者にはアクセス権がありません。 受信者は発信者に共有する必要があります。|
|グループ通話                                 |通話のいずれかのメンバー |レコードの OneDrive for Business アカウントをクリックしたグループ メンバー  |レコードをクリックしたメンバーは完全な権限を持っています。 <br /><br /> 同じテナントの他の fr には読み取り権限があります。 <br /><br /> 異なるテナントの他のグループ メンバーには、その権限はありません。|
|アドホック/スケジュールされた会議                    |開催者              |開催者の OneDrive for Business アカウントです。                     |開催者は記録に対して完全な権限を持ちます。 <br /><br /> 会議の他のメンバー全員が読み取りアクセス権を持ちます。|
|アドホック/スケジュールされた会議                    |その他の会議メンバー   |[レコード] をクリックした会議メンバー                                  |レコードをクリックしたメンバーには、記録への完全なアクセス権があります。 <br /><br />開催者は編集の権利を持ち、共有できます。<br /><br /> 他のすべての会議メンバーは読み取りアクセス権を持っています。|
|外部ユーザーとのアドホック/予定された会議|開催者              |開催者の OneDrive for Business アカウントです。                     |開催者は記録に対して完全な権限を持ちます。<br /> <br /> 開催者と同じテナントのすべての会議メンバーは、読み取りアクセス権を持ちます。 <br /><br /> 他のすべての外部メンバーにはアクセス権がありません。開催者はそれを共有する必要があります。|
|外部ユーザーとのアドホック/予定された会議|その他の会議メンバー   |レコードをクリックしたメンバー                                  |レコードをクリックしたメンバーには、記録への完全なアクセス権があります。 開催者は編集の権利を持ち、共有できます。 <br /><br /> 開催者と同じテナントのすべての会議メンバーは、読み取りアクセス権を持ちます。 <br /><br />他のすべての外部メンバーにはアクセス権がありません。開催者はそれを共有する必要があります。|
|チャネル会議                            |チャネル メンバー         |そのチャネルの Teams の SharePoint の場所                   |レコードをクリックしたメンバーには、記録の編集権限があります。 <br /> <br />他のすべてのメンバーの権限は、Channel SharePoint の権限に基づいて設定されます。|

## <a name="frequently-asked-questions"></a>よく寄せられる質問

**会議の記録はどこに保存されますか?**

- チャネル以外の会議の場合、記録は **レコーディング** という名前のフォルダーに格納されており、 これは会議の記録を開始したユーザーに属している OneDrive for Business の最上位のレベルです。 例: 

  <i>レコーダーの OneDrive for Business</i>/**レコーディング**

- チャネル会議については、記録は、 **レコーディング** という名前のフォルダーにある Teams サイトのドキュメント ライブラリに格納されます。 例: 

  <i>Teams 名 - チャネル名</i>/**ドキュメント**/**記録**

**Stream ファイル (レコーディングなど) が SharePoint/OneDrive に保存されている場合、どこに移動するかはどのようにして決定されますか?管理者は行き先を変更できますか?**

既定では、すべての記録ファイルは、[レコード] を選択したユーザーの OneDrive アカウントに移動 **します**。 チャネル会議の場合、記録は常にチャネルの SharePoint サイトに移動します。 管理者は記録の保存場所を変更できない。

**元従業員の記録を処理するにはどうすればよいですか?**

ビデオは、OneDrive for Business と SharePoint の他のファイルと同じであるため、従業員が退職した後の所有権と保持は、通常の「[OneDrive for business および SharePoint プロセス]( https://docs.microsoft.com/onedrive/retention-and-deletion#the-onedrive-deletion-process)」に従います。

**会議の記録を表示するためのアクセス許可を持つユーザーは誰ですか?**

- チャネル以外の会議では、外部ユーザーを除くすべての会議出席者が、自動的に個人の共有リンクを取得します。 外部ユーザーは、会議の開催者または会議の記録を開始したユーザーが、共有リストに明示的に追加する必要があります。

- チャネル会議の場合、アクセス許可はチャネルの所有者とメンバーの一覧から継承されます。

**トランスクリプトを管理するにはどうすればよいですか?**

お客様がこのプレビューを選択しても、OneDrive for Business と SharePoint に移行された Teams会議の記録にクローズド キャプションは利用可能ではありません。 現在キャプション追加の作業中です。英語のクローズド キャプションから始めて、CY2020 第 4 半期の会議の記録にキャプションを追加します。

[[Teams のクラウド記録](cloud-recording.md)] に記載されているように、議事録を許可しているお客様のためにTeams 会議記録のクローズド キャプションを使用することができるようになります。

キャプションを使用すると、障害者も健常者も含めすべての視聴者に対して包括的コンテンツを作成できます。 所有者は、キャプションを非表示にすることができます。トランスクリプトは、Teams のキャプションを削除しない限り、Teams で引き続き使用できます。 「[会議の記録をオンまたはオフにする方法](cloud-recording.md#set-up-teams-cloud-meeting-recording-for-users-in-your-organization)」 を参照してください。

Teams 会議記録のクローズド キャプションは、会議が記録された時点からの 60 日間サポートされています。

Teams 会議の記録を元の場所から、OneDrive for Business または SharePoint 上に移動またはコピーした場合、クローズド キャプションは完全にサポートされません。

**記憶域のクォータにどのような影響がありますか?**

Teams 会議の記録ファイルは、OneDrive for Business と SharePoint の中にあり、これらのサービスのクォータに含まれています。 詳細については、「[SharePoint のクォータ](https://docs.microsoft.com/sharepoint/sites/plan-site-maintenance-and-management#quotas)」および「[OneDrive for Businessのクォータ](https://docs.microsoft.com/onedrive/set-default-storage-space)」を参照してください。

[OneDrive for Business](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)を使用すると、Stream よりも多くのストレージを使用できます。 SharePoint.を使うと代替可能なストレージをもっと入手できます。

**会議の記録を再生するにはどうすればよいですか?**

ファイルにどこからアクセスするかによって、ビデオは、OneDrive for Business または SharePoint のビデオプレーヤーで再生されます。

**もしStreamに追加することを避難するつもりなら、既存のビデオは今のままで利用できますか、いつまで使用できますか?**

Stream は、近い将来プラットフォームとして廃止の予定はありません。 現在、Stream に存在するビデオは、移行を開始するまで残っています。 移行すると、これらのビデオも OneDrive for Business または SharePoint に移行されます。 詳細については、「[Stream クラシックの移行](https://docs.microsoft.com/stream/streamnew/classic-migration)」を参照してください。

**保持ラベルを適用するにはどうすれば良いですか?**

「[保持ラベルを自動適用する方法](https://docs.microsoft.com/microsoft-365/compliance/apply-retention-labels-automatically?view=o365-worldwide#microsoft-teams-meeting-recordings)」を参照してください。

**Microsoft Teams のユーザーにポリシーを割り当てるにはどうすればよいですか、どのポリシーを優先すべきですか?**

「[どのポリシーが優先されますか?](https://docs.microsoft.com/MicrosoftTeams/assign-policies#which-policy-takes-precedence)」を参照してください。
