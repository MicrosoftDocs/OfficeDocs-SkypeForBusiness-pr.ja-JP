---
title: レポートを実行してアクティブな StaffHub の利用状況を表示する
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.date: 05/10/2019
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: レポートを実行して、組織内のアクティブな StaffHub ユーザーの一覧を取得する方法について説明します。
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 59931183cadec09b2fc26a55cf7e284f51198efc
ms.sourcegitcommit: b5949233f8080a6cf0edb4b5e27272214feb1c22
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "34548208"
---
# <a name="run-a-report-to-show-active-staffhub-usage"></a><span data-ttu-id="9f64f-103">レポートを実行してアクティブな StaffHub の利用状況を表示する</span><span class="sxs-lookup"><span data-stu-id="9f64f-103">Run a report to show active StaffHub usage</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9f64f-104">2019 年 10 月 1 日より、Microsoft StaffHub が廃止されます。</span><span class="sxs-lookup"><span data-stu-id="9f64f-104">Effective October 1, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="9f64f-105">Microsoft Teams で StaffHub 機能を構築しています。</span><span class="sxs-lookup"><span data-stu-id="9f64f-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="9f64f-106">現在、チームには、スケジュール管理のためのシフトアプリが含まれており、その他の機能も時間の経過と共にロールアウトされます。</span><span class="sxs-lookup"><span data-stu-id="9f64f-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="9f64f-107">2019年10月1日の StaffHub はすべてのユーザーに対して機能しなくなります。</span><span class="sxs-lookup"><span data-stu-id="9f64f-107">StaffHub will stop working for all users on October 1, 2019.</span></span> <span data-ttu-id="9f64f-108">StaffHub を開こうとしたユーザーには、チームをダウンロードするように指示するメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9f64f-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="9f64f-109">詳細については、「[Microsoft StaffHub の廃止](microsoft-staffhub-to-be-retired.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9f64f-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>  

<span data-ttu-id="9f64f-110">この記事の手順を使用してレポートを実行し、組織内のアクティブな StaffHub ユーザーの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="9f64f-110">Use the steps in this article to run a report to get a list of active StaffHub users in your organization.</span></span> <span data-ttu-id="9f64f-111">この情報は[、StaffHub teams を Microsoft teams に移行](move-staffhub-teams-to-shifts-in-teams.md)するときに役立つ場合があります。</span><span class="sxs-lookup"><span data-stu-id="9f64f-111">This information may come in handy when you prepare to [move your StaffHub teams to Microsoft Teams](move-staffhub-teams-to-shifts-in-teams.md).</span></span> <span data-ttu-id="9f64f-112">このレポートでは、StaffHub から Teams への切り替えを行うときに、通信に含める必要があるユーザーを確認できます。</span><span class="sxs-lookup"><span data-stu-id="9f64f-112">From the report, you'll know who you need to include in your communications when you make the switch from StaffHub to Teams.</span></span>

<span data-ttu-id="9f64f-113">この記事の手順を実行するには、Azure AD Premium が必要です。</span><span class="sxs-lookup"><span data-stu-id="9f64f-113">You need to have Azure AD Premium to perform the steps in this article.</span></span>

1. <span data-ttu-id="9f64f-114">Azure ポータルにサインインします。</span><span class="sxs-lookup"><span data-stu-id="9f64f-114">Sign in to the Azure portal.</span></span>
2. <span data-ttu-id="9f64f-115">左側のウィンドウで、 **Azure Active Directory**リソースをクリックします。</span><span class="sxs-lookup"><span data-stu-id="9f64f-115">In the left pane, click the **Azure Active Directory** resource.</span></span>
3. <span data-ttu-id="9f64f-116">[**監視**] で [**サインイン**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9f64f-116">Under **Monitoring**, click **Sign-ins**.</span></span>
4. <span data-ttu-id="9f64f-117">[**アプリケーション**] の下に「 **Microsoft StaffHub**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="9f64f-117">Under **Application**, type **Microsoft StaffHub**.</span></span>
5. <span data-ttu-id="9f64f-118">レポートに必要な日付の範囲を設定して、[**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9f64f-118">Set the date range that you want for the report, and then click **Apply**.</span></span> 

    ![アクティブな StaffHub の利用状況を表示する手順を示すスクリーンショット](../../media/staffhub-active-usage-report.png)

## <a name="related-topics"></a><span data-ttu-id="9f64f-120">関連トピック</span><span class="sxs-lookup"><span data-stu-id="9f64f-120">Related topics</span></span>

- [<span data-ttu-id="9f64f-121">Microsoft Teams で Microsoft StaffHub teams をシフトに移行する</span><span class="sxs-lookup"><span data-stu-id="9f64f-121">Move your Microsoft StaffHub teams to Shifts in Microsoft Teams</span></span>](move-staffhub-teams-to-shifts-in-teams.md)
