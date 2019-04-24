---
title: Microsoft Teams での使用状況とフィードバックを監視する
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 03/20/2019
ms.topic: article
ms.service: msteams
ms.reviewer: lolaj
description: ユーザーが Microsoft Teams をどのように使用しているかについて確認する場合や、ユーザーのエクスペリエンスに関するフィードバックを収集する場合に使用可能なレポート オプションについて説明します。
localization_priority: Priority
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e53ed44f4377d90ae0d43b8c8971f651d940b839
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32245708"
---
# <a name="monitor-usage-and-feedback-in-microsoft-teams"></a><span data-ttu-id="45402-103">Microsoft Teams での使用状況とフィードバックを監視する</span><span class="sxs-lookup"><span data-stu-id="45402-103">Monitor usage and feedback in Microsoft Teams</span></span>
<span data-ttu-id="45402-104">ユーザーがどのように Teams を使用していているか、また Teams に関するユーザーのエクスペリエンスはどのようなものかを知ることは重要です。</span><span class="sxs-lookup"><span data-stu-id="45402-104">It's important to know how users are using Teams and what their experience is with Teams.</span></span> <span data-ttu-id="45402-105">使用状況レポートは、使用パターンを正しく理解するために役立ちます。また、ユーザーのフィードバックと併用することで、広範な展開の情報を確認し、トレーニングとコミュニケーションの取り組みに関する優先順位を決定するための見識が得られます。</span><span class="sxs-lookup"><span data-stu-id="45402-105">Usage reports can help you better understand usage patterns, and along with user feedback, give you insights to inform your wider rollout and where to prioritize training and communication efforts.</span></span>

## <a name="monitor-usage"></a><span data-ttu-id="45402-106">使用状況の監視</span><span class="sxs-lookup"><span data-stu-id="45402-106">Monitor usage</span></span>
<span data-ttu-id="45402-107">最初のチームのセットについては、新たに出現する傾向を理解するために 1 週間に 2 回はレポートを確認するようにしてください。</span><span class="sxs-lookup"><span data-stu-id="45402-107">For your first set of teams, we recommend you review reports twice a week to understand emerging trends.</span></span> 

<span data-ttu-id="45402-108">たとえば、Teams のモバイル クライアントを使用しているユーザーが、それほど多くいないことが使用状況レポートに示されているとします。</span><span class="sxs-lookup"><span data-stu-id="45402-108">For example, usage reports show that not many users are using the Teams mobile clients.</span></span> <span data-ttu-id="45402-109">これは、ユーザーがクライアントのインストール方法を理解していないことを示している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="45402-109">This may indicate that users aren't sure how to install the clients.</span></span> <span data-ttu-id="45402-110">チャネルに詳しいインストールの手順を投稿することで、広範なクライアントの使用を推進できるでしょう。</span><span class="sxs-lookup"><span data-stu-id="45402-110">Posting step-by-step installation instructions in a channel may help drive usage of a wider range of clients.</span></span> <span data-ttu-id="45402-111">また、ユーザーが主にプライベート チャットのために Teams を使用していることを使用状況レポートが示しているとします。</span><span class="sxs-lookup"><span data-stu-id="45402-111">Or, usage reports show that users are primarily using Teams for private chats.</span></span> <span data-ttu-id="45402-112">この例では、ユーザーは最初にセットアップしたチームとチャネル以外でチャットしているため、チームのシナリオの再検討が必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="45402-112">In this example, you may want to review your team scenarios because users are chatting outside the initial teams and channels that were set up.</span></span> 

<span data-ttu-id="45402-113">次に、Teams の使用状況を確認するレポートの取得方法を示します。</span><span class="sxs-lookup"><span data-stu-id="45402-113">Here's how to get reports to view Teams usage.</span></span> 

### <a name="teams-analytics--reports-microsoft-teams-admin-center"></a><span data-ttu-id="45402-114">Teams の分析とレポート (Microsoft Teams 管理センター)</span><span class="sxs-lookup"><span data-stu-id="45402-114">Teams analytics & reports (Microsoft Teams admin center)</span></span>

<span data-ttu-id="45402-115">Microsoft Teams 管理センターでの Teams のレポートにより、Teams が組織内でどのように使用されているかについての見識が得られます。</span><span class="sxs-lookup"><span data-stu-id="45402-115">Teams reports in the Microsoft Teams admin center give you insights into how Teams is used in your organization.</span></span> <span data-ttu-id="45402-116">このレポートを使用して組織全体の Teams の使用状況、ユーザー アクティビティ、およびデバイスの使用状況について調べます。</span><span class="sxs-lookup"><span data-stu-id="45402-116">Use the reports to get a view into Teams usage, user activity, and device usage across your organization.</span></span> 

