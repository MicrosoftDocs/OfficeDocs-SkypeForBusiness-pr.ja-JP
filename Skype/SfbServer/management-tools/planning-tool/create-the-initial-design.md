---
title: Skype for Business Server 2015 の初期トポロジ設計の作成
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 4/5/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f3131153-de14-41be-b1e6-7d4bb0191af1
description: Skype のビジネス サーバー計画ツールのインストールが完了したら後、は、計画ツールを起動し、サーバー 2015 のビジネス ・ インフラストラクチャの提案された Skype の設計を開始する準備が整ったら。
ms.openlocfilehash: 73fd6f4a83ec5aec6808124728c1c73419bcdd28
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/28/2018
ms.locfileid: "23246667"
---
# <a name="create-the-initial-topology-design-for-skype-for-business-server-2015"></a><span data-ttu-id="81e9c-103">Skype for Business Server 2015 の初期トポロジ設計の作成</span><span class="sxs-lookup"><span data-stu-id="81e9c-103">Create the initial topology design for Skype for Business Server 2015</span></span>

<span data-ttu-id="81e9c-104">Skype のビジネス サーバー計画ツールのインストールが完了したら後、は、計画ツールを起動し、サーバー 2015 のビジネス ・ インフラストラクチャの提案された Skype の設計を開始する準備が整ったら。</span><span class="sxs-lookup"><span data-stu-id="81e9c-104">After you have finished installing the Skype for Business Server Planning Tool, you are ready to start the Planning Tool and begin designing the proposed Skype for Business Server 2015 infrastructure.</span></span>

> [!NOTE]
>  <span data-ttu-id="81e9c-105">計画ツールは、サイトとトポロジを設計することで、意思決定のプロセスを通知するために詳細なガイドを使用してウィザード ベースのツールです。</span><span class="sxs-lookup"><span data-stu-id="81e9c-105">The Planning Tool is a wizard-driven tool with detailed guides to inform your decision-making process in designing your sites and topology.</span></span> <span data-ttu-id="81e9c-106">すべてを網羅したガイドでは、としてではなくツールを使用して、計画、設計のセッションでお客様を支援するためだけには、このトピックを対象としています。</span><span class="sxs-lookup"><span data-stu-id="81e9c-106">This topic is intended not as an exhaustive guide, but simply to help get you started using the Planning Tool in your design sessions.</span></span>

### <a name="to-get-started-using-the-planning-tool-and-create-the-initial-design"></a><span data-ttu-id="81e9c-107">計画ツールの使用を開始し、初期のデザインを作成するには</span><span class="sxs-lookup"><span data-stu-id="81e9c-107">To get started using the Planning Tool and create the initial design</span></span>

1. <span data-ttu-id="81e9c-108">ビジネス サーバー 2015 計画ツールは、Skype を起動する: [**スタート**] ボタン、[**すべてのプログラム**] をクリックして、**ビジネス サーバー 2015 の Skype**をクリックしておよび**計画ツール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="81e9c-108">Start the Skype for Business Server 2015 Planning Tool: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Planning Tool**.</span></span>

