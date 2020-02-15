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
f1.keywords:
- NOCSH
description: Microsoft Teams でクラウド音声機能を展開するための実用的なガイダンス。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5041b35822a04dc98aa6c07d3731ad8c6791af98
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030721"
---
# <a name="teams-cloud-meeting-recording"></a>Teams のクラウド会議の記録

> [!IMPORTANT]
> **今後、** Microsoft Stream が国内データ常駐地域で利用できない場合でも、teams のデータが国内に保存されているお客様に対しては、構成の変更が有効になります。 この変更が有効になると、会議の記録は既定で最も近い Microsoft Stream 領域に保存されます。 チームデータが国内に保存されていて、会議の記録を国内で保存する場合は、[会議の記録] をオフにして、Microsoft Stream が国内の地域に展開された後で有効にすることをお勧めします。 詳細については、「[会議のレコーディングが保存](#where-your-meeting-recordings-are-stored)されている場所」を参照してください。

Microsoft Teams では、ユーザーはチーム会議やグループ通話を記録して、音声、ビデオ、画面共有のアクティビティをキャプチャすることができます。 自動的に文字起こしする記録のオプションもあるため、ユーザーはミーティングの記録を字幕付きで再生して、会議内容の重要な議題を検索できます。 記録はクラウドで行われ、 [Microsoft Stream](https://docs.microsoft.com/stream/)に保存されるため、ユーザーは組織全体で安全に共有することができます。

関連: [Teams 会議でのエンドユーザー向けドキュメントの記録](https://aka.ms/recordmeeting)

## <a name="prerequisites-for-teams-cloud-meeting-recording"></a>Teams クラウド会議レコーディングの前提条件

チームユーザーの会議を記録するには、テナントに対して Microsoft Stream を有効にする必要があります。 さらに、会議の開催者とレコーディングを開始するユーザーの両方に対して、次の前提条件が必要になります。

- ユーザーには、Office 365 E1、E3、E5、A1、A3、A5、M365 Business、Business Premium または Business Essentials が含まれています。
- ユーザーには Microsoft Stream<sup>1</sup>のライセンスが必要です 
- ユーザーは Microsoft Stream アップロードのビデオアクセス許可を持っています
- ユーザーは管理者によって設定されている場合、会社のガイドラインに各人しました。
- レコーディングを保存するために Microsoft Stream に十分なストレージがあるユーザー
- ユーザーには TeamsMeetingPolicy/AllowCloudRecording 設定が true に設定されています
- ユーザーは、会議の匿名、ゲスト、またはフェデレーションユーザーではありません

> [!NOTE]
> さらに、レコーディングを開始するユーザーがレコーディングを自動的に議事録に追加するかどうかを選択できるようにするには、ユーザーの TeamsMeetingPolicy/AllowTranscription 設定を true に設定する必要があります。

<sup>1</sup>ユーザーは Microsoft Stream との会議をアップロード/ダウンロードするためのライセンスが必要ですが、会議を記録するためのライセンスは必要ありません。 ユーザーによる Microsoft Teams 会議の記録をブロックする場合は、$False に AllowCloudRecording が設定されている TeamsMeetingPolicy を付与する必要があります。

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

Microsoft Teams 管理センターまたは PowerShell を使用して、Teams 会議ポリシーを設定し、ユーザーの会議を記録できるかどうかを制御することができます。

Microsoft Teams 管理センターで、会議ポリシーの [**クラウドレコーディングを許可する**] 設定をオンまたはオフにします。 詳細については、「 [Teams の会議ポリシーを管理](meeting-policies-in-teams.md#allow-cloud-recording)する」を参照してください。

PowerShell を使用して、TeamsMeetingPolicy で AllowCloudRecording 設定を構成します。 詳細については、「 [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) and [CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)」を参照してください。

会議の開催者とレコーディングの開始者の両方が、会議を記録するための書き込みアクセス許可を持っている必要があることに注意してください。 ユーザーにカスタムポリシーを割り当てていない限り、ユーザーはグローバルポリシーを取得します。これには、既定で AllowCloudRecording が無効になっています。

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
|                                                   レコーディングを100% 無効にする                                                   |                                                                <ol><li>グローバル CsTeamsMeetingPolicy の確認 AllowCloudRecording = False<li>すべてのユーザーに、AllowCloudRecording = False を持つグローバル CsTeamsMeetingPolicy または CsTeamsMeetingPolicy ポリシーのいずれかが許可されている                                                                 |
|      大部分のユーザーに対してレコーディングを無効にして、記録を許可する特定のユーザーを選択する       | <ol><li>グローバル CsTeamsMeetingPolicy の確認 AllowCloudRecording = False<li>大部分のユーザーには、AllowCloudRecording = False を持つグローバル CsTeamsMeetingPolicy または CsTeamsMeetingPolicy ポリシーのいずれかが付与されています<li>他のすべてのユーザーに AllowCloudRecording = True の CsTeamsMeetingPolicy ポリシーのいずれかが付与されている <ol> |
|                                                                                                                                          |                                                                                                                                                                                                                                                                                                                                                  |
#### <a name="where-your-meeting-recordings-are-stored"></a>会議のレコーディングが保存されている場所

会議のレコーディングは、Microsoft Stream クラウドストレージに保存されます。 現時点では、データが保存されている国内のデータ常駐地域で Microsoft Stream を使用できない場合、会議のレコーディング機能は、その国のデータが国内に保存されているお客様にはオフになっています。 今後、Microsoft Stream が国内データ常駐地域で利用できない場合でも、データが国内に保存されているお客様のために、会議のレコーディング機能が有効になります。

この変更が有効になると、会議の記録は既定で Microsoft Stream の最も近い地理的地域に保存されます。 チームデータが国内に保存されていて、会議の記録を国内で保存する場合は、この機能をオフにして、Microsoft Stream が国内のデータ常駐地域に展開された後に有効にすることをお勧めします。 組織内のすべてのユーザーに対してこの機能を無効にするには、Microsoft Teams 管理センターで、グローバルチーム会議ポリシーの [**クラウドレコーディングの許可**] 設定をオフにします。

この変更が有効になったときに会議のレコーディングをオンにすると、次のような問題が発生します。

|会議のレコーディングをオンにした場合 |会議のレコーディングは保存されます...  |
|---------|---------|
|国内のデータ常駐地域で Microsoft Stream を使用できるようにする前に    |最寄りの Microsoft Stream 領域         |
|国内データ常駐地域で Microsoft Stream を利用できるようになった後    | 国内のデータ常駐地域で        |

会議の記録をまだ有効にしていない新規および既存のテナントの場合は、Microsoft Stream が国内のデータ常駐地域で利用可能になると、新しいレコーディングが国内に保存されます。 ただし、国内データ常駐地域で Microsoft Stream が利用可能になる前に会議レコーディングを有効にするすべてのテナントは、Microsoft Stream を使用している場合でも、既存の記録と新しい記録用に Microsoft Stream storage を引き続き使用します。国内データ常駐の地域。

Microsoft stream データが保存されている地域を確認するには、Microsoft Stream でをクリックし**ます。** 右上隅の [ **Microsoft Stream のバージョン情報**] をクリックし、**データが保存**されているをクリックします。  Microsoft Stream にデータが保存されている地域の詳細については、「 [Microsoft stream](https://docs.microsoft.com/stream/faq#which-regions-does-microsoft-stream-host-my-data-in)に関する FAQ」を参照してください。

Office 365 のサービス間でデータが保存される場所の詳細については、「[データがどこにあるか](https://products.office.com/where-is-your-data-located?rtc=1)を確認する」を参照してください。

### <a name="turn-on-or-turn-off-recording-transcription"></a>レコーディングの議事録を有効または無効にする

ユーザーはチーム会議を記録したときに、会議が記録された後にトランスクリプトが自動生成されるかどうかを確認できます。 会議の開催者とレコーディングの開始側の [議事録機能] を無効にした場合、レコーディングの開始者は、会議の記録の議事録を設定することはできません。

Microsoft Teams 管理センターまたは PowerShell を使用して、Teams 会議ポリシーを設定して、レコーディングの開始者が会議の記録の議事録を行うかどうかを制御できます。

Microsoft Teams 管理センターで、会議ポリシーの [**議事録の許可**] 設定をオンまたはオフにします。 詳細については、「 [Teams の会議ポリシーを管理](meeting-policies-in-teams.md#allow-transcription)する」を参照してください。

PowerShell を使用して、TeamsMeetingPolicy で AllowTranscription 設定を構成します。 詳細については、「 [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) and [CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)」を参照してください。

ユーザーにカスタムポリシーを割り当てていない限り、ユーザーはグローバルポリシーを取得します。これには、既定で AllowTranscription が無効になっています。

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
|レコーディングの議事録を100% 無効にする |<ol><li>グローバル CsTeamsMeetingPolicy の確認 AllowTranscription = False <li>すべてのユーザーに AllowTranscription = False を使用してグローバル CsTeamsMeetingPolicy または CsTeamsMeetingPolicy ポリシーのいずれかが付与されている </ol>|
|ほとんどのユーザーに対して、議事録を無効にしたいが、議事録を許可された特定のユーザーを選択できるようにする |<ol><li>グローバル CsTeamsMeetingPolicy の確認 AllowCloudRecording = False <li>大部分のユーザーには、AllowCloudRecording = False を持つグローバル CsTeamsMeetingPolicy または CsTeamsMeetingPolicy ポリシーのいずれかが付与されています <li>他のすべてのユーザーに AllowCloudRecording = True の CsTeamsMeetingPolicy ポリシーのいずれかが付与されている </ol>|
|||

### <a name="planning-for-storage"></a>記憶域の計画

1時間の記録のサイズは 400 MB です。 記録されたファイルに必要な容量を理解していること、および Microsoft Stream で利用できる十分なストレージがあることを確認してください。  [この記事](https://docs.microsoft.com/stream/license-overview)では、サブスクリプションに含まれている基本記憶域と追加記憶域の購入方法について説明します。

## <a name="manage-meeting-recordings"></a>会議のレコーディングを管理する

会議のレコーディングは、テナントが所有しているコンテンツと見なされます。 レコーディングの所有者が退職した場合、管理者は、Microsoft Stream in 管理モードでレコーディングビデオの URL を開くことができます。 管理者は、レコーディングを削除したり、レコーディングメタデータを更新したり、レコーディングビデオのアクセス許可を変更したりできます。 [ストリームの管理機能の](https://docs.microsoft.com/stream/manage-content-permissions)詳細については、こちらを参照してください。

## <a name="compliance-and-ediscovery-for-meeting-recordings"></a>会議のレコーディングのコンプライアンスと電子情報開示

会議のレコーディングは、Office 365 Tier C に準拠している Microsoft Stream に保存されます。 Microsoft のストリームの会議または通話の記録に関心を持っているコンプライアンス管理者に対する e 検出要求をサポートするため、[レコーディング完了] メッセージは Microsoft Teams のコンプライアンスコンテンツ検索機能で利用できます。 コンプライアンス管理者は、コンプライアンスコンテンツ検索プレビューのアイテムの件名行に "レコーディング" というキーワードを検索して、組織内の会議と通話の記録を検出できます。 すべてのレコーディングを表示するには、Microsoft Stream で管理者アクセス権を設定する必要があることが前提となります。 詳しく[は、「Stream での管理権限の割り当て」を](https://docs.microsoft.com/stream/assign-administrator-user-role)ご覧ください。

## <a name="related-topics"></a>関連トピック

- [Teams での PowerShell の概要](teams-powershell-overview.md)
