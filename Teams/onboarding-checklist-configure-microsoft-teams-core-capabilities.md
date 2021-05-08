---
title: オンボード チェックリスト - コア機能の構成 - Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: 組織のタスクを構成する場合は、このチェックリストの中心となる to do タスクTeamsに従ってください。
ms.custom: seo-marvel-apr2020
localization_priority: Normal
f1.keywords:
- NOCSH
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7c28f33cb8d3c3823f74deb8f6540a39482f68b9
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098033"
---
# <a name="configure-microsoft-teams-core-capabilities"></a>コア機能Microsoft Teams構成する

| いいえ | アクティビティまたはタスク | 説明 | 完了状態 | その他の情報 |
|----|-----------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | 環境にすべての前提条件が含Teamsする | Teams、他のプラットフォームに依存して、エンドツーエンドのコラボレーション ソリューションを構築します。 IT チームと一緒に、ユーザーがデプロイされ、正しく構成されていることを確認し、Exchange、SharePoint、OneDrive for Business。 | | [Microsoft Teams との SharePoint Online と OneDrive for Business の連携](sharepoint-onedrive-interact.md) <br/><br/>[Exchange と Microsoft Teams の連携](exchange-teams-interact.md) |
| 2  | テナントのTeamsが有効になっているか検証する | Teams組織で既定で有効になっています。 Microsoft 365 管理 **センターの [&** アドイン] ページで、Teams が組織に対して有効になっているか確認し、必要に応じて有効にします。 | | [Microsoft Teams Microsoft 365 または Office 365 でOffice 365](office-365-set-up.md) |
| 3  | ロールとアクセス許可を構成する | Teams、メンバーと所有者の 2 種類のロールをサポートしています。 <br/><br/>メンバーをチームに追加した後、所有者はメンバーを所有者ロールに昇格できます。 ベスト プラクティスとして、各チームに少なくとも 2 人の所有者を割り当てすることをお勧めします。 <br/><br/>既定では、組織内でホストされているメールボックスを持つすべてのユーザー Exchange Onlineチームを作成できます。 新しいチームを作成したユーザーには、そのチームの所有者ロールが自動的に付与されます。 <br/><br/>必要に応じて、特定のユーザーだけが新しいチームMicrosoft 365グループ設定を構成できます。 | | [Microsoft Teams で役割と権限を割り当てる](assign-roles-permissions.md) <br/><br/>[Microsoft 365グループとMicrosoft Teams](office-365-groups.md) <br/><br/>[グループを作成できるユーザー Microsoft 365管理する](https://support.office.com/article/Manage-who-can-create-Office-365-Groups-4c46c8cb-17d0-44b5-9776-005fced8e618) |
| 4  | テナント全体の設定をTeamsする | テナント レベルでTeams設定を構成できます。 この設定を有効にしたユーザー Teamsテナント構成から次の設定を継承します。<ul><li>全般</li><li>電子メールの統合</li><li>アプリ</li><li>カスタム クラウド ストレージ</li><li>通話と会議</li><li>メッセージング</li></ul>| | [組織のMicrosoft Teams の設定を管理する](enable-features-office-365.md) |
| 5  | 省略可能: ゲスト アクセスを構成する | ゲスト アクセスは、Teamsチームやチャネルへのアクセスを許可することで、組織外のユーザーと共同作業するために使用します。 ゲスト アクセスは、テナント レベルの設定で、Teams。 規定ではオフになっています。 <br/>組織でこの機能を使用する予定がある場合は、ゲスト アクセスを有効にし、テナント全体のゲスト設定を構成します。 | | [Microsoft Teams でのゲスト アクセス](guest-access.md) |
| 6  | 省略可能: 名前付けポリシー Teams構成する | Teamsは、ユーザーがチーム名を作成または編集するときにMicrosoft 365グループの名前付けポリシーを活用します。 <br/><br/>既定では、ユーザーがチームを作成するときに名前付け制限は適用されません。 <br/><br/>チーム名にルールを適用する必要がある場合は、組織にMicrosoft 365グループの名前付けポリシーを構成します。 必須のプレフィックスとサフィックスを設定し、ブロックする単語を指定できます。 | | [チームを作成Microsoft 365グループの計画を立Microsoft Teams](plan-office-365-groups.md) <br/><br/>[Microsoft 365グループの名前付けポリシー](https://support.office.com/article/Office-365-Groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552) |
| 7  | SMTP ExchangeドメインのTeams構成する | TeamsはExchange Onlineを使用して、SMTP ドメイン (email.teams.microsoft.com) を使用してチーム メンバーに通知を送信します (追加または削除された場合)。 <br/><br/>必ず、この SMTP ドメインを、ご利用のドメイン インフラストラクチャの受け入れドメインの一覧Exchangeしてください。 | | [差出人セーフ リストを作成Exchange](/microsoft-365/security/office-365-security/create-safe-sender-lists-in-office-365?view=o365-worldwide) |
| 8  | アプリケーションへのユーザー アクセスを構成および管理Teams | Teams のすべてのユーザーを有効にすることを強くお勧めしますが、Teams 製品ライセンスを割り当てるか削除することで、ユーザーごとに Teams へのアクセスを許可または禁止することができます。 | | [Microsoft Teams へのユーザー アクセスを管理する](user-access.md) |
| 9  | ユーザーにライセンスを割り当てる | 電話会議、電話会議、通話プラン電話システムユーザーにライセンスを割り当てる | | [追加Microsoft Teamsライセンスを割り当てる](teams-add-on-licensing/assign-teams-add-on-licenses.md)|
| 10 | 省略可能: PowerShell を使用して管理Teams | 管理センターではなく PowerShell コマンドレットを使用してMicrosoft 365設定を管理および管理Teamsできます。 | | [Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps) |