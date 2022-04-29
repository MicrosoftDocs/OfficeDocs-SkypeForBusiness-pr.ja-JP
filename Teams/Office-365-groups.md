---
title: Microsoft 365 グループとMicrosoft Teams
ms.reviewer: kblevins
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
description: Microsoft 365 グループとグループ メンバーシップがMicrosoft Teamsと連携する方法について説明します。
ms.openlocfilehash: cf84c58e05e65b187ebe9c0d5a4560cf861fb9be
ms.sourcegitcommit: d16fb01f752d186445893ea8e3b0d4450a4a0e67
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/29/2022
ms.locfileid: "65125432"
---
# <a name="microsoft-365-groups-and-microsoft-teams"></a>Microsoft 365 グループとMicrosoft Teams

Microsoft 365 グループは、Microsoft 365のアプリケーション間メンバーシップ サービスです。 基本的なレベルでは、Microsoft 365 グループは、メンバーの一覧と、SharePoint チーム サイト、共有Exchangeメールボックス、Planner、OneNote ノートブックなどの関連ワークロードとの結合を持つAzure Active Directoryのオブジェクトです。 Active Directory の他のグループ ベースのセキュリティ オブジェクトと同様に、グループにユーザーを追加または削除できます。

![Microsoft 365 グループおよび関連するサービスを示す図。](/microsoft-365/media/microsoft-365-groups-hub-spoke.png?view=o365-worldwide)

既定では、Microsoft 365のユーザーはグループを作成および管理できます。 Microsoft 365 グループの詳細については、「[it Architects](teams-architecture-solutions-posters.md#groups-in-microsoft-365) の[Microsoft 365のMicrosoft 365 グループ](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2)とグループの詳細」を参照してください。

## <a name="how-microsoft-365-groups-work-with-teams"></a>Teams Microsoft 365 グループ操作する方法

チームを作成すると、チーム メンバーシップを管理するためにMicrosoft 365 グループが作成されます。 グループの関連サービス (SharePoint サイト、メールボックスなど) が同時に作成されます。

チームを作成するユーザーは、そのグループの所有者であれば、既存のMicrosoft 365 グループを使用することを選択できます。 チーム内の各チャネルには、ドキュメント ライブラリ内に個別のフォルダーがあります。 ドキュメント ライブラリにフォルダーを直接作成しても、チームにチャネルは作成されません。

OutlookまたはSharePointでMicrosoft 365 グループを作成すると、グループ メールボックスがOutlookに表示されます。 Teamsでチームを作成すると、グループ メールボックスは既定で非表示になります。 [Set-UnifiedGroup](/powershell/module/exchange/users-and-groups/set-unifiedgroup) コマンドレットと **HiddenFromExchangeClientsEnabled** パラメーターを使用して、メールボックスを表示できます。

## <a name="group-membership"></a>グループ メンバーシップ

チームのメンバーを削除すると、Microsoft 365 グループからも削除されます。 グループから削除すると、すぐにチームとチャネルがTeams クライアントから削除されます。 Microsoft 365 管理センターを使用してグループからユーザーを削除すると、SharePoint Online ドキュメント ライブラリ、Yammer グループ、共有OneNoteなどの他の共同作業の側面にアクセスできなくなります。 ただし、チームは約 2 時間、チームのチャット機能にアクセスできます。

チーム メンバーを管理するためのベスト プラクティスとして、それらをTeams クライアントに追加および削除して、他のグループに接続されたワークロードのアクセス許可の更新が迅速に行われるようにします。 Teams クライアントの外部で (Microsoft 365 管理センター、Azure AD、Exchange Online PowerShell を使用して) チーム メンバーを追加または削除すると、変更がTeamsに反映されるまでに最大 24 時間かかる場合があります。

## <a name="deleting-groups-and-teams"></a>グループとチームの削除

Microsoft 365 グループを削除すると、永続的なOutlook/OWA 会話と会議出席依頼のTeamsメールボックス エイリアスが削除され、SharePoint サイトに削除のマークが付けられます。 チームの削除からOutlookへの影響まで約 20 分かかります。 Teams クライアントからチームを削除すると、チームのメンバーであるすべてのユーザーがすぐに削除されます。 Teams機能が有効になっているMicrosoft 365 グループのメンバーを削除すると、削除された影響を受けたユーザーに対して、チームがTeams クライアントでビューから削除されるまでに約 2 時間の遅延が発生する可能性があります。

グループとチームのライフサイクル終了オプションの詳細については、「[グループ、チーム、Yammerのライフサイクルの終了オプション](/microsoft-365/solutions/end-life-cycle-groups-teams-sites-yammer)」を参照し、[Microsoft Teamsでチームをアーカイブまたは削除](./archive-or-delete-a-team.md)します。

## <a name="related-topics"></a>関連項目

[Microsoft Teamsの基礎 (ビデオ)](https://aka.ms/teams-foundations)

[削除されたグループを復元する](/microsoft-365/admin/create-groups/restore-deleted-group)
