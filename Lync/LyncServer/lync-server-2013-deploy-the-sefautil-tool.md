---
title: 'Lync Server 2013: SEFAUtil ツールの展開'
description: 'Lync Server 2013: SEFAUtil ツールを展開します。'
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
ms.openlocfilehash: 311f14f33dff30b388836a7f02483c4afe5da1b1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558613"
---
# <a name="deploy-the-sefautil-tool-in-lync-server-2013"></a><span data-ttu-id="fba98-103">SEFAUtil ツールを Lync Server 2013 に展開する</span><span class="sxs-lookup"><span data-stu-id="fba98-103">Deploy the SEFAUtil tool in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fba98-104">_**トピックの最終更新日:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="fba98-104">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="fba98-105">グループ通話ピックアップを展開および管理するには、SEFAUtil リソースキットツールを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fba98-105">To deploy and manage Group Call Pickup, you need to use the SEFAUtil resource kit tool.</span></span> <span data-ttu-id="fba98-106">このツールは、Lync Server 2013 リソースキットツールに含まれています。</span><span class="sxs-lookup"><span data-stu-id="fba98-106">The tool is part of the Lync Server 2013 resource kit tools.</span></span> <span data-ttu-id="fba98-107">SEFAUtil をインストールする前に、信頼されたアプリケーションプールをトポロジに含める必要があり、信頼済みアプリケーションとして SEFAUtil を指定し、トポロジを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="fba98-107">Before you can install SEFAUtil, you must have a trusted application pool in your topology, specify SEFAUtil as a trusted application, and enable the topology.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="fba98-108">Microsoft 統合コミュニケーション管理 API (UCMA) 3.0 コア SDK は、SEFAUtil ツールの実行を計画している任意のコンピューターにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="fba98-108">Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK must be installed on any computer where you plan to run the SEFAUtil tool.</span></span>



</div>

<span data-ttu-id="fba98-109">SEFAUtil は、展開内の任意のフロントエンドプールで実行できます。</span><span class="sxs-lookup"><span data-stu-id="fba98-109">You can run the SEFAUtil in any Front End pool in your deployment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fba98-110">SEFAUtil の実行の詳細については、Technet の記事「How to get SEFAutil running?」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fba98-110">For more details about running SEFAUtil, see the Technet blog article, "How to get SEFAutil running?"</span></span> <span data-ttu-id="fba98-111">at <A href="https://go.microsoft.com/fwlink/?linkid=278940">https://go.microsoft.com/fwlink/?LinkId=278940</A></span><span class="sxs-lookup"><span data-stu-id="fba98-111">at <A href="https://go.microsoft.com/fwlink/?linkid=278940">https://go.microsoft.com/fwlink/?LinkId=278940</A>.</span></span>



</div>

<div>

## <a name="to-deploy-sefautil"></a><span data-ttu-id="fba98-112">SEFAUtil を展開するには</span><span class="sxs-lookup"><span data-stu-id="fba98-112">To deploy SEFAUtil</span></span>

1.  <span data-ttu-id="fba98-113">Lync Server 管理シェルがインストールされているコンピューターに、RTCUniversalServerAdmins グループのメンバーとして、または「 [Lync server 2013 のセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)」に説明されている必要なユーザー権限を使用してログオンします。</span><span class="sxs-lookup"><span data-stu-id="fba98-113">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="fba98-114">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="fba98-114">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="fba98-115">SEFAUtil ツールは、信頼されたアプリケーションプールの一部であるコンピューターでのみ実行できます。</span><span class="sxs-lookup"><span data-stu-id="fba98-115">The SEFAUtil tool can be run only on a computer that is part of a trusted application pool.</span></span> <span data-ttu-id="fba98-116">必要に応じて、SEFAUtil の実行を計画しているフロントエンドプールの信頼されたアプリケーションプールを定義します。</span><span class="sxs-lookup"><span data-stu-id="fba98-116">If needed, define a trusted application pool for the Front End pool where you plan to run SEFAUtil.</span></span> <span data-ttu-id="fba98-117">コマンド ラインで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="fba98-117">At the command line, run:</span></span>
    
        New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>

4.  <span data-ttu-id="fba98-118">SEFAUtil ツールを信頼済みアプリケーションとして定義します。</span><span class="sxs-lookup"><span data-stu-id="fba98-118">Define the SEFAUtil tool as a trusted application.</span></span> <span data-ttu-id="fba98-119">コマンド ラインで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="fba98-119">At the command line, run:</span></span>
    
        New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fba98-120">必要に応じて、別のポートを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="fba98-120">You can use a different port if needed.</span></span>

    
    </div>

5.  <span data-ttu-id="fba98-121">変更したトポロジを有効にします。</span><span class="sxs-lookup"><span data-stu-id="fba98-121">Enable the topology with your changes.</span></span> <span data-ttu-id="fba98-122">コマンド ラインで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="fba98-122">At the command line, run:</span></span>
    
        Enable-CsTopology

6.  <span data-ttu-id="fba98-123">手順3で作成した信頼されたアプリケーションプールにあるフロントエンドサーバーに、Lync Server 2013 リソースキットツールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="fba98-123">Install the Lync Server 2013 resource kit tools on a Front End Server that is in the trusted application pool that you created in step 3.</span></span>

7.  <span data-ttu-id="fba98-124">SEFAUtil ツールが正常に実行されていることを、次のように確認します。</span><span class="sxs-lookup"><span data-stu-id="fba98-124">Verify that the SEFAUtil tool is running correctly, as follows:</span></span>
    
    1.  <span data-ttu-id="fba98-125">管理者特権を使用して Windows コマンドプロンプトからツールを実行し、展開内のユーザーの着信転送設定を表示します。</span><span class="sxs-lookup"><span data-stu-id="fba98-125">Run the tool from the Windows command prompt with administrator privileges to display the call forwarding settings of a user in your deployment.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="fba98-126">このツールは、うえの「Lync Server 2013」にあります。</span><span class="sxs-lookup"><span data-stu-id="fba98-126">The tool is located at \Program Files\Microsoft Lync Server 2013\Reskit.</span></span>

        
        </div>
    
    2.  <span data-ttu-id="fba98-127">ユーザーの着信転送設定を表示します。</span><span class="sxs-lookup"><span data-stu-id="fba98-127">Display the call forwarding settings of a user.</span></span> <span data-ttu-id="fba98-128">コマンド ラインで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="fba98-128">At the command line, run:</span></span>
        
            SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
        
        <span data-ttu-id="fba98-129">ユーザーの着信転送設定が表示されます。</span><span class="sxs-lookup"><span data-stu-id="fba98-129">The call forwarding settings for the user will be displayed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

