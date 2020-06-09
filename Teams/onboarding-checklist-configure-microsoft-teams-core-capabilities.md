---
title: オンボードチェックリスト-主要機能を構成する-Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: 組織のチームを構成するときに、このチェックリストでコア、to do、タスク、アクティビティに従います。
ms.custom: seo-marvel-apr2020
localization_priority: Normal
f1.keywords:
- NOCSH
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 42dc9f53a5adab40857180ccf8f54b92dd4cb77f
ms.sourcegitcommit: 3323c86f31c5ab304944a34892601fcc7b448025
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "44637526"
---
# <a name="configure-microsoft-teams-core-capabilities"></a>Microsoft Teams のコア機能を構成する

| X | アクティビティまたはタスク | 説明 | 完了状態 | その他の情報 |
|----|-----------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | 環境にすべての Teams の前提条件が含まれていることを検証する | チームは、他のプラットフォームに依存して、エンドツーエンドのコラボレーションソリューションを構築します。 IT チームと協力して、Exchange、SharePoint Online、および OneDrive for Business を展開し、適切に構成していることを確認します。 | | [Microsoft Teams との SharePoint Online と OneDrive for Business の連携](sharepoint-onedrive-interact.md) <br/><br/>[Exchange と Microsoft Teams の連携](exchange-teams-interact.md) |
| 2  | チームがテナントで有効になっていることを検証する | すべての組織に対して、チームは既定でオンになっています。 Microsoft 365 管理センターで [**サービス & アドイン**] ページを確認して、自分のテナントで Teams が有効になっていることを確認し、必要に応じて有効にします。 | | [Microsoft 365 または Office 365 で Microsoft Teams を設定する](office-365-set-up.md) |
| 3  | 役割と権限を構成する | Teams は、メンバーと所有者の2種類の役割をサポートしています。 <br/><br/>メンバーをチームに追加した後は、所有者が所有者の役割にメンバーを昇格させることもできます。 ベストプラクティスとして、各チームに少なくとも2人の所有者を割り当てることをお勧めします。 <br/><br/>既定では、Exchange Online でホストされているメールボックスを持つ組織内のすべてのユーザーが、チームを作成できます。 新しいチームを作成したユーザーには、そのチームの所有者の役割が自動的に与えられます。 <br/><br/>必要に応じて、特定のユーザーが新しいチームを作成できるように Microsoft 365 グループ設定を構成することができます。 | | [Microsoft Teams で役割と権限を割り当てる](assign-roles-permissions.md) <br/><br/>[Microsoft 365 グループおよび Microsoft Teams](office-365-groups.md) <br/><br/>[Microsoft 365 グループを作成できるユーザーを管理する](https://support.office.com/article/Manage-who-can-create-Office-365-Groups-4c46c8cb-17d0-44b5-9776-005fced8e618) |
| 4  | テナント全体のチーム設定を構成する | 一部の Teams の設定は、テナントレベルで構成できます。 チームに対して有効になっているユーザーは、テナントの構成から次の設定を継承します。<ul><li>一般</li><li>電子メールの統合</li><li>アプリ</li><li>カスタム クラウド ストレージ</li><li>通話と会議</li><li>Messaging</li></ul>| | [組織のMicrosoft Teams の設定を管理する](enable-features-office-365.md) |
| 5  | オプション: ゲストアクセスを構成する | Teams でゲストアクセスを使用して、チームとチャネルへのアクセスを付与することで、組織外のユーザーと共同作業を行うことができます。 ゲストアクセスは、Teams のテナントレベルの設定です。 規定ではオフになっています。 <br/>組織でゲストアクセスを有効にして、その機能を使用する予定がある場合は、テナント全体のゲスト設定を構成します。 | | [Microsoft Teams でのゲスト アクセス](guest-access.md) |
| 6  | オプション: チームの名前付けポリシーを構成する | チームは、ユーザーがチーム名を作成または編集するときに、Microsoft 365 グループの名前付けポリシーを活用します。 <br/><br/>既定では、ユーザーがチームを作成したときに、名前付けの制限は適用されません。 <br/><br/>チーム名にルールを適用する必要がある場合は、組織に適用される Microsoft 365 グループの名前付けポリシーを構成します。 必須のプレフィックスとサフィックスを設定して、ブロックする単語を指定できます。 | | [Microsoft Teams で teams を作成するときに Microsoft 365 グループを計画する](plan-office-365-groups.md) <br/><br/>[Microsoft 365 グループの名前付けポリシー](https://support.office.com/article/Office-365-Groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552) |
| 7  | Teams の SMTP ドメイン用に Exchange を構成する | チームは Exchange Online を使用して、email.teams.microsoft.com (追加または削除された SMTP ドメイン) を使用して、チームメンバーに通知を送信します。 <br/><br/>この SMTP ドメインは、必ず Exchange インフラストラクチャの [承認済みドメイン] リストに追加してください。 | | [Microsoft Teams SMTP ドメインを承認済みドメインとして Exchange Online に追加する](smtp-accepted-domain.md) |
| 個  | チームへのユーザーアクセスを構成および管理する | チームのすべてのユーザーを有効にすることを強くお勧めしますが、Teams 製品ライセンスを割り当てるか削除することで、ユーザーごとにチームへのアクセスを許可または禁止することができます。 | | [Microsoft Teams へのユーザー アクセスを管理する](user-access.md) |
| ファイブ  | ライセンスをユーザーに割り当てる | 電話会議、電話システム、通話プランなどの機能を使用するためのライセンスをユーザーに割り当てます。 | | [Microsoft Teams のアドオンライセンスを割り当てる](teams-add-on-licensing/assign-teams-add-on-licenses.md)|
| 常用 | オプション: PowerShell を使用してチームを管理する | Microsoft 365 管理センターではなく、PowerShell コマンドレットを使用して、チームの設定を管理および管理できます。 | | [Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) |
