---
title: 'Lync Server 2013: 初期トポロジ設計の作成'
description: 'Lync Server 2013: 初期トポロジ設計を作成します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create the initial design
ms:assetid: f3131153-de14-41be-b1e6-7d4bb0191af1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615047(v=OCS.15)
ms:contentKeyID: 51541530
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c91bfe68a1de4a1f9862948edd708b8efa6a5c6d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551093"
---
# <a name="create-the-initial-topology-design-for-lync-server-2013"></a><span data-ttu-id="455fb-103">Lync Server 2013 の初期トポロジ設計を作成する</span><span class="sxs-lookup"><span data-stu-id="455fb-103">Create the initial topology design for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="455fb-104">_**トピックの最終更新日:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="455fb-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="455fb-105">Lync Server 2013 の計画ツールのインストールが終了したら、計画ツールを開始して、提案されている Lync Server 2013 インフラストラクチャの設計を開始する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="455fb-105">After you have finished installing the Lync Server 2013, Planning Tool, you are ready to start the Planning Tool and begin designing the proposed Lync Server 2013 infrastructure.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="455fb-106">計画ツールは、詳細なガイドを備えたウィザードベースのツールであり、サイトとトポロジの設計における意思決定プロセスについての情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="455fb-106">The Planning Tool is a wizard-driven tool with detailed guides to inform your decision-making process in designing your sites and topology.</span></span> <span data-ttu-id="455fb-107">このトピックは完全なガイドではありませんが、設計セッションで計画ツールの使用を開始するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="455fb-107">This topic is intended not as an exhaustive guide, but simply to help get you started using the Planning Tool in your design sessions.</span></span>



</div>

<div>

## <a name="to-get-started-using-the-planning-tool-and-create-the-initial-design"></a><span data-ttu-id="455fb-108">計画ツールを使用して作業を開始し、最初の設計を作成するには</span><span class="sxs-lookup"><span data-stu-id="455fb-108">To get started using the Planning Tool and create the initial design</span></span>

1.  <span data-ttu-id="455fb-109">Lync Server 2013 計画ツールを以下の手順で起動します。[**スタート**] ボタンをクリックし、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**計画ツール**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="455fb-109">Start the Lync Server 2013, Planning Tool: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Planning Tool**.</span></span>

2.  <span data-ttu-id="455fb-110">計画ツールが開始されると、「 **Planning tool For Microsoft Lync Server 2013 へようこそ** 」ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="455fb-110">After the Planning Tool has started, the **Welcome to the Planning Tool for Microsoft Lync Server 2013** page appears.</span></span> <span data-ttu-id="455fb-111">次のいずれかのオプションを選択して、設計を開始します。</span><span class="sxs-lookup"><span data-stu-id="455fb-111">Choose one of the following options to begin your design:</span></span>
    
      - <span data-ttu-id="455fb-112">**オプション 1: 作業の開始**    [**開始**] をクリックすると、特定の一連のインタビュー質問が表示され、条件を定義できます。</span><span class="sxs-lookup"><span data-stu-id="455fb-112">**Option 1: Get Started**   Clicking **Get Started** provides a specific series of interview questions with relevant selections to define the criteria.</span></span> <span data-ttu-id="455fb-113">最初の **[開始]** の質問セクションが終わったら、**[サイトの設計]** に進んでサイトのアーキテクチャを定義します。</span><span class="sxs-lookup"><span data-stu-id="455fb-113">After you have finished the initial **Get Started** interview section, you proceed into **Design Sites** to define your site architecture.</span></span> <span data-ttu-id="455fb-114">このオプションを完了するには、ステップ 3 に進みます。</span><span class="sxs-lookup"><span data-stu-id="455fb-114">To complete this option, proceed to step 3.</span></span>
    
      - <span data-ttu-id="455fb-115">**オプション 2: サイト**     の設計ウェルカムページで [**サイトの設計**] をクリックすると、[**作業の開始**] セクションに表示されるインタビューの質問は無視されます。</span><span class="sxs-lookup"><span data-stu-id="455fb-115">**Option 2: Design Sites**   Clicking **Design Sites** at the Welcome page bypasses the interview questions presented in the **Get Started** section.</span></span> <span data-ttu-id="455fb-116">「 **はじめ** に」セクションの「インタビューの質問」に返答することによって収集された情報は、このオプションを使用して既定値に設定されています。</span><span class="sxs-lookup"><span data-stu-id="455fb-116">The information that would have been gathered by responding to the interview questions in **Get Started** section is set to default values with this option.</span></span> <span data-ttu-id="455fb-117">[ **デザインサイト**] をクリックすると、経験豊富な設計者が最初のインタビューを省略し、必要に応じて既定値を変更することができます ( **中央サイト** の開始ページ)。</span><span class="sxs-lookup"><span data-stu-id="455fb-117">By clicking **Design Sites**, the experienced designer can bypass the initial interview and change the default values, as needed, on the **Central Sites** start page.</span></span> <span data-ttu-id="455fb-118">このオプションを完了するには、ステップ 3 ～ 5 をスキップしてステップ 6 から開始してください。</span><span class="sxs-lookup"><span data-stu-id="455fb-118">To complete this option, skip over steps 3-5 and start at step 6.</span></span>
    
      - <span data-ttu-id="455fb-119">**オプション 3: 保存したトポロジ**     を表示する計画ツールの以前の使用によってトポロジを既に完了し、保存している場合は、これらの手順の大部分をスキップし、トポロジを開いて表示することで開始できます。</span><span class="sxs-lookup"><span data-stu-id="455fb-119">**Option 3: Display Your Saved Topology**   If you have already completed and saved a topology through previous use of the Planning Tool, you can skip over most of these steps and start by opening and displaying the topology.</span></span> <span data-ttu-id="455fb-120">また、トポロジの変更や更新を行った後、再保存して、Microsoft Excel または Microsoft Visio にエクスポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="455fb-120">You can also make changes and updates to the topology, resave it, and then export it to Microsoft Excel or Microsoft Visio.</span></span> <span data-ttu-id="455fb-121">このオプションを完了するには、ステップ 3 ～ 12 をスキップしてステップ 13 から開始してください。</span><span class="sxs-lookup"><span data-stu-id="455fb-121">To complete this option, skip over steps 3-12 and start at step 13.</span></span>

