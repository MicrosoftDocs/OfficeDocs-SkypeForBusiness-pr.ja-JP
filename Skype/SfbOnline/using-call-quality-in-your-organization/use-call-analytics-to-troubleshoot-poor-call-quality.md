---
title: 通話分析を使用して Skype for Business の低い通話品質をトラブルシューティングする
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 66945036-ae87-4c08-a0bb-984e50d6b009
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
description: Skype のビジネス通話や会議のためのユーザーの問題を解決するのには、分析機能の呼び出しの詳細については、デバイス、ネットワーク、および接続を使用します。
ms.openlocfilehash: 933c041fd9683dd84d82fd9abdcf4cc627cf4366
ms.sourcegitcommit: 26d93a15c9d4704c08f3fabc5635839ce2456b2d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2018
ms.locfileid: "20205007"
---
# <a name="use-call-analytics-to-troubleshoot-poor-call-quality"></a><span data-ttu-id="c07c1-103">通話分析を使用して低い通話品質をトラブルシューティングする</span><span class="sxs-lookup"><span data-stu-id="c07c1-103">Use Call Analytics to troubleshoot poor call quality</span></span>

<span data-ttu-id="c07c1-104">呼び出しの分析では、Microsof チームと、ビジネスの Skype の呼び出し、または接続の問題をトラブルシューティングすることができます。</span><span class="sxs-lookup"><span data-stu-id="c07c1-104">Call Analytics helps you to troubleshoot call or connection problems with Microsof Teams and Skype for Business.</span></span> <span data-ttu-id="c07c1-105">コール分析では、Office 365 アカウントでデバイス、ネットワーク、および呼び出しと各ユーザーの会議のための接続に関する詳細情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c07c1-105">Call Analytics shows detailed information about the devices, networks, and connectivity for the calls and meetings of each user in your Office 365 account.</span></span> <span data-ttu-id="c07c1-106">サイトを作成する場合と、テナント情報が追加されました分析機能の呼び出しを呼び出し、およびセッションごとにも表示されます。</span><span class="sxs-lookup"><span data-stu-id="c07c1-106">If building, site, and tenant information has been added to Call Analytics, it will also be shown for each call and session.</span></span> <span data-ttu-id="c07c1-107">情報分析機能の呼び出しを使用できます不適切な呼び出しを持っていた理由の解明や、会議を経験します。</span><span class="sxs-lookup"><span data-stu-id="c07c1-107">Information available via Call Analytics can help you figure out why a user had a poor call or meeting experience.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="c07c1-108">呼び出しの分析では、マイクロソフトのチームと Skype ビジネス管理センターのhttps://admin.teams.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="c07c1-108">Call Analytics is now available in the Microsoft Teams and Skype for Business admin center at https://admin.teams.microsoft.com.</span></span>  <span data-ttu-id="c07c1-109">ヘルプデスク エージェントのアクセス許可とネットワーク トポロジのアップロードがで使用できる新しい管理ポータルで、今後数か月。</span><span class="sxs-lookup"><span data-stu-id="c07c1-109">Helpdesk agent permissions and network topology upload will be available in the new admin portal in the coming months.</span></span>  <span data-ttu-id="c07c1-110">エンドポイントを使用する続行する間に、https://adminportal.services.skypeforbusiness.comの第 1 層および第 2 層のヘルプデスクへのアクセス。</span><span class="sxs-lookup"><span data-stu-id="c07c1-110">In the meantime you can continue to use the endpoint at https://adminportal.services.skypeforbusiness.com for Tier 1 and Tier 2 helpdesk access.</span></span>
  
## <a name="troubleshoot-call-quality-problems-using-call-analytics"></a><span data-ttu-id="c07c1-111">分析機能の呼び出しを使用して通話品質の問題のトラブルシューティングを行う</span><span class="sxs-lookup"><span data-stu-id="c07c1-111">Troubleshoot call quality problems using Call Analytics</span></span>

