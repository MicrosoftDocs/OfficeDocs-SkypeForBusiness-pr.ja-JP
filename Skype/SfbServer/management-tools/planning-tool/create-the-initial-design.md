---
title: Skype for Business Server 2015 の初期トポロジ設計の作成
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/5/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f3131153-de14-41be-b1e6-7d4bb0191af1
description: Skype for Business Server 計画ツールのインストールが完了したら、計画ツールを開始して、提案された Skype for Business Server 2015 インフラストラクチャの設計を開始する準備ができました。
ms.openlocfilehash: 8c19551d2273b992b5148646e28d726f5aea5900
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816496"
---
# <a name="create-the-initial-topology-design-for-skype-for-business-server-2015"></a><span data-ttu-id="9e427-103">Skype for Business Server 2015 の初期トポロジ設計の作成</span><span class="sxs-lookup"><span data-stu-id="9e427-103">Create the initial topology design for Skype for Business Server 2015</span></span>

<span data-ttu-id="9e427-104">Skype for Business Server 計画ツールのインストールが完了したら、計画ツールを開始して、提案された Skype for Business Server 2015 インフラストラクチャの設計を開始する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="9e427-104">After you have finished installing the Skype for Business Server Planning Tool, you are ready to start the Planning Tool and begin designing the proposed Skype for Business Server 2015 infrastructure.</span></span>

> [!NOTE]
>  <span data-ttu-id="9e427-105">計画ツールは、サイトとトポロジの設計で意思決定プロセスについて通知するための詳細なガイドを含むウィザードベースのツールです。</span><span class="sxs-lookup"><span data-stu-id="9e427-105">The Planning Tool is a wizard-driven tool with detailed guides to inform your decision-making process in designing your sites and topology.</span></span> <span data-ttu-id="9e427-106">このトピックは、すべてを網羅したガイドではありませんが、設計セッションで計画ツールを使い始めることができるようにすることを目的としています。</span><span class="sxs-lookup"><span data-stu-id="9e427-106">This topic is intended not as an exhaustive guide, but simply to help get you started using the Planning Tool in your design sessions.</span></span>

### <a name="to-get-started-using-the-planning-tool-and-create-the-initial-design"></a><span data-ttu-id="9e427-107">計画ツールの使用を開始するには、最初のデザインを作成するには</span><span class="sxs-lookup"><span data-stu-id="9e427-107">To get started using the Planning Tool and create the initial design</span></span>

