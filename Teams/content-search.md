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
description: Microsoft 365 コンプライアンス センターでコンテンツ検索を使用して、Exchange Online、SharePoint Online、OneDrive for Business、OneNote に保存されている Microsoft Teams のコンテンツを検索する方法について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: f91e630b6f0666def3e64e40e68a6a3f18097152
ms.sourcegitcommit: 0b584d40e95cbde33cee3691edadb12156d72fb5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "49980441"
---
<a name="use-content-search-in-microsoft-teams"></a>Microsoft Teams でコンテンツ検索を使用する
=====================================

> [!NOTE]
> プライベート チャネルでのメッセージやファイルのコンテンツ検索は [、](private-channels.md) 標準チャネルとは異なる動作をします。 詳細については、「プライベート チャネルの [コンテンツ検索」を参照してください](#content-search-of-private-channels)。

コンテンツ検索は、Exchange、SharePoint Online、OneDrive for Business に関する Microsoft Teams の情報を照会する方法を提供します。

詳細については [、Microsoft 365 のコンテンツ検索を参照してください](https://docs.microsoft.com/microsoft-365/compliance/content-search)。

たとえば、製造仕様メールボックスと製造仕様 SharePoint サイトに対してコンテンツ検索を使用すると、Exchange からの Teams の標準チャネルの会話、SharePoint Online からのファイルのアップロードと変更、OneNote の変更を検索できます。

クエリ条件をコンテンツ検索に追加して **、** 返される結果を絞り込む方法もできます。 上記の例では、キーワード **"New Factory Specs"** が使用されたコンテンツを検索できます。

> [!TIP]
> 検索条件を追加した後、レポートまたは実際のコンテンツを分析のためにコンピューターにエクスポートできます。

## <a name="content-search-of-private-channels"></a>プライベート チャネルのコンテンツ検索

プライベート チャネルで送信されたメッセージのレコードは、グループのメールボックスではなく、すべてのプライベート チャネル メンバーのメールボックスに配信されます。 レコードのタイトルは、送信元のプライベート チャネルが示されるように書式設定されています。

各プライベート チャネルには、親チーム サイトとは別の独自の SharePoint サイト コレクションが用意されています。プライベート チャネル内のファイルは、親チームとは独立して管理されます。

Teams は 1 つのチャネルのコンテンツ検索をサポートしないので、チーム全体を検索する必要があります。 プライベート チャネルのコンテンツ検索を実行するには、チーム、プライベート チャネルに関連付けられているサイト コレクション (ファイルを含める)、プライベート チャネル メンバーのメールボックス (メッセージを含める) を検索します。

コンテンツ検索に含めるプライベート チャネル内のファイルとメッセージを識別するには、次の手順を使用します。

### <a name="include-private-channel-files-in-a-content-search"></a>コンテンツ検索にプライベート チャネル ファイルを含める

これらの手順を実行する前に、SharePoint Online 管理シェルをインストールし [、SharePoint Online に接続します](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)。

1. チーム内のプライベート チャネルに関連付けられているすべての SharePoint サイト コレクションの一覧を取得するには、次を実行します。

    ```PowerShell
    Get-SPOSite
    ```
2. 次の PowerShell スクリプトを実行して、チーム内のプライベート チャネルに関連付けられているすべての SharePoint サイト コレクション URL と親チーム グループ ID の一覧を取得します。

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

これらの手順を実行する前に、最新バージョンの [Teams PowerShell モジュールがインストールされていることを確認](teams-powershell-overview.md) します。

1. チーム内のプライベート チャネルの一覧を取得するには、次を実行します。

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```
2. プライベート チャネル メンバーの一覧を取得するには、次を実行します。

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```
3. コンテンツ検索クエリの一部として、チームの各プライベート チャネルのすべてのメンバーのメールボックスを含める。

## <a name="related-topics"></a>関連項目

- [Microsoft 365 コンプライアンス センターの電子情報開示ケース](https://docs.microsoft.com/Office365/SecurityCompliance/ediscovery-cases) 