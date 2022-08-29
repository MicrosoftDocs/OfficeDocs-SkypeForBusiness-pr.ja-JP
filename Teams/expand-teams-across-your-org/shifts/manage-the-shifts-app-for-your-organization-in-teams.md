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
description: 組織内のフロントライン ワーカー用に Teams で Shifts アプリを設定および管理する方法について説明します。
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- microsoftcloud-healthcare
- microsoftcloud-retail
- m365-frontline
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 759e0cb846b6bca404276e50ca00a1ff28d5725c
ms.sourcegitcommit: 17f4baf85e1ac6a2af5f5c6ea2d5aae763efd917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/23/2022
ms.locfileid: "67405139"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a>Microsoft Teams で組織のシフト アプリを管理する

## <a name="overview-of-shifts"></a>シフトの概要

Microsoft Teams の Shifts アプリでは、現場のワーカーが接続され、同期されます。これは、チームの迅速かつ効果的な時間管理とコミュニケーションを実現するために、モバイルファーストで構築されています。 シフトにより、現場の従業員とそのマネージャーは、モバイル デバイスを使用してスケジュールを管理し、連絡を取り合うことができます。

- マネージャーは、チームのシフト スケジュールを作成、更新、および管理します。 マネージャーは、メッセージを 1 人のユーザーに送ることも ("床が汚れています" など)、チーム全体に送ることもできます ("地区本部長があと 20 分で到着します" など)。 マネージャーは、ポリシー ドキュメント、ニュース速報、およびビデオを送信することもできます。
- 従業員は、自分の今後のシフトの確認、自分の他にその日にスケジュールが入っている従業員の表示、シフトの入れ替えや申し出のリクエスト、および休暇のリクエストを行います。

Shifts は現在、ゲストをサポートしていないことを知しておくことが重要です。 つまり、Teams でゲスト アクセスがオンになっていると、チームのゲストをシフト スケジュールに追加することも、チームのゲストがシフト スケジュールを使用することもできません。

> [!Note]
> さまざまなプラットフォームでの Shifts 機能の詳細については、「[プラットフォームごとの Teams の機能](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)」を参照してください。

## <a name="availability-of-shifts"></a>シフトの可用性

シフトは、Teams が使用可能なすべてのエンタープライズ SKU で使用できます。

> [!NOTE]
> シフトは Government Community Cloud (GCC) 環境で使用できますが、GCC High 環境や DoD 環境では使用できません。

## <a name="location-of-shifts-data"></a>シフトのデータの場所

