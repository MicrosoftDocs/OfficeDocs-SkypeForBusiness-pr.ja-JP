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
description: Office 365 監査ログから Microsoft Teams データを取得する方法について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3c1f82a7688e3fdde7be85004c717293cc5777fa
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41826275"
---
<a name="search-the-audit-log-for-events-in-microsoft-teams"></a><span data-ttu-id="a9c15-103">Microsoft Teams でイベントの監査ログを検索する</span><span class="sxs-lookup"><span data-stu-id="a9c15-103">Search the audit log for events in Microsoft Teams</span></span>
==================================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="a9c15-104">監査ログは Office 365 の複数のサービスにわたって特定のアクティビティを調査するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a9c15-104">The audit log can help you investigate specific activities across Office 365 services.</span></span> <span data-ttu-id="a9c15-105">Teams の場合は、次のいくつかのアクティビティが監査対象になります。</span><span class="sxs-lookup"><span data-stu-id="a9c15-105">For Teams, here are some of the activities that are audited:</span></span>

- <span data-ttu-id="a9c15-106">チームの作成</span><span class="sxs-lookup"><span data-stu-id="a9c15-106">Team creation</span></span>

- <span data-ttu-id="a9c15-107">チームの削除</span><span class="sxs-lookup"><span data-stu-id="a9c15-107">Team deletion</span></span>

- <span data-ttu-id="a9c15-108">追加されたチャネル</span><span class="sxs-lookup"><span data-stu-id="a9c15-108">Added channel</span></span>

- <span data-ttu-id="a9c15-109">変更された設定</span><span class="sxs-lookup"><span data-stu-id="a9c15-109">Changed setting</span></span>

> [!NOTE]
> <span data-ttu-id="a9c15-110">プライベートチャネルからの監査イベントも、teams および標準チャネル用としてログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="a9c15-110">Audit events from private channels are also logged as they are for teams and standard channels.</span></span>

<span data-ttu-id="a9c15-111">Office 365 で監査されるアクティビティの完全なリストを確認するには、「[Office 365 のセキュリティ センターとコンプライアンス センターで監査ログを検索する](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a9c15-111">To see the complete list of activities that are audited in Office 365, read [Search the audit log in the Office 365 Security & Compliance Center](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c).</span></span>

## <a name="turn-on-auditing-in-teams"></a><span data-ttu-id="a9c15-112">Teams での監査をオンにする</span><span class="sxs-lookup"><span data-stu-id="a9c15-112">Turn on auditing in Teams</span></span>

<span data-ttu-id="a9c15-113">監査データを表示するには、まず[セキュリティ & コンプライアンスセンター](https://protection.office.com)で監査を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9c15-113">Before you can look at audit data, you have to first turn on auditing in the [Security & Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="a9c15-114">監査をオンにする方法の詳細については、「[Office 365 監査ログの検索を有効または無効にする](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a9c15-114">For help turning on auditing, read [Turn Office 365 audit log search on or off](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a9c15-115">利用できる監査データは、監査を有効にした時点以降のデータのみです。</span><span class="sxs-lookup"><span data-stu-id="a9c15-115">Audit data is only available from the point at which you turned on Auditing.</span></span>

## <a name="retrieve-teams-data-from-the-audit-log"></a><span data-ttu-id="a9c15-116">監査ログから Teams データを取得する</span><span class="sxs-lookup"><span data-stu-id="a9c15-116">Retrieve Teams data from the audit log</span></span>


1.  <span data-ttu-id="a9c15-117">監査ログを取得するには、[セキュリティ/コンプライアンス センター](https://go.microsoft.com/fwlink/?linkid=855775)に移動します。</span><span class="sxs-lookup"><span data-stu-id="a9c15-117">To retrieve audit logs, go to the [Security & Compliance Center](https://go.microsoft.com/fwlink/?linkid=855775).</span></span> <span data-ttu-id="a9c15-118">[**検索**] で、[**監査ログの検索**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="a9c15-118">Under **Search**, select **Audit log search**.</span></span>



2. <span data-ttu-id="a9c15-119">[**Search (検索)**] を使用して、監査するアクティビティ、日付、ユーザーをフィルターします。</span><span class="sxs-lookup"><span data-stu-id="a9c15-119">Use **Search** to filter by the activities, dates, and users you want to audit.</span></span>

3. <span data-ttu-id="a9c15-120">さらに詳しく分析するために、結果を Excel にエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="a9c15-120">Export your results to Excel for further analysis.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a9c15-121">監査データは、監査がオンになっている場合に、監査ログでのみ見ることができます。</span><span class="sxs-lookup"><span data-stu-id="a9c15-121">Audit data is only visible in the Audit Log if auditing is turned on.</span></span>

## <a name="video-techtip-using-audit-log-search-in-teams"></a><span data-ttu-id="a9c15-122">ビデオ: TechTip: Using Audit Log Search in Teams (技術ヒント: Teams で監査ログ検索を使用する)</span><span class="sxs-lookup"><span data-stu-id="a9c15-122">Video: TechTip: Using Audit Log Search in Teams</span></span>

<span data-ttu-id="a9c15-123">Teams のプログラム マネージャーの Ansuman Acharya が実施する、Office 365 セキュリティ/コンプライアンス センターでの Teams の監査ログ検索のデモンストレーションに参加できます。</span><span class="sxs-lookup"><span data-stu-id="a9c15-123">Join Ansuman Acharya, a program manager for Teams, as he demonstrates conducting an Audit Log search for Teams in the Office 365 Security & Compliance Center.</span></span> 

> [!VIDEO https://www.youtube.com/embed/UBxaRySAxyE]
