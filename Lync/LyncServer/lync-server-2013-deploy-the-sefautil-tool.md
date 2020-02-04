---
title: 'Lync Server 2013: SEFAUtil ツールの展開'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy the SEFAUtil tool
ms:assetid: fb556e50-88dd-4404-a3d5-be36f5ba41e6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945659(v=OCS.15)
ms:contentKeyID: 51541534
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dcd995a99514fa54a221e17f1ea556565cbebdcb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729617"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-the-sefautil-tool-in-lync-server-2013"></a><span data-ttu-id="5e1d3-102">Deploy the SEFAUtil tool in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5e1d3-102">Deploy the SEFAUtil tool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5e1d3-103">_**最終更新日:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="5e1d3-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="5e1d3-104">グループ通話のピックアップを展開して管理するには、SEFAUtil リソースキットツールを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5e1d3-104">To deploy and manage Group Call Pickup, you need to use the SEFAUtil resource kit tool.</span></span> <span data-ttu-id="5e1d3-105">このツールは、Lync Server 2013 リソースキットツールに含まれています。</span><span class="sxs-lookup"><span data-stu-id="5e1d3-105">The tool is part of the Lync Server 2013 resource kit tools.</span></span> <span data-ttu-id="5e1d3-106">SEFAUtil をインストールする前に、信頼できるアプリケーションプールをトポロジに設定し、信頼できるアプリケーションとして SEFAUtil を指定して、トポロジを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5e1d3-106">Before you can install SEFAUtil, you must have a trusted application pool in your topology, specify SEFAUtil as a trusted application, and enable the topology.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="5e1d3-107">Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK を、SEFAUtil ツールを実行する予定のすべてのコンピューターにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5e1d3-107">Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK must be installed on any computer where you plan to run the SEFAUtil tool.</span></span>



</div>

<span data-ttu-id="5e1d3-108">SEFAUtil は、展開の任意のフロントエンドプールで実行できます。</span><span class="sxs-lookup"><span data-stu-id="5e1d3-108">You can run the SEFAUtil in any Front End pool in your deployment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5e1d3-109">SEFAUtil の実行の詳細については、Technet の記事「SEFAutil を実行する方法」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e1d3-109">For more details about running SEFAUtil, see the Technet blog article, "How to get SEFAutil running?"</span></span> <span data-ttu-id="5e1d3-110">at <A href="http://go.microsoft.com/fwlink/?linkid=278940">http://go.microsoft.com/fwlink/?LinkId=278940</A>。</span><span class="sxs-lookup"><span data-stu-id="5e1d3-110">at <A href="http://go.microsoft.com/fwlink/?linkid=278940">http://go.microsoft.com/fwlink/?LinkId=278940</A>.</span></span>



</div>

<div>

## <a name="to-deploy-sefautil"></a><span data-ttu-id="5e1d3-111">SEFAUtil を展開するには</span><span class="sxs-lookup"><span data-stu-id="5e1d3-111">To deploy SEFAUtil</span></span>

1.  <span data-ttu-id="5e1d3-112">Lync Server 管理シェルが RTCUniversalServerAdmins グループのメンバーとして、または「 [Lync server 2013 の委任セットアップの権限](lync-server-2013-delegate-setup-permissions.md)」で説明されているように、必要なユーザー権限を持つコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="5e1d3-112">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="5e1d3-113">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="5e1d3-113">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="5e1d3-114">SEFAUtil ツールは、信頼済みアプリケーション プールに含まれるコンピューターでのみ実行できます。</span><span class="sxs-lookup"><span data-stu-id="5e1d3-114">The SEFAUtil tool can be run only on a computer that is part of a trusted application pool.</span></span> <span data-ttu-id="5e1d3-115">必要に応じて、SEFAUtil を実行する予定のフロントエンドプールの信頼されたアプリケーションプールを定義します。</span><span class="sxs-lookup"><span data-stu-id="5e1d3-115">If needed, define a trusted application pool for the Front End pool where you plan to run SEFAUtil.</span></span> <span data-ttu-id="5e1d3-116">コマンド ラインで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5e1d3-116">At the command line, run:</span></span>
    
        New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>

4.  <span data-ttu-id="5e1d3-p104">SEFAUtil ツールを信頼済みアプリケーションとして定義します。コマンド ラインで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5e1d3-p104">Define the SEFAUtil tool as a trusted application. At the command line, run:</span></span>
    
        New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5e1d3-119">必要に応じて、別のポートを使用できます。</span><span class="sxs-lookup"><span data-stu-id="5e1d3-119">You can use a different port if needed.</span></span>

    
    </div>

5.  <span data-ttu-id="5e1d3-p105">変更を加えたトポロジを有効にします。コマンド ラインで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5e1d3-p105">Enable the topology with your changes. At the command line, run:</span></span>
    
        Enable-CsTopology

6.  <span data-ttu-id="5e1d3-122">手順3で作成した信頼済みアプリケーションプール内のフロントエンドサーバーに Lync Server 2013 リソースキットツールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="5e1d3-122">Install the Lync Server 2013 resource kit tools on a Front End Server that is in the trusted application pool that you created in step 3.</span></span>

7.  <span data-ttu-id="5e1d3-123">次のように、SEFAUtil ツールが正常に実行していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5e1d3-123">Verify that the SEFAUtil tool is running correctly, as follows:</span></span>
    
    1.  <span data-ttu-id="5e1d3-124">管理者特権で Windows コマンド プロンプトからツールを実行し、展開内のユーザーの着信転送設定を表示します。</span><span class="sxs-lookup"><span data-stu-id="5e1d3-124">Run the tool from the Windows command prompt with administrator privileges to display the call forwarding settings of a user in your deployment.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="5e1d3-125">このツールは、Reskit の Lync Server 2013 \ にあります。</span><span class="sxs-lookup"><span data-stu-id="5e1d3-125">The tool is located at \Program Files\Microsoft Lync Server 2013\Reskit.</span></span>

        
        </div>
    
    2.  <span data-ttu-id="5e1d3-p106">ユーザーの着信転送設定を表示します。コマンド ラインで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5e1d3-p106">Display the call forwarding settings of a user. At the command line, run:</span></span>
        
            SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
        
        <span data-ttu-id="5e1d3-128">ユーザーの着信転送設定が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5e1d3-128">The call forwarding settings for the user will be displayed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

