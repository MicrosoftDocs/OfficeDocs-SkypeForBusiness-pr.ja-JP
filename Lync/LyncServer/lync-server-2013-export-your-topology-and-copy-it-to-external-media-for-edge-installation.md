---
title: エッジ インストール用のトポロジをエクスポートして外部メディアにコピーする
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
ms.openlocfilehash: 8eb8f20e7af8cbfd772226917b027a33a688a4a5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756211"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="export-your-lync-server-2013-topology-and-copy-it-to-external-media-for-edge-installation"></a><span data-ttu-id="c3b63-102">エッジ インストール用の Lync Server 2013 のトポロジをエクスポートして外部メディアにコピーする</span><span class="sxs-lookup"><span data-stu-id="c3b63-102">Export your Lync Server 2013 topology and copy it to external media for edge installation</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c3b63-103">_**最終更新日:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="c3b63-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="c3b63-104">トポロジを公開した後、Lync Server 展開ウィザードでは、サーバー上で展開プロセスを開始するために、中央管理ストアのデータにアクセスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3b63-104">After you publish your topology, the Lync Server Deployment Wizard needs access to the Central Management store data in order to start the deployment process on the server.</span></span> <span data-ttu-id="c3b63-105">内部ネットワークでは、データはサーバーから直接利用できますが、内部ドメインにないエッジサーバーはデータにアクセスすることはできません。</span><span class="sxs-lookup"><span data-stu-id="c3b63-105">In the internal network, the data is available directly from the servers, but Edge Servers that are not in the internal domain cannot access the data.</span></span> <span data-ttu-id="c3b63-106">エッジサーバーの展開用にトポロジ構成データを利用できるようにするには、Lync Server の Dep を実行する前に、トポロジデータをファイルにエクスポートして、外部メディア (USB ドライブや、エッジサーバーから入手できるネットワーク共有など) にコピーする必要があります。エッジサーバー上の loyment ウィザード。</span><span class="sxs-lookup"><span data-stu-id="c3b63-106">To make the topology configuration data available for an Edge Server deployment, you must export the topology data to a file and copy it to external media (for example, a USB drive or a network share that is available from the Edge Server) before you run the Lync Server Deployment Wizard on the Edge Server.</span></span> <span data-ttu-id="c3b63-107">展開するエッジサーバーでトポロジ構成データを利用できるようにするには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="c3b63-107">Use the following procedure to make your topology configuration data available on the Edge Server that you are deploying.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="c3b63-108">エッジサーバーに Lync Server 2013 をインストールした後は、内部ネットワークの管理ツールを使用してエッジサーバーを管理します。これにより、展開のエッジサーバーに構成が自動的にレプリケートされます。</span><span class="sxs-lookup"><span data-stu-id="c3b63-108">After you install Lync Server 2013 on an Edge Server, you manage the Edge Server using the administrative tools in the internal network, which automatically replicate configuration to any Edge Servers in your deployment.</span></span> <span data-ttu-id="c3b63-109">唯一の例外として、証明書の割り当てとインストール、サービスの停止と開始はどちらもエッジサーバーで実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3b63-109">The only exception is assigning and installing certificates and stopping and starting services, both of which must be done on the Edge Server.</span></span>



</div>

<div>

## <a name="to-make-your-topology-data-available-on-an-edge-server-by-using-lync-server-management-shell"></a><span data-ttu-id="c3b63-110">Lync Server 管理シェルを使用して、トポロジデータをエッジサーバーで利用できるようにするには</span><span class="sxs-lookup"><span data-stu-id="c3b63-110">To make your topology data available on an Edge Server by using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="c3b63-111">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="c3b63-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="c3b63-112">Lync Server 管理シェルで、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="c3b63-112">In the Lync Server Management Shell, run the following cmdlet:</span></span>
    
        Export-CsConfiguration -FileName <ConfigurationFilePath.zip>

3.  <span data-ttu-id="c3b63-113">エクスポートしたファイルを外部メディア (たとえば、展開中にエッジサーバーから利用可能な USB ドライブやネットワーク共有など) にコピーします。</span><span class="sxs-lookup"><span data-stu-id="c3b63-113">Copy the exported file to external media (for example, a USB drive or a network share that is available from the Edge Server during deployment).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

