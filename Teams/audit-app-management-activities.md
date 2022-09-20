---
title: アプリ管理イベントの監査ログを検索する
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
ms.subservice: teams-apps
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
f1keywords: ''
description: 組織内のユーザーと管理者の Teams アプリ アクティビティを監査する方法について説明します。
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.openlocfilehash: f1b7a8ca14a087ecaf7e7a8898f9bdb85e87e3c5
ms.sourcegitcommit: ceba5fd8f098c8d0eafaffe5c5301c845a3ae7ab
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2022
ms.locfileid: "67837727"
---
# <a name="audit-for-app-management-activities-and-events"></a>アプリ管理アクティビティとイベントの監査

Microsoft 365 のMicrosoft Purview 監査 (Standard) を使用すると、エンド ユーザーと管理者によってさまざまな Microsoft 365 サービスで実行されたアクティビティの監査レコードを検索できます。

監査を検索する前に、次の前提条件を満たしていることを確認します。

* [組織のサブスクリプションとユーザー ライセンスを取得する](/microsoft-365/compliance/set-up-basic-audit)。
* [Microsoft Purview コンプライアンス ポータルで監査を有効にする](/microsoft-365/compliance/turn-audit-log-search-on-or-off)。
* [監査ログを検索するためのアクセス許可を割り当てる](/microsoft-365/compliance/set-up-basic-audit)。

## <a name="search-the-audit-logs-for-app-events-in-teams"></a>Teams でアプリ イベントの監査ログを検索する

Teams のアプリ イベントの監査ログは、特定のアクションを調査するのに役立ちます。 ログを検索してさまざまなアクションを検索できますが、ログに記録される Teams アプリ アクションの一部を次の表に示します。 さらに、コネクタ、ボット、タブに関連するアクティビティを検索することもできます。

| Teams アプリ アクション                  | アクティビティ名                | 説明                                              |
|-----------------------------------|------------------------------|:---------------------------------------------------------|
| **インストールされたアプリ**                 | `AppInstalled`               | アプリがインストールされました。                                     |
| **アップグレードされたアプリ**                  | `AppUpgraded`                | アプリがカタログで最新版にアップグレードされました。 |
| **削除されたアプリ**               | `AppUninstalled`             | アプリがアンインストールされました。                                   |
| **公開済みのアプリ**                 | `AppPublishedToCatalog`      | アプリがカタログに追加されました。                          |
| **更新されたアプリ**                   | `AppUpdatedInCatalog`        | アプリがカタログで更新されました。                        |
| **削除されたアプリ**                   | `AppDeletedFromCatalog`      | カタログからアプリが削除されました。                      |
| **すべての組織のアプリが削除されました** | `DeletedAllOrganizationApps` | カタログからすべての組織アプリを削除しました。          |

監査対象となる Teams アクティビティの完全な一覧については、「[Teams アクティビティ](audit-log-events.md#teams-activities)」および「[Teams アクティビティでのシフト](audit-log-events.md#shifts-in-teams-activities)」を参照してください。

> [!NOTE]
> プライベート チャネルからの監査イベントも、チームや標準チャネルの場合と同様に記録されます。

コンプライアンス ポータルで監査ログ検索ツールを使用して監査記録を検索します。 アプリ イベント監査ログを検索するには、次の手順に従います。

1. Microsoft Purview コンプライアンス ポータルにサインインし、**[ソリューション]** > **[[監査]](https://compliance.microsoft.com/auditlogsearch)** の順に移動します。
1. 監査ページで、要件に従って次のフィールドを更新します。

   * **日付と時刻の範囲**: 開始日と終了日を選択します。
   * **アクティビティ**: Microsoft Teams アクティビティを入力します。 一覧から、1 つ以上のアプリ アクティビティを選択します。 Teams アクティビティをすばやく見つけるには、[**アクティビティ**] 検索フィールドで単語 `Teams activities` を検索できます。
   * **ファイル、フォルダー、またはサイト**: ファイル名、URL、またはその一部を入力します。
   * **ユーザー**: 検索する監査ログを持つユーザーを追加します。

1. **[検索]** を選択します。

   :::image type="content" source="media/compliance-search-teams-activities-trimmed.png" alt-text="Microsoft Purview コンプライアンス ポータルで Teams アクティビティを検索し、Teams イベントを監査します。" lightbox="media/compliance-search-teams-activities.png":::

コンプライアンス ポータルで監査サインインを検索した後、監査レコードを CSV ファイルとしてエクスポートできます。 詳細については、「[監査ログのエクスポート、構成、および表示](/microsoft-365/compliance/export-view-audit-log-records)」を参照してください。

> [!NOTE]
> 上記のアクティビティのいずれかがユーザーまたは管理者によって実行されると、Teams は監査レコードを生成して格納します。 監査 (標準) では、記録は 90 日間保持されるため、過去 3 か月以内に発生したアクティビティを検索することができます。

> [!TIP]
> 管理者として、ユーザーがボットをブロックまたはミュートしたかどうかを知るためにユーザーごとのレポートを作成する場合は、「ボットを [ブロック、ミュート、またはアンインストールしたユーザーを把握](/microsoftteams/platform/bots/how-to/conversations/send-proactive-messages?#understand-who-blocked-muted-or-uninstalled-a-bot)する」を参照してください。

## <a name="related-articles"></a>関連記事

* [監査ログを使用して Microsoft Power Platform のインストール アクティビティを調査する](manage-power-platform-apps.md#use-audit-logs-to-investigate-microsoft-power-platform-installation-activity)
* [コンプライアンス ポータルで監査サインインを検索します](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)。
* [Microsoft Purview 監査 Premium の概要](/microsoft-365/compliance/advanced-audit)。
* [監査をオンまたはオフにします](/microsoft-365/compliance/turn-audit-log-search-on-or-off)。
