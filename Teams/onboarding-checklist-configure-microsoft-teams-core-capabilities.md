---
title: オンボード チェックリスト - コア機能の構成 - Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: 組織のTeamsを構成するときは、このチェックリストのコアタスク、To Do タスク、アクティビティに従ってください。
ms.custom: seo-marvel-apr2020
ms.localizationpriority: medium
f1.keywords:
- NOCSH
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: d1d8368f43dd321ff03a5ecfc31fa376e13bda8c
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "62417370"
---
# <a name="configure-microsoft-teams-core-capabilities"></a>コア機能Microsoft Teams構成する

| いいえ | アクティビティまたはタスク | 説明 | 完了状態 | その他の情報 |
|----|-----------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | 環境にTeams前提条件がすべて含まれていることを検証する | Teamsは、エンド ツー エンドのコラボレーション ソリューションを構築するために他のプラットフォームに依存します。 IT チームと協力して、Exchange、SharePoint Online、OneDrive for Businessを展開し、適切に構成していることを確認します。 | | [Microsoft Teams との SharePoint Online と OneDrive for Business の連携](sharepoint-onedrive-interact.md) <br/><br/>[Exchange と Microsoft Teams の連携](exchange-teams-interact.md) |
| 2  | テナントに対してTeamsが有効になっていることを検証する | Teamsは、すべての組織で既定で有効になっています。 Microsoft 365 管理センターの [**サービス & アドイン**] ページを確認して、組織でTeamsが有効になっていることを確認し、必要に応じて有効にします。 | | [Microsoft 365またはOffice 365でMicrosoft Teamsを設定する](office-365-set-up.md) |
| 3  | ロールとアクセス許可を構成する | Teamsは、メンバーと所有者の 2 種類のロールをサポートします。 <br/><br/>チームにメンバーを追加した後、所有者はメンバーを所有者ロールに昇格することもできます。 ベスト プラクティスとして、各チームに少なくとも 2 人の所有者が割り当てられていることをお勧めします。 <br/><br/>既定では、Exchange Onlineでホストされているメールボックスを持つ組織内のすべてのユーザーがチームを作成できます。 新しいチームを作成したユーザーには、そのチームの所有者ロールが自動的に付与されます。 <br/><br/>必要に応じて、特定のユーザーのみが新しいチームを作成できるように、Microsoft 365グループ設定を構成できます。 | | [Microsoft Teams で役割と権限を割り当てる](assign-roles-permissions.md) <br/><br/>[Microsoft 365 グループとMicrosoft Teams](office-365-groups.md) <br/><br/>[Microsoft 365 グループを作成できるユーザーを管理する](https://support.office.com/article/Manage-who-can-create-Office-365-Groups-4c46c8cb-17d0-44b5-9776-005fced8e618) |
| 4  | テナント全体のTeams設定を構成する | テナント レベルで一部のTeams設定を構成できます。 Teamsに対して有効になっているユーザーは、テナント構成からこれらの設定を継承します。<ul><li>全般</li><li>電子メールの統合</li><li>アプリ</li><li>カスタム クラウド ストレージ</li><li>通話と会議</li><li>Messaging</li></ul>| | [組織のMicrosoft Teams の設定を管理する](enable-features-office-365.md) |
| 5  | 省略可能: ゲスト アクセスを構成する | Teamsでゲスト アクセスを使用して、チームやチャネルへのアクセスを許可することで、組織外のユーザーと共同作業を行います。 ゲスト アクセスは、Teamsのテナント レベルの設定です。 規定ではオフになっています。 <br/>組織がその機能を使用する予定の場合は、ゲスト アクセスを有効にし、テナント全体のゲスト設定を構成します。 | | [Microsoft Teams でのゲスト アクセス](guest-access.md) |
| 6  | 省略可能: 名前付けポリシー Teams構成する | Teamsは、ユーザーがチーム名を作成または編集するときに、Microsoft 365 グループの名前付けポリシーを利用します。 <br/><br/>既定では、ユーザーがチームを作成するときに名前付けの制限は適用されません。 <br/><br/>チーム名にルールを適用する必要がある場合は、組織に適用Microsoft 365 グループ名前付けポリシーを構成します。 必須のプレフィックスとサフィックスを設定し、ブロックされた単語を指定できます。 | | [Microsoft Teamsでチームを作成するときにMicrosoft 365 グループを計画する](plan-office-365-groups.md) <br/><br/>[Microsoft 365 グループ名前付けポリシー](https://support.office.com/article/Office-365-Groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552) |
| 7  | Teams SMTP ドメインのExchangeを構成する | TeamsはExchange Onlineを使用して、SMTP ドメイン (email.teams.microsoft.com) を使用してチーム メンバーに通知を送信します。追加または削除されました。 <br/><br/>この SMTP ドメインは、Exchange インフラストラクチャの承認済みドメインの一覧に必ず追加してください。 | | [Exchangeで差出人セーフ リストを作成する](/microsoft-365/security/office-365-security/create-safe-sender-lists-in-office-365?view=o365-worldwide) |
| 8  | Teamsへのユーザー アクセスを構成および管理する | すべてのユーザーに対してTeamsを有効にすることを非常に推奨しますが、Teams製品ライセンスを割り当てるか削除することで、ユーザーごとにTeamsへのアクセスを許可または禁止できます。 | | [Microsoft Teams へのユーザー アクセスを管理する](user-access.md) |
| 9  | ユーザーにライセンスを割り当てる | 電話会議、電話システム、通話プランなどの機能のライセンスをユーザーに割り当てる | | [アドオン ライセンスMicrosoft Teams割り当てる](teams-add-on-licensing/assign-teams-add-on-licenses.md)|
| 10 | 省略可能: PowerShell を使用してTeamsを管理する | Microsoft 365 管理センターではなく PowerShell コマンドレットを使用して、Teams設定を管理できます。 | | [Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps) |