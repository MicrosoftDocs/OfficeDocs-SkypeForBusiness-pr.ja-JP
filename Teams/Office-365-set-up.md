---
title: "Office 365 を使用する組織で Microsoft Teams をセットアップする"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.reviewer: ritikag
description: "Office 365 を使用する組織で Microsoft Teams をセットアップする方法について説明します。"
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 486fe4834678299896ab81ad7de8202d0d873b8c
ms.sourcegitcommit: 4b69ae91de3f82912eda3513cec65ae12e1ce2b2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2018
---
<a name="set-up-microsoft-teams-in-your-office-365-organization"></a><span data-ttu-id="1a7d4-103">Office 365 を使用する組織で Microsoft Teams をセットアップする</span><span class="sxs-lookup"><span data-stu-id="1a7d4-103">Set up Microsoft Teams in your Office 365 organization</span></span>
======================================================

<span data-ttu-id="1a7d4-104">既定では、Teams はすべての組織でオンになります。</span><span class="sxs-lookup"><span data-stu-id="1a7d4-104">By default, Teams is turned on for all organizations.</span></span> <span data-ttu-id="1a7d4-105">プレビュー期間において Teams を使用した場合、Teams プレビューの間に設定したものと同じ設定がそのまま維持されます。</span><span class="sxs-lookup"><span data-stu-id="1a7d4-105">If you used Teams during the preview period, the setting stays the same as what you set during your Teams preview.</span></span>


<span data-ttu-id="1a7d4-p102">組織の管理者は、ユーザー ライセンスを割り当てることで Teams への個々のアクセスを制御できます。さらに、Teams で使用できるコンテンツ ソースを許可または禁止できます。詳しくは、「[Microsoft Teams の管理者設定](https://support.office.com/article/3966a3f5-7e0f-4ea9-a402-41888f455ba2)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1a7d4-p102">As an administrator for your organization, you can assign user licenses to control individual access to Teams, and you can allow or block what content sources can be used in Teams. See [Administrator settings for Microsoft Teams](https://support.office.com/article/3966a3f5-7e0f-4ea9-a402-41888f455ba2) for more information.</span></span>

<span data-ttu-id="1a7d4-108">個別のライセンスを管理する方法については、「[Microsoft Teams 用の Office 365 ライセンス](Office-365-licensing.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1a7d4-108">To learn more about managing individual licenses, read [Office 365 licensing for Microsoft Teams](Office-365-licensing.md).</span></span>


## <a name="turn-teams-on-or-off-for-your-entire-organization"></a><span data-ttu-id="1a7d4-109">組織全体に対して Teams をオンまたはオフにする</span><span class="sxs-lookup"><span data-stu-id="1a7d4-109">Turn Teams on or off for your entire organization</span></span>


1.  <span data-ttu-id="1a7d4-110">グローバル管理者の権限を持つアカウントで [Office 365 管理センター](https://go.microsoft.com/fwlink/?linkid=854614)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="1a7d4-110">Sign in to the [Office 365 Admin center](https://go.microsoft.com/fwlink/?linkid=854614) with an account that has Global Administrator privileges.</span></span>

2.  <span data-ttu-id="1a7d4-111">[**設定**]  >  [**サービスとアドイン**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="1a7d4-111">Go to **Settings** > **Services & add-ins**.</span></span>

    ![<span data-ttu-id="1a7d4-112">Office 365 管理センターの、[サービスとアドイン] が選択されている [設定] セクションのスクリーンショット。</span><span class="sxs-lookup"><span data-stu-id="1a7d4-112">Screenshot of the Settings section in the Office 365 admin center with Services & add-ins selected.</span></span> ](media/Set_up_Microsoft_Teams_in_your_Office_365_organization_image1.png)

3.  <span data-ttu-id="1a7d4-113">[サービスとアドイン] ページで **[Microsoft Teams]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1a7d4-113">On the Services & add-ins page, click **Microsoft Teams**.</span></span>

    ![[Microsoft Teams] が選択されている [サービスとアドイン] ページのスクリーンショット。](media/Set_up_Microsoft_Teams_in_your_Office_365_organization_image2.png)

4.  <span data-ttu-id="1a7d4-115">組織に対して Teams を有効にするには、ライセンス選択ウィンドウで各ライセンスを選択してからトグルを [**オン**] に設定して [**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1a7d4-115">To turn on Teams for the organization use the license picker and select each license then set the toggle to **On** and then click **Save**.</span></span>

    ![トグルがオンに設定されて Microsoft Teams が有効になっていることを示す Microsoft Teams の設定ページのスクリーンショット。](media/Services-and-addins-control-Microsoft-Teams.PNG)


> [!NOTE]
> <span data-ttu-id="1a7d4-117">Teams のオン/オフの状態に関するテナント レベルの制御は一時的なもので、その後のある時点で削除されます。</span><span class="sxs-lookup"><span data-stu-id="1a7d4-117">Tenant-level control of the on/off status for Teams is temporary and will be removed at some point in the future.</span></span> <span data-ttu-id="1a7d4-118">その時点以降、Teams へのアクセスはユーザー レベルのライセンスを介してのみ制御されます。</span><span class="sxs-lookup"><span data-stu-id="1a7d4-118">At that time, access to Teams will be controlled via user-level licensing only.</span></span> 