---
title: 通話分析を使用して低品質の通話をトラブルシューティングする
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
- ms.teamsadmincenter.directrouting.callanalytics
- ms.teamsadmincenter.users.activity.audioqualitycolumn
ms.custom:
- Reporting
description: デバイス、ネットワーク、接続に関する通話分析の詳細を使用して、Microsoft Teams および Skype for Business の通話と会議でのユーザーの問題のトラブルシューティングを行います。
ms.openlocfilehash: e8b1fe4bbad2b744310d0b609fdc6c6d5a23fea2
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2020
ms.locfileid: "41707723"
---
# <a name="use-call-analytics-to-troubleshoot-poor-call-quality"></a><span data-ttu-id="fe945-103">通話分析を使用して低品質の通話をトラブルシューティングする</span><span class="sxs-lookup"><span data-stu-id="fe945-103">Use Call Analytics to troubleshoot poor call quality</span></span>

<span data-ttu-id="fe945-104">通話分析は、Microsoft Teams と Skype for Business の通話や接続の問題のトラブルシューティングに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="fe945-104">Call Analytics helps you troubleshoot call or connection problems with Microsoft Teams and Skype for Business.</span></span> <span data-ttu-id="fe945-105">通話分析には、Office 365 アカウントの各ユーザーの通話と会議のデバイス、ネットワーク、接続に関する詳細情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="fe945-105">Call Analytics shows detailed information about the devices, networks, and connectivity for the calls and meetings of each user in your Office 365 account.</span></span> <span data-ttu-id="fe945-106">通話分析に建物、サイト、テナントの情報が追加されている場合は、通話とセッションごとにも表示されます。</span><span class="sxs-lookup"><span data-stu-id="fe945-106">If building, site, and tenant information has been added to Call Analytics, it will also be shown for each call and session.</span></span> <span data-ttu-id="fe945-107">通話分析を通じて提供される情報は、ユーザーが不適切な通話や会議の操作を行った理由を把握するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="fe945-107">Information available via Call Analytics can help you figure out why a user had a poor call or meeting experience.</span></span> 
  
## <a name="call-analytics-permissions"></a><span data-ttu-id="fe945-108">通話分析のアクセス許可</span><span class="sxs-lookup"><span data-stu-id="fe945-108">Call Analytics permissions</span></span>

<span data-ttu-id="fe945-109">管理者として、通話分析の全機能にアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="fe945-109">As the admin, you get full access to all the features of Call Analytics.</span></span> <span data-ttu-id="fe945-110">また、サポートスタッフに Azure Active Directory ロールを割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="fe945-110">In addition, you can assign Azure Active Directory roles to support staff.</span></span> <span data-ttu-id="fe945-111">通話分析の限定されたビューが必要なユーザーにチーム通信のサポートスペシャリストの役割を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="fe945-111">Assign the Teams communications support specialist role to users who should have a limited view of Call Analytics.</span></span> <span data-ttu-id="fe945-112">通話分析の全機能にアクセスする必要があるユーザーに、Teams 通信サポートエンジニアの役割を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="fe945-112">Assign the Teams communications support engineer role to users who need access to the full functionality of Call Analytics.</span></span> <span data-ttu-id="fe945-113">どちらの権限レベルでも、Microsoft Teams 管理センターの残りの部分にはアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="fe945-113">Both permission levels prevent access to the rest of the Microsoft Teams admin center.</span></span>

<span data-ttu-id="fe945-114">通信サポートの専門家が、基本的な通話品質の問題を処理します。</span><span class="sxs-lookup"><span data-stu-id="fe945-114">Communications support specialists handle basic call-quality problems.</span></span> <span data-ttu-id="fe945-115">会議の問題を調査することはありません。</span><span class="sxs-lookup"><span data-stu-id="fe945-115">They don't investigate issues with meetings.</span></span> <span data-ttu-id="fe945-116">代わりに、関連情報を収集し、コミュニケーションサポートエンジニアにエスカレートします。</span><span class="sxs-lookup"><span data-stu-id="fe945-116">Instead, they collect related information and then escalate to a communications support engineer.</span></span> <span data-ttu-id="fe945-117">通信サポートエンジニアは、コミュニケーションサポートスペシャリストから非表示になっている詳細な通話ログに情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="fe945-117">Communications support engineers see information in detailed call logs that's hidden from communications support specialists.</span></span> <span data-ttu-id="fe945-118">次の表では、通話分析を使用している場合の通信サポートスペシャリストと通信サポートエンジニアが利用できる情報の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="fe945-118">The following table gives an overview of information available to communications support specialists and communications support engineers when they use Call Analytics.</span></span>

