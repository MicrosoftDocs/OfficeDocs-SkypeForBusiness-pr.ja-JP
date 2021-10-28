---
title: 組織のシフト アプリを管理する
author: serdarsoysal
ms.author: serdars
ms.reviewer: lisawu,gumariam
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
description: 組織内のフロントライン ワーカー向け Teams Shifts アプリを設定および管理する方法について学習します。
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 87389dfaba68de8cfe02f3291e03d593bb9de75b
ms.sourcegitcommit: 3a8bec0445cee5cd776fb1991f093a0ec4351852
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/28/2021
ms.locfileid: "60605833"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a>Microsoft Teams で組織のシフト アプリを管理する

> [!IMPORTANT]
> 2020 年 6 月 30 日をもって、Microsoft Staffhub は廃止されました。 Microsoft では、StaffHub の機能を Microsoft Teams に組み込む作業に取り組んでいます。 現在、Teams にはシフト アプリのスケジュール管理機能が含まれています。今後、他の機能もロールアウトされる予定です。 StaffHub は 2020 年 6 月 30 日をもって、すべてのユーザーがご利用できなくなりました。 ユーザーが StaffHub を開くと、Teams をダウンロードするように求めるメッセージが表示されます。 詳細については、「[Microsoft StaffHub は廃止されました](microsoft-staffhub-to-be-retired.md)」を参照してください。  

## <a name="overview-of-shifts"></a>シフトの概要

Microsoft Teams Shifts アプリは、フロントライン ワーカーを接続し、同期を維持します。チームの時間管理とコミュニケーションを迅速かつ効果的に行うモバイルを最初に構築します。 シフトを使用すると、フロントラインの従業員とそのマネージャーは、モバイル デバイスを使用してスケジュールを管理し、連絡を取り合います。

- マネージャーは、チームのシフト スケジュールを作成、更新、および管理します。 マネージャーは、メッセージを 1 人のユーザーに送ることも ("床が汚れています" など)、チーム全体に送ることもできます ("地区本部長があと 20 分で到着します" など)。 マネージャーは、ポリシー ドキュメント、ニュース速報、およびビデオを送信することもできます。
- 従業員は、自分の今後のシフトの確認、自分の他にその日にスケジュールが入っている従業員の表示、シフトの入れ替えや申し出のリクエスト、および休暇のリクエストを行います。

Shifts では現在ゲストがサポートされていません。 つまり、Teams でゲスト アクセスがオンになっていると、チームのゲストをシフト スケジュールに追加することも、チームのゲストがシフト スケジュールを使用することもできません。 

> [!Note]
> さまざまなプラットフォームでの Shifts 機能の詳細については、「[プラットフォームごとの Teams の機能](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)」を参照してください。

## <a name="availability-of-shifts"></a>シフトの可用性

シフトは、Teams が使用可能なすべてのエンタープライズ SKU で使用できます。

## <a name="location-of-shifts-data"></a>シフトのデータの場所

現在、シフトのデータは、北米、西ヨーロッパ、およびアジア太平洋にあるデータ センターの Azure に保存されています。 データが保存される場所の詳細については、「[データの保存場所](http://o365datacentermap.azurewebsites.net/)」を参照してください。

## <a name="set-up-shifts"></a>シフトのセットアップ

### <a name="enable-or-disable-shifts-in-your-organization"></a>組織のシフトを有効または無効にする

シフトは、組織内のすべての Teams ユーザーに対して既定で有効になっています。 組織レベルでアプリをオフまたはオンにするには、Microsoft Teams 管理センターの [[アプリを管理]](../../manage-apps.md) ページで行います。

1. Microsoft Teams 管理センターの左側のナビゲーションで、**[Teams アプリ]** > **[アプリを管理]** の順に移動します。
2. アプリ リストで、次のいずれかの操作を実行します。

    - 組織のシフトをオフにするには、シフト アプリを検索して選択し、**[ブロック]** を選択します。
    - 組織のシフトをオンにするには、シフト アプリを検索して選択し、**[許可]** を選択します。

### <a name="enable-or-disable-shifts-for-specific-users-in-your-organization"></a>組織内の特定のユーザーのシフトを有効または無効にする

組織内の特定のユーザーによる Shifts の使用を許可またはブロックするには、[アプリの管理] ページで組織の Shifts が有効 [になっていることを確認](../../manage-apps.md) します。 次に、カスタム アプリのアクセス許可ポリシーを作成し、それらのユーザーに割り当てる必要があります。 詳細については、「[Teams のアプリのアクセス許可ポリシーを管理する](../../teams-app-permission-policies.md)」を参照してください。

### <a name="use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams"></a>FirstLineWorker のアプリ セットアップ ポリシーを使用してシフトを Teams にピン留めする

アプリ セットアップ ポリシーを使用すると、組織内のユーザーにとって最も重要なアプリを強調表示するように Teams をカスタマイズできます。 ポリシーに設定されたアプリは、アプリ バー (Teams デスクトップ クライアントの横、および Teams モバイル クライアントの一番下にある) にピン留めされ、ユーザーはそこからすばやく簡単にアプリにアクセスできます。
 
Teamsには、組織内のフロントライン ワーカーに割り当て可能な組み込みの FirstLineWorker アプリセットアップ ポリシーが含まれています。 既定では、ポリシーにはアクティビティ、シフト、チャット、および通話の各アプリが含まれています。

FirstLineWorker ポリシーを表示するには、Microsoft Teams 管理センターの左側のナビゲーションで、[アプリのセットアップ Teams **に**  >  **移動します**。

:::image type="content" source="../../media/firstline-worker-app-setup-policy-new.png" alt-text="管理センターの FirstLineWorker アプリセットアップ ポリシー Microsoft Teamsスクリーンショット" lightbox="../../media/firstline-worker-app-setup-policy-new.png":::

#### <a name="assign-the-firstlineworker-app-setup-policy-to-users"></a>FirstLineWorker アプリセットアップ ポリシーをユーザーに割り当てる

[!INCLUDE [assign-policy](../../includes/assign-policy.md)]

## <a name="search-the-audit-log-for-shifts-events"></a>Teams でシフト イベントの監査ログを検索する

**(プレビュー段階)**

監査ログを検索して、組織内のシフト アクティビティを表示できます。  監査ログを検索する方法と、監査ログに記録されている [Shifts アクティビティ](../../audit-log-events.md#shifts-in-teams-activities)のリストを確認するには、「[Teams 内でイベントの監査ログを検索する](../../audit-log-events.md)を参照してください。

監査ログを検索できるようになるには、最初に[セキュリティ/コンプライアンス センター](https://protection.office.com)で監査をオンにする必要があります。 詳細については、「[監査ログの検索を有効または無効にする](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014)」を参照してください。 利用できる監査データは、監査を有効にした時点以降のデータのみであることにご注意ください。

## <a name="related-topics"></a>関連トピック

- [フロントライン ワーカー向けシフト ヘルプ](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
- [ Teams でユーザーにポリシーを割り当てる](../../policy-assignment-overview.md)
