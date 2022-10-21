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
description: 組織内の現場担当者向けに Teams で Shifts アプリを設定および管理する方法について説明します。
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- microsoftcloud-healthcare
- microsoftcloud-retail
- m365-frontline
- highpri
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 358a0078eed6f693922b3aaedb3eea38a8bb7f82
ms.sourcegitcommit: 1161cddd077056a9c1e2da99a84e35be0380b1b1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/20/2022
ms.locfileid: "68655863"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a>Microsoft Teams で組織のシフト アプリを管理する

## <a name="overview-of-shifts"></a>シフトの概要

Microsoft Teams の Shifts アプリは、現場担当者の接続と同期を維持します。これは、チームの迅速かつ効果的な時間管理とコミュニケーションのために、最初にモバイルを構築しています。 シフトを使用すると、現場担当者とそのマネージャーはモバイル デバイスを使用してスケジュールを管理し、連絡を取り合うことができます。

- マネージャーは、チームのシフト スケジュールを作成、更新、および管理します。 マネージャーは、メッセージを 1 人のユーザーに送ることも ("床が汚れています" など)、チーム全体に送ることもできます ("地区本部長があと 20 分で到着します" など)。 マネージャーは、ポリシー ドキュメント、ニュース速報、およびビデオを送信することもできます。
- 従業員は、自分の今後のシフトの確認、自分の他にその日にスケジュールが入っている従業員の表示、シフトの入れ替えや申し出のリクエスト、および休暇のリクエストを行います。

Shifts は現在ゲストをサポートしていないことを知っておくべきことが重要です。 つまり、Teams でゲスト アクセスがオンになっていると、チームのゲストをシフト スケジュールに追加することも、チームのゲストがシフト スケジュールを使用することもできません。

> [!Note]
> さまざまなプラットフォームでの Shifts 機能の詳細については、「[プラットフォームごとの Teams の機能](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)」を参照してください。

## <a name="availability-of-shifts"></a>シフトの可用性

シフトは、Teams が使用可能なすべてのエンタープライズ SKU で使用できます。

> [!NOTE]
> シフトは Government Community Cloud (GCC) 環境では使用できますが、GCC High または DoD 環境では使用できません。

## <a name="location-of-shifts-data"></a>シフトのデータの場所