2. <span data-ttu-id="81e9c-109">計画ツールの起動後、 **Skype のビジネス サーバー 2015 の計画ツールへようこそ**] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="81e9c-109">After the Planning Tool has started, the **Welcome to the Planning Tool for Skype for Business Server 2015** page appears.</span></span> <span data-ttu-id="81e9c-110">次のいずれかを選択して、設計を開始します。</span><span class="sxs-lookup"><span data-stu-id="81e9c-110">Choose one of the following options to begin your design:</span></span>

   - <span data-ttu-id="81e9c-111">**オプション 1: 開始****開始**をクリックすると、特定の一連の条件を定義するのには関連する選択範囲を面接の質問を提供します。</span><span class="sxs-lookup"><span data-stu-id="81e9c-111">**Option 1: Get Started** Clicking **Get Started** provides a specific series of interview questions with relevant selections to define the criteria.</span></span> <span data-ttu-id="81e9c-112">初期**開始**のインタビューのセクションが完了したら後、は、サイトのアーキテクチャを定義するのには**サイトを設計**に進みます。</span><span class="sxs-lookup"><span data-stu-id="81e9c-112">After you have finished the initial **Get Started** interview section, you proceed into **Design Sites** to define your site architecture.</span></span> <span data-ttu-id="81e9c-113">このオプションを完了するには、手順 3 に進みます。</span><span class="sxs-lookup"><span data-stu-id="81e9c-113">To complete this option, proceed to step 3.</span></span>

   - <span data-ttu-id="81e9c-114">**オプション 2: サイトのデザイン**[ようこそ] ページで**サイトのデザイン**をクリックすると「**はじめ**に」に記載されている面接質問を無視します。</span><span class="sxs-lookup"><span data-stu-id="81e9c-114">**Option 2: Design Sites** Clicking **Design Sites** at the Welcome page bypasses the interview questions presented in the **Get Started** section.</span></span> <span data-ttu-id="81e9c-115">「**はじめ**に」のインタビューの質問に応答することによって収集された情報は、このオプションを既定値に設定されていますいます。</span><span class="sxs-lookup"><span data-stu-id="81e9c-115">The information that would have been gathered by responding to the interview questions in **Get Started** section is set to default values with this option.</span></span> <span data-ttu-id="81e9c-116">**デザインのサイト**をクリックすると、経験豊富なデザイナーが最初の面接をバイパスし、**セントラル サイト**のスタート ページで、必要に応じて既定値を変更できます。</span><span class="sxs-lookup"><span data-stu-id="81e9c-116">By clicking **Design Sites**, the experienced designer can bypass the initial interview and change the default values, as needed, on the **Central Sites** start page.</span></span> <span data-ttu-id="81e9c-117">このオプションを完了するために 3-5 の手順をスキップし、手順 6 で開始します。</span><span class="sxs-lookup"><span data-stu-id="81e9c-117">To complete this option, skip over steps 3-5 and start at step 6.</span></span>

   - <span data-ttu-id="81e9c-118">**オプション 3: 保存したトポロジの表示**場合は既に完了して保存したトポロジ計画のツールを使用する前から、次の手順のほとんどをスキップしを開くと、トポロジを表示して起動できます。</span><span class="sxs-lookup"><span data-stu-id="81e9c-118">**Option 3: Display Your Saved Topology** If you have already completed and saved a topology through previous use of the Planning Tool, you can skip over most of these steps and start by opening and displaying the topology.</span></span> <span data-ttu-id="81e9c-119">トポロジを変更および更新をするもし、それを保存し、Microsoft Excel または Microsoft Visio にエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="81e9c-119">You can also make changes and updates to the topology, resave it, and then export it to Microsoft Excel or Microsoft Visio.</span></span> <span data-ttu-id="81e9c-120">このオプションを完了するために 3-12 の手順をスキップし、手順 13 から開始してください。</span><span class="sxs-lookup"><span data-stu-id="81e9c-120">To complete this option, skip over steps 3-12 and start at step 13.</span></span>

3. <span data-ttu-id="81e9c-121">ビジネス サーバー 2015 トポロジの場合、Skype のデザインを開始する**開始**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="81e9c-121">Click **Get Started** to begin designing your Skype for Business Server 2015 topology.</span></span>

