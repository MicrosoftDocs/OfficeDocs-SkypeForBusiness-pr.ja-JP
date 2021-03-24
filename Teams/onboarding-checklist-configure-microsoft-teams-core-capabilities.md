---
title: オンボーディング チェックリスト - コア機能を構成する - Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: 組織用に Teams を構成する場合は、このチェックリストの主要な To Do タスクとアクティビティに従います。
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
# <a name="configure-microsoft-teams-core-capabilities"></a>Microsoft Teams のコア機能を構成する

| いいえ | アクティビティまたはタスク | 説明 | 完了状態 | その他の情報 |
|----|-----------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | 使用している環境に Teams のすべての前提条件が含まれるか検証する | Teams は、他のプラットフォームに依存して、エンドツーエンドのコラボレーション ソリューションを構築します。 IT チームと作業して、Exchange、SharePoint Online、OneDrive for Business を展開し、適切に構成されていることを確認します。 | | [Microsoft Teams との SharePoint Online と OneDrive for Business の連携](sharepoint-onedrive-interact.md) <br/><br/>[Exchange と Microsoft Teams の連携](exchange-teams-interact.md) |
| 2  | Teams がテナントに対して有効になっているか検証する | Teams は、すべての組織で既定で有効になっています。 Microsoft 365 管理 **&** の [サービスとアドイン] ページで、Teams が組織で有効になっているか確認し、必要に応じて有効にします。 | | [Microsoft 365 または Office 365 で Microsoft Teams をセットアップする](office-365-set-up.md) |
| 3  | 役割とアクセス許可を構成する | Teams では、メンバーと所有者の 2 種類の役割がサポートされます。 <br/><br/>メンバーをチームに追加した後、所有者はメンバーを所有者ロールに昇格できます。 ベスト プラクティスとして、各チームに少なくとも 2 人の所有者を割り当てすることをお勧めします。 <br/><br/>既定では、Exchange Online でホストされているメールボックスを持つ組織内のすべてのユーザーがチームを作成できます。 新しいチームを作成したユーザーには、そのチームの所有者ロールが自動的に付与されます。 <br/><br/>必要に応じて、特定のユーザーだけが新しいチームを作成できるよう Microsoft 365 グループ設定を構成できます。 | | [Microsoft Teams で役割と権限を割り当てる](assign-roles-permissions.md) <br/><br/>[Microsoft 365 グループと Microsoft Teams](office-365-groups.md) <br/><br/>[Microsoft 365 グループを作成できるユーザーを管理する](https://support.office.com/article/Manage-who-can-create-Office-365-Groups-4c46c8cb-17d0-44b5-9776-005fced8e618) |
| 4  | テナント全体の Teams の設定を構成する | テナント レベルで Teams の一部の設定を構成できます。 Teams に対して有効になっているユーザーは、テナント構成からこれらの設定を継承します。<ul><li>全般</li><li>電子メールの統合</li><li>アプリ</li><li>カスタム クラウド ストレージ</li><li>通話と会議</li><li>Messaging</li></ul>| | [組織のMicrosoft Teams の設定を管理する](enable-features-office-365.md) |
| 5  | オプション: ゲスト アクセスを構成する | Teams のゲスト アクセスを使用して、チームやチャネルへのアクセス権を付与することで、組織外のユーザーと共同作業を行います。 ゲスト アクセスは、Teams のテナント レベルの設定です。 規定ではオフになっています。 <br/>組織でこの機能を使用する予定がある場合は、ゲスト アクセスを有効にし、テナント全体のゲスト設定を構成します。 | | [Microsoft Teams でのゲスト アクセス](guest-access.md) |
| 6  | オプション: Teams の名前付けポリシーを構成する | Teams では、ユーザーがチーム名を作成または編集するときに、Microsoft 365 グループの名前付けポリシーを利用します。 <br/><br/>既定では、ユーザーがチームを作成するときに名前付け制限は適用されません。 <br/><br/>チーム名にルールを適用する必要がある場合は、組織に適用される Microsoft 365 グループの名前付けポリシーを構成します。 必須のプレフィックスとサフィックスを設定し、ブロックする単語を指定できます。 | | [Microsoft Teams でチームを作成するときに Microsoft 365 グループを計画する](plan-office-365-groups.md) <br/><br/>[Microsoft 365 グループの名前付けポリシー](https://support.office.com/article/Office-365-Groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552) |
| 7  | Teams SMTP ドメイン用に Exchange を構成する | Teams では、追加または削除された場合に、Exchange Online を使用して SMTP email.teams.microsoft.com を使用してチーム メンバーに通知を送信します。 <br/><br/>この SMTP ドメインは、Exchange インフラストラクチャの承認されたドメインの一覧に必ず追加してください。 | | [Exchange で差出人セーフ リストを作成する](/microsoft-365/security/office-365-security/create-safe-sender-lists-in-office-365?view=o365-worldwide) |
| 8  | Teams へのユーザー アクセスを構成および管理する | Teams のすべてのユーザーを有効にすることを強くお勧めしますが、Teams 製品ライセンスを割り当てるか削除することで、ユーザー単位で Teams へのアクセスを許可または禁止することができます。 | | [Microsoft Teams へのユーザー アクセスを管理する](user-access.md) |
| 9  | ユーザーにライセンスを割り当てる | 電話会議、電話システム、通話プランのような機能のライセンスをユーザーに割り当てる | | [Microsoft Teams アドオン ライセンスを割り当てる](teams-add-on-licensing/assign-teams-add-on-licenses.md)|
| 10 | オプション: PowerShell を使用して Teams を管理する | Microsoft 365 管理センターではなく PowerShell コマンドレットを使用して、Teams の設定を管理および管理できます。 | | [Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps) |