<span data-ttu-id="c07c1-112">自分に割り当てられたアクセス許可レベルは、どのような種類の情報へのアクセスにある分析機能を呼び出すかを決定します。</span><span class="sxs-lookup"><span data-stu-id="c07c1-112">The permissions level assigned to you determines what type of information you have access to in Call Analytics:</span></span>
  
- <span data-ttu-id="c07c1-113">**ビジネス管理者の Skype**: 分析機能を呼び出すと、Skype のビジネス管理センターですべての情報へのアクセスがあります。</span><span class="sxs-lookup"><span data-stu-id="c07c1-113">**Skype for Business admin**: You have access to all the information in Call Analytics and in the Skype for Business Admin center.</span></span>
    
- <span data-ttu-id="c07c1-114">**第 1 層のアクセス許可を持つヘルプデスク エージェント**: 限られた分析機能の呼び出しでデータを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c07c1-114">**Helpdesk agent with Tier 1 permissions**: You see a limited set of data in Call Analytics.</span></span> <span data-ttu-id="c07c1-115">呼び出しのトラブルシューティングを行うことができますが、第 2 層のエージェントに会議の問題を入稿するでしょう。</span><span class="sxs-lookup"><span data-stu-id="c07c1-115">You can troubleshoot calls, but you'll hand off problems with meetings to a Tier 2 agent.</span></span> <span data-ttu-id="c07c1-116">ビジネス管理センターは、Skype の残りの部分にアクセスする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="c07c1-116">You don't have access to the rest of the Skype for Business Admin center.</span></span>
    
- <span data-ttu-id="c07c1-117">**層 2 のアクセス許可を持つヘルプデスク エージェント**: 分析の呼び出しで使用可能なすべてのデータを参照してくださいし、通話や会議の両方に関する問題のトラブルシューティングに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c07c1-117">**Helpdesk agent with Tier 2 permissions**: You see all available data in Call Analytics and can help troubleshoot problems with both calls and meetings.</span></span> <span data-ttu-id="c07c1-118">ビジネス管理センターは、Skype の残りの部分にアクセスする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="c07c1-118">You don't have access to the rest of the Skype for Business Admin center.</span></span>
    
<span data-ttu-id="c07c1-119">アクセス許可についてのヘルプが必要な場合は、ビジネス管理者は、Skype を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c07c1-119">See your Skype for Business admin if you need help with permissions.</span></span>
  
 <span data-ttu-id="c07c1-120">**第 1 層または 2 層のヘルプデスク エージェントとしての分析機能の呼び出しを開く**</span><span class="sxs-lookup"><span data-stu-id="c07c1-120">**Open Call Analytics as a Tier 1 or Tier 2 helpdesk agent**</span></span>
  
1. <span data-ttu-id="c07c1-121">Office 365 の管理ページに移動し、職場、学校のアカウントを使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="c07c1-121">Go to the Office 365 admin center and sign in using your work or school account.</span></span> <span data-ttu-id="c07c1-122">Web ブラウザーには、 *https://adminportal.services.skypeforbusiness.com*。</span><span class="sxs-lookup"><span data-stu-id="c07c1-122">Then in your web browser go to *https://adminportal.services.skypeforbusiness.com*.</span></span>
    
2. <span data-ttu-id="c07c1-123">で**ユーザーの検索**呼び出しのトラブルシューティングを行うし、一覧からユーザーを選択するをユーザーの名前または sip のいずれかのアドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="c07c1-123">In **User Search**, start typing either the name or sip address of the user whose calls you want to troubleshoot and then select the user from the list.</span></span>
    
    ![ビジネス管理センターの Skype での分析機能の呼び出しのユーザーの検索ボックスのスクリーン ショットです。](../images/db52efc5-dac1-4623-ba72-41e42f0a0fb4.png)
  
