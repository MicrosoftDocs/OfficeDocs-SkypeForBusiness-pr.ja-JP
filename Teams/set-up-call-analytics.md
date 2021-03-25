---
title: Microsoft Teams の通話分析を設定する
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
description: Microsoft Teams の通話品質の問題を特定してトラブルシューティングするために、ユーザーごとの通話分析を設定します。
ms.openlocfilehash: 209fcad851f5ba7b0183a9988372e249f99cc4fd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117135"
---
# <a name="set-up-call-analytics-for-microsoft-teams"></a><span data-ttu-id="d8242-103">Microsoft Teams の通話分析を設定する</span><span class="sxs-lookup"><span data-stu-id="d8242-103">Set up call analytics for Microsoft Teams</span></span>

<span data-ttu-id="d8242-104">Microsoft Teams 管理者は、ユーザーごとの通話分析を使用して、個々のユーザーの Teams の通話品質と接続の問題を **トラブルシューティングできます**。</span><span class="sxs-lookup"><span data-stu-id="d8242-104">As a Microsoft Teams admin, you can use per-user call analytics to troubleshoot Teams call quality and connection problems for **individual users**.</span></span> <span data-ttu-id="d8242-105">通話分析をフルに活用するには、次の設定を行います。</span><span class="sxs-lookup"><span data-stu-id="d8242-105">To take full advantage of call analytics, set up the following:</span></span>
  
- <span data-ttu-id="d8242-106">ヘルプデスク エージェントなどの特殊なサポート ロールをユーザーに割り当て、ユーザーの通話分析を表示します。</span><span class="sxs-lookup"><span data-stu-id="d8242-106">Assign specialized support roles to people, such as helpdesk agents, to let them view call analytics for users.</span></span> <span data-ttu-id="d8242-107">これらのサポート ロールは、Teams 管理センターの他の部分にはアクセスできない。</span><span class="sxs-lookup"><span data-stu-id="d8242-107">These support roles can't access the rest of the Teams admin center.</span></span> 
    
- <span data-ttu-id="d8242-108">.tsv または .csv データ ファイルをアップロードして、ユーザーごとの通話分析に建物、サイト、テナントの情報を追加します。</span><span class="sxs-lookup"><span data-stu-id="d8242-108">Add building, site, and tenant information to per-user call analytics by uploading a .tsv or .csv data file.</span></span>
    
<span data-ttu-id="d8242-109">ユーザーごとの通話分析の使用を開始する準備ができたら、「ユーザーごとの通話分析を使用して低品質の通話のトラブルシューティングを行う」を参照 [してください](use-call-analytics-to-troubleshoot-poor-call-quality.md)。</span><span class="sxs-lookup"><span data-stu-id="d8242-109">When you're ready to start using per-user call analytics, read [Use per-user call analytics to troubleshoot poor call quality](use-call-analytics-to-troubleshoot-poor-call-quality.md).</span></span>
  
## <a name="give-permission-to-support-and-helpdesk-staff"></a><span data-ttu-id="d8242-110">サポートおよびヘルプデスク スタッフにアクセス許可を付与する</span><span class="sxs-lookup"><span data-stu-id="d8242-110">Give permission to support and helpdesk staff</span></span>

<span data-ttu-id="d8242-111">Teams 管理者は、すべてのユーザーの通話分析情報にフル アクセスできます。</span><span class="sxs-lookup"><span data-stu-id="d8242-111">As the Teams admin, you have full access to call analytics information for all users.</span></span> <span data-ttu-id="d8242-112">サポート スタッフとヘルプデスク エージェントに割り当て、(Teams 管理センターの他の部分にアクセスすることなく) ユーザーごとの通話分析にアクセスできるよう、いくつかの特殊な Azure Active Directory ロールを作成しました。</span><span class="sxs-lookup"><span data-stu-id="d8242-112">We've created some specialized Azure Active Directory roles that you can assign to support staff and helpdesk agents so they can also access per-user call analytics (without having access to the rest of the Teams admin center).</span></span> <span data-ttu-id="d8242-113">ユーザーごとの **通話分析 (** 階層 1 のサポート) のビューを限定する必要があるユーザーに、Teams 通信サポートの専門の役割を割り当てる。</span><span class="sxs-lookup"><span data-stu-id="d8242-113">Assign the **Teams communications support specialist** role to users who should have a limited view of per-user call analytics (Tier 1 support).</span></span> <span data-ttu-id="d8242-114">ユーザーごとの **通話分析 (** 階層 2 のサポート) へのフル アクセスが必要なユーザーに、Teams コミュニケーション サポート エンジニアの役割を割り当てる。</span><span class="sxs-lookup"><span data-stu-id="d8242-114">Assign the **Teams communications support engineer** role to users who need full access to per-user call analytics (Tier 2 support).</span></span> <span data-ttu-id="d8242-115">どちらの役割も、Teams 管理センターの他の部分にアクセス権を持つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8242-115">Neither role has access to the rest of the Teams admin center.</span></span>

