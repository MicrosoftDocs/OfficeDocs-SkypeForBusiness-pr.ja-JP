---
title: アーカイブ サーバーの関連付けの削除
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
ms.openlocfilehash: 04bf1a5a3c68ab1123431543e08618c4eacb7559
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727117"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-the-archiving-server-association"></a><span data-ttu-id="38ef7-102">アーカイブ サーバーの関連付けの削除</span><span class="sxs-lookup"><span data-stu-id="38ef7-102">Remove the Archiving server association</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="38ef7-103">_**最終更新日:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="38ef7-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="38ef7-104">アーカイブサーバーを削除するには、関連するフロントエンドプール、フロントエンドサーバー、Survivable Branch Appliance、および Survivable Branch Server の依存関係を変更またはクリアする必要があります。</span><span class="sxs-lookup"><span data-stu-id="38ef7-104">To remove an Archiving Server, you need to change or clear the dependency on the associated Front End pool, Front End Server, Survivable Branch Appliance and Survivable Branch Server.</span></span> <span data-ttu-id="38ef7-105">フロントエンドプール、フロントエンドサーバー、Survivable Branch Appliance、Survivable Branch Server のプロパティを編集して、依存関係を削除します。</span><span class="sxs-lookup"><span data-stu-id="38ef7-105">You edit the properties of the Front End pool, Front End Server, Survivable Branch Appliance and Survivable Branch Server to remove the dependency.</span></span> <span data-ttu-id="38ef7-106">依存関係を消去して、トポロジビルダーでサーバーを削除すると、トポロジビルダーの関連付けられたデータベースストアオブジェクトも削除されることが通知されます。</span><span class="sxs-lookup"><span data-stu-id="38ef7-106">After you clear the dependency and you delete the server in Topology Builder, you are notified that the associated database store object in Topology Builder will also be deleted.</span></span>

<div>

## <a name="to-remove-the-archiving-server-association"></a><span data-ttu-id="38ef7-107">アーカイブサーバーの関連付けを削除するには</span><span class="sxs-lookup"><span data-stu-id="38ef7-107">To remove the Archiving Server association</span></span>

1.  <span data-ttu-id="38ef7-108">Lync Server 2013 フロントエンドサーバーを開き、[トポロジビルダー] を開きます。</span><span class="sxs-lookup"><span data-stu-id="38ef7-108">Open the Lync Server 2013 Front End Server, open Topology Builder.</span></span>

2.  <span data-ttu-id="38ef7-109">Lync Server 2010 ノードに移動します。</span><span class="sxs-lookup"><span data-stu-id="38ef7-109">Navigate to the Lync Server 2010 node.</span></span>

3.  <span data-ttu-id="38ef7-110">[トポロジビルダー] で、アーカイブサーバーが定義されている場所に基づいて、 **Enterprise Edition のフロントエンドプール**、**標準エディションのフロントエンドサーバー**、または**ブランチサイト**を展開します。</span><span class="sxs-lookup"><span data-stu-id="38ef7-110">In Topology Builder, expand **Enterprise Edition Front End pools**, **Standard Edition Front End Servers**, or **Branch sites**, based on where the Archiving Server is defined.</span></span>

4.  <span data-ttu-id="38ef7-111">Survivable Branch Server が関連付けられている場合は、[**ブランチサイト**] を展開し、[ブランチサイト名] を展開して、[ **Survivable branch アプライアンス**] を展開します。</span><span class="sxs-lookup"><span data-stu-id="38ef7-111">If you have Survivable Branch Server associated, expand **Branch sites**, expand the branch site name, and then expand **Survivable Branch Appliances**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="38ef7-112">ユーザーインターフェイス内の<STRONG>Survivable Branch アプライアンス</STRONG>は、Survivable branch Server と Survivable branch Appliance の両方に適用されます。</span><span class="sxs-lookup"><span data-stu-id="38ef7-112"><STRONG>Survivable Branch Appliances</STRONG> in the user interface applies to both Survivable Branch Server and Survivable Branch Appliance.</span></span>

    
    </div>

5.  <span data-ttu-id="38ef7-113">アーカイブサーバーに関連付けられているプール、サーバー、またはデバイスを右クリックし、[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="38ef7-113">Right-click the pool, server, or device that is associated with the Archiving Server, and then click **Edit Properties**.</span></span>

6.  <span data-ttu-id="38ef7-114">[**プロパティの編集**] の [**全般**] で、[**関連付け**] の下の [**アーカイブサーバーの関連付け**] チェックボックスをオフにして、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="38ef7-114">In **Edit Properties**, under **General**, under **Associations**, clear the **Associate Archiving Server** check box, and then click **OK**.</span></span>

7.  <span data-ttu-id="38ef7-115">削除するアーカイブサーバーに関連付けられているその他のプール、サーバー、またはデバイスについて、前の手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="38ef7-115">Repeat the previous step for any other pool, server or device associated with the Archiving Server that you want to remove.</span></span>

8.  <span data-ttu-id="38ef7-116">アーカイブサーバーを右クリックし、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="38ef7-116">Right-click the Archiving Server, and then click **Delete**.</span></span>

9.  <span data-ttu-id="38ef7-117">[**依存**しているストアの削除] で、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="38ef7-117">On **Delete Dependent Stores**, click **OK**.</span></span>

10. <span data-ttu-id="38ef7-118">トポロジを公開し、レプリケーションの状態を確認してから、必要に応じて Lync Server 展開ウィザードを実行します。</span><span class="sxs-lookup"><span data-stu-id="38ef7-118">Publish the topology, check replication status, and then run the Lync Server Deployment Wizard as needed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

