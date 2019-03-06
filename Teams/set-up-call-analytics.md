---
title: 通話分析をセットアップする
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: fbf7247a-84ae-46cc-9204-2c45b1c734cd
ms.tgt.pltfrm: cloud
ms.service:
- skype-for-business-online
- msteams
ms.collection:
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
search.appverid: MET150
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Reporting
description: 設定し、分析機能の呼び出しを使用して特定し、Skype のビジネスおよびマイクロソフトのチームの通話品質の問題に関するトラブルシューティングを行います。
ms.openlocfilehash: 4d6216fe1771158453ca32bbabfed5fcf9b09156
ms.sourcegitcommit: d90beb625c2d12616fb9aee39b6dd1c2d4c12947
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "30408292"
---
# <a name="set-up-call-analytics"></a><span data-ttu-id="16ec5-103">通話分析をセットアップする</span><span class="sxs-lookup"><span data-stu-id="16ec5-103">Set up Call Analytics</span></span>

<span data-ttu-id="16ec5-104">チームとして、またはオンライン ビジネスの管理の Skype は、分析機能の呼び出しを使用するにはビジネス用の Skype のトラブルシューティングを行うと、マイクロソフトのチームは、品質との接続の問題を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="16ec5-104">As a Teams or Skype for Business Online admin, you can use Call Analytics to troubleshoot Skype for Business and Microsoft Teams call quality and connection problems.</span></span> <span data-ttu-id="16ec5-105">分析機能を呼び出すには、次の機能を設定すると便利です。</span><span class="sxs-lookup"><span data-stu-id="16ec5-105">You may find it useful to set up the following capabilities in Call Analytics:</span></span>
  
- <span data-ttu-id="16ec5-106">その他のスタッフ、ヘルプ デスク担当者など、分析機能の呼び出しを使用してアクセス許可を設定、マイクロソフトのチームの管理センターの残りの部分にアクセスすることができません。</span><span class="sxs-lookup"><span data-stu-id="16ec5-106">Set permissions that let other personnel, such as helpdesk agents, use Call Analytics, but prevent them from accessing the rest of the Microsoft Teams admin center.</span></span> 
    
- <span data-ttu-id="16ec5-107">.Tsv または .csv データ ファイルをアップロードすることで、分析機能の呼び出しを構築、サイト、およびテナントの情報を追加します。</span><span class="sxs-lookup"><span data-stu-id="16ec5-107">Add building, site, and tenant information to Call Analytics by uploading a .tsv or .csv data file.</span></span>
    
<span data-ttu-id="16ec5-108">**呼び出すの分析機能はマイクロソフト チームの管理センターで使用できるようになりました**。</span><span class="sxs-lookup"><span data-stu-id="16ec5-108">**Call Analytics is now available in the Microsoft Teams admin center**.</span></span> <span data-ttu-id="16ec5-109">すべてのコール情報、ユーザーのデータを表示するには、[**呼び出し履歴**] タブを使用します。次のいずれかの方法でユーザーのプロファイル ページで調べることによってこれを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="16ec5-109">To see all the call information and data for a user, use the **Call History** tab. You can do this by looking on the user's profile page by doing one of the following:</span></span>

- <span data-ttu-id="16ec5-110">ダッシュ ボードからユーザーを検索します。</span><span class="sxs-lookup"><span data-stu-id="16ec5-110">Search for the user from the dashboard.</span></span>
  
   ![ダッシュ ボードのユーザー検索のスクリーン ショット](media/set-up-call-analytics-image-1.png)

-  <span data-ttu-id="16ec5-112">左側のナビゲーションで**ユーザー**を選択します。</span><span class="sxs-lookup"><span data-stu-id="16ec5-112">Select **Users** in the left navigation.</span></span>

   ![左側のナビゲーションのスクリーン ショット](media/set-up-call-analytics-image-2.png)
  
## <a name="set-call-analytics-permissions"></a><span data-ttu-id="16ec5-114">分析機能を呼び出すアクセス許可を設定します。</span><span class="sxs-lookup"><span data-stu-id="16ec5-114">Set Call Analytics permissions</span></span>
<a name="BKMK_SetCAPerms"></a>

