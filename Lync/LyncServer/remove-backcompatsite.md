---
title: BackCompatSite を削除する
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove BackCompatSite
ms:assetid: 039650e3-541b-45c2-a682-c4fa08423118
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204637(v=OCS.15)
ms:contentKeyID: 48183265
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ccfcd48c575e300b12fe08611d6f898749041478
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727197"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-backcompatsite"></a><span data-ttu-id="ad3f2-102">BackCompatSite を削除する</span><span class="sxs-lookup"><span data-stu-id="ad3f2-102">Remove BackCompatSite</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ad3f2-103">_**最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="ad3f2-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="ad3f2-104">すべてのプールが非アクティブ化され、すべてのエッジサーバーがアンインストールされたら、トポロジビルダーの結合ウィザードを実行して、 **BackCompatSite**を削除します。</span><span class="sxs-lookup"><span data-stu-id="ad3f2-104">After all pools are deactivated and all Edge Servers have been uninstalled, run the Topology Builder Merge wizard to remove the **BackCompatSite**.</span></span>

<div>

## <a name="to-remove-backcompat-site-from-topology-builder"></a><span data-ttu-id="ad3f2-105">Topology Builder から BackCompat サイトを削除するには</span><span class="sxs-lookup"><span data-stu-id="ad3f2-105">To remove BackCompat site from Topology Builder</span></span>

1.  <span data-ttu-id="ad3f2-106">トポロジビルダーから既存の展開を開きます。</span><span class="sxs-lookup"><span data-stu-id="ad3f2-106">Open an existing deployment from Topology Builder.</span></span>

2.  <span data-ttu-id="ad3f2-107">[**操作**] メニューで、[ **2007 R2 トポロジのマージ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ad3f2-107">In the **Action** menu, click **Merge 2007 R2 Topology**.</span></span>

3.  <span data-ttu-id="ad3f2-108">[**次へ**] をクリックして続行します。</span><span class="sxs-lookup"><span data-stu-id="ad3f2-108">Click **Next** to continue.</span></span>

4.  <span data-ttu-id="ad3f2-109">[**レガシ edge の指定**] ページで、エッジサーバーの一覧が空であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ad3f2-109">On the **Specify Legacy Edge** page, ensure that list of Edge Servers is empty.</span></span> <span data-ttu-id="ad3f2-110">リストが空でない場合は、[**削除**] ボタンを使用して、すべてのレガシーエッジサーバーを削除してから、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ad3f2-110">If the list is not empty, use the **Remove** button to remove all the legacy Edge Servers, and then click **Next**.</span></span>
    
    <span data-ttu-id="ad3f2-111">![トポロジの結合ウィザード、[Edge セットアップ] ページを指定する](images/JJ204637.fb35a59a-711e-4259-b177-7311df1fed3c(OCS.15).jpg "トポロジの結合ウィザード、[Edge セットアップ] ページを指定する")</span><span class="sxs-lookup"><span data-stu-id="ad3f2-111">![Merge Topology Wizard, Specify Edge Setup page](images/JJ204637.fb35a59a-711e-4259-b177-7311df1fed3c(OCS.15).jpg "Merge Topology Wizard, Specify Edge Setup page")</span></span>  

5.  <span data-ttu-id="ad3f2-112">[**内部 SIP ポート設定の指定**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ad3f2-112">On the **Specify Internal SIP port setting** page, click **Next**.</span></span>

6.  <span data-ttu-id="ad3f2-113">[**概要**] ページで、[**次**へ] をクリックして、トポロジの結合を開始して、従来のサイトを削除します。</span><span class="sxs-lookup"><span data-stu-id="ad3f2-113">On the **Summary** page, click **Next** to begin merging the topologies to remove the legacy site.</span></span>

7.  <span data-ttu-id="ad3f2-114">[**状態**] 列で、値が**成功**していることを確認し、[**完了**] をクリックしてウィザードを閉じます。</span><span class="sxs-lookup"><span data-stu-id="ad3f2-114">In the **Status** column, verify that the value is **Success** and then click **Finish** to close the wizard.</span></span>

8.  <span data-ttu-id="ad3f2-115">[Topology Builder] の左側のウィンドウで、[BackCompatSite] を展開して、サーバーが一覧に表示されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="ad3f2-115">In the left pane of Topology Builder, expand the BackCompatSite and ensure no servers are listed.</span></span>

9.  <span data-ttu-id="ad3f2-116">**BackCompatSite**を右クリックし、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ad3f2-116">Right-click the **BackCompatSite**, and then click **Delete**.</span></span>

10. <span data-ttu-id="ad3f2-117">[**トポロジビルダー**] で、トップノードの**Lync Server**を選択します。</span><span class="sxs-lookup"><span data-stu-id="ad3f2-117">In **Topology Builder**, select the top-most node **Lync Server**.</span></span>

11. <span data-ttu-id="ad3f2-118">[**アクション**] メニューで、[**発行トポロジ**] を選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ad3f2-118">From the **Action** menu, select **Publish Topology** and then click **Next**.</span></span>

12. <span data-ttu-id="ad3f2-119">**発行ウィザード**が完了したら、[**完了**] をクリックしてウィザードを閉じます。</span><span class="sxs-lookup"><span data-stu-id="ad3f2-119">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

