---
title: 監視サーバーの関連付けの削除
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Remove the Monitoring server association
ms:assetid: c45b22ae-fc06-484a-a05b-735bd1bb7448
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721877(v=OCS.15)
ms:contentKeyID: 49733810
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a5703153bb1034f1318fbe14ca3583ad5744ffdb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847954"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-the-monitoring-server-association"></a><span data-ttu-id="cceca-102">監視サーバーの関連付けの削除</span><span class="sxs-lookup"><span data-stu-id="cceca-102">Remove the Monitoring server association</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cceca-103">_**最終更新日:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="cceca-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="cceca-104">監視サーバーを削除するには、関連するフロントエンドプール、フロントエンドサーバー、Survivable Branch Appliance、および Survivable Branch Server の依存関係を変更またはクリアする必要があります。</span><span class="sxs-lookup"><span data-stu-id="cceca-104">To remove the Monitoring Server, you need to change or clear the dependency on the associated Front End pool, Front End Server, Survivable Branch Appliance and Survivable Branch Server.</span></span> <span data-ttu-id="cceca-105">フロントエンドプール、フロントエンドサーバー、Survivable Branch Appliance、Survivable Branch Server のプロパティを編集して、依存関係を削除します。</span><span class="sxs-lookup"><span data-stu-id="cceca-105">You edit the properties of the Front End pool, Front End Server, Survivable Branch Appliance and Survivable Branch Server to remove the dependency.</span></span> <span data-ttu-id="cceca-106">[トポロジビルダー] で、依存関係を消去してサーバーを削除すると、関連付けられているデータベースストアオブジェクトもトポロジビルダーで削除されることが通知されます。</span><span class="sxs-lookup"><span data-stu-id="cceca-106">After you clear the dependency and delete the server in Topology Builder, you are notified that the associated database store object in Topology Builder will also be deleted.</span></span>

<div>

## <a name="to-remove-the-monitoring-server-association"></a><span data-ttu-id="cceca-107">監視サーバーの関連付けを削除するには</span><span class="sxs-lookup"><span data-stu-id="cceca-107">To remove the Monitoring Server association</span></span>

1.  <span data-ttu-id="cceca-108">Lync Server 2013 フロントエンドサーバーを開き、[トポロジビルダー] を開きます。</span><span class="sxs-lookup"><span data-stu-id="cceca-108">Open the Lync Server 2013 Front End Server, open Topology Builder.</span></span>

2.  <span data-ttu-id="cceca-109">Lync Server 2010 ノードに移動します。</span><span class="sxs-lookup"><span data-stu-id="cceca-109">Navigate to the Lync Server 2010 node.</span></span>

3.  <span data-ttu-id="cceca-110">[トポロジビルダー] で、監視サーバーが定義されている場所に基づいて、 **Enterprise Edition のフロントエンドプール**、**標準エディションのフロントエンドサーバー**、または**ブランチサイト**を展開します。</span><span class="sxs-lookup"><span data-stu-id="cceca-110">In Topology Builder, expand **Enterprise Edition Front End pools**, **Standard Edition Front End Servers**, or **Branch sites**, based on where the Monitoring Server is defined.</span></span>

4.  <span data-ttu-id="cceca-111">Survivable Branch Server が関連付けられている場合は、[**ブランチサイト**] を展開し、[ブランチサイト名] を展開して、[ **Survivable branch アプライアンス**] を展開します。</span><span class="sxs-lookup"><span data-stu-id="cceca-111">If you have Survivable Branch Server associated, expand **Branch sites**, expand the branch site name, and then expand **Survivable Branch Appliances**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cceca-112">ユーザーインターフェイス内の<STRONG>Survivable Branch アプライアンス</STRONG>は、Survivable branch Server と Survivable branch Appliance の両方に適用されます。</span><span class="sxs-lookup"><span data-stu-id="cceca-112"><STRONG>Survivable Branch Appliances</STRONG> in the user interface applies to both Survivable Branch Server and Survivable Branch Appliance.</span></span>

    
    </div>

5.  <span data-ttu-id="cceca-113">監視サーバーと関連付けられているプール、サーバー、またはデバイスを右クリックし、[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cceca-113">Right-click the pool, server, or device that is associated with the Monitoring Server, and then click **Edit Properties**.</span></span>

6.  <span data-ttu-id="cceca-114">[**プロパティの編集**] の [**全般**] で、[**関連付け**] の下の [**監視サーバーの関連付け**] チェックボックスをオフにして、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cceca-114">In **Edit Properties**, under **General**, under **Associations**, clear the **Associate Monitoring Server** check box, and then click **OK**.</span></span>

7.  <span data-ttu-id="cceca-115">監視サーバーに関連付けられているその他のプール、サーバー、またはデバイスについて、前の手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="cceca-115">Repeat the previous step for any other pool, server or device associated with the Monitoring Server.</span></span>

8.  <span data-ttu-id="cceca-116">監視サーバーを右クリックし、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cceca-116">Right-click the Monitoring Server, and then click **Delete**.</span></span>

9.  <span data-ttu-id="cceca-117">[**依存**しているストアの削除] で、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cceca-117">On **Delete Dependent Stores**, click **OK**.</span></span>

10. <span data-ttu-id="cceca-118">トポロジを公開し、レプリケーションの状態を確認し、必要に応じて Lync Server 展開ウィザードを実行します。</span><span class="sxs-lookup"><span data-stu-id="cceca-118">Publish the topology, check replication status, and run the Lync Server Deployment Wizard as needed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

