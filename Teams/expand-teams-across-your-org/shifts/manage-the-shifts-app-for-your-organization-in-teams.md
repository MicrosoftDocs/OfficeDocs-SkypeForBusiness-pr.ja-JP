---
title: 組織のシフト アプリを管理する
author: LanaChin
ms.author: v-lanachin
ms.reviewer: aaku
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
- Microsoft Cloud for Retail
description: 組織内のフロントライン ワーカー向け Teams Shifts アプリを設定および管理する方法について学習します。
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
- microsoftcloud-healthcare
- microsoftcloud-retail
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: dd40888ec8f1f7c5c05c3f5a2bf5a867ece93a65
ms.sourcegitcommit: 10bee789272e648ea1e93d7d7c27ec645d0a8bdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/22/2022
ms.locfileid: "62918880"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a>Microsoft Teams で組織のシフト アプリを管理する

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

## <a name="shifts-data"></a>データをシフトする

Shifts データの保存場所と、Shifts データのリテンション期間、取得、暗号化の詳細については、「Shifts データに関する [FAQ」を参照してください](shifts-data-faq.md)。

## <a name="set-up-shifts"></a>シフトのセットアップ

### <a name="enable-or-disable-shifts-in-your-organization"></a>組織のシフトを有効または無効にする

シフトは、組織内のすべての Teams ユーザーに対して既定で有効になっています。 組織レベルでアプリをオフまたはオンにするには、Microsoft Teams 管理センターの [[アプリを管理]](../../manage-apps.md) ページで行います。

1. Microsoft Teams 管理センターの左側のナビゲーションで、**[Teams アプリ]** > **[アプリを管理]** の順に移動します。
2. アプリの一覧で Shifts アプリを検索して選択し、[状態] トグルを [ブロック] または [許可 **] に****切り替えます**。

### <a name="enable-or-disable-shifts-for-specific-users-in-your-organization"></a>組織内の特定のユーザーのシフトを有効または無効にする

組織内の特定のユーザーによる Shifts の使用を許可またはブロックするには、[アプリの管理] ページで組織の Shifts が有効 [になっていることを確認](../../manage-apps.md) します。 次に、カスタム アプリのアクセス許可ポリシーを作成し、それらのユーザーに割り当てる必要があります。 詳細については、「[Teams のアプリのアクセス許可ポリシーを管理する](../../teams-app-permission-policies.md)」を参照してください。

### <a name="use-an-app-setup-policy-to-pin-shifts-to-teams"></a>アプリセットアップ ポリシーを使用して、Shifts をアプリにピン留Teams

アプリ セットアップ ポリシーを使用すると、組織内のユーザーにとって最も重要なアプリを強調表示するように Teams をカスタマイズできます。 ポリシーに設定されたアプリは、アプリ バー (Teams デスクトップ クライアントの横、および Teams モバイル クライアントの一番下にある) にピン留めされ、ユーザーはそこからすばやく簡単にアプリにアクセスできます。

Shifts アプリを [追加してカスタム アプリセットアップ ポリシー](../../teams-app-setup-policies.md) を作成し、そのポリシーを [ユーザー](../../assign-policies-users-and-groups.md) に割り当てできます。 または、Frontline Worker および Frontline Manager ポリシー パッケージの一部であるアプリセットアップ ポリシーを使用できます。

Teams [の](../../manage-policy-packages.md)ポリシー パッケージは、組織内で同様のロールを持つユーザーに割り当て可能な定義済みのポリシーとポリシー設定のコレクションです。 Frontline Worker ポリシー パッケージと Frontline Manager ポリシー パッケージの一連のポリシーには、Shifts アプリと、そのロールのコミュニケーションおよびコラボレーション アクティビティをサポートする他のアプリをピン留めするアプリセットアップ ポリシーが含まれています。

Frontline Worker ポリシー パッケージと Frontline Manager ポリシー パッケージを使用することをお勧めします。Frontline Worker と Frontline Manager のポリシー パッケージは、フロントラインの従業員のポリシーを管理する際に簡素化、合理化、一貫性を提供するのに役立ちます。

## <a name="search-the-audit-log-for-shifts-events"></a>Teams でシフト イベントの監査ログを検索する

**(プレビュー段階)**

監査ログを検索して、組織内のシフト アクティビティを表示できます。  監査ログを検索する方法と、監査ログに記録されている [Shifts アクティビティ](../../audit-log-events.md#shifts-in-teams-activities)のリストを確認するには、「[Teams 内でイベントの監査ログを検索する](../../audit-log-events.md)を参照してください。

監査ログを検索できるようになるには、最初に[セキュリティ/コンプライアンス センター](https://protection.office.com)で監査をオンにする必要があります。 詳細については、「[監査ログの検索を有効または無効にする](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014)」を参照してください。 利用できる監査データは、監査を有効にした時点以降のデータのみであることにご注意ください。

## <a name="related-topics"></a>関連トピック

- [Shifts for Teams](../shifts-for-teams-landing-page.md)
- [フロントライン ワーカー向けシフト ヘルプ](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
- [コネクタをシフトする](shifts-connectors.md)
- [ Teams でユーザーにポリシーを割り当てる](../../policy-assignment-overview.md)
