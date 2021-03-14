---
title: 組織のシフト アプリを管理する
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
description: Teams で組織の現場担当者向けにシフト アプリを設定および管理する方法を説明します。
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
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909091"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a>Microsoft Teams で組織のシフト アプリを管理する

> [!IMPORTANT]
> 2020 年 6 月 30 日をもって、Microsoft Staffhub は廃止されました。 Microsoft では、StaffHub の機能を Microsoft Teams に組み込む作業に取り組んでいます。 現在、Teams にはシフト アプリのスケジュール管理機能が含まれています。今後、他の機能もロールアウトされる予定です。 StaffHub は 2020 年 6 月 30 日をもって、すべてのユーザーがご利用できなくなりました。 ユーザーが StaffHub を開くと、Teams をダウンロードするように求めるメッセージが表示されます。 詳細については、「[Microsoft StaffHub は廃止されました](microsoft-staffhub-to-be-retired.md)」を参照してください。  

## <a name="overview-of-shifts"></a>シフトの概要

Microsoft Teams のシフト アプリでは、現場担当者との連絡と同期を常に行えます。このアプリは、チームが迅速で効果的な時間管理とコミュニケーションを行えるようにモバイル ファーストで構築されています。 シフトを使用すると、現場担当者とそのマネージャーは自分のモバイル デバイスを使用して、スケジュールを管理し、連絡を取ることができます。

- マネージャーは、チームのシフト スケジュールを作成、更新、および管理します。 マネージャーは、メッセージを 1 人のユーザーに送ることも ("床が汚れています" など)、チーム全体に送ることもできます ("地区本部長があと 20 分で到着します" など)。 マネージャーは、ポリシー ドキュメント、ニュース速報、およびビデオを送信することもできます。 
- 従業員は、自分の今後のシフトの確認、自分の他にその日にスケジュールが入っている従業員の表示、シフトの入れ替えや申し出のリクエスト、および休暇のリクエストを行います。 

シフトでは現在、ゲスト ユーザーはサポートされていませんのでご注意ください。 つまり、Teams でゲスト アクセスがオンになっていると、チームのゲストをシフト スケジュールに追加することも、チームのゲストがシフト スケジュールを使用することもできません。 

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

組織内の特定のユーザーによるシフトの使用を許可またはブロックするには、[[アプリの管理]](../../manage-apps.md) ページで組織のシフトがオンになっていることを確認してからカスタムのアプリのアクセス許可ポリシーを作成し、それらのユーザーに割り当てます。 詳細については、「[Teams のアプリのアクセス許可ポリシーを管理する](../../teams-app-permission-policies.md)」を参照してください。

### <a name="use-the-frontlineworker-app-setup-policy-to-pin-shifts-to-teams"></a>現場担当者のアプリ セットアップ ポリシーを使用してシフトを Teams にピン留めする

アプリ セットアップ ポリシーを使用すると、組織内のユーザーにとって最も重要なアプリを強調表示するように Teams をカスタマイズできます。 ポリシーに設定されたアプリは、アプリ バー (Teams デスクトップ クライアントの横、および Teams モバイル クライアントの一番下にある) にピン留めされ、ユーザーはそこからすばやく簡単にアプリにアクセスできます。
 
Teams には組み込みの現場担当者アプリ セットアップ ポリシーが含まれており、これを組織内の現場担当者に割り当てることができます。 既定では、ポリシーにはアクティビティ、シフト、チャット、および通話の各アプリが含まれています。 

現場担当者ポリシーを表示するには、Microsoft Teams 管理センターの左側のナビゲーションで、**[Teams アプリ]** > **[アプリ セットアップ ポリシー]** の順に移動します。

![現場担当者アプリのセットアップ ポリシーのスクリーンショット](../../media/firstline-worker-app-setup-policy.png "Microsoft Teams 管理センターの現場担当者アプリのセットアップ ポリシーのスクリーンショット")

#### <a name="assign-the-frontlineworker-app-setup-policy-to-users"></a>現場担当者アプリのセットアップ ポリシーをユーザーに割り当てる

[!INCLUDE [assign-policy](../../includes/assign-policy.md)]

## <a name="search-the-audit-log-for-shifts-events"></a>Teams でシフト イベントの監査ログを検索する

**(プレビュー段階)**

監査ログを検索して、組織内のシフト アクティビティを表示できます。  監査ログを検索する方法と、監査ログに記録されている [Shifts アクティビティ](../../audit-log-events.md#shifts-in-teams-activities)のリストを確認するには、「[Teams 内でイベントの監査ログを検索する](../../audit-log-events.md)を参照してください。

監査ログを検索できるようになるには、最初に[セキュリティ/コンプライアンス センター](https://protection.office.com)で監査をオンにする必要があります。 詳細については、「[監査ログの検索を有効または無効にする](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014)」を参照してください。 利用できる監査データは、監査を有効にした時点以降のデータのみであることにご注意ください。

## <a name="related-topics"></a>関連トピック

- [現場担当者向けのシフトのヘルプ](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
- [Teams でユーザーにポリシーを割り当てる](../../assign-policies.md)
