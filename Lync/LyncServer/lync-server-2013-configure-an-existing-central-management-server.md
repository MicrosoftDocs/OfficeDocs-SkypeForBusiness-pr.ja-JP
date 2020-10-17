---
title: 'Lync Server 2013: 既存の中央管理サーバーの構成'
description: 'Lync Server 2013: 既存の中央管理サーバーを構成します。'
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
ms.openlocfilehash: ef93281be2537ca5e4a5892a8617500ce54f3c45
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546713"
---
# <a name="configure-an-existing-central-management-server-in-lync-server-2013"></a><span data-ttu-id="1ede3-103">Lync Server 2013 で既存の中央管理サーバーを構成する</span><span class="sxs-lookup"><span data-stu-id="1ede3-103">Configure an existing Central Management Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1ede3-104">_**トピックの最終更新日:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="1ede3-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="1ede3-105">既存の Lync Server 2013 展開から中央管理サーバーを再利用する場合は、以下に示す手順を実行して、Lync Server コントロールパネルおよび Windows PowerShell が正しく機能していることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1ede3-105">If you reuse a Central Management Server from an existing Lync Server 2013 deployment, you must run the procedure described below to make sure that Lync Server Control Panel and Windows PowerShell function correctly.</span></span>

<div>

## <a name="to-configure-an-existing-central-management-server"></a><span data-ttu-id="1ede3-106">既存の中央管理サーバーを構成するには</span><span class="sxs-lookup"><span data-stu-id="1ede3-106">To configure an existing Central Management Server</span></span>

1.  <span data-ttu-id="1ede3-107">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="1ede3-107">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="1ede3-108">中央管理サーバーに格納されている役割ベースのアクセス制御 (RBAC) の役割を更新するには、 **更新-CsAdminRole** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="1ede3-108">Use the **Update-CsAdminRole** cmdlet to update the role-based access control (RBAC) roles stored in the Central Management Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1ede3-109">エラーがない限り、何も出力されません。</span><span class="sxs-lookup"><span data-stu-id="1ede3-109">No output is expected unless there is an error.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

