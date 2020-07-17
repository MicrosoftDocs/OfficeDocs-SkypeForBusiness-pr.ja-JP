---
title: Microsoft Teams の通話分析を設定する
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, vkorlep
ms.topic: article
ms.assetid: fbf7247a-84ae-46cc-9204-2c45b1c734cd
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Reporting
description: Microsoft Teams の通話品質の問題を特定してトラブルシューティングするために、ユーザーごとの通話分析をセットアップします。
ms.openlocfilehash: 233d91a60ea783238e10ed1baa02334494ef6e08
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085313"
---
# <a name="set-up-call-analytics-for-microsoft-teams"></a><span data-ttu-id="0d552-103">Microsoft Teams の通話分析を設定する</span><span class="sxs-lookup"><span data-stu-id="0d552-103">Set up call analytics for Microsoft Teams</span></span>

<span data-ttu-id="0d552-104">Microsoft Teams の管理者は、ユーザーごとの通話分析を使用して、**個々のユーザー**に対するチームの通話品質と接続の問題のトラブルシューティングを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="0d552-104">As a Microsoft Teams admin, you can use per-user call analytics to troubleshoot Teams call quality and connection problems for **individual users**.</span></span> <span data-ttu-id="0d552-105">通話分析を最大限に活用するには、次のように設定します。</span><span class="sxs-lookup"><span data-stu-id="0d552-105">To take full advantage of call analytics, set up the following:</span></span>
  
- <span data-ttu-id="0d552-106">特別なサポートロールを、ヘルプデスクエージェントなどのユーザーに割り当てて、ユーザーに対して通話分析を表示できるようにします。</span><span class="sxs-lookup"><span data-stu-id="0d552-106">Assign specialized support roles to people, such as helpdesk agents, to let them view call analytics for users.</span></span> <span data-ttu-id="0d552-107">これらのサポートロールは、Teams 管理センターの残りの部分にはアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="0d552-107">These support roles can't access the rest of the Teams admin center.</span></span> 
    
- <span data-ttu-id="0d552-108">.Tsv または .csv データファイルをアップロードして、建物、サイト、テナントの情報をユーザーごとの通話分析に追加します。</span><span class="sxs-lookup"><span data-stu-id="0d552-108">Add building, site, and tenant information to per-user call analytics by uploading a .tsv or .csv data file.</span></span>
    
