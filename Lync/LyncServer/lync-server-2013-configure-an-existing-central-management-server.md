---
title: 'Lync Server 2013: 既存の中央管理サーバーの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure an existing Central Management Server
ms:assetid: d715b24a-1256-4a7c-a5ef-1cee41d6b733
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205315(v=OCS.15)
ms:contentKeyID: 48185584
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eec9193d8c40a26179c5dfe1f142740abdda8bc4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840433"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-an-existing-central-management-server-in-lync-server-2013"></a><span data-ttu-id="73756-102">Lync Server 2013 での既存の中央管理サーバーの構成</span><span class="sxs-lookup"><span data-stu-id="73756-102">Configure an existing Central Management Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="73756-103">_**最終更新日:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="73756-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="73756-104">既存の Lync Server 2013 の展開から中央管理サーバーを再利用する場合は、次に説明する手順を実行して、Lync Server コントロールパネルと Windows PowerShell が正しく機能することを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="73756-104">If you reuse a Central Management Server from an existing Lync Server 2013 deployment, you must run the procedure described below to make sure that Lync Server Control Panel and Windows PowerShell function correctly.</span></span>

<div>

## <a name="to-configure-an-existing-central-management-server"></a><span data-ttu-id="73756-105">既存のサーバーの全体管理サーバーを構成するには</span><span class="sxs-lookup"><span data-stu-id="73756-105">To configure an existing Central Management Server</span></span>

1.  <span data-ttu-id="73756-106">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="73756-106">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="73756-107">[**更新プログラム**]、[管理者] の役割コマンドレットを使用して、サーバーの全体管理サーバーに保存されている役割ベースのアクセス制御 (RBAC) ロールを更新します。</span><span class="sxs-lookup"><span data-stu-id="73756-107">Use the **Update-CsAdminRole** cmdlet to update the role-based access control (RBAC) roles stored in the Central Management Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="73756-108">エラーがない限り、出力は予期されません。</span><span class="sxs-lookup"><span data-stu-id="73756-108">No output is expected unless there is an error.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