4. <span data-ttu-id="81e9c-p106">設計に対して該当する条件を選択して各セクションに回答し、[**次へ**] をクリックして、ウィザードの次のページに進みます。前の各ページを変更するには、[**戻る**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="81e9c-p106">Answer each section by selecting the appropriate criteria for your design, and then click **Next** to proceed to the next Wizard page. Click **Back** to make changes on previous pages.</span></span>

    > [!TIP]
    > <span data-ttu-id="81e9c-124">各ページには、選択条件の説明および望ましい方法や処理能力計画に基づいた推奨事項が表示されます。</span><span class="sxs-lookup"><span data-stu-id="81e9c-124">Each page has a description of the selection criteria, and recommendations based on preferred practices and capacity planning.</span></span> <span data-ttu-id="81e9c-125">追加の詳細情報を必要とする場合は、Microsoft の web サイト上のドキュメントのビジネス サーバー 2015 の計画の Skype から詳細な情報を読み取るため**の詳細を表示**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="81e9c-125">If you require additional details, click **Learn more** to read detailed information from the Skype for Business Server 2015 Planning documentation on the Microsoft  website.</span></span> <span data-ttu-id="81e9c-126">Microsoft の web サイトにアクセスするのにはインターネットに接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="81e9c-126">You must have Internet connectivity to access the Microsoft  website.</span></span>

5. <span data-ttu-id="81e9c-p108">設計に適合するオプションを選択します。初期条件を定義すると、新しいページが表示され [機能の概要] が完成しているかどうかが確認されます。</span><span class="sxs-lookup"><span data-stu-id="81e9c-p108">Select the appropriate options for your design. After the initial criteria are defined, a page will confirm that your Features Overview is complete.</span></span>

6. <span data-ttu-id="81e9c-129">セントラル サイトを定義するのには**サイトのデザイン**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="81e9c-129">Click **Design Sites** to define your central site.</span></span>

    > [!NOTE]
    > <span data-ttu-id="81e9c-130">ビジネス サーバー 2015 トポロジの各 Skype は、少なくとも 1 つのセントラル サイトにがあります。</span><span class="sxs-lookup"><span data-stu-id="81e9c-130">Each Skype for Business Server 2015 topology will have at least one central site.</span></span> <span data-ttu-id="81e9c-131">設計には、1 つのセントラル サイト、いくつかのブランチ サイトのいくつかの中心的なサイト、または各中央サイトに関連付けられているブランチ サイトと中央サイトの中心的なサイトがあります。</span><span class="sxs-lookup"><span data-stu-id="81e9c-131">Your design may have a single central site, a central site with a number of branch sites, a number of central sites, or a number of central sites with branch sites associated with each central site.</span></span>

7. <span data-ttu-id="81e9c-132">[**サイト名**] には、この中央のサイトを識別する名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="81e9c-132">In **Site Name**, type the name that will identify this central site.</span></span>

8. <span data-ttu-id="81e9c-133">] で、**サイトのホーム ユーザー**は、この中央のサイトに所属する設置同時ユーザーの数を入力します。</span><span class="sxs-lookup"><span data-stu-id="81e9c-133">In **Site Homed Users**, type the expected number of on-premises concurrent users who will be homed in this central site.</span></span>

9. <span data-ttu-id="81e9c-134">**クラウド ホーム ユーザー**の場合は、この中央のサイトに所属するオンラインの同時ユーザーの数を入力します。</span><span class="sxs-lookup"><span data-stu-id="81e9c-134">In **Cloud Homed Users**, type the expected number of online concurrent users who will be homed in this central site.</span></span>

