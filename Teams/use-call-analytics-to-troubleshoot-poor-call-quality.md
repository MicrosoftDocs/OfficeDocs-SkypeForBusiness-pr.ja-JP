---
title: 通話分析を使用して低い通話品質をトラブルシューティングする
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 66945036-ae87-4c08-a0bb-984e50d6b009
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
description: ビジネス通話や会議のためのマイクロソフトのチームと Skype ユーザーの問題のトラブルシューティングを行うには、分析機能の呼び出しの詳細については、デバイス、ネットワーク、および接続を使用します。
ms.openlocfilehash: 3e35a72150d74580d1f44623583419b37e3ad1c5
ms.sourcegitcommit: 31827526894ffb75d64fcb0a7c76ee874ad3c269
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2019
ms.locfileid: "29754066"
---
# <a name="use-call-analytics-to-troubleshoot-poor-call-quality"></a><span data-ttu-id="3d859-103">通話分析を使用して低い通話品質をトラブルシューティングする</span><span class="sxs-lookup"><span data-stu-id="3d859-103">Use Call Analytics to troubleshoot poor call quality</span></span>

<span data-ttu-id="3d859-104">呼び出しの分析では、マイクロソフトのチームと、ビジネスの Skype の呼び出し、または接続の問題を解決することができます。</span><span class="sxs-lookup"><span data-stu-id="3d859-104">Call Analytics helps you troubleshoot call or connection problems with Microsoft Teams and Skype for Business.</span></span> <span data-ttu-id="3d859-105">コール分析では、Office 365 アカウントでデバイス、ネットワーク、および呼び出しと各ユーザーの会議のための接続に関する詳細情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3d859-105">Call Analytics shows detailed information about the devices, networks, and connectivity for the calls and meetings of each user in your Office 365 account.</span></span> <span data-ttu-id="3d859-106">サイトを作成する場合と、テナント情報が追加されました分析機能の呼び出しを呼び出し、およびセッションごとにも表示されます。</span><span class="sxs-lookup"><span data-stu-id="3d859-106">If building, site, and tenant information has been added to Call Analytics, it will also be shown for each call and session.</span></span> <span data-ttu-id="3d859-107">情報分析機能の呼び出しを使用できます不適切な呼び出しを持っていた理由の解明や、会議を経験します。</span><span class="sxs-lookup"><span data-stu-id="3d859-107">Information available via Call Analytics can help you figure out why a user had a poor call or meeting experience.</span></span> 
  
## <a name="call-analytics-permissions"></a><span data-ttu-id="3d859-108">分析機能のアクセス許可を呼び出し</span><span class="sxs-lookup"><span data-stu-id="3d859-108">Call Analytics permissions</span></span>

<span data-ttu-id="3d859-109">管理者としては、分析機能の呼び出しのすべての機能へのフル アクセスを取得します。</span><span class="sxs-lookup"><span data-stu-id="3d859-109">As the admin, you get full access to all the features of Call Analytics.</span></span> <span data-ttu-id="3d859-110">さらに、スタッフをサポートするために Active Directory の Azure ロールを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="3d859-110">In addition, you can assign Azure Active Directory roles to support staff.</span></span> <span data-ttu-id="3d859-111">分析機能の呼び出しの制限付きビューを持つユーザーにチームのコミュニケーションのサポート専門家のロールを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="3d859-111">Assign the Teams communications support specialist role to users who should have a limited view of Call Analytics.</span></span> <span data-ttu-id="3d859-112">分析機能の呼び出しのすべての機能へのアクセスを必要とするユーザーには、チーム コミュニケーションのサポート エンジニアの役割を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="3d859-112">Assign the Teams communications support engineer role to users who need access to the full functionality of Call Analytics.</span></span> <span data-ttu-id="3d859-113">両方のアクセス許可レベルは、マイクロソフトのチームの管理センターの残りの部分へのアクセスを防止します。</span><span class="sxs-lookup"><span data-stu-id="3d859-113">Both permission levels prevent access to the rest of the Microsoft Teams admin center.</span></span>

<span data-ttu-id="3d859-114">通信のサポート ・ スペシャ リストは、基本的な通話品質の問題を処理します。</span><span class="sxs-lookup"><span data-stu-id="3d859-114">Communications support specialists handle basic call-quality problems.</span></span> <span data-ttu-id="3d859-115">会議に関する問題を調査するありません。</span><span class="sxs-lookup"><span data-stu-id="3d859-115">They don't investigate issues with meetings.</span></span> <span data-ttu-id="3d859-116">関連情報を収集し、通信のサポート ・ エンジニアにエスカレーションします。</span><span class="sxs-lookup"><span data-stu-id="3d859-116">Instead, they collect related information and then escalate to a communications support engineer.</span></span> <span data-ttu-id="3d859-117">通信のサポート エンジニアは、サポート ・ スペシャ リストの通信から非表示にする詳細な呼び出しのログ内の情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3d859-117">Communications support engineers see information in detailed call logs that's hidden from communications support specialists.</span></span> <span data-ttu-id="3d859-118">次の表は、分析機能の呼び出しを使用するときに、通信のサポートのスペシャ リストとの通信のサポート エンジニアに利用可能な情報の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="3d859-118">The following table gives an overview of information available to communications support specialists and communications support engineers when they use Call Analytics.</span></span>