<span data-ttu-id="fe945-119">割り当てられたアクセス許可レベルによって、通話分析でどの種類の情報にアクセスできるかが決まります。</span><span class="sxs-lookup"><span data-stu-id="fe945-119">The permissions level assigned to you determines what type of information you have access to in Call Analytics:</span></span>
  
- <span data-ttu-id="fe945-120">**Teams サービス管理者またはチームコミュニケーション管理者**: 通話分析および Microsoft Teams 管理センターのすべての情報にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="fe945-120">**Teams service administrator or Teams communications administrator**: You have access to all the information in Call Analytics and in the Microsoft Teams admin center.</span></span>
    
- <span data-ttu-id="fe945-121">**Teams のコミュニケーションサポートスペシャリスト**: 通話分析では、データの一部しか表示されません。</span><span class="sxs-lookup"><span data-stu-id="fe945-121">**Teams communications support specialist**: You see a limited set of data in Call Analytics.</span></span> <span data-ttu-id="fe945-122">通話のトラブルシューティングを行うことはできますが、チームの通信サポートエンジニアに会議の問題を渡すことになります。</span><span class="sxs-lookup"><span data-stu-id="fe945-122">You can troubleshoot calls, but you'll hand off problems with meetings to a Teams communications support engineer.</span></span> <span data-ttu-id="fe945-123">Microsoft Teams 管理センターの残りの部分にはアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="fe945-123">You don't have access to the rest of the Microsoft Teams admin center.</span></span>
    
- <span data-ttu-id="fe945-124">**Teams 通信サポートエンジニア**: 通話分析で利用可能なすべてのデータが表示され、通話と会議の両方に関する問題のトラブルシューティングに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="fe945-124">**Teams communications support engineer**: You see all available data in Call Analytics and can help troubleshoot problems with both calls and meetings.</span></span> <span data-ttu-id="fe945-125">Microsoft Teams 管理センターの残りの部分にはアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="fe945-125">You don't have access to the rest of the Microsoft Teams admin center.</span></span>
    
> [!NOTE]
> <span data-ttu-id="fe945-126">通信サポートスペシャリストの役割は、tier 1 のサポートと同等であり、通信サポートエンジニアの役割は tier 2 サポートと同等です。</span><span class="sxs-lookup"><span data-stu-id="fe945-126">The communications support specialist role is equivalent to tier 1 support and the communications support engineer role is equivalent to tier 2 support.</span></span>