10. <span data-ttu-id="81e9c-135">必要に応じて、オンライン コラボレーション、ユーザー、音声、追加展開オプション、またはサーバー アプリケーションの選択を変更します。</span><span class="sxs-lookup"><span data-stu-id="81e9c-135">Modify the selections for Online Collaboration, Users, Voice, Additional Deployment Options, or Server Applications, as needed.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="81e9c-136">この時点で設計では、することができますのみをオンまたはオフのオプションを展開するためです。</span><span class="sxs-lookup"><span data-stu-id="81e9c-136">At this point in the design, you can only select or clear options for your deployment.</span></span> <span data-ttu-id="81e9c-137">ただし、計画ツールの後の段階で、他のオプションを設定できます。</span><span class="sxs-lookup"><span data-stu-id="81e9c-137">However, you can configure more options in a later phase of the Planning Tool.</span></span> <span data-ttu-id="81e9c-138">オプションが使用できず、オフにできないこともあります。</span><span class="sxs-lookup"><span data-stu-id="81e9c-138">There are also options that are unavailable and cannot be cleared.</span></span> <span data-ttu-id="81e9c-139">さらに、別にクリアするために 1 つのオプションをオフにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="81e9c-139">In addition, you may have to clear one option in order to clear another.</span></span> <span data-ttu-id="81e9c-140">などの音声、**応答グループ**、**発表**では、[**エンタープライズ VoIP** ] オプションと [サーバー アプリケーション (すべてのエンタープライズ VoIP の機能)**コール パーク**オプションをオフにする場合もクリアします。</span><span class="sxs-lookup"><span data-stu-id="81e9c-140">For example, if you clear the **Enterprise Voice** option under Voice, then the **Response Group**, **Announcement**, and **Call Park** options under Server Applications (all of which are features of Enterprise Voice) are also cleared.</span></span>

11. <span data-ttu-id="81e9c-141">サイト名とユーザー数を定義したら、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="81e9c-141">After defining a site name and number of users, click **Next**.</span></span>

12. <span data-ttu-id="81e9c-142">次のページは、SIP ドメイン、会議の設定、音声設定とインフラストラクチャ、Exchange UM、外部ユーザー アクセス、永続的なチャットの設定、クライアントの設定、コロケーション オプション、およびブランチ サイトについては、情報を問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="81e9c-142">The following pages ask for information about SIP domains, conference settings, voice settings and infrastructure, Exchange UM, external user access, Persistent Chat settings, client settings, collocation options, and branch sites.</span></span> <span data-ttu-id="81e9c-143">これらの質問に適切に回答します。</span><span class="sxs-lookup"><span data-stu-id="81e9c-143">Answer these questions as appropriate.</span></span>

13. <span data-ttu-id="81e9c-144">最後の質問は、別のセントラル サイトを作成するかどうかを要求します。</span><span class="sxs-lookup"><span data-stu-id="81e9c-144">The final question asks if you want to create another central site.</span></span> <span data-ttu-id="81e9c-145">**[はい]** を選択した場合、計画ツールは、セントラル サイトのページに返します。</span><span class="sxs-lookup"><span data-stu-id="81e9c-145">If you select **Yes**, then the Planning Tool returns to the Central Sites page.</span></span> <span data-ttu-id="81e9c-146">[**いいえ**] を選択した場合は、[**次へ**]、[**描画**] の順にクリックすると、基本的なグローバル トポロジ ビューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="81e9c-146">If you select **No**, click **Next**, and then click **Draw** to display the high-level Global Topology view.</span></span>

14. <span data-ttu-id="81e9c-147">既存のトポロジを表示するには、[**表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="81e9c-147">To view an existing topology, click **Display**.</span></span>

15. <span data-ttu-id="81e9c-148">前に保存したトポロジを表す .xml ファイルをクリックして、[**開く**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="81e9c-148">Click the .xml file that represents the previously saved topology, and then click **Open**.</span></span>

16. <span data-ttu-id="81e9c-149">計画ツールでは、[グローバル トポロジ] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="81e9c-149">The Planning Tool displays the Global Topology page.</span></span> <span data-ttu-id="81e9c-150">計画ツールで使用可能なツールを使用してトポロジを変更または編集、更新、今すぐ開始できます。</span><span class="sxs-lookup"><span data-stu-id="81e9c-150">You can now begin editing, updating, or changing the topology by using the tools available in the Planning Tool.</span></span>

## <a name="see-also"></a><span data-ttu-id="81e9c-151">関連項目</span><span class="sxs-lookup"><span data-stu-id="81e9c-151">See also</span></span>

[<span data-ttu-id="81e9c-152">デザインを編集</span><span class="sxs-lookup"><span data-stu-id="81e9c-152">Editing the Design</span></span>](https://technet.microsoft.com/library/08f639ba-0e5f-4ae7-9191-c3d96c25b169.aspx)