---
title: 通話分析をセットアップする
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: fbf7247a-84ae-46cc-9204-2c45b1c734cd
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Reporting
description: Skype for Business および Microsoft Teams の通話品質の問題を特定してトラブルシューティングするために通話分析をセットアップして使用します。
ms.openlocfilehash: 7a91bc0d8503d313ae3b3dfa7ddd32b6a8c5207a
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2019
ms.locfileid: "37571251"
---
# <a name="set-up-call-analytics"></a><span data-ttu-id="7e131-103">通話分析をセットアップする</span><span class="sxs-lookup"><span data-stu-id="7e131-103">Set up Call Analytics</span></span>

<span data-ttu-id="7e131-104">チームまたは Skype for Business Online 管理者は、通話分析を使用して、Skype for Business および Microsoft Teams の通話品質と接続の問題のトラブルシューティングを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="7e131-104">As a Teams or Skype for Business Online admin, you can use Call Analytics to troubleshoot Skype for Business and Microsoft Teams call quality and connection problems.</span></span> <span data-ttu-id="7e131-105">通話分析では、次の機能を設定すると便利です。</span><span class="sxs-lookup"><span data-stu-id="7e131-105">You may find it useful to set up the following capabilities in Call Analytics:</span></span>
  
- <span data-ttu-id="7e131-106">ヘルプデスクエージェントなどの他のユーザーが通話分析を使用して、Microsoft Teams 管理センターの他のユーザーにアクセスできないようにするアクセス許可を設定します。</span><span class="sxs-lookup"><span data-stu-id="7e131-106">Set permissions that let other personnel, such as helpdesk agents, use Call Analytics, but prevent them from accessing the rest of the Microsoft Teams admin center.</span></span> 
    
- <span data-ttu-id="7e131-107">.Tsv または .csv データファイルをアップロードすることにより、建物、サイト、テナント情報を通話分析に追加します。</span><span class="sxs-lookup"><span data-stu-id="7e131-107">Add building, site, and tenant information to Call Analytics by uploading a .tsv or .csv data file.</span></span>
    
<span data-ttu-id="7e131-108">**通話分析は Microsoft Teams 管理センターで利用できるようになりました**。</span><span class="sxs-lookup"><span data-stu-id="7e131-108">**Call Analytics is now available in the Microsoft Teams admin center**.</span></span> <span data-ttu-id="7e131-109">すべての通話情報とユーザーのデータを表示するには、[**通話履歴**] タブを使用します。これを行うには、次のいずれかの操作を行って、ユーザーのプロファイルページを参照します。</span><span class="sxs-lookup"><span data-stu-id="7e131-109">To see all the call information and data for a user, use the **Call History** tab. You can do this by looking on the user's profile page by doing one of the following:</span></span>

- <span data-ttu-id="7e131-110">ダッシュボードからユーザーを検索します。</span><span class="sxs-lookup"><span data-stu-id="7e131-110">Search for the user from the dashboard.</span></span>
  
   ![ダッシュボードでのユーザー検索のスクリーンショット](media/set-up-call-analytics-image-1.png)

