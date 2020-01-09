---
title: Microsoft Teams のコンテンツ検索を使用する
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
- SPO_Content
ms.reviewer: anach
search.appverid: MET150
description: Microsoft Teams のコンテンツ検索について説明し、Exchange からのチャネル会話の検索方法、SharePoint からのファイルのアップロードと変更、OneNote の変更について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: fea6e671a84eec6f064a7ccc1f7f9b3f237a220d
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991082"
---
<a name="use-content-search-in-microsoft-teams"></a>Microsoft Teams のコンテンツ検索を使用する
=====================================

> [!NOTE]
> [プライベートチャネル](private-channels.md)でのメッセージやファイルのコンテンツ検索の動作は、標準チャネルとは異なります。 詳細については、「[プライベートチャネルのコンテンツ検索](#content-search-of-private-channels)」を参照してください。

コンテンツ検索を使用すると、Exchange、SharePoint Online、OneDrive for Business にわたる Microsoft Teams の情報を照会することができます。

詳細については、「 [Office 365 でコンテンツ検索](https://support.office.com/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a)を読む」を参照してください。

たとえば、製造仕様のメールボックスと製造仕様の SharePoint サイトに対して**コンテンツ検索**を使用すると、Exchange からの Teams 標準チャネルの会話、sharepoint Online からのファイルのアップロードと変更、OneNote の変更を検索することができます。

**コンテンツ検索**にクエリ条件を追加して、返される結果を絞り込むこともできます。 上の例では、"**新しいファクトリの仕様"** というキーワードが使用されているコンテンツを確認できます。

> [!TIP]
> 検索条件を追加した後は、レポートまたはデータをコンピューターにエクスポートして分析することができます。

## <a name="content-search-of-private-channels"></a>プライベートチャネルのコンテンツ検索

プライベートチャネルで送信されたメッセージのレコードは、グループメールボックスではなく、すべてのプライベートチャネルメンバーのメールボックスに配信されます。 レコードのタイトルは、送信元のプライベートチャネルを示すように書式設定されます。

各プライベートチャネルには、親チームサイトとは別の SharePoint サイトコレクションがあるため、プライベートチャネルのファイルは親チームとは独立して管理されます。

チームは1つのチャネルのコンテンツ検索をサポートしていないため、チーム全体を検索する必要があります。 プライベートチャネルのコンテンツ検索を実行するには、チーム、プライベートチャネルに関連付けられたサイトコレクション (ファイルを含む)、プライベートチャネルメンバーのメールボックス (メッセージを含む) を検索します。

次の手順を使用して、コンテンツ検索に含めるファイルとプライベートチャネル内のメッセージを識別します。

### <a name="include-private-channel-files-in-a-content-search"></a>コンテンツ検索にプライベートチャネルファイルを含める

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
3. 各チームまたはグループ ID について、次の PowerShell スクリプトを実行して、関連するすべてのプライベートチャネルサイトを特定します。

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = “e8195240-4a70-4830-9106-80193cf717cb“
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-a-content-search"></a>コンテンツ検索にプライベートチャネルメッセージを含める

これらの手順を実行する前に、[最新バージョンの Teams PowerShell モジュール](teams-powershell-overview.md)がインストールされていることを確認してください。

1. チーム内のプライベートチャネルの一覧を取得するには、次の操作を実行します。

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```
2. プライベートチャネルメンバーの一覧を取得するには、次を実行します。

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```
3. コンテンツ検索クエリの一部として、チーム内の各プライベートチャネルからすべてのメンバーのメールボックスを含めます。

## <a name="related-topics"></a>関連項目

- [Office 365 セキュリティ & コンプライアンスセンターの電子情報開示ケース](https://docs.microsoft.com/Office365/SecurityCompliance/ediscovery-cases) 