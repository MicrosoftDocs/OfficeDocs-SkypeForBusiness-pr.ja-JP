---
title: Teams のクラウド会議のレコーディング
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: nakulm
search.appverid: MET150
f1.keywords:
- NOCSH
description: Microsoft Teams で会議のレコーディングをオンにして管理する方法を説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1098b1e316bb6ed747577183fc144bf2db7d0b9d
ms.sourcegitcommit: 48f64fa38509cf7141b944cd3da60409ec51860b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "43751854"
---
# <a name="teams-cloud-meeting-recording"></a>Teams のクラウド会議のレコーディング

Microsoft Teams では、ユーザーは Teams 会議やグループ通話を記録して、音声、ビデオ、および画面共有のアクティビティをキャプチャできます。 自動的に文字起こしする記録のオプションもあるため、ユーザーはミーティングの記録を字幕付きで再生して、会議内容の重要な議題を検索できます。 レコーディングはクラウドで実行され、[Microsoft Stream](https://docs.microsoft.com/stream/) に保存されるため、ユーザーは組織全体で安全にそのレコーディングを共有できます。

関連: [Teams 会議のレコーディングに関するエンド ユーザー向けドキュメント](https://aka.ms/recordmeeting)

## <a name="prerequisites-for-teams-cloud-meeting-recording"></a>Teams のクラウド会議をレコーディングするための前提条件

Teams ユーザーの会議を記録するには、そのテナントに対して Microsoft Stream を有効にする必要があります。 また、会議の開催者とレコーディングを開始するユーザーの双方は、次の前提条件を満たす必要があります。

- Office 365 E1、E3、E5、A1、A3、A5、M365 Business、Business Premium または Business Essentials を所有している
- Microsoft Stream<sup>1</sup> のライセンスが付与されている必要がある 
- Microsoft Stream でビデオをアップロードするアクセス許可を持っている
- 会社のガイドラインが管理者によって設定されている場合、そのガイドラインに同意している
- レコーディングを保存するのに十分なストレージを Microsoft Stream に確保している
- TeamsMeetingPolicy-AllowCloudRecording 設定が true に設定されている
- その会議の匿名ユーザー、ゲスト ユーザー、フェデレーション ユーザーではない

> [!NOTE]
> また、レコーディングを自動的に文字起こしするかどうかをレコーディングを開始するユーザーが選択できるようにするには、そのユーザーの TeamsMeetingPolicy -AllowTranscription 設定を true に設定する必要があります。

<sup>1</sup> 会議を Microsoft Stream にアップロードおよびダウンロードするライセンスは必要ですが、会議を記録するライセンスは必要ありません。 あるユーザーが Microsoft Teams の会議をレコーディングできないようにするには、AllowCloudRecording が $False に設定されている TeamsMeetingPolicy を付与する必要があります。

## <a name="set-up-teams-cloud-meeting-recording-for-users-in-your-organization"></a>組織内のユーザーに対して Teams のクラウド会議のレコーディングを設定する

このセクションでは、Teams 会議をレコーディングするための設定方法と計画方法について説明します。

### <a name="turn-on-microsoft-stream-for-users-in-the-organization"></a>組織内のユーザーに対して Microsoft Stream を有効にする

Microsoft Stream は、対象となる Office 365 サブスクリプションの一部として、またはスタンドアロン サービスとして使用できます。  詳細については、「[Microsoft Stream ライセンスの概要](https://docs.microsoft.com/stream/license-overview)」を参照してください。  Microsoft Stream は、現在、Microsoft 365 Business、Office 365 Business Premium、および Office 365 Business Essentials に含まれています。

ユーザーが Microsoft Stream にアクセスできるように [Office 365 でユーザーにライセンスを割り当てる](https://support.office.com/article/Assign-licenses-to-users-in-Office-365-for-business-997596B5-4173-4627-B915-36ABAC6786DC)方法をご確認ください。 Microsoft Stream がそのユーザーに対してブロックされていないことを、[この記事](https://docs.microsoft.com/stream/disable-user-organization)の定義に従って確認します。

### <a name="make-sure-users-have-upload-video-permissions-in-microsoft-stream"></a>ユーザーが Microsoft Stream でビデオのアクセス許可をアップロードしていることを確認する

既定では、Stream が有効になっており、ユーザーにライセンスが割り当てられていれば、社内のすべてのユーザーが Stream でコンテンツを作成できます。 Microsoft Stream の管理者は、Stream で[コンテンツを作成できる従業員を制限する](https://docs.microsoft.com/stream/restrict-uploaders)ことができます。 この制限リストに記載されているユーザーは、会議を記録できません。

### <a name="notify-employees-to-consent-to-company-guidelines-in-microsoft-stream"></a>Microsoft Stream で会社のガイドラインに同意するよう従業員に通知する

Microsoft Stream の管理者が[会社のガイドライン ポリシーを設定](https://docs.microsoft.com/stream/company-policy-and-consent)しており、コンテンツを保存する前にこのポリシーを承諾することを従業員に求めている場合、ユーザーは Microsoft Teams でレコーディングする前にポリシーを承諾する必要があります。 その組織のレコーディング機能を展開する前に、ユーザーがポリシーに同意していることを確認してください。

### <a name="turn-on-or-turn-off-cloud-recording"></a>クラウド レコーディングを開始または停止する

Microsoft Teams 管理センターまたは PowerShell を使用して、Teams の会議ポリシーを設定すると、ユーザーの会議を記録できるかどうかを制御できます。

Microsoft Teams 管理センターを使用する場合は、会議ポリシーの **[Allow cloud recording](クラウド レコーディングを許可する)** 設定をオンまたはオフにします。 詳細については、「[Teams での会議ポリシーを管理する](meeting-policies-in-teams.md#allow-cloud-recording)」を参照してください。

PowerShell を使用する場合は、TeamsMeetingPolicy で AllowCloudRecording 設定を構成します。 詳細については、「[New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy)」および「[Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)」を参照してください。

会議をレコーディングするには、会議の開催者とレコーディングを開始するユーザーの双方に、レコーディングのアクセス許可が必要です。 管理者がユーザーにカスタム ポリシーを割り当てていない限り、ユーザーはグローバル ポリシーを取得します。グローバル ポリシーでは、既定で AllowCloudRecording が無効になっています。

ユーザーがグローバル ポリシーにフォールバックするには、次のコマンドレットを使用して、ユーザーの特定のポリシーの割り当てを削除します。

`Grant-CsTeamsMeetingPolicy -Identity {user} -PolicyName $null -Verbose`

グローバル ポリシーの AllowCloudRecording の値を変更するには、次のコマンドレットを使用します。

`Set-CsTeamsMeetingPolicy -Identity Global -AllowCloudRecording $false`
</br>
</br>


|                                                                 シナリオ                                                                 |                                                                                                                                                                         手順                                                                                                                                                                          |
|------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                    社内のすべてのユーザーが会議を記録できるようにする                                    |                                                                     <ol><li>グローバルな CsTeamsMeetingPolicy が AllowCloudRecording = True に設定されていることを確認する<li>すべてのユーザーについて、グローバルな CsTeamsMeetingPolicy または CsTeamsMeetingPolicy ポリシーの 1 つが AllowCloudRecording = True に設定されていることを確認する </ol>                                                                     |
| ユーザーの大半に会議の記録を許可し、記録を許可されていない特定のユーザーについては選択的に記録できないようにする |        <ol><li>GlobalCsTeamsMeetingPolicy が AllowCloudRecording = True に設定されていることを確認する<li>大半のユーザーについて、グローバルな CsTeamsMeetingPolicy または CsTeamsMeetingPolicy ポリシーの 1 つが AllowCloudRecording = True に設定されていることを確認する<li>その他のすべてのユーザーには、AllowCloudRecording = False に設定された CsTeamsMeetingPolicy ポリシーの 1 つが付与されている</ol>         |
|                                                   レコーディングを完全に無効にする                                                   |                                                                <ol><li>グローバルな CsTeamsMeetingPolicy が AllowCloudRecording = False に設定されていることを確認する<li>すべてのユーザーについて、AllowCloudRecording = False に設定されたグローバルな CsTeamsMeetingPolicy または CsTeamsMeetingPolicy ポリシーの 1 つが付与されている                                                                 |
|      多くのユーザーに対してレコーディングをオフにして、記録を許可する特定のユーザーを選択する       | <ol><li>グローバルな CsTeamsMeetingPolicy が AllowCloudRecording = False に設定されていることを確認する<li>大半のユーザーについて、AllowCloudRecording = False に設定されたグローバルな CsTeamsMeetingPolicy または CsTeamsMeetingPolicy ポリシーの 1 つが付与されている<li>その他のすべてのユーザーには、AllowCloudRecording = True に設定された CsTeamsMeetingPolicy ポリシーの 1 つが付与されている <ol> |
|                                                                                                                                          |                                                                                                                                                                                                                                                                                                                                                  |
#### <a name="where-your-meeting-recordings-are-stored"></a>会議のレコーディングの保存場所

会議のレコーディングは、Microsoft Stream クラウド ストレージに保存されます。 会議を記録すると、Microsoft Stream は、永久に保持されます (またはレコーディングの所有者が削除するまで)。 レコーディングがストリームにアップロードされない場合は、チームのクラウドストレージに保存され、20日間ダウンロードできます。 現在は、データが保存される国内のデータ所在地では Microsoft Stream が利用できない場合、Teams のデータが国内に保存されるお客様の会議のレコーディング機能は無効になっています。

お客様の Microsoft Stream データが保存されるリージョンを確認するには、Microsoft Stream で、右上隅にある **[?]** をクリックし、 **[About Microsoft Stream](Microsoft Stream について)** をクリックして、**[Your data is stored in](データの保存場所)** をクリックします。  Microsoft Stream でデータが保存されるリージョンについて詳しくは、「[Microsoft Stream FAQ](https://docs.microsoft.com/stream/faq#which-regions-does-microsoft-stream-host-my-data-in)」を参照してください。

Office 365 のサービス全体のデータの保存場所について詳しくは、「[データの保管場所](https://products.office.com/where-is-your-data-located?rtc=1)」を参照してください。

### <a name="turn-on-or-turn-off-recording-transcription"></a>レコーディングの文字起こしを有効または無効にする

ユーザーは、Teams 会議を記録する際に、会議を記録した後でトランスクリプトを自動的に生成されるかどうかを確認できます。 管理者が会議の開催者とレコーディングを開始するユーザーの文字起こし機能を無効にすると、レコーディングを開始するユーザーは会議のレコーディングを文字起こしする機能を選択できません。

Microsoft Teams 管理センターまたは PowerShell を使用して、Teams の会議ポリシーを設定すると、レコーディングを開始するユーザーが会議のレコーディングを文字起こしする機能を選択できるかどうかを制御できます。

Microsoft Teams 管理センターを使用する場合は、会議ポリシーの **[Allow transcription](議事録作成を許可する)** 設定をオンまたはオフにします。 詳細については、「[Teams での会議ポリシーを管理する](meeting-policies-in-teams.md#allow-transcription)」を参照してください。

PowerShell を使用する場合は、TeamsMeetingPolicy で AllowTranscription 設定を構成します。 詳細については、「[New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy)」および「[Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)」を参照してください。

管理者がユーザーにカスタム ポリシーを割り当てていない限り、ユーザーはグローバル ポリシーを取得します。グローバル ポリシーでは、既定で AllowTranscription が無効になっています。

ユーザーがグローバル ポリシーにフォールバックするには、次のコマンドレットを使用して、ユーザーの特定のポリシーの割り当てを削除します。

`Grant-CsTeamsMeetingPolicy -Identity {user} -PolicyName $null -Verbose`

グローバル ポリシーの AllowCloudRecording の値を変更するには、次のコマンドレットを使用します。

`Set-CsTeamsMeetingPolicy -Identity Global -AllowTranscription $false`
</br>
</br>

|シナリオ|手順 |
|---|---|
|社内のすべてのユーザーが会議のレコーディングを開始するときに文字起こしできるようにしたい |<ol><li>グローバルな CsTeamsMeetingPolicy が AllowTranscription = True に設定されていることを確認する <li>すべてのユーザーについて、グローバルな CsTeamsMeetingPolicy または CsTeamsMeetingPolicy ポリシーの 1 つが AllowTranscription = True に設定されていることを確認する </ol>|
|ユーザーの大半に会議のレコーディングの文字起こしを許可し、文字起こしを許可されていない特定のユーザーについては選択的に文字起こしできないようにする |<ol><li>グローバルな CsTeamsMeetingPolicy が AllowTranscription = True に設定されていることを確認する <li>大半のユーザーについて、グローバルな CsTeamsMeetingPolicy または CsTeamsMeetingPolicy ポリシーの 1 つが AllowTranscription = True に設定されていることを確認する <li>その他のすべてのユーザーには、AllowTranscription = False に設定された CsTeamsMeetingPolicy ポリシーの 1 つが付与されている </ol>|
|レコーディングの文字起こしを完全に無効にする |<ol><li>グローバルな CsTeamsMeetingPolicy が AllowTranscription = False に設定されていることを確認する <li>すべてのユーザーについて、AllowTranscription = False に設定されたグローバルな CsTeamsMeetingPolicy または CsTeamsMeetingPolicy ポリシーの 1 つが付与されている </ol>|
|ユーザーの大半の文字起こしを無効にし、文字起こしを許可されている特定のユーザーについては文字起こしを選択的に許可する |<ol><li>グローバルな CsTeamsMeetingPolicy が AllowCloudRecording = False に設定されていることを確認する <li>大半のユーザーについて、AllowCloudRecording = False に設定されたグローバルな CsTeamsMeetingPolicy または CsTeamsMeetingPolicy ポリシーの 1 つが付与されている <li>その他のすべてのユーザーには、AllowCloudRecording = True に設定された CsTeamsMeetingPolicy ポリシーの 1 つが付与されている </ol>|
|||

### <a name="planning-for-storage"></a>ストレージの計画

1 時間のレコーディングのサイズは 400 MB です。 記録されたファイルに必要な容量を理解していること、および Microsoft Stream で使用できる十分なストレージがあることを確認します。  サブスクリプションに含まれている基本ストレージ、および追加のストレージの購入方法については、[こちらの記事](https://docs.microsoft.com/stream/license-overview)をご確認ください。

## <a name="manage-meeting-recordings"></a>会議のレコーディングを管理する

会議のレコーディングは、テナントで所有されるコンテンツとみなされます。 レコーディングの所有者が退職する場合、管理者は、管理者モードで Microsoft Stream のレコーディング ビデオ URL を開くことができます。 管理者は、そのレコーディングの削除、任意のレコーディング メタデータの更新、レコーディング ビデオに対するアクセス許可の変更を実行できます。 [Stream での管理機能](https://docs.microsoft.com/stream/manage-content-permissions)の詳細をご確認ください。

> [!NOTE]
> レコーディングとユーザー アクセスを管理する方法の詳細については、「[Microsoft Stream でユーザー データを管理する](https://docs.microsoft.com/stream/managing-user-data)」と「[Microsoft Stream でのアクセス許可とプライバシー](https://docs.microsoft.com/stream/portal-permissions)」を参照してください。


## <a name="compliance-and-ediscovery-for-meeting-recordings"></a>会議のレコーディングのコンプライアンスと電子情報開示

会議のレコーディングは、Office 365 の C レベルに準拠している Microsoft Stream に保存されます。 Microsoft Streams の会議や通話のレコーディングに関心があるコンプライアンス管理者の電子情報開示要求をサポートするため、Microsoft Teams のコンプライアンス コンテンツ検索機能ではレコーディング完了メッセージを利用できます。 コンプライアンス管理者は、コンプライアンス コンテンツ検索プレビューのアイテムの件名で "レコーディング" をキーワード検索して、組織内の会議や通話のレコーディングを見つけることができます。 コンプライアンス管理者がすべてのレコーディングを表示するための前提条件として、コンプライアンス管理者は Microsoft Stream の設定で管理アクセスを付与されている必要があります。 詳細については、「[Assign Microsoft Stream admins](https://docs.microsoft.com/stream/assign-administrator-user-role)」(Microsoft Stream で管理者を割り当てる) を参照してください。

## <a name="related-topics"></a>関連項目

- [Teams での PowerShell の概要](teams-powershell-overview.md)
