---
title: Skype for Business Server 2015 の初期トポロジ設計を作成する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Skype for Business Server 計画ツールのインストールが完了したら、計画ツールを開始し、提案された Skype for Business Server 2015 インフラストラクチャの設計を開始する準備が整いました。
ms.openlocfilehash: 756c59ce0598af186a5cedabe250f7f1e7ec323c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098683"
---
# <a name="create-the-initial-topology-design-for-skype-for-business-server-2015"></a><span data-ttu-id="0d354-103">Skype for Business Server 2015 の初期トポロジ設計を作成する</span><span class="sxs-lookup"><span data-stu-id="0d354-103">Create the initial topology design for Skype for Business Server 2015</span></span>

<span data-ttu-id="0d354-104">Skype for Business Server 計画ツールのインストールが完了したら、計画ツールを開始し、提案された Skype for Business Server 2015 インフラストラクチャの設計を開始する準備が整いました。</span><span class="sxs-lookup"><span data-stu-id="0d354-104">After you have finished installing the Skype for Business Server Planning Tool, you are ready to start the Planning Tool and begin designing the proposed Skype for Business Server 2015 infrastructure.</span></span>

> [!NOTE]
>  <span data-ttu-id="0d354-105">計画ツールは、サイトとトポロジを設計する際の意思決定プロセスを通知する詳細なガイドを含むウィザード駆動型ツールです。</span><span class="sxs-lookup"><span data-stu-id="0d354-105">The Planning Tool is a wizard-driven tool with detailed guides to inform your decision-making process in designing your sites and topology.</span></span> <span data-ttu-id="0d354-106">このトピックは、網羅的なガイドとしてではなく、設計セッションで計画ツールを使い始めるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="0d354-106">This topic is intended not as an exhaustive guide, but simply to help get you started using the Planning Tool in your design sessions.</span></span>

### <a name="to-get-started-using-the-planning-tool-and-create-the-initial-design"></a><span data-ttu-id="0d354-107">計画ツールを使用して作業を開始し、最初の設計を作成するには</span><span class="sxs-lookup"><span data-stu-id="0d354-107">To get started using the Planning Tool and create the initial design</span></span>

1. <span data-ttu-id="0d354-108">Skype for Business Server 2015 計画ツールを開始する: [スタート] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business Server 2015]** をクリックし、[計画ツール]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="0d354-108">Start the Skype for Business Server 2015 Planning Tool: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Planning Tool**.</span></span>

2. <span data-ttu-id="0d354-109">計画ツールが開始すると **、[Skype for Business Server 2015** の計画ツールへようこそ] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0d354-109">After the Planning Tool has started, the **Welcome to the Planning Tool for Skype for Business Server 2015** page appears.</span></span> <span data-ttu-id="0d354-110">デザインを開始するには、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="0d354-110">Choose one of the following options to begin your design:</span></span>

   - <span data-ttu-id="0d354-111">**オプション 1: 開始する** [開始] **をクリックすると** 、条件を定義する関連する選択項目を含む、特定の一連のインタビュー質問が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0d354-111">**Option 1: Get Started** Clicking **Get Started** provides a specific series of interview questions with relevant selections to define the criteria.</span></span> <span data-ttu-id="0d354-112">最初の **[開始]** の質問セクションが終わったら、**[サイトの設計]** に進んでサイトのアーキテクチャを定義します。</span><span class="sxs-lookup"><span data-stu-id="0d354-112">After you have finished the initial **Get Started** interview section, you proceed into **Design Sites** to define your site architecture.</span></span> <span data-ttu-id="0d354-113">このオプションを完了するには、ステップ 3 に進みます。</span><span class="sxs-lookup"><span data-stu-id="0d354-113">To complete this option, proceed to step 3.</span></span>

   - <span data-ttu-id="0d354-114">**オプション 2: デザイン サイト** [ようこそ] **ページの [** デザイン サイト] をクリックすると、[開始] セクションに示されているインタビューの質問 **がバイパス** されます。</span><span class="sxs-lookup"><span data-stu-id="0d354-114">**Option 2: Design Sites** Clicking **Design Sites** at the Welcome page bypasses the interview questions presented in the **Get Started** section.</span></span> <span data-ttu-id="0d354-115">[開始する] セクションのインタビューの質問に応答して収集される情報は、このオプションを使用して既定値に設定されます。</span><span class="sxs-lookup"><span data-stu-id="0d354-115">The information that would have been gathered by responding to the interview questions in **Get Started** section is set to default values with this option.</span></span> <span data-ttu-id="0d354-116">[サイトの **設計] をクリック** すると、経験豊富なデザイナーは、最初のインタビューをバイパスし、必要に応じて中央サイトの開始ページで既定値 **を** 変更できます。</span><span class="sxs-lookup"><span data-stu-id="0d354-116">By clicking **Design Sites**, the experienced designer can bypass the initial interview and change the default values, as needed, on the **Central Sites** start page.</span></span> <span data-ttu-id="0d354-117">このオプションを完了するには、ステップ 3 ～ 5 をスキップしてステップ 6 から開始してください。</span><span class="sxs-lookup"><span data-stu-id="0d354-117">To complete this option, skip over steps 3-5 and start at step 6.</span></span>

   - <span data-ttu-id="0d354-118">**オプション 3: 保存したトポロジを表示する** 計画ツールの以前の使用を通じてトポロジを既に完了して保存している場合は、これらの手順のほとんどをスキップして、トポロジを開いて表示します。</span><span class="sxs-lookup"><span data-stu-id="0d354-118">**Option 3: Display Your Saved Topology** If you have already completed and saved a topology through previous use of the Planning Tool, you can skip over most of these steps and start by opening and displaying the topology.</span></span> <span data-ttu-id="0d354-119">トポロジを変更して更新し、再保存してから、Microsoft Excel または Microsoft Visio にエクスポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="0d354-119">You can also make changes and updates to the topology, resave it, and then export it to Microsoft Excel or Microsoft Visio.</span></span> <span data-ttu-id="0d354-120">このオプションを完了するには、ステップ 3 ～ 12 をスキップしてステップ 13 から開始してください。</span><span class="sxs-lookup"><span data-stu-id="0d354-120">To complete this option, skip over steps 3-12 and start at step 13.</span></span>

