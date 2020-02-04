---
title: トポロジビルダーの結合ウィザードを使用してマージする
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Merge using Topology Builder Merge wizard
ms:assetid: c3f3c425-dab6-4dcd-bf0e-d7fde05f2ebf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205243(v=OCS.15)
ms:contentKeyID: 48185343
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 61981ae875fef9976377644a9b67f0a329581a90
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763641"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="merge-using-topology-builder-merge-wizard"></a><span data-ttu-id="6209e-102">トポロジビルダーの結合ウィザードを使用してマージする</span><span class="sxs-lookup"><span data-stu-id="6209e-102">Merge using Topology Builder Merge wizard</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6209e-103">_**最終更新日:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="6209e-103">_**Topic Last Modified:** 2012-10-02_</span></span>

1.  <span data-ttu-id="6209e-104">トポロジビルダーを使用して、既存の展開をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="6209e-104">Download the existing deployment using Topology Builder.</span></span>

2.  <span data-ttu-id="6209e-105">[**アクション**] メニューで、[ **Office Communications Server 2007 R2 の結合**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6209e-105">From the **Action** menu, select **Merge Office Communications Server 2007 R2**.</span></span>

3.  <span data-ttu-id="6209e-106">[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6209e-106">Click **Next**.</span></span>

4.  <span data-ttu-id="6209e-107">[ **Edge セットアップの指定**] で [**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6209e-107">In **Specify Edge Setup**, click **Add**.</span></span>
    
    <span data-ttu-id="6209e-108">![トポロジの結合ウィザード、[Edge セットアップ] ページを指定する](images/JJ205243.cdca609d-d4d5-47d9-9ff8-8b1daa4106e1(OCS.15).jpg "トポロジの結合ウィザード、[Edge セットアップ] ページを指定する")</span><span class="sxs-lookup"><span data-stu-id="6209e-108">![Merge Topology Wizard, Specify Edge Setup page](images/JJ205243.cdca609d-d4d5-47d9-9ff8-8b1daa4106e1(OCS.15).jpg "Merge Topology Wizard, Specify Edge Setup page")</span></span>  

5.  <span data-ttu-id="6209e-109">[ **Edge の種類の指定**] で、エッジサーバー構成の種類を入力し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6209e-109">In **Specify Edge Type**, enter the type of Edge Server configuration, and then click **Next**.</span></span> <span data-ttu-id="6209e-110">この例では、[**単一エッジサーバー** ] オプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="6209e-110">This example uses the **Single Edge Server** option.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="6209e-111">拡張された<STRONG>エッジ展開</STRONG>は、サポートされている構成ではありません。</span><span class="sxs-lookup"><span data-stu-id="6209e-111"><STRONG>Expanded Edge deployment</STRONG> is not a supported configuration.</span></span> <span data-ttu-id="6209e-112">展開された<STRONG>エッジサーバー</STRONG>は、最初に<STRONG>1 つのエッジサーバー</STRONG>または負荷分散された<STRONG>統合エッジ</STRONG>サーバーに変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6209e-112">An <STRONG>Expanded Edge Server</STRONG> must first be converted to a <STRONG>Single Edge Server</STRONG> or a <STRONG>Load-balanced consolidated Edge</STRONG> Server.</span></span>

    
    </div>

6.  <span data-ttu-id="6209e-113">[**内部エッジ設定の指定**] で、必要に応じて、エッジプールの内部 FQDN とポートに関連する情報を入力し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6209e-113">In **Specify Internal Edge Settings** , enter the relevant information for your Edge pool’s internal FQDN and ports as needed, and then click **Next**.</span></span>
    
    <span data-ttu-id="6209e-114">![内部の端の設定ダイアログを指定する](images/JJ205243.dd664761-839c-4ac8-bd1a-5525589dfbb0(OCS.15).jpg "内部の端の設定ダイアログを指定する")</span><span class="sxs-lookup"><span data-stu-id="6209e-114">![Specify Internal Edge Settings dialog](images/JJ205243.dd664761-839c-4ac8-bd1a-5525589dfbb0(OCS.15).jpg "Specify Internal Edge Settings dialog")</span></span>  

7.  <span data-ttu-id="6209e-115">[**外部エッジの指定**] で、エッジサーバーの web 会議の FQDN 情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="6209e-115">In **Specify External Edge**, enter the web conferencing FQDN information for your Edge Server.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="6209e-116">[<STRONG>次へ</STRONG>] をクリックする前に、この手順の次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="6209e-116">Before you click <STRONG>Next</STRONG>, do the next step in this procedure.</span></span> <span data-ttu-id="6209e-117">この手順を見逃さないようにすることは非常に重要です。</span><span class="sxs-lookup"><span data-stu-id="6209e-117">It is very important that you do not miss this step.</span></span>

    
    </div>

8.  <span data-ttu-id="6209e-118">フェデレーション用の従来の Office Communications Server 2007 R2 Edge サーバーの使用を計画している場合は、[**このエッジプールをフェデレーションとパブリック IM 接続に使用**する] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="6209e-118">Check the **This Edge pool is used for federation and public IM connectivity** check box if you plan to use the legacy Office Communications Server 2007 R2 Edge Server for federation.</span></span> <span data-ttu-id="6209e-119">複数のエッジサーバーが展開されている場合は、そのうちの1つのみがフェデレーション対象として有効になります。</span><span class="sxs-lookup"><span data-stu-id="6209e-119">If you have multiple Edge Servers deployed, only one of them will be enabled for federation.</span></span> <span data-ttu-id="6209e-120">このチェックボックスをオフにして、後でフェデレーションを有効にする場合は、トポロジビルダーの結合ウィザードを実行して、もう一度トポロジを公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6209e-120">If you do not check this box and you decide later that you want to enable federation, you must run the Topology Builder Merge wizard and publish your topology again.</span></span>
    
    <span data-ttu-id="6209e-121">![[エッジサーバー] ダイアログ、[外部エッジの指定] ページ](images/JJ205243.32e97ce5-92f0-477e-8125-5d2ece237b13(OCS.15).jpg "[エッジサーバー] ダイアログ、[外部エッジの指定] ページ")</span><span class="sxs-lookup"><span data-stu-id="6209e-121">![Edge Server dialog, Specify External Edge page](images/JJ205243.32e97ce5-92f0-477e-8125-5d2ece237b13(OCS.15).jpg "Edge Server dialog, Specify External Edge page")</span></span>  

9.  <span data-ttu-id="6209e-122">[**次ホップの指定**] で、環境内の次のホップ位置の完全修飾ドメイン名 (FQDN) を入力します。</span><span class="sxs-lookup"><span data-stu-id="6209e-122">In **Specify Next Hop**, enter the fully qualified domain name (FQDN) of the next hop location in your environment.</span></span> <span data-ttu-id="6209e-123">[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6209e-123">Click **Finish**.</span></span>
    
    <span data-ttu-id="6209e-124">![[エッジサーバー] ダイアログボックス、[次ホップの指定] ページ](images/JJ205243.e734ee0d-f91c-4f3f-8ae6-248ecabcf678(OCS.15).jpg "[エッジサーバー] ダイアログボックス、[次ホップの指定] ページ")</span><span class="sxs-lookup"><span data-stu-id="6209e-124">![Edge Server dialog, Specify Next Hop page](images/JJ205243.e734ee0d-f91c-4f3f-8ae6-248ecabcf678(OCS.15).jpg "Edge Server dialog, Specify Next Hop page")</span></span>  

10. <span data-ttu-id="6209e-125">Office Communications Server 2007 R2 Edge サーバーがすべて追加されている場合は、[ **Edge セットアップの指定**] で [**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6209e-125">In **Specify Edge Setup**, if all your Office Communications Server 2007 R2 Edge Servers have been added, click **Next**.</span></span> <span data-ttu-id="6209e-126">追加する Office Communications Server 2007 R2 Edge サーバーが他にもある場合は、手順4からこの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="6209e-126">If you have more Office Communications Server 2007 R2 Edge Servers to add, repeat this procedure starting at step 4.</span></span>

11. <span data-ttu-id="6209e-127">[**内部 sip ポートの指定**] で、既定の設定 (つまり、既定の sip ポートを変更していない場合) を選択します。</span><span class="sxs-lookup"><span data-stu-id="6209e-127">In **Specify Internal SIP port** , select the default setting (that is, if you did not modify the default SIP port).</span></span> <span data-ttu-id="6209e-128">既定のポート5061を使用していない場合は、必要に応じて変更して、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6209e-128">Change as appropriate if you are not using a default port of 5061, and then click **Next**.</span></span>

12. <span data-ttu-id="6209e-129">[**概要**] で、[**次へ**] をクリックしてトポロジのマージを開始します。</span><span class="sxs-lookup"><span data-stu-id="6209e-129">In **Summary**, click **Next** to begin merging the topologies.</span></span>

13. <span data-ttu-id="6209e-130">ウィザードのページで、トポロジの結合が正常に完了したことを確認します。</span><span class="sxs-lookup"><span data-stu-id="6209e-130">The wizard page verifies that the merging of the topologies was successful.</span></span>

14. <span data-ttu-id="6209e-131">[**状態**] 列で、値が**成功**していることを確認し、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6209e-131">In the **Status** column, verify that the value is **Success**, and then click **Finish**.</span></span>

15. <span data-ttu-id="6209e-132">[Topology Builder] の左側のウィンドウに、 **BackCompatSite**が表示されます。これは、Office Communications Server 2007 R2 環境が Lync Server 2013 に統合されていることを示します。</span><span class="sxs-lookup"><span data-stu-id="6209e-132">In the left pane of Topology Builder, you should now see the **BackCompatSite**, which indicates that your Office Communications Server 2007 R2 environment has been merged with Lync Server 2013.</span></span>
    
    <span data-ttu-id="6209e-133">![結合されたトポロジを示すトポロジビルダー](images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "結合されたトポロジを示すトポロジビルダー")</span><span class="sxs-lookup"><span data-stu-id="6209e-133">![Topology Builder showing a merged topology](images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "Topology Builder showing a merged topology")</span></span>  

16. <span data-ttu-id="6209e-134">[**操作**] メニューの [**トポロジの公開**] をクリックし、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6209e-134">From the **Action** menu, click **Publish Topology**, and then click **Next**.</span></span>

17. <span data-ttu-id="6209e-135">**発行ウィザード**が完了したら、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6209e-135">When the **Publishing wizard** completes, click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6209e-136">従来のポリシー設定が Lync Server 2013 にインポートされるようにするには、次のトピック「<A href="import-policies-and-settings.md">ポリシーと設定のインポート</A>」を完了しておくことが重要です。</span><span class="sxs-lookup"><span data-stu-id="6209e-136">It’s important that you complete the next topic, <A href="import-policies-and-settings.md">Import policies and settings</A>, to ensure that the legacy policy settings are imported into Lync Server 2013.</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

