---
title: "Skype for Business 通話分析を設定します。"
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Reporting
description: "セットアップし、通話の分析を使用して特定し、Skype for Business や Microsoft チームの通話品質の問題のトラブルシューティングします。"
ms.openlocfilehash: 81d3f88bf04fa63aaa5857e2056aaf429e7ffcd4
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="set-up-skype-for-business-call-analytics"></a><span data-ttu-id="a6d91-103">Skype for Business 通話分析を設定します。</span><span class="sxs-lookup"><span data-stu-id="a6d91-103">Set up Skype for Business Call Analytics</span></span>

<span data-ttu-id="a6d91-p101">Skype for Business Online の管理者にするには、Skype for Business のトラブルシューティングに通話の分析を使用して Microsoft チーム通話の品質との接続の問題。通話の分析では、次の機能を設定すると便利です。</span><span class="sxs-lookup"><span data-stu-id="a6d91-p101">As a Skype for Business Online admin, you can use Call Analytics to troubleshoot Skype for Business and Microsoft Teams call quality and connection problems. You may find it useful to set up the following capabilities in Call Analytics:</span></span>
  
- <span data-ttu-id="a6d91-106">ヘルプデスク エージェントなど、その他の担当者ができるように、通話の分析を使用する権限を設定して、Skype for Business 管理センターの残りの部分にアクセスすることができません。</span><span class="sxs-lookup"><span data-stu-id="a6d91-106">Set permissions that let other personnel, such as helpdesk agents, use Call Analytics but prevent them from accessing the rest of the Skype for Business admin center.</span></span> 
    
- <span data-ttu-id="a6d91-107">通話の分析に .tsv または .csv のデータ ファイルをアップロードして、文書、サイト、およびテナントの情報を追加します。</span><span class="sxs-lookup"><span data-stu-id="a6d91-107">Add building, site, and tenant information to Call Analytics by uploading a .tsv or .csv data file.</span></span>
    
> [!NOTE]
> <span data-ttu-id="a6d91-p102">通話の分析は、現在のプレビューです。テキストと画像がここに示されたは、操作が一致しない場合があります。</span><span class="sxs-lookup"><span data-stu-id="a6d91-p102">Call Analytics is currently in preview. Text and images described here may not match your experience.</span></span> 
  
## <a name="set-call-analytics-permissions"></a><span data-ttu-id="a6d91-110">通話の分析の権限を設定します。</span><span class="sxs-lookup"><span data-stu-id="a6d91-110">Set Call Analytics permissions</span></span>
<a name="BKMK_SetCAPerms"></a>

