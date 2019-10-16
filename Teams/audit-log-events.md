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
ms.reviewer: anach
search.appverid: MET150
description: Office 365 監査ログから Microsoft Teams データを取得する方法について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5d332880756c0173045fc1e5464bd889d0131301
ms.sourcegitcommit: 5695ce88d4a6a8fb9594df8dd1c207e45be067be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "37515813"
---
<a name="search-the-audit-log-for-events-in-microsoft-teams"></a>Microsoft Teams でイベントの監査ログを検索する
==================================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

監査ログは Office 365 の複数のサービスにわたって特定のアクティビティを調査するのに役立ちます。 Teams の場合は、次のいくつかのアクティビティが監査対象になります。

-   チームの作成

-   チームの削除

-   追加されたチャネル

-   変更された設定

Office 365 で監査されるアクティビティの完全なリストを確認するには、「[Office 365 のセキュリティ センターとコンプライアンス センターで監査ログを検索する](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c)」をご覧ください。

## <a name="turn-on-auditing-in-teams"></a>Teams での監査をオンにする

監査データを表示するには、まず、**セキュリティ & コンプライアンスセンター**(https://protection.office.com)) で監査を有効にする必要があります。 監査をオンにする方法の詳細については、「[Office 365 監査ログの検索を有効または無効にする](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014)」をご覧ください。


> [!IMPORTANT]
> 利用できる監査データは、監査を有効にした時点以降のデータのみです。



## <a name="retrieve-teams-data-from-the-audit-log"></a>監査ログから Teams データを取得する

1.  監査ログを取得するには、[セキュリティ/コンプライアンス センター](https://go.microsoft.com/fwlink/?linkid=855775)に移動します。 [**検索 & 調査**] で、[**監査ログの検索**] を選びます。

2.  [**Search (検索)**] を使用して、監査するアクティビティ、日付、ユーザーをフィルターします。

3.  さらに詳しく分析するために、結果を Excel にエクスポートします。


> [!IMPORTANT]
> 監査データは、監査がオンになっている場合に、監査ログでのみ見ることができます。

## <a name="video-techtip-using-audit-log-search-in-teams"></a>ビデオ: TechTip: Using Audit Log Search in Teams (技術ヒント: Teams で監査ログ検索を使用する)

Teams のプログラム マネージャーの Ansuman Acharya が実施する、Office 365 セキュリティ/コンプライアンス センターでの Teams の監査ログ検索のデモンストレーションに参加できます。 


> [!VIDEO https://www.youtube.com/embed/UBxaRySAxyE]