3.  <span data-ttu-id="455fb-122">[ **今すぐ開始** ] をクリックして、Lync Server 2013 トポロジの設計を開始します。</span><span class="sxs-lookup"><span data-stu-id="455fb-122">Click **Get Started** to begin designing your Lync Server 2013 topology.</span></span>

4.  <span data-ttu-id="455fb-123">設計に対して該当する条件を選択して各セクションに回答し、**[次へ]** をクリックして、ウィザードの次のページに進みます。</span><span class="sxs-lookup"><span data-stu-id="455fb-123">Answer each section by selecting the appropriate criteria for your design, and then click **Next** to proceed to the next Wizard page.</span></span> <span data-ttu-id="455fb-124">前のページに変更を加えるには、[ **戻る** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="455fb-124">Click **Back** to make changes on previous pages.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="455fb-125">各ページには、選択条件の説明および望ましい方法や処理能力計画に基づいた推奨事項が表示されます。</span><span class="sxs-lookup"><span data-stu-id="455fb-125">Each page has a description of the selection criteria, and recommendations based on preferred practices and capacity planning.</span></span> <span data-ttu-id="455fb-126">詳細については、「詳細情報 <STRONG>」を参照して</STRONG> ください。詳細については、Microsoft TechNet web サイトの Lync Server 2013 の計画に関するドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="455fb-126">If you require additional details, click <STRONG>Learn more</STRONG> to read detailed information from the Lync Server 2013 Planning documentation on the Microsoft TechNet website.</span></span> <span data-ttu-id="455fb-127">Microsoft TechNet Web サイトにアクセスするには、インターネットに接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="455fb-127">You must have Internet connectivity to access the Microsoft TechNet website.</span></span>

    
    </div>

5.  <span data-ttu-id="455fb-128">設計に適合するオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="455fb-128">Select the appropriate options for your design.</span></span> <span data-ttu-id="455fb-129">初期条件を定義すると、新しいページが表示され [機能の概要] が完成しているかどうかが確認されます。</span><span class="sxs-lookup"><span data-stu-id="455fb-129">After the initial criteria are defined, a page will confirm that your Features Overview is complete.</span></span>

6.  <span data-ttu-id="455fb-130">[ **サイトの設計** ] をクリックして、セントラルサイトを定義します。</span><span class="sxs-lookup"><span data-stu-id="455fb-130">Click **Design Sites** to define your central site.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="455fb-131">各 Lync Server 2013 トポロジには、少なくとも1つの中央サイトがあります。</span><span class="sxs-lookup"><span data-stu-id="455fb-131">Each Lync Server 2013 topology will have at least one central site.</span></span> <span data-ttu-id="455fb-132">設計には、1つの中央サイト、複数のブランチサイトを含む中央サイト、中央サイトの数、各中央サイトに関連付けられたブランチサイトを備えた多数のセントラルサイトがあります。</span><span class="sxs-lookup"><span data-stu-id="455fb-132">Your design may have a single central site, a central site with a number of branch sites, a number of central sites, or a number of central sites with branch sites associated with each central site.</span></span>

    
    </div>

7.  <span data-ttu-id="455fb-133">[ **サイト名**] に、この中央サイトを識別する名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="455fb-133">In **Site Name**, type the name that will identify this central site.</span></span>

8.  <span data-ttu-id="455fb-134">[ **サイトの所属先ユーザー**] で、この中央サイトに所属する、予想される社内同時ユーザーの数を入力します。</span><span class="sxs-lookup"><span data-stu-id="455fb-134">In **Site Homed Users**, type the expected number of on-premises concurrent users who will be homed in this central site.</span></span>

9.  <span data-ttu-id="455fb-135">[ **クラウドに所属するユーザー**] に、この中央サイトに所属する、予想されるオンライン同時ユーザーの数を入力します。</span><span class="sxs-lookup"><span data-stu-id="455fb-135">In **Cloud Homed Users**, type the expected number of online concurrent users who will be homed in this central site.</span></span>

10. <span data-ttu-id="455fb-136">必要に応じて、オンライングループ作業、ユーザー、音声、その他の展開オプション、またはサーバーアプリケーションの選択を変更します。</span><span class="sxs-lookup"><span data-stu-id="455fb-136">Modify the selections for Online Collaboration, Users, Voice, Additional Deployment Options, or Server Applications, as needed.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="455fb-137">設計のこの時点では、展開のオプションのみを選択または選択解除できます。</span><span class="sxs-lookup"><span data-stu-id="455fb-137">At this point in the design, you can only select or clear options for your deployment.</span></span> <span data-ttu-id="455fb-138">ただし、計画ツールの後の段階では、より多くのオプションを構成できます。</span><span class="sxs-lookup"><span data-stu-id="455fb-138">However, you can configure more options in a later phase of the Planning Tool.</span></span> <span data-ttu-id="455fb-139">また、使用できなくなってクリアすることができないオプションもあります。</span><span class="sxs-lookup"><span data-stu-id="455fb-139">There are also options that are unavailable and cannot be cleared.</span></span> <span data-ttu-id="455fb-140">また、別のオプションをオフにするには、1つのオプションをオフにする必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="455fb-140">In addition, you may have to clear one option in order to clear another.</span></span> <span data-ttu-id="455fb-141">たとえば、[音声] の下の [ <STRONG>エンタープライズ voip</STRONG> ] オプションをオフにすると、[サーバーアプリケーション (すべてはエンタープライズ voip の機能)] の下にある <STRONG>応答グループ</STRONG>、 <STRONG>アナウンス</STRONG>、および <STRONG>コールパーク</STRONG> オプションもオフになります。</span><span class="sxs-lookup"><span data-stu-id="455fb-141">For example, if you clear the <STRONG>Enterprise Voice</STRONG> option under Voice, then the <STRONG>Response Group</STRONG>, <STRONG>Announcement</STRONG>, and <STRONG>Call Park</STRONG> options under Server Applications (all of which are features of Enterprise Voice) are also cleared.</span></span>

    
    </div>

11. <span data-ttu-id="455fb-142">サイト名とユーザー数を定義したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="455fb-142">After defining a site name and number of users, click **Next**.</span></span>

12. <span data-ttu-id="455fb-143">次のページでは、SIP ドメイン、会議の設定、音声の設定とインフラストラクチャ、Exchange UM、外部ユーザーアクセス、常設チャットの設定、クライアント設定、併置オプション、ブランチサイトについての情報を求められます。</span><span class="sxs-lookup"><span data-stu-id="455fb-143">The following pages ask for information about SIP domains, conference settings, voice settings and infrastructure, Exchange UM, external user access, Persistent Chat settings, client settings, collocation options, and branch sites.</span></span> <span data-ttu-id="455fb-144">これらの質問に適切に回答します。</span><span class="sxs-lookup"><span data-stu-id="455fb-144">Answer these questions as appropriate.</span></span>

13. <span data-ttu-id="455fb-145">最後の質問は、別のセントラルサイトを作成するかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="455fb-145">The final question asks if you want to create another central site.</span></span> <span data-ttu-id="455fb-146">[ **はい**] を選択すると、計画ツールは [中央サイト] ページに戻ります。</span><span class="sxs-lookup"><span data-stu-id="455fb-146">If you select **Yes**, then the Planning Tool returns to the Central Sites page.</span></span> <span data-ttu-id="455fb-147">[ **いいえ**] を選択した場合は、[ **次へ**] をクリックし、[ **描画** ] をクリックして、高レベルのグローバルトポロジビューを表示します。</span><span class="sxs-lookup"><span data-stu-id="455fb-147">If you select **No**, click **Next**, and then click **Draw** to display the high-level Global Topology view.</span></span>

14. <span data-ttu-id="455fb-148">既存のトポロジを表示するには、[ **表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="455fb-148">To view an existing topology, click **Display**.</span></span>

15. <span data-ttu-id="455fb-149">前に保存したトポロジを表す .xml ファイルをクリックして、**[開く]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="455fb-149">Click the .xml file that represents the previously saved topology, and then click **Open**.</span></span>

16. <span data-ttu-id="455fb-150">計画ツールでは、[グローバルトポロジ] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="455fb-150">The Planning Tool displays the Global Topology page.</span></span> <span data-ttu-id="455fb-151">計画ツールで利用可能なツールを使用して、トポロジの編集、更新、または変更を開始できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="455fb-151">You can now begin editing, updating, or changing the topology by using the tools available in the Planning Tool.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="455fb-152">関連項目</span><span class="sxs-lookup"><span data-stu-id="455fb-152">See Also</span></span>


[<span data-ttu-id="455fb-153">Lync Server 2013 での設計の編集</span><span class="sxs-lookup"><span data-stu-id="455fb-153">Editing the design in Lync Server 2013</span></span>](lync-server-2013-editing-the-design.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

