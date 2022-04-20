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
description: Microsoft Purview コンプライアンス ポータルでコンテンツ検索を使用して、Exchange Online、SharePoint Online、OneDrive for Business、OneNoteに格納されているMicrosoft Teams コンテンツを検索する方法について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 00de0bb3ecdcaf6dc674f08438b896abaaa49448
ms.sourcegitcommit: 1d990582e2deb5f55ba9adada3e17377f792a141
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2022
ms.locfileid: "64922478"
---
# <a name="use-content-search-in-microsoft-teams"></a>Microsoft Teamsでコンテンツ検索を使用する

> [!NOTE]
> [プライベート チャネル](private-channels.md)内のメッセージとファイルのコンテンツ検索は、標準チャネルとは異なります。 詳細については、「 [プライベート チャネルのコンテンツ検索](#content-search-of-private-channels)」を参照してください。

コンテンツ検索は、Exchange、SharePoint Online、およびOneDrive for BusinessにまたがるMicrosoft Teams情報にクエリを実行する方法を提供します。

詳細については、[Microsoft 365のコンテンツ検索に関](/microsoft-365/compliance/content-search)するページを参照してください。

たとえば、製造仕様メールボックスと製造スペック SharePoint サイトに対する **コンテンツ検索** を使用すると、Exchangeからの標準チャネル会話Teams、SharePoint Online からのファイルのアップロードと変更、および変更OneNoteを検索できます。

**コンテンツ検索** にクエリ条件を追加して、返された結果を絞り込むこともできます。 上の例では、キーワード "**New Factory Specs"** が使用されたコンテンツを探すことができます。

> [!TIP]
> 検索条件を追加した後、分析のためにレポートまたは実際のコンテンツをコンピューターにエクスポートできます。

## <a name="content-search-of-private-channels"></a>プライベート チャネルのコンテンツ検索

プライベート チャネルで送信されたメッセージのレコードは、グループのメールボックスではなく、すべてのプライベート チャネル メンバーのメールボックスに配信されます。 レコードのタイトルは、送信元のプライベート チャネルが示されるように書式設定されています。

各プライベート チャネルには、親チーム サイトとは別の独自のSharePoint サイト コレクションがあるため、プライベート チャネル内のファイルは親チームとは独立して管理されます。

Teamsは 1 つのチャネルのコンテンツ検索をサポートしていないため、チーム全体を検索する必要があります。 プライベート チャネルのコンテンツ検索を実行するには、チーム全体、プライベート チャネルに関連付けられているサイト コレクション (ファイルを含む)、プライベート チャネル メンバーのメールボックス (メッセージを含む) を検索します。

次の手順を使用して、コンテンツ検索に含めるプライベート チャネル内のファイルとメッセージを識別します。

### <a name="include-private-channel-files-in-a-content-search"></a>コンテンツ検索にプライベート チャネル ファイルを含める

これらの手順を実行する前に、[SharePoint Online Management Shell をインストールし、SharePoint Online に接続](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)します。

1. 次を実行して、チーム内のプライベート チャネルに関連付けられているすべてのSharePoint サイト コレクションの一覧を取得します。

    ```PowerShell
    Get-SPOSite
    ```
2. 次の PowerShell スクリプトを実行して、チーム内のプライベート チャネルと親チーム グループ ID に関連付けられているすべてのSharePoint サイト コレクション URL の一覧を取得します。

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

これらの手順を実行する前に、[Teams PowerShell モジュールの最新バージョンが](teams-powershell-overview.md)インストールされていることを確認してください。

1. 次を実行して、チーム内のプライベート チャネルの一覧を取得します。

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```
2. 次を実行して、プライベート チャネル メンバーの一覧を取得します。

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```
3. コンテンツ検索クエリの一部として、チーム内の各プライベート チャネルのすべてのメンバーのメールボックスを含めます。

## <a name="related-topics"></a>関連項目

- [Microsoft Purview コンプライアンス ポータルの電子情報開示ケース](/Office365/SecurityCompliance/ediscovery-cases)