<span data-ttu-id="16ec5-115">管理者としては、分析機能の呼び出しのすべての機能へのフル アクセスを取得します。</span><span class="sxs-lookup"><span data-stu-id="16ec5-115">As the admin, you get full access to all the features of Call Analytics.</span></span> <span data-ttu-id="16ec5-116">さらに、スタッフをサポートするために Active Directory の Azure ロールを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="16ec5-116">In addition, you can assign Azure Active Directory roles to support staff.</span></span> <span data-ttu-id="16ec5-117">分析機能の呼び出しの制限付きビューを持つユーザーにチームのコミュニケーションのサポート専門家のロールを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="16ec5-117">Assign the Teams communications support specialist role to users who should have a limited view of Call Analytics.</span></span> <span data-ttu-id="16ec5-118">分析機能の呼び出しのすべての機能へのアクセスを必要とするユーザーには、チーム コミュニケーションのサポート エンジニアの役割を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="16ec5-118">Assign the Teams communications support engineer role to users who need access to the full functionality of Call Analytics.</span></span> <span data-ttu-id="16ec5-119">両方のアクセス許可レベルは、マイクロソフトのチームの管理センターの残りの部分へのアクセスを防止します。</span><span class="sxs-lookup"><span data-stu-id="16ec5-119">Both permission levels prevent access to the rest of the Microsoft Teams admin center.</span></span>

> [!NOTE]
> <span data-ttu-id="16ec5-120">通信のサポート ・ スペシャ リストの役割は、第 1 層のサポートに相当と通信のサポート ・ エンジニアの役割は、第 2 層のサポートに相当します。</span><span class="sxs-lookup"><span data-stu-id="16ec5-120">The communications support specialist role is equivalent to tier 1 support and the communications support engineer role is equivalent to tier 2 support.</span></span>

