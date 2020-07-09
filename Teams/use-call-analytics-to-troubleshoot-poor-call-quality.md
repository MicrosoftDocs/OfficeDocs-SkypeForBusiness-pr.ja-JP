---
title: 通話分析を使用して通話品質の低下をトラブルシューティングする
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, vkorlep
ms.topic: article
ms.assetid: 66945036-ae87-4c08-a0bb-984e50d6b009
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
- ms.teamsadmincenter.directrouting.callanalytics
- ms.teamsadmincenter.users.activity.audioqualitycolumn
- Reporting
description: デバイス、ネットワーク、接続に関するユーザーごとの通話分析の詳細を使用して、Microsoft Teams の通話と会議でのユーザーの問題のトラブルシューティングを行います。
ms.openlocfilehash: fa923a133ac6a56edcbc6f6445d2859692adf351
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085323"
---
# <a name="use-call-analytics-to-troubleshoot-poor-call-quality"></a><span data-ttu-id="c2322-103">通話分析を使用して通話品質の低下をトラブルシューティングする</span><span class="sxs-lookup"><span data-stu-id="c2322-103">Use call analytics to troubleshoot poor call quality</span></span>

<span data-ttu-id="c2322-104">この記事では、チームの管理者またはチームのコミュニケーションサポートスペシャリストまたはエンジニアの場合に、通話分析を使用して、個々のユーザーに対して、Microsoft Teams の不十分な通話や会議の品質をトラブルシューティングする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c2322-104">This article explains how to use call analytics to troubleshoot poor Microsoft Teams call or meeting quality for individual users if you're a Teams admin or a Teams communications support specialist or engineer.</span></span>


  
## <a name="call-analytics-permissions"></a><span data-ttu-id="c2322-105">通話分析のアクセス許可</span><span class="sxs-lookup"><span data-stu-id="c2322-105">Call Analytics permissions</span></span>

<span data-ttu-id="c2322-106">この記事では、既に通話分析を設定済みであることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="c2322-106">This article assumes that you've already set up call analytics.</span></span> <span data-ttu-id="c2322-107">まだお持ちでない場合は、「 [Teams での通話分析のセットアップ](set-up-call-analytics.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2322-107">If you haven't, read [Set up call analytics for Teams](set-up-call-analytics.md).</span></span>

## <a name="introduction-to-call-analytics"></a><span data-ttu-id="c2322-108">通話分析の概要</span><span class="sxs-lookup"><span data-stu-id="c2322-108">Introduction to call analytics</span></span>

<span data-ttu-id="c2322-109">通話分析には、Office 365 アカウントの各ユーザーのチームの通話と会議に関する詳細情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c2322-109">Call analytics shows detailed information about Teams calls and meetings for each user in your Office 365 account.</span></span> <span data-ttu-id="c2322-110">デバイス、ネットワーク、接続性、通話品質についての情報が含まれています (いずれの場合も、通話品質や会議の品質に影響する可能性があります)。</span><span class="sxs-lookup"><span data-stu-id="c2322-110">It includes information about devices, networks, connectivity, and call quality (any of these can be a factor in poor call or meeting quality).</span></span> <span data-ttu-id="c2322-111">建物、サイト、テナントの情報をアップロードすると、通話と会議ごとにこの情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c2322-111">If you upload building, site, and tenant information, this information will also be shown for each call and meeting.</span></span> <span data-ttu-id="c2322-112">通話分析を使用して、ユーザーが不適切な通話や会議の操作を行った理由を確認します。</span><span class="sxs-lookup"><span data-stu-id="c2322-112">Use call analytics to help you figure out why a user had a poor call or meeting experience.</span></span>

<span data-ttu-id="c2322-113">通話分析では、1人の参加者から2つ目の参加者に、通話や会議の各区間が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c2322-113">Call analytics shows you each leg of a call or meeting - for example, from one participant to a second participant.</span></span> <span data-ttu-id="c2322-114">これらの詳細を分析することで、チーム管理者は問題のある領域を特定し、低品質の根本原因を特定することができます。</span><span class="sxs-lookup"><span data-stu-id="c2322-114">By analyzing these details, a Teams admin can isolate problem areas and identify the root cause for poor quality.</span></span>
   