<span data-ttu-id="3d859-119">自分に割り当てられたアクセス許可レベルは、どのような種類の情報へのアクセスにある分析機能を呼び出すかを決定します。</span><span class="sxs-lookup"><span data-stu-id="3d859-119">The permissions level assigned to you determines what type of information you have access to in Call Analytics:</span></span>
  
- <span data-ttu-id="3d859-120">**チーム サービスの管理者またはチーム通信管理者**: 分析機能を呼び出すと、マイクロソフトのチーム管理センターのすべての情報へのアクセスがあります。</span><span class="sxs-lookup"><span data-stu-id="3d859-120">**Teams service administrator or Teams communications administrator**: You have access to all the information in Call Analytics and in the Microsoft Teams admin center.</span></span>
    
- <span data-ttu-id="3d859-121">**チームのコミュニケーション ・ スペシャ リストのサポート**: 限られた分析機能の呼び出しでデータを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3d859-121">**Teams communications support specialist**: You see a limited set of data in Call Analytics.</span></span> <span data-ttu-id="3d859-122">呼び出しのトラブルシューティングを行うことができますが、チームのコミュニケーションのサポート エンジニアに会議の問題を入稿するでしょう。</span><span class="sxs-lookup"><span data-stu-id="3d859-122">You can troubleshoot calls, but you'll hand off problems with meetings to a Teams communications support engineer.</span></span> <span data-ttu-id="3d859-123">マイクロソフトのチームの管理センターの残りの部分にアクセスする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="3d859-123">You don't have access to the rest of the Microsoft Teams admin center.</span></span>
    
- <span data-ttu-id="3d859-124">**チームのコミュニケーションのサポート ・ エンジニア**: 分析の呼び出しで使用可能なすべてのデータを参照してくださいし、通話や会議の両方に関する問題のトラブルシューティングに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="3d859-124">**Teams communications support engineer**: You see all available data in Call Analytics and can help troubleshoot problems with both calls and meetings.</span></span> <span data-ttu-id="3d859-125">マイクロソフトのチームの管理センターの残りの部分にアクセスする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="3d859-125">You don't have access to the rest of the Microsoft Teams admin center.</span></span>
    
> [!NOTE]
> <span data-ttu-id="3d859-126">通信のサポート ・ スペシャ リストの役割は、第 1 層のサポートに相当と通信のサポート ・ エンジニアの役割は、第 2 層のサポートに相当します。</span><span class="sxs-lookup"><span data-stu-id="3d859-126">The communications support specialist role is equivalent to tier 1 support and the communications support engineer role is equivalent to tier 2 support.</span></span>