<span data-ttu-id="16ec5-121">チーム管理者の役割の詳細については、[チームを管理する管理者の役割を使用してマイクロソフトのチーム](using-admin-roles.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="16ec5-121">For more information about Teams admin roles, see [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md).</span></span> 
  
<span data-ttu-id="16ec5-122">通信のサポート ・ スペシャ リストは、基本的な通話品質の問題を処理します。</span><span class="sxs-lookup"><span data-stu-id="16ec5-122">Communications support specialists handle basic call-quality problems.</span></span> <span data-ttu-id="16ec5-123">会議に関する問題を調査するありません。</span><span class="sxs-lookup"><span data-stu-id="16ec5-123">They don't investigate issues with meetings.</span></span> <span data-ttu-id="16ec5-124">関連情報を収集し、通信のサポート ・ エンジニアにエスカレーションします。</span><span class="sxs-lookup"><span data-stu-id="16ec5-124">Instead, they collect related information and then escalate to a communications support engineer.</span></span> <span data-ttu-id="16ec5-125">通信のサポート エンジニアは、サポート ・ スペシャ リストの通信から非表示にする詳細な呼び出しのログ内の情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="16ec5-125">Communications support engineers see information in detailed call logs that's hidden from communications support specialists.</span></span> <span data-ttu-id="16ec5-126">次の表は、分析機能の呼び出しを使用するときに、通信のサポートのスペシャ リストとの通信のサポート エンジニアに利用可能な情報の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="16ec5-126">The following table gives an overview of information available to communications support specialists and communications support engineers when they use Call Analytics.</span></span>

|<span data-ttu-id="16ec5-127">**アクティビティ**</span><span class="sxs-lookup"><span data-stu-id="16ec5-127">**Activity**</span></span>|<span data-ttu-id="16ec5-128">**コール分析の情報**</span><span class="sxs-lookup"><span data-stu-id="16ec5-128">**Information in Call Analytics**</span></span>|<span data-ttu-id="16ec5-129">**どのような通信のサポート ・ スペシャ リストが表示されます。**</span><span class="sxs-lookup"><span data-stu-id="16ec5-129">**What the communications support specialist sees**</span></span>|<span data-ttu-id="16ec5-130">**どのような通信のサポート ・ エンジニアが表示されます。**</span><span class="sxs-lookup"><span data-stu-id="16ec5-130">**What the communications support engineer sees**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="16ec5-131">**通話**</span><span class="sxs-lookup"><span data-stu-id="16ec5-131">**Calls**</span></span> <br/> |<span data-ttu-id="16ec5-132">呼び出し元の名前</span><span class="sxs-lookup"><span data-stu-id="16ec5-132">Caller name</span></span>  <br/> |<span data-ttu-id="16ec5-133">エージェントが検索対象となるユーザーの名前のみです。</span><span class="sxs-lookup"><span data-stu-id="16ec5-133">Only the name of the user for whom the agent searched.</span></span>  <br/> |<span data-ttu-id="16ec5-134">ユーザー名です。</span><span class="sxs-lookup"><span data-stu-id="16ec5-134">User name.</span></span>  <br/> |
||<span data-ttu-id="16ec5-135">受取人の名前</span><span class="sxs-lookup"><span data-stu-id="16ec5-135">Recipient name</span></span>  <br/> |<span data-ttu-id="16ec5-136">内部ユーザーまたは外部のユーザーとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="16ec5-136">Shows as Internal User or External User.</span></span>  <br/> |<span data-ttu-id="16ec5-137">受信者の名前です。</span><span class="sxs-lookup"><span data-stu-id="16ec5-137">Recipient name.</span></span>  <br/> |
||<span data-ttu-id="16ec5-138">発信者電話番号</span><span class="sxs-lookup"><span data-stu-id="16ec5-138">Caller phone number</span></span>  <br/> |<span data-ttu-id="16ec5-139">最後の 3 桁の数字以外の電話番号はアスタリスク記号を難読化します。</span><span class="sxs-lookup"><span data-stu-id="16ec5-139">Entire phone number except last three digits are obfuscated with asterisk symbols.</span></span> <span data-ttu-id="16ec5-140">たとえば、15552823。。</span><span class="sxs-lookup"><span data-stu-id="16ec5-140">For example, 15552823\*\*\*.</span></span>  <br/> |<span data-ttu-id="16ec5-141">最後の 3 桁の数字以外の電話番号はアスタリスク記号を難読化します。</span><span class="sxs-lookup"><span data-stu-id="16ec5-141">Entire phone number except last three digits are obfuscated with asterisk symbols.</span></span> <span data-ttu-id="16ec5-142">たとえば、15552823。。</span><span class="sxs-lookup"><span data-stu-id="16ec5-142">For example, 15552823\*\*\*.</span></span>  <br/> |
||<span data-ttu-id="16ec5-143">受信者の電話番号</span><span class="sxs-lookup"><span data-stu-id="16ec5-143">Recipient phone number</span></span>  <br/> |<span data-ttu-id="16ec5-144">最後の 3 桁の数字以外の電話番号はアスタリスク記号を難読化します。</span><span class="sxs-lookup"><span data-stu-id="16ec5-144">Entire phone number except last three digits are obfuscated with asterisk symbols.</span></span> <span data-ttu-id="16ec5-145">たとえば、15552823。。</span><span class="sxs-lookup"><span data-stu-id="16ec5-145">For example, 15552823\*\*\*.</span></span>  <br/> |<span data-ttu-id="16ec5-146">最後の 3 桁の数字以外の電話番号はアスタリスク記号を難読化します。</span><span class="sxs-lookup"><span data-stu-id="16ec5-146">Entire phone number except last three digits are obfuscated with asterisk symbols.</span></span> <span data-ttu-id="16ec5-147">たとえば、15552823。。</span><span class="sxs-lookup"><span data-stu-id="16ec5-147">For example, 15552823\*\*\*.</span></span>  <br/> |
||<span data-ttu-id="16ec5-148">**通話の詳細** > [**詳細**] タブ</span><span class="sxs-lookup"><span data-stu-id="16ec5-148">**Call Details** > **Advanced** tab</span></span> <br/> |<span data-ttu-id="16ec5-149">情報は表示されません。</span><span class="sxs-lookup"><span data-stu-id="16ec5-149">Information not shown.</span></span>  <br/> |<span data-ttu-id="16ec5-150">すべての詳細が表示されます、デバイス名、IP アドレス、サブネットのマッピング、および詳細などです。</span><span class="sxs-lookup"><span data-stu-id="16ec5-150">All details shown, such as device names, IP address, subnet mapping, and more.</span></span>  <br/> |
||<span data-ttu-id="16ec5-151">**通話の詳細** > **詳細** > [**デバッグ**] タブ</span><span class="sxs-lookup"><span data-stu-id="16ec5-151">**Call Details** > **Advanced** > **Debug** tab</span></span> <br/> |<span data-ttu-id="16ec5-152">情報は表示されません。</span><span class="sxs-lookup"><span data-stu-id="16ec5-152">Information not shown.</span></span>  <br/> |<span data-ttu-id="16ec5-153">すべての詳細を示すように、DNS サフィックスであり、SSID などです。</span><span class="sxs-lookup"><span data-stu-id="16ec5-153">All details shown, such as DNS suffix and SSID.</span></span>  <br/> |
|<span data-ttu-id="16ec5-154">**会議**</span><span class="sxs-lookup"><span data-stu-id="16ec5-154">**Meetings**</span></span> <br/> |<span data-ttu-id="16ec5-155">参加者名</span><span class="sxs-lookup"><span data-stu-id="16ec5-155">Participant names</span></span>  <br/> |<span data-ttu-id="16ec5-156">エージェントが検索対象となるユーザーの名前のみです。</span><span class="sxs-lookup"><span data-stu-id="16ec5-156">Only the name of the user for whom the agent searched.</span></span> <span data-ttu-id="16ec5-157">他の参加者は、内部ユーザーと外部ユーザーを識別します。</span><span class="sxs-lookup"><span data-stu-id="16ec5-157">Other participants identified as Internal User or External User.</span></span>  <br/> |<span data-ttu-id="16ec5-158">すべての名前が表示されます。</span><span class="sxs-lookup"><span data-stu-id="16ec5-158">All names shown.</span></span>  <br/> |
||<span data-ttu-id="16ec5-159">参加者数</span><span class="sxs-lookup"><span data-stu-id="16ec5-159">Participant count</span></span>  <br/> |<span data-ttu-id="16ec5-160">参加者の数です。</span><span class="sxs-lookup"><span data-stu-id="16ec5-160">Number of participants.</span></span>  <br/> |<span data-ttu-id="16ec5-161">参加者の数です。</span><span class="sxs-lookup"><span data-stu-id="16ec5-161">Number of participants.</span></span>  <br/> |
||<span data-ttu-id="16ec5-162">セッションの詳細</span><span class="sxs-lookup"><span data-stu-id="16ec5-162">Session details</span></span>  <br/> |<span data-ttu-id="16ec5-163">セッションの詳細が例外を使用して表示します。</span><span class="sxs-lookup"><span data-stu-id="16ec5-163">Session details shown with exceptions.</span></span> <span data-ttu-id="16ec5-164">エージェントが検索対象となるユーザーの名前のみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="16ec5-164">Only the name of the user for whom the agent searched is shown.</span></span> <span data-ttu-id="16ec5-165">他の参加者は、内部ユーザーと外部ユーザーを識別します。</span><span class="sxs-lookup"><span data-stu-id="16ec5-165">Other participants identified as Internal User or External User.</span></span> <span data-ttu-id="16ec5-166">最後のアスタリスク記号を使用して難読化の電話番号の 3 桁の数字です。</span><span class="sxs-lookup"><span data-stu-id="16ec5-166">Last three digits of telephone number obfuscated with asterisk symbols.</span></span>  <br/> |<span data-ttu-id="16ec5-167">セッションの詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="16ec5-167">Session details shown.</span></span> <span data-ttu-id="16ec5-168">ユーザー名およびセッションの詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="16ec5-168">User names and session details shown.</span></span> <span data-ttu-id="16ec5-169">最後のアスタリスク記号を使用して難読化の電話番号の 3 桁の数字です。</span><span class="sxs-lookup"><span data-stu-id="16ec5-169">Last three digits of telephone number obfuscated with asterisk symbols.</span></span>  <br/> |
||||
   
 ### <a name="set-up-permissions-by-assigning-admin-roles"></a><span data-ttu-id="16ec5-170">管理者の役割を割り当てることによってアクセス許可を設定します。</span><span class="sxs-lookup"><span data-stu-id="16ec5-170">Set up permissions by assigning admin roles</span></span>
<span data-ttu-id="16ec5-171"><a name="BKMK_SetUpTier"> </a></span><span class="sxs-lookup"><span data-stu-id="16ec5-171"></span></span>

<span data-ttu-id="16ec5-172">Azure Active Directory で管理役割を割り当てる方法については、 [Azure Active Directory で表示し、割り当てのロール](https://docs.microsoft.com/en-us/azure/active-directory/users-groups-roles/directory-manage-roles-portal)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="16ec5-172">To learn how to assign administrative roles in Azure Active Directory, see [View and assign roles in Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/users-groups-roles/directory-manage-roles-portal).</span></span>

## <a name="upload-a-tsv-or-csv-file-to-add-building-site-and-tenant-information"></a><span data-ttu-id="16ec5-173">サイトの構築を追加し、情報をテナントに .tsv または .csv ファイルをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="16ec5-173">Upload a .tsv or .csv file to add building, site, and tenant information</span></span>
<span data-ttu-id="16ec5-174"><a name="BKMK_UploadFiles"> </a></span><span class="sxs-lookup"><span data-stu-id="16ec5-174"></span></span>

<span data-ttu-id="16ec5-175">.Csv または .tsv ファイルをアップロードすることで、分析機能の呼び出しを構築、サイト、およびテナント情報を追加できます。</span><span class="sxs-lookup"><span data-stu-id="16ec5-175">You can add building, site, and tenant information to Call Analytics by uploading a .csv or .tsv file.</span></span> <span data-ttu-id="16ec5-176">この情報は、分析機能の呼び出しは、物理的な場所に IP アドレスをマップできます。</span><span class="sxs-lookup"><span data-stu-id="16ec5-176">With all this information, Call Analytics can map IP addresses to physical locations.</span></span> <span data-ttu-id="16ec5-177">か、ヘルプデスク エージェントについては、この役に立つの呼び出しに関する問題の傾向を支援します。</span><span class="sxs-lookup"><span data-stu-id="16ec5-177">You or helpdesk agents might find this information useful to help spot trends in call problems.</span></span> <span data-ttu-id="16ec5-178">などの品質の問題を呼び出すのような多くのユーザーが同じ建物ではなぜですか。</span><span class="sxs-lookup"><span data-stu-id="16ec5-178">For example, why are many users in the same building having similar call quality issues?</span></span> 

<span data-ttu-id="16ec5-179">場合は、チームと Skype ビジネス管理者とのビジネス電話品質ダッシュ ボードのチーム & Skype から既存のデータ ファイルを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="16ec5-179">If you're a Teams and Skype for Business admin, you can use an existing data file from the Teams & Skype for Business Call Quality Dashboard.</span></span> <span data-ttu-id="16ec5-180">まず、コール品質のダッシュ ボードからファイルをダウンロードして、分析機能の呼び出しにアップロードします。</span><span class="sxs-lookup"><span data-stu-id="16ec5-180">First, you download the file from Call Quality Dashboard, and then you upload it to Call Analytics.</span></span> 

- <span data-ttu-id="16ec5-181">既存のデータ ファイルをダウンロードするには、**マイクロソフトのチーム管理センター** > **品質のダッシュ ボードを呼び出す** > **今すぐアップロード**します。</span><span class="sxs-lookup"><span data-stu-id="16ec5-181">To download an existing data file, go to **Microsoft Teams admin center** > **Call Quality Dashboard** > **Upload now**.</span></span> <span data-ttu-id="16ec5-182">**[アップロード**] の一覧で目的のファイルの横にある [**ダウンロード**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="16ec5-182">In the **My uploads** list, click **Download** next to the file you want.</span></span>

- <span data-ttu-id="16ec5-183">**マイクロソフトのチーム管理センター**に新しいファイルをアップロードするには、 > **の場所**、および] をクリックし**場所のデータをアップロード**または**場所のデータを置換**します。</span><span class="sxs-lookup"><span data-stu-id="16ec5-183">To upload the new file, go to **Microsoft Teams admin center** > **Locations**, and then select **Upload location data** or **Replace location data**.</span></span>
  
<span data-ttu-id="16ec5-184">.Tsv または .csv ファイルを最初から作成する場合は、[テナントのデータ ファイルの形式とデータ ファイルの構造の構築](turning-on-and-using-call-quality-dashboard.md#BKMKTenantDataFile)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="16ec5-184">If you're creating the .tsv or .csv file from scratch, see [Tenant data file format and Building data file structure](turning-on-and-using-call-quality-dashboard.md#BKMKTenantDataFile).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="16ec5-185">関連トピック</span><span class="sxs-lookup"><span data-stu-id="16ec5-185">Related topics</span></span>
<span data-ttu-id="16ec5-186"><a name="BKMK_UploadFiles"> </a></span><span class="sxs-lookup"><span data-stu-id="16ec5-186"></span></span>

[<span data-ttu-id="16ec5-187">通話分析を使用して低品質の通話をトラブルシューティングする</span><span class="sxs-lookup"><span data-stu-id="16ec5-187">Use Call Analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="16ec5-188">通話分析および通話品質ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="16ec5-188">Call Analytics and Call Quality Dashboard</span></span>](difference-between-call-analytics-and-call-quality-dashboard.md)

  
 