3. <span data-ttu-id="c07c1-125">**履歴を呼び出す**には、トラブルシューティングを行う、電話または会議を選択します。</span><span class="sxs-lookup"><span data-stu-id="c07c1-125">In **Call history**, select the call or meeting that you want to troubleshoot.</span></span>
    
    ![スクリーン ショットは、日付と時刻、受信者、およびオーディオの品質の概要と、7 日間の品質との会議や呼び出し、アクティビティの概要、ユーザーの連絡先の詳細などの情報を持つユーザーの呼び出し履歴] ページを示しています。](../images/aef80e09-3b37-46db-8e7b-8cf71712349b.png)
  
4. <span data-ttu-id="c07c1-127">[**詳細設定**] タブを選択し、不適切な呼び出しの品質または接続の問題を示す黄色と赤色の項目を検索します。</span><span class="sxs-lookup"><span data-stu-id="c07c1-127">Select the **Advanced** tab, and then look for yellow and red items which indicate poor call quality or connection problems.</span></span>
    
    <span data-ttu-id="c07c1-128">各コールまたは会議のセッションの詳細] では、軽微な問題は黄色で表示されます。</span><span class="sxs-lookup"><span data-stu-id="c07c1-128">In the session details for each call or meeting, minor issues appear in yellow.</span></span> <span data-ttu-id="c07c1-129">(たとえば、次のスクリーン ショットでは、値、平均変位、変位の最大値、および平均パケット損失の割合が黄色で)。何かが黄色の場合正常範囲の外にあるとそれが原因になっている問題は、問題の主な原因をする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c07c1-129">(For example, in the following screenshot, the values are in yellow for Average jitter, Max jitter, and Average packet loss rate.) If something is yellow, it's outside of normal range, and it may be contributing to the problem, but it's unlikely to be the main cause of the problem.</span></span> <span data-ttu-id="c07c1-130">何かが赤い場合は、これは重大な問題と、このセッションの呼び出しが不適切な品質の主な原因である可能性が。</span><span class="sxs-lookup"><span data-stu-id="c07c1-130">If something is red, it's a significant problem, and it's likely the main cause of the poor call quality for this session.</span></span> 
    
    ![スクリーン ショットは、軽微な問題があり、受信ネットワーク セクションが展開され、平均変位、最大のジッターおよび平均パケット損失率のデータが、色を黄色で表示されているユーザーの呼び出し履歴の詳細設定] タブを示します。](../images/13f314ce-97cf-4bd0-a147-14b177d07040.png)
  
<span data-ttu-id="c07c1-132">まれに、経験のデータの品質はありませんオーディオ ・ セッションを受信しました。</span><span class="sxs-lookup"><span data-stu-id="c07c1-132">In rare cases, quality of experience data isn't received for audio sessions.</span></span> <span data-ttu-id="c07c1-133">多くの場合これはによる呼び出しを削除し、接続を終了して、クライアントを使用しています。</span><span class="sxs-lookup"><span data-stu-id="c07c1-133">Often this is caused by the call dropping and connection with the client terminating.</span></span> <span data-ttu-id="c07c1-134">このような場合は、セッションの評価は「使用可能」ではありません。</span><span class="sxs-lookup"><span data-stu-id="c07c1-134">When this occurs, the session rating is "unavailable".</span></span>
  
<span data-ttu-id="c07c1-135">エクスペリエンス (QoE) データの品質を持っているオーディオ ・ セッションには、次の表は「が低下します。」としてセッションに適用される主な問題点を示します。</span><span class="sxs-lookup"><span data-stu-id="c07c1-135">For audio sessions that do have quality of experience (QoE) data, the following table describes major issues that qualify a session as "poor."</span></span>
  
