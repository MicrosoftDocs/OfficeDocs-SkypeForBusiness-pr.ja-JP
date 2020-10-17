---
title: エッジインストール用のトポロジをエクスポートして外部メディアにコピーする
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Export your topology and copy it to external media for edge installation
ms:assetid: def9f416-c519-4a72-b242-7d3057d9c1fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398983(v=OCS.15)
ms:contentKeyID: 48185615
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5dd461e6a8ce184e5e418feddede258af68d2c25
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528374"
---
# <a name="export-your-lync-server-2013-topology-and-copy-it-to-external-media-for-edge-installation"></a><span data-ttu-id="f1031-102">エッジインストールのために Lync Server 2013 トポロジをエクスポートして外部メディアにコピーする</span><span class="sxs-lookup"><span data-stu-id="f1031-102">Export your Lync Server 2013 topology and copy it to external media for edge installation</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f1031-103">_**トピックの最終更新日:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="f1031-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="f1031-104">トポロジを公開した後、Lync Server 展開ウィザードは、サーバー上で展開プロセスを開始するために、中央管理ストアのデータにアクセスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f1031-104">After you publish your topology, the Lync Server Deployment Wizard needs access to the Central Management store data in order to start the deployment process on the server.</span></span> <span data-ttu-id="f1031-105">内部ネットワークでは、データはサーバーから直接使用できますが、内部ドメインにないエッジサーバーはデータにアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="f1031-105">In the internal network, the data is available directly from the servers, but Edge Servers that are not in the internal domain cannot access the data.</span></span> <span data-ttu-id="f1031-106">トポロジ構成データをエッジサーバーの展開に使用できるようにするには、エッジサーバーで Lync Server 展開ウィザードを実行する前に、トポロジデータをファイルにエクスポートして外部メディア (たとえば、エッジサーバーから使用できる USB ドライブやネットワーク共有) にコピーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f1031-106">To make the topology configuration data available for an Edge Server deployment, you must export the topology data to a file and copy it to external media (for example, a USB drive or a network share that is available from the Edge Server) before you run the Lync Server Deployment Wizard on the Edge Server.</span></span> <span data-ttu-id="f1031-107">展開するエッジサーバーでトポロジ構成データを使用できるようにするには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="f1031-107">Use the following procedure to make your topology configuration data available on the Edge Server that you are deploying.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="f1031-108">エッジサーバーに Lync Server 2013 をインストールした後、内部ネットワークの管理ツールを使用してエッジサーバーを管理します。これにより、展開内の任意のエッジサーバーに構成が自動的にレプリケートされます。</span><span class="sxs-lookup"><span data-stu-id="f1031-108">After you install Lync Server 2013 on an Edge Server, you manage the Edge Server using the administrative tools in the internal network, which automatically replicate configuration to any Edge Servers in your deployment.</span></span> <span data-ttu-id="f1031-109">唯一の例外は、証明書を割り当ててインストールし、サービスを停止および開始することです。どちらもエッジサーバーで実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f1031-109">The only exception is assigning and installing certificates and stopping and starting services, both of which must be done on the Edge Server.</span></span>



</div>

<div>

## <a name="to-make-your-topology-data-available-on-an-edge-server-by-using-lync-server-management-shell"></a><span data-ttu-id="f1031-110">Lync Server 管理シェルを使用して、エッジサーバーでトポロジデータを使用できるようにするには</span><span class="sxs-lookup"><span data-stu-id="f1031-110">To make your topology data available on an Edge Server by using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="f1031-111">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="f1031-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="f1031-112">Lync Server 管理シェルで、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="f1031-112">In the Lync Server Management Shell, run the following cmdlet:</span></span>
    
        Export-CsConfiguration -FileName <ConfigurationFilePath.zip>

3.  <span data-ttu-id="f1031-113">エクスポートされたファイルを外部メディア (たとえば、展開中にエッジサーバーから使用できる USB ドライブやネットワーク共有) にコピーします。</span><span class="sxs-lookup"><span data-stu-id="f1031-113">Copy the exported file to external media (for example, a USB drive or a network share that is available from the Edge Server during deployment).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

