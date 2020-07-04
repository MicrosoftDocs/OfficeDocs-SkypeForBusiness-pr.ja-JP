---
title: 通話分析を使用して低品質な通話をトラブルシューティングする
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney
ms.date: 03/08/2019
ms.topic: article
ms.assetid: 66945036-ae87-4c08-a0bb-984e50d6b009
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
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.directrouting.callanalytics
- ms.teamsadmincenter.users.activity.audioqualitycolumn
- Reporting
description: Microsoft Teams や Skype for Business の通話や会議に関する問題のトラブルシューティングを行うには、デバイス、ネットワーク、接続に関わる通話分析の詳細を使用します。
ms.openlocfilehash: 71a1e1c339c502da5cbbf998c75e758f2bbe3be2
ms.sourcegitcommit: f586d2765195dbd5b7cf65615a03a1cb098c5466
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "44665249"
---
# <a name="use-call-analytics-to-troubleshoot-poor-call-quality"></a><span data-ttu-id="6446a-103">通話分析を使用して低品質な通話をトラブルシューティングする</span><span class="sxs-lookup"><span data-stu-id="6446a-103">Use Call Analytics to troubleshoot poor call quality</span></span>

<span data-ttu-id="6446a-104">通話分析を使用すると、Microsoft Teams や Skype for Business の通話や接続に関する問題をトラブルシューティングできます。</span><span class="sxs-lookup"><span data-stu-id="6446a-104">Call Analytics helps you troubleshoot call or connection problems with Microsoft Teams and Skype for Business.</span></span> <span data-ttu-id="6446a-105">通話分析は、Microsoft 365 または Office 365 アカウントの各ユーザーが行う通話および会議のデバイス、ネットワーク、および接続性についての詳細情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="6446a-105">Call Analytics shows detailed information about the devices, networks, and connectivity for the calls and meetings of each user in your Microsoft 365 or Office 365 account.</span></span> <span data-ttu-id="6446a-106">通話分析に建物、サイト、テナント情報が追加された場合は、通話とセッションごとに表示されます。</span><span class="sxs-lookup"><span data-stu-id="6446a-106">If building, site, and tenant information has been added to Call Analytics, it will also be shown for each call and session.</span></span> <span data-ttu-id="6446a-107">通話分析を通して得られる情報は、ユーザーの通話や会議の品質を低下させた原因を把握するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="6446a-107">Information available via Call Analytics can help you figure out why a user had a poor call or meeting experience.</span></span> 
  
## <a name="call-analytics-permissions"></a><span data-ttu-id="6446a-108">通話分析のアクセス許可</span><span class="sxs-lookup"><span data-stu-id="6446a-108">Call Analytics permissions</span></span>

<span data-ttu-id="6446a-109">管理者として、通話分析のすべての機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="6446a-109">As the admin, you get full access to all the features of Call Analytics.</span></span> <span data-ttu-id="6446a-110">さらに、Azure Active Directory の役割をサポートスタッフに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="6446a-110">In addition, you can assign Azure Active Directory roles to support staff.</span></span> <span data-ttu-id="6446a-111">通話分析の一部の情報のビューのみが必要なユーザーには、Teams コミュニケーション サポート スペシャリストの役割を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="6446a-111">Assign the Teams communications support specialist role to users who should have a limited view of Call Analytics.</span></span> <span data-ttu-id="6446a-112">通話分析の完全な機能にアクセスする必要があるユーザーには、Teams コミュニケーション サポート エンジニアの役割を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="6446a-112">Assign the Teams communications support engineer role to users who need access to the full functionality of Call Analytics.</span></span> <span data-ttu-id="6446a-113">両方のアクセス許可レベルを設定すると、Microsoft Teams 管理センターのその他の部分にアクセスできなくなります。</span><span class="sxs-lookup"><span data-stu-id="6446a-113">Both permission levels prevent access to the rest of the Microsoft Teams admin center.</span></span>

