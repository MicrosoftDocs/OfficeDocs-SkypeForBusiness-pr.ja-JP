---
title: Microsoft 365 グループと Microsoft Teams
ms.reviewer: kblevins
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
description: Microsoft 365 グループとグループ メンバーシップが Microsoft Teams でどのように機能するのかについて説明します。
ms.openlocfilehash: d258fa4252f6bbb02d2b9a8211dd5919c2d7a67b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51105243"
---
# <a name="microsoft-365-groups-and-microsoft-teams"></a>Microsoft 365 グループと Microsoft Teams

Microsoft 365 グループは、Microsoft 365 のクロスアプリケーション メンバーシップ サービスです。 基本的なレベルでは、Microsoft 365 グループは Azure Active Directory 内のオブジェクトであり、メンバーの一覧と、SharePoint チーム サイト、共有 Exchange メールボックス、Planner、Power BI ワークスペースなどの関連するワークロードに対応しています。 Active Directory の他のグループ ベースのセキュリティ オブジェクトと同様に、グループにユーザーを追加または削除できます。

![Microsoft 365 グループと関連サービスを示す図](/microsoft-365/media/microsoft-365-groups-hub-spoke.png?view=o365-worldwide)

既定では、Microsoft 365 のユーザーはグループを作成および管理できます。 Microsoft 365 グループの詳細については [、「Microsoft 365](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2) グループと [Microsoft 365 for IT Architects](teams-architecture-solutions-posters.md#groups-in-microsoft-365) ポスターのグループ」を参照してください。

## <a name="how-microsoft-365-groups-work-with-teams"></a>Microsoft 365 グループと Teams の動作

チームを作成すると、チーム メンバーシップを管理するために Microsoft 365 グループが作成されます。 SharePoint サイト、Power BI ワークスペースなど、グループに関連するサービスが同時に作成されます。

チームを作成するユーザーは、そのグループの所有者である場合、既存の Microsoft 365 グループを使用することができます。 チーム内の各チャネルには、ドキュメント ライブラリに個別のフォルダーがあります。 ドキュメント ライブラリにフォルダーを直接作成しても、チームにチャネルは作成されません。

Outlook または SharePoint で Microsoft 365 グループを作成すると、グループ メールボックスが Outlook に表示されます。 Teams でチームを作成する場合、既定ではグループ メールボックスは非表示になっています。 [Set-UnifiedGroup](/powershell/module/exchange/users-and-groups/set-unifiedgroup)コマンドレットと **HiddenFromExchangeClientsEnabled** パラメーターを使用して、メールボックスを表示することができます。

## <a name="group-membership"></a>グループ メンバーシップ

チームのメンバーを削除すると、そのメンバーも Microsoft 365 グループから削除されます。 グループから削除すると、Teams クライアントからチームとチャネルが直ちに削除されます。 Microsoft 365 管理センターを使用してグループからユーザーを削除すると、そのユーザーは SharePoint Online ドキュメント ライブラリ、Yammer グループ、共有 OneNote などの他の共同作業面にアクセスできなくなりました。 ただし、チームのチャット機能には約 2 時間引き続きアクセスできます。

チーム メンバーを管理するためのベスト プラクティスとして、Teams クライアントにチーム メンバーを追加して削除し、他のグループに接続されたワークロードのアクセス許可の更新が迅速に行われるのを確認します。 Teams クライアントの外部で (Microsoft 365 管理センター、Azure AD、または Exchange Online PowerShell を使用して) チーム メンバーを追加または削除した場合、変更が Teams に反映されるのに最大 24 時間かかる場合があります。

## <a name="deleting-groups-and-teams"></a>グループとチームの削除

Microsoft 365 グループを削除すると、永続的な Outlook/OWA 会話と Teams 会議の招待のメールボックス エイリアスが削除され、SharePoint サイトに削除のマークが付けされます。 チームの削除から Outlook への影響まで、約 20 分かかります。 Teams クライアントからチームを削除すると、そのチームはビューからチームのメンバー全員に直ちに削除されます。 Teams 機能が有効になっている Microsoft 365 グループのメンバーを削除した場合、チームが削除された影響を受けたユーザーの Teams クライアントのビューからチームが削除されるのに約 2 時間遅れる可能性があります。

グループとチームのライフサイクルの終了オプションの詳細については[、「Microsoft Teams](./archive-or-delete-a-team.md)でグループ、[チーム](/microsoft-365/solutions/end-life-cycle-groups-teams-sites-yammer)、Yammer およびチームをアーカイブまたは削除するためのライフサイクルの終了オプション」を参照してください。

## <a name="related-topics"></a>関連項目

[Microsoft Teams の基礎 (ビデオ)](https://aka.ms/teams-foundations)

[削除したグループを復元する](/microsoft-365/admin/create-groups/restore-deleted-group)