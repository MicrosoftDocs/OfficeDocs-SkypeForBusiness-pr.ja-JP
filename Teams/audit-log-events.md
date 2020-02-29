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
ms.openlocfilehash: 3f53d1a0b5e600de9d38233b243dba3486b88bf1
ms.sourcegitcommit: 6cfaadec5782ca7316db36472bd0be20217da693
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/29/2020
ms.locfileid: "42341625"
---
# <a name="search-the-audit-log-for-events-in-microsoft-teams"></a><span data-ttu-id="8fba7-103">Microsoft Teams でイベントの監査ログを検索する</span><span class="sxs-lookup"><span data-stu-id="8fba7-103">Search the audit log for events in Microsoft Teams</span></span>

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="8fba7-104">監査ログは Office 365 の複数のサービスにわたって特定のアクティビティを調査するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="8fba7-104">The audit log can help you investigate specific activities across Office 365 services.</span></span> <span data-ttu-id="8fba7-105">Teams の場合は、次のいくつかのアクティビティが監査対象になります。</span><span class="sxs-lookup"><span data-stu-id="8fba7-105">For Teams, here are some of the activities that are audited:</span></span>

- <span data-ttu-id="8fba7-106">チームの作成</span><span class="sxs-lookup"><span data-stu-id="8fba7-106">Team creation</span></span>

- <span data-ttu-id="8fba7-107">チームの削除</span><span class="sxs-lookup"><span data-stu-id="8fba7-107">Team deletion</span></span>

- <span data-ttu-id="8fba7-108">追加されたチャネル</span><span class="sxs-lookup"><span data-stu-id="8fba7-108">Added channel</span></span>

- <span data-ttu-id="8fba7-109">変更された設定</span><span class="sxs-lookup"><span data-stu-id="8fba7-109">Changed setting</span></span>

> [!NOTE]
> <span data-ttu-id="8fba7-110">プライベートチャネルからの監査イベントも、teams および標準チャネル用としてログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="8fba7-110">Audit events from private channels are also logged as they are for teams and standard channels.</span></span>