<span data-ttu-id="3d859-127">チーム管理者の役割の詳細については、[チームを管理する管理者の役割を使用してマイクロソフトのチーム](using-admin-roles.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3d859-127">For more information about Teams admin roles, see [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md).</span></span> <span data-ttu-id="3d859-128">チーム通信のサポートの詳細な比較についてはスペシャ リストとチームのコミュニケーション エンジニア リングの役割をサポート、[分析機能の呼び出しの設定](set-up-call-analytics.md#set-call-analytics-permissions)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3d859-128">For a detailed comparison of the Teams communications support specialist and Teams communications support engineer roles, see [Set up Call Analytics](set-up-call-analytics.md#set-call-analytics-permissions)</span></span> 
  
<span data-ttu-id="3d859-129">参照してください、チームと Skype ビジネス管理者のアクセス許可についてのヘルプが必要な場合です。</span><span class="sxs-lookup"><span data-stu-id="3d859-129">See your Teams and Skype for Business admin if you need help with permissions.</span></span>
  
## <a name="troubleshoot-call-quality-problems-using-call-analytics"></a><span data-ttu-id="3d859-130">分析機能の呼び出しを使用して通話品質の問題のトラブルシューティングを行う</span><span class="sxs-lookup"><span data-stu-id="3d859-130">Troubleshoot call quality problems using Call Analytics</span></span>

1. <span data-ttu-id="3d859-131">チーム通信のサポート、チームの管理者の資格情報でサインインします。</span><span class="sxs-lookup"><span data-stu-id="3d859-131">Sign in with your Teams communications support or Teams admin credentials.</span></span>

2. <span data-ttu-id="3d859-132">Office 365 の管理ページに移動し、職場、学校のアカウントを使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="3d859-132">Go to the Office 365 admin center and sign in using your work or school account.</span></span> <span data-ttu-id="3d859-133">Web ブラウザーには、 *https://adminportal.services.skypeforbusiness.com*。</span><span class="sxs-lookup"><span data-stu-id="3d859-133">Then in your web browser go to *https://adminportal.services.skypeforbusiness.com*.</span></span>

3. <span data-ttu-id="3d859-134">[**管理センター**] > [**Teams & Skype**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3d859-134">Select **Admin centers** > **Teams & Skype**.</span></span> 
    
4. <span data-ttu-id="3d859-135">**ダッシュ ボード\*\*\*\*ユーザーの検索**] で [名前の入力を開始または呼び出しのトラブルシューティングを行うか、ユーザーの一覧を表示する**ユーザーを表示する**を選択するをユーザーの sip アドレスです。</span><span class="sxs-lookup"><span data-stu-id="3d859-135">On the **Dashboard**, in **User Search**, start typing either the name or sip address of the user whose calls you want to troubleshoot or select **View users** to see a list of users.</span></span>
    
    ![マイクロソフトのチームの管理センターでの分析機能の呼び出しのユーザーの検索ボックスのスクリーン ショットです。](media/use-call-analytics-to-troubleshoot-image-1.png)
  
5. <span data-ttu-id="3d859-137">リストからユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="3d859-137">Select the user from the list.</span></span>

6. <span data-ttu-id="3d859-138">**履歴を呼び出す**を選択し、トラブルシューティングを行うにコールまたは会議を選択します。</span><span class="sxs-lookup"><span data-stu-id="3d859-138">Select **Call history**, and then select the call or meeting that you want to troubleshoot.</span></span>
    
    ![スクリーン ショットは、ユーザーの [呼び出し履歴] ページを示しています。](media/use-call-analytics-to-troubleshoot-image-2.png)
  
7. <span data-ttu-id="3d859-140">[**詳細設定**] タブを選択し、不適切な呼び出しの品質または接続の問題を示す黄色と赤色の項目を検索します。</span><span class="sxs-lookup"><span data-stu-id="3d859-140">Select the **Advanced** tab, and then look for yellow and red items which indicate poor call quality or connection problems.</span></span>
    
    <span data-ttu-id="3d859-141">各コールまたは会議のセッションの詳細] では、軽微な問題は黄色で表示されます。</span><span class="sxs-lookup"><span data-stu-id="3d859-141">In the session details for each call or meeting, minor issues appear in yellow.</span></span> <span data-ttu-id="3d859-142">(たとえば、次のスクリーン ショットでは、値、平均変位、変位の最大値、および平均パケット損失の割合が黄色で)。何かが黄色の場合正常範囲の外にあるとそれが原因になっている問題は、問題の主な原因をする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3d859-142">(For example, in the following screenshot, the values are in yellow for Average jitter, Max jitter, and Average packet loss rate.) If something is yellow, it's outside of normal range, and it may be contributing to the problem, but it's unlikely to be the main cause of the problem.</span></span> <span data-ttu-id="3d859-143">何かが赤い場合は、これは重大な問題と、このセッションの呼び出しが不適切な品質の主な原因である可能性が。</span><span class="sxs-lookup"><span data-stu-id="3d859-143">If something is red, it's a significant problem, and it's likely the main cause of the poor call quality for this session.</span></span> 
    
    ![<span data-ttu-id="3d859-144">スクリーン ショットは、ユーザーの呼び出し履歴の詳細設定] タブを示しています。</span><span class="sxs-lookup"><span data-stu-id="3d859-144">Screenshot shows the Advanced tab of a user's Call history</span></span> ](media/use-call-analytics-to-troubleshoot-image-3.png)
  
<span data-ttu-id="3d859-145">まれに、経験のデータの品質はありませんオーディオ ・ セッションを受信しました。</span><span class="sxs-lookup"><span data-stu-id="3d859-145">In rare cases, quality of experience data isn't received for audio sessions.</span></span> <span data-ttu-id="3d859-146">多くの場合これはによる呼び出しを削除し、接続を終了して、クライアントを使用しています。</span><span class="sxs-lookup"><span data-stu-id="3d859-146">Often this is caused by the call dropping and connection with the client terminating.</span></span> <span data-ttu-id="3d859-147">このような場合は、セッションの評価は**利用できません**。</span><span class="sxs-lookup"><span data-stu-id="3d859-147">When this occurs, the session rating is **unavailable**.</span></span>
  
<span data-ttu-id="3d859-148">エクスペリエンス (QoE) データの品質を持っているオーディオ ・ セッションの次の表は**低い**としてセッションに適用される主な問題点について説明します。</span><span class="sxs-lookup"><span data-stu-id="3d859-148">For audio sessions that do have quality of experience (QoE) data, the following table describes major issues that qualify a session as **poor**.</span></span>
  
|<span data-ttu-id="3d859-149">**問題**</span><span class="sxs-lookup"><span data-stu-id="3d859-149">**Issue**</span></span>|<span data-ttu-id="3d859-150">**エリア**</span><span class="sxs-lookup"><span data-stu-id="3d859-150">**Area**</span></span>|<span data-ttu-id="3d859-151">**説明**</span><span class="sxs-lookup"><span data-stu-id="3d859-151">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3d859-152">呼び出しのセットアップ</span><span class="sxs-lookup"><span data-stu-id="3d859-152">Call setup</span></span>  <br/> |<span data-ttu-id="3d859-153">セッション</span><span class="sxs-lookup"><span data-stu-id="3d859-153">Session</span></span>  <br/> |<span data-ttu-id="3d859-154">20 ~ 29 の Ms の diag のエラーコードでは、呼び出しのセットアップが失敗したことを示します。</span><span class="sxs-lookup"><span data-stu-id="3d859-154">The error code Ms-diag 20-29 indicates the call setup failed.</span></span> <span data-ttu-id="3d859-155">ユーザーは、通話や会議に参加できませんでした。</span><span class="sxs-lookup"><span data-stu-id="3d859-155">The user couldn't join the call or meeting.</span></span>  <br/> |
|<span data-ttu-id="3d859-156">オーディオ ネットワークに不適切な呼び出しが分類されます。</span><span class="sxs-lookup"><span data-stu-id="3d859-156">Audio network classified poor call</span></span>  <br/> |<span data-ttu-id="3d859-157">セッション</span><span class="sxs-lookup"><span data-stu-id="3d859-157">Session</span></span>  <br/> |<span data-ttu-id="3d859-158">パケット損失、ジッター、NMOS の低下、RTT、または非表示の文字列の比率) などのネットワーク品質の問題が発生しました。</span><span class="sxs-lookup"><span data-stu-id="3d859-158">Network quality issues (such as packet loss, jitter, NMOS degradation, RTT, or concealed ratio) were encountered.</span></span> <span data-ttu-id="3d859-159">不適切な呼び出しを分類するための条件の詳細については、この[マイクロソフトのブログ記事](https://go.microsoft.com/fwlink/p/?linkid=852133)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3d859-159">For more information about the conditions used to classify poor calls, see this [Microsoft blog post](https://go.microsoft.com/fwlink/p/?linkid=852133).</span></span>  <br/> |
|<span data-ttu-id="3d859-160">デバイスが機能しません。</span><span class="sxs-lookup"><span data-stu-id="3d859-160">Device not functioning</span></span>  <br/> |<span data-ttu-id="3d859-161">デバイス</span><span class="sxs-lookup"><span data-stu-id="3d859-161">Device</span></span>  <br/> | <span data-ttu-id="3d859-162">デバイスが正常に機能はありません。</span><span class="sxs-lookup"><span data-stu-id="3d859-162">A device isn't functioning correctly.</span></span> <span data-ttu-id="3d859-163">比率が機能していないデバイスは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="3d859-163">Device not functioning ratios are :</span></span> <br/>  <span data-ttu-id="3d859-164">DeviceRenderNotFunctioningEventRatio _gt = 0.005</span><span class="sxs-lookup"><span data-stu-id="3d859-164">DeviceRenderNotFunctioningEventRatio >= 0.005</span></span> <br/>  <span data-ttu-id="3d859-165">DeviceCaptureNotFunctioningEventRatio _gt = 0.005</span><span class="sxs-lookup"><span data-stu-id="3d859-165">DeviceCaptureNotFunctioningEventRatio >= 0.005</span></span> <br/> |
   
## <a name="related-topics"></a><span data-ttu-id="3d859-166">関連トピック</span><span class="sxs-lookup"><span data-stu-id="3d859-166">Related topics</span></span>
[<span data-ttu-id="3d859-167">分析機能の呼び出しを設定します</span><span class="sxs-lookup"><span data-stu-id="3d859-167">Set up Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="3d859-168">呼び出しを分析し、通話品質のダッシュ ボード</span><span class="sxs-lookup"><span data-stu-id="3d859-168">Call Analytics and Call Quality Dashboard</span></span>](difference-between-call-analytics-and-call-quality-dashboard.md)

  
 