|<span data-ttu-id="c07c1-136">**問題**</span><span class="sxs-lookup"><span data-stu-id="c07c1-136">**Issue**</span></span>|<span data-ttu-id="c07c1-137">**エリア**</span><span class="sxs-lookup"><span data-stu-id="c07c1-137">**Area**</span></span>|<span data-ttu-id="c07c1-138">**説明**</span><span class="sxs-lookup"><span data-stu-id="c07c1-138">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c07c1-139">呼び出しのセットアップ</span><span class="sxs-lookup"><span data-stu-id="c07c1-139">Call setup</span></span>  <br/> |<span data-ttu-id="c07c1-140">セッション</span><span class="sxs-lookup"><span data-stu-id="c07c1-140">Session</span></span>  <br/> |<span data-ttu-id="c07c1-141">20 ~ 29 の Ms の diag のエラーコードでは、呼び出しのセットアップが失敗したことを示します。</span><span class="sxs-lookup"><span data-stu-id="c07c1-141">The error code Ms-diag 20-29 indicates the call setup failed.</span></span> <span data-ttu-id="c07c1-142">ユーザーは、通話や会議に参加できませんでした。</span><span class="sxs-lookup"><span data-stu-id="c07c1-142">The user couldn't join the call or meeting.</span></span>  <br/> |
|<span data-ttu-id="c07c1-143">オーディオ ネットワークに不適切な呼び出しが分類されます。</span><span class="sxs-lookup"><span data-stu-id="c07c1-143">Audio network classified poor call</span></span>  <br/> |<span data-ttu-id="c07c1-144">セッション</span><span class="sxs-lookup"><span data-stu-id="c07c1-144">Session</span></span>  <br/> |<span data-ttu-id="c07c1-145">ネットワークの品質の問題は、パケット損失、ジッター、NMOS の低下、RTT などの分野において発生したまたは比率を非表示。</span><span class="sxs-lookup"><span data-stu-id="c07c1-145">Network quality issues were encountered in areas such as packet loss, jitter, NMOS degradation, RTT, or concealed ratio.</span></span> <span data-ttu-id="c07c1-146">不適切な呼び出しを分類するための条件の詳細については、この[マイクロソフトのブログ記事](https://go.microsoft.com/fwlink/p/?linkid=852133)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c07c1-146">For more information about the conditions used to classify poor calls, see this [Microsoft blog post](https://go.microsoft.com/fwlink/p/?linkid=852133).</span></span>  <br/> |
|<span data-ttu-id="c07c1-147">デバイスが機能しません。</span><span class="sxs-lookup"><span data-stu-id="c07c1-147">Device not functioning</span></span>  <br/> |<span data-ttu-id="c07c1-148">デバイス</span><span class="sxs-lookup"><span data-stu-id="c07c1-148">Device</span></span>  <br/> | <span data-ttu-id="c07c1-149">デバイスが正常に機能はありません。</span><span class="sxs-lookup"><span data-stu-id="c07c1-149">A device isn't functioning correctly.</span></span> <span data-ttu-id="c07c1-150">比率が機能していないデバイスは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c07c1-150">Device not functioning ratios are :</span></span> <br/>  <span data-ttu-id="c07c1-151">DeviceRenderNotFunctioningEventRatio > = 0.005</span><span class="sxs-lookup"><span data-stu-id="c07c1-151">DeviceRenderNotFunctioningEventRatio >= 0.005</span></span> <br/>  <span data-ttu-id="c07c1-152">DeviceCaptureNotFunctioningEventRatio > = 0.005</span><span class="sxs-lookup"><span data-stu-id="c07c1-152">DeviceCaptureNotFunctioningEventRatio >= 0.005</span></span> <br/> |
   
## <a name="related-topics"></a><span data-ttu-id="c07c1-153">このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「Skype for Business Online 用 Windows PowerShell モジュール」からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="c07c1-153">Related topics</span></span>
[<span data-ttu-id="c07c1-154">Skype for Business の通話分析をセットアップする</span><span class="sxs-lookup"><span data-stu-id="c07c1-154">Set up Skype for Business Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="c07c1-155">呼び出しを分析し、通話品質のダッシュ ボード</span><span class="sxs-lookup"><span data-stu-id="c07c1-155">Call Analytics and Call Quality Dashboard</span></span>](difference-between-call-analytics-and-call-quality-dashboard.md)

  
 
