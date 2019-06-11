---
title: 'Lync Server 2013: 最初のトポロジ設計を作成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create the initial design
ms:assetid: f3131153-de14-41be-b1e6-7d4bb0191af1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615047(v=OCS.15)
ms:contentKeyID: 51541530
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 656e9605695fe7dab160469ffa9e9c5075ac807b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833768"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-the-initial-topology-design-for-lync-server-2013"></a><span data-ttu-id="5218e-102">Lync Server 2013 用の最初のトポロジ設計を作成する</span><span class="sxs-lookup"><span data-stu-id="5218e-102">Create the initial topology design for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5218e-103">_**最終更新日:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="5218e-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="5218e-104">Lync Server 2013、計画ツールのインストールが完了したら、計画ツールを開始して、提案された Lync Server 2013 インフラストラクチャの設計を開始する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="5218e-104">After you have finished installing the Lync Server 2013, Planning Tool, you are ready to start the Planning Tool and begin designing the proposed Lync Server 2013 infrastructure.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5218e-105">計画ツールは、サイトとトポロジの設計で意思決定プロセスについて通知するための詳細なガイドを含むウィザードベースのツールです。</span><span class="sxs-lookup"><span data-stu-id="5218e-105">The Planning Tool is a wizard-driven tool with detailed guides to inform your decision-making process in designing your sites and topology.</span></span> <span data-ttu-id="5218e-106">このトピックは、すべてを網羅したガイドではありませんが、設計セッションで計画ツールを使い始めることができるようにすることを目的としています。</span><span class="sxs-lookup"><span data-stu-id="5218e-106">This topic is intended not as an exhaustive guide, but simply to help get you started using the Planning Tool in your design sessions.</span></span>



</div>

<div>

## <a name="to-get-started-using-the-planning-tool-and-create-the-initial-design"></a><span data-ttu-id="5218e-107">計画ツールの使用を開始するには、最初のデザインを作成するには</span><span class="sxs-lookup"><span data-stu-id="5218e-107">To get started using the Planning Tool and create the initial design</span></span>