<span data-ttu-id="8fba7-111">Office 365 で監査されるアクティビティの完全なリストを確認するには、「[Office 365 のセキュリティ センターとコンプライアンス センターで監査ログを検索する](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8fba7-111">To see the complete list of activities that are audited in Office 365, read [Search the audit log in the Office 365 Security & Compliance Center](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c).</span></span>

## <a name="turn-on-auditing-in-teams"></a><span data-ttu-id="8fba7-112">Teams での監査をオンにする</span><span class="sxs-lookup"><span data-stu-id="8fba7-112">Turn on auditing in Teams</span></span>

<span data-ttu-id="8fba7-113">監査データを表示するには、まず[セキュリティ & コンプライアンスセンター](https://protection.office.com)で監査を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8fba7-113">Before you can look at audit data, you have to first turn on auditing in the [Security & Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="8fba7-114">監査をオンにする方法の詳細については、「[Office 365 監査ログの検索を有効または無効にする](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8fba7-114">For help turning on auditing, read [Turn Office 365 audit log search on or off](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8fba7-115">利用できる監査データは、監査を有効にした時点以降のデータのみです。</span><span class="sxs-lookup"><span data-stu-id="8fba7-115">Audit data is only available from the point at which you turned on Auditing.</span></span>

## <a name="retrieve-teams-data-from-the-audit-log"></a><span data-ttu-id="8fba7-116">監査ログから Teams データを取得する</span><span class="sxs-lookup"><span data-stu-id="8fba7-116">Retrieve Teams data from the audit log</span></span>

1. <span data-ttu-id="8fba7-117">監査ログを取得するには、[セキュリティ/コンプライアンス センター](https://go.microsoft.com/fwlink/?linkid=855775)に移動します。</span><span class="sxs-lookup"><span data-stu-id="8fba7-117">To retrieve audit logs, go to the [Security & Compliance Center](https://go.microsoft.com/fwlink/?linkid=855775).</span></span> <span data-ttu-id="8fba7-118">[**検索**] で、[**監査ログの検索**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="8fba7-118">Under **Search**, select **Audit log search**.</span></span>
1. <span data-ttu-id="8fba7-119">[**Search (検索)**] を使用して、監査するアクティビティ、日付、ユーザーをフィルターします。</span><span class="sxs-lookup"><span data-stu-id="8fba7-119">Use **Search** to filter by the activities, dates, and users you want to audit.</span></span>
1. <span data-ttu-id="8fba7-120">さらに詳しく分析するために、結果を Excel にエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="8fba7-120">Export your results to Excel for further analysis.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8fba7-121">監査データは、監査がオンになっている場合に、監査ログでのみ見ることができます。</span><span class="sxs-lookup"><span data-stu-id="8fba7-121">Audit data is only visible in the Audit Log if auditing is turned on.</span></span>

## <a name="external-user-scenario"></a><span data-ttu-id="8fba7-122">外部ユーザーのシナリオ</span><span class="sxs-lookup"><span data-stu-id="8fba7-122">External user scenario</span></span>

<span data-ttu-id="8fba7-123">ビジネスの観点から見ていく1つのシナリオは、チーム環境に外部ユーザーを追加することです。</span><span class="sxs-lookup"><span data-stu-id="8fba7-123">One scenario you might want to keep an eye on, from a business perspective, is the addition of external users to your Teams environment.</span></span> <span data-ttu-id="8fba7-124">外部ユーザーが有効になっている場合は、そのプレゼンスを監視することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8fba7-124">If external users are enabled, then monitoring their presence is a good idea.</span></span>

![一括削除によってトリガーされるイベントの一覧のスクリーンショット](media/TeamsExternalUserAddPolicy.png)

<span data-ttu-id="8fba7-126">外部ユーザーを監視するこのポリシーのスクリーンショットでは、ポリシーに名前を付け、ビジネスニーズに応じて重要度を設定し、(この例では) 1 つのアクティビティとして設定して、追加のみを監視するパラメーターを確立することができます。を超えている場合は、このアクティビティを Microsoft Teams に制限します。</span><span class="sxs-lookup"><span data-stu-id="8fba7-126">The screenshot of this policy to monitor external user adds allows you to name the policy, set the severity according to your business needs, set it as (in this case) a single activity, and then establish the parameters that will specifically monitor only the addition of non-internal users, and limit this activity to Microsoft Teams.</span></span>

<span data-ttu-id="8fba7-127">このポリシーの結果は、アクティビティログで確認できます。</span><span class="sxs-lookup"><span data-stu-id="8fba7-127">Then results from this policy will be able to be viewed in the activity log:</span></span>

![一括削除によってトリガーされるイベントの一覧のスクリーンショット](media/TeamsExternalUserList.png)

<span data-ttu-id="8fba7-129">ここでは、設定したポリシーとの一致を確認し、必要に応じて調整を行います。または、他の場所で使用するように結果をエクスポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="8fba7-129">Here you can review matches to the policy you've set, and make any adjustments as needed, or export the results to use elsewhere.</span></span>

## <a name="mass-delete-scenario"></a><span data-ttu-id="8fba7-130">一括削除のシナリオ</span><span class="sxs-lookup"><span data-stu-id="8fba7-130">Mass delete scenario</span></span>

<span data-ttu-id="8fba7-131">前に説明したように、削除シナリオを監視できます。</span><span class="sxs-lookup"><span data-stu-id="8fba7-131">As mentioned above, you can monitor deletion scenarios.</span></span> <span data-ttu-id="8fba7-132">チームサイトの一括削除を監視するポリシーを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="8fba7-132">It's possible to create a policy that would monitor mass deletion of Teams sites:</span></span>

![大量のチーム削除のポリシーの設定を示すポリシー作成ページのスクリーンショット](media/TeamsMassDeletePolicy.png)

<span data-ttu-id="8fba7-134">スクリーンショットのように、このポリシーのさまざまなパラメーターを設定して、レベル、単一または繰り返しのアクション、[チームとサイトの削除に制限するパラメーター] などのチームの削除を監視することができます。</span><span class="sxs-lookup"><span data-stu-id="8fba7-134">As the screenshot shows, you can set many different parameters for this policy to monitor Teams deletions, including severity, single or repeated action, and parameters limiting this to Teams and site deletion.</span></span> <span data-ttu-id="8fba7-135">この操作は、テンプレートから独立して行うことも、組織のニーズに応じて、このポリシーを基にして設定するテンプレートを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="8fba7-135">This can be done independently of a template, or you may have a template created to base this policy off, depending on your organizational needs.</span></span>

<span data-ttu-id="8fba7-136">ビジネスに適したポリシーを確立したら、イベントがトリガーされたときにアクティビティログで結果を確認できます。</span><span class="sxs-lookup"><span data-stu-id="8fba7-136">Once you've established a policy that will work for your business, you can then review the results in the activity log as events are triggered:</span></span>

![一括削除によってトリガーされるイベントの一覧のスクリーンショット](media/TeamsMassDeleteList.png)

<span data-ttu-id="8fba7-138">設定したポリシーにフィルターを適用して、そのポリシーの結果を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="8fba7-138">You can filter down to the policy you've set to see the results of that policy.</span></span> <span data-ttu-id="8fba7-139">アクティビティログに表示された結果が適切ではない場合 (多くの結果が表示されている場合や、何も起こらない場合) は、クエリを微調整して、必要な処理により関連性を高めることができます。</span><span class="sxs-lookup"><span data-stu-id="8fba7-139">If the results you're getting in the activity log are not satisfactory (maybe you're seeing a lot of results, or nothing at all), this may help you to fine-tune the query to make it more relevant to what you need it to do.</span></span>

## <a name="video-techtip-using-audit-log-search-in-teams"></a><span data-ttu-id="8fba7-140">ビデオ: TechTip: Using Audit Log Search in Teams (技術ヒント: Teams で監査ログ検索を使用する)</span><span class="sxs-lookup"><span data-stu-id="8fba7-140">Video: TechTip: Using Audit Log Search in Teams</span></span>

<span data-ttu-id="8fba7-141">Teams のプログラム マネージャーの Ansuman Acharya が実施する、Office 365 セキュリティ/コンプライアンス センターでの Teams の監査ログ検索のデモンストレーションに参加できます。</span><span class="sxs-lookup"><span data-stu-id="8fba7-141">Join Ansuman Acharya, a program manager for Teams, as he demonstrates conducting an Audit Log search for Teams in the Office 365 Security & Compliance Center.</span></span>

> [!VIDEO https://www.youtube.com/embed/UBxaRySAxyE]
