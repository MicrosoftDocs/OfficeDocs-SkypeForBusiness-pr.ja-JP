---
title: 'Lync Server 2013: 既存の中央管理サーバーの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure an existing Central Management Server
ms:assetid: d715b24a-1256-4a7c-a5ef-1cee41d6b733
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205315(v=OCS.15)
ms:contentKeyID: 48185584
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 09c4102008eca37d79d2862a3ede8b1498899511
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205153"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-an-existing-central-management-server-in-lync-server-2013"></a><span data-ttu-id="82ec1-102">Lync Server 2013 で既存の中央管理サーバーを構成する</span><span class="sxs-lookup"><span data-stu-id="82ec1-102">Configure an existing Central Management Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="82ec1-103">_**トピックの最終更新日:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="82ec1-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="82ec1-104">既存の Lync Server 2013 展開から中央管理サーバーを再利用する場合は、以下に示す手順を実行して、Lync Server コントロールパネルおよび Windows PowerShell が正しく機能していることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="82ec1-104">If you reuse a Central Management Server from an existing Lync Server 2013 deployment, you must run the procedure described below to make sure that Lync Server Control Panel and Windows PowerShell function correctly.</span></span>

<div>

## <a name="to-configure-an-existing-central-management-server"></a><span data-ttu-id="82ec1-105">既存の中央管理サーバーを構成するには</span><span class="sxs-lookup"><span data-stu-id="82ec1-105">To configure an existing Central Management Server</span></span>

1.  <span data-ttu-id="82ec1-106">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="82ec1-106">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="82ec1-107">中央管理サーバーに格納されている役割ベースのアクセス制御 (RBAC) の役割を更新するには、**更新-CsAdminRole**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="82ec1-107">Use the **Update-CsAdminRole** cmdlet to update the role-based access control (RBAC) roles stored in the Central Management Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="82ec1-108">エラーがない限り、何も出力されません。</span><span class="sxs-lookup"><span data-stu-id="82ec1-108">No output is expected unless there is an error.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