3. <span data-ttu-id="0d354-121">[ **開始] を** クリックして、Skype for Business Server 2015 トポロジの設計を開始します。</span><span class="sxs-lookup"><span data-stu-id="0d354-121">Click **Get Started** to begin designing your Skype for Business Server 2015 topology.</span></span>

4. <span data-ttu-id="0d354-122">設計に対して該当する条件を選択して各セクションに回答し、**[次へ]** をクリックして、ウィザードの次のページに進みます。</span><span class="sxs-lookup"><span data-stu-id="0d354-122">Answer each section by selecting the appropriate criteria for your design, and then click **Next** to proceed to the next Wizard page.</span></span> <span data-ttu-id="0d354-123">[ **戻る]** をクリックして、前のページに変更を加えます。</span><span class="sxs-lookup"><span data-stu-id="0d354-123">Click **Back** to make changes on previous pages.</span></span>

    > [!TIP]
    > <span data-ttu-id="0d354-124">各ページには、選択条件の説明および望ましい方法や処理能力計画に基づいた推奨事項が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0d354-124">Each page has a description of the selection criteria, and recommendations based on preferred practices and capacity planning.</span></span> <span data-ttu-id="0d354-125">詳細が必要な場合は、[詳細] をクリックして、Microsoft Web サイトの Skype for Business Server 2015 Planning ドキュメントの詳細情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0d354-125">If you require additional details, click **Learn more** to read detailed information from the Skype for Business Server 2015 Planning documentation on the Microsoft  website.</span></span> <span data-ttu-id="0d354-126">Microsoft Web サイトにアクセスするには、インターネット接続が必要です。</span><span class="sxs-lookup"><span data-stu-id="0d354-126">You must have Internet connectivity to access the Microsoft  website.</span></span>

5. <span data-ttu-id="0d354-127">設計に適合するオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="0d354-127">Select the appropriate options for your design.</span></span> <span data-ttu-id="0d354-128">初期条件を定義すると、新しいページが表示され [機能の概要] が完成しているかどうかが確認されます。</span><span class="sxs-lookup"><span data-stu-id="0d354-128">After the initial criteria are defined, a page will confirm that your Features Overview is complete.</span></span>

6. <span data-ttu-id="0d354-129">[サイト **の設計] を** クリックして、中央サイトを定義します。</span><span class="sxs-lookup"><span data-stu-id="0d354-129">Click **Design Sites** to define your central site.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0d354-130">各 Skype for Business Server 2015 トポロジには、少なくとも 1 つの中央サイトがあります。</span><span class="sxs-lookup"><span data-stu-id="0d354-130">Each Skype for Business Server 2015 topology will have at least one central site.</span></span> <span data-ttu-id="0d354-131">設計には、単一の中央サイト、多数のブランチ サイトを持つ中央サイト、多数の中央サイト、または各中央サイトに関連付けられたブランチ サイトを持つ多数の中央サイトがあります。</span><span class="sxs-lookup"><span data-stu-id="0d354-131">Your design may have a single central site, a central site with a number of branch sites, a number of central sites, or a number of central sites with branch sites associated with each central site.</span></span>

7. <span data-ttu-id="0d354-132">[ **サイト名]** に、この中央サイトを識別する名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="0d354-132">In **Site Name**, type the name that will identify this central site.</span></span>

8. <span data-ttu-id="0d354-133">[Site **Homed Users]** で、この中央サイトにホームを設定するオンプレミスの同時ユーザーの予想数を入力します。</span><span class="sxs-lookup"><span data-stu-id="0d354-133">In **Site Homed Users**, type the expected number of on-premises concurrent users who will be homed in this central site.</span></span>