1.  <span data-ttu-id="5218e-108">Lync Server 2013、計画ツールを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[**計画ツール**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="5218e-108">Start the Lync Server 2013, Planning Tool: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Planning Tool**.</span></span>

2.  <span data-ttu-id="5218e-109">計画ツールが開始されると、**計画ツールの [Microsoft Lync Server 2013 へようこそ**] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5218e-109">After the Planning Tool has started, the **Welcome to the Planning Tool for Microsoft Lync Server 2013** page appears.</span></span> <span data-ttu-id="5218e-110">次のいずれかを選択して、設計を開始します。</span><span class="sxs-lookup"><span data-stu-id="5218e-110">Choose one of the following options to begin your design:</span></span>
    
      - <span data-ttu-id="5218e-111">**オプション 1:**   [はじめに\*\*\*\* ] をクリックすると、検索条件を定義する関連項目が含まれている特定の一連の面接質問が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5218e-111">**Option 1: Get Started**   Clicking **Get Started** provides a specific series of interview questions with relevant selections to define the criteria.</span></span> <span data-ttu-id="5218e-112">初めての「面接**開始**」セクションを完了した後、サイトのアーキテクチャを定義するための**設計サイト**に進みます。</span><span class="sxs-lookup"><span data-stu-id="5218e-112">After you have finished the initial **Get Started** interview section, you proceed into **Design Sites** to define your site architecture.</span></span> <span data-ttu-id="5218e-113">このオプションを完了するには、手順3に進みます。</span><span class="sxs-lookup"><span data-stu-id="5218e-113">To complete this option, proceed to step 3.</span></span>
    
      - <span data-ttu-id="5218e-114">**オプション 2:**   [ようこそ] ページで [**デザインサイト**] をクリックすると、[はじめ\*\*\*\* に] セクションに表示される面接の質問が無視されます。</span><span class="sxs-lookup"><span data-stu-id="5218e-114">**Option 2: Design Sites**   Clicking **Design Sites** at the Welcome page bypasses the interview questions presented in the **Get Started** section.</span></span> <span data-ttu-id="5218e-115">「**はじめ**に」セクションの「面接の質問」セクションで収集された情報は、このオプションを使用して既定値に設定されています。</span><span class="sxs-lookup"><span data-stu-id="5218e-115">The information that would have been gathered by responding to the interview questions in **Get Started** section is set to default values with this option.</span></span> <span data-ttu-id="5218e-116">[**サイトのデザイン**] をクリックすることで、経験豊富なデザイナーは最初のインタビューを回避し、必要\*\*\*\* に応じて既定値を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="5218e-116">By clicking **Design Sites**, the experienced designer can bypass the initial interview and change the default values, as needed, on the **Central Sites** start page.</span></span> <span data-ttu-id="5218e-117">このオプションを完了するには、手順3-5 をスキップして、手順6から始めます。</span><span class="sxs-lookup"><span data-stu-id="5218e-117">To complete this option, skip over steps 3-5 and start at step 6.</span></span>
    
      - <span data-ttu-id="5218e-118">**オプション 3:**   計画ツールの以前の使用によってトポロジを既に完了し保存している場合は、保存されているトポロジを表示する次の手順をスキップして、最初にトポロジを開いて表示することができます。</span><span class="sxs-lookup"><span data-stu-id="5218e-118">**Option 3: Display Your Saved Topology**   If you have already completed and saved a topology through previous use of the Planning Tool, you can skip over most of these steps and start by opening and displaying the topology.</span></span> <span data-ttu-id="5218e-119">また、トポロジの変更や更新を行ったり、保存したり、Microsoft Excel または Microsoft Visio にエクスポートしたりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="5218e-119">You can also make changes and updates to the topology, resave it, and then export it to Microsoft Excel or Microsoft Visio.</span></span> <span data-ttu-id="5218e-120">このオプションを完了するには、手順3-12 をスキップして、手順13から始めます。</span><span class="sxs-lookup"><span data-stu-id="5218e-120">To complete this option, skip over steps 3-12 and start at step 13.</span></span>

3.  <span data-ttu-id="5218e-121">[**はじめ**に] をクリックして、Lync Server 2013 トポロジの設計を開始します。</span><span class="sxs-lookup"><span data-stu-id="5218e-121">Click **Get Started** to begin designing your Lync Server 2013 topology.</span></span>

4.  <span data-ttu-id="5218e-p106">設計に対して該当する条件を選択して各セクションに回答し、[**次へ**] をクリックして、ウィザードの次のページに進みます。前の各ページを変更するには、[**戻る**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5218e-p106">Answer each section by selecting the appropriate criteria for your design, and then click **Next** to proceed to the next Wizard page. Click **Back** to make changes on previous pages.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="5218e-124">各ページには、選択条件の説明および望ましい方法や処理能力計画に基づいた推奨事項が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5218e-124">Each page has a description of the selection criteria, and recommendations based on preferred practices and capacity planning.</span></span> <span data-ttu-id="5218e-125">追加の詳細が必要な場合は、「<STRONG>詳細</STRONG>情報」をクリックして、Microsoft TechNet web サイトの Lync Server 2013 計画のドキュメントから詳細情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5218e-125">If you require additional details, click <STRONG>Learn more</STRONG> to read detailed information from the Lync Server 2013 Planning documentation on the Microsoft TechNet website.</span></span> <span data-ttu-id="5218e-126">Microsoft TechNet Web サイトにアクセスするには、インターネットに接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5218e-126">You must have Internet connectivity to access the Microsoft TechNet website.</span></span>

    
    </div>

5.  <span data-ttu-id="5218e-127">設計に適合するオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="5218e-127">Select the appropriate options for your design.</span></span> <span data-ttu-id="5218e-128">初期条件を定義すると、新しいページが表示され [機能の概要] が完成しているかどうかが確認されます。</span><span class="sxs-lookup"><span data-stu-id="5218e-128">After the initial criteria are defined, a page will confirm that your Features Overview is complete.</span></span>

6.  <span data-ttu-id="5218e-129">[**サイトのデザイン**] をクリックしてセントラルサイトを定義します。</span><span class="sxs-lookup"><span data-stu-id="5218e-129">Click **Design Sites** to define your central site.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5218e-130">各 Lync Server 2013 トポロジには、少なくとも1つのセントラルサイトが含まれます。</span><span class="sxs-lookup"><span data-stu-id="5218e-130">Each Lync Server 2013 topology will have at least one central site.</span></span> <span data-ttu-id="5218e-131">設計には、1つのセントラルサイト、多数のブランチサイトを含むセントラルサイト、一連のセントラルサイト、または各セントラルサイトに関連付けられたブランチサイトを含むセントラルサイトが含まれている場合があります。</span><span class="sxs-lookup"><span data-stu-id="5218e-131">Your design may have a single central site, a central site with a number of branch sites, a number of central sites, or a number of central sites with branch sites associated with each central site.</span></span>

    
    </div>

7.  <span data-ttu-id="5218e-132">[**サイト名**] に、このセントラルサイトを識別する名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="5218e-132">In **Site Name**, type the name that will identify this central site.</span></span>

8.  <span data-ttu-id="5218e-133">[**サイトのホームユーザー**] に、このセントラルサイトに表示されるオンプレミスの同時ユーザー数を入力します。</span><span class="sxs-lookup"><span data-stu-id="5218e-133">In **Site Homed Users**, type the expected number of on-premises concurrent users who will be homed in this central site.</span></span>

9.  <span data-ttu-id="5218e-134">[**クラウドのホームユーザー**] に、このセントラルサイトに表示されるオンラインの同時ユーザー数を入力します。</span><span class="sxs-lookup"><span data-stu-id="5218e-134">In **Cloud Homed Users**, type the expected number of online concurrent users who will be homed in this central site.</span></span>

10. <span data-ttu-id="5218e-135">必要に応じて、オンライン コラボレーション、ユーザー、音声、追加展開オプション、またはサーバー アプリケーションの選択を変更します。</span><span class="sxs-lookup"><span data-stu-id="5218e-135">Modify the selections for Online Collaboration, Users, Voice, Additional Deployment Options, or Server Applications, as needed.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="5218e-136">デザインのこの時点では、展開のオプションのみを選択またはクリアできます。</span><span class="sxs-lookup"><span data-stu-id="5218e-136">At this point in the design, you can only select or clear options for your deployment.</span></span> <span data-ttu-id="5218e-137">ただし、計画ツールの後のフェーズでその他のオプションを構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="5218e-137">However, you can configure more options in a later phase of the Planning Tool.</span></span> <span data-ttu-id="5218e-138">利用できないオプションもあり、オフにすることはできません。</span><span class="sxs-lookup"><span data-stu-id="5218e-138">There are also options that are unavailable and cannot be cleared.</span></span> <span data-ttu-id="5218e-139">また、別のオプションをオフにするには、1つのオプションをオフにする必要がある場合もあります。</span><span class="sxs-lookup"><span data-stu-id="5218e-139">In addition, you may have to clear one option in order to clear another.</span></span> <span data-ttu-id="5218e-140">たとえば、[ボイス] の [<STRONG>エンタープライズボイス</STRONG>] オプションをオフにすると、[サーバーアプリケーション (すべての機能はエンタープライズ voip の機能)] の下の [<STRONG>返信] グループ</STRONG>、<STRONG>お知らせ</STRONG>、および [<STRONG>コールパーク</STRONG>] のオプションもクリアされます。</span><span class="sxs-lookup"><span data-stu-id="5218e-140">For example, if you clear the <STRONG>Enterprise Voice</STRONG> option under Voice, then the <STRONG>Response Group</STRONG>, <STRONG>Announcement</STRONG>, and <STRONG>Call Park</STRONG> options under Server Applications (all of which are features of Enterprise Voice) are also cleared.</span></span>

    
    </div>

11. <span data-ttu-id="5218e-141">サイト名とユーザー数を定義したら、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5218e-141">After defining a site name and number of users, click **Next**.</span></span>

12. <span data-ttu-id="5218e-142">SIP ドメイン、会議の設定、音声の設定とインフラストラクチャ、Exchange UM、外部ユーザーアクセス、常設チャットの設定、クライアント設定、collocation オプション、ブランチサイトについての情報を、次のページで確認できます。</span><span class="sxs-lookup"><span data-stu-id="5218e-142">The following pages ask for information about SIP domains, conference settings, voice settings and infrastructure, Exchange UM, external user access, Persistent Chat settings, client settings, collocation options, and branch sites.</span></span> <span data-ttu-id="5218e-143">これらの質問に適切に回答します。</span><span class="sxs-lookup"><span data-stu-id="5218e-143">Answer these questions as appropriate.</span></span>

13. <span data-ttu-id="5218e-144">最後の質問では、別のセントラルサイトを作成するかどうかをたずねられます。</span><span class="sxs-lookup"><span data-stu-id="5218e-144">The final question asks if you want to create another central site.</span></span> <span data-ttu-id="5218e-145">[**はい**] を選択すると、計画ツールは [セントラルサイト] ページに戻ります。</span><span class="sxs-lookup"><span data-stu-id="5218e-145">If you select **Yes**, then the Planning Tool returns to the Central Sites page.</span></span> <span data-ttu-id="5218e-146">[**いいえ**] を選択した場合は、[**次へ**]、[**描画**] の順にクリックすると、基本的なグローバル トポロジ ビューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5218e-146">If you select **No**, click **Next**, and then click **Draw** to display the high-level Global Topology view.</span></span>

14. <span data-ttu-id="5218e-147">既存のトポロジを表示するには、[**表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5218e-147">To view an existing topology, click **Display**.</span></span>

15. <span data-ttu-id="5218e-148">前に保存したトポロジを表す .xml ファイルをクリックして、[**開く**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5218e-148">Click the .xml file that represents the previously saved topology, and then click **Open**.</span></span>

16. <span data-ttu-id="5218e-149">計画ツールによって、グローバルトポロジページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5218e-149">The Planning Tool displays the Global Topology page.</span></span> <span data-ttu-id="5218e-150">計画ツールで利用可能なツールを使用して、トポロジの編集、更新、または変更を開始できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="5218e-150">You can now begin editing, updating, or changing the topology by using the tools available in the Planning Tool.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5218e-151">関連項目</span><span class="sxs-lookup"><span data-stu-id="5218e-151">See Also</span></span>


[<span data-ttu-id="5218e-152">Lync Server 2013 での設計の編集</span><span class="sxs-lookup"><span data-stu-id="5218e-152">Editing the design in Lync Server 2013</span></span>](lync-server-2013-editing-the-design.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

