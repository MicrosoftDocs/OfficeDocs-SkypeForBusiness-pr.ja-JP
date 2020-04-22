---
title: Microsoft Teams でイベントの監査ログを検索する
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
ms.reviewer: anach
search.appverid: MET150
description: 監査ログから Microsoft Teams のデータを取得する方法について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9b1235dcd1a33800185eb005f5e309204790c5b1
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "43778893"
---
# <a name="search-the-audit-log-for-events-in-microsoft-teams"></a>Microsoft Teams でイベントの監査ログを検索する

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

監査ログは Office 365 の複数のサービスにわたって特定のアクティビティを調査するのに役立ちます。 Teams の場合は、次のいくつかのアクティビティが監査対象になります。

- チームの作成

- チームの削除

- 追加されたチャネル

- 変更された設定

> [!NOTE]
> プライベートチャネルからの監査イベントも、teams および標準チャネル用としてログに記録されます。

Microsoft 365 で監査されるアクティビティの完全なリストを確認するには、「 [microsoft 365 コンプライアンスセンターで監査ログを検索](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c)する」を参照してください。

## <a name="turn-on-auditing-in-teams"></a>Teams での監査をオンにする

監査データを表示するには、まず[セキュリティ & コンプライアンスセンター](https://protection.office.com)で監査を有効にする必要があります。 監査を有効にする方法については、「[監査ログの検索を有効または無効にする](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014)」を参照してください。

> [!IMPORTANT]
> 利用できる監査データは、監査を有効にした時点以降のデータのみです。

## <a name="retrieve-teams-data-from-the-audit-log"></a>監査ログから Teams データを取得する

1. 監査ログを取得するには、[セキュリティ/コンプライアンス センター](https://go.microsoft.com/fwlink/?linkid=855775)に移動します。 [**検索**] で、[**監査ログの検索**] を選びます。
1. [**Search (検索)**] を使用して、監査するアクティビティ、日付、ユーザーをフィルターします。
1. さらに詳しく分析するために、結果を Excel にエクスポートします。

> [!IMPORTANT]
> 監査データは、監査がオンになっている場合に、監査ログでのみ見ることができます。

## <a name="external-user-scenario"></a>外部ユーザーのシナリオ

ビジネスの観点から見ていく1つのシナリオは、チーム環境に外部ユーザーを追加することです。 外部ユーザーが有効になっている場合は、そのプレゼンスを監視することをお勧めします。

![一括削除によってトリガーされるイベントの一覧のスクリーンショット](media/TeamsExternalUserAddPolicy.png)

外部ユーザーを監視するこのポリシーのスクリーンショットを使用すると、ポリシーに名前を付け、ビジネスニーズに応じて重要度を設定して、(この例では) 1 つのアクティビティとして設定し、このアクティビティを Microsoft Teams に制限することができます。

このポリシーの結果は、アクティビティログで確認できます。

![一括削除によってトリガーされるイベントの一覧のスクリーンショット](media/TeamsExternalUserList.png)

ここでは、設定したポリシーとの一致を確認し、必要に応じて調整を行います。または、他の場所で使用するように結果をエクスポートすることができます。

## <a name="mass-delete-scenario"></a>一括削除のシナリオ

前に説明したように、削除シナリオを監視できます。 チームサイトの一括削除を監視するポリシーを作成することができます。

![大量のチーム削除のポリシーの設定を示すポリシー作成ページのスクリーンショット](media/TeamsMassDeletePolicy.png)

スクリーンショットのように、このポリシーのさまざまなパラメーターを設定して、レベル、単一または繰り返しのアクション、[チームとサイトの削除に制限するパラメーター] などのチームの削除を監視することができます。 この操作は、テンプレートから独立して行うことも、組織のニーズに応じて、このポリシーを基にして設定するテンプレートを作成することもできます。

ビジネスに適したポリシーを確立したら、イベントがトリガーされたときにアクティビティログで結果を確認できます。

![一括削除によってトリガーされるイベントの一覧のスクリーンショット](media/TeamsMassDeleteList.png)

設定したポリシーにフィルターを適用して、そのポリシーの結果を表示することができます。 アクティビティログに表示された結果が適切ではない場合 (多くの結果が表示されている場合や、何も起こらない場合) は、クエリを微調整して、必要な処理により関連性を高めることができます。

## <a name="video-techtip-using-audit-log-search-in-teams"></a>ビデオ: TechTip: Using Audit Log Search in Teams (技術ヒント: Teams で監査ログ検索を使用する)

Teams のプログラム マネージャーの Ansuman Acharya が実施する、Office 365 セキュリティ/コンプライアンス センターでの Teams の監査ログ検索のデモンストレーションに参加できます。

> [!VIDEO https://www.youtube.com/embed/UBxaRySAxyE]
