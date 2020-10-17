---
title: 'Lync Server 2013: 中央管理サーバーの選択'
description: 'Lync Server 2013: 中央管理サーバーを選択します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Select the Central Management Server
ms:assetid: 1ca6b7d0-125c-4727-aac4-2d683d23394d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204726(v=OCS.15)
ms:contentKeyID: 48183561
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a754a9b46b1cd8213a6987c4fc200edaa01fb6d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555163"
---
# <a name="select-the-central-management-server-in-lync-server-2013"></a><span data-ttu-id="cd678-103">Lync Server 2013 で中央管理サーバーを選択します。</span><span class="sxs-lookup"><span data-stu-id="cd678-103">Select the Central Management Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cd678-104">_**トピックの最終更新日:** 2012-01-02_</span><span class="sxs-lookup"><span data-stu-id="cd678-104">_**Topic Last Modified:** 2012-01-02_</span></span>

<span data-ttu-id="cd678-105">トポロジを定義および構成する前に、中央管理サーバーをインストールする場所を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd678-105">Before you can define and configure your topology, you must first define the location to install the Central Management Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="cd678-106">トポロジビルダーでトポロジを公開するまで、これは有効になりません。</span><span class="sxs-lookup"><span data-stu-id="cd678-106">This will not take effect until you have published a topology in Topology Builder.</span></span> <span data-ttu-id="cd678-107">トポロジを作成して発行する前に中央管理サーバーを設定するには、 <STRONG>remove-csconfigurationstorelocation</STRONG>を実行します。</span><span class="sxs-lookup"><span data-stu-id="cd678-107">To set the Central Management Server before the topology is created and published, run <STRONG>Set-CSConfigurationStoreLocation</STRONG>.</span></span>



</div>

<div>

## <a name="to-select-the-central-management-server"></a><span data-ttu-id="cd678-108">中央管理サーバーを選択するには</span><span class="sxs-lookup"><span data-stu-id="cd678-108">To select the Central Management Server</span></span>

1.  <span data-ttu-id="cd678-109">トポロジ ビルダーを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server トポロジ ビルダー**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="cd678-109">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="cd678-110">[Lync Server 2013] ノードを右クリックし、[ **プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cd678-110">Right-click the Lync Server 2013 node, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="cd678-111">中央管理サーバーウィンドウで、中央管理サーバーをインストールするフロントエンドサーバーを選択し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cd678-111">In the Central Management Server pane, select the Front End Server to install the Central Management Server on and then click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

