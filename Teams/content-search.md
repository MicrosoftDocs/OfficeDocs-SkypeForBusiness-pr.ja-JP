---
title: Microsoft Teams のコンテンツ検索を使用する
author: markjjo
ms.author: markjjo
manager: laurawi
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
- SPO_Content
ms.reviewer: anwara
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: seo-marvel-mar2020
description: Microsoft 365 コンプライアンス センターでコンテンツ検索を使用して、Exchange Online、SharePoint Online、OneDrive for Business、OneNote に保存されている Microsoft Teams コンテンツを検索する方法について学習します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: cb63f3668ef03cdaf760a24ae1df0a815e7f282d
ms.sourcegitcommit: 36bc47b2b9ee0e738fa814c31accacfe816da4a3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2021
ms.locfileid: "52855806"
---
# <a name="use-content-search-in-microsoft-teams"></a>Microsoft Teams でコンテンツ検索を使用する

> [!NOTE]
> プライベート チャネルでのメッセージとファイルのコンテンツ [検索は、](private-channels.md) 標準チャネルとは異なる方法で動作します。 詳細については、「プライベート チャネルの [コンテンツ検索」を参照してください](#content-search-of-private-channels)。

コンテンツ検索では、オンライン、オンライン、Microsoft TeamsにExchange情報SharePointクエリを実行OneDrive for Business。

詳細については、「コンテンツ検索」[を参照Microsoft 365。](/microsoft-365/compliance/content-search)

たとえば、製造仕様メールボックスと製造仕様 SharePoint サイトに対してコンテンツ検索を使用すると、Exchange からの Teams 標準チャネルの会話、SharePoint Online からのファイルのアップロードと変更、OneNote の変更に対して検索できます。

クエリ条件をコンテンツ検索に追加して **、** 返される結果を絞り込む方法も可能です。 上記の例では、キーワード **"New Factory Specs"** が使用されたコンテンツを検索できます。

> [!TIP]
> 検索条件を追加した後、レポートまたは実際のコンテンツを分析のためにコンピューターにエクスポートできます。

## <a name="content-search-of-private-channels"></a>プライベート チャネルのコンテンツ検索

プライベート チャネルで送信されたメッセージのレコードは、グループのメールボックスではなく、すべてのプライベート チャネル メンバーのメールボックスに配信されます。 レコードのタイトルは、送信元のプライベート チャネルが示されるように書式設定されています。

各プライベート チャネルには、親チーム サイトとは別の独自の SharePoint サイト コレクションが用意されています。プライベート チャネル内のファイルは、親チームとは独立して管理されます。

Teamsは 1 つのチャネルのコンテンツ検索をサポートしないので、チーム全体を検索する必要があります。 プライベート チャネルのコンテンツ検索を実行するには、チーム全体、プライベート チャネルに関連付けられているサイト コレクション (ファイルを含める)、プライベート チャネル メンバーのメールボックス (メッセージを含める) を検索します。

次の手順を使用して、コンテンツ検索に含めるプライベート チャネル内のファイルとメッセージを識別します。

### <a name="include-private-channel-files-in-a-content-search"></a>コンテンツ検索にプライベート チャネル ファイルを含める

これらの手順を実行する前に、SharePoint Online Management Shell をインストールし、SharePoint [Online に接続します](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)。

1. 次のコマンドを実行して、チーム内のプライベート SharePointに関連付けられているすべてのサイト コレクションの一覧を取得します。

    ```PowerShell
    Get-SPOSite
    ```
2. 次の PowerShell スクリプトを実行して、チーム内のプライベート チャネルSharePoint関連付けられているすべてのサイト コレクション URL と親チーム グループ ID の一覧を取得します。

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url} 
    ```
3. チームまたはグループ ID ごとに、次の PowerShell スクリプトを実行して、関連するすべてのプライベート チャネル サイトを識別します。

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "e8195240-4a70-4830-9106-80193cf717cb"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-a-content-search"></a>コンテンツ検索にプライベート チャネル メッセージを含める

これらの手順を実行する前に、PowerShell モジュールの最新バージョンが[インストールTeams確認](teams-powershell-overview.md)してください。

1. 次のコマンドを実行して、チーム内のプライベート チャネルの一覧を取得します。

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```
2. プライベート チャネル メンバーの一覧を取得するには、次のコマンドを実行します。

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```
3. コンテンツ検索クエリの一部として、チーム内の各プライベート チャネルのすべてのメンバーのメールボックスを含める。

## <a name="related-topics"></a>関連項目

- [Microsoft 365 コンプライアンス センターの電子情報開示ケース](/Office365/SecurityCompliance/ediscovery-cases)