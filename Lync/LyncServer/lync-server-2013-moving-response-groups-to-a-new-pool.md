---
title: 'Lync Server 2013: 応答グループを新しいプールに移動する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Moving response groups to a new pool
ms:assetid: da0db765-41e5-430b-b5a7-5418ec5ff2a7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205298(v=OCS.15)
ms:contentKeyID: 48185538
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 96740d8937f1548952d41d5674ef3e66cd29e2b6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756711"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="moving-response-groups-to-a-new-pool-in-lync-server-2013"></a><span data-ttu-id="5f794-102">Lync Server 2013 の新しいプールへの応答グループの移動</span><span class="sxs-lookup"><span data-stu-id="5f794-102">Moving response groups to a new pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5f794-103">_**最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="5f794-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="5f794-104">Lync Server 2013 では、完全修飾ドメイン名 (FQDN) が異なる場合でも、1つのプールから別のプールに応答グループを移動するための新しいコマンドレットのサポートが導入されています。</span><span class="sxs-lookup"><span data-stu-id="5f794-104">Lync Server 2013 introduces new cmdlet support for moving response groups from one pool to another pool, even when the fully qualified domain name (FQDN) is different.</span></span>

<span data-ttu-id="5f794-105">次の手順を使用して、1つのフロントエンドプールから別の FQDN で応答グループを別のフロントエンドプールに移動します。</span><span class="sxs-lookup"><span data-stu-id="5f794-105">Use the steps in the following procedure to move response groups from one Front End pool to another Front End pool with a different FQDN.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5f794-106">共存環境では、Lync Server 2013&nbsp;フロントエンドプール間でのみ応答グループを移動できます。</span><span class="sxs-lookup"><span data-stu-id="5f794-106">In a coexistence environment, you can move response groups only between Lync Server 2013&nbsp;Front End pools.</span></span>



</div>

<div>

## <a name="to-move-response-groups-to-a-pool-with-a-different-fqdn"></a><span data-ttu-id="5f794-107">応答グループを別の FQDN のプールに移動するには</span><span class="sxs-lookup"><span data-stu-id="5f794-107">To move response groups to a pool with a different FQDN</span></span>

1.  <span data-ttu-id="5f794-108">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="5f794-108">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="5f794-109">ソースプールの応答グループをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="5f794-109">Export the response groups in the source pool.</span></span> <span data-ttu-id="5f794-110">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="5f794-110">At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<source FQDN>" -FileName "<export file name>"
    
    <span data-ttu-id="5f794-111">例:</span><span class="sxs-lookup"><span data-stu-id="5f794-111">For example:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:source.contoso.com" -FileName "C:\RgsExportSource.zip"
    
    <span data-ttu-id="5f794-112">エクスポート中にソースプールから応答グループを削除するには、– RemoveExportedConfiguration パラメーターを含めます。</span><span class="sxs-lookup"><span data-stu-id="5f794-112">To remove the response groups from the source pool during the export, include the –RemoveExportedConfiguration parameter.</span></span> <span data-ttu-id="5f794-113">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="5f794-113">For example:</span></span>
    
        Export-CsRgsConfiguration -Source ApplicationServer:source.contoso.com -FileName "C:\RgsExportSource.zip" -RemoveExportedConfiguration

