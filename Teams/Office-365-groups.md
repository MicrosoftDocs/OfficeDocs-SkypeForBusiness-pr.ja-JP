---
title: Microsoft 365グループとMicrosoft Teams
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
description: グループとグループ メンバーシップMicrosoft 365の機能についてMicrosoft Teams。
ms.openlocfilehash: 4e140d50bb16c9ed99f126662545fb026c3df60a
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2021
ms.locfileid: "58729736"
---
# <a name="microsoft-365-groups-and-microsoft-teams"></a>Microsoft 365グループとMicrosoft Teams

Microsoft 365グループは、アプリケーション間メンバーシップ サービスです。Microsoft 365。 基本的なレベルでは、Microsoft 365 グループは Azure Active Directory 内のオブジェクトであり、メンバーの一覧と、SharePoint チーム サイト、共有 Exchange メールボックス、Planner、Power BI ワークスペースなどの関連ワークロードとの結合を含むオブジェクトです。 Active Directory の他のグループ ベースのセキュリティ オブジェクトと同様に、グループにユーザーを追加または削除できます。

![グループとMicrosoft 365サービスを示す図。](/microsoft-365/media/microsoft-365-groups-hub-spoke.png?view=o365-worldwide)

既定では、ユーザーはグループMicrosoft 365グループを作成および管理できます。 グループグループの詳細Microsoft 365、「it Architects[](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2)のMicrosoft 365グループと Microsoft 365について[」を参照](teams-architecture-solutions-posters.md#groups-in-microsoft-365)してください。

## <a name="how-microsoft-365-groups-work-with-teams"></a>グループMicrosoft 365を使用するTeams

チームを作成すると、チーム メンバーシップMicrosoft 365グループが作成されます。 グループの関連サービス (SharePoint、Power BIなど) が同時に作成されます。

チームを作成するユーザーは、そのグループの所有者Microsoft 365既存のチーム グループを使用できます。 チーム内の各チャネルには、ドキュメント ライブラリ内に個別のフォルダーがあります。 ドキュメント ライブラリにフォルダーを直接作成しても、チーム内にチャネルは作成されません。

グループまたはグループMicrosoft 365グループOutlook作成SharePointグループ メールボックスは、グループメールボックスにOutlook。 グループメールボックスでチームをTeams既定では、グループ メールボックスは非表示になります。 [Set-UnifiedGroup コマンドレット](/powershell/module/exchange/users-and-groups/set-unifiedgroup)と **HiddenFromExchangeClientsEnabled** パラメーターを使用して、メールボックスを表示できます。

## <a name="group-membership"></a>グループ メンバーシップ

チームのメンバーを削除すると、チームのメンバー Microsoft 365削除されます。 グループから削除すると、チームとチャネルがクライアントからすぐにTeamsされます。 Microsoft 365 管理センター を使用してグループからユーザーを削除すると、SharePoint Online ドキュメント ライブラリ、Yammer グループ、共有 OneNote などの他の共同作業面にアクセスできなくなりました。 ただし、チームのチャット機能には約 2 時間アクセスできます。

チーム メンバーを管理するためのベスト プラクティスとして、Teams クライアントにチーム メンバーを追加して削除し、他のグループに接続されたワークロードのアクセス許可の更新が迅速に実行されていることを確認します。 (Microsoft 365 管理センター、Azure AD、または Exchange Online PowerShell を使用して) Teams クライアントの外部でチーム メンバーを追加または削除した場合、変更が Teams に反映されるのに最大 24 時間かかる場合があります。

## <a name="deleting-groups-and-teams"></a>グループとチームの削除

Microsoft 365 グループを削除すると、永続的な Outlook/OWA の会話と Teams 会議の招待のメールボックス エイリアスが削除され、SharePoint サイトが削除用にマークされます。 チームの削除とチームへの影響の間に約 20 分Outlook。 クライアントからチームを削除Teams、チームのメンバーであるすべてのユーザーがすぐに削除されます。 Teams 機能が有効になっている Microsoft 365 グループのメンバーを削除した場合、チームが削除された影響を受けたユーザーについて、Teams クライアントの表示からチームが削除されるのに約 2 時間の遅延が発生する可能性があります。

グループとチームのライフサイクル終了オプションの詳細については、「グループ[](/microsoft-365/solutions/end-life-cycle-groups-teams-sites-yammer)、チーム、および Yammer のライフサイクルの終了オプション」および「Microsoft Teams でチームをアーカイブまたは削除する[」を参照してください](./archive-or-delete-a-team.md)。

## <a name="related-topics"></a>関連項目

[Microsoft Teamsの基礎 (ビデオ)](https://aka.ms/teams-foundations)

[削除されたグループを復元する](/microsoft-365/admin/create-groups/restore-deleted-group)