シフト データは現在、アジア太平洋 (APAC)、欧州連合 (EU)、北米のデータ センターの Azure に格納されています。 データが保存される場所の詳細については、「[データの保存場所](http://o365datacentermap.azurewebsites.net/)」を参照してください。

Shifts データのストレージ、保持、取得、暗号化など、Shifts データの詳細については、「 [Shifts データに関する FAQ](shifts-data-faq.md)」を参照してください。

## <a name="set-up-shifts"></a>シフトのセットアップ

### <a name="enable-or-disable-shifts-in-your-organization"></a>組織のシフトを有効または無効にする

シフトは、組織内のすべての Teams ユーザーに対して既定で有効になっています。 組織レベルでアプリをオフまたはオンにするには、Microsoft Teams 管理センターの [[アプリを管理]](../../manage-apps.md) ページで行います。

1. Microsoft Teams 管理センターの左側のナビゲーションで、**[Teams アプリ]** > **[アプリを管理]** の順に移動します。
2. アプリの一覧で Shifts アプリを検索して選択し、[ **状態]** トグルを **[ブロック** ] または [ **許可]** に切り替えます。

### <a name="enable-or-disable-shifts-for-specific-users-in-your-organization"></a>組織内の特定のユーザーのシフトを有効または無効にする

組織内の特定のユーザーが Shifts を使用することを許可またはブロックするには、[ [アプリの管理](../../manage-apps.md) ] ページで組織の Shifts がオンになっていることを確認します。 次に、アプリのアクセス許可のカスタム ポリシーを作成し、それらのユーザーに割り当てます。 詳細については、「[Teams のアプリのアクセス許可ポリシーを管理する](../../teams-app-permission-policies.md)」を参照してください。

### <a name="pin-shifts-to-teams"></a>シフトを Teams にピン留めする

#### <a name="use-the-tailored-frontline-app-experience-to-pin-shifts-and-other-apps-to-teams"></a>調整済みの現場アプリ エクスペリエンスを使用して、Shifts やその他のアプリを Teams にピン留めする

Teams のカスタマイズされたフロントライン アプリ エクスペリエンスは、 [F ライセンス](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt)を持つユーザーにとって Teams で最も関連性の高いアプリをピン留めします。 ピン留めされたアプリには、Shifts、Walkie Talkie、Tasks、Approvals が含まれます。 既定では、この機能はオンになっており、現場のワーカーはニーズに合わせてすぐに使えるエクスペリエンスを提供します。

このアプリは、アプリ バー (Teams デスクトップ クライアントの横、および Teams モバイル クライアントの一番下にある) にピン留めされ、ユーザーはそこからすばやく簡単にアプリにアクセスできます。

その他設定したアプリ ポリシーでのエクスペリエンスの動作など、詳細については、「[現場の従業員向けの Teams アプリの調整](/microsoft-365/frontline/pin-teams-apps-based-on-license?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json)」を参照してください。  

#### <a name="use-an-app-setup-policy-to-pin-shifts-to-teams"></a>アプリセットアップ ポリシーを使用して Shifts を Teams にピン留めする

アプリセットアップ ポリシーを使用すると、ユーザーにとって最も重要なアプリをピン留めするように Teams をカスタマイズできます。

[Shifts アプリを追加して、アプリセットアップ ポリシーでカスタム ポリシー](../../teams-app-setup-policies.md)を作成し、その[ポリシーをユーザーに割り当てることができます](../../assign-policies-users-and-groups.md)。 または、Frontline Worker および Frontline Manager ポリシー パッケージの一部であるアプリセットアップ ポリシーを使用することもできます。

Teams の [ポリシー パッケージ](../../manage-policy-packages.md) は、定義済みのポリシーとポリシー設定のコレクションであり、組織内で同様のロールを持つユーザーに割り当てることができます。 Frontline Worker および Frontline Manager ポリシー パッケージのポリシーのセットには、Shifts アプリとそのロールのコミュニケーションおよびコラボレーション アクティビティをサポートする他のアプリをピン留めするアプリセットアップ ポリシーが含まれています。

現場担当者のポリシーを管理するときに、現場担当者と現場担当者のポリシー パッケージを使用して、簡素化、合理化、一貫性を提供することをお勧めします。

### <a name="enable-shift-based-tags-in-teams"></a>Teams でシフトベースのタグを有効にする

Teams の[タグ](https://support.microsoft.com/office/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e)を使用すると、ユーザーはチームの一部のユーザーと簡単に接続できます。 シフトベースのタグを使用すると、スケジュールとシフト グループ名に一致するタグが Shifts に自動的に割り当てられます。 タグは、チャットまたはチームの任意の標準チャネルの投稿の **[To** ] 行の@mentionsで使用できます。

シフトベースのタグを使用すると、ユーザーはリアルタイムでシフトオンのユーザーにリーチできます。 通知は、タグがチャットまたはチャネル投稿で使用された時点でシフト中のユーザーにのみ送信されます。 次に例を示します。

- ストア マネージャーは、@Cashiers タグを使用して、すべてのオンシフト レジ担当者のチャネルにアナウンスを投稿します。
- 看護師は、@CardiologistsOnCallタグを使用して、すべてのオンコール心臓科医とチャットを開始します。

この機能は、Microsoft Teams 管理センターでオンまたはオフにすることができます。 詳細については、「[Teams でタグを管理する](../../manage-tags.md)」を参照してください。

## <a name="search-the-audit-log-for-shifts-events"></a>Teams でシフト イベントの監査ログを検索する

**(プレビュー段階)**

監査ログを検索して、組織内のシフト アクティビティを表示できます。  監査ログを検索する方法と、監査ログに記録されている [Shifts アクティビティ](../../audit-log-events.md#shifts-in-teams-activities)のリストを確認するには、「[Teams 内でイベントの監査ログを検索する](../../audit-log-events.md)を参照してください。

監査ログを検索できるようになるには、最初に[セキュリティ/コンプライアンス センター](https://protection.office.com) で監査をオンにする必要があります。 詳細については、「[監査ログの検索を有効または無効にする](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014)」を参照してください。 利用できる監査データは、監査を有効にした時点以降のデータのみであることにご注意ください。

## <a name="related-articles"></a>関連記事

- [Shifts for Teams](/microsoft-365/frontline/shifts-for-teams-landing-page)
- [シフト データに関する FAQ](shifts-data-faq.md)
- [Shifts コネクタ](/microsoft-365/frontline/shifts-connectors)
- [現場担当者向けの Shifts ヘルプ](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
- [ Teams でユーザーにポリシーを割り当てる](../../policy-assignment-overview.md)