<span data-ttu-id="a6d91-p103">管理者は、通話の分析のすべての機能へのフル アクセスを取得します。さらに、着信分析層 1 と第 2 のアクセス許可グループを含むでヘルプデスク モデルを使用することができます。階層の 1 の権限を持つユーザーは、通話の分析の制限付きビューだけにアクセスできます。第 2 の権限を持つユーザーは、通話の分析のすべての機能にアクセスできます。両方のアクセス許可レベルは、残りの Skype for Business 管理センターへのアクセスを防止します。階層へのアクセスの許可を付与するには、階層 1 または権限のページの [第 2] セクションに、ユーザーが含まれているグループを追加します。詳細については、[通話の分析の階層型のアクセス許可を設定する](set-up-call-analytics.md#BKMK_SetUpTier)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6d91-p103">As the admin, you get full access to all the features of Call Analytics. In addition, you can use a helpdesk model in Call Analytics that includes Tier 1 and Tier 2 permission groups. Users with Tier 1 permissions can access only a limited view of Call Analytics. Users with Tier 2 permissions can access the full functionality of Call Analytics. Both permission levels prevent access to the rest of the Skype for Business admin center. You can grant access to the tiers by adding a group that contains the user to either the Tier 1 or the Tier 2 section of the Permissions page. For details, see [Set up tiered permissions in Call Analytics](set-up-call-analytics.md#BKMK_SetUpTier).</span></span>
  
<span data-ttu-id="a6d91-p104">階層 1 ヘルプデスク担当者は、通話品質の基本的な問題を処理します。第 1 層エージェントは、会議が、ユーザーに関する問題を調査しません。関連する情報を収集、第 2 のエージェントにエスカレートします。第 2 エージェントは、階層 1 エージェントからが非表示にする詳細な通話ログの情報を参照してください。次の表は、通話の分析を使用してエージェントに使用できる情報の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="a6d91-p104">Tier 1 helpdesk agents handle basic call-quality problems. Tier 1 agents don't investigate issues with meetings; they collect related information and then escalate to a Tier 2 agent. Tier 2 agents see information in detailed call logs that's hidden from Tier 1 agents. The following table gives an overview of information available to agents using Call Analytics.</span></span>


|<span data-ttu-id="a6d91-122">**アクティビティ**</span><span class="sxs-lookup"><span data-stu-id="a6d91-122">**Activity**</span></span>|<span data-ttu-id="a6d91-123">**通話の分析などの情報**</span><span class="sxs-lookup"><span data-stu-id="a6d91-123">**Information in Call Analytics**</span></span>|<span data-ttu-id="a6d91-124">**階層 1 エージェントが表示されます。**</span><span class="sxs-lookup"><span data-stu-id="a6d91-124">**What the Tier 1 agent sees**</span></span>|<span data-ttu-id="a6d91-125">**第 2 エージェントが表示されます。**</span><span class="sxs-lookup"><span data-stu-id="a6d91-125">**What the Tier 2 agent sees**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a6d91-126">**通話**</span><span class="sxs-lookup"><span data-stu-id="a6d91-126">**Calls**</span></span> <br/> |<span data-ttu-id="a6d91-127">発信者の名前</span><span class="sxs-lookup"><span data-stu-id="a6d91-127">Caller name</span></span>  <br/> |<span data-ttu-id="a6d91-128">のみ、エージェントの検索対象のユーザーの名前。</span><span class="sxs-lookup"><span data-stu-id="a6d91-128">Only the name of the user for whom the agent searched.</span></span>  <br/> |<span data-ttu-id="a6d91-129">ユーザーの名前です。</span><span class="sxs-lookup"><span data-stu-id="a6d91-129">User name.</span></span>  <br/> |
||<span data-ttu-id="a6d91-130">受信者の名前</span><span class="sxs-lookup"><span data-stu-id="a6d91-130">Recipient name</span></span>  <br/> |<span data-ttu-id="a6d91-131">ユーザーの内部と外部のユーザーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a6d91-131">Shows as Internal User or External User.</span></span>  <br/> |<span data-ttu-id="a6d91-132">受信者の名前です。</span><span class="sxs-lookup"><span data-stu-id="a6d91-132">Recipient name.</span></span>  <br/> |
||<span data-ttu-id="a6d91-133">発信者の電話番号</span><span class="sxs-lookup"><span data-stu-id="a6d91-133">Caller phone number</span></span>  <br/> |<span data-ttu-id="a6d91-p105">最後の 3 つの数字を除く全体の電話番号は、アスタリスク記号と特殊文字で解読されます。たとえば、15552823。 します。</span><span class="sxs-lookup"><span data-stu-id="a6d91-p105">Entire phone number except last three digits are obfuscated with asterisk symbols. For example, 15552823\*\*\*.</span></span>  <br/> |<span data-ttu-id="a6d91-p106">最後の 3 つの数字を除く全体の電話番号は、アスタリスク記号と特殊文字で解読されます。たとえば、15552823。 します。</span><span class="sxs-lookup"><span data-stu-id="a6d91-p106">Entire phone number except last three digits are obfuscated with asterisk symbols. For example, 15552823\*\*\*.</span></span>  <br/> |
||<span data-ttu-id="a6d91-138">受信者の電話番号</span><span class="sxs-lookup"><span data-stu-id="a6d91-138">Recipient phone number</span></span>  <br/> |<span data-ttu-id="a6d91-p107">最後の 3 つの数字を除く全体の電話番号は、アスタリスク記号と特殊文字で解読されます。たとえば、15552823。 します。</span><span class="sxs-lookup"><span data-stu-id="a6d91-p107">Entire phone number except last three digits are obfuscated with asterisk symbols. For example, 15552823\*\*\*.</span></span>  <br/> |<span data-ttu-id="a6d91-p108">最後の 3 つの数字を除く全体の電話番号は、アスタリスク記号と特殊文字で解読されます。たとえば、15552823。 します。</span><span class="sxs-lookup"><span data-stu-id="a6d91-p108">Entire phone number except last three digits are obfuscated with asterisk symbols. For example, 15552823\*\*\*.</span></span>  <br/> |
||<span data-ttu-id="a6d91-143">**通話の詳細** > **詳細設定**] タブ</span><span class="sxs-lookup"><span data-stu-id="a6d91-143">**Call Details** > **Advanced** tab</span></span> <br/> |<span data-ttu-id="a6d91-144">情報は表示されません。</span><span class="sxs-lookup"><span data-stu-id="a6d91-144">Information not shown.</span></span>  <br/> |<span data-ttu-id="a6d91-145">すべて詳細については、デバイスの名前、IP アドレス、サブネット マッピング、およびなどに表示されます。</span><span class="sxs-lookup"><span data-stu-id="a6d91-145">All details shown, such as device names, IP address, subnet mapping, and more.</span></span>  <br/> |
||<span data-ttu-id="a6d91-146">**通話の詳細** > **詳細** > **デバッグ**] タブ</span><span class="sxs-lookup"><span data-stu-id="a6d91-146">**Call Details** > **Advanced** > **Debug** tab</span></span> <br/> |<span data-ttu-id="a6d91-147">情報は表示されません。</span><span class="sxs-lookup"><span data-stu-id="a6d91-147">Information not shown.</span></span>  <br/> |<span data-ttu-id="a6d91-148">DNS サフィックスと SSID など、表示されるすべての詳細。</span><span class="sxs-lookup"><span data-stu-id="a6d91-148">All details shown, such as DNS suffix and SSID.</span></span>  <br/> |
|<span data-ttu-id="a6d91-149">**会議**</span><span class="sxs-lookup"><span data-stu-id="a6d91-149">**Meetings**</span></span> <br/> |<span data-ttu-id="a6d91-150">参加者の名前</span><span class="sxs-lookup"><span data-stu-id="a6d91-150">Participant names</span></span>  <br/> |<span data-ttu-id="a6d91-p109">のみ、エージェントの検索対象のユーザーの名前。他の参加者は、内部ユーザーまたは外部ユーザーに識別します。</span><span class="sxs-lookup"><span data-stu-id="a6d91-p109">Only the name of the user for whom the agent searched. Other participants identified as Internal User or External User.</span></span>  <br/> |<span data-ttu-id="a6d91-153">すべての名前が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a6d91-153">All names shown.</span></span>  <br/> |
||<span data-ttu-id="a6d91-154">参加者の数</span><span class="sxs-lookup"><span data-stu-id="a6d91-154">Participant count</span></span>  <br/> |<span data-ttu-id="a6d91-155">参加者の数です。</span><span class="sxs-lookup"><span data-stu-id="a6d91-155">Number of participants.</span></span>  <br/> |<span data-ttu-id="a6d91-156">参加者の数です。</span><span class="sxs-lookup"><span data-stu-id="a6d91-156">Number of participants.</span></span>  <br/> |
||<span data-ttu-id="a6d91-157">セッションの詳細</span><span class="sxs-lookup"><span data-stu-id="a6d91-157">Session details</span></span>  <br/> |<span data-ttu-id="a6d91-p110">セッションの詳細については以下の例外が表示されます。エージェントが検索対象のユーザーの名前のみが表示されます。他の参加者は、内部ユーザーまたは外部ユーザーに識別します。最後の電話番号のアスタリスク記号と特殊文字で解読の 3 つの数字です。</span><span class="sxs-lookup"><span data-stu-id="a6d91-p110">Session details shown with exceptions. Only the name of the user for whom the agent searched is shown. Other participants identified as Internal User or External User. Last three digits of telephone number obfuscated with asterisk symbols.</span></span>  <br/> |<span data-ttu-id="a6d91-p111">セッションの詳細が表示されます。ユーザー名とセッションの詳細を表示します。最後の電話番号のアスタリスク記号と特殊文字で解読の 3 つの数字です。</span><span class="sxs-lookup"><span data-stu-id="a6d91-p111">Session details shown. User names and session details shown. Last three digits of telephone number obfuscated with asterisk symbols.</span></span>  <br/> |
   
 <span data-ttu-id="a6d91-165">**通話の分析の階層型のアクセス許可を設定する**
 <a name="BKMK_SetUpTier"> </a></span><span class="sxs-lookup"><span data-stu-id="a6d91-165">**Set up tiered permissions in Call Analytics**
