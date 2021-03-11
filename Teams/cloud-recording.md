---
title: Teams のクラウド会議のレコーディング
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- M365-collaboration
- m365initiative-meetings
ms.reviewer: nakulm
search.appverid: MET150
f1.keywords:
- NOCSH
description: Teams にクラウド音声機能を展開して、音声、ビデオ、画面共有活動をキャプチャして、Teams 会議やグループ通話を記録するための実践的なガイダンスです。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 851901a6f985ecfecdcd6e3fda67aa5c1f11af3b
ms.sourcegitcommit: 31a585cc0fe6350efacf3a7771d1e590d5e4233c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/10/2021
ms.locfileid: "50615103"
---
# <a name="teams-cloud-meeting-recording"></a>Teams のクラウド会議のレコーディング

Microsoft Teams では、ユーザーは Teams 会議やグループ通話を記録して、音声、ビデオ、および画面共有のアクティビティをキャプチャできます。 自動的に文字起こしする記録のオプションもあるため、ユーザーはミーティングの記録を字幕付きで再生して、会議内容の重要な議題を検索できます。 レコーディングはクラウドで実行され、[Microsoft Stream](https://docs.microsoft.com/stream/) に保存されるため、ユーザーは組織全体で安全にそのレコーディングを共有できます。

関連: [Teams 会議のレコーディングに関するエンド ユーザー向けドキュメント](https://aka.ms/recordmeeting)

>[!Note]
> Microsoft Stream の使用から 会議の記録用の OneDrive for Business および SharePoint への変更は段階的なアプローチになります。 各フェーズの詳細については、「会議のレコーディングに OneDrive for Business と SharePoint または Stream を使用する [」を参照してください](tmr-meeting-recording-change.md)。

> [!NOTE]
> Teams 会議でロールを使用する方法、およびユーザーのロールを変更する方法の詳細については、「[Teams 会議での役割](https://support.microsoft.com/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us)」を参照してください。 ライブ イベントの記録オプションについては [、Teams のライブ イベント記録ポリシーを参照してください](teams-live-events/live-events-recording-policies.md)。

## <a name="prerequisites-for-teams-cloud-meeting-recording"></a>Teams クラウド会議のレコーディングのための前提条件

Teams ユーザーの会議を記録するには、そのテナントに対して Microsoft Stream を有効にする必要があります。 また、会議の開催者とレコーディングを開始するユーザーの双方は、次の前提条件を満たす必要があります。

- Office 365 E1、E3、E5、A1、A3、A5、Microsoft 365 Business Premium または Business Standard または Business Basic<sup>1</sup> を所有している
- 会社のガイドラインが管理者によって設定されている場合、そのガイドラインに同意している
- レコーディングを保存するのに十分なストレージを Microsoft Stream に確保している
- ユーザーが CsTeamsMeetingPolicy -AllowCloudRecording 設定を true に設定して会議やグループ通話を記録する
- ユーザーが CsTeamsCallingPolicy -AllowCloudRecordingForCalls 設定を true に設定して 1 対 1 の呼び出しを記録しています
- その会議の匿名ユーザー、ゲスト ユーザー、フェデレーション ユーザーではない
- ユーザーの会議の議事録作成を有効にするには、割り当てられている Teams の会議ポリシーで-AllowTranscription 設定が「正」に設定されている必要があります。

<sup>1</sup> 2020 年 8 月 20 日以降、A1 を使用しているユーザーの場合、会議記録ファイルへのアクセスは 21 日後に有効期限が切れます。 詳細については、「[Microsoft Teams 会議の記録を Stream にアップロードする](https://docs.microsoft.com/stream/portal-upload-teams-meeting-recording)」を参照してください。

<sup>2</sup> 会議を Microsoft Stream に/からアップロードおよび/またはダウンロードするライセンスは必要ですが、会議を記録するライセンスは必要ありません。 あるユーザーが Microsoft Teams の会議をレコーディングできないようにするには、AllowCloudRecording が $False に設定されている TeamsMeetingPolicy を付与する必要があります。

> [!IMPORTANT]
> ユーザーに録音とそれのダウンロードのみを許可する場合は、Microsoft Stream のライセンスを割り当てる必要はありません。 つまり、録音は Microsoft Stream に保存されず、削除されるまでの 21 日間の制限付きで Azure Media Services (AMS) に保存されるということです。 現時点では、削除機能を含め、管理者が制御または管理できるものではありません。

## <a name="set-up-teams-cloud-meeting-recording-for-users-in-your-organization"></a>組織内のユーザーに対して Teams のクラウド会議のレコーディングを設定する

このセクションでは、Teams 会議をレコーディングするための設定方法と計画方法について説明します。

### <a name="turn-on-microsoft-stream-for-users-in-the-organization"></a>組織内のユーザーに対して Microsoft Stream を有効にする

Microsoft Stream は、対象となる Microsoft 365 または Office 365 サブスクリプションの一部として、またはスタンドアロン サービスとして使用できます。  詳細については、「[Microsoft Stream ライセンスの概要](https://docs.microsoft.com/stream/license-overview)」を参照してください。  Microsoft Stream は、現在、Microsoft 365 Business、Microsoft 365 Business Standard、 および Microsoft 365 Business Basic に含まれています。

ユーザーが Microsoft Stream にアクセスできるように 「[Microsoft 365 またはOffice 365 でユーザーにライセンスを割り当てる](https://support.office.com/article/Assign-licenses-to-users-in-Office-365-for-business-997596B5-4173-4627-B915-36ABAC6786DC)」を参照してください。 Microsoft Stream がそのユーザーに対してブロックされていないことを、「[Microsoft Stream へのサインアップをブロックする](https://docs.microsoft.com/stream/disable-user-organization)」の定義に従って確認します。

### <a name="make-sure-users-have-upload-video-permissions-in-microsoft-stream"></a>ユーザーが Microsoft Stream でビデオをアップロードするアクセス許可を持っていることを確認する

既定では、Stream が有効になっており、ユーザーにライセンスが割り当てられていれば、社内のすべてのユーザーが Stream でコンテンツを作成できます。 Microsoft Stream の管理者は、Stream で[コンテンツを作成できる従業員を制限する](https://docs.microsoft.com/stream/restrict-uploaders)ことができます。 この制限リストに記載されているユーザーは、会議を記録できません。

### <a name="notify-employees-to-consent-to-company-guidelines-in-microsoft-stream"></a>Microsoft Stream で会社のガイドラインに同意するよう従業員に通知する

Microsoft Stream の管理者が[会社のガイドライン ポリシーを設定](https://docs.microsoft.com/stream/company-policy-and-consent)しており、コンテンツを保存する前にこのポリシーを承諾することを従業員に求めている場合、ユーザーは Microsoft Teams でレコーディングする前にポリシーを承諾する必要があります。 その組織のレコーディング機能を展開する前に、ユーザーがポリシーに同意していることを確認してください。

### <a name="turn-on-or-turn-off-cloud-recording"></a>クラウド レコーディングを開始または停止する

Microsoft Teams 管理センターまたは PowerShell を使用して、Teams の会議ポリシーを設定すると、ユーザーの会議を記録できるかどうかを制御できます。

Microsoft Teams 管理センターを使用する場合は、会議ポリシーの **[Allow cloud recording](クラウド レコーディングを許可する)** 設定をオンまたはオフにします。 詳細については、「[Teams での会議ポリシーを管理する](meeting-policies-in-teams.md#allow-cloud-recording)」を参照してください。

PowerShell を使用する場合は、TeamsMeetingPolicy で AllowCloudRecording 設定を構成します。 詳細については、「[New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy)」および「[Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)」を参照してください。

会議をレコーディングするには、会議の開催者とレコーディングを開始するユーザーの双方に、レコーディングのアクセス許可が必要です。 管理者がユーザーにカスタム ポリシーを割り当てていない限り、ユーザーはグローバル ポリシーを取得します。グローバル ポリシーでは、既定で AllowCloudRecording が有効になっています。

> [!NOTE]
> Teams の役割を使用して、会議を記録するためのアクセス許可を持つユーザーを構成する方法の詳細については、「[Teams 会議での役割](https://support.microsoft.com/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us)」 を参照してください。

ユーザーがグローバル ポリシーにフォールバックするには、次のコマンドレットを使用して、ユーザーの特定のポリシーの割り当てを削除します。

```powershell
Grant-CsTeamsMeetingPolicy -Identity {user} -PolicyName $null -Verbose
```

グローバル ポリシーの AllowCloudRecording の値を変更するには、次のコマンドレットを使用します。

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -AllowCloudRecording $false
```

</br>
</br>


|                                                                 シナリオ                                                                 |                                                                                                                                                                         手順                                                                                                                                                                          |
|------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                    社内のすべてのユーザーが会議を記録できるようにする                                    |                                                                     <ol><li>グローバルな CsTeamsMeetingPolicy が AllowCloudRecording = True に設定されていることを確認する<li>すべてのユーザーについて、グローバルな CsTeamsMeetingPolicy または CsTeamsMeetingPolicy ポリシーの 1 つが AllowCloudRecording = True に設定されていることを確認する </ol>                                                                     |
| ユーザーの大半に会議の記録を許可し、記録を許可されていない特定のユーザーについては選択的に記録できないようにする |        <ol><li>GlobalCsTeamsMeetingPolicy が AllowCloudRecording = True に設定されていることを確認する<li>大半のユーザーについて、グローバルな CsTeamsMeetingPolicy または CsTeamsMeetingPolicy ポリシーの 1 つが AllowCloudRecording = True に設定されていることを確認する<li>その他のすべてのユーザーには、AllowCloudRecording = False に設定された CsTeamsMeetingPolicy ポリシーの 1 つが付与されている</ol>         |
|                                                   レコーディングを完全に無効にする                                                   |                                                                <ol><li>グローバルな CsTeamsMeetingPolicy が AllowCloudRecording = False に設定されていることを確認する<li>すべてのユーザーについて、AllowCloudRecording = False に設定されたグローバルな CsTeamsMeetingPolicy または CsTeamsMeetingPolicy ポリシーの 1 つが付与されている                                                                 |
|      ユーザーの大半に対してはレコーディングを無効にし、特定のユーザーにのみ、記録することを許可しレコーディングを選択的に許可したい       | <ol><li>グローバルな CsTeamsMeetingPolicy が AllowCloudRecording = False に設定されていることを確認する<li>大半のユーザーについて、AllowCloudRecording = False に設定されたグローバルな CsTeamsMeetingPolicy または CsTeamsMeetingPolicy ポリシーの 1 つが付与されている<li>その他のすべてのユーザーには、AllowCloudRecording = True に設定された CsTeamsMeetingPolicy ポリシーの 1 つが付与されている <ol> |
|                                                                                                                                          |                                                                                                                                                                                                                                                                                                                                                  |

#### <a name="where-your-meeting-recordings-are-stored"></a>会議のレコーディングの保存場所

会議のレコーディングは、Microsoft Stream クラウド ストレージに保存されます。 現在は、データが保存される国内のデータ所在地では Microsoft Stream が利用できない場合、Teams のデータが国内に保存されるお客様の会議のレコーディング機能は無効になっています。 Microsoft Stream が国内のデータ常駐地域で利用できない場合でも、データが国内に保存されるはずの顧客に対して、会議の記録機能を有効にできます。 これは、記録を Microsoft Stream の最も近い地理的地域に保存できるようにして行います。 

Teams のデータが国内に保存されており、会議のレコーディングを国内に保存することをご希望の場合は、この機能を無効にし、Microsoft Stream がお客様の国内のデータ所在地のリージョンに展開されてから有効にすることをお勧めします。 組織内のすべてのユーザーに対してこの機能を無効にするには、Microsoft Teams 管理センターで、グローバルな Teams 会議ポリシーの **クラウドの記録を許可する** 設定をオフにします。 ただし、記録を Microsoft Stream の最も近い地理的地域に保存できるようにしたい場合は、この変更を実行する前に、「**クラウドの記録を許可する**」 と 「**外部の領域の保存を許可**」の両方を有効にする必要があります。

グローバル ポリシーで領域内のレコーディングを有効にするには、次のコマンドレットを使用します。

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -AllowCloudRecording $true -AllowRecordingStorageOutsideRegion $true
```

この変更が有効になると、会議のレコーディングを開始した場合の動作は次のようになります。

|会議のレコーディングを開始した場合...|会議のレコーディングの保存先... |
|---|---|
|Microsoft Stream がお客様の国内のデータ所在地のリージョンで利用できるようになる前 |最も近い Microsoft Stream のリージョン|
|Microsoft Stream がお客様の国内のデータ所在地のリージョンで利用できるようになった後 |お客様の国内のデータ所在地のリージョン|

会議のレコーディングが開始していない新規および既存のテナントの場合、Microsoft Stream がその国内のデータ所在地のリージョンで利用できるようになると、新しいレコーディングは国内に保存されます。 ただし、Microsoft Stream がその国内のデータ所在地のリージョンで利用できるようになる前に会議のレコーディングが有効になっているすべてのテナントでは、Microsoft Stream がその国内のデータ所在地のリージョンで利用できるようになった後でも、既存および新規のレコーディングに引き続き Microsoft Stream ストレージが使用されます。

お客様の Microsoft Stream データが保存されるリージョンを確認するには、Microsoft Stream で、右上隅にある **[?]** をクリックし、 **[About Microsoft Stream](Microsoft Stream について)** をクリックして、**[Your data is stored in](データの保存場所)** をクリックします。  Microsoft Stream でデータが保存されるリージョンについて詳しくは、「[Microsoft Stream FAQ](https://docs.microsoft.com/stream/faq#which-regions-does-microsoft-stream-host-my-data-in)」を参照してください。

Office 365 または Office 365 のサービス全体のデータの保存場所について詳しくは、「[データの保管場所](https://products.office.com/where-is-your-data-located?rtc=1)」を参照してください。

### <a name="turn-on-or-turn-off-recording-transcription"></a>記録の文字起こしを有効または無効にする

この設定は、会議の記録の再生中にキャプションと文字起こし機能を使用できるかどうかを制御します。 これをオフにすると、会議の記録の再生中に [**検索**] および [**CC**] オプションを使用できなくなります。 記録を開始したユーザーは、記録に文字起こしも含まれるように、この設定を有効にする必要があります。

> [!NOTE]
> 記録された会議の文字起こしは、現在 Teams の言語が英語に設定されているユーザー、および会議で英語が話されている場合のみサポートされていることに注意してください。 これらは、Microsoft Stream クラウド ストレージに会議のレコーディングと共に保存されます。

Microsoft Teams 管理センターまたは PowerShell を使用して、Teams の会議ポリシーを設定すると、レコーディングを開始するユーザーが会議のレコーディングを文字起こしする機能を選択できるかどうかを制御できます。

Microsoft Teams 管理センターを使用する場合は、会議ポリシーの **[Allow transcription](議事録作成を許可する)** 設定をオンまたはオフにします。 詳細については、「[Teams での会議ポリシーを管理する](meeting-policies-in-teams.md#allow-transcription)」を参照してください。

PowerShell を使用する場合は、TeamsMeetingPolicy で AllowTranscription 設定を構成します。 詳細については、「[New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy)」および「[Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)」を参照してください。

管理者がユーザーにカスタム ポリシーを割り当てていない限り、ユーザーはグローバル ポリシーを取得します。グローバル ポリシーでは、既定で AllowTranscription が無効になっています。

ユーザーがグローバル ポリシーにフォールバックするには、次のコマンドレットを使用して、ユーザーの特定のポリシーの割り当てを削除します。

```powershell
Grant-CsTeamsMeetingPolicy -Identity {user} -PolicyName $null -Verbose
```

グローバル ポリシーの AllowCloudRecording の値を変更するには、次のコマンドレットを使用します。

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -AllowTranscription $false
```

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

1 時間のレコーディングのサイズは 400 MB です。 記録されたファイルに必要な容量を理解していること、および Microsoft Stream で使用できる十分なストレージがあることを確認します。  サブスクリプションに含まれている基本ストレージ、および追加のストレージの購入方法については「[Microsoft Stream ライセンスの概要](https://docs.microsoft.com/stream/license-overview)」をお読みください。

## <a name="manage-meeting-recordings"></a>会議のレコーディングを管理する

会議のレコーディングは、テナントで所有されるコンテンツとみなされます。 レコーディングの所有者が退職する場合、管理者は、管理者モードで Microsoft Stream のレコーディング ビデオ URL を開くことができます。 管理者は、そのレコーディングの削除、任意のレコーディング メタデータの更新、レコーディング ビデオに対するアクセス許可の変更を実行できます。 [Stream での管理機能](https://docs.microsoft.com/stream/manage-content-permissions)の詳細をご確認ください。

> [!NOTE]
> レコーディングとユーザー アクセスを管理する方法の詳細については、「[Microsoft Stream でユーザー データを管理する](https://docs.microsoft.com/stream/managing-user-data)」と「[Microsoft Stream でのアクセス許可とプライバシー](https://docs.microsoft.com/stream/portal-permissions)」を参照してください。

## <a name="compliance-and-ediscovery-for-meeting-recordings"></a>会議のレコーディングのコンプライアンスと電子情報開示

会議のレコーディングは、Microsoft 365 と Office 365 の C レベルに準拠している Microsoft Stream に保存されます。 Microsoft Streams の会議や通話のレコーディングに関心があるコンプライアンス管理者の電子情報開示要求をサポートするため、Microsoft Teams のコンプライアンス コンテンツ検索機能ではレコーディング完了メッセージを利用できます。 コンプライアンス管理者は、コンプライアンス コンテンツ検索プレビューのアイテムの件名で "レコーディング" をキーワード検索して、組織内の会議や通話のレコーディングを見つけることができます。 コンプライアンス管理者がすべてのレコーディングを表示するための前提条件として、コンプライアンス管理者は Microsoft Stream の設定で管理アクセスを付与されている必要があります。 詳細については、「[Assign Microsoft Stream admins](https://docs.microsoft.com/stream/assign-administrator-user-role)」(Microsoft Stream で管理者を割り当てる) を参照してください。

## <a name="related-topics"></a>関連項目

- [Teams での PowerShell の概要](teams-powershell-overview.md)
