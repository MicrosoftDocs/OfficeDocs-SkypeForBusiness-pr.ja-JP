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
ms.reviewer: nakulm
search.appverid: MET150
f1.keywords:
- NOCSH
description: オーディオ、ビデオ、画面共有のアクティビティをキャプチャするために、チームの会議とグループの通話を記録するためにクラウド音声機能を展開するための実用的なガイダンス。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c0030cdc3a7e4929435127f9c4fbe549c7a6bf20
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503464"
---
# <a name="teams-cloud-meeting-recording"></a>Teams のクラウド会議のレコーディング

Microsoft Teams では、ユーザーは Teams 会議やグループ通話を記録して、音声、ビデオ、および画面共有のアクティビティをキャプチャできます。 自動的に文字起こしする記録のオプションもあるため、ユーザーはミーティングの記録を字幕付きで再生して、会議内容の重要な議題を検索できます。 レコーディングはクラウドで実行され、[Microsoft Stream](https://docs.microsoft.com/stream/) に保存されるため、ユーザーは組織全体で安全にそのレコーディングを共有できます。

関連: [Teams 会議のレコーディングに関するエンド ユーザー向けドキュメント](https://aka.ms/recordmeeting)

>[!Note]
> Microsoft Stream の使用から [会議の記録用の OneDrive for Business および SharePoint ](tmr-meeting-recording-change.md)への変更は段階的なアプローチになります。 リリース時には、この機能にオプトインできるようになります。Stream を使い続けるには、11 月にオプトアウトする必要があります。また、2021 年初頭には、すべてのお客様に、会議の記録に OneDrive と SharePoint を使用するように要請する予定です。

> [!NOTE]
> Teams 会議での役割の使用について、およびユーザーの役割を変更する方法については、「 [teams 会議の役割](https://support.microsoft.com/en-us/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us)」を参照してください。

## <a name="prerequisites-for-teams-cloud-meeting-recording"></a>Teams のクラウド会議をレコーディングするための前提条件

チームユーザーの会議を記録するには、テナントに対して Microsoft Stream を有効にする必要があります。 また、会議の開催者とレコーディングを開始するユーザーの双方は、次の前提条件を満たす必要があります。

- ユーザーは、Office 365 E1、E3、E5、A1、A3、A5、Microsoft 365 Business Premium、ビジネス標準、またはビジネス Basic<sup>1</sup>を持っています。
- ユーザーに Microsoft Stream<sup>2</sup>のライセンスが必要です 
- Microsoft Stream でビデオをアップロードするアクセス許可を持っている
- 会社のガイドラインが管理者によって設定されている場合、そのガイドラインに同意している
- レコーディングを保存するのに十分なストレージを Microsoft Stream に確保している
- TeamsMeetingPolicy-AllowCloudRecording 設定が true に設定されている
- その会議の匿名ユーザー、ゲスト ユーザー、フェデレーション ユーザーではない
- ユーザーの会議に対して議事録を有効にするには、割り当てられている Teams の会議ポリシーで、-AllowTranscription 設定を true に設定する必要があります。

<sup>1</sup> 2020 年8月20日の間、会議レコーディングファイルへのアクセスは21日が経過すると、A1 を使用しているユーザーの有効期限が切れます。 詳細については、「 [Microsoft Teams の会議レコーディングをストリーミングにアップロードする](https://docs.microsoft.com/stream/portal-upload-teams-meeting-recording)」を参照してください。

<sup>2</sup> Microsoft Stream との会議をアップロード/ダウンロードするには、ライセンスが必要ですが、会議を記録するためのライセンスは必要ありません。 あるユーザーが Microsoft Teams の会議をレコーディングできないようにするには、AllowCloudRecording が $False に設定されている TeamsMeetingPolicy を付与する必要があります。

> [!IMPORTANT] 
> ユーザーに録音とそれのダウンロードのみを許可する場合は、Microsoft Stream のライセンスを割り当てる必要はありません。 これは、レコーディングが Microsoft Stream に保存されていないことを意味しますが、その記録は、削除される前に21日間の制限付きで Azure メディアサービス (AMS) に保存されます。 現時点では、削除機能を含め、管理者が制御または管理できるものではありません。

## <a name="set-up-teams-cloud-meeting-recording-for-users-in-your-organization"></a>組織内のユーザーに対して Teams のクラウド会議のレコーディングを設定する

このセクションでは、Teams 会議をレコーディングするための設定方法と計画方法について説明します。

### <a name="turn-on-microsoft-stream-for-users-in-the-organization"></a>組織内のユーザーに対して Microsoft Stream を有効にする

Microsoft Stream は、適格な Microsoft 365 および Office 365 サブスクリプションの一部として、またはスタンドアロンサービスとして利用できます。  詳細については、「[Microsoft Stream ライセンスの概要](https://docs.microsoft.com/stream/license-overview)」を参照してください。  Microsoft Stream は、microsoft 365 Business、Microsoft 365 Business Standard、および Microsoft 365 Business Basic に含まれるようになりました。

ユーザーが Microsoft Stream にアクセスできるように、 [microsoft 365 または Office 365 でユーザーにライセンスを割り当てる](https://support.office.com/article/Assign-licenses-to-users-in-Office-365-for-business-997596B5-4173-4627-B915-36ABAC6786DC) 方法について説明します。 Microsoft stream [のブロックサイン](https://docs.microsoft.com/stream/disable-user-organization)アップで定義されているように、ユーザーに対して microsoft stream がブロックされていないことを確認します。

### <a name="make-sure-users-have-upload-video-permissions-in-microsoft-stream"></a>ユーザーが Microsoft Stream でビデオのアクセス許可をアップロードしていることを確認する

既定では、Stream が有効になっており、ユーザーにライセンスが割り当てられていれば、社内のすべてのユーザーが Stream でコンテンツを作成できます。 Microsoft Stream の管理者は、Stream で[コンテンツを作成できる従業員を制限する](https://docs.microsoft.com/stream/restrict-uploaders)ことができます。 この制限リストに記載されているユーザーは、会議を記録できません。

### <a name="notify-employees-to-consent-to-company-guidelines-in-microsoft-stream"></a>Microsoft Stream で会社のガイドラインに同意するよう従業員に通知する

Microsoft Stream の管理者が[会社のガイドライン ポリシーを設定](https://docs.microsoft.com/stream/company-policy-and-consent)しており、コンテンツを保存する前にこのポリシーを承諾することを従業員に求めている場合、ユーザーは Microsoft Teams でレコーディングする前にポリシーを承諾する必要があります。 その組織のレコーディング機能を展開する前に、ユーザーがポリシーに同意していることを確認してください。

### <a name="turn-on-or-turn-off-cloud-recording"></a>クラウド レコーディングを開始または停止する

Microsoft Teams 管理センターまたは PowerShell を使用して、Teams の会議ポリシーを設定すると、ユーザーの会議を記録できるかどうかを制御できます。

Microsoft Teams 管理センターを使用する場合は、会議ポリシーの **[Allow cloud recording](クラウド レコーディングを許可する)** 設定をオンまたはオフにします。 詳細については、「[Teams での会議ポリシーを管理する](meeting-policies-in-teams.md#allow-cloud-recording)」を参照してください。

PowerShell を使用する場合は、TeamsMeetingPolicy で AllowCloudRecording 設定を構成します。 詳細については、「[New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy)」および「[Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)」を参照してください。

会議をレコーディングするには、会議の開催者とレコーディングを開始するユーザーの双方に、レコーディングのアクセス許可が必要です。 ユーザーにカスタムポリシーを割り当てていない限り、ユーザーはグローバルポリシーを取得します。これには、既定で AllowCloudRecording が有効になっています。

> [!NOTE]
> チームロールを使用して、会議を記録する権限を持つユーザーを構成する方法については、「 [teams 会議のロール](https://support.microsoft.com/en-us/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us)」を参照してください。

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
|      多くのユーザーに対してレコーディングをオフにして、記録を許可する特定のユーザーを選択する       | <ol><li>グローバルな CsTeamsMeetingPolicy が AllowCloudRecording = False に設定されていることを確認する<li>大半のユーザーについて、AllowCloudRecording = False に設定されたグローバルな CsTeamsMeetingPolicy または CsTeamsMeetingPolicy ポリシーの 1 つが付与されている<li>その他のすべてのユーザーには、AllowCloudRecording = True に設定された CsTeamsMeetingPolicy ポリシーの 1 つが付与されている <ol> |
|                                                                                                                                          |                                                                                                                                                                                                                                                                                                                                                  |
#### <a name="where-your-meeting-recordings-are-stored"></a>会議のレコーディングの保存場所

会議のレコーディングは、Microsoft Stream クラウド ストレージに保存されます。 記録は保持され、21日間は表示およびダウンロードできます。 現在は、データが保存される国内のデータ所在地では Microsoft Stream が利用できない場合、Teams のデータが国内に保存されるお客様の会議のレコーディング機能は無効になっています。 将来、Microsoft Stream がその国内のデータ所在地では利用できない場合でも、データが国内に保存されるお客様が Teams 会議のレコーディング機能をご利用いただけるようになる予定です。

この変更が有効になると、会議のレコーディングは既定で地理的に最も近い Microsoft Stream のリージョンに保存されます。 Teams のデータが国内に保存されており、会議のレコーディングを国内に保存することをご希望の場合は、この機能を無効にし、Microsoft Stream がお客様の国内のデータ所在地のリージョンに展開されてから有効にすることをお勧めします。 組織内のすべてのユーザーに対してこの機能を無効にするには、Microsoft Teams 管理センターのグローバルチーム会議ポリシーで [ **クラウドレコーディングの許可** ] 設定をオフにします。 ただし、記録を Microsoft Stream の最も近い地理的地域に保存することをまだ許可している場合は、この変更が発生する前に、[ **クラウドの記録を許可** する] と [外部の領域を越えて **記録** する] の両方を有効にする必要があります。

グローバルポリシーの地域でのレコーディングを有効にするには、次のコマンドレットを使用します。

```powershell
Set-CsTeamsMeetingPolicy -Identity Global – AllowCloudRecording $true -AllowRecordingStorageOutsideRegion $true
```


この変更が有効になると、会議のレコーディングを開始した場合の動作は次のようになります。

|会議のレコーディングをオンにした場合|会議のレコーディングの保存先... |
|---|---|
|国内のデータ常駐地域で Microsoft Stream を使用できるようにする前に |最寄りの Microsoft Stream 領域|
|国内データ常駐地域で Microsoft Stream を利用できるようになった後 |国内のデータ常駐地域で|

会議のレコーディングが開始していない新規および既存のテナントの場合、Microsoft Stream がその国内のデータ所在地のリージョンで利用できるようになると、新しいレコーディングは国内に保存されます。 ただし、国内データ常駐地域で Microsoft Stream が利用可能になる前に会議レコーディングを有効にするすべてのテナントは、Microsoft Stream が国内のデータ常駐地域で利用できるようになった後でも、既存の録音および新規の記録に Microsoft stream ストレージを使い続けます。

お客様の Microsoft Stream データが保存されるリージョンを確認するには、Microsoft Stream で、右上隅にある **[?]** をクリックし、 **[About Microsoft Stream](Microsoft Stream について)** をクリックして、**[Your data is stored in](データの保存場所)** をクリックします。  Microsoft Stream でデータが保存されるリージョンについて詳しくは、「[Microsoft Stream FAQ](https://docs.microsoft.com/stream/faq#which-regions-does-microsoft-stream-host-my-data-in)」を参照してください。

Microsoft 365 または Office 365 のサービス間でデータが保存される場所の詳細については、「[データがどこにあるか](https://products.office.com/where-is-your-data-located?rtc=1)を確認する」を参照してください。

### <a name="turn-on-or-turn-off-recording-transcription"></a>レコーディングの文字起こしを有効または無効にする

この設定は、会議の記録の再生中にキャプションと文字起こし機能を使用できるかどうかを制御します。 これをオフにすると、会議の記録の再生中に [**検索**] および [**CC**] オプションを使用できなくなります。 記録を開始したユーザーは、記録に文字起こしも含まれるように、この設定を有効にする必要があります。

> [!NOTE]
> 記録された会議のための議事録は、現在のところ、Teams の言語が英語に設定され、会議で英語が話されているユーザーのみがサポートしています。 Microsoft Stream クラウドストレージの会議のレコーディングと共に保存されます。

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

1 時間のレコーディングのサイズは 400 MB です。 記録されたファイルに必要な容量を理解していること、および Microsoft Stream で使用できる十分なストレージがあることを確認します。  サブスクリプションに含まれている基本記憶域と追加記憶域の購入方法を理解するには、 [「Microsoft Stream ライセンスの概要」](https://docs.microsoft.com/stream/license-overview) を参照してください。

## <a name="manage-meeting-recordings"></a>会議のレコーディングを管理する

会議のレコーディングは、テナントで所有されるコンテンツとみなされます。 レコーディングの所有者が退職する場合、管理者は、管理者モードで Microsoft Stream のレコーディング ビデオ URL を開くことができます。 管理者は、そのレコーディングの削除、任意のレコーディング メタデータの更新、レコーディング ビデオに対するアクセス許可の変更を実行できます。 [Stream での管理機能](https://docs.microsoft.com/stream/manage-content-permissions)の詳細をご確認ください。

> [!NOTE]
> レコーディングとユーザー アクセスを管理する方法の詳細については、「[Microsoft Stream でユーザー データを管理する](https://docs.microsoft.com/stream/managing-user-data)」と「[Microsoft Stream でのアクセス許可とプライバシー](https://docs.microsoft.com/stream/portal-permissions)」を参照してください。

## <a name="compliance-and-ediscovery-for-meeting-recordings"></a>会議のレコーディングのコンプライアンスと電子情報開示

会議のレコーディングは Microsoft Stream に保存されます。これは Microsoft 365 と Office 365 Tier C に準拠しています。 Microsoft Streams の会議や通話のレコーディングに関心があるコンプライアンス管理者の電子情報開示要求をサポートするため、Microsoft Teams のコンプライアンス コンテンツ検索機能ではレコーディング完了メッセージを利用できます。 コンプライアンス管理者は、コンプライアンス コンテンツ検索プレビューのアイテムの件名で "レコーディング" をキーワード検索して、組織内の会議や通話のレコーディングを見つけることができます。 コンプライアンス管理者がすべてのレコーディングを表示するための前提条件として、コンプライアンス管理者は Microsoft Stream の設定で管理アクセスを付与されている必要があります。 詳細については、「[Assign Microsoft Stream admins](https://docs.microsoft.com/stream/assign-administrator-user-role)」(Microsoft Stream で管理者を割り当てる) を参照してください。

## <a name="related-topics"></a>関連項目

- [Teams での PowerShell の概要](teams-powershell-overview.md)
