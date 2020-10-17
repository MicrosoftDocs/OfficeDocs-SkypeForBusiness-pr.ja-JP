---
title: BackCompatSite の削除
description: BackCompatSite を削除します。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove BackCompatSite
ms:assetid: 039650e3-541b-45c2-a682-c4fa08423118
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204637(v=OCS.15)
ms:contentKeyID: 48183265
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 809324320ec1869ac0c9d324b8fc270a3cf8f174
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570273"
---
# <a name="remove-backcompatsite"></a><span data-ttu-id="b3635-103">BackCompatSite の削除</span><span class="sxs-lookup"><span data-stu-id="b3635-103">Remove BackCompatSite</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b3635-104">_**トピックの最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="b3635-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="b3635-105">すべてのプールを非アクティブ化し、すべてのエッジ サーバーをアンインストールした後、トポロジ ビルダー結合ウィザードを実行して、[**BackCompatSite**] を削除します。</span><span class="sxs-lookup"><span data-stu-id="b3635-105">After all pools are deactivated and all Edge Servers have been uninstalled, run the Topology Builder Merge wizard to remove the **BackCompatSite**.</span></span>

<div>

## <a name="to-remove-backcompat-site-from-topology-builder"></a><span data-ttu-id="b3635-106">トポロジ ビルダーで BackCompat サイトを削除するには</span><span class="sxs-lookup"><span data-stu-id="b3635-106">To remove BackCompat site from Topology Builder</span></span>

1.  <span data-ttu-id="b3635-107">トポロジ ビルダーから既存の展開を開きます。</span><span class="sxs-lookup"><span data-stu-id="b3635-107">Open an existing deployment from Topology Builder.</span></span>

2.  <span data-ttu-id="b3635-108">[**操作**] メニューの [**Office Communications Server 2007 R2 トポロジのマージ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b3635-108">In the **Action** menu, click **Merge 2007 R2 Topology**.</span></span>

3.  <span data-ttu-id="b3635-109">[**次へ**] をクリックして続行します。</span><span class="sxs-lookup"><span data-stu-id="b3635-109">Click **Next** to continue.</span></span>

4.  <span data-ttu-id="b3635-p101">[**レガシ エッジの指定**] ページで、エッジ サーバーの一覧が空になっていることを確認します。一覧が空でない場合は、[**削除**] ボタンを使用してすべてのレガシ エッジ サーバーを削除し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b3635-p101">On the **Specify Legacy Edge** page, ensure that list of Edge Servers is empty. If the list is not empty, use the **Remove** button to remove all the legacy Edge Servers, and then click **Next**.</span></span>
    
    <span data-ttu-id="b3635-112">![トポロジのマージウィザード、[エッジセットアップの指定] ページ](images/JJ204637.fb35a59a-711e-4259-b177-7311df1fed3c(OCS.15).jpg "トポロジのマージウィザード、[エッジセットアップの指定] ページ")</span><span class="sxs-lookup"><span data-stu-id="b3635-112">![Merge Topology Wizard, Specify Edge Setup page](images/JJ204637.fb35a59a-711e-4259-b177-7311df1fed3c(OCS.15).jpg "Merge Topology Wizard, Specify Edge Setup page")</span></span>  

5.  <span data-ttu-id="b3635-113">[**内部 SIP ポートの指定**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b3635-113">On the **Specify Internal SIP port setting** page, click **Next**.</span></span>

6.  <span data-ttu-id="b3635-114">[ **概要** ] ページで、[ **次** へ] をクリックして、従来のサイトを削除するためのトポロジのマージを開始します。</span><span class="sxs-lookup"><span data-stu-id="b3635-114">On the **Summary** page, click **Next** to begin merging the topologies to remove the legacy site.</span></span>

7.  <span data-ttu-id="b3635-115">[**状態**] 列の値が "**成功**" になっていることを確認し、[**完了**] をクリックしてウィザードを閉じます。</span><span class="sxs-lookup"><span data-stu-id="b3635-115">In the **Status** column, verify that the value is **Success** and then click **Finish** to close the wizard.</span></span>

8.  <span data-ttu-id="b3635-116">トポロジ ビルダーの左側のウィンドウで [BackCompatSite] を展開し、サーバーが表示されないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="b3635-116">In the left pane of Topology Builder, expand the BackCompatSite and ensure no servers are listed.</span></span>

9.  <span data-ttu-id="b3635-117">[**BackCompatSite**] を右クリックし、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b3635-117">Right-click the **BackCompatSite**, and then click **Delete**.</span></span>

10. <span data-ttu-id="b3635-118">**トポロジ ビルダー**で、最上位ノードの [**Lync Server**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b3635-118">In **Topology Builder**, select the top-most node **Lync Server**.</span></span>

11. <span data-ttu-id="b3635-119">[**操作**] メニューの [**トポロジの公開**] を選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b3635-119">From the **Action** menu, select **Publish Topology** and then click **Next**.</span></span>

12. <span data-ttu-id="b3635-120">**公開ウィザード**の実行が完了したら、[**完了**] をクリックしてウィザードを閉じます。</span><span class="sxs-lookup"><span data-stu-id="b3635-120">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