<a name="BKMK_SetUpTier"> </a></span></span>
  
1. <span data-ttu-id="a6d91-p112">層 1 と 2 の層の Office 365 セキュリティ グループを作成し、各グループに人を追加します。既存のセキュリティ グループ再利用することもできます。詳細については、[作成、編集、または Office 365 管理センターでセキュリティ グループを削除する](https://support.office.com/article/55c96b32-e086-4c9e-948b-a018b44510cb)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6d91-p112">Create Office 365 security groups for Tier 1 and Tier 2, and add the people you want to each group. You can also reuse existing security groups. For more information, see [Create, edit, or delete a security group in the Office 365 admin center](https://support.office.com/article/55c96b32-e086-4c9e-948b-a018b44510cb).</span></span>
    
2. <span data-ttu-id="a6d91-169">Office 365 管理センターで、**管理センター**に移動 > **Skype for Business**します。</span><span class="sxs-lookup"><span data-stu-id="a6d91-169">In the Office 365 admin center, go to **Admin centers** > **Skype for Business**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a6d91-170">古い Skype for Business 管理センターにアクセスする場合は、**付属の新しい管理センターを実行してください**] をクリックして、新しいバージョンに移動します。</span><span class="sxs-lookup"><span data-stu-id="a6d91-170">If you land in the old Skype for Business admin center, go to the new version by clicking **Come try our new admin center**.</span></span> 
  
3. <span data-ttu-id="a6d91-171">新しい Skype for Business 管理センターでは、[**権限**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6d91-171">In the new Skype for Business admin center, click **Permissions**.</span></span>
    
4. <span data-ttu-id="a6d91-p113">[**階層の 1**と**第 2** ] ボックスに、Office 365 セキュリティ グループを追加します。役割ごとに複数のグループを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="a6d91-p113">Add the Office 365 security groups to the **Tier 1** and **Tier 2** boxes. You can add multiple groups to each role.</span></span>
    
     ![スクリーン ショットは、階層の 1 と第 2 レベルの権限オプションと通話分析のページのアクセス許可を示しています。](../images/ed5b6b05-b407-4363-8cf0-a6e79027f64b.png)
  
 <span data-ttu-id="a6d91-175">どちらのアクセス許可レベルを持つユーザーは、専用の URL *https://adminportal.services.skypeforbusiness.com*経由で通話の分析を表示します。</span><span class="sxs-lookup"><span data-stu-id="a6d91-175">Users with either of these permission levels get to Call Analytics via the dedicated URL *https://adminportal.services.skypeforbusiness.com*.</span></span>
  
## <a name="upload-a-tsv-or-csv-file-to-add-building-site-and-tenant-information"></a><span data-ttu-id="a6d91-176">サイトの構築を追加して、情報のテナントに .tsv または .csv ファイルをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="a6d91-176">Upload a .tsv or .csv file to add building, site, and tenant information</span></span>
<span data-ttu-id="a6d91-177"><a name="BKMK_UploadFiles"> </a></span><span class="sxs-lookup"><span data-stu-id="a6d91-177"></span></span>

<span data-ttu-id="a6d91-p114">.Csv または .tsv ファイルをアップロードして、通話の分析に文書、サイト、およびテナントの情報を追加できます。このすべての情報を通話分析は、物理的な場所に IP アドレスをマップすることができます。ヘルプデスクまたはするエージェント役に立つ情報傾向通話の問題のためにします。たとえば、品質に問題を呼び出すのような多くのユーザーが同じ文書はなぜですか。</span><span class="sxs-lookup"><span data-stu-id="a6d91-p114">You can add building, site, and tenant information to Call Analytics by uploading a .csv or .tsv file. With all this information, Call Analytics can map IP addresses to physical locations. You or helpdesk agents might find this information useful to help spot trends in call problems. For example, why are many users in the same building having similar call quality issues?</span></span> 
  
![スクリーン ショットは、サイトの数およびサブネット数の値を持つサイト] ページと、.tsv または .csv ファイルをアップロードすることで、サイトのデータをインポートするファイルの選択] ボタンが表示されます。](../images/b2f3a5cb-32b5-4f60-a9af-0691aa6ff1e8.png)
  
