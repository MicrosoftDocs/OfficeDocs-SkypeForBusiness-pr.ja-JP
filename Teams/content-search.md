---
title: Microsoft Teams のコンテンツ検索を使用する
description: Microsoft Purview コンプライアンス ポータルでコンテンツ検索を使用して、Exchange Online、SharePoint Online、OneDrive for Business、OneNote に格納されている Microsoft Teams コンテンツを検索する方法について説明します。
author: robmazz
ms.author: robmazz
manager: laurawi
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- tier1
- purview-compliance
- M365-collaboration
- content-search
ms.reviewer: anwara
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: ff8ee3990b1ebf406fbecaff3e090f010e2beb2a
ms.sourcegitcommit: 507e186972bcbc56c1547a1b9f357bfd38170b5a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/27/2022
ms.locfileid: "68046517"
---
# <a name="use-content-search-in-microsoft-teams"></a>Microsoft Teams でコンテンツ検索を使用する

> [!NOTE]
> [プライベート チャネル](private-channels.md)内のメッセージとファイルのコンテンツ検索は、標準チャネルとは異なります。 詳細については、「 [プライベート チャネルのコンテンツ検索](#content-search-of-private-channels)」を参照してください。

コンテンツ検索は、Exchange、SharePoint Online、およびOneDrive for Businessに及ぶ Microsoft Teams 情報に対してクエリを実行する方法を提供します。

詳細については、 [Microsoft 365 のコンテンツ検索に関するページを](/microsoft-365/compliance/content-search)参照してください。

たとえば、製造仕様メールボックスと製造仕様 SharePoint サイトに対する **コンテンツ検索** を使用すると、Exchange からの Teams 標準チャネル会話、SharePoint Online からのファイルのアップロードと変更、および OneNote の変更に対して検索できます。

**コンテンツ検索** にクエリ条件を追加して、返された結果を絞り込むこともできます。 上の例では、キーワード "**New Factory Specs"** が使用されたコンテンツを探すことができます。

> [!TIP]
> 検索条件を追加した後、分析のためにレポートまたは実際のコンテンツをコンピューターにエクスポートできます。

## <a name="content-search-of-private-channels"></a>プライベート チャネルのコンテンツ検索

プライベート チャネルで送信されたメッセージのレコードは、グループのメールボックスではなく、すべてのプライベート チャネル メンバーのメールボックスに配信されます。 レコードのタイトルは、送信元のプライベート チャネルが示されるように書式設定されています。

各プライベート チャネルには、親チーム サイトとは別の独自の SharePoint サイト コレクションがあるため、プライベート チャネル内のファイルは親チームとは独立して管理されます。

Teams は 1 つのチャネルのコンテンツ検索をサポートしていないため、チーム全体を検索する必要があります。 プライベート チャネルのコンテンツ検索を実行するには、チーム全体、プライベート チャネルに関連付けられているサイト コレクション (ファイルを含む)、プライベート チャネル メンバーのメールボックス (メッセージを含む) を検索します。

次の手順を使用して、コンテンツ検索に含めるプライベート チャネル内のファイルとメッセージを識別します。

### <a name="include-private-channel-files-in-a-content-search"></a>コンテンツ検索にプライベート チャネル ファイルを含める

これらの手順を実行する前に、 [SharePoint Online 管理シェルをインストールし、SharePoint Online に接続します](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)。

1. 次を実行して、チーム内のプライベート チャネルに関連付けられているすべての SharePoint サイト コレクションの一覧を取得します。

    ```PowerShell
    Get-SPOSite
    ```
2. 次の PowerShell スクリプトを実行して、チーム内のプライベート チャネルと親チーム グループ ID に関連付けられているすべての SharePoint サイト コレクション URL の一覧を取得します。

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

これらの手順を実行する前に、 [Teams PowerShell モジュールの最新バージョンが](teams-powershell-overview.md) インストールされていることを確認してください。

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