<span data-ttu-id="c2322-115">Teams 管理者として、各ユーザーのすべての通話分析データにアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="c2322-115">As the Teams admin, you get full access to all call analytics data for each user.</span></span> <span data-ttu-id="c2322-116">さらに、Azure Active Directory の役割をサポートスタッフに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="c2322-116">In addition, you can assign Azure Active Directory roles to support staff.</span></span> <span data-ttu-id="c2322-117">これらの役割の詳細については、「[サポートおよびヘルプデスクスタッフへのアクセス許可を付与](set-up-call-analytics.md#give-permission-to-support-and-helpdesk-staff)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2322-117">To learn more about these roles, read [Give permission to support and helpdesk staff](set-up-call-analytics.md#give-permission-to-support-and-helpdesk-staff).</span></span> <span data-ttu-id="c2322-118">[各チームがどのような役割をサポート](#what-does-each-teams-support-role-do)していても、次のようにしてください。</span><span class="sxs-lookup"><span data-stu-id="c2322-118">Don't miss [What does each Teams Support role do?](#what-does-each-teams-support-role-do) below.</span></span>

## <a name="where-to-find-per-user-call-analytics"></a><span data-ttu-id="c2322-119">ユーザーごとの通話分析を表示する場所</span><span class="sxs-lookup"><span data-stu-id="c2322-119">Where to find per-user call analytics</span></span>

<span data-ttu-id="c2322-120">ユーザーのすべての通話情報とデータを表示するには、 [Teams 管理センター](https://admin.teams.microsoft.com)に移動します。</span><span class="sxs-lookup"><span data-stu-id="c2322-120">To see all call information and data for a user, go to the [Teams admin center](https://admin.teams.microsoft.com).</span></span> <span data-ttu-id="c2322-121">[**ユーザー**] の下でユーザーを選択し、ユーザーのプロファイルページで [**通話履歴**] タブを開きます。</span><span class="sxs-lookup"><span data-stu-id="c2322-121">Under **Users**, select a user and then open the **Call History** tab on the user's profile page.</span></span> <span data-ttu-id="c2322-122">ここでは、過去30日間、そのユーザーのすべての通話と会議が検索されます。</span><span class="sxs-lookup"><span data-stu-id="c2322-122">Here you'll find all calls and meetings for that user for the last 30 days.</span></span>

![すべての分析ユーザーデータのスクリーンショット](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image1.png)

<span data-ttu-id="c2322-124">詳細なメディアとネットワークの統計情報など、特定のセッションに関する追加情報を取得するには、セッションをクリックして詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="c2322-124">To get additional information about a given session, including detailed media and networking statistics, click a session to see the details.</span></span>

![通話分析のユーザーセッションデータのスクリーンショット](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image2.png)
  
## <a name="what-does-each-teams-support-role-do"></a><span data-ttu-id="c2322-126">各チームはどのような役割をサポートしていますか?</span><span class="sxs-lookup"><span data-stu-id="c2322-126">What does each Teams Support role do?</span></span>

<span data-ttu-id="c2322-127">**チームのコミュニケーションサポートスペシャリスト**(Tier 1 のサポート) が、基本的な通話品質の問題を処理します。</span><span class="sxs-lookup"><span data-stu-id="c2322-127">The **Teams communications support specialist** (Tier 1 support) handles basic call-quality problems.</span></span> <span data-ttu-id="c2322-128">会議に関する問題は調査しません。</span><span class="sxs-lookup"><span data-stu-id="c2322-128">They don't investigate issues with meetings.</span></span> <span data-ttu-id="c2322-129">代わりに、関連情報を収集し、コミュニケーション サポート エンジニアにエスカレートします。</span><span class="sxs-lookup"><span data-stu-id="c2322-129">Instead, they collect related information and then escalate to a communications support engineer.</span></span> 

<span data-ttu-id="c2322-130">**Teams 通信サポートエンジニア**(Tier 2 サポート) では、チーム通信サポートスペシャリストから非表示になっている詳細な通話ログに情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c2322-130">The **Teams communications support engineer** (Tier 2 support) sees information in detailed call logs that are hidden from the Teams communications support specialist.</span></span> <span data-ttu-id="c2322-131">以下の表は、各 Teams コミュニケーションサポートロールで利用できる情報を示しています。</span><span class="sxs-lookup"><span data-stu-id="c2322-131">The table below lists the information available to each Teams communication support role.</span></span>

<span data-ttu-id="c2322-132">次の表は、各コミュニケーションサポートロールで利用可能なユーザーごとの情報を示しています。</span><span class="sxs-lookup"><span data-stu-id="c2322-132">The following table tells you what per-user information is available for each communications support role.</span></span>

|<span data-ttu-id="c2322-133">**アクティビティ**</span><span class="sxs-lookup"><span data-stu-id="c2322-133">**Activity**</span></span>|<span data-ttu-id="c2322-134">**詳しく**</span><span class="sxs-lookup"><span data-stu-id="c2322-134">**Information**</span></span>|<span data-ttu-id="c2322-135">コミュニケーションサポート**スペシャリスト**が表示する内容</span><span class="sxs-lookup"><span data-stu-id="c2322-135">What the communications support **specialist** sees</span></span>|<span data-ttu-id="c2322-136">通信サポート**エンジニア**が見ることができる内容</span><span class="sxs-lookup"><span data-stu-id="c2322-136">What the communications support **engineer** sees</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c2322-137">**通話**</span><span class="sxs-lookup"><span data-stu-id="c2322-137">**Calls**</span></span> <br/> |<span data-ttu-id="c2322-138">発信者の名前</span><span class="sxs-lookup"><span data-stu-id="c2322-138">Caller name</span></span>  <br/> |<span data-ttu-id="c2322-139">エージェントが検索したユーザーの名前のみ。</span><span class="sxs-lookup"><span data-stu-id="c2322-139">Only the name of the user for whom the agent searched.</span></span>  <br/> |<span data-ttu-id="c2322-140">ユーザー名。</span><span class="sxs-lookup"><span data-stu-id="c2322-140">User name.</span></span>  <br/> |
||<span data-ttu-id="c2322-141">受信者の名前</span><span class="sxs-lookup"><span data-stu-id="c2322-141">Recipient name</span></span>  <br/> |<span data-ttu-id="c2322-142">内部ユーザーまたは外部ユーザーとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="c2322-142">Shows as Internal User or External User.</span></span>  <br/> |<span data-ttu-id="c2322-143">受信者の名前。</span><span class="sxs-lookup"><span data-stu-id="c2322-143">Recipient name.</span></span>  <br/> |
||<span data-ttu-id="c2322-144">発信者の電話番号</span><span class="sxs-lookup"><span data-stu-id="c2322-144">Caller phone number</span></span>  <br/> |<span data-ttu-id="c2322-145">最後の3桁を除くすべての電話番号は、アスタリスク記号で隠蔽されています。</span><span class="sxs-lookup"><span data-stu-id="c2322-145">Entire phone number except last three digits are obfuscated with asterisk symbols.</span></span> <span data-ttu-id="c2322-146">たとえば、15552823 \* \* \* とします。</span><span class="sxs-lookup"><span data-stu-id="c2322-146">For example, 15552823\*\*\*.</span></span>  <br/> |<span data-ttu-id="c2322-147">最後の3桁を除くすべての電話番号は、アスタリスク記号で隠蔽されています。</span><span class="sxs-lookup"><span data-stu-id="c2322-147">Entire phone number except last three digits are obfuscated with asterisk symbols.</span></span> <span data-ttu-id="c2322-148">たとえば、15552823 \* \* \* とします。</span><span class="sxs-lookup"><span data-stu-id="c2322-148">For example, 15552823\*\*\*.</span></span>  <br/> |
||<span data-ttu-id="c2322-149">受信者の電話番号</span><span class="sxs-lookup"><span data-stu-id="c2322-149">Recipient phone number</span></span>  <br/> |<span data-ttu-id="c2322-150">最後の3桁を除くすべての電話番号は、アスタリスク記号で隠蔽されています。</span><span class="sxs-lookup"><span data-stu-id="c2322-150">Entire phone number except last three digits are obfuscated with asterisk symbols.</span></span> <span data-ttu-id="c2322-151">たとえば、15552823 \* \* \* とします。</span><span class="sxs-lookup"><span data-stu-id="c2322-151">For example, 15552823\*\*\*.</span></span>  <br/> |<span data-ttu-id="c2322-152">最後の3桁を除くすべての電話番号は、アスタリスク記号で隠蔽されています。</span><span class="sxs-lookup"><span data-stu-id="c2322-152">Entire phone number except last three digits are obfuscated with asterisk symbols.</span></span> <span data-ttu-id="c2322-153">たとえば、15552823 \* \* \* とします。</span><span class="sxs-lookup"><span data-stu-id="c2322-153">For example, 15552823\*\*\*.</span></span>  <br/> |
||<span data-ttu-id="c2322-154">**通話の詳細**  > **[詳細設定**] タブ</span><span class="sxs-lookup"><span data-stu-id="c2322-154">**Call Details** > **Advanced** tab</span></span> <br/> |<span data-ttu-id="c2322-155">情報は表示されません。</span><span class="sxs-lookup"><span data-stu-id="c2322-155">Information not shown.</span></span>  <br/> |<span data-ttu-id="c2322-156">デバイス名、IP アドレス、サブネットマッピングなど、すべての詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c2322-156">All details shown, such as device names, IP address, subnet mapping, and more.</span></span>  <br/> |
||<span data-ttu-id="c2322-157">**通話の詳細**  > **[詳細設定**  >  ][**デバッグ**] タブ</span><span class="sxs-lookup"><span data-stu-id="c2322-157">**Call Details** > **Advanced** > **Debug** tab</span></span> <br/> |<span data-ttu-id="c2322-158">情報は表示されません。</span><span class="sxs-lookup"><span data-stu-id="c2322-158">Information not shown.</span></span>  <br/> |<span data-ttu-id="c2322-159">DNS サフィックスや SSID などのすべての詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c2322-159">All details shown, such as DNS suffix and SSID.</span></span>  <br/> |
|<span data-ttu-id="c2322-160">**会議**</span><span class="sxs-lookup"><span data-stu-id="c2322-160">**Meetings**</span></span> <br/> |<span data-ttu-id="c2322-161">参加者名</span><span class="sxs-lookup"><span data-stu-id="c2322-161">Participant names</span></span>  <br/> |<span data-ttu-id="c2322-162">エージェントが検索したユーザーの名前のみ。</span><span class="sxs-lookup"><span data-stu-id="c2322-162">Only the name of the user for whom the agent searched.</span></span> <span data-ttu-id="c2322-163">内部ユーザーまたは外部ユーザーとして識別された他の参加者。</span><span class="sxs-lookup"><span data-stu-id="c2322-163">Other participants identified as Internal User or External User.</span></span>  <br/> |<span data-ttu-id="c2322-164">すべての名前が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c2322-164">All names shown.</span></span>  <br/> |
||<span data-ttu-id="c2322-165">参加者数</span><span class="sxs-lookup"><span data-stu-id="c2322-165">Participant count</span></span>  <br/> |<span data-ttu-id="c2322-166">参加者の数。</span><span class="sxs-lookup"><span data-stu-id="c2322-166">Number of participants.</span></span>  <br/> |<span data-ttu-id="c2322-167">参加者の数。</span><span class="sxs-lookup"><span data-stu-id="c2322-167">Number of participants.</span></span>  <br/> |
||<span data-ttu-id="c2322-168">セッションの詳細</span><span class="sxs-lookup"><span data-stu-id="c2322-168">Session details</span></span>  <br/> |<span data-ttu-id="c2322-169">例外と共に表示されるセッションの詳細。</span><span class="sxs-lookup"><span data-stu-id="c2322-169">Session details shown with exceptions.</span></span> <span data-ttu-id="c2322-170">エージェントで検索されたユーザーの名前のみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c2322-170">Only the name of the user for whom the agent searched is shown.</span></span> <span data-ttu-id="c2322-171">内部ユーザーまたは外部ユーザーとして識別された他の参加者。</span><span class="sxs-lookup"><span data-stu-id="c2322-171">Other participants identified as Internal User or External User.</span></span> <span data-ttu-id="c2322-172">アスタリスク記号が付いた、電話番号の最後の3桁が隠蔽されています。</span><span class="sxs-lookup"><span data-stu-id="c2322-172">Last three digits of telephone number obfuscated with asterisk symbols.</span></span>  <br/> |<span data-ttu-id="c2322-173">セッションの詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c2322-173">Session details shown.</span></span> <span data-ttu-id="c2322-174">ユーザー名とセッションの詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c2322-174">User names and session details shown.</span></span> <span data-ttu-id="c2322-175">アスタリスク記号が付いた、電話番号の最後の3桁が隠蔽されています。</span><span class="sxs-lookup"><span data-stu-id="c2322-175">Last three digits of telephone number obfuscated with asterisk symbols.</span></span>  <br/> |
||||
  
## <a name="troubleshoot-user-call-quality-problems"></a><span data-ttu-id="c2322-176">ユーザーの通話品質の問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="c2322-176">Troubleshoot user call quality problems</span></span> 

1. <span data-ttu-id="c2322-177">Teams 管理センターを開き ( https://admin.teams.microsoft.com) チーム通信サポートまたは teams 管理者の資格情報でサインインします。</span><span class="sxs-lookup"><span data-stu-id="c2322-177">Open the Teams admin center (https://admin.teams.microsoft.com) and sign in with your Teams communications support or Teams admin credentials.</span></span>

2. <span data-ttu-id="c2322-178">**ダッシュボード**の [**ユーザー検索**] で、通話のトラブルシューティングを行うユーザーの名前または SIP アドレスの入力を開始するか、[**ユーザーの表示**] を選択してユーザーのリストを表示します。</span><span class="sxs-lookup"><span data-stu-id="c2322-178">On the **Dashboard**, in **User Search**, start typing either the name or SIP address of the user whose calls you want to troubleshoot, or select **View users** to see a list of users.</span></span>

3. <span data-ttu-id="c2322-179">リストからユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="c2322-179">Select the user from the list.</span></span>

4. <span data-ttu-id="c2322-180">[**通話履歴**] を選択し、トラブルシューティングする通話または会議を選択します。</span><span class="sxs-lookup"><span data-stu-id="c2322-180">Select **Call history**, and then select the call or meeting that you want to troubleshoot.</span></span>
    
5. <span data-ttu-id="c2322-181">[**詳細**] タブを選択して、通話の品質が低下したり、接続の問題が発生していることを示す黄色と赤色アイテムを探します。</span><span class="sxs-lookup"><span data-stu-id="c2322-181">Select the **Advanced** tab, and then look for yellow and red items which indicate poor call quality or connection problems.</span></span>
    
    <span data-ttu-id="c2322-182">各通話や会議のセッションの詳細において、小さな問題は黄色で表示されます。</span><span class="sxs-lookup"><span data-stu-id="c2322-182">In the session details for each call or meeting, minor issues appear in yellow.</span></span> <span data-ttu-id="c2322-183">黄色で表示されているものは、通常の範囲外であり、問題の原因となっている可能性がありますが、この問題の主な原因ではない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c2322-183">If something is yellow, it's outside of normal range, and it may be contributing to the problem, but it's unlikely to be the main cause of the problem.</span></span> <span data-ttu-id="c2322-184">赤色の場合は重大な問題であり、このセッションの通話が低品質である主な原因の可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c2322-184">If something is red, it's a significant problem, and it's likely the main cause of the poor call quality for this session.</span></span> 
      
<span data-ttu-id="c2322-185">まれなケースとして、オーディオセッションの品質エクスペリエンスデータが受信されないことがあります。</span><span class="sxs-lookup"><span data-stu-id="c2322-185">In rare cases, Quality of Experience data isn't received for audio sessions.</span></span> <span data-ttu-id="c2322-186">多くの場合、これは、ドロップされた通話、またはクライアントとの接続が終了したときに発生します。</span><span class="sxs-lookup"><span data-stu-id="c2322-186">Often this is caused by the a dropped call or when the connection with the client terminates.</span></span> <span data-ttu-id="c2322-187">このような場合、セッションの評価は**使用**できません。</span><span class="sxs-lookup"><span data-stu-id="c2322-187">When this occurs, the session rating is **unavailable**.</span></span>
  
<span data-ttu-id="c2322-188">Quality of Experience (QoE) データを持つオーディオセッションについては、次の表では、セッションが**低**品質と見なされる主な問題について説明します。</span><span class="sxs-lookup"><span data-stu-id="c2322-188">For audio sessions that do have Quality of Experience (QoE) data, the following table describes major issues that qualify a session as **poor**.</span></span>
  
|<span data-ttu-id="c2322-189">**問題**</span><span class="sxs-lookup"><span data-stu-id="c2322-189">**Issue**</span></span>|<span data-ttu-id="c2322-190">**領域**</span><span class="sxs-lookup"><span data-stu-id="c2322-190">**Area**</span></span>|<span data-ttu-id="c2322-191">**説明**</span><span class="sxs-lookup"><span data-stu-id="c2322-191">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c2322-192">通話設定</span><span class="sxs-lookup"><span data-stu-id="c2322-192">Call setup</span></span>  <br/> |<span data-ttu-id="c2322-193">セッション</span><span class="sxs-lookup"><span data-stu-id="c2322-193">Session</span></span>  <br/> |<span data-ttu-id="c2322-194">エラー コード Ms-diag 20-29 は、設定が失敗したことを示します。</span><span class="sxs-lookup"><span data-stu-id="c2322-194">The error code Ms-diag 20-29 indicates the call setup failed.</span></span> <span data-ttu-id="c2322-195">ユーザーが通話または会議に参加できませんでした。</span><span class="sxs-lookup"><span data-stu-id="c2322-195">The user couldn't join the call or meeting.</span></span>  <br/> |
|<span data-ttu-id="c2322-196">音声ネットワークよって低品質と分類された通話</span><span class="sxs-lookup"><span data-stu-id="c2322-196">Audio network classified poor call</span></span>  <br/> |<span data-ttu-id="c2322-197">セッション</span><span class="sxs-lookup"><span data-stu-id="c2322-197">Session</span></span>  <br/> |<span data-ttu-id="c2322-198">ネットワーク品質の問題 (パケット損失、ジッタ、NMOS 劣化、RTT、隠し比率) が発生しました。</span><span class="sxs-lookup"><span data-stu-id="c2322-198">Network quality issues (such as packet loss, jitter, NMOS degradation, RTT, or concealed ratio) were encountered.</span></span>  <br/> |
|<span data-ttu-id="c2322-199">デバイスが機能しない</span><span class="sxs-lookup"><span data-stu-id="c2322-199">Device not functioning</span></span>  <br/> |<span data-ttu-id="c2322-200">デバイス</span><span class="sxs-lookup"><span data-stu-id="c2322-200">Device</span></span>  <br/> | <span data-ttu-id="c2322-201">デバイスが正常に機能していない。</span><span class="sxs-lookup"><span data-stu-id="c2322-201">A device isn't functioning correctly.</span></span> <span data-ttu-id="c2322-202">機能していないデバイスの割合:</span><span class="sxs-lookup"><span data-stu-id="c2322-202">Device not functioning ratios are :</span></span> <br/>  <span data-ttu-id="c2322-203">DeviceRenderNotFunctioningEventRatio >= 0.005</span><span class="sxs-lookup"><span data-stu-id="c2322-203">DeviceRenderNotFunctioningEventRatio >= 0.005</span></span> <br/>  <span data-ttu-id="c2322-204">DeviceCaptureNotFunctioningEventRatio >= 0.005</span><span class="sxs-lookup"><span data-stu-id="c2322-204">DeviceCaptureNotFunctioningEventRatio >= 0.005</span></span> <br/> |
   

## <a name="related-topics"></a><span data-ttu-id="c2322-205">関連トピック</span><span class="sxs-lookup"><span data-stu-id="c2322-205">Related topics</span></span>

[<span data-ttu-id="c2322-206">ユーザーごとの通話分析を設定する</span><span class="sxs-lookup"><span data-stu-id="c2322-206">Set up per-user call analytics</span></span>](set-up-call-analytics.md)



  
 