1. <span data-ttu-id="9e427-108">Skype for Business Server 2015 計画ツールを起動します。 [**スタート**]、[**すべてのプログラム**]、[ **skype for business Server 2015**]、[**計画ツール**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="9e427-108">Start the Skype for Business Server 2015 Planning Tool: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Planning Tool**.</span></span>

2. <span data-ttu-id="9e427-109">計画ツールが開始されると、[ **Skype For Business Server 2015 の計画ツール] ページにようこそ**が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9e427-109">After the Planning Tool has started, the **Welcome to the Planning Tool for Skype for Business Server 2015** page appears.</span></span> <span data-ttu-id="9e427-110">次のいずれかを選択して、設計を開始します。</span><span class="sxs-lookup"><span data-stu-id="9e427-110">Choose one of the following options to begin your design:</span></span>

   - <span data-ttu-id="9e427-111">**オプション 1: 使い始める**[**はじめ**に] をクリックすると、特定の一連の面接質問が表示され、条件を定義できます。</span><span class="sxs-lookup"><span data-stu-id="9e427-111">**Option 1: Get Started** Clicking **Get Started** provides a specific series of interview questions with relevant selections to define the criteria.</span></span> <span data-ttu-id="9e427-112">初めての「面接**開始**」セクションを完了した後、サイトのアーキテクチャを定義するための**設計サイト**に進みます。</span><span class="sxs-lookup"><span data-stu-id="9e427-112">After you have finished the initial **Get Started** interview section, you proceed into **Design Sites** to define your site architecture.</span></span> <span data-ttu-id="9e427-113">このオプションを完了するには、手順3に進みます。</span><span class="sxs-lookup"><span data-stu-id="9e427-113">To complete this option, proceed to step 3.</span></span>

   - <span data-ttu-id="9e427-114">**オプション 2: サイトを設計**する[ようこそ] ページで [**サイトのデザイン**] をクリックすると **、[はじめに] セクションに**表示される面接の質問が無視されます。</span><span class="sxs-lookup"><span data-stu-id="9e427-114">**Option 2: Design Sites** Clicking **Design Sites** at the Welcome page bypasses the interview questions presented in the **Get Started** section.</span></span> <span data-ttu-id="9e427-115">「**はじめ**に」セクションの「面接の質問」セクションで収集された情報は、このオプションを使用して既定値に設定されています。</span><span class="sxs-lookup"><span data-stu-id="9e427-115">The information that would have been gathered by responding to the interview questions in **Get Started** section is set to default values with this option.</span></span> <span data-ttu-id="9e427-116">[**サイトのデザイン**] をクリックすることで、経験豊富なデザイナーは**最初のインタビュー**を回避し、必要に応じて既定値を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="9e427-116">By clicking **Design Sites**, the experienced designer can bypass the initial interview and change the default values, as needed, on the **Central Sites** start page.</span></span> <span data-ttu-id="9e427-117">このオプションを完了するには、手順3-5 をスキップして、手順6から始めます。</span><span class="sxs-lookup"><span data-stu-id="9e427-117">To complete this option, skip over steps 3-5 and start at step 6.</span></span>

   - <span data-ttu-id="9e427-118">**オプション 3: 保存したトポロジを表示する**計画ツールの以前の使用でトポロジを既に完了し保存している場合は、これらの手順のほとんどをスキップして、最初にトポロジを開いて表示することができます。</span><span class="sxs-lookup"><span data-stu-id="9e427-118">**Option 3: Display Your Saved Topology** If you have already completed and saved a topology through previous use of the Planning Tool, you can skip over most of these steps and start by opening and displaying the topology.</span></span> <span data-ttu-id="9e427-119">また、トポロジの変更や更新を行ったり、保存したり、Microsoft Excel または Microsoft Visio にエクスポートしたりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="9e427-119">You can also make changes and updates to the topology, resave it, and then export it to Microsoft Excel or Microsoft Visio.</span></span> <span data-ttu-id="9e427-120">このオプションを完了するには、手順3-12 をスキップして、手順13から始めます。</span><span class="sxs-lookup"><span data-stu-id="9e427-120">To complete this option, skip over steps 3-12 and start at step 13.</span></span>

3. <span data-ttu-id="9e427-121">[**はじめ**に] をクリックして、Skype For business Server 2015 トポロジの設計を開始します。</span><span class="sxs-lookup"><span data-stu-id="9e427-121">Click **Get Started** to begin designing your Skype for Business Server 2015 topology.</span></span>

4. <span data-ttu-id="9e427-p106">設計に対して該当する条件を選択して各セクションに回答し、[**次へ**] をクリックして、ウィザードの次のページに進みます。前の各ページを変更するには、[**戻る**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9e427-p106">Answer each section by selecting the appropriate criteria for your design, and then click **Next** to proceed to the next Wizard page. Click **Back** to make changes on previous pages.</span></span>

    > [!TIP]
    > <span data-ttu-id="9e427-124">各ページには、選択条件の説明および望ましい方法や処理能力計画に基づいた推奨事項が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9e427-124">Each page has a description of the selection criteria, and recommendations based on preferred practices and capacity planning.</span></span> <span data-ttu-id="9e427-125">追加情報が必要な場合は、[**詳細**情報] をクリックして、Microsoft web サイトの Skype For business Server 2015 計画のドキュメントから詳細情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e427-125">If you require additional details, click **Learn more** to read detailed information from the Skype for Business Server 2015 Planning documentation on the Microsoft  website.</span></span> <span data-ttu-id="9e427-126">Microsoft の web サイトにアクセスするには、インターネット接続が必要です。</span><span class="sxs-lookup"><span data-stu-id="9e427-126">You must have Internet connectivity to access the Microsoft  website.</span></span>

5. <span data-ttu-id="9e427-127">設計に適合するオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="9e427-127">Select the appropriate options for your design.</span></span> <span data-ttu-id="9e427-128">初期条件を定義すると、新しいページが表示され [機能の概要] が完成しているかどうかが確認されます。</span><span class="sxs-lookup"><span data-stu-id="9e427-128">After the initial criteria are defined, a page will confirm that your Features Overview is complete.</span></span>

6. <span data-ttu-id="9e427-129">[**サイトのデザイン**] をクリックしてセントラルサイトを定義します。</span><span class="sxs-lookup"><span data-stu-id="9e427-129">Click **Design Sites** to define your central site.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9e427-130">各 Skype for Business Server 2015 トポロジには、少なくとも1つのセントラルサイトが含まれます。</span><span class="sxs-lookup"><span data-stu-id="9e427-130">Each Skype for Business Server 2015 topology will have at least one central site.</span></span> <span data-ttu-id="9e427-131">設計には、1つのセントラルサイト、多数のブランチサイトを含むセントラルサイト、一連のセントラルサイト、または各セントラルサイトに関連付けられたブランチサイトを含むセントラルサイトが含まれている場合があります。</span><span class="sxs-lookup"><span data-stu-id="9e427-131">Your design may have a single central site, a central site with a number of branch sites, a number of central sites, or a number of central sites with branch sites associated with each central site.</span></span>

7. <span data-ttu-id="9e427-132">[**サイト名**] に、このセントラルサイトを識別する名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="9e427-132">In **Site Name**, type the name that will identify this central site.</span></span>

8. <span data-ttu-id="9e427-133">[**サイトのホームユーザー**] に、このセントラルサイトに表示されるオンプレミスの同時ユーザー数を入力します。</span><span class="sxs-lookup"><span data-stu-id="9e427-133">In **Site Homed Users**, type the expected number of on-premises concurrent users who will be homed in this central site.</span></span>

9. <span data-ttu-id="9e427-134">[**クラウドのホームユーザー**] に、このセントラルサイトに表示されるオンラインの同時ユーザー数を入力します。</span><span class="sxs-lookup"><span data-stu-id="9e427-134">In **Cloud Homed Users**, type the expected number of online concurrent users who will be homed in this central site.</span></span>

10. <span data-ttu-id="9e427-135">必要に応じて、オンライン コラボレーション、ユーザー、音声、追加展開オプション、またはサーバー アプリケーションの選択を変更します。</span><span class="sxs-lookup"><span data-stu-id="9e427-135">Modify the selections for Online Collaboration, Users, Voice, Additional Deployment Options, or Server Applications, as needed.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="9e427-136">デザインのこの時点では、展開のオプションのみを選択またはクリアできます。</span><span class="sxs-lookup"><span data-stu-id="9e427-136">At this point in the design, you can only select or clear options for your deployment.</span></span> <span data-ttu-id="9e427-137">ただし、計画ツールの後のフェーズでその他のオプションを構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="9e427-137">However, you can configure more options in a later phase of the Planning Tool.</span></span> <span data-ttu-id="9e427-138">利用できないオプションもあり、オフにすることはできません。</span><span class="sxs-lookup"><span data-stu-id="9e427-138">There are also options that are unavailable and cannot be cleared.</span></span> <span data-ttu-id="9e427-139">また、別のオプションをオフにするには、1つのオプションをオフにする必要がある場合もあります。</span><span class="sxs-lookup"><span data-stu-id="9e427-139">In addition, you may have to clear one option in order to clear another.</span></span> <span data-ttu-id="9e427-140">たとえば、[ボイス] の [**エンタープライズボイス**] オプションをオフにすると、[サーバーアプリケーション (すべての機能はエンタープライズ voip の機能)] の下の [**返信] グループ**、**お知らせ**、および [**コールパーク**] のオプションもクリアされます。</span><span class="sxs-lookup"><span data-stu-id="9e427-140">For example, if you clear the **Enterprise Voice** option under Voice, then the **Response Group**, **Announcement**, and **Call Park** options under Server Applications (all of which are features of Enterprise Voice) are also cleared.</span></span>

11. <span data-ttu-id="9e427-141">サイト名とユーザー数を定義したら、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9e427-141">After defining a site name and number of users, click **Next**.</span></span>

12. <span data-ttu-id="9e427-142">SIP ドメイン、会議の設定、音声の設定とインフラストラクチャ、Exchange UM、外部ユーザーアクセス、常設チャットの設定、クライアント設定、collocation オプション、ブランチサイトについての情報を、次のページで確認できます。</span><span class="sxs-lookup"><span data-stu-id="9e427-142">The following pages ask for information about SIP domains, conference settings, voice settings and infrastructure, Exchange UM, external user access, Persistent Chat settings, client settings, collocation options, and branch sites.</span></span> <span data-ttu-id="9e427-143">これらの質問に適切に回答します。</span><span class="sxs-lookup"><span data-stu-id="9e427-143">Answer these questions as appropriate.</span></span>

13. <span data-ttu-id="9e427-144">最後の質問では、別のセントラルサイトを作成するかどうかをたずねられます。</span><span class="sxs-lookup"><span data-stu-id="9e427-144">The final question asks if you want to create another central site.</span></span> <span data-ttu-id="9e427-145">[**はい**] を選択すると、計画ツールは [セントラルサイト] ページに戻ります。</span><span class="sxs-lookup"><span data-stu-id="9e427-145">If you select **Yes**, then the Planning Tool returns to the Central Sites page.</span></span> <span data-ttu-id="9e427-146">[**いいえ**] を選択した場合は、[**次へ**]、[**描画**] の順にクリックすると、基本的なグローバル トポロジ ビューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9e427-146">If you select **No**, click **Next**, and then click **Draw** to display the high-level Global Topology view.</span></span>

14. <span data-ttu-id="9e427-147">既存のトポロジを表示するには、[**表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9e427-147">To view an existing topology, click **Display**.</span></span>

15. <span data-ttu-id="9e427-148">前に保存したトポロジを表す .xml ファイルをクリックして、[**開く**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9e427-148">Click the .xml file that represents the previously saved topology, and then click **Open**.</span></span>

16. <span data-ttu-id="9e427-149">計画ツールによって、グローバルトポロジページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9e427-149">The Planning Tool displays the Global Topology page.</span></span> <span data-ttu-id="9e427-150">計画ツールで利用可能なツールを使用して、トポロジの編集、更新、または変更を開始できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="9e427-150">You can now begin editing, updating, or changing the topology by using the tools available in the Planning Tool.</span></span>

## <a name="see-also"></a><span data-ttu-id="9e427-151">関連項目</span><span class="sxs-lookup"><span data-stu-id="9e427-151">See also</span></span>

[<span data-ttu-id="9e427-152">Editing the Design</span><span class="sxs-lookup"><span data-stu-id="9e427-152">Editing the Design</span></span>](https://technet.microsoft.com/library/08f639ba-0e5f-4ae7-9191-c3d96c25b169.aspx)