<span data-ttu-id="6446a-114">コミュニケーション サポート スペシャリストが、基本的な通話の品質に関する問題を解決します。</span><span class="sxs-lookup"><span data-stu-id="6446a-114">Communications support specialists handle basic call-quality problems.</span></span> <span data-ttu-id="6446a-115">会議に関する問題は調査しません。</span><span class="sxs-lookup"><span data-stu-id="6446a-115">They don't investigate issues with meetings.</span></span> <span data-ttu-id="6446a-116">代わりに、関連情報を収集し、コミュニケーション サポート エンジニアにエスカレートします。</span><span class="sxs-lookup"><span data-stu-id="6446a-116">Instead, they collect related information and then escalate to a communications support engineer.</span></span> <span data-ttu-id="6446a-117">コミュニケーション サポート エンジニアは、コミュニケーション サポート スペシャリストに対して表示されない詳細な通話ログの情報を確認します。</span><span class="sxs-lookup"><span data-stu-id="6446a-117">Communications support engineers see information in detailed call logs that's hidden from communications support specialists.</span></span> <span data-ttu-id="6446a-118">次の表では、通話分析を利用する際に、コミュニケーション サポート スペシャリストとコミュニケーション サポート エンジニアが使用できる情報の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="6446a-118">The following table gives an overview of information available to communications support specialists and communications support engineers when they use Call Analytics.</span></span>

<span data-ttu-id="6446a-119">割り当てられているアクセス許可レベルによって、アクセスできる情報の種類が決まります。</span><span class="sxs-lookup"><span data-stu-id="6446a-119">The permissions level assigned to you determines what type of information you have access to in Call Analytics:</span></span>
  
- <span data-ttu-id="6446a-120">**Teams サービス管理者または Teams コミュニケーション管理者**: 通話分析および Microsoft Teams 管理センターのすべての情報にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="6446a-120">**Teams service administrator or Teams communications administrator**: You have access to all the information in Call Analytics and in the Microsoft Teams admin center.</span></span>
    
- <span data-ttu-id="6446a-121">**Teams コミュニケーション サポート スペシャリスト**: データの一部だけが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6446a-121">**Teams communications support specialist**: You see a limited set of data in Call Analytics.</span></span> <span data-ttu-id="6446a-122">通話のトラブルシューティングを行うことはできますが、会議に関する問題は Teams コミュニケーション サポート エンジニアに引き継がれます。</span><span class="sxs-lookup"><span data-stu-id="6446a-122">You can troubleshoot calls, but you'll hand off problems with meetings to a Teams communications support engineer.</span></span> <span data-ttu-id="6446a-123">その他の Microsoft Teams 管理センターにはアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="6446a-123">You don't have access to the rest of the Microsoft Teams admin center.</span></span>
    
- <span data-ttu-id="6446a-124">**Teams コミュニケーション サポート エンジニア**: 通話分析のすべてのデータを表示し、通話と会議の両方の問題を解決することができます。</span><span class="sxs-lookup"><span data-stu-id="6446a-124">**Teams communications support engineer**: You see all available data in Call Analytics and can help troubleshoot problems with both calls and meetings.</span></span> <span data-ttu-id="6446a-125">その他の Microsoft Teams 管理センターにはアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="6446a-125">You don't have access to the rest of the Microsoft Teams admin center.</span></span>
    
> [!NOTE]
> <span data-ttu-id="6446a-126">コミュニケーション サポート スペシャリストの役割は、サポート階層 1 と同等です。コミュニケーション サポート エンジニアの役割は、サポート階層 2 と同じです。</span><span class="sxs-lookup"><span data-stu-id="6446a-126">The communications support specialist role is equivalent to tier 1 support and the communications support engineer role is equivalent to tier 2 support.</span></span>