3.  <span data-ttu-id="5f794-114">宛先プールに応答グループをインポートして、新しい所有者として宛先プールを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="5f794-114">Import the response groups to the destination pool and assign the destination pool as the new owner.</span></span> <span data-ttu-id="5f794-115">コマンド ラインで次を入力します。</span><span class="sxs-lookup"><span data-stu-id="5f794-115">At the command line, type:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<destination pool>" -FileName "<export file name>" -OverwriteOwner
    
    <span data-ttu-id="5f794-116">応答グループのアプリケーションレベルの設定をソースプールから移行先のプールにコピーする必要がある場合は、– ReplaceExistingRgsSettings パラメーターを含めます。</span><span class="sxs-lookup"><span data-stu-id="5f794-116">If you also want to copy the Response Group application-level settings from the source pool to the destination pool, include the –ReplaceExistingRgsSettings parameter.</span></span> <span data-ttu-id="5f794-117">プールごとに1つのアプリケーションレベルの設定のみを定義できます。</span><span class="sxs-lookup"><span data-stu-id="5f794-117">You can define only one set of application-level settings per pool.</span></span> <span data-ttu-id="5f794-118">ソースプールからターゲットプールにアプリケーションレベルの設定をコピーすると、ソースプールの設定が移行先のプールの設定と置き換わります。</span><span class="sxs-lookup"><span data-stu-id="5f794-118">If you copy the application-level settings from the source pool to the destination pool, the settings from the source pool replace the settings for the destination pool.</span></span> <span data-ttu-id="5f794-119">ソースプールからアプリケーションレベルの設定をコピーしない場合、移行先プールの既存の設定はインポートされた応答グループに適用されます。</span><span class="sxs-lookup"><span data-stu-id="5f794-119">If you do not copy the application-level settings from the source pool, the existing settings from the destination pool apply to the imported response groups.</span></span>
    
    <span data-ttu-id="5f794-120">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="5f794-120">For example:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:destination.contoso.com" -FileName "C:\RgsExportSource.zip" -OverwriteOwner -ReplaceExistingRgsSettings
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5f794-121">アプリケーションレベルの設定には、既定の音楽保留の構成、既定の音楽の保留中のオーディオファイル、エージェントの ringback の猶予期間、通話コンテキストの構成が含まれます。</span><span class="sxs-lookup"><span data-stu-id="5f794-121">Application-level settings include the default music-on-hold configuration, the default music-on-hold audio file, the agent ringback grace period, and the call context configuration.</span></span> <span data-ttu-id="5f794-122">これらの構成設定を表示するには、 <STRONG>Get-CsRgsConfiguration</STRONG>コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="5f794-122">To view these configuration settings, run the <STRONG>Get-CsRgsConfiguration</STRONG> cmdlet.</span></span> <span data-ttu-id="5f794-123">このコマンドレットの詳細については、「 <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration">Get-CsRgsConfiguration</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5f794-123">For details about this cmdlet, see <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration">Get-CsRgsConfiguration</A>.</span></span>

    
    </div>

4.  <span data-ttu-id="5f794-124">インポートされた応答グループの構成を表示してインポートが正常に完了したことを確認するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="5f794-124">Verify that the import was successful by displaying the imported response group configuration by doing the following:</span></span>
    
      - <span data-ttu-id="5f794-125">すべてのワークフローがインポートされたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="5f794-125">Verify that all the workflows were imported.</span></span> <span data-ttu-id="5f794-126">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="5f794-126">At the command line, type the following:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - <span data-ttu-id="5f794-127">すべてのキューがインポートされたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="5f794-127">Verify that all the queues were imported.</span></span> <span data-ttu-id="5f794-128">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="5f794-128">At the command line, type the following:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - <span data-ttu-id="5f794-129">すべてのエージェントグループがインポートされたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="5f794-129">Verify that all the agent groups were imported.</span></span> <span data-ttu-id="5f794-130">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="5f794-130">At the command line, type the following:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - <span data-ttu-id="5f794-131">すべての勤務時間がインポートされたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="5f794-131">Verify that all the hours of business were imported.</span></span> <span data-ttu-id="5f794-132">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="5f794-132">At the command line, type the following:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<destination pool FQDN>" 
    
      - <span data-ttu-id="5f794-133">すべての休日セットがインポートされたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="5f794-133">Verify that all the holiday sets were imported.</span></span> <span data-ttu-id="5f794-134">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="5f794-134">At the command line, type the following:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<destination pool FQDN>" 

5.  <span data-ttu-id="5f794-135">応答グループの1つに通話を発信し、通話が正しく処理されていることを確認して、インポートが成功したことを確認します。</span><span class="sxs-lookup"><span data-stu-id="5f794-135">Verify that the import was successful by placing a call to one of the response groups and verifying that the call is handled correctly.</span></span>

6.  <span data-ttu-id="5f794-136">送信先のプールのエージェントグループにサインインするために、正式なエージェントグループのメンバーであるエージェントを要求します。</span><span class="sxs-lookup"><span data-stu-id="5f794-136">Request agents who are members of formal agent groups to sign in to their agent groups in the destination pool.</span></span>

7.  <span data-ttu-id="5f794-137">ソースプールから応答グループを削除していない場合は、ソースプールから応答グループを削除します。</span><span class="sxs-lookup"><span data-stu-id="5f794-137">If you did not previously remove response groups from the source pool, remove the response groups from the source pool.</span></span> <span data-ttu-id="5f794-138">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="5f794-138">At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<source pool FQDN> -RemoveExportedConfiguration -FileName "<temporary export file name>"
    
    <span data-ttu-id="5f794-139">例:</span><span class="sxs-lookup"><span data-stu-id="5f794-139">For example:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:source.contoso.com" -RemoveExportedConfiguration -FileName "C:\TempRGsConfiguration.zip"

</div>

</div>

<span> </span>

</div>

</div>

</div>

