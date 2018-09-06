---
title: チーム クラウドのミーティングのレコーディング
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
description: Microsoft Teams での Cloud Voice の機能の展開についての実践的なガイダンス
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6c1ca0045eb980a83852426b9c0b2c12f1e317f0
ms.sourcegitcommit: 33966ebb9ca3d922d47aaa9b9e3a2ddd26c320ca
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2018
ms.locfileid: "23845534"
---
# <a name="teams-cloud-meeting-recording"></a>チーム クラウドのミーティングのレコーディング

> [!Note]
> [!INCLUDE [preview-feature](includes/preview-feature.md)]

マイクロソフトのチームで、ユーザーは、チームの会議やオーディオ、ビデオ、およびアクティビティを共有する画面のキャプチャ グループの呼び出しを記録できます。 自動の議事録を記録するためのオプションをユーザーがクローズド キャプションおよび重要なディスカッション アイテムの検索とのミーティングのレコーディングで再生、トラン スクリプトです。 録音では、クラウドでの動作し、ユーザーを共有できるように、安全に組織全体に、[マイクロソフトのストリーム](https://docs.microsoft.com/stream/)に保存されます。

関連:[エンド ・ ユーザーのドキュメントを記録、チーム会議](https://aka.ms/recordmeeting)

## <a name="prerequisites-for-teams-cloud-meeting-recording"></a>チーム クラウドのミーティングのレコーディングのための前提条件

チーム ユーザーのミーティングを記録するのには、テナントのマイクロソフトのストリームを有効にする必要があります。 さらに、次の前提条件は、そのような会議の開催者と録音を開始したユーザーの両方に必要です。

- ユーザーが Office 365 のエンタープライズの E1、E3、E5 のライセンスを持っています。
- ユーザーが Microsoft のストリームのライセンスを取得する必要があります。
- ユーザーには Microsoft のストリーム ビデオのアクセス許可をアップロード
- ユーザーに同意した、会社のガイドラインでは場合、によって管理者の設定
- ユーザーはレコーディングを保存する Microsoft のストリームに十分な記憶域を持つ
- ユーザーは、TeamsMeetingPolicy AllowCloudRecording を true に設定されている設定を持っています。
- ユーザーは、オーディオとビデオの議事録を自動的に作成するかどうかを選択できるように、ユーザーは TeamsMeetingPolicy.AllowTranscription を true に設定されている設定を持っています。
- ユーザーは匿名、ゲスト、または会議でのフェデレーションのユーザーではありません。

## <a name="set-up-teams-cloud-meeting-recording-for-users-in-your-organization"></a>チーム、組織内のユーザーのクラウド ミーティングのレコーディングの設定します。

このセクションでは、方法を設定し、チームのミーティングを記録するための計画について説明します。

### <a name="enable-microsoft-stream-for-users-in-the-organization"></a>組織内のユーザーに対して Microsoft ストリームを有効にします。

Microsoft ストリームは、対象の Office 365 サブスクリプションの一部として、またはスタンドアロン サービスとして利用できます。  [ストリームのライセンスの概要](https://docs.microsoft.com/stream/license-overview)の詳細についてを参照してください。  ビジネスに関する重要事項でマイクロソフトのストリームが含まれていないこと、またはビジネス プレミアム プランに注意してください。

方法[Office 365 のユーザーにライセンスを割り当てる](https://support.office.com/article/Assign-licenses-to-users-in-Office-365-for-business-997596B5-4173-4627-B915-36ABAC6786DC)ユーザーが Microsoft のストリームにアクセスできるようにする方法の詳細について説明します。 [この資料](https://docs.microsoft.com/stream/disable-user-organization)で定義されているユーザー、Microsoft のストリームがブロックされていないことを確認します。

### <a name="ensure-that-users-have-upload-video-permissions-in-microsoft-stream"></a>Microsoft ストリーム内のビデオのアクセス許可をユーザーがアップロードがいることを確認します。

既定で、ストリームで指定されたコンテンツを作成して、ストリームが有効になっているし、ライセンスがユーザーに割り当てられている会社内のすべてのユーザーできます。 Microsoft ストリームには、管理者は、ストリーム内の[コンテンツを作成するための従業員を制限する](https://docs.microsoft.com/stream/restrict-uploaders)ことができます。 この制限の一覧にあるユーザーはミーティングを記録することができません。

### <a name="notify-employees-to-consent-to-company-guidelines-in-microsoft-stream"></a>Microsoft ストリーム内の会社のガイドラインに同意するものを従業員に通知します。

Microsoft ストリームの管理者は、[会社の規定のポリシーを設定する](https://docs.microsoft.com/stream/company-policy-and-consent)には、従業員にコンテンツを保存する前にこのポリシーをそのまま使用する必要がありますユーザーする必要がありますようにマイクロソフトのチームでのレコーディングの前にします。 組織の記録機能をロールアウトする前にユーザーが、ポリシーに同意したことを確認します。

### <a name="enabledisable-cloud-recording-for-users"></a>クラウドのユーザーの記録を有効または無効にします。

ユーザーの会議はできるかを記録するかどうかにコントロールするチーム PowerShell の TeamsMeetingPolicy で AllowCloudRecording の設定を使用します。 Office 365 の PowerShell での TeamsMeetingPolicy の管理に関する詳細については、[ここで](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)。

会議の開催者と録音の開始側の両方がミーティングを記録するのには書き込み権限を持っている必要があることに注意してください。 カスタム ポリシーは、ユーザーに割り当てている、しない限り、ユーザーはグローバル ポリシーは既定で有効になっている記録を取得します。

グローバル ポリシーにユーザーが、ユーザーの特定のポリシーの割り当てを削除するのには次のコマンドレットを使用します。

`Grant-CsTeamsMeetingPolicy -Identity {user} -PolicyName $null -Verbose`

グローバル ポリシーで AllowCloudRecording の値を変更するには、次のコマンドレットを使用します。

`Set-CsTeamsMeetingPolicy -Identity Global -AllowCloudRecording $false`
</br>
</br>


|シナリオ|手順 |
|---|---|
|すべてのユーザーがミーティングを記録することができる会社にします |<ol><li>確認するグローバル CsTeamsMeetingPolicy AllowCloudRecording = True<li>すべてのユーザーがあるグローバルの CsTeamsMeetingPolicy または AllowCloudRecording と CsTeamsMeetingPolicy のポリシーのいずれかの指定 </ol>|
|大多数のユーザーがミーティングを記録するが、選択的に記録するのには許可されていない特定のユーザーを無効にすることにします |<ol><li>確認する GlobalCsTeamsMeetingPolicy AllowCloudRecording = True<li>大半のユーザーがあるグローバル CsTeamsMeetingPolicy またはいずれかの CsTeamsMeetingPolicy ポリシーの AllowCloudRecording を持つ = True<li>AllowCloudRecording と CsTeamsMeetingPolicy のポリシーのいずれかの他のすべてのユーザーが付与されて false</ol>|
|100% 無効にするを記録したいです。| <ol><li>確認するグローバル CsTeamsMeetingPolicy AllowCloudRecording = False<li>ユーザーをすべて与えられているグローバル CsTeamsMeetingPolicy または CsTeamsMeetingPolicy のポリシーの 1 つで AllowCloudRecording = False|
|大半のユーザーを無効にするが、選択的に記録するために許可されている特定のユーザーを有効にするを記録したいです。|<ol><li>確認するグローバル CsTeamsMeetingPolicy AllowCloudRecording = False<li>大半のユーザーが与えられて、グローバル CsTeamsMeetingPolicy またはいずれかの CsTeamsMeetingPolicy ポリシーの AllowCloudRecording を指定<li>AllowCloudRecording と CsTeamsMeetingPolicy のポリシーのいずれかの他のすべてのユーザーが与えられて = True <ol>|
|||

### <a name="enabledisable-recording-transcription-for-users"></a>ユーザーの議事録の記録を有効または無効

ユーザーは、チーム ミーティングを記録、議事録がミーティングを記録した後自動的に生成するかどうかを確認できます。 管理者には、会議の開催者と録音の開始側の議事録作成機能が無効になりますが、録音の開始側は、ミーティングのレコーディングの議事録を作成するを取得できません。

録音の開始側がミーティングのレコーディングの議事録を作成する選択を取得するかどうかにコントロールする PowerShell のチームの TeamsMeetingPolicy で AllowTranscription の設定を使用します。 Office 365 の PowerShell での TeamsMeetingPolicy の管理に関する詳細については、[ここで](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)。

カスタム ポリシーは、ユーザーに割り当てている、しない限り、グローバル ポリシーが無効になっている既定で有効になっているを取得します。

グローバル ポリシーにユーザーが、ユーザーの特定のポリシーの割り当てを削除するのには次のコマンドレットを使用します。

`Grant-CsTeamsMeetingPolicy -Identity {user} -PolicyName $null -Verbose`

グローバル ポリシーで AllowCloudRecording の値を変更するには、次のコマンドレットを使用します。

`Set-CsTeamsMeetingPolicy -Identity Global -AllowTranscription $false`
</br>
</br>

|シナリオ|手順 |
|---|---|
|すべてのユーザーがミーティングのレコーディングを開始するときに議事録を作成できる会社にします |<ol><li>確認するグローバル CsTeamsMeetingPolicy AllowTranscription = True <li>すべてのユーザーがグローバルの csTeamsMeetingPolicy にある 1 つまたは AllowTranscription と CsTeamsMeetingPolicy のポリシーを指定します。 </ol>|
|大多数のユーザーにミーティングのレコーディングの議事録を作成、議事録を作成するのには許可されていない特定のユーザーを選択して無効にすることが必要 |<ol><li>確認するグローバル CsTeamsMeetingPolicy AllowTranscription = True <li>大半のユーザーがあるグローバル CsTeamsMeetingPolicy またはいずれかの CsTeamsMeetingPolicy ポリシーの AllowTranscription を持つ = True <li>AllowTranscription と CsTeamsMeetingPolicy のポリシーのいずれかの他のすべてのユーザーが付与されて false </ol>|
|100% 無効にする録音の議事録を作成したいです。 |<ol><li>確認するグローバル CsTeamsMeetingPolicy AllowTranscription = False <li>ユーザーをすべて与えられているグローバル CsTeamsMeetingPolicy または CsTeamsMeetingPolicy のポリシーの 1 つで AllowTranscription = False </ol>|
|大半のユーザーを無効にするが、議事録の作成を許可されている特定のユーザーを選択して有効にするには、議事録作成をします |<ol><li>確認するグローバル CsTeamsMeetingPolicy AllowCloudRecording = False <li>大半のユーザーが与えられて、グローバル CsTeamsMeetingPolicy またはいずれかの CsTeamsMeetingPolicy ポリシーの AllowCloudRecording を指定 <li>AllowCloudRecording と CsTeamsMeetingPolicy のポリシーのいずれかの他のすべてのユーザーが与えられて = True </ol>|
|||

### <a name="planning-for-storage"></a>ストレージのプランニング

1 時間の記録のサイズは、400 MB です。 録画したファイルに必要な能力を理解し、Microsoft のストリームで利用可能な十分なストレージがあることを確認してください。  読み取りサブスクリプションおよびその他の記憶域を購入する方法に含まれている記憶域の基本を理解するのには[ここ](https://docs.microsoft.com/stream/license-overview)です。

## <a name="manage-meeting-recordings"></a>ミーティングのレコーディングを管理します。
ミーティングのレコーディングは、テナントが所有するコンテンツと見なされます。 記録の所有者が会社を辞める場合、管理者開くことができます記録ビデオの URL Microsoft ストリームで管理者モードで。 管理者、録音を削除、記録、メタデータを更新したり、ビデオの録画用のアクセス許可を変更できます。 [ストリーム内の管理機能](https://docs.microsoft.com/stream/manage-content-permissions)について説明します。

## <a name="compliance-and-ediscovery-for-meeting-recordings"></a>コンプライアンスと eDiscovery のミーティングのレコーディング
ミーティングのレコーディングは、Office 365 層 C 準拠では、Microsoft のストリームに格納されます。 Microsoft ストリームの会議またはコールのレコーディングに興味があるコンプライアンス管理者の電子的証拠開示の要求をサポートするために録画完了したメッセージは、マイクロソフト チームのコンプライアンスのコンテンツの検索機能で利用可能なです。 コンプライアンス管理者ことができますコンプライアンス ・ コンテンツの検索・ プレビュー内のアイテムの件名に「記録」のキーワードを検索し、会議を見つけて組織でのレコーディングを呼び出します。 すべてのレコーディングを表示するための前提条件では、管理者のアクセス権を持つ Microsoft ストリームに設定する必要があります。 [ストリーム内の管理者のアクセス許可の割り当て](https://docs.microsoft.com/stream/assign-administrator-user-role)の詳細を表示します。

## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell の詳細情報

Windows PowerShell is all about managing users and what users are allowed or not allowed to do. Windows PowerShell を利用すると、Office 365 と Skype for Business Online の管理を 1 か所で行うことができるので、複数のタスクを担当する管理者の日常業務を単純化できます。 Windows PowerShell には、実行しようとする設定の変更多くのユーザーを一度に 1 つなど、Office 365 管理センターを使用するだけでスピード、シンプルさと生産性に多くの利点があります。 To get started with Windows PowerShell, see these topics:

- [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525041)
- [Windows PowerShell 用にコンピューターをセットアップする](https://go.microsoft.com/fwlink/?LinkId=525038)

