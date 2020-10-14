---
title: Microsoft 365 グループおよび Microsoft Teams
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
description: Microsoft 365 グループとグループメンバーシップが Microsoft Teams とどのように連携するかについて説明します。
ms.openlocfilehash: a4227432ab3557ca5e74ee5a769641185c1e432c
ms.sourcegitcommit: f18941b6dc17b6ea411e10970602aee271242d43
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/14/2020
ms.locfileid: "48456081"
---
# <a name="microsoft-365-groups-and-microsoft-teams"></a>Microsoft 365 グループおよび Microsoft Teams

Microsoft 365 グループは、Microsoft 365 のクロスアプリケーションメンバーシップサービスです。 基本的なレベルでは、Microsoft 365 グループは Azure Active Directory 内のオブジェクトであり、メンバーの一覧と、SharePoint チームサイト、共有 Exchange メールボックス、Planner、Power BI workspace などの関連ワークロードへの結合です。 Active Directory の他のグループベースのセキュリティオブジェクトと同様に、グループにユーザーを追加または削除することができます。

![Microsoft 365 グループと関連サービスを示す図](https://docs.microsoft.com/microsoft-365/media/microsoft-365-groups-hub-spoke.png?view=o365-worldwide)

既定では、Microsoft 365 のユーザーはグループの作成と管理を行うことができます。 Microsoft 365 グループの詳細については、「 [microsoft 365 グループ](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2) および microsoft [365 の IT アーキテクト向けグループ](teams-architecture-solutions-posters.md#groups-in-microsoft-365) 」を参照してください。

## <a name="how-microsoft-365-groups-work-with-teams"></a>Microsoft 365 グループが Teams と連携する方法

チームを作成するときに、チームのメンバーシップを管理するために Microsoft 365 グループが作成されます。 SharePoint サイト、Power BI workspace などのグループ関連サービスは、同時に作成されます。

チームを作成するユーザーは、そのグループの所有者である場合は、既存の Microsoft 365 グループを使用することを選ぶことができます。 チーム内の各チャネルには、ドキュメントライブラリ内の個別のフォルダーがあります。 ドキュメントライブラリで直接フォルダーを作成しても、チーム内にチャネルは作成されません。

Outlook または SharePoint で Microsoft 365 グループを作成すると、Outlook にグループメールボックスが表示されます。 Teams でチームを作成する場合、グループのメールボックスは既定で非表示になっています。 **HiddenFromExchangeClientsEnabled**パラメーターを指定して[get-unifiedgroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-unifiedgroup)コマンドレットを使用して、メールボックスを表示することができます。

## <a name="group-membership"></a>グループ メンバーシップ

チームのメンバーを削除すると、Microsoft 365 グループからも削除されます。 グループから削除すると、チームクライアントからチームとチャネルが直ちに削除されます。 Microsoft 365 管理センターを使用してグループからユーザーを削除すると、SharePoint Online ドキュメントライブラリ、Yammer グループ、共有 OneNote などの他の共同作業の側面にはアクセスできなくなります。 ただし、チームのチャット機能へのアクセス権は、約2時間で引き続き利用できます。

チームメンバーを管理するためのベストプラクティスとして、チームクライアントに対してそれらを追加および削除して、他のグループに接続されたワークロードのアクセス許可の更新がすばやく行われるようにします。 Teams クライアントの外部でチームメンバーを追加または削除する場合 (Microsoft 365 管理センター、Azure AD、または Exchange Online PowerShell を使用して)、変更が Teams に反映されるまでに最大24時間かかることがあります。

## <a name="deleting-groups-and-teams"></a>グループとチームを削除する

Microsoft 365 グループを削除すると、永続的な Outlook/OWA の会話と Teams の会議出席依頼のメールボックスのエイリアスが削除され、SharePoint サイトの削除のマークが付けられます。 チームの削除と Outlook への影響の間は、約20分かかります。 チームクライアントからチームを削除すると、チームのメンバーになっているすべてのユーザーに直ちにチームが削除されます。 チーム機能が有効になっている Microsoft 365 グループのメンバーを削除した場合は、削除された対象ユーザーのチームクライアントでチームがビューから削除されるまでに約2時間かかることがあります。

グループとチームのライフサイクルの終了オプションの詳細については、「  [グループ、チーム、Yammer のライフサイクルの終了オプション](https://docs.microsoft.com/microsoft-365/solutions/end-life-cycle-groups-teams-sites-yammer) 」と「 [Microsoft teams でチームをアーカイブまたは削除](https://docs.microsoft.com/microsoftteams/archive-or-delete-a-team)する」を参照してください。

## <a name="related-topics"></a>関連項目

[Microsoft Teams の基礎 (ビデオ)](https://aka.ms/teams-foundations)

[削除したグループを復元する](https://docs.microsoft.com/microsoft-365/admin/create-groups/restore-deleted-group)