-  <span data-ttu-id="7e131-112">左側のナビゲーションで [**ユーザー** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7e131-112">Select **Users** in the left navigation.</span></span>

   ![左側のナビゲーションのスクリーンショット](media/set-up-call-analytics-image-2.png)
  
## <a name="set-call-analytics-permissions"></a><span data-ttu-id="7e131-114">通話分析のアクセス許可を設定する</span><span class="sxs-lookup"><span data-stu-id="7e131-114">Set Call Analytics permissions</span></span>
<a name="BKMK_SetCAPerms"></a>

<span data-ttu-id="7e131-115">管理者は、通話分析のすべての機能にフルアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="7e131-115">As the admin, you have full access to all the features of Call Analytics.</span></span> <span data-ttu-id="7e131-116">また、サポートスタッフに Azure Active Directory ロールを割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="7e131-116">In addition, you can assign Azure Active Directory roles to support staff.</span></span> <span data-ttu-id="7e131-117">通話分析の限定されたビューが必要なユーザーにチーム通信のサポートスペシャリストの役割を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="7e131-117">Assign the Teams communications support specialist role to users who should have a limited view of Call Analytics.</span></span> <span data-ttu-id="7e131-118">通話分析の全機能にアクセスする必要があるユーザーに、Teams 通信サポートエンジニアの役割を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="7e131-118">Assign the Teams communications support engineer role to users who need access to the full functionality of Call Analytics.</span></span> <span data-ttu-id="7e131-119">どちらの権限レベルでも、Microsoft Teams 管理センターの残りの部分にはアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="7e131-119">Both permission levels prevent access to the rest of the Microsoft Teams admin center.</span></span>

> [!NOTE]
> <span data-ttu-id="7e131-120">通信サポートスペシャリストの役割は、tier 1 のサポートと同等であり、通信サポートエンジニアの役割は tier 2 サポートと同等です。</span><span class="sxs-lookup"><span data-stu-id="7e131-120">The communications support specialist role is equivalent to tier 1 support and the communications support engineer role is equivalent to tier 2 support.</span></span>

<span data-ttu-id="7e131-121">Teams の管理者ロールの詳細については、「 [Microsoft teams の管理者ロールを使用してチームを管理する](using-admin-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7e131-121">For more information about Teams admin roles, see [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md).</span></span> 
  
<span data-ttu-id="7e131-122">通信サポートの専門家が、基本的な通話品質の問題を処理します。</span><span class="sxs-lookup"><span data-stu-id="7e131-122">Communications support specialists handle basic call-quality problems.</span></span> <span data-ttu-id="7e131-123">会議の問題を調査することはありません。</span><span class="sxs-lookup"><span data-stu-id="7e131-123">They don't investigate issues with meetings.</span></span> <span data-ttu-id="7e131-124">代わりに、関連情報を収集し、コミュニケーションサポートエンジニアにエスカレートします。</span><span class="sxs-lookup"><span data-stu-id="7e131-124">Instead, they collect related information and then escalate to a communications support engineer.</span></span> <span data-ttu-id="7e131-125">通信サポートエンジニアは、コミュニケーションサポートスペシャリストから非表示になっている詳細な通話ログに情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="7e131-125">Communications support engineers see information in detailed call logs that's hidden from communications support specialists.</span></span> <span data-ttu-id="7e131-126">次の表では、通話分析を使用している場合の通信サポートスペシャリストと通信サポートエンジニアが利用できる情報の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="7e131-126">The following table gives an overview of information available to communications support specialists and communications support engineers when they use Call Analytics.</span></span>

|<span data-ttu-id="7e131-127">**処理**</span><span class="sxs-lookup"><span data-stu-id="7e131-127">**Activity**</span></span>|<span data-ttu-id="7e131-128">**通話分析の情報**</span><span class="sxs-lookup"><span data-stu-id="7e131-128">**Information in Call Analytics**</span></span>|<span data-ttu-id="7e131-129">**コミュニケーションサポートスペシャリストが表示する内容**</span><span class="sxs-lookup"><span data-stu-id="7e131-129">**What the communications support specialist sees**</span></span>|<span data-ttu-id="7e131-130">**通信サポートエンジニアが見ることができる内容**</span><span class="sxs-lookup"><span data-stu-id="7e131-130">**What the communications support engineer sees**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7e131-131">**通話**</span><span class="sxs-lookup"><span data-stu-id="7e131-131">**Calls**</span></span> <br/> |<span data-ttu-id="7e131-132">発信者の名前</span><span class="sxs-lookup"><span data-stu-id="7e131-132">Caller name</span></span>  <br/> |<span data-ttu-id="7e131-133">エージェントが検索したユーザーの名前のみ。</span><span class="sxs-lookup"><span data-stu-id="7e131-133">Only the name of the user for whom the agent searched.</span></span>  <br/> |<span data-ttu-id="7e131-134">ユーザー名。</span><span class="sxs-lookup"><span data-stu-id="7e131-134">User name.</span></span>  <br/> |
||<span data-ttu-id="7e131-135">受信者の名前</span><span class="sxs-lookup"><span data-stu-id="7e131-135">Recipient name</span></span>  <br/> |<span data-ttu-id="7e131-136">内部ユーザーまたは外部ユーザーとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="7e131-136">Shows as Internal User or External User.</span></span>  <br/> |<span data-ttu-id="7e131-137">受信者の名前。</span><span class="sxs-lookup"><span data-stu-id="7e131-137">Recipient name.</span></span>  <br/> |
||<span data-ttu-id="7e131-138">発信者の電話番号</span><span class="sxs-lookup"><span data-stu-id="7e131-138">Caller phone number</span></span>  <br/> |<span data-ttu-id="7e131-139">最後の3桁を除くすべての電話番号は、アスタリスク記号で隠蔽されています。</span><span class="sxs-lookup"><span data-stu-id="7e131-139">Entire phone number except last three digits are obfuscated with asterisk symbols.</span></span> <span data-ttu-id="7e131-140">たとえば、15552823 \* \* \* とします。</span><span class="sxs-lookup"><span data-stu-id="7e131-140">For example, 15552823\*\*\*.</span></span>  <br/> |<span data-ttu-id="7e131-141">最後の3桁を除くすべての電話番号は、アスタリスク記号で隠蔽されています。</span><span class="sxs-lookup"><span data-stu-id="7e131-141">Entire phone number except last three digits are obfuscated with asterisk symbols.</span></span> <span data-ttu-id="7e131-142">たとえば、15552823 \* \* \* とします。</span><span class="sxs-lookup"><span data-stu-id="7e131-142">For example, 15552823\*\*\*.</span></span>  <br/> |
||<span data-ttu-id="7e131-143">受信者の電話番号</span><span class="sxs-lookup"><span data-stu-id="7e131-143">Recipient phone number</span></span>  <br/> |<span data-ttu-id="7e131-144">最後の3桁を除くすべての電話番号は、アスタリスク記号で隠蔽されています。</span><span class="sxs-lookup"><span data-stu-id="7e131-144">Entire phone number except last three digits are obfuscated with asterisk symbols.</span></span> <span data-ttu-id="7e131-145">たとえば、15552823 \* \* \* とします。</span><span class="sxs-lookup"><span data-stu-id="7e131-145">For example, 15552823\*\*\*.</span></span>  <br/> |<span data-ttu-id="7e131-146">最後の3桁を除くすべての電話番号は、アスタリスク記号で隠蔽されています。</span><span class="sxs-lookup"><span data-stu-id="7e131-146">Entire phone number except last three digits are obfuscated with asterisk symbols.</span></span> <span data-ttu-id="7e131-147">たとえば、15552823 \* \* \* とします。</span><span class="sxs-lookup"><span data-stu-id="7e131-147">For example, 15552823\*\*\*.</span></span>  <br/> |
||<span data-ttu-id="7e131-148">\*\*\*\* > **[** 通話の詳細] タブ</span><span class="sxs-lookup"><span data-stu-id="7e131-148">**Call Details** > **Advanced** tab</span></span> <br/> |<span data-ttu-id="7e131-149">情報は表示されません。</span><span class="sxs-lookup"><span data-stu-id="7e131-149">Information not shown.</span></span>  <br/> |<span data-ttu-id="7e131-150">デバイス名、IP アドレス、サブネットマッピングなど、すべての詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7e131-150">All details shown, such as device names, IP address, subnet mapping, and more.</span></span>  <br/> |
||<span data-ttu-id="7e131-151">**[通話の詳細** > ] の **[詳細** > **デバッグ**] タブ</span><span class="sxs-lookup"><span data-stu-id="7e131-151">**Call Details** > **Advanced** > **Debug** tab</span></span> <br/> |<span data-ttu-id="7e131-152">情報は表示されません。</span><span class="sxs-lookup"><span data-stu-id="7e131-152">Information not shown.</span></span>  <br/> |<span data-ttu-id="7e131-153">DNS サフィックスや SSID などのすべての詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7e131-153">All details shown, such as DNS suffix and SSID.</span></span>  <br/> |
|<span data-ttu-id="7e131-154">**会議**</span><span class="sxs-lookup"><span data-stu-id="7e131-154">**Meetings**</span></span> <br/> |<span data-ttu-id="7e131-155">参加者名</span><span class="sxs-lookup"><span data-stu-id="7e131-155">Participant names</span></span>  <br/> |<span data-ttu-id="7e131-156">エージェントが検索したユーザーの名前のみ。</span><span class="sxs-lookup"><span data-stu-id="7e131-156">Only the name of the user for whom the agent searched.</span></span> <span data-ttu-id="7e131-157">内部ユーザーまたは外部ユーザーとして識別された他の参加者。</span><span class="sxs-lookup"><span data-stu-id="7e131-157">Other participants identified as Internal User or External User.</span></span>  <br/> |<span data-ttu-id="7e131-158">すべての名前が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7e131-158">All names shown.</span></span>  <br/> |
||<span data-ttu-id="7e131-159">参加者数</span><span class="sxs-lookup"><span data-stu-id="7e131-159">Participant count</span></span>  <br/> |<span data-ttu-id="7e131-160">参加者の数。</span><span class="sxs-lookup"><span data-stu-id="7e131-160">Number of participants.</span></span>  <br/> |<span data-ttu-id="7e131-161">参加者の数。</span><span class="sxs-lookup"><span data-stu-id="7e131-161">Number of participants.</span></span>  <br/> |
||<span data-ttu-id="7e131-162">セッションの詳細</span><span class="sxs-lookup"><span data-stu-id="7e131-162">Session details</span></span>  <br/> |<span data-ttu-id="7e131-163">例外と共に表示されるセッションの詳細。</span><span class="sxs-lookup"><span data-stu-id="7e131-163">Session details shown with exceptions.</span></span> <span data-ttu-id="7e131-164">エージェントで検索されたユーザーの名前のみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7e131-164">Only the name of the user for whom the agent searched is shown.</span></span> <span data-ttu-id="7e131-165">内部ユーザーまたは外部ユーザーとして識別された他の参加者。</span><span class="sxs-lookup"><span data-stu-id="7e131-165">Other participants identified as Internal User or External User.</span></span> <span data-ttu-id="7e131-166">アスタリスク記号が付いた、電話番号の最後の3桁が隠蔽されています。</span><span class="sxs-lookup"><span data-stu-id="7e131-166">Last three digits of telephone number obfuscated with asterisk symbols.</span></span>  <br/> |<span data-ttu-id="7e131-167">セッションの詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7e131-167">Session details shown.</span></span> <span data-ttu-id="7e131-168">ユーザー名とセッションの詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7e131-168">User names and session details shown.</span></span> <span data-ttu-id="7e131-169">アスタリスク記号が付いた、電話番号の最後の3桁が隠蔽されています。</span><span class="sxs-lookup"><span data-stu-id="7e131-169">Last three digits of telephone number obfuscated with asterisk symbols.</span></span>  <br/> |
||||
   
 ### <a name="set-up-permissions-by-assigning-admin-roles"></a><span data-ttu-id="7e131-170">管理者ロールを割り当ててアクセス許可を設定する</span><span class="sxs-lookup"><span data-stu-id="7e131-170">Set up permissions by assigning admin roles</span></span>
<span data-ttu-id="7e131-171"><a name="BKMK_SetUpTier"> </a></span><span class="sxs-lookup"><span data-stu-id="7e131-171"></span></span>

<span data-ttu-id="7e131-172">Azure Active Directory に管理者ロールを割り当てる方法については、「 [Azure Active directory での役割の表示と割り当て](https://docs.microsoft.com/en-us/azure/active-directory/users-groups-roles/directory-manage-roles-portal)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7e131-172">To learn how to assign administrative roles in Azure Active Directory, see [View and assign roles in Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/users-groups-roles/directory-manage-roles-portal).</span></span>

## <a name="upload-a-tsv-or-csv-file-to-add-building-site-and-tenant-information"></a><span data-ttu-id="7e131-173">.Tsv または .csv ファイルをアップロードして、建物、サイト、テナントの情報を追加する</span><span class="sxs-lookup"><span data-stu-id="7e131-173">Upload a .tsv or .csv file to add building, site, and tenant information</span></span>
<span data-ttu-id="7e131-174"><a name="BKMK_UploadFiles"> </a></span><span class="sxs-lookup"><span data-stu-id="7e131-174"></span></span>

<span data-ttu-id="7e131-175">.Csv または .tsv ファイルをアップロードすることにより、建物、サイト、テナント情報を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="7e131-175">You can add building, site, and tenant information to Call Analytics by uploading a .csv or .tsv file.</span></span> <span data-ttu-id="7e131-176">すべての情報を使って、通話分析で IP アドレスを物理的な場所に対応付けることができます。</span><span class="sxs-lookup"><span data-stu-id="7e131-176">With all this information, Call Analytics can map IP addresses to physical locations.</span></span> <span data-ttu-id="7e131-177">この情報は、お客様またはヘルプデスクの担当者が、通話の問題の傾向を見つけるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="7e131-177">You or helpdesk agents might find this information useful to help spot trends in call problems.</span></span> <span data-ttu-id="7e131-178">たとえば、同じ建物内の多くのユーザーが同様の通話品質の問題を抱えているのはなぜですか?</span><span class="sxs-lookup"><span data-stu-id="7e131-178">For example, why are many users in the same building having similar call quality issues?</span></span> 

<span data-ttu-id="7e131-179">チームと Skype for business の管理者である場合は、Teams & Skype for Business 通話品質ダッシュボードから既存のデータファイルを使用できます。</span><span class="sxs-lookup"><span data-stu-id="7e131-179">If you're a Teams and Skype for Business admin, you can use an existing data file from the Teams & Skype for Business Call Quality Dashboard.</span></span> <span data-ttu-id="7e131-180">まず、通話品質ダッシュボードからファイルをダウンロードしてから、それをアップロードして分析を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="7e131-180">First, you download the file from Call Quality Dashboard, and then you upload it to Call Analytics.</span></span> 

- <span data-ttu-id="7e131-181">既存のデータファイルをダウンロードするには、 **Microsoft Teams 管理センター** > の**通話品質ダッシュボード** > **で今すぐアップロード**します。</span><span class="sxs-lookup"><span data-stu-id="7e131-181">To download an existing data file, go to **Microsoft Teams admin center** > **Call Quality Dashboard** > **Upload now**.</span></span> <span data-ttu-id="7e131-182">[**マイアップロード**] ボックスの一覧で、目的のファイルの横にある [**ダウンロード**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e131-182">In the **My uploads** list, click **Download** next to the file you want.</span></span>

- <span data-ttu-id="7e131-183">新しいファイルをアップロードするには、 **Microsoft Teams 管理センター** > の**場所**に移動し、[**場所データのアップロード**] または [場所のデータの**置き換え**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7e131-183">To upload the new file, go to **Microsoft Teams admin center** > **Locations**, and then select **Upload location data** or **Replace location data**.</span></span>
  
<span data-ttu-id="7e131-184">.Tsv または .csv ファイルを最初から作成する場合は、「[テナントデータファイルの形式と建物データファイルの構造](turning-on-and-using-call-quality-dashboard.md#BKMKTenantDataFile)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7e131-184">If you're creating the .tsv or .csv file from scratch, see [Tenant data file format and Building data file structure](turning-on-and-using-call-quality-dashboard.md#BKMKTenantDataFile).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="7e131-185">関連項目</span><span class="sxs-lookup"><span data-stu-id="7e131-185">Related topics</span></span>
<span data-ttu-id="7e131-186"><a name="BKMK_UploadFiles"> </a></span><span class="sxs-lookup"><span data-stu-id="7e131-186"></span></span>

[<span data-ttu-id="7e131-187">通話分析を使用して低品質の通話をトラブルシューティングする</span><span class="sxs-lookup"><span data-stu-id="7e131-187">Use Call Analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="7e131-188">通話分析および通話品質ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="7e131-188">Call Analytics and Call Quality Dashboard</span></span>](difference-between-call-analytics-and-call-quality-dashboard.md)

  
 
