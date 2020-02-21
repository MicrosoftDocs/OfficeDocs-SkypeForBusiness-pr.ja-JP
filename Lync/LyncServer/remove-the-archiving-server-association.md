---
title: アーカイブサーバーの関連付けを削除する
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove the Archiving server association
ms:assetid: dabac157-71ee-4afe-b0b6-4a083d165ffb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721903(v=OCS.15)
ms:contentKeyID: 49733837
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 93c53ef1e70b174681149593237db3f9d0268209
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42189490"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-the-archiving-server-association"></a><span data-ttu-id="74acb-102">アーカイブサーバーの関連付けを削除する</span><span class="sxs-lookup"><span data-stu-id="74acb-102">Remove the Archiving server association</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="74acb-103">_**トピックの最終更新日:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="74acb-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="74acb-104">アーカイブサーバーを削除するには、関連付けられているフロントエンドプール、フロントエンドサーバー、存続可能ブランチアプライアンス、および存続可能ブランチサーバーの依存関係を変更またはクリアする必要があります。</span><span class="sxs-lookup"><span data-stu-id="74acb-104">To remove an Archiving Server, you need to change or clear the dependency on the associated Front End pool, Front End Server, Survivable Branch Appliance and Survivable Branch Server.</span></span> <span data-ttu-id="74acb-105">依存関係を削除するには、フロントエンドプール、フロントエンドサーバー、存続可能 Branch Appliance、存続可能 Branch Server の各プロパティを編集します。</span><span class="sxs-lookup"><span data-stu-id="74acb-105">You edit the properties of the Front End pool, Front End Server, Survivable Branch Appliance and Survivable Branch Server to remove the dependency.</span></span> <span data-ttu-id="74acb-106">依存関係をクリアし、トポロジビルダーでサーバーを削除すると、トポロジビルダー内の関連付けられたデータベースストアオブジェクトも削除されることが通知されます。</span><span class="sxs-lookup"><span data-stu-id="74acb-106">After you clear the dependency and you delete the server in Topology Builder, you are notified that the associated database store object in Topology Builder will also be deleted.</span></span>

<div>

## <a name="to-remove-the-archiving-server-association"></a><span data-ttu-id="74acb-107">アーカイブサーバーの関連付けを削除するには</span><span class="sxs-lookup"><span data-stu-id="74acb-107">To remove the Archiving Server association</span></span>

1.  <span data-ttu-id="74acb-108">Lync Server 2013 フロントエンドサーバーを開き、トポロジビルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="74acb-108">Open the Lync Server 2013 Front End Server, open Topology Builder.</span></span>

2.  <span data-ttu-id="74acb-109">[Lync Server 2010 ノードに移動します。</span><span class="sxs-lookup"><span data-stu-id="74acb-109">Navigate to the Lync Server 2010 node.</span></span>

3.  <span data-ttu-id="74acb-110">トポロジビルダーで、アーカイブサーバーが定義されている場所に基づいて、 **Enterprise Edition フロントエンドプール**、 **Standard Edition フロントエンドサーバー**、または**ブランチサイト**を展開します。</span><span class="sxs-lookup"><span data-stu-id="74acb-110">In Topology Builder, expand **Enterprise Edition Front End pools**, **Standard Edition Front End Servers**, or **Branch sites**, based on where the Archiving Server is defined.</span></span>

4.  <span data-ttu-id="74acb-111">存続可能 Branch Server が関連付けられている場合は、[**ブランチサイト**] を展開し、[ブランチサイト] を展開して、[**存続可能ブランチアプライアンス**] を展開します。</span><span class="sxs-lookup"><span data-stu-id="74acb-111">If you have Survivable Branch Server associated, expand **Branch sites**, expand the branch site name, and then expand **Survivable Branch Appliances**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="74acb-112">ユーザーインターフェイスの<STRONG>存続可能 Branch アプライアンス</STRONG>は、存続可能 branch Server と存続可能 branch Appliance の両方に適用されます。</span><span class="sxs-lookup"><span data-stu-id="74acb-112"><STRONG>Survivable Branch Appliances</STRONG> in the user interface applies to both Survivable Branch Server and Survivable Branch Appliance.</span></span>

    
    </div>

5.  <span data-ttu-id="74acb-113">アーカイブサーバーに関連付けられているプール、サーバー、またはデバイスを右クリックし、[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="74acb-113">Right-click the pool, server, or device that is associated with the Archiving Server, and then click **Edit Properties**.</span></span>

6.  <span data-ttu-id="74acb-114">[**プロパティの編集**] の [**全般**] で、[**関連付け**] の [**アーカイブサーバーの関連付け**] チェックボックスをオフにして、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="74acb-114">In **Edit Properties**, under **General**, under **Associations**, clear the **Associate Archiving Server** check box, and then click **OK**.</span></span>

7.  <span data-ttu-id="74acb-115">削除するアーカイブサーバーに関連付けられているその他のプール、サーバー、またはデバイスに対して、前の手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="74acb-115">Repeat the previous step for any other pool, server or device associated with the Archiving Server that you want to remove.</span></span>

8.  <span data-ttu-id="74acb-116">アーカイブサーバーを右クリックし、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="74acb-116">Right-click the Archiving Server, and then click **Delete**.</span></span>

9.  <span data-ttu-id="74acb-117">[**依存ストアの削除**] で、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="74acb-117">On **Delete Dependent Stores**, click **OK**.</span></span>

10. <span data-ttu-id="74acb-118">トポロジを公開し、レプリケーションの状態を確認してから、必要に応じて Lync Server 展開ウィザードを実行します。</span><span class="sxs-lookup"><span data-stu-id="74acb-118">Publish the topology, check replication status, and then run the Lync Server Deployment Wizard as needed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