<span data-ttu-id="d8242-116">これらの各役割の機能については、「Teams の各サポートの役割について [」を参照してください](use-call-analytics-to-troubleshoot-poor-call-quality.md#what-does-each-teams-support-role-do)。</span><span class="sxs-lookup"><span data-stu-id="d8242-116">To learn what each of these roles does, read [What does each Teams Support role do](use-call-analytics-to-troubleshoot-poor-call-quality.md#what-does-each-teams-support-role-do)?</span></span>

<span data-ttu-id="d8242-117">Teams の管理者ロールの詳細については、「Teams 管理者ロールを使用して Teams を [管理する」を参照してください](using-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="d8242-117">For more information about Teams admin roles, see [Use Teams admin roles to manage Teams](using-admin-roles.md).</span></span> <span data-ttu-id="d8242-118">Azure Active Directory で管理者ロールを割り当てる方法については、「Azure Active Directory でロールを表示して割り当てる [」を参照してください](/Azure/active-directory/users-groups-roles/directory-manage-roles-portal)。</span><span class="sxs-lookup"><span data-stu-id="d8242-118">To learn how to assign admin roles in Azure Active Directory, see [View and assign roles in Azure Active Directory](/Azure/active-directory/users-groups-roles/directory-manage-roles-portal).</span></span>

<span data-ttu-id="d8242-119">Azure Active Directory で管理ロールを割り当てる方法については、「Azure Active Directory でロールを表示および割り当てる [」を参照してください](/azure/active-directory/users-groups-roles/directory-manage-roles-portal)。</span><span class="sxs-lookup"><span data-stu-id="d8242-119">To learn how to assign administrative roles in Azure Active Directory, see [View and assign roles in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-manage-roles-portal).</span></span>

## <a name="upload-a-tsv-or-csv-file-to-add-building-site-and-tenant-information"></a><span data-ttu-id="d8242-120">.tsv または .csv ファイルをアップロードして、建物、サイト、テナント情報を追加する</span><span class="sxs-lookup"><span data-stu-id="d8242-120">Upload a .tsv or .csv file to add building, site, and tenant information</span></span>

<span data-ttu-id="d8242-121">.csv ファイルまたは .tsv ファイルをアップロードすると、ユーザーごとの通話分析に建物、サイト、テナントの情報を追加できます。</span><span class="sxs-lookup"><span data-stu-id="d8242-121">You can add building, site, and tenant information to per-user call analytics by uploading a .csv or .tsv file.</span></span> <span data-ttu-id="d8242-122">これらの情報はすべて、通話分析によって IP アドレスを物理的な場所にマップできます。</span><span class="sxs-lookup"><span data-stu-id="d8242-122">With all this information, call analytics can map IP addresses to physical locations.</span></span> <span data-ttu-id="d8242-123">管理者とヘルプデスク エージェントは、この情報を使用して通話の問題の傾向を把握できます。</span><span class="sxs-lookup"><span data-stu-id="d8242-123">Admins and helpdesk agents can use this information to help spot trends in call problems.</span></span> <span data-ttu-id="d8242-124">たとえば、同じ建物内のユーザーが同様の通話品質の問題を抱えている理由は何ですか?</span><span class="sxs-lookup"><span data-stu-id="d8242-124">For example, why are users in the same building having similar call quality problems?</span></span> 

<span data-ttu-id="d8242-125">Teams または Skype for Business 管理者の場合は、既存のテナントを使用して、Teams または Skype for Business 通話品質ダッシュボード (CQD) からデータ ファイルを作成できます。</span><span class="sxs-lookup"><span data-stu-id="d8242-125">If you're a Teams or Skype for Business admin, you can use an existing tenant and building data file from the Teams or Skype for Business Call Quality Dashboard (CQD).</span></span> <span data-ttu-id="d8242-126">まず、CQD からファイルをダウンロードし、それを通話分析にアップロードします。</span><span class="sxs-lookup"><span data-stu-id="d8242-126">First, you download the file from CQD, then upload it to call analytics.</span></span> 

- <span data-ttu-id="d8242-127">既存のデータ ファイルをダウンロードするには **、Microsoft Teams** 管理センターの [通話品質ダッシュボードのアップロード]  >    >  **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="d8242-127">To download an existing data file, go to **Microsoft Teams admin center** > **Call Quality Dashboard** > **Upload now**.</span></span> <span data-ttu-id="d8242-128">[マイ **アップロード] リストで、** 必要なファイル **の** 横にある [ダウンロード] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d8242-128">In the **My uploads** list, click **Download** next to the file you want.</span></span> 

- <span data-ttu-id="d8242-129">新しいファイルをアップロードするには **、Microsoft Teams** 管理センターの [場所] に移動し、[場所データのアップロード] または [場所データの置き換  >  え]**を選択します**。 </span><span class="sxs-lookup"><span data-stu-id="d8242-129">To upload the new file, go to **Microsoft Teams admin center** > **Locations**, and then select **Upload location data** or **Replace location data**.</span></span>
  
<span data-ttu-id="d8242-130">.tsv または .csv ファイルを最初から作成する場合は、「テナントをアップロードしてデータを作成する [」を参照してください](CQD-upload-tenant-building-data.md)。</span><span class="sxs-lookup"><span data-stu-id="d8242-130">If you're creating the .tsv or .csv file from scratch, see [Upload tenant and building data](CQD-upload-tenant-building-data.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="d8242-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="d8242-131">Related topics</span></span>

[<span data-ttu-id="d8242-132">低品質の通話のトラブルシューティングにユーザーごとの通話分析を使用する</span><span class="sxs-lookup"><span data-stu-id="d8242-132">Use per-user call analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="d8242-133">Teams のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="d8242-133">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)