9. <span data-ttu-id="0d354-134">[Cloud **Homed Users]** で、この中央サイトにホームになるオンライン同時ユーザーの予想数を入力します。</span><span class="sxs-lookup"><span data-stu-id="0d354-134">In **Cloud Homed Users**, type the expected number of online concurrent users who will be homed in this central site.</span></span>

10. <span data-ttu-id="0d354-135">必要に応じて、オンライン コラボレーション、ユーザー、音声、追加展開オプション、またはサーバー アプリケーションの選択内容を変更します。</span><span class="sxs-lookup"><span data-stu-id="0d354-135">Modify the selections for Online Collaboration, Users, Voice, Additional Deployment Options, or Server Applications, as needed.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="0d354-136">デザインのこの時点では、展開のオプションのみを選択またはクリアできます。</span><span class="sxs-lookup"><span data-stu-id="0d354-136">At this point in the design, you can only select or clear options for your deployment.</span></span> <span data-ttu-id="0d354-137">ただし、計画ツールの後のフェーズでは、その他のオプションを構成できます。</span><span class="sxs-lookup"><span data-stu-id="0d354-137">However, you can configure more options in a later phase of the Planning Tool.</span></span> <span data-ttu-id="0d354-138">また、使用できないオプションやクリアできないオプションも用意されています。</span><span class="sxs-lookup"><span data-stu-id="0d354-138">There are also options that are unavailable and cannot be cleared.</span></span> <span data-ttu-id="0d354-139">さらに、別のオプションをクリアするには、1 つのオプションをクリアする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0d354-139">In addition, you may have to clear one option in order to clear another.</span></span> <span data-ttu-id="0d354-140">たとえば、[Voice] の **[エンタープライズ VoIP]** オプションをオフにすると、[サーバー アプリケーション] の[応答グループ] 、[アナウンス] 、および [通話パーク] オプション (エンタープライズ VoIP の機能のすべて) もクリアされます。 </span><span class="sxs-lookup"><span data-stu-id="0d354-140">For example, if you clear the **Enterprise Voice** option under Voice, then the **Response Group**, **Announcement**, and **Call Park** options under Server Applications (all of which are features of Enterprise Voice) are also cleared.</span></span>

11. <span data-ttu-id="0d354-141">サイト名とユーザー数を定義したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0d354-141">After defining a site name and number of users, click **Next**.</span></span>

12. <span data-ttu-id="0d354-142">次のページでは、SIP ドメイン、会議設定、音声設定とインフラストラクチャ、Exchange UM、外部ユーザー アクセス、常設チャット設定、クライアント設定、コロケーション オプション、ブランチ サイトに関する情報を求めるメッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="0d354-142">The following pages ask for information about SIP domains, conference settings, voice settings and infrastructure, Exchange UM, external user access, Persistent Chat settings, client settings, collocation options, and branch sites.</span></span> <span data-ttu-id="0d354-143">これらの質問に適切に回答します。</span><span class="sxs-lookup"><span data-stu-id="0d354-143">Answer these questions as appropriate.</span></span>

13. <span data-ttu-id="0d354-144">最後の質問では、別の中央サイトを作成する必要がある場合に質問されます。</span><span class="sxs-lookup"><span data-stu-id="0d354-144">The final question asks if you want to create another central site.</span></span> <span data-ttu-id="0d354-145">[はい] **を選択** すると、[計画ツール] が [中央サイト] ページに戻ります。</span><span class="sxs-lookup"><span data-stu-id="0d354-145">If you select **Yes**, then the Planning Tool returns to the Central Sites page.</span></span> <span data-ttu-id="0d354-146">[いいえ] を **選択した** 場合は、[**次** へ] をクリックし、[描画] をクリックして、高レベルのグローバル トポロジ ビューを表示します。 </span><span class="sxs-lookup"><span data-stu-id="0d354-146">If you select **No**, click **Next**, and then click **Draw** to display the high-level Global Topology view.</span></span>

14. <span data-ttu-id="0d354-147">既存のトポロジを表示するには、[表示] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="0d354-147">To view an existing topology, click **Display**.</span></span>

15. <span data-ttu-id="0d354-148">前に保存したトポロジを表す .xml ファイルをクリックして、**[開く]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0d354-148">Click the .xml file that represents the previously saved topology, and then click **Open**.</span></span>

16. <span data-ttu-id="0d354-149">計画ツールには、[グローバル トポロジ] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0d354-149">The Planning Tool displays the Global Topology page.</span></span> <span data-ttu-id="0d354-150">これで、計画ツールで使用できるツールを使用して、トポロジの編集、更新、または変更を開始できます。</span><span class="sxs-lookup"><span data-stu-id="0d354-150">You can now begin editing, updating, or changing the topology by using the tools available in the Planning Tool.</span></span>

## <a name="see-also"></a><span data-ttu-id="0d354-151">関連項目</span><span class="sxs-lookup"><span data-stu-id="0d354-151">See also</span></span>

[<span data-ttu-id="0d354-152">設計の編集</span><span class="sxs-lookup"><span data-stu-id="0d354-152">Editing the Design</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-editing-the-design)