<span data-ttu-id="fe945-127">Teams の管理者ロールの詳細については、「 [Microsoft teams の管理者ロールを使用してチームを管理する](using-admin-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe945-127">For more information about Teams admin roles, see [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md).</span></span> <span data-ttu-id="fe945-128">Teams の通信サポートスペシャリストと Teams の通信サポートエンジニアの役割を詳細に比較するには、「[通話分析を設定](set-up-call-analytics.md#set-call-analytics-permissions)する」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="fe945-128">For a detailed comparison of the Teams communications support specialist and Teams communications support engineer roles, see [Set up Call Analytics](set-up-call-analytics.md#set-call-analytics-permissions)</span></span> 
  
<span data-ttu-id="fe945-129">アクセス許可についてのヘルプが必要な場合は、チームと Skype for Business の管理者にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="fe945-129">See your Teams and Skype for Business admin if you need help with permissions.</span></span>
  
## <a name="troubleshoot-call-quality-problems-using-call-analytics"></a><span data-ttu-id="fe945-130">通話分析を使用して通話品質の問題のトラブルシューティングを行う</span><span class="sxs-lookup"><span data-stu-id="fe945-130">Troubleshoot call quality problems using Call Analytics</span></span>

1. <span data-ttu-id="fe945-131">Teams の通信サポートまたはチーム管理者の資格情報でサインインします。</span><span class="sxs-lookup"><span data-stu-id="fe945-131">Sign in with your Teams communications support or Teams admin credentials.</span></span>

2. <span data-ttu-id="fe945-132">Web ブラウザーで、に*https://admin.teams.microsoft.com*移動します。</span><span class="sxs-lookup"><span data-stu-id="fe945-132">In your web browser go to *https://admin.teams.microsoft.com*.</span></span>
    
3. <span data-ttu-id="fe945-133">**ダッシュボード**の [**ユーザー検索**] で、通話のトラブルシューティングを行うユーザーの名前または sip アドレスの入力を開始するか、[**ユーザーの表示**] を選択してユーザーのリストを表示します。</span><span class="sxs-lookup"><span data-stu-id="fe945-133">On the **Dashboard**, in **User Search**, start typing either the name or sip address of the user whose calls you want to troubleshoot or select **View users** to see a list of users.</span></span>
    
    ![通話分析の [ユーザーの検索] ボックスのスクリーンショット](media/use-call-analytics-to-troubleshoot-image-1.png)
  
4. <span data-ttu-id="fe945-135">リストからユーザーを選びます。</span><span class="sxs-lookup"><span data-stu-id="fe945-135">Select the user from the list.</span></span>

5. <span data-ttu-id="fe945-136">[**通話履歴**] を選択し、トラブルシューティングする通話または会議を選択します。</span><span class="sxs-lookup"><span data-stu-id="fe945-136">Select **Call history**, and then select the call or meeting that you want to troubleshoot.</span></span>
    
    ![ユーザーの [通話履歴] ページのスクリーンショット。](media/use-call-analytics-to-troubleshoot-image-2.png)
  
6. <span data-ttu-id="fe945-138">[**詳細設定**] タブを選択し、良好な音質または接続の問題を示す黄色と赤色の項目を探します。</span><span class="sxs-lookup"><span data-stu-id="fe945-138">Select the **Advanced** tab, and then look for yellow and red items which indicate poor call quality or connection problems.</span></span>
    
    <span data-ttu-id="fe945-139">各通話または会議のセッションの詳細では、小さな問題が黄色で表示されます。</span><span class="sxs-lookup"><span data-stu-id="fe945-139">In the session details for each call or meeting, minor issues appear in yellow.</span></span> <span data-ttu-id="fe945-140">(たとえば、次のスクリーンショットでは、平均ジッター、最大ジッター、平均パケット損失率の値が黄色で指定されています)。黄色で表示されているものは、通常の範囲外であり、問題の原因となっている可能性がありますが、この問題の主な原因ではない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fe945-140">(For example, in the following screenshot, the values are in yellow for Average jitter, Max jitter, and Average packet loss rate.) If something is yellow, it's outside of normal range, and it may be contributing to the problem, but it's unlikely to be the main cause of the problem.</span></span> <span data-ttu-id="fe945-141">赤色の問題は重大な問題であり、このセッションでは通話品質が低下する可能性が高いと考えられます。</span><span class="sxs-lookup"><span data-stu-id="fe945-141">If something is red, it's a significant problem, and it's likely the main cause of the poor call quality for this session.</span></span> 
    
    ![<span data-ttu-id="fe945-142">ユーザーの通話履歴の [詳細設定] タブのスクリーンショット</span><span class="sxs-lookup"><span data-stu-id="fe945-142">Screenshot of the Advanced tab of a user's Call history</span></span> ](media/use-call-analytics-to-troubleshoot-image-3.png)
  
<span data-ttu-id="fe945-143">まれなケースとして、オーディオセッションの品質エクスペリエンスデータが受信されないことがあります。</span><span class="sxs-lookup"><span data-stu-id="fe945-143">In rare cases, quality of experience data isn't received for audio sessions.</span></span> <span data-ttu-id="fe945-144">多くの場合、呼び出しがドロップされ、クライアントが終了して接続されていることが原因です。</span><span class="sxs-lookup"><span data-stu-id="fe945-144">Often this is caused by the call dropping and connection with the client terminating.</span></span> <span data-ttu-id="fe945-145">この場合、セッションの評価は**利用できません**。</span><span class="sxs-lookup"><span data-stu-id="fe945-145">When this occurs, the session rating is **unavailable**.</span></span>
  
<span data-ttu-id="fe945-146">Quality of experience (QoE) データを持つオーディオセッションについては、次の表では、セッションが**低**品質と見なされる主な問題について説明します。</span><span class="sxs-lookup"><span data-stu-id="fe945-146">For audio sessions that do have quality of experience (QoE) data, the following table describes major issues that qualify a session as **poor**.</span></span>
  
|<span data-ttu-id="fe945-147">**問題**</span><span class="sxs-lookup"><span data-stu-id="fe945-147">**Issue**</span></span>|<span data-ttu-id="fe945-148">**分野**</span><span class="sxs-lookup"><span data-stu-id="fe945-148">**Area**</span></span>|<span data-ttu-id="fe945-149">**説明**</span><span class="sxs-lookup"><span data-stu-id="fe945-149">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="fe945-150">通話の設定</span><span class="sxs-lookup"><span data-stu-id="fe945-150">Call setup</span></span>  <br/> |<span data-ttu-id="fe945-151">Session</span><span class="sxs-lookup"><span data-stu-id="fe945-151">Session</span></span>  <br/> |<span data-ttu-id="fe945-152">エラーコード Ms-diag 20-29 は通話の設定に失敗したことを示します。</span><span class="sxs-lookup"><span data-stu-id="fe945-152">The error code Ms-diag 20-29 indicates the call setup failed.</span></span> <span data-ttu-id="fe945-153">ユーザーが通話または会議に参加できませんでした。</span><span class="sxs-lookup"><span data-stu-id="fe945-153">The user couldn't join the call or meeting.</span></span>  <br/> |
|<span data-ttu-id="fe945-154">オーディオネットワークで分類された低品質通話</span><span class="sxs-lookup"><span data-stu-id="fe945-154">Audio network classified poor call</span></span>  <br/> |<span data-ttu-id="fe945-155">Session</span><span class="sxs-lookup"><span data-stu-id="fe945-155">Session</span></span>  <br/> |<span data-ttu-id="fe945-156">ネットワーク品質の問題 (パケット損失、ジッター、NMOS 劣化、RTT、または隠れた比率など) が発生しました。</span><span class="sxs-lookup"><span data-stu-id="fe945-156">Network quality issues (such as packet loss, jitter, NMOS degradation, RTT, or concealed ratio) were encountered.</span></span> <span data-ttu-id="fe945-157">不適切な通話の分類に使われる条件の詳細については、 [Microsoft ブログの投稿](https://go.microsoft.com/fwlink/p/?linkid=852133)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe945-157">For more information about the conditions used to classify poor calls, see this [Microsoft blog post](https://go.microsoft.com/fwlink/p/?linkid=852133).</span></span>  <br/> |
|<span data-ttu-id="fe945-158">デバイスが機能しない</span><span class="sxs-lookup"><span data-stu-id="fe945-158">Device not functioning</span></span>  <br/> |<span data-ttu-id="fe945-159">Device</span><span class="sxs-lookup"><span data-stu-id="fe945-159">Device</span></span>  <br/> | <span data-ttu-id="fe945-160">デバイスが正常に機能していません。</span><span class="sxs-lookup"><span data-stu-id="fe945-160">A device isn't functioning correctly.</span></span> <span data-ttu-id="fe945-161">機能していないデバイスの比率は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="fe945-161">Device not functioning ratios are :</span></span> <br/>  <span data-ttu-id="fe945-162">DeviceRenderNotFunctioningEventRatio >= 0.005</span><span class="sxs-lookup"><span data-stu-id="fe945-162">DeviceRenderNotFunctioningEventRatio >= 0.005</span></span> <br/>  <span data-ttu-id="fe945-163">DeviceCaptureNotFunctioningEventRatio >= 0.005</span><span class="sxs-lookup"><span data-stu-id="fe945-163">DeviceCaptureNotFunctioningEventRatio >= 0.005</span></span> <br/> |
   
## <a name="related-topics"></a><span data-ttu-id="fe945-164">関連トピック</span><span class="sxs-lookup"><span data-stu-id="fe945-164">Related topics</span></span>
[<span data-ttu-id="fe945-165">通話分析をセットアップする</span><span class="sxs-lookup"><span data-stu-id="fe945-165">Set up Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="fe945-166">通話分析および通話品質ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="fe945-166">Call Analytics and Call Quality Dashboard</span></span>](difference-between-call-analytics-and-call-quality-dashboard.md)

  
 