<span data-ttu-id="0d552-109">ユーザーごとの通話分析の使用を開始する準備ができたら、「[ユーザーごとの通話分析を使用して通話品質の低下を解決する」を](use-call-analytics-to-troubleshoot-poor-call-quality.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="0d552-109">When you're ready to start using per-user call analytics, read [Use per-user call analytics to troubleshoot poor call quality](use-call-analytics-to-troubleshoot-poor-call-quality.md).</span></span>
  
## <a name="give-permission-to-support-and-helpdesk-staff"></a><span data-ttu-id="0d552-110">サポートおよびヘルプデスクスタッフへのアクセス許可を付与する</span><span class="sxs-lookup"><span data-stu-id="0d552-110">Give permission to support and helpdesk staff</span></span>

<span data-ttu-id="0d552-111">Teams の管理者は、すべてのユーザーについて分析情報を取得するための完全なアクセス権を持っています。</span><span class="sxs-lookup"><span data-stu-id="0d552-111">As the Teams admin, you have full access to call analytics information for all users.</span></span> <span data-ttu-id="0d552-112">ユーザーがユーザーごとの通話分析にアクセスできるように、チーム管理センターの他の部分にはアクセスできないようにするために、ユーザーが1人ずつの通話分析にも割り当てることができる特別な Azure Active Directory ロールを作成しました。</span><span class="sxs-lookup"><span data-stu-id="0d552-112">We've created some specialized Azure Active Directory roles that you can assign to support staff and helpdesk agents so they can also access per-user call analytics (without having access to the rest of the Teams admin center).</span></span> <span data-ttu-id="0d552-113">ユーザーごとの通話分析 (Tier 1 サポート) の制限されたビューが必要なユーザーに**チーム通信のサポートスペシャリスト**の役割を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="0d552-113">Assign the **Teams communications support specialist** role to users who should have a limited view of per-user call analytics (Tier 1 support).</span></span> <span data-ttu-id="0d552-114">ユーザー単位の通話分析 (Tier 2 サポート) へのフルアクセスが必要なユーザーに、 **Teams 通信サポートエンジニア**の役割を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="0d552-114">Assign the **Teams communications support engineer** role to users who need full access to per-user call analytics (Tier 2 support).</span></span> <span data-ttu-id="0d552-115">どちらのロールでも、Teams 管理センターの残りの部分にはアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="0d552-115">Neither role has access to the rest of the Teams admin center.</span></span>

<span data-ttu-id="0d552-116">これらの各ロールの概要については、「[各チームでサポート](use-call-analytics-to-troubleshoot-poor-call-quality.md#what-does-each-teams-support-role-do)される役割」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0d552-116">To learn what each of these roles does, read [What does each Teams Support role do](use-call-analytics-to-troubleshoot-poor-call-quality.md#what-does-each-teams-support-role-do)?</span></span>

<span data-ttu-id="0d552-117">Teams の管理者ロールの詳細については、「チーム管理[者ロールを使用してチームを管理する](using-admin-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0d552-117">For more information about Teams admin roles, see [Use Teams admin roles to manage Teams](using-admin-roles.md).</span></span> <span data-ttu-id="0d552-118">Azure Active Directory に管理者ロールを割り当てる方法については、「 [Azure Active directory でロールを表示して割り当てる](https://docs.microsoft.com/Azure/active-directory/users-groups-roles/directory-manage-roles-portal)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0d552-118">To learn how to assign admin roles in Azure Active Directory, see [View and assign roles in Azure Active Directory](https://docs.microsoft.com/Azure/active-directory/users-groups-roles/directory-manage-roles-portal).</span></span>

<span data-ttu-id="0d552-119">Azure Active Directory に管理者ロールを割り当てる方法については、「 [Azure Active directory での役割の表示と割り当て](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0d552-119">To learn how to assign administrative roles in Azure Active Directory, see [View and assign roles in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal).</span></span>

## <a name="upload-a-tsv-or-csv-file-to-add-building-site-and-tenant-information"></a><span data-ttu-id="0d552-120">.Tsv または .csv ファイルをアップロードして、建物、サイト、テナントの情報を追加する</span><span class="sxs-lookup"><span data-stu-id="0d552-120">Upload a .tsv or .csv file to add building, site, and tenant information</span></span>

<span data-ttu-id="0d552-121">.Csv または .tsv ファイルをアップロードすることによって、建物、サイト、テナントの情報をユーザーごとの呼び出し分析に追加することができます。</span><span class="sxs-lookup"><span data-stu-id="0d552-121">You can add building, site, and tenant information to per-user call analytics by uploading a .csv or .tsv file.</span></span> <span data-ttu-id="0d552-122">すべての情報を使って、通話分析で IP アドレスを物理的な場所に対応付けることができます。</span><span class="sxs-lookup"><span data-stu-id="0d552-122">With all this information, call analytics can map IP addresses to physical locations.</span></span> <span data-ttu-id="0d552-123">管理者およびヘルプデスクエージェントは、この情報を使って、通話の問題に関する傾向を見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="0d552-123">Admins and helpdesk agents can use this information to help spot trends in call problems.</span></span> <span data-ttu-id="0d552-124">たとえば、同じ建物のユーザーが同様の通話品質の問題を抱えているのはなぜですか?</span><span class="sxs-lookup"><span data-stu-id="0d552-124">For example, why are users in the same building having similar call quality problems?</span></span> 

<span data-ttu-id="0d552-125">チームまたは Skype for business の管理者である場合は、Teams または Skype for Business 通話品質ダッシュボード (CQD) から既存のテナントと建物データファイルを使用できます。</span><span class="sxs-lookup"><span data-stu-id="0d552-125">If you're a Teams or Skype for Business admin, you can use an existing tenant and building data file from the Teams or Skype for Business Call Quality Dashboard (CQD).</span></span> <span data-ttu-id="0d552-126">まず、CQD からファイルをダウンロードしてから、通話分析にアップロードします。</span><span class="sxs-lookup"><span data-stu-id="0d552-126">First, you download the file from CQD, then upload it to call analytics.</span></span> 

- <span data-ttu-id="0d552-127">既存のデータファイルをダウンロードするには、 **Microsoft Teams 管理センター**の  >  **通話品質ダッシュボード**  >  **で今すぐアップロード**します。</span><span class="sxs-lookup"><span data-stu-id="0d552-127">To download an existing data file, go to **Microsoft Teams admin center** > **Call Quality Dashboard** > **Upload now**.</span></span> <span data-ttu-id="0d552-128">[**マイアップロード**] ボックスの一覧で、目的のファイルの横にある [**ダウンロード**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0d552-128">In the **My uploads** list, click **Download** next to the file you want.</span></span> 

- <span data-ttu-id="0d552-129">新しいファイルをアップロードするには、 **Microsoft Teams 管理センター**の場所に移動し、  >  **Locations**[**場所データのアップロード**] または [**場所のデータの置き換え**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0d552-129">To upload the new file, go to **Microsoft Teams admin center** > **Locations**, and then select **Upload location data** or **Replace location data**.</span></span>
  
<span data-ttu-id="0d552-130">.Tsv または .csv ファイルを最初から作成する場合は、「[テナントと建物データをアップロード](CQD-upload-tenant-building-data.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0d552-130">If you're creating the .tsv or .csv file from scratch, see [Upload tenant and building data](CQD-upload-tenant-building-data.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="0d552-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="0d552-131">Related topics</span></span>

[<span data-ttu-id="0d552-132">ユーザーごとの通話分析を使用して、低品質の通話品質をトラブルシューティングする</span><span class="sxs-lookup"><span data-stu-id="0d552-132">Use per-user call analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="0d552-133">チームのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="0d552-133">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