Shifts データは現在、アジア太平洋 (APAC)、欧州連合 (EU)、北米のデータ センターに Azure に格納されています。 データが保存される場所の詳細については、「[データの保存場所](http://o365datacentermap.azurewebsites.net/)」を参照してください。

Shifts データのストレージ、リテンション期間、取得、暗号化など、Shifts データの詳細については、「 [Shifts データに関する FAQ](shifts-data-faq.md)」を参照してください。

## <a name="set-up-shifts"></a>シフトのセットアップ

### <a name="enable-or-disable-shifts-in-your-organization"></a>組織のシフトを有効または無効にする

シフトは、組織内のすべての Teams ユーザーに対して既定で有効になっています。 組織レベルでアプリをオフまたはオンにするには、Microsoft Teams 管理センターの [[アプリを管理]](../../manage-apps.md) ページで行います。

1. Microsoft Teams 管理センターの左側のナビゲーションで、**[Teams アプリ]** > **[アプリを管理]** の順に移動します。
2. アプリの一覧で Shifts アプリを検索し、それを選択し、[ **状態** ] トグルを **[ブロック** ] または [ **許可**] に切り替えます。

### <a name="enable-or-disable-shifts-for-specific-users-in-your-organization"></a>組織内の特定のユーザーのシフトを有効または無効にする

組織内の特定のユーザーに Shifts の使用を許可またはブロックするには、[ [アプリの管理](../../manage-apps.md) ] ページで組織の Shift が有効になっていることを確認します。 次に、カスタム アプリのアクセス許可ポリシーを作成し、それらのユーザーに割り当てます。 詳細については、「[Teams のアプリのアクセス許可ポリシーを管理する](../../teams-app-permission-policies.md)」を参照してください。

### <a name="pin-shifts-to-teams"></a>Teams にシフトをピン留めする

#### <a name="use-the-tailored-frontline-app-experience-to-pin-shifts-and-other-apps-to-teams"></a>カスタマイズされたフロントライン アプリ エクスペリエンスを使用して、Shift やその他のアプリを Teams にピン留めする

Teams のカスタマイズされたフロントライン アプリ エクスペリエンスは、 [F ライセンス](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt)を持つユーザーにとって Teams で最も関連性の高いアプリをピン留めします。 ピン留めされたアプリには、Shifts、Walkie Talkie、タスク、承認などがあります。 既定では、この機能はオンになっており、現場のワーカーはニーズに合わせてすぐに使えるエクスペリエンスを提供します。

このアプリは、アプリ バー (Teams デスクトップ クライアントの横、および Teams モバイル クライアントの一番下にある) にピン留めされ、ユーザーはそこからすばやく簡単にアプリにアクセスできます。

その他設定したアプリ ポリシーでのエクスペリエンスの動作など、詳細については、「[現場の従業員向けの Teams アプリの調整](/microsoft-365/frontline/pin-teams-apps-based-on-license?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json)」を参照してください。  

#### <a name="use-an-app-setup-policy-to-pin-shifts-to-teams"></a>アプリセットアップ ポリシーを使用して Shifts を Teams にピン留めする

アプリセットアップ ポリシーを使用すると、Teams をカスタマイズして、ユーザーにとって最も重要なアプリをピン留めできます。

Shifts アプリを追加して [カスタム アプリセットアップ ポリシー](../../teams-app-setup-policies.md) を作成し、その [ポリシーをユーザーに割り当てることができます](../../assign-policies-users-and-groups.md) 。 または、Frontline Worker および Frontline Manager ポリシー パッケージの一部であるアプリ設定ポリシーを使用することもできます。

Teams の [ポリシー パッケージ](../../manage-policy-packages.md) は、組織内で同様のロールを持つユーザーに割り当てることができる定義済みのポリシーとポリシー設定のコレクションです。 Frontline Worker および Frontline Manager ポリシー パッケージの一連のポリシーには、Shifts アプリとそのロールのコミュニケーションとコラボレーション アクティビティをサポートするその他のアプリを固定するアプリセットアップ ポリシーが含まれます。

フロントライン ワーカーと Frontline Manager ポリシー パッケージは、フロントラインの従業員のポリシーを管理する際に簡略化、合理化、一貫性を提供するために使用することをお勧めします。

### <a name="enable-shift-based-tags-in-teams"></a>Teams でシフトベースのタグを有効にする

Teams の[タグ](https://support.microsoft.com/office/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e)を使用すると、ユーザーはチームの一部のユーザーと簡単に接続できます。 シフトベースのタグを使用すると、ユーザーには、Shifts でスケジュールとシフト グループ名に一致するタグが自動的に割り当てられます。 このタグは、チャットの [ **To** ] 行の@mentions、またはチームの任意の標準チャネルの投稿で使用できます。

シフトベースのタグを使用すると、ユーザーはリアルタイムでオンシフトしているユーザーにアクセスできます。 通知は、タグがチャットまたはチャネルの投稿で使用された時点でオンシフトしているユーザーにのみ送信されます。 次に例を示します。

- 店長は、@Cashiers タグを使用して、シフト内のすべてのキャッシャーのチャネルにアナウンスを投稿します。
- 看護師は、@CardiologistsOnCall タグを使用して、すべてのオンコールの心臓医とのチャットを開始します。

この機能は、Microsoft Teams 管理センターでオンまたはオフにすることができます。 詳細については、「[Teams でタグを管理する](../../manage-tags.md)」を参照してください。

## <a name="search-the-audit-log-for-shifts-events"></a>Teams でシフト イベントの監査ログを検索する

**(プレビュー段階)**

監査ログを検索して、組織内のシフト アクティビティを表示できます。  監査ログを検索する方法と、監査ログに記録されている [Shifts アクティビティ](../../audit-log-events.md#shifts-in-teams-activities)のリストを確認するには、「[Teams 内でイベントの監査ログを検索する](../../audit-log-events.md)を参照してください。

監査ログを検索できるようになるには、最初に[セキュリティ/コンプライアンス センター](https://protection.office.com) で監査をオンにする必要があります。 詳細については、「[監査ログの検索を有効または無効にする](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014)」を参照してください。 利用できる監査データは、監査を有効にした時点以降のデータのみであることにご注意ください。

## <a name="related-articles"></a>関連記事

- [Shifts for Teams](/microsoft-365/frontline/shifts-for-teams-landing-page)
- [Shifts データに関する FAQ](shifts-data-faq.md)
- [コネクタをシフトする](/microsoft-365/frontline/shifts-connectors)
- [フロントライン ワーカーの Shifts ヘルプ](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
- [ Teams でユーザーにポリシーを割り当てる](../../policy-assignment-overview.md)