<span data-ttu-id="6446a-127">Teams 管理者の役割の詳細については、「[Microsoft Teams の管理者の役割を使用して Teams を管理する](using-admin-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6446a-127">For more information about Teams admin roles, see [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md).</span></span> <span data-ttu-id="6446a-128">Teams コミュニケーション サポート スペシャリストおよび Teams コミュニケーション サポート エンジニアの役割の詳細については、「[通話分析を設定する](set-up-call-analytics.md#set-call-analytics-permissions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6446a-128">For a detailed comparison of the Teams communications support specialist and Teams communications support engineer roles, see [Set up Call Analytics](set-up-call-analytics.md#set-call-analytics-permissions)</span></span> 
  
<span data-ttu-id="6446a-129">アクセス許可に関してサポートが必要な場合は、Teams と Skype for Business の管理者に問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="6446a-129">See your Teams and Skype for Business admin if you need help with permissions.</span></span>
  
## <a name="troubleshoot-call-quality-problems-using-call-analytics"></a><span data-ttu-id="6446a-130">通話分析を使用して通話品質の問題をトラブルシューティングする</span><span class="sxs-lookup"><span data-stu-id="6446a-130">Troubleshoot call quality problems using Call Analytics</span></span>

1. <span data-ttu-id="6446a-131">Teams のコミュニケーション サポートまたは Teams 管理者の資格情報でサインインします。</span><span class="sxs-lookup"><span data-stu-id="6446a-131">Sign in with your Teams communications support or Teams admin credentials.</span></span>

2. <span data-ttu-id="6446a-132">Web ブラウザーで、*https://admin.teams.microsoft.com* にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="6446a-132">In your web browser go to *https://admin.teams.microsoft.com*.</span></span>
    
3. <span data-ttu-id="6446a-133">**ダッシュボード**で、**ユーザー検索**に通話のトラブルシューティンするユーザーの名前または sip アドレスのいずれかを入力するか、[**ユーザーを表示**] を選択してユーザーのリストを表示します。</span><span class="sxs-lookup"><span data-stu-id="6446a-133">On the **Dashboard**, in **User Search**, start typing either the name or sip address of the user whose calls you want to troubleshoot or select **View users** to see a list of users.</span></span>
    
    ![通話分析のユーザー検索のスクリーンショット](media/use-call-analytics-to-troubleshoot-image-1.png)
  
4. <span data-ttu-id="6446a-135">リストからユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="6446a-135">Select the user from the list.</span></span>

5. <span data-ttu-id="6446a-136">[**通話履歴**] を選択し、トラブルシューティングする通話または会議を選択します。</span><span class="sxs-lookup"><span data-stu-id="6446a-136">Select **Call history**, and then select the call or meeting that you want to troubleshoot.</span></span>  <span data-ttu-id="6446a-137">最大500レコードが返されます。</span><span class="sxs-lookup"><span data-stu-id="6446a-137">A maximum of 500 records will be returned.</span></span>
    
    ![ユーザーの通話履歴ページのスクリーンショット。](media/use-call-analytics-to-troubleshoot-image-2.png)
  
6. <span data-ttu-id="6446a-139">[**詳細**] タブを選択して、通話の品質が低下したり、接続の問題が発生していることを示す黄色と赤色アイテムを探します。</span><span class="sxs-lookup"><span data-stu-id="6446a-139">Select the **Advanced** tab, and then look for yellow and red items which indicate poor call quality or connection problems.</span></span>
    
    <span data-ttu-id="6446a-140">各通話や会議のセッションの詳細において、小さな問題は黄色で表示されます。</span><span class="sxs-lookup"><span data-stu-id="6446a-140">In the session details for each call or meeting, minor issues appear in yellow.</span></span> <span data-ttu-id="6446a-141">(たとえば、次のスクリーンショットでは、平均ジッタ、最大ジッタ、平均パケット損失率として黄色で値が指定されています)。黄色は通常の範囲外で、問題の原因になっている可能性がありますが、問題の主な原因になることはほとんどありません。</span><span class="sxs-lookup"><span data-stu-id="6446a-141">(For example, in the following screenshot, the values are in yellow for Average jitter, Max jitter, and Average packet loss rate.) If something is yellow, it's outside of normal range, and it may be contributing to the problem, but it's unlikely to be the main cause of the problem.</span></span> <span data-ttu-id="6446a-142">赤色の場合は重大な問題であり、このセッションの通話が低品質である主な原因の可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6446a-142">If something is red, it's a significant problem, and it's likely the main cause of the poor call quality for this session.</span></span> 
    
    ![<span data-ttu-id="6446a-143">ユーザーの通話履歴の [詳細設定] タブのスクリーンショット</span><span class="sxs-lookup"><span data-stu-id="6446a-143">Screenshot of the Advanced tab of a user's Call history</span></span> ](media/use-call-analytics-to-troubleshoot-image-3.png)
  
<span data-ttu-id="6446a-144">稀に、音声セッションの品質のデータは受信されません。</span><span class="sxs-lookup"><span data-stu-id="6446a-144">In rare cases, quality of experience data isn't received for audio sessions.</span></span> <span data-ttu-id="6446a-145">多くの場合、これは通話の中断、クライアントとの接続が終了することが原因です。</span><span class="sxs-lookup"><span data-stu-id="6446a-145">Often this is caused by the call dropping and connection with the client terminating.</span></span> <span data-ttu-id="6446a-146">このような場合、セッションの評価は**使用**できません。</span><span class="sxs-lookup"><span data-stu-id="6446a-146">When this occurs, the session rating is **unavailable**.</span></span>
  
<span data-ttu-id="6446a-147">体験品質 (QoE) データがある音声セッションについては、次の表において、セッションを**低品質**とする主な問題について説明します。</span><span class="sxs-lookup"><span data-stu-id="6446a-147">For audio sessions that do have quality of experience (QoE) data, the following table describes major issues that qualify a session as **poor**.</span></span>
  
|<span data-ttu-id="6446a-148">**問題**</span><span class="sxs-lookup"><span data-stu-id="6446a-148">**Issue**</span></span>|<span data-ttu-id="6446a-149">**領域**</span><span class="sxs-lookup"><span data-stu-id="6446a-149">**Area**</span></span>|<span data-ttu-id="6446a-150">**説明**</span><span class="sxs-lookup"><span data-stu-id="6446a-150">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6446a-151">通話設定</span><span class="sxs-lookup"><span data-stu-id="6446a-151">Call setup</span></span>  <br/> |<span data-ttu-id="6446a-152">セッション</span><span class="sxs-lookup"><span data-stu-id="6446a-152">Session</span></span>  <br/> |<span data-ttu-id="6446a-153">エラー コード Ms-diag 20-29 は、設定が失敗したことを示します。</span><span class="sxs-lookup"><span data-stu-id="6446a-153">The error code Ms-diag 20-29 indicates the call setup failed.</span></span> <span data-ttu-id="6446a-154">ユーザーが通話または会議に参加できませんでした。</span><span class="sxs-lookup"><span data-stu-id="6446a-154">The user couldn't join the call or meeting.</span></span>  <br/> |
|<span data-ttu-id="6446a-155">音声ネットワークよって低品質と分類された通話</span><span class="sxs-lookup"><span data-stu-id="6446a-155">Audio network classified poor call</span></span>  <br/> |<span data-ttu-id="6446a-156">セッション</span><span class="sxs-lookup"><span data-stu-id="6446a-156">Session</span></span>  <br/> |<span data-ttu-id="6446a-157">ネットワーク品質の問題 (パケット損失、ジッタ、NMOS 劣化、RTT、隠し比率) が発生しました。</span><span class="sxs-lookup"><span data-stu-id="6446a-157">Network quality issues (such as packet loss, jitter, NMOS degradation, RTT, or concealed ratio) were encountered.</span></span> <span data-ttu-id="6446a-158">低品質な通話の分類に使用される条件の詳細については、この[Microsoft blog 記事](https://go.microsoft.com/fwlink/p/?linkid=852133)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6446a-158">For more information about the conditions used to classify poor calls, see this [Microsoft blog post](https://go.microsoft.com/fwlink/p/?linkid=852133).</span></span>  <br/> |
|<span data-ttu-id="6446a-159">デバイスが機能しない</span><span class="sxs-lookup"><span data-stu-id="6446a-159">Device not functioning</span></span>  <br/> |<span data-ttu-id="6446a-160">デバイス</span><span class="sxs-lookup"><span data-stu-id="6446a-160">Device</span></span>  <br/> | <span data-ttu-id="6446a-161">デバイスが正常に機能していない。</span><span class="sxs-lookup"><span data-stu-id="6446a-161">A device isn't functioning correctly.</span></span> <span data-ttu-id="6446a-162">機能していないデバイスの割合:</span><span class="sxs-lookup"><span data-stu-id="6446a-162">Device not functioning ratios are :</span></span> <br/>  <span data-ttu-id="6446a-163">DeviceRenderNotFunctioningEventRatio >= 0.005</span><span class="sxs-lookup"><span data-stu-id="6446a-163">DeviceRenderNotFunctioningEventRatio >= 0.005</span></span> <br/>  <span data-ttu-id="6446a-164">DeviceCaptureNotFunctioningEventRatio >= 0.005</span><span class="sxs-lookup"><span data-stu-id="6446a-164">DeviceCaptureNotFunctioningEventRatio >= 0.005</span></span> <br/> |
   
## <a name="related-topics"></a><span data-ttu-id="6446a-165">関連トピック</span><span class="sxs-lookup"><span data-stu-id="6446a-165">Related topics</span></span>
[<span data-ttu-id="6446a-166">通話分析を設定する</span><span class="sxs-lookup"><span data-stu-id="6446a-166">Set up Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="6446a-167">通話分析および通話品質ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="6446a-167">Call Analytics and Call Quality Dashboard</span></span>](difference-between-call-analytics-and-call-quality-dashboard.md)

  
 
