---
title: 作業中の StaffHub の使用状況を表示するレポートを実行します。
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.date: 05/10/2019
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: 組織内でアクティブな StaffHub ユーザーの一覧を取得するレポートを実行する方法について説明します。
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e66e889fbc7fb26b8fda55beb889bc95b155666d
ms.sourcegitcommit: b2acf18ba6487154ebb4ee46938e96dc56cb2c9a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/09/2019
ms.locfileid: "33868197"
---
# <a name="run-a-report-to-show-active-staffhub-usage"></a><span data-ttu-id="dcea3-103">作業中の StaffHub の使用状況を表示するレポートを実行します。</span><span class="sxs-lookup"><span data-stu-id="dcea3-103">Run a report to show active StaffHub usage</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dcea3-104">2019 年 10 月 1 日より、Microsoft StaffHub が廃止されます。</span><span class="sxs-lookup"><span data-stu-id="dcea3-104">Effective October 1, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="dcea3-105">マイクロソフトのチームに StaffHub 機能が進められています。</span><span class="sxs-lookup"><span data-stu-id="dcea3-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="dcea3-106">今日では、チームには、スケジュール管理のためのシフトのアプリケーションが含まれていて、その他の機能が時間の経過と共に展開されます。</span><span class="sxs-lookup"><span data-stu-id="dcea3-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="dcea3-107">StaffHub は、2019 年 10 月 1 日ですべてのユーザーの作業を停止します。</span><span class="sxs-lookup"><span data-stu-id="dcea3-107">StaffHub will stop working for all users on October 1, 2019.</span></span> <span data-ttu-id="dcea3-108">StaffHub を開こうとするとすべての人がチームをダウンロードすることを指示するメッセージ表示されます。</span><span class="sxs-lookup"><span data-stu-id="dcea3-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="dcea3-109">詳細については、「[Microsoft StaffHub の廃止](microsoft-staffhub-to-be-retired.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dcea3-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>  

<span data-ttu-id="dcea3-110">組織内でアクティブな StaffHub ユーザーの一覧を取得するのにレポートを実行するのにこの資料の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="dcea3-110">Use the steps in this article to run a report to get a list of active StaffHub users in your organization.</span></span> <span data-ttu-id="dcea3-111">この情報が役に立つ[マイクロソフトのチーム、StaffHub チームに移動](move-staffhub-teams-to-shifts-in-teams.md)する準備ができたら。</span><span class="sxs-lookup"><span data-stu-id="dcea3-111">This information may come in handy when you prepare to [move your StaffHub teams to Microsoft Teams](move-staffhub-teams-to-shifts-in-teams.md).</span></span> <span data-ttu-id="dcea3-112">レポートからわかりますに含める、通信の際に、スイッチ StaffHub からのチームにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="dcea3-112">From the report, you'll know who you need to include in your communications when you make the switch from StaffHub to Teams.</span></span>

<span data-ttu-id="dcea3-113">Azure AD のプレミアムに、この資料の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dcea3-113">You need to have Azure AD Premium to perform the steps in this article.</span></span>

1. <span data-ttu-id="dcea3-114">Azure ポータルにサインインします。</span><span class="sxs-lookup"><span data-stu-id="dcea3-114">Sign in to the Azure portal.</span></span>
2. <span data-ttu-id="dcea3-115">左側のウィンドウでは、 **Azure Active Directory**リソースをクリックします。</span><span class="sxs-lookup"><span data-stu-id="dcea3-115">In the left pane, click the **Azure Active Directory** resource.</span></span>
3. <span data-ttu-id="dcea3-116">**監視**では、[**サインイン**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dcea3-116">Under **Monitoring**, click **Sign-ins**.</span></span>
4. <span data-ttu-id="dcea3-117">**アプリケーション**では、下には、**マイクロソフトの StaffHub**を入力します。</span><span class="sxs-lookup"><span data-stu-id="dcea3-117">Under **Application**, type **Microsoft StaffHub**.</span></span>
5. <span data-ttu-id="dcea3-118">レポートに使用する日付範囲を設定し、[**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dcea3-118">Set the date range that you want for the report, and then click **Apply**.</span></span> 

    ![スクリーン ショット Azure ポータルで作業中の StaffHub の使用状況を表示するレポートを実行する方法について手順を表示](../../media/staffhub-active-usage-report.png)

## <a name="related-topics"></a><span data-ttu-id="dcea3-120">関連トピック</span><span class="sxs-lookup"><span data-stu-id="dcea3-120">Related topics</span></span>

- [<span data-ttu-id="dcea3-121">マイクロソフト チームの変化に、マイクロソフトの StaffHub チームを移動します。</span><span class="sxs-lookup"><span data-stu-id="dcea3-121">Move your Microsoft StaffHub teams to Shifts in Microsoft Teams</span></span>](move-staffhub-teams-to-shifts-in-teams.md)
