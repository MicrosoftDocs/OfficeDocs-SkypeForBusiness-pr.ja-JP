---
title: 組織の Shifts アプリを管理する
author: cichur
ms.author: v-cichur
ms.reviewer: lisawu,gumariam
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
description: 組織内の最前線の従業員向け Teams で Shifts アプリを設定および管理する方法について学習します。
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 218b041d83cde91a23201ab864160ce3b8b7cb6e
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909091"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a>Microsoft Teams で組織のシフト アプリを管理する

> [!IMPORTANT]
> Microsoft StaffHub は 2020 年 6 月 30 日に廃止されました。 StaffHub の機能を Microsoft Teams に構築しています。 現在、Teams にはシフト アプリのスケジュール管理機能が含まれています。今後、他の機能もロールアウトされる予定です。 StaffHub は、2020 年 6 月 30 日にすべてのユーザーの作業を停止しました。 StaffHub を開しようとすると、Teams のダウンロードを指示するメッセージが表示されます。 詳細については [、Microsoft StaffHub の廃止に関するページを参照してください](microsoft-staffhub-to-be-retired.md)。  

## <a name="overview-of-shifts"></a>シフトの概要

Microsoft Teams の Shifts アプリでは、Frontline Worker の接続と同期が維持されます。モバイルを最初に構築して、チームの時間管理とコミュニケーションを迅速かつ効果的に行います。 シフトを使用すると、Frontline Worker とそのマネージャーはモバイル デバイスを使用してスケジュールを管理し、連絡を取り合います。

- マネージャーは、チームのシフト スケジュールを作成、更新、および管理します。 マネージャーは、メッセージを 1 人のユーザーに送ることも ("床が汚れています" など)、チーム全体に送ることもできます ("地区本部長があと 20 分で到着します" など)。 マネージャーは、ポリシー ドキュメント、ニュース速報、およびビデオを送信することもできます。 
- 従業員は今後のシフトの表示、その日に予定されている他のユーザーの確認、シフトの交換または提供の要求、および休みリクエストを行います。 

シフトでは現在、ゲスト ユーザーはサポートされていませんのでご注意ください。 つまり、Teams でゲスト アクセスがオンになっていると、チームのゲストをシフト スケジュールに追加することも、チームのゲストがシフト スケジュールを使用することもできません。 

> [!Note]
> さまざまなプラットフォームでの Shifts 機能の詳細については、プラットフォーム別 [の Teams の機能を参照してください](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)。

## <a name="availability-of-shifts"></a>シフトの可用性

シフトは、Teams が利用可能なすべてのエンタープライズ SKU で利用できます。

## <a name="location-of-shifts-data"></a>シフトのデータの場所

現在、シフトのデータは、北米、西ヨーロッパ、およびアジア太平洋にあるデータ センターの Azure に保存されています。 データが保存される場所の詳細については、「[データの保存場所](http://o365datacentermap.azurewebsites.net/)」を参照してください。

## <a name="set-up-shifts"></a>シフトのセットアップ

### <a name="enable-or-disable-shifts-in-your-organization"></a>組織のシフトを有効または無効にする

シフトは、組織内のすべての Teams ユーザーに対して既定で有効になっています。 Microsoft Teams 管理センターの [アプリの管理] ページ[](../../manage-apps.md)で、組織レベルでアプリをオフまたはオンにできます。

1. Microsoft Teams 管理センターの左側のナビゲーションで、Teams アプリの [アプリの **管理]**  >  **に移動します**。
2. アプリの一覧で、次のいずれかの操作を行います。

    - 組織の Shifts をオフにする場合は、Shifts アプリを検索して選択し、[ブロック] を選択 **します**。
    - 組織の Shifts を有効にする場合は、Shifts アプリを検索して選択し、[許可] を選択 **します**。

### <a name="enable-or-disable-shifts-for-specific-users-in-your-organization"></a>組織内の特定のユーザーに対して Shifts を有効または無効にする

組織内の特定のユーザーに対して Shifts の使用を許可またはブロックするには、[アプリの管理] ページ[](../../manage-apps.md)で組織の Shifts が有効になっていることを確認し、カスタム アプリのアクセス許可ポリシーを作成して、それらのユーザーに割り当てします。 詳細については、「Teams でアプリ [のアクセス許可ポリシーを管理する」を参照してください](../../teams-app-permission-policies.md)。

### <a name="use-the-frontlineworker-app-setup-policy-to-pin-shifts-to-teams"></a>FrontlineWorker アプリのセットアップ ポリシーを使用して、Shifts を Teams にピン留めする

アプリ セットアップ ポリシーを使用すると、組織内のユーザーにとって最も重要なアプリを強調表示するように Teams をカスタマイズできます。 ポリシーに設定されたアプリは、アプリ バー (Teams デスクトップ クライアントの横、および Teams モバイル クライアントの一番下にある) にピン留めされ、ユーザーはそこからすばやく簡単にアプリにアクセスできます。
 
Teams には、組織内の Frontline Worker に割り当て可能な組み込みの FrontlineWorker アプリセットアップ ポリシーが含まれています。 既定では、ポリシーにはアクティビティ、シフト、チャット、および通話の各アプリが含まれています。 

FrontlineWorker ポリシーを表示するには、Microsoft Teams 管理センターの左側のナビゲーションで **、Teams** アプリアプリのセットアップ ポリシー  >  **に移動します**。

![FrontlineWorker アプリのセットアップ ポリシーのスクリーンショット](../../media/firstline-worker-app-setup-policy.png "Microsoft Teams 管理センターの FrontlineWorker アプリセットアップ ポリシーのスクリーンショット")

#### <a name="assign-the-frontlineworker-app-setup-policy-to-users"></a>FrontlineWorker アプリのセットアップ ポリシーをユーザーに割り当てる

[!INCLUDE [assign-policy](../../includes/assign-policy.md)]

## <a name="search-the-audit-log-for-shifts-events"></a>監査ログで Shifts イベントを検索する

**(プレビュー段階)**

監査ログを検索して、組織内のシフト アクティビティを表示できます。  監査ログを検索する方法と、監査ログに記録された [シフト](../../audit-log-events.md#shifts-in-teams-activities) アクティビティの一覧を表示する方法の詳細については [、「Teams](../../audit-log-events.md)でイベントの監査ログを検索する」を参照してください。

監査ログを検索するには、まずセキュリティ/コンプライアンス センターで監査 [&があります](https://protection.office.com)。 詳細については、「監査ログの検索 [を有効またはオフにする」を参照してください](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014)。 監査データは、監査を有効にした時点からのみ利用できます。

## <a name="related-topics"></a>関連項目

- [最前線の従業員向けシフト ヘルプ](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
- [ Teams でユーザーにポリシーを割り当てる](../../assign-policies.md)
