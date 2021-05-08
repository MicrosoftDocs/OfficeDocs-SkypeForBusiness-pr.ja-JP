---
title: ユーザーの通話分析を設定Microsoft Teams
ms.author: serdars
author: SerdarSoysal
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
description: ユーザーごとの通話分析を設定して、通話品質の問題を特定Microsoft Teamsトラブルシューティングします。
ms.openlocfilehash: 209fcad851f5ba7b0183a9988372e249f99cc4fd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117135"
---
# <a name="set-up-call-analytics-for-microsoft-teams"></a><span data-ttu-id="3f78c-103">ユーザーの通話分析を設定Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3f78c-103">Set up call analytics for Microsoft Teams</span></span>

<span data-ttu-id="3f78c-104">管理者Microsoft Teams、ユーザーごとの呼び出し分析を使用して、個々のユーザーの通話品質Teams接続に関する問題のトラブルシューティング **を行います**。</span><span class="sxs-lookup"><span data-stu-id="3f78c-104">As a Microsoft Teams admin, you can use per-user call analytics to troubleshoot Teams call quality and connection problems for **individual users**.</span></span> <span data-ttu-id="3f78c-105">通話分析をフルに活用するには、次の設定を行います。</span><span class="sxs-lookup"><span data-stu-id="3f78c-105">To take full advantage of call analytics, set up the following:</span></span>
  
- <span data-ttu-id="3f78c-106">ヘルプデスク エージェントなどのユーザーに特殊なサポート ロールを割り当て、ユーザーの通話分析を表示します。</span><span class="sxs-lookup"><span data-stu-id="3f78c-106">Assign specialized support roles to people, such as helpdesk agents, to let them view call analytics for users.</span></span> <span data-ttu-id="3f78c-107">これらのサポート ロールは、管理センターの残りのTeamsアクセスできない。</span><span class="sxs-lookup"><span data-stu-id="3f78c-107">These support roles can't access the rest of the Teams admin center.</span></span> 
    
- <span data-ttu-id="3f78c-108">.tsv または .csv データ ファイルをアップロードして、ビル、サイト、テナントの情報をユーザーごとの呼び出し分析に追加します。</span><span class="sxs-lookup"><span data-stu-id="3f78c-108">Add building, site, and tenant information to per-user call analytics by uploading a .tsv or .csv data file.</span></span>
    
<span data-ttu-id="3f78c-109">ユーザーごとの呼び出し分析の使用を開始する準備ができたら、「ユーザーごとの通話分析を使用して低品質の通話のトラブルシューティングを行う」 [を参照してください](use-call-analytics-to-troubleshoot-poor-call-quality.md)。</span><span class="sxs-lookup"><span data-stu-id="3f78c-109">When you're ready to start using per-user call analytics, read [Use per-user call analytics to troubleshoot poor call quality](use-call-analytics-to-troubleshoot-poor-call-quality.md).</span></span>
  
## <a name="give-permission-to-support-and-helpdesk-staff"></a><span data-ttu-id="3f78c-110">サポートとヘルプデスクのスタッフにアクセス許可を付与する</span><span class="sxs-lookup"><span data-stu-id="3f78c-110">Give permission to support and helpdesk staff</span></span>

<span data-ttu-id="3f78c-111">管理者はTeams、すべてのユーザーの分析情報を呼び出すフル アクセス権を持っています。</span><span class="sxs-lookup"><span data-stu-id="3f78c-111">As the Teams admin, you have full access to call analytics information for all users.</span></span> <span data-ttu-id="3f78c-112">サポート スタッフおよびヘルプデスク エージェントに割り当て可能な特殊な Azure Active Directory ロールを作成しました。このロールは、ユーザーごとの通話分析にもアクセスできます (Teams 管理センターの他の部分にアクセスすることはできません)。</span><span class="sxs-lookup"><span data-stu-id="3f78c-112">We've created some specialized Azure Active Directory roles that you can assign to support staff and helpdesk agents so they can also access per-user call analytics (without having access to the rest of the Teams admin center).</span></span> <span data-ttu-id="3f78c-113">ユーザーごとの **通話Teamsビュー** を限定する必要があるユーザーに、コミュニケーション サポート スペシャリスト ロールを割り当てる (階層 1 のサポート)。</span><span class="sxs-lookup"><span data-stu-id="3f78c-113">Assign the **Teams communications support specialist** role to users who should have a limited view of per-user call analytics (Tier 1 support).</span></span> <span data-ttu-id="3f78c-114">ユーザーごとの通話 **Teamsフル** アクセスが必要なユーザーに、コミュニケーション サポート エンジニア ロールを割り当てる (階層 2 のサポート)。</span><span class="sxs-lookup"><span data-stu-id="3f78c-114">Assign the **Teams communications support engineer** role to users who need full access to per-user call analytics (Tier 2 support).</span></span> <span data-ttu-id="3f78c-115">どちらのロールも、管理センターの他のTeamsアクセス権を持つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f78c-115">Neither role has access to the rest of the Teams admin center.</span></span>

