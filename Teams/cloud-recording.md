---
title: Teams のクラウド会議の記録
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
ms.reviewer: sonua
search.appverid: MET150
description: Microsoft Teams でクラウド音声機能を展開するための実用的なガイダンス。
appliesto:
- Microsoft Teams
ms.openlocfilehash: bd749e00966c21677019d5d68d12e88287e96b45
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36237032"
---
# <a name="teams-cloud-meeting-recording"></a>Teams のクラウド会議の記録

Microsoft Teams では、ユーザーはチーム会議やグループ通話を記録して、音声、ビデオ、画面共有のアクティビティをキャプチャすることができます。 自動的に文字起こしする記録のオプションもあるため、ユーザーはミーティングの記録を字幕付きで再生して、会議内容の重要な議題を検索できます。 記録はクラウドで行われ、 [Microsoft Stream](https://docs.microsoft.com/stream/)に保存されるため、ユーザーは組織全体で安全に共有することができます。

関連: [Teams 会議でのエンドユーザー向けドキュメントの記録](https://aka.ms/recordmeeting)

## <a name="prerequisites-for-teams-cloud-meeting-recording"></a>Teams クラウド会議レコーディングの前提条件

チームユーザーの会議を記録するには、テナントに対して Microsoft Stream を有効にする必要があります。 さらに、会議の開催者とレコーディングを開始するユーザーの両方に対して、次の前提条件が必要になります。

- ユーザーには、Office 365 E1、E3、E5、A1、A3、A5、M365 Business、Business Premium または Business Essentials が含まれています。
- ユーザーは Microsoft Stream のライセンスが必要です
- ユーザーは Microsoft Stream アップロードのビデオアクセス許可を持っています
- ユーザーは管理者によって設定されている場合、会社のガイドラインに各人しました。
- レコーディングを保存するために Microsoft Stream に十分なストレージがあるユーザー
- ユーザーには TeamsMeetingPolicy/AllowCloudRecording 設定が true に設定されています
- ユーザーは、会議の匿名、ゲスト、またはフェデレーションユーザーではありません

> [!NOTE]
> さらに、レコーディングを開始するユーザーがレコーディングを自動的に議事録に追加するかどうかを選択できるようにするには、ユーザーの TeamsMeetingPolicy/AllowTranscription 設定を true に設定する必要があります。

## <a name="set-up-teams-cloud-meeting-recording-for-users-in-your-organization"></a>組織内のユーザーに対して Teams クラウド会議のレコーディングを設定する

このセクションでは、Teams 会議の記録を設定および計画する方法について説明します。

### <a name="enable-microsoft-stream-for-users-in-the-organization"></a>組織内のユーザーに対して Microsoft Stream を有効にする

Microsoft Stream は、有効な Office 365 サブスクリプションの一部として、またはスタンドアロンサービスとして利用できます。  詳細については、「[ストリームライセンスの概要](https://docs.microsoft.com/stream/license-overview)」を参照してください。  Microsoft Stream は、Microsoft 365 Business、Office 365 Business Premium、および Office 365 Business Essentials に含まれるようになりました。

ユーザーが Microsoft Stream にアクセスできるように[Office 365 のユーザーにライセンスを割り当てる](https://support.office.com/article/Assign-licenses-to-users-in-Office-365-for-business-997596B5-4173-4627-B915-36ABAC6786DC)方法について説明します。 [この記事](https://docs.microsoft.com/stream/disable-user-organization)で定義されているように、ユーザーに対して Microsoft Stream がブロックされていないことを確認します。

### <a name="ensure-that-users-have-upload-video-permissions-in-microsoft-stream"></a>ユーザーが Microsoft Stream のビデオのアクセス許可をアップロードできることを確認する

既定では、Stream を有効にしてライセンスがユーザーに割り当てられると、社内のすべてのユーザーが Stream でコンテンツを作成することができます。 Microsoft Stream 管理者は、Stream で[のコンテンツ作成を制限](https://docs.microsoft.com/stream/restrict-uploaders)できます。 この制限付きリストに登録されているユーザーは、会議を記録できません。

### <a name="notify-employees-to-consent-to-company-guidelines-in-microsoft-stream"></a>Microsoft Stream の会社ガイドラインに同意するよう従業員に通知する

Microsoft Stream 管理者が[会社ガイドラインポリシーを設定](https://docs.microsoft.com/stream/company-policy-and-consent)しており、コンテンツを保存する前に従業員がこのポリシーを承認する必要がある場合、ユーザーは microsoft Teams でレコーディングを行う必要があります。 組織でレコーディング機能を展開する前に、ユーザーがポリシーに各人していることを確認します。

### <a name="turn-on-or-turn-off-cloud-recording"></a>クラウドの記録を有効または無効にする

Teams PowerShell の TeamsMeetingPolicy で AllowCloudRecording を使用して、ユーザーの会議を記録することを許可するかどうかを制御します。 TeamsMeetingPolicy を Office 365 PowerShell で管理する方法については、[こちら](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)を参照してください。

会議の開催者とレコーディングの開始者の両方が、会議を記録するための書き込みアクセス許可を持っている必要があることに注意してください。 ユーザーにカスタムポリシーを割り当てていない場合、ユーザーはグローバルポリシーを取得します。これには、既定で AllowTranscription が無効になっています。

ユーザーがグローバルポリシーに戻すには、次のコマンドレットを使用して、ユーザーの特定のポリシー割り当てを削除します。

`Grant-CsTeamsMeetingPolicy -Identity {user} -PolicyName $null -Verbose`

グローバルポリシーで AllowCloudRecording の値を変更するには、次のコマンドレットを使用します。

`Set-CsTeamsMeetingPolicy -Identity Global -AllowCloudRecording $false`
</br>
</br>


|                                                                 シナリオ                                                                 |                                                                                                                                                                         手順                                                                                                                                                                          |
|------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                    社内のすべてのユーザーが会議を記録できるようにする                                    |                                                                     <ol><li>グローバル CsTeamsMeetingPolicy に AllowCloudRecording = True が含まれていることを確認する<li>すべてのユーザーは、AllowCloudRecording = True を持つグローバル CsTeamsMeetingPolicy または CsTeamsMeetingPolicy ポリシーのいずれかを使用しています </ol>                                                                     |
| ユーザーの大半が会議を記録できるようにしたいが、記録を許可されていない特定のユーザーを選択する |        <ol><li>GlobalCsTeamsMeetingPolicy に AllowCloudRecording = True が含まれていることを確認する<li>大部分のユーザーは、AllowCloudRecording = True を持つグローバル CsTeamsMeetingPolicy または CsTeamsMeetingPolicy ポリシーのいずれかを使用しています<li>他のすべてのユーザーに AllowCloudRecording = False の CsTeamsMeetingPolicy ポリシーのいずれかが付与されている</ol>         |
|                                                   レコーディングを 100% 無効にする                                                   |                                                                <ol><li>グローバル CsTeamsMeetingPolicy の確認 AllowCloudRecording = False<li>すべてのユーザーに、AllowCloudRecording = False を持つグローバル CsTeamsMeetingPolicy または CsTeamsMeetingPolicy ポリシーのいずれかが許可されている                                                                 |
|      大部分のユーザーに対してレコーディングを無効にして、記録を許可する特定のユーザーを選択する       | <ol><li>グローバル CsTeamsMeetingPolicy の確認 AllowCloudRecording = False<li>大部分のユーザーには、AllowCloudRecording = False を持つグローバル CsTeamsMeetingPolicy または CsTeamsMeetingPolicy ポリシーのいずれかが付与されています<li>他のすべてのユーザーに AllowCloudRecording = True の CsTeamsMeetingPolicy ポリシーのいずれかが付与されている <ol> |
|                                                                                                                                          |                                                                                                                                                                                                                                                                                                                                                        |

### <a name="turn-on-or-turn-off-recording-transcription"></a>レコーディングの議事録を有効または無効にする

ユーザーはチーム会議を記録したときに、会議が記録された後にトランスクリプトが自動生成されるかどうかを確認できます。 管理者が会議の開催者とレコーディングイニシエーターの議事録機能を無効にしている場合、レコーディングの開始者は、会議のレコーディングの議事録を設定することはできません。

Teams PowerShell の TeamsMeetingPolicy で AllowTranscription を使って、レコーディングの開始者が会議のレコーディングの議事録を行うかどうかを制御します。 TeamsMeetingPolicy を Office 365 PowerShell で管理する方法については、[こちら](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)を参照してください。

カスタムポリシーがユーザーに割り当てられていない場合は、グローバルポリシーを取得します。これには、既定で AllowTranscription が無効になっています。

ユーザーがグローバルポリシーに戻すには、次のコマンドレットを使用して、ユーザーの特定のポリシー割り当てを削除します。

`Grant-CsTeamsMeetingPolicy -Identity {user} -PolicyName $null -Verbose`

グローバルポリシーで AllowCloudRecording の値を変更するには、次のコマンドレットを使用します。

`Set-CsTeamsMeetingPolicy -Identity Global -AllowTranscription $false`
</br>
</br>

|シナリオ|手順 |
|---|---|
|社内のすべてのユーザーが、会議の記録を開始するときに議事録を表示できるようにする |<ol><li>グローバル CsTeamsMeetingPolicy の確認 AllowTranscription = True <li>すべてのユーザーには、csTeamsMeetingPolicy という CsTeamsMeetingPolicy ポリシーが含まれています。 </ol>|
|ユーザーの大半が会議の記録の議事録を行うことができるようにしたいが、議事録を許可されていない特定のユーザーを選択する |<ol><li>グローバル CsTeamsMeetingPolicy の確認 AllowTranscription = True <li>大部分のユーザーは、CsTeamsMeetingPolicy というグローバルな CsTeamsMeetingPolicy ポリシーを持っています。 <li>他のすべてのユーザーに AllowTranscription = False の CsTeamsMeetingPolicy ポリシーのいずれかが付与されています。 </ol>|
|レコーディングの議事録を 100% 無効にする |<ol><li>グローバル CsTeamsMeetingPolicy の確認 AllowTranscription = False <li>すべてのユーザーに AllowTranscription = False を使用してグローバル CsTeamsMeetingPolicy または CsTeamsMeetingPolicy ポリシーのいずれかが付与されている </ol>|
|ほとんどのユーザーに対して、議事録を無効にしたいが、議事録を許可された特定のユーザーを選択できるようにする |<ol><li>グローバル CsTeamsMeetingPolicy の確認 AllowCloudRecording = False <li>大部分のユーザーには、AllowCloudRecording = False を持つグローバル CsTeamsMeetingPolicy または CsTeamsMeetingPolicy ポリシーのいずれかが付与されています <li>他のすべてのユーザーに AllowCloudRecording = True の CsTeamsMeetingPolicy ポリシーのいずれかが付与されている </ol>|
|||

### <a name="planning-for-storage"></a>記憶域の計画

1時間の記録のサイズは 400 MB です。 記録されたファイルに必要な容量を理解していること、および Microsoft Stream で利用できる十分なストレージがあることを確認してください。  [この記事](https://docs.microsoft.com/stream/license-overview)では、サブスクリプションに含まれている基本記憶域と追加記憶域の購入方法について説明します。

## <a name="manage-meeting-recordings"></a>会議のレコーディングを管理する
会議のレコーディングは、テナントが所有しているコンテンツと見なされます。 レコーディングの所有者が退職した場合、管理者は、Microsoft Stream in 管理モードでレコーディングビデオの URL を開くことができます。 管理者は、レコーディングを削除したり、レコーディングメタデータを更新したり、レコーディングビデオのアクセス許可を変更したりできます。 [ストリームの管理機能の](https://docs.microsoft.com/stream/manage-content-permissions)詳細については、こちらを参照してください。

## <a name="compliance-and-ediscovery-for-meeting-recordings"></a>会議のレコーディングのコンプライアンスと電子情報開示
会議のレコーディングは、Office 365 Tier C に準拠している Microsoft Stream に保存されます。 Microsoft のストリームの会議または通話の記録に関心を持っているコンプライアンス管理者に対する e 検出要求をサポートするため、[レコーディング完了] メッセージは Microsoft Teams のコンプライアンスコンテンツ検索機能で利用できます。 コンプライアンス管理者は、コンプライアンスコンテンツ検索プレビューのアイテムの件名行に "レコーディング" というキーワードを検索して、組織内の会議と通話の記録を検出できます。 すべてのレコーディングを表示するには、Microsoft Stream で管理者アクセス権を設定する必要があることが前提となります。 詳しく[は、「Stream での管理権限の割り当て」を](https://docs.microsoft.com/stream/assign-administrator-user-role)ご覧ください。

## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell の詳細情報

Windows PowerShell では、ユーザーの管理と、許可または許可されていないユーザーの操作について説明します。 Windows PowerShell を利用すると、Office 365 と Skype for Business Online の管理を 1 か所で行うことができるので、複数のタスクを担当する管理者の日常業務を単純化できます。 Windows PowerShell には、Microsoft 365 管理センターを使用する場合にのみ、速度、シンプルさ、生産性を向上させるための多くの利点があります。たとえば、複数のユーザーに対して同時に設定を変更する場合です。 Windows PowerShell の使用を開始するには、次のトピックを参照してください。

- [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525041)
- [Windows PowerShell 用にコンピューターをセットアップする](https://go.microsoft.com/fwlink/?LinkId=525038)