<span data-ttu-id="45402-117">このようなレポートを表示するには、Office 365 の全体管理者、Teams のサービス管理者、または Skype for Business の管理者であることが必要です。Microsoft Teams 管理センターに移動して、左側のナビゲーションにある **[分析およびレポート]** を選択し、**[レポート]** から実行するレポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="45402-117">To view these reports, you must be a global admin in Office 365, Teams service admin, or Skype for Business admin. Go to the Microsoft Teams admin center, in the left navigation, select **Analytics & reports**, and then under **Report**, choose the report you want to run.</span></span>

- <span data-ttu-id="45402-118">**Teams の使用状況レポート**: このレポートには、Teams の使用状況アクティビティの概要が示されます。アクティブなユーザーとチャネルの合計数、アクティブなユーザー数とチャネル数、ゲスト数、および各チームのメッセージ数も示されます。</span><span class="sxs-lookup"><span data-stu-id="45402-118">**Teams usage report**: This report gives you an overview of usage activity in Teams, including the total active users and channels, and the number of active users and channels, guests, and messages in each team.</span></span> 

    <span data-ttu-id="45402-119">![Teams の使用状況レポート](media/teams-reports-teams-usage.png "Microsoft Teams 管理センターでの Teams の使用状況レポートを示すスクリーンショット")</span><span class="sxs-lookup"><span data-stu-id="45402-119">![Teams usage report](media/teams-reports-teams-usage.png "Screen shot of the Teams usage report in the Microsoft Teams admin center")</span></span>     
- <span data-ttu-id="45402-120">**Teams のユーザー アクティビティ レポート**: このレポートでは、1 対 1 の通話、チャネルのメッセージ、およびプライベート チャットのメッセージで通信したユーザー数など、ユーザーが関与したアクティビティの種類についての見識が得られます。</span><span class="sxs-lookup"><span data-stu-id="45402-120">**Teams user activity report**: This report gives you insight into the types of activities users engage in, such as how many people communicate through 1:1 calls, channel messages, and private chat messages.</span></span> 

    <span data-ttu-id="45402-121">![Teams のユーザー アクティビティ レポート](media/teams-reports-user-activity.png "Microsoft Teams 管理センターでの Teams のユーザー アクティビティ レポートを示すスクリーンショット") 
