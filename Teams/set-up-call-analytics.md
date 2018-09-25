---
title: 分析機能の呼び出しを設定します
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: ''
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
ms.openlocfilehash: 1e7c7eaa769ba1e08a46b539b15e673d35891f5c
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2018
ms.locfileid: "25016910"
---
# <a name="set-up-call-analytics"></a><span data-ttu-id="ca8e3-103">分析機能の呼び出しを設定します</span><span class="sxs-lookup"><span data-stu-id="ca8e3-103">Set up Call Analytics</span></span>

<span data-ttu-id="ca8e3-104">Skype のオンライン ビジネスの管理、分析機能の呼び出しを使用するにはビジネス用の Skype のトラブルシューティングを行うとマイクロソフトのチームは、品質との接続の問題を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="ca8e3-104">As a Skype for Business Online admin, you can use Call Analytics to troubleshoot Skype for Business and Microsoft Teams call quality and connection problems.</span></span> <span data-ttu-id="ca8e3-105">分析機能を呼び出すには、次の機能を設定すると便利です。</span><span class="sxs-lookup"><span data-stu-id="ca8e3-105">You may find it useful to set up the following capabilities in Call Analytics:</span></span>
  
- <span data-ttu-id="ca8e3-106">その他のスタッフ、ヘルプ デスク担当者など、分析機能の呼び出しを使用してアクセス許可を設定、ビジネス管理センターの Skype の残りの部分にアクセスすることができません。</span><span class="sxs-lookup"><span data-stu-id="ca8e3-106">Set permissions that let other personnel, such as helpdesk agents, use Call Analytics but prevent them from accessing the rest of the Skype for Business admin center.</span></span> 
    
- <span data-ttu-id="ca8e3-107">.Tsv または .csv データ ファイルをアップロードすることで、分析機能の呼び出しを構築、サイト、およびテナントの情報を追加します。</span><span class="sxs-lookup"><span data-stu-id="ca8e3-107">Add building, site, and tenant information to Call Analytics by uploading a .tsv or .csv data file.</span></span>
    
<span data-ttu-id="ca8e3-108">**コール分析では、マイクロソフトのチームとビジネス管理センターの Skype です。**</span><span class="sxs-lookup"><span data-stu-id="ca8e3-108">**Call Analytics is now available in the Microsoft Teams and Skype for Business Admin Center.**</span></span> <span data-ttu-id="ca8e3-109">すべてのコール情報とユーザーのデータを表示するには、[**呼び出し履歴**] タブを使用します。ダッシュ ボードからユーザーを検索するか、[プロファイル] ページでユーザーの検索、または左側のナビゲーションで、**ユーザー**からユーザーを検索してこれを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="ca8e3-109">To see all of the call information and data for a user, use the **Call History** tab. You can do this by looking on the user's profile page by either searching for the user from the dashboard or finding the user from **Users** in the left navigation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ca8e3-110">ヘルプデスク エージェントのアクセス許可とネットワーク トポロジのアップロードがで使用できる新しい管理ポータルで、今後数か月。</span><span class="sxs-lookup"><span data-stu-id="ca8e3-110">Helpdesk agent permissions and network topology upload will be available in the new admin portal in the coming months.</span></span> <span data-ttu-id="ca8e3-111">使用を続行する間、https://adminportal.services.skypeforbusiness.comの第 1 層および第 2 層のヘルプデスクへのアクセス。</span><span class="sxs-lookup"><span data-stu-id="ca8e3-111">In the meantime, you can continue to use https://adminportal.services.skypeforbusiness.com for Tier 1 and Tier 2 helpdesk access.</span></span>
  
## <a name="set-call-analytics-permissions"></a><span data-ttu-id="ca8e3-112">分析機能を呼び出すアクセス許可を設定します。</span><span class="sxs-lookup"><span data-stu-id="ca8e3-112">Set Call Analytics permissions</span></span>
<a name="BKMK_SetCAPerms"></a>