<span data-ttu-id="a6d91-p115">Skype for Business の管理者の場合、ビジネス オンライン通話品質のダッシュ ボードの Skype から既存のデータ ファイルを使用することができます。最初に、通話品質のダッシュ ボード] からファイルをダウンロードしてを呼び出す分析にアップロードします。既存のデータ ファイルをダウンロードするには、 **Skype for Business 管理センター**に移動 > **ツール** > **Skype for Business Online 通話品質のダッシュ ボード** > **アップロードするようになりました**。**[アップロード**] ボックスの一覧で、目的のファイルの横にある [**ダウンロード**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6d91-p115">If you're a Skype for Business admin, you can use an existing data file from the Skype for Business Online Call Quality Dashboard. First, you download the file from Call Quality Dashboard, and then you upload it to Call Analytics. To download an existing data file, go to the **Skype for Business Admin center** > **Tools** > **Skype for Business Online Call Quality Dashboard** > **Upload now**. In the **My uploads** list, click **Download** next to the file you want.</span></span>
  
<span data-ttu-id="a6d91-187">ゼロから .tsv または .csv ファイルを作成する場合は、[テナントのデータ ファイルの形式と文書のデータ ファイルの構造](turning-on-and-using-call-quality-dashboard.md#BKMKTenantDataFile)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6d91-187">If you're creating the .tsv or .csv file from scratch, see [Tenant data file format and Building data file structure](turning-on-and-using-call-quality-dashboard.md#BKMKTenantDataFile).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="a6d91-188">関連トピック</span><span class="sxs-lookup"><span data-stu-id="a6d91-188">Related topics</span></span>
<span data-ttu-id="a6d91-189"><a name="BKMK_UploadFiles"> </a></span><span class="sxs-lookup"><span data-stu-id="a6d91-189"></span></span>

[<span data-ttu-id="a6d91-190">不適切な Skype for Business のトラブルシューティングに使用する通話分析通話品質</span><span class="sxs-lookup"><span data-stu-id="a6d91-190">Use Call Analytics to troubleshoot poor Skype for Business call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="a6d91-191">通話の分析手法と通話品質のダッシュ ボードの違いは何ですか。</span><span class="sxs-lookup"><span data-stu-id="a6d91-191">What's the difference between Call Analytics and Call Quality Dashboard?</span></span>](difference-between-call-analytics-and-call-quality-dashboard.md)