<span data-ttu-id="3f78c-116">これらの各ロールについて詳しくは、「各ロールのサポート ロール[Teamsについて」をご覧ください](use-call-analytics-to-troubleshoot-poor-call-quality.md#what-does-each-teams-support-role-do)。</span><span class="sxs-lookup"><span data-stu-id="3f78c-116">To learn what each of these roles does, read [What does each Teams Support role do](use-call-analytics-to-troubleshoot-poor-call-quality.md#what-does-each-teams-support-role-do)?</span></span>

<span data-ttu-id="3f78c-117">管理者ロールの詳細についてはTeams管理者ロールを使用[した](using-admin-roles.md)管理Teamsを参照Teams。</span><span class="sxs-lookup"><span data-stu-id="3f78c-117">For more information about Teams admin roles, see [Use Teams admin roles to manage Teams](using-admin-roles.md).</span></span> <span data-ttu-id="3f78c-118">Azure Active Directory で管理者ロールを割り当てる方法については、「Azure Active Directory でロールを表示して[割り当てる」を参照してください](/Azure/active-directory/users-groups-roles/directory-manage-roles-portal)。</span><span class="sxs-lookup"><span data-stu-id="3f78c-118">To learn how to assign admin roles in Azure Active Directory, see [View and assign roles in Azure Active Directory](/Azure/active-directory/users-groups-roles/directory-manage-roles-portal).</span></span>

<span data-ttu-id="3f78c-119">管理ロールを管理ロールに割り当てる方法については、「Azure Active Directory でロールを表示して割り当[てる」をAzure Active Directory。](/azure/active-directory/users-groups-roles/directory-manage-roles-portal)</span><span class="sxs-lookup"><span data-stu-id="3f78c-119">To learn how to assign administrative roles in Azure Active Directory, see [View and assign roles in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-manage-roles-portal).</span></span>

## <a name="upload-a-tsv-or-csv-file-to-add-building-site-and-tenant-information"></a><span data-ttu-id="3f78c-120">アップロード.tsv または .csv ファイルを作成して、ビル、サイト、テナントの情報を追加します。</span><span class="sxs-lookup"><span data-stu-id="3f78c-120">Upload a .tsv or .csv file to add building, site, and tenant information</span></span>

<span data-ttu-id="3f78c-121">ユーザーごとの呼び出し分析に建物、サイト、テナントの情報を追加するには、.csv または .tsv ファイルをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="3f78c-121">You can add building, site, and tenant information to per-user call analytics by uploading a .csv or .tsv file.</span></span> <span data-ttu-id="3f78c-122">このすべての情報により、通話分析は IP アドレスを物理的な場所にマップできます。</span><span class="sxs-lookup"><span data-stu-id="3f78c-122">With all this information, call analytics can map IP addresses to physical locations.</span></span> <span data-ttu-id="3f78c-123">管理者とヘルプデスク エージェントは、この情報を使用して通話の問題の傾向を特定できます。</span><span class="sxs-lookup"><span data-stu-id="3f78c-123">Admins and helpdesk agents can use this information to help spot trends in call problems.</span></span> <span data-ttu-id="3f78c-124">たとえば、同じビル内のユーザーが同様の通話品質の問題を抱えている理由は何ですか。</span><span class="sxs-lookup"><span data-stu-id="3f78c-124">For example, why are users in the same building having similar call quality problems?</span></span> 

<span data-ttu-id="3f78c-125">Teams または Skype for Business 管理者の場合は、既存のテナントを使用し、Teams または Skype for Business 通話品質ダッシュボード (CQD) からデータ ファイルを構築できます。</span><span class="sxs-lookup"><span data-stu-id="3f78c-125">If you're a Teams or Skype for Business admin, you can use an existing tenant and building data file from the Teams or Skype for Business Call Quality Dashboard (CQD).</span></span> <span data-ttu-id="3f78c-126">最初に、CQD からファイルをダウンロードし、それをアップロードして分析を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="3f78c-126">First, you download the file from CQD, then upload it to call analytics.</span></span> 

- <span data-ttu-id="3f78c-127">既存のデータ ファイルをダウンロードするには、管理センターの [通話品質ダッシュボード] **Microsoft Teamsに移動** アップロード  >    >  **します**。</span><span class="sxs-lookup"><span data-stu-id="3f78c-127">To download an existing data file, go to **Microsoft Teams admin center** > **Call Quality Dashboard** > **Upload now**.</span></span> <span data-ttu-id="3f78c-128">[マイ **アップロード] の一覧** で、必要な **ファイルの** 横にある [ダウンロード] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f78c-128">In the **My uploads** list, click **Download** next to the file you want.</span></span> 

- <span data-ttu-id="3f78c-129">新しいファイルをアップロードするには、[管理センターの場所] Microsoft Teamsに移動し、[場所データ] または [場所アップロード置き換える]  >  **を選択します**。 </span><span class="sxs-lookup"><span data-stu-id="3f78c-129">To upload the new file, go to **Microsoft Teams admin center** > **Locations**, and then select **Upload location data** or **Replace location data**.</span></span>
  
<span data-ttu-id="3f78c-130">.tsv または .csv ファイルを最初から作成する場合は、テナントのアップロードデータの構築に関する[ページを参照してください](CQD-upload-tenant-building-data.md)。</span><span class="sxs-lookup"><span data-stu-id="3f78c-130">If you're creating the .tsv or .csv file from scratch, see [Upload tenant and building data](CQD-upload-tenant-building-data.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="3f78c-131">関連トピック</span><span class="sxs-lookup"><span data-stu-id="3f78c-131">Related topics</span></span>

[<span data-ttu-id="3f78c-132">ユーザーごとの通話分析を使用して低品質の通話のトラブルシューティングを行う</span><span class="sxs-lookup"><span data-stu-id="3f78c-132">Use per-user call analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="3f78c-133">Teams のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="3f78c-133">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)