<span data-ttu-id="ca8e3-113">管理者としては、分析機能の呼び出しのすべての機能へのフル アクセスを取得します。</span><span class="sxs-lookup"><span data-stu-id="ca8e3-113">As the admin, you get full access to all the features of Call Analytics.</span></span> <span data-ttu-id="ca8e3-114">さらに、第 1 層および第 2 層のアクセス許可グループを含む呼び出しの分析で、ヘルプデスク モデルを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="ca8e3-114">In addition, you can use a helpdesk model in Call Analytics that includes Tier 1 and Tier 2 permission groups.</span></span> <span data-ttu-id="ca8e3-115">第 1 層のアクセス許可を持つユーザーは、分析機能の呼び出しの制限付きビューだけにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="ca8e3-115">Users with Tier 1 permissions can access only a limited view of Call Analytics.</span></span> <span data-ttu-id="ca8e3-116">層 2 のアクセス許可を持つユーザーは、分析機能の呼び出しのすべての機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="ca8e3-116">Users with Tier 2 permissions can access the full functionality of Call Analytics.</span></span> <span data-ttu-id="ca8e3-117">両方のアクセス許可レベルは、ビジネス管理センターの Skype、マイクロソフトのチームの残りの部分へのアクセスを防止します。</span><span class="sxs-lookup"><span data-stu-id="ca8e3-117">Both permission levels prevent access to the rest of the Microsoft Teams and Skype for Business Admin Center.</span></span> <span data-ttu-id="ca8e3-118">層へのアクセス権を付与するには、1 層または [権限] ページの第 2 層のセクションのいずれかにユーザーを含むグループを追加します。</span><span class="sxs-lookup"><span data-stu-id="ca8e3-118">You can grant access to the tiers by adding a group that contains the user to either the Tier 1 or the Tier 2 section of the Permissions page.</span></span> <span data-ttu-id="ca8e3-119">詳細については、[分析機能の呼び出しの階層型のアクセス許可の設定](set-up-call-analytics.md#BKMK_SetUpTier)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca8e3-119">For details, see [Set up tiered permissions in Call Analytics](set-up-call-analytics.md#BKMK_SetUpTier).</span></span>
  
<span data-ttu-id="ca8e3-120">第 1 層のヘルプ デスクの担当者は、基本的な通話品質の問題を処理します。</span><span class="sxs-lookup"><span data-stu-id="ca8e3-120">Tier 1 helpdesk agents handle basic call-quality problems.</span></span> <span data-ttu-id="ca8e3-121">第 1 層のエージェントは、会議が、ユーザーに関する問題を調査しません。関連情報を収集、第 2 層のエージェントにエスカレートします。</span><span class="sxs-lookup"><span data-stu-id="ca8e3-121">Tier 1 agents don't investigate issues with meetings; they collect related information and then escalate to a Tier 2 agent.</span></span> <span data-ttu-id="ca8e3-122">第 2 層のエージェントは、エージェントの第 1 層から非表示になっている呼び出しの詳細なログ内の情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca8e3-122">Tier 2 agents see information in detailed call logs that's hidden from Tier 1 agents.</span></span> <span data-ttu-id="ca8e3-123">次の表は、分析機能の呼び出しを使用してエージェントを使用できる情報の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="ca8e3-123">The following table gives an overview of information available to agents using Call Analytics.</span></span>


|<span data-ttu-id="ca8e3-124">**アクティビティ**</span><span class="sxs-lookup"><span data-stu-id="ca8e3-124">**Activity**</span></span>|<span data-ttu-id="ca8e3-125">**コール分析の情報**</span><span class="sxs-lookup"><span data-stu-id="ca8e3-125">**Information in Call Analytics**</span></span>|<span data-ttu-id="ca8e3-126">**第 1 層のエージェントが表示されます。**</span><span class="sxs-lookup"><span data-stu-id="ca8e3-126">**What the Tier 1 agent sees**</span></span>|<span data-ttu-id="ca8e3-127">**第 2 層のエージェントが表示されます。**</span><span class="sxs-lookup"><span data-stu-id="ca8e3-127">**What the Tier 2 agent sees**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ca8e3-128">**[通話]**</span><span class="sxs-lookup"><span data-stu-id="ca8e3-128">**Calls**</span></span> <br/> |<span data-ttu-id="ca8e3-129">呼び出し元の名前</span><span class="sxs-lookup"><span data-stu-id="ca8e3-129">Caller name</span></span>  <br/> |<span data-ttu-id="ca8e3-130">エージェントが検索対象となるユーザーの名前のみです。</span><span class="sxs-lookup"><span data-stu-id="ca8e3-130">Only the name of the user for whom the agent searched.</span></span>  <br/> |<span data-ttu-id="ca8e3-131">ユーザー名です。</span><span class="sxs-lookup"><span data-stu-id="ca8e3-131">User name.</span></span>  <br/> |
||<span data-ttu-id="ca8e3-132">受取人の名前</span><span class="sxs-lookup"><span data-stu-id="ca8e3-132">Recipient name</span></span>  <br/> |<span data-ttu-id="ca8e3-133">内部ユーザーまたは外部のユーザーとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="ca8e3-133">Shows as Internal User or External User.</span></span>  <br/> |<span data-ttu-id="ca8e3-134">受信者の名前です。</span><span class="sxs-lookup"><span data-stu-id="ca8e3-134">Recipient name.</span></span>  <br/> |
||<span data-ttu-id="ca8e3-135">発信者電話番号</span><span class="sxs-lookup"><span data-stu-id="ca8e3-135">Caller phone number</span></span>  <br/> |<span data-ttu-id="ca8e3-136">最後の 3 桁の数字以外の電話番号はアスタリスク記号を難読化します。</span><span class="sxs-lookup"><span data-stu-id="ca8e3-136">Entire phone number except last three digits are obfuscated with asterisk symbols.</span></span> <span data-ttu-id="ca8e3-137">たとえば、15552823。。</span><span class="sxs-lookup"><span data-stu-id="ca8e3-137">For example, 15552823\*\*\*.</span></span>  <br/> |<span data-ttu-id="ca8e3-138">最後の 3 桁の数字以外の電話番号はアスタリスク記号を難読化します。</span><span class="sxs-lookup"><span data-stu-id="ca8e3-138">Entire phone number except last three digits are obfuscated with asterisk symbols.</span></span> <span data-ttu-id="ca8e3-139">たとえば、15552823。。</span><span class="sxs-lookup"><span data-stu-id="ca8e3-139">For example, 15552823\*\*\*.</span></span>  <br/> |
||<span data-ttu-id="ca8e3-140">受信者の電話番号</span><span class="sxs-lookup"><span data-stu-id="ca8e3-140">Recipient phone number</span></span>  <br/> |<span data-ttu-id="ca8e3-141">最後の 3 桁の数字以外の電話番号はアスタリスク記号を難読化します。</span><span class="sxs-lookup"><span data-stu-id="ca8e3-141">Entire phone number except last three digits are obfuscated with asterisk symbols.</span></span> <span data-ttu-id="ca8e3-142">たとえば、15552823。。</span><span class="sxs-lookup"><span data-stu-id="ca8e3-142">For example, 15552823\*\*\*.</span></span>  <br/> |<span data-ttu-id="ca8e3-143">最後の 3 桁の数字以外の電話番号はアスタリスク記号を難読化します。</span><span class="sxs-lookup"><span data-stu-id="ca8e3-143">Entire phone number except last three digits are obfuscated with asterisk symbols.</span></span> <span data-ttu-id="ca8e3-144">たとえば、15552823。。</span><span class="sxs-lookup"><span data-stu-id="ca8e3-144">For example, 15552823\*\*\*.</span></span>  <br/> |
||<span data-ttu-id="ca8e3-145">**通話の詳細** > [**詳細**] タブ</span><span class="sxs-lookup"><span data-stu-id="ca8e3-145">**Call Details** > **Advanced** tab</span></span> <br/> |<span data-ttu-id="ca8e3-146">情報は表示されません。</span><span class="sxs-lookup"><span data-stu-id="ca8e3-146">Information not shown.</span></span>  <br/> |<span data-ttu-id="ca8e3-147">すべての詳細が表示されます、デバイス名、IP アドレス、サブネットのマッピング、および詳細などです。</span><span class="sxs-lookup"><span data-stu-id="ca8e3-147">All details shown, such as device names, IP address, subnet mapping, and more.</span></span>  <br/> |
||<span data-ttu-id="ca8e3-148">**通話の詳細** > **詳細** > [**デバッグ**] タブ</span><span class="sxs-lookup"><span data-stu-id="ca8e3-148">**Call Details** > **Advanced** > **Debug** tab</span></span> <br/> |<span data-ttu-id="ca8e3-149">情報は表示されません。</span><span class="sxs-lookup"><span data-stu-id="ca8e3-149">Information not shown.</span></span>  <br/> |<span data-ttu-id="ca8e3-150">すべての詳細を示すように、DNS サフィックスであり、SSID などです。</span><span class="sxs-lookup"><span data-stu-id="ca8e3-150">All details shown, such as DNS suffix and SSID.</span></span>  <br/> |
|<span data-ttu-id="ca8e3-151">**会議**</span><span class="sxs-lookup"><span data-stu-id="ca8e3-151">**Meetings**</span></span> <br/> |<span data-ttu-id="ca8e3-152">参加者名</span><span class="sxs-lookup"><span data-stu-id="ca8e3-152">Participant names</span></span>  <br/> |<span data-ttu-id="ca8e3-153">エージェントが検索対象となるユーザーの名前のみです。</span><span class="sxs-lookup"><span data-stu-id="ca8e3-153">Only the name of the user for whom the agent searched.</span></span> <span data-ttu-id="ca8e3-154">他の参加者は、内部ユーザーと外部ユーザーを識別します。</span><span class="sxs-lookup"><span data-stu-id="ca8e3-154">Other participants identified as Internal User or External User.</span></span>  <br/> |<span data-ttu-id="ca8e3-155">すべての名前が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ca8e3-155">All names shown.</span></span>  <br/> |
||<span data-ttu-id="ca8e3-156">参加者数</span><span class="sxs-lookup"><span data-stu-id="ca8e3-156">Participant count</span></span>  <br/> |<span data-ttu-id="ca8e3-157">参加者の数です。</span><span class="sxs-lookup"><span data-stu-id="ca8e3-157">Number of participants.</span></span>  <br/> |<span data-ttu-id="ca8e3-158">参加者の数です。</span><span class="sxs-lookup"><span data-stu-id="ca8e3-158">Number of participants.</span></span>  <br/> |
||<span data-ttu-id="ca8e3-159">セッションの詳細</span><span class="sxs-lookup"><span data-stu-id="ca8e3-159">Session details</span></span>  <br/> |<span data-ttu-id="ca8e3-160">セッションの詳細が例外を使用して表示します。</span><span class="sxs-lookup"><span data-stu-id="ca8e3-160">Session details shown with exceptions.</span></span> <span data-ttu-id="ca8e3-161">エージェントが検索対象となるユーザーの名前のみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ca8e3-161">Only the name of the user for whom the agent searched is shown.</span></span> <span data-ttu-id="ca8e3-162">他の参加者は、内部ユーザーと外部ユーザーを識別します。</span><span class="sxs-lookup"><span data-stu-id="ca8e3-162">Other participants identified as Internal User or External User.</span></span> <span data-ttu-id="ca8e3-163">最後のアスタリスク記号を使用して難読化の電話番号の 3 桁の数字です。</span><span class="sxs-lookup"><span data-stu-id="ca8e3-163">Last three digits of telephone number obfuscated with asterisk symbols.</span></span>  <br/> |<span data-ttu-id="ca8e3-164">セッションの詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ca8e3-164">Session details shown.</span></span> <span data-ttu-id="ca8e3-165">ユーザー名およびセッションの詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ca8e3-165">User names and session details shown.</span></span> <span data-ttu-id="ca8e3-166">最後のアスタリスク記号を使用して難読化の電話番号の 3 桁の数字です。</span><span class="sxs-lookup"><span data-stu-id="ca8e3-166">Last three digits of telephone number obfuscated with asterisk symbols.</span></span>  <br/> |
   
 <span data-ttu-id="ca8e3-167">**分析機能の呼び出しの階層型のアクセス許可を設定**
 <a name="BKMK_SetUpTier"> </a></span><span class="sxs-lookup"><span data-stu-id="ca8e3-167">**Set up tiered permissions in Call Analytics**
<a name="BKMK_SetUpTier"> </a></span></span>

<span data-ttu-id="ca8e3-168">![デバイスのロゴ-30x30.png](media/sfb-logo-30x30.png) **、マイクロソフトのチームとビジネス管理センターの Skype を使用します。**</span><span class="sxs-lookup"><span data-stu-id="ca8e3-168">![sfb-logo-30x30.png](media/sfb-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>
  
1. <span data-ttu-id="ca8e3-169">第 1 層および第 2 層には、Office 365 のセキュリティ グループを作成し、各グループにユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="ca8e3-169">Create Office 365 security groups for Tier 1 and Tier 2, and add the people you want to each group.</span></span> <span data-ttu-id="ca8e3-170">既存のセキュリティ グループを再利用することができます。</span><span class="sxs-lookup"><span data-stu-id="ca8e3-170">You can also reuse existing security groups.</span></span> <span data-ttu-id="ca8e3-171">詳細については、[作成、編集、または、Office 365 の管理センターでセキュリティ グループを削除する](https://support.office.com/article/55c96b32-e086-4c9e-948b-a018b44510cb)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca8e3-171">For more information, see [Create, edit, or delete a security group in the Office 365 admin center](https://support.office.com/article/55c96b32-e086-4c9e-948b-a018b44510cb).</span></span>
    
2. <span data-ttu-id="ca8e3-172">Office 365 の管理センターで**管理センター**に移動する > **ビジネス用の Skype**です。</span><span class="sxs-lookup"><span data-stu-id="ca8e3-172">In the Office 365 admin center, go to **Admin centers** > **Skype for Business**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ca8e3-173">**マイクロソフトのチームとビジネス管理センターの Skype**を使用する場合は左側のナビゲーションでは、**従来のポータル**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ca8e3-173">If you are in the **Microsoft Teams and Skype for Business Admin Center**, in the left navigation, click **Legacy portal**.</span></span>
  
3. <span data-ttu-id="ca8e3-174">**ツール**を選択 > **Skype**を呼び出すビジネス分析 (プレビュー) を > **の設定**、し、[**権限**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ca8e3-174">Select **Tools** > **Skype for Business Call Analytics (preview)** > **Settings**, and then click **Permissions**.</span></span>
    
4. <span data-ttu-id="ca8e3-175">**第 1 層**および**第 2 層**のボックスには、Office 365 のセキュリティ グループを追加します。</span><span class="sxs-lookup"><span data-stu-id="ca8e3-175">Add the Office 365 security groups to the **Tier 1** and **Tier 2** boxes.</span></span> <span data-ttu-id="ca8e3-176">各ロールに複数のグループを追加できます。</span><span class="sxs-lookup"><span data-stu-id="ca8e3-176">You can add multiple groups to each role.</span></span>
    
     ![スクリーン ショットは、第 1 層および第 2 層のアクセス許可のオプションを使用して分析を呼び出すページのアクセス許可を示しています。](media/setup-call-analytics-image1.png)
  
 <span data-ttu-id="ca8e3-178">どちらのアクセス許可レベルを持つユーザーが専用の URL を使用して分析機能の呼び出しを取得*https://adminportal.services.skypeforbusiness.com*。</span><span class="sxs-lookup"><span data-stu-id="ca8e3-178">Users with either of these permission levels get to Call Analytics via the dedicated URL *https://adminportal.services.skypeforbusiness.com*.</span></span>
  
## <a name="upload-a-tsv-or-csv-file-to-add-building-site-and-tenant-information"></a><span data-ttu-id="ca8e3-179">サイトの構築を追加し、情報をテナントに .tsv または .csv ファイルをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="ca8e3-179">Upload a .tsv or .csv file to add building, site, and tenant information</span></span>
<span data-ttu-id="ca8e3-180"><a name="BKMK_UploadFiles"> </a></span><span class="sxs-lookup"><span data-stu-id="ca8e3-180"></span></span>

<span data-ttu-id="ca8e3-181">.Csv または .tsv ファイルをアップロードすることで、分析機能の呼び出しを構築、サイト、およびテナント情報を追加できます。</span><span class="sxs-lookup"><span data-stu-id="ca8e3-181">You can add building, site, and tenant information to Call Analytics by uploading a .csv or .tsv file.</span></span> <span data-ttu-id="ca8e3-182">この情報は、分析機能の呼び出しは、物理的な場所に IP アドレスをマップできます。</span><span class="sxs-lookup"><span data-stu-id="ca8e3-182">With all this information, Call Analytics can map IP addresses to physical locations.</span></span> <span data-ttu-id="ca8e3-183">か、ヘルプデスク エージェントについては、この役に立つの呼び出しに関する問題の傾向を支援します。</span><span class="sxs-lookup"><span data-stu-id="ca8e3-183">You or helpdesk agents might find this information useful to help spot trends in call problems.</span></span> <span data-ttu-id="ca8e3-184">などの品質の問題を呼び出すのような多くのユーザーが同じ建物ではなぜですか。</span><span class="sxs-lookup"><span data-stu-id="ca8e3-184">For example, why are many users in the same building having similar call quality issues?</span></span> 
  
![スクリーン ショットには、サイトの数とサブネット数の値を持つサイトのページと、.tsv または .csv ファイルをアップロードすることでサイトのデータをインポートするファイルを選択します] ボタンが表示されます。](media/b2f3a5cb-32b5-4f60-a9af-0691aa6ff1e8.png)
  
<span data-ttu-id="ca8e3-186">Skype ビジネス管理者の場合は、ビジネス オンライン コール品質のダッシュ ボードは、Skype から既存のデータ ファイルを使用できます。</span><span class="sxs-lookup"><span data-stu-id="ca8e3-186">If you're a Skype for Business admin, you can use an existing data file from the Skype for Business Online Call Quality Dashboard.</span></span> <span data-ttu-id="ca8e3-187">まず、コール品質のダッシュ ボードからファイルをダウンロードして、分析機能の呼び出しにアップロードします。</span><span class="sxs-lookup"><span data-stu-id="ca8e3-187">First, you download the file from Call Quality Dashboard, and then you upload it to Call Analytics.</span></span> <span data-ttu-id="ca8e3-188">既存のデータ ファイルをダウンロードするには、**ビジネス管理センターの Skype** > **ツール** > **ビジネス オンライン コール品質のダッシュ ボードの Skype** > **今すぐアップロード**します。</span><span class="sxs-lookup"><span data-stu-id="ca8e3-188">To download an existing data file, go to the **Skype for Business Admin center** > **Tools** > **Skype for Business Online Call Quality Dashboard** > **Upload now**.</span></span> <span data-ttu-id="ca8e3-189">**[アップロード**] の一覧で目的のファイルの横にある [**ダウンロード**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ca8e3-189">In the **My uploads** list, click **Download** next to the file you want.</span></span>
  
<span data-ttu-id="ca8e3-190">.Tsv または .csv ファイルを最初から作成する場合は、[テナントのデータ ファイルの形式とデータ ファイルの構造の構築](turning-on-and-using-call-quality-dashboard.md#BKMKTenantDataFile)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca8e3-190">If you're creating the .tsv or .csv file from scratch, see [Tenant data file format and Building data file structure](turning-on-and-using-call-quality-dashboard.md#BKMKTenantDataFile).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="ca8e3-191">関連トピック</span><span class="sxs-lookup"><span data-stu-id="ca8e3-191">Related topics</span></span>
<span data-ttu-id="ca8e3-192"><a name="BKMK_UploadFiles"> </a></span><span class="sxs-lookup"><span data-stu-id="ca8e3-192"></span></span>

[<span data-ttu-id="ca8e3-193">通話分析を使用して低い通話品質をトラブルシューティングする</span><span class="sxs-lookup"><span data-stu-id="ca8e3-193">Use Call Analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="ca8e3-194">呼び出しを分析し、通話品質のダッシュ ボード</span><span class="sxs-lookup"><span data-stu-id="ca8e3-194">Call Analytics and Call Quality Dashboard</span></span>](difference-between-call-analytics-and-call-quality-dashboard.md)

  
 
