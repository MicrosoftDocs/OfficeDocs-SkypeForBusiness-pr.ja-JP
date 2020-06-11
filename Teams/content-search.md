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
f1.keywords:
- NOCSH
ms.custom: seo-marvel-mar2020
description: Microsoft Teams のコンテンツ検索を使用して、Exchange、SharePoint Online、OneDrive for Business、OneNote から Microsoft Teams の情報を照会する方法について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 45da4a0f4acf66cb8caafcd8d2bc2287c1176c94
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2020
ms.locfileid: "44690443"
---
<a name="use-content-search-in-microsoft-teams"></a>Microsoft Teams のコンテンツ検索を使用する
=====================================

> [!NOTE]
> [プライベートチャネル](private-channels.md)でのメッセージやファイルのコンテンツ検索の動作は、標準チャネルとは異なります。 詳細については、「[プライベートチャネルのコンテンツ検索](#content-search-of-private-channels)」を参照してください。

コンテンツ検索を使用すると、Exchange、SharePoint Online、OneDrive for Business にわたる Microsoft Teams の情報を照会することができます。

詳細については、「 [Microsoft 365 または Office 365 でコンテンツ検索](https://support.office.com/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a)を読む」を参照してください。

たとえば、製造仕様のメールボックスと製造仕様の SharePoint サイトに対して**コンテンツ検索**を使用すると、Exchange からの Teams 標準チャネルの会話、sharepoint Online からのファイルのアップロードと変更、OneNote の変更を検索することができます。

**コンテンツ検索**にクエリ条件を追加して、返される結果を絞り込むこともできます。 上の例では、"**新しいファクトリの仕様"** というキーワードが使用されているコンテンツを確認できます。

> [!TIP]
> 検索条件を追加した後は、レポートまたはデータをコンピューターにエクスポートして分析することができます。

## <a name="content-search-of-private-channels"></a>プライベートチャネルのコンテンツ検索

プライベート チャネルで送信されたメッセージのレコードは、グループのメールボックスではなく、すべてのプライベート チャネル メンバーのメールボックスに配信されます。 レコードのタイトルは、送信元のプライベート チャネルが示されるように書式設定されています。

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
    $groupID = "e8195240-4a70-4830-9106-80193cf717cb"
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

- [Microsoft 365 コンプライアンスセンターの電子情報開示ケース](https://docs.microsoft.com/Office365/SecurityCompliance/ediscovery-cases) 