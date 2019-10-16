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
<a name="search-the-audit-log-for-events-in-microsoft-teams"></a><span data-ttu-id="51091-103">Microsoft Teams でイベントの監査ログを検索する</span><span class="sxs-lookup"><span data-stu-id="51091-103">Search the audit log for events in Microsoft Teams</span></span>
==================================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="51091-104">監査ログは Office 365 の複数のサービスにわたって特定のアクティビティを調査するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="51091-104">The audit log can help you investigate specific activities across Office 365 services.</span></span> <span data-ttu-id="51091-105">Teams の場合は、次のいくつかのアクティビティが監査対象になります。</span><span class="sxs-lookup"><span data-stu-id="51091-105">For Teams, here are some of the activities that are audited:</span></span>

-   <span data-ttu-id="51091-106">チームの作成</span><span class="sxs-lookup"><span data-stu-id="51091-106">Team creation</span></span>

-   <span data-ttu-id="51091-107">チームの削除</span><span class="sxs-lookup"><span data-stu-id="51091-107">Team deletion</span></span>

-   <span data-ttu-id="51091-108">追加されたチャネル</span><span class="sxs-lookup"><span data-stu-id="51091-108">Added channel</span></span>

-   <span data-ttu-id="51091-109">変更された設定</span><span class="sxs-lookup"><span data-stu-id="51091-109">Changed setting</span></span>

<span data-ttu-id="51091-110">Office 365 で監査されるアクティビティの完全なリストを確認するには、「[Office 365 のセキュリティ センターとコンプライアンス センターで監査ログを検索する](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="51091-110">To see the complete list of activities that are audited in Office 365, read [Search the audit log in the Office 365 Security & Compliance Center](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c).</span></span>

## <a name="turn-on-auditing-in-teams"></a><span data-ttu-id="51091-111">Teams での監査をオンにする</span><span class="sxs-lookup"><span data-stu-id="51091-111">Turn on auditing in Teams</span></span>

<span data-ttu-id="51091-112">監査データを表示するには、まず、**セキュリティ & コンプライアンスセンター**(https://protection.office.com)) で監査を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="51091-112">Before you can look at audit data, you have to first turn on auditing in the **Security & Compliance Center**(https://protection.office.com).</span></span> <span data-ttu-id="51091-113">監査をオンにする方法の詳細については、「[Office 365 監査ログの検索を有効または無効にする](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="51091-113">For help turning on auditing, read [Turn Office 365 audit log search on or off](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).</span></span>


> [!IMPORTANT]
> <span data-ttu-id="51091-114">利用できる監査データは、監査を有効にした時点以降のデータのみです。</span><span class="sxs-lookup"><span data-stu-id="51091-114">Audit data is only available from the point at which you turned on Auditing.</span></span>



## <a name="retrieve-teams-data-from-the-audit-log"></a><span data-ttu-id="51091-115">監査ログから Teams データを取得する</span><span class="sxs-lookup"><span data-stu-id="51091-115">Retrieve Teams data from the audit log</span></span>

1.  <span data-ttu-id="51091-116">監査ログを取得するには、[セキュリティ/コンプライアンス センター](https://go.microsoft.com/fwlink/?linkid=855775)に移動します。</span><span class="sxs-lookup"><span data-stu-id="51091-116">To retrieve audit logs, go to the [Security & Compliance Center](https://go.microsoft.com/fwlink/?linkid=855775).</span></span> <span data-ttu-id="51091-117">[**検索 & 調査**] で、[**監査ログの検索**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="51091-117">Under **Search & Investigation**, select **Audit log search**.</span></span>

2.  <span data-ttu-id="51091-118">[**Search (検索)**] を使用して、監査するアクティビティ、日付、ユーザーをフィルターします。</span><span class="sxs-lookup"><span data-stu-id="51091-118">Use **Search** to filter by the activities, dates, and users you want to audit.</span></span>

3.  <span data-ttu-id="51091-119">さらに詳しく分析するために、結果を Excel にエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="51091-119">Export your results to Excel for further analysis.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="51091-120">監査データは、監査がオンになっている場合に、監査ログでのみ見ることができます。</span><span class="sxs-lookup"><span data-stu-id="51091-120">Audit data is only visible in the Audit Log if auditing is turned on.</span></span>

## <a name="video-techtip-using-audit-log-search-in-teams"></a><span data-ttu-id="51091-121">ビデオ: TechTip: Using Audit Log Search in Teams (技術ヒント: Teams で監査ログ検索を使用する)</span><span class="sxs-lookup"><span data-stu-id="51091-121">Video: TechTip: Using Audit Log Search in Teams</span></span>

<span data-ttu-id="51091-122">Teams のプログラム マネージャーの Ansuman Acharya が実施する、Office 365 セキュリティ/コンプライアンス センターでの Teams の監査ログ検索のデモンストレーションに参加できます。</span><span class="sxs-lookup"><span data-stu-id="51091-122">Join Ansuman Acharya, a program manager for Teams, as he demonstrates conducting an Audit Log search for Teams in the Office 365 Security & Compliance Center.</span></span> 


> [!VIDEO https://www.youtube.com/embed/UBxaRySAxyE]






