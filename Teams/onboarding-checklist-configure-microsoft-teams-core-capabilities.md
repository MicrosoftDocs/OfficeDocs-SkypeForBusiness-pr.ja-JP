---
title: オンボード チェックリスト - コア機能を構成する - Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: 組織の Teams を構成するときは、このチェックリストのコアタスク、To Do タスク、アクティビティに従ってください。
ms.custom: seo-marvel-apr2020
ms.localizationpriority: medium
f1.keywords:
- NOCSH
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 200edfcbe8c93c2f629f176a17959e60f70cb902
ms.sourcegitcommit: 472e46b6eb907f41920516616683a61f0fc6f741
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/30/2022
ms.locfileid: "66564245"
---
# <a name="configure-microsoft-teams-core-capabilities"></a>Microsoft Teams のコア機能を構成する

| いいえ | アクティビティまたはタスク | 説明 | 完了状態 | その他の情報 |
|----|-----------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | 環境に Teams のすべての前提条件が含まれていることを検証する | Teams は、エンド ツー エンドのコラボレーション ソリューションを構築するために、他のプラットフォームに依存しています。 IT チームと協力して、Exchange、SharePoint Online、およびOneDrive for Businessを展開して適切に構成していることを確認します。 | | [Microsoft Teams との SharePoint Online と OneDrive for Business の連携](sharepoint-onedrive-interact.md) <br/><br/>[Exchange と Microsoft Teams の連携](exchange-teams-interact.md) |
| 2  | テナントに対して Teams が有効になっていることを確認する | Teams は、すべての組織に対して既定で有効になっています。 Microsoft 365 管理センターの [**サービス & アドイン**] ページを確認して、Teams が組織で有効になっていることを確認し、必要に応じて有効にします。 | | [Microsoft 365 または Office 365 で Microsoft Teams を設定する](office-365-set-up.md) |
| 3  | ロールとアクセス許可を構成する | Teams では、メンバーと所有者の 2 種類のロールがサポートされています。 <br/><br/>チームにメンバーを追加した後、所有者はメンバーを所有者ロールに昇格することもできます。 ベスト プラクティスとして、各チームに少なくとも 2 人の所有者が割り当てられていることをお勧めします。 <br/><br/>既定では、Exchange Onlineでホストされているメールボックスを持つ組織内のすべてのユーザーがチームを作成できます。 新しいチームを作成したユーザーには、そのチームの所有者ロールが自動的に付与されます。 <br/><br/>必要に応じて、特定のユーザーのみが新しいチームを作成できるように、Microsoft 365 グループ設定を構成できます。 | | [Microsoft Teams で役割と権限を割り当てる](assign-roles-permissions.md) <br/><br/>[Microsoft 365 グループと Microsoft Teams](office-365-groups.md) <br/><br/>[Microsoft 365 グループを作成できるユーザーを管理する](https://support.office.com/article/Manage-who-can-create-Office-365-Groups-4c46c8cb-17d0-44b5-9776-005fced8e618) |
| 4  | テナント全体の Teams 設定を構成する | テナント レベルで Teams の一部の設定を構成できます。 Teams が有効になっているユーザーは、テナント構成からこれらの設定を継承します。<ul><li>General</li><li>電子メールの統合</li><li>アプリ</li><li>カスタム クラウド ストレージ</li><li>通話と会議</li><li>Messaging</li></ul>| | [組織のMicrosoft Teams の設定を管理する](enable-features-office-365.md) |
| 5  | 省略可能: ゲスト アクセスを構成する | Teams のゲスト アクセスを使用して、チームとチャネルへのアクセスを許可することで、組織外のユーザーと共同作業を行います。 ゲスト アクセスは、Teams のテナント レベルの設定です。 規定ではオフになっています。 <br/>組織がその機能を使用する予定の場合は、ゲスト アクセスを有効にし、テナント全体のゲスト設定を構成します。 | | [Microsoft Teams でのゲスト アクセス](guest-access.md) |
| 6  | 省略可能: Teams の名前付けポリシーを構成する | チームは、ユーザーがチーム名を作成または編集するときに、Microsoft 365 グループの名前付けポリシーを利用します。 <br/><br/>既定では、ユーザーがチームを作成するときに名前付けの制限は適用されません。 <br/><br/>チーム名にルールを適用する必要がある場合は、組織に適用Microsoft 365 グループ名前付けポリシーを構成します。 必須のプレフィックスとサフィックスを設定し、ブロックされた単語を指定できます。 | | [Microsoft Teams でチームを作成するときに Microsoft 365 グループを計画する](plan-office-365-groups.md) <br/><br/>[Microsoft 365 グループ名前付けポリシー](https://support.office.com/article/Office-365-Groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552) |
| 7  | Teams SMTP ドメインの Exchange を構成する | Teams はExchange Onlineを使用して、SMTP ドメイン (email.teams.microsoft.com) を使用してチーム メンバーに通知を送信します。追加または削除されました。 <br/><br/>この SMTP ドメインは、Exchange インフラストラクチャの承認済みドメインの一覧に必ず追加してください。 | | [Exchange で差出人セーフ リストを作成する](/microsoft-365/security/office-365-security/create-safe-sender-lists-in-office-365?view=o365-worldwide) |
| 8  | Teams へのユーザー アクセスを構成および管理する | Teams のすべてのユーザーを有効にすることを非常に推奨しますが、Teams 製品ライセンスを割り当てるか削除することで、ユーザーごとに Teams へのアクセスを許可または禁止できます。 | | [Microsoft Teams へのユーザー アクセスを管理する](user-access.md) |
| 9  | ユーザーにライセンスを割り当てる | 電話会議、電話システム、通話プランなどの機能のライセンスをユーザーに割り当てる | | [Microsoft Teams アドオン ライセンスの割り当て](teams-add-on-licensing/assign-teams-add-on-licenses.md)|
| 10 | 省略可能: PowerShell を使用して Teams を管理する | Microsoft 365 管理センターではなく PowerShell コマンドレットを使用して、Teams の設定を管理および管理できます。 | | [Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps) |