\`</span><span class="sxs-lookup"><span data-stu-id="45402-121">![Teams user activity report](media/teams-reports-user-activity.png "Screen shot of the Teams user activity report in the Microsoft Teams admin center") 
\`</span></span>
- <span data-ttu-id="45402-122">**Teams のデバイス使用状況レポート**: このレポートには、ユーザーがどのように Teams に接続しているかが示されます。外出先で自分のモバイル デバイスから Teams を使用したユーザーの数も示されます。</span><span class="sxs-lookup"><span data-stu-id="45402-122">**Teams device usage report**: This report shows you how users connect to Teams, including how many people use Teams on their mobile devices when on-the-go.</span></span> 

    <span data-ttu-id="45402-123">![Teams デバイス使用状況レポート](media/teams-reports-device-usage.png "Microsoft Teams 管理センターでの Teams のデバイス使用状況レポートを示すスクリーンショット")</span><span class="sxs-lookup"><span data-stu-id="45402-123">![Teams device usage report](media/teams-reports-device-usage.png "Screen shot of the Teams device usage report in the Microsoft Teams admin center")</span></span>

<span data-ttu-id="45402-124">詳細については、「[Teams の分析とレポート](teams-analytics-and-reports/teams-reporting-reference.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="45402-124">To learn more, check out [Teams analytics and reporting](teams-analytics-and-reports/teams-reporting-reference.md).</span></span> 

### <a name="teams-activity-reports-office-365-admin-center"></a><span data-ttu-id="45402-125">Teams のアクティビティ レポート (Office 365 管理センター)</span><span class="sxs-lookup"><span data-stu-id="45402-125">Teams activity reports (Office 365 admin center)</span></span>
<span data-ttu-id="45402-126">Teams のアクティビティは、Office 365 管理センターから利用可能なレポートで確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="45402-126">You can also view Teams activity through reports that are available from the Office 365 admin center.</span></span> <span data-ttu-id="45402-127">これに該当するレポートは、Office 365 管理センターの Office 365 レポートに含まれていて、ユーザー アクティビティとデバイス使用状況に関する情報が示されます。</span><span class="sxs-lookup"><span data-stu-id="45402-127">These reports are part of the Office 365 reports in the Office 365 admin center and provide information about user activity and device usage.</span></span> 

<span data-ttu-id="45402-128">このレポートを表示するには、Office 365 管理センターに移動して **[レポート]** > **[使用状況]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="45402-128">To view these reports, go to the Office 365 admin center, click **Reports** > **Usage**.</span></span> <span data-ttu-id="45402-129">**[レポートの選択]** で、**[Microsoft Teams]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="45402-129">Under **Select a report**, click **Microsoft Teams**.</span></span> <span data-ttu-id="45402-130">ここから、表示するレポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="45402-130">From here, choose the report you want to view.</span></span>

<span data-ttu-id="45402-131">詳細については、「[Teams のアクティビティ レポートを使用する](teams-activity-reports.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="45402-131">To learn more, go to [Use activity reports for Teams](teams-activity-reports.md).</span></span>

### <a name="microsoft-365-usage-analytics"></a><span data-ttu-id="45402-132">Microsoft 365 利用状況分析</span><span class="sxs-lookup"><span data-stu-id="45402-132">Microsoft 365 usage analytics</span></span>

<span data-ttu-id="45402-133">Power BI の Microsoft 365 利用状況分析を使用すると、Teams などの Office 365 製品とサービスの使用状況データを表示および分析できます。</span><span class="sxs-lookup"><span data-stu-id="45402-133">You can use Microsoft 365 usage analytics in Power BI to view and analyze usage data for Teams and other Office 365 products and services.</span></span> <span data-ttu-id="45402-134">Microsoft 365 利用状況分析は、事前に作成された 1 つのダッシュボードと事前に作成された複数のレポートが含まれているコンテンツ パックです。</span><span class="sxs-lookup"><span data-stu-id="45402-134">Microsoft 365 usage analytics is a content pack that includes a pre-built dashboard and a number of pre-built reports.</span></span> <span data-ttu-id="45402-135">それぞれのレポートで特定の使用状況のデータと見識が得られます。</span><span class="sxs-lookup"><span data-stu-id="45402-135">Each report gives you specific usage data and insights.</span></span> <span data-ttu-id="45402-136">このコンテンツ パックに接続するには、Power BI が必要になります。また、Office 365 の全体管理者かレポート閲覧者であることが必要です。</span><span class="sxs-lookup"><span data-stu-id="45402-136">To connect to the content pack, you need Power BI and must be a global admin in Office 365 or reports reader.</span></span> <span data-ttu-id="45402-137">まだ Power BI がない場合は、[無料の Power BI サービスにサイン アップ](https://powerbi.microsoft.com)してください。</span><span class="sxs-lookup"><span data-stu-id="45402-137">If you don't already have Power BI, [sign up for the free Power BI service](https://powerbi.microsoft.com).</span></span> 

<span data-ttu-id="45402-138">詳細については、「[Microsoft 365 利用状況分析](https://support.office.com/article/Microsoft-365-usage-analytics-77ff780d-ab19-4553-adea-09cb65ad0f1f)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="45402-138">To learn more, see [Microsoft 365 usage analytics](https://support.office.com/article/Microsoft-365-usage-analytics-77ff780d-ab19-4553-adea-09cb65ad0f1f).</span></span> 

## <a name="gather-feedback"></a><span data-ttu-id="45402-139">フィードバックの収集</span><span class="sxs-lookup"><span data-stu-id="45402-139">Gather feedback</span></span>
<span data-ttu-id="45402-140">新しい共同作業エクスペリエンスの導入は、ユーザーの行動を変更するということです。</span><span class="sxs-lookup"><span data-stu-id="45402-140">The adoption of a new collaboration experience is about changing the behavior of users.</span></span> <span data-ttu-id="45402-141">その変更を可能にするには、トレーニング、奨励、および肯定的な例が必要です。</span><span class="sxs-lookup"><span data-stu-id="45402-141">Enabling change requires training, encouragement, and positive examples.</span></span> <span data-ttu-id="45402-142">Teams への移行時にはユーザーに発言権があることと、ユーザーの経験をオープンに共有できるようにすることが重要です。</span><span class="sxs-lookup"><span data-stu-id="45402-142">It's important for users to have a voice during the transition to Teams and to be able to openly share their experiences.</span></span> <span data-ttu-id="45402-143">「Get to know Teams」チームの [Feedback] チャネルの使用をお勧めします。このチャネルは、ユーザーから Teams での経験に関するフィードバックを収集して処理するために作成したものです。</span><span class="sxs-lookup"><span data-stu-id="45402-143">We recommend using the Feedback channel in the "Get to know Teams" team you created to collect and address feedback from users on their experiences with Teams.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="45402-144">次のステップ</span><span class="sxs-lookup"><span data-stu-id="45402-144">Next steps</span></span>
<span data-ttu-id="45402-145">「[Teams の組織全体の展開を計画するためのリソースを取得する](get-started-with-teams-resources-for-org-wide-rollout.md)」に移動します。</span><span class="sxs-lookup"><span data-stu-id="45402-145">Go to [Get resources to plan your organization-wide rollout of Teams](get-started-with-teams-resources-for-org-wide-rollout.md).</span></span>
