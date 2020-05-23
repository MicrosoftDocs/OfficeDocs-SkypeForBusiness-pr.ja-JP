---
title: レポートを実行してアクティブな StaffHub の使用状況を表示する
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: レポートを実行して、組織内のアクティブな StaffHub ユーザーの一覧を取得する方法について説明します。
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5701e508440a338e0f0ba1fd133dac98ec35d57f
ms.sourcegitcommit: ee2b4c207b3c9f993309f66cf8016e137c001c7f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/23/2020
ms.locfileid: "44349631"
---
# <a name="run-a-report-to-show-active-staffhub-usage"></a><span data-ttu-id="29d88-103">レポートを実行してアクティブな StaffHub の使用状況を表示する</span><span class="sxs-lookup"><span data-stu-id="29d88-103">Run a report to show active StaffHub usage</span></span>

> [!IMPORTANT]
> <span data-ttu-id="29d88-104">2020年6月30日の有効な Microsoft StaffHub は廃止されます。</span><span class="sxs-lookup"><span data-stu-id="29d88-104">Effective June 30, 2020, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="29d88-105">Microsoft では、StaffHub の機能を Microsoft Teams に組み込む作業に取り組んでいます。</span><span class="sxs-lookup"><span data-stu-id="29d88-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="29d88-106">現在、Teams にはシフト アプリのスケジュール管理機能が含まれています。今後、他の機能もロールアウトされる予定です。</span><span class="sxs-lookup"><span data-stu-id="29d88-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="29d88-107">2020年6月30日に、StaffHub はすべてのユーザーに対して機能しなくなります。</span><span class="sxs-lookup"><span data-stu-id="29d88-107">StaffHub will stop working for all users on June 30, 2020.</span></span> <span data-ttu-id="29d88-108">ユーザーが StaffHub を開くと、Teams をダウンロードするように求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="29d88-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="29d88-109">詳細については、「[Microsoft StaffHub の廃止](microsoft-staffhub-to-be-retired.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29d88-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>  

<span data-ttu-id="29d88-110">この記事の手順を使用してレポートを実行し、組織内のアクティブな StaffHub ユーザーの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="29d88-110">Use the steps in this article to run a report to get a list of active StaffHub users in your organization.</span></span> <span data-ttu-id="29d88-111">この情報は[、StaffHub teams を Microsoft teams に移行](move-staffhub-teams-to-shifts-in-teams.md)するときに役立つ場合があります。</span><span class="sxs-lookup"><span data-stu-id="29d88-111">This information may come in handy when you prepare to [move your StaffHub teams to Microsoft Teams](move-staffhub-teams-to-shifts-in-teams.md).</span></span> <span data-ttu-id="29d88-112">このレポートでは、StaffHub から Teams への切り替えを行うときに、通信に含める必要があるユーザーを確認できます。</span><span class="sxs-lookup"><span data-stu-id="29d88-112">From the report, you'll know who you need to include in your communications when you make the switch from StaffHub to Teams.</span></span>

<span data-ttu-id="29d88-113">この記事の手順を実行するには、Azure AD Premium が必要です。</span><span class="sxs-lookup"><span data-stu-id="29d88-113">You need to have Azure AD Premium to perform the steps in this article.</span></span>

1. <span data-ttu-id="29d88-114">Azure ポータルにサインインします。</span><span class="sxs-lookup"><span data-stu-id="29d88-114">Sign in to the Azure portal.</span></span>
2. <span data-ttu-id="29d88-115">左側のウィンドウで、 **Azure Active Directory**リソースをクリックします。</span><span class="sxs-lookup"><span data-stu-id="29d88-115">In the left pane, click the **Azure Active Directory** resource.</span></span>
3. <span data-ttu-id="29d88-116">[**監視**] で [**サインイン**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="29d88-116">Under **Monitoring**, click **Sign-ins**.</span></span>
4. <span data-ttu-id="29d88-117">[**アプリケーション**] の下に「 **Microsoft StaffHub**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="29d88-117">Under **Application**, type **Microsoft StaffHub**.</span></span>
5. <span data-ttu-id="29d88-118">レポートに必要な日付の範囲を設定して、[**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="29d88-118">Set the date range that you want for the report, and then click **Apply**.</span></span> 

    ![アクティブな StaffHub の利用状況を表示する手順を示すスクリーンショット](../../media/staffhub-active-usage-report.png)

## <a name="related-topics"></a><span data-ttu-id="29d88-120">関連トピック</span><span class="sxs-lookup"><span data-stu-id="29d88-120">Related topics</span></span>

- [<span data-ttu-id="29d88-121">Microsoft StaffHub のチームを Microsoft Teams のシフトに移動する</span><span class="sxs-lookup"><span data-stu-id="29d88-121">Move your Microsoft StaffHub teams to Shifts in Microsoft Teams</span></span>](move-staffhub-teams-to-shifts-in-teams.md)
