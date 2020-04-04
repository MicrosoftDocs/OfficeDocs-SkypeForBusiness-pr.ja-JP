---
title: コンテンツの電子情報開示調査の実施
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- SPO_Content
ms.reviewer: anach
search.appverid: MET150
f1.keywords:
- NOCSH
description: 法的な手続きのために電子的に保存された情報をすべて提出する必要がある場合など、電子情報開示を実行する必要がある場合の対処方法について説明します。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 955fbf6ba937ca0fc11270cb58c12a0349d46330
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/03/2020
ms.locfileid: "43136687"
---
# <a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a>Microsoft Teams のコンテンツに対して電子情報開示の調査を行う

大企業は、多くの場合、電子的に保存されている情報 (ESI) の申請を要求する高ペナルティ法的手続きにさらされています。

すべての Teams 1:1 またはグループチャットは、それぞれのユーザーのメールボックスにジャーナリングされ、すべての標準チャネルメッセージは、チームを表すグループメールボックスによってジャーナリングされます。 標準チャネルにアップロードされたファイルについては、SharePoint Online と OneDrive for business の電子情報開示機能の下に記載されています。 [プライベートチャネル](private-channels.md)のメッセージやファイルの電子情報開示は、標準チャネルでの動作とは異なります。 詳細については、「[プライベートチャネルの電子情報開示](#ediscovery-of-private-channels)」を参照してください。

> [!NOTE]
> 現時点では、ゲストユーザが1:1 または 1: N のチャットで唯一の参加者であるシナリオでは、チャットメッセージの電子情報開示はサポートされていません。 これらの種類のチャットは、*ゲスト間*のチャットとも呼ばれます。これは、ホームテナントのユーザーが含まれていないためです。

1. Microsoft Teams のコンテンツで電子情報開示の調査を実施するには、[この](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da)リンクの手順1を確認してください。

2. Microsoft Teams のデータは、Excel eDiscovery のエクスポート出力で IM または会話として表示され、Outlook で PST を開いて、エクスポート後のメッセージを表示することができます。

    チームの PST を表示している場合は、すべてのスレッドが [会話履歴] の下にあるチームチャットフォルダーに保存されていることに注意してください。 メッセージのタイトルは、チームとチャネルに揃えて配置されます。 以下の画像を確認すると、製造仕様チームのプロジェクト7標準チャネルを送信先しているボブからのメッセージが表示されます。

    ![Outlook のユーザーのメールボックス内のチームチャットフォルダーのスクリーンショット](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

3. ユーザーのメールボックスにプライベートなチャットを表示するには、[会話履歴] の下にあるチームチャットフォルダーにも配置します。

## <a name="ediscovery-of-private-channels"></a>プライベートチャネルの電子情報開示

プライベート チャネルで送信されたメッセージのレコードは、グループのメールボックスではなく、すべてのプライベート チャネル メンバーのメールボックスに配信されます。 レコードのタイトルは、送信元のプライベート チャネルが示されるように書式設定されています。

各プライベートチャネルには、親チームサイトとは別の SharePoint サイトコレクションがあるため、プライベートチャネルのファイルは親チームとは独立して管理されます。

チームは1つのチャネルの電子情報開示をサポートしていないため、チーム全体を検索する必要があります。 プライベートチャネルのコンテンツの電子情報開示検索を実行するには、チーム全体、プライベートチャネルに関連付けられたサイトコレクション (ファイルを含む)、プライベートチャネルメンバーのメールボックス (メッセージを含む) を検索します。

次の手順を使用して、プライベートチャネル内のファイルとメッセージを特定し、電子情報開示検索に含めることができます。

### <a name="include-private-channel-files-in-an-ediscovery-search"></a>電子情報開示検索でプライベートチャネルファイルを含める

これらの手順を実行する前に、 [Sharepoint Online 管理シェルをインストールして、Sharepoint online に接続](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)します。

1. チーム内のプライベートチャネルに関連付けられているすべての SharePoint サイトコレクションの一覧を取得するには、次の操作を実行します。

    ```PowerShell
    Get-SPOSite
    ```

2. 次の PowerShell スクリプトを実行して、チーム内のプライベートチャネルと親チームグループ ID に関連付けられたすべての SharePoint サイトコレクション Url の一覧を取得します。

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url} 
    ```

3. チームまたはグループの ID ごとに、次の PowerShell スクリプトを実行して、関連するすべてのプライベートチャネルサイト ($groupID はチームのグループ ID) を特定します。

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "e8195240-4a70-4830-9106-80193cf717cb"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-an-ediscovery-search"></a>電子情報開示検索でプライベートチャネルメッセージを含める

これらの手順を実行する前に、[最新バージョンの Teams PowerShell モジュール](teams-powershell-overview.md)がインストールされていることを確認してください。

1. チーム内のプライベートチャネルの一覧を取得するには、次の操作を実行します。

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```

2. プライベートチャネルメンバーの一覧を取得するには、次を実行します。

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```

3. 電子情報開示検索クエリの一部として、チーム内の各プライベートチャネルからすべてのメンバーのメールボックスを含めることができます。

## <a name="related-topics"></a>関連項目

- [Teams での PowerShell の概要](teams-powershell-overview.md)
