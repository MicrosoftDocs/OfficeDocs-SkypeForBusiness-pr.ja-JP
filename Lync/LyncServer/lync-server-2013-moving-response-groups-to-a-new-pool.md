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
ms.openlocfilehash: 41d739ae79998fe3dbf3acadba2b2f480a960a30
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046280"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="moving-response-groups-to-a-new-pool-in-lync-server-2013"></a><span data-ttu-id="d21f2-102">Lync Server 2013 の新しいプールへの応答グループの移動</span><span class="sxs-lookup"><span data-stu-id="d21f2-102">Moving response groups to a new pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d21f2-103">_**トピックの最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="d21f2-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="d21f2-104">Lync Server 2013 は、完全修飾ドメイン名 (FQDN) が異なる場合でも、あるプールから別のプールに応答グループを移動するための新しいコマンドレットのサポートを導入しました。</span><span class="sxs-lookup"><span data-stu-id="d21f2-104">Lync Server 2013 introduces new cmdlet support for moving response groups from one pool to another pool, even when the fully qualified domain name (FQDN) is different.</span></span>

<span data-ttu-id="d21f2-105">次の手順を使用して、応答グループを1つのフロントエンドプールから別の FQDN の別のフロントエンドプールに移動します。</span><span class="sxs-lookup"><span data-stu-id="d21f2-105">Use the steps in the following procedure to move response groups from one Front End pool to another Front End pool with a different FQDN.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d21f2-106">共存環境では、Lync Server 2013&nbsp;フロントエンドプール間でのみ応答グループを移動できます。</span><span class="sxs-lookup"><span data-stu-id="d21f2-106">In a coexistence environment, you can move response groups only between Lync Server 2013&nbsp;Front End pools.</span></span>



</div>

<div>

## <a name="to-move-response-groups-to-a-pool-with-a-different-fqdn"></a><span data-ttu-id="d21f2-107">応答グループを異なる FQDN を持つプールに移動するには</span><span class="sxs-lookup"><span data-stu-id="d21f2-107">To move response groups to a pool with a different FQDN</span></span>

1.  <span data-ttu-id="d21f2-108">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="d21f2-108">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="d21f2-p101">移動元のプール内の応答グループをエクスポートします。コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="d21f2-p101">Export the response groups in the source pool. At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<source FQDN>" -FileName "<export file name>"
    
    <span data-ttu-id="d21f2-111">例:</span><span class="sxs-lookup"><span data-stu-id="d21f2-111">For example:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:source.contoso.com" -FileName "C:\RgsExportSource.zip"
    
    <span data-ttu-id="d21f2-p102">エクスポート中に移動元のプールから応答グループを削除するには、–RemoveExportedConfiguration パラメーターを含めます。たとえば、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="d21f2-p102">To remove the response groups from the source pool during the export, include the –RemoveExportedConfiguration parameter. For example:</span></span>
    
        Export-CsRgsConfiguration -Source ApplicationServer:source.contoso.com -FileName "C:\RgsExportSource.zip" -RemoveExportedConfiguration

3.  <span data-ttu-id="d21f2-p103">応答グループを移動先のプールにインポートし、移動先のプールを新しい所有者として割り当てます。コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="d21f2-p103">Import the response groups to the destination pool and assign the destination pool as the new owner. At the command line, type:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<destination pool>" -FileName "<export file name>" -OverwriteOwner
    
    <span data-ttu-id="d21f2-116">応答グループのアプリケーションレベルの設定をソースプールから移行先のプールにコピーする場合は、-ReplaceExistingRgsSettings パラメーターを含めます。</span><span class="sxs-lookup"><span data-stu-id="d21f2-116">If you also want to copy the Response Group application-level settings from the source pool to the destination pool, include the –ReplaceExistingRgsSettings parameter.</span></span> <span data-ttu-id="d21f2-117">プールごとにアプリケーションレベルの設定のセットを 1 つだけ定義できます。</span><span class="sxs-lookup"><span data-stu-id="d21f2-117">You can define only one set of application-level settings per pool.</span></span> <span data-ttu-id="d21f2-118">アプリケーションレベルの設定をソース プールから転送先プールにコピーする場合は、転送先プールの設定がソース プールの設定に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="d21f2-118">If you copy the application-level settings from the source pool to the destination pool, the settings from the source pool replace the settings for the destination pool.</span></span> <span data-ttu-id="d21f2-119">アプリケーションレベルの設定をソース プールからコピーしない場合は、転送先プールの既存の設定が、インポートされた応答グループに適用されます。</span><span class="sxs-lookup"><span data-stu-id="d21f2-119">If you do not copy the application-level settings from the source pool, the existing settings from the destination pool apply to the imported response groups.</span></span>
    
    <span data-ttu-id="d21f2-120">例:</span><span class="sxs-lookup"><span data-stu-id="d21f2-120">For example:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:destination.contoso.com" -FileName "C:\RgsExportSource.zip" -OverwriteOwner -ReplaceExistingRgsSettings
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d21f2-121">アプリケーションレベルの設定には、既定の保留音の構成、既定の保留音の音声ファイル、エージェント リングバックの猶予期間、および通話コンテキストの構成が含まれます。</span><span class="sxs-lookup"><span data-stu-id="d21f2-121">Application-level settings include the default music-on-hold configuration, the default music-on-hold audio file, the agent ringback grace period, and the call context configuration.</span></span> <span data-ttu-id="d21f2-122">これらの構成を表示するには、<STRONG>Get-CsRgsConfiguration</STRONG> コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="d21f2-122">To view these configuration settings, run the <STRONG>Get-CsRgsConfiguration</STRONG> cmdlet.</span></span> <span data-ttu-id="d21f2-123">このコマンドレットの詳細については、「 <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration">get-help</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d21f2-123">For details about this cmdlet, see <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration">Get-CsRgsConfiguration</A>.</span></span>

    
    </div>

4.  <span data-ttu-id="d21f2-124">次の操作を実行してインポートされた応答グループの構成を表示することにより、インポートが成功したことを確認します。</span><span class="sxs-lookup"><span data-stu-id="d21f2-124">Verify that the import was successful by displaying the imported response group configuration by doing the following:</span></span>
    
      - <span data-ttu-id="d21f2-p106">すべてのワークフローがインポートされたことを確認します。コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="d21f2-p106">Verify that all the workflows were imported. At the command line, type the following:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - <span data-ttu-id="d21f2-p107">すべてのキューがインポートされたことを確認します。コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="d21f2-p107">Verify that all the queues were imported. At the command line, type the following:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - <span data-ttu-id="d21f2-p108">すべてのエージェント グループがインポートされたことを確認します。コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="d21f2-p108">Verify that all the agent groups were imported. At the command line, type the following:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - <span data-ttu-id="d21f2-p109">すべての営業時間がインポートされたことを確認します。コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="d21f2-p109">Verify that all the hours of business were imported. At the command line, type the following:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<destination pool FQDN>" 
    
      - <span data-ttu-id="d21f2-p110">すべての休日セットがインポートされたことを確認します。コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="d21f2-p110">Verify that all the holiday sets were imported. At the command line, type the following:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<destination pool FQDN>" 

5.  <span data-ttu-id="d21f2-135">応答グループの 1 つに電話をかけ、通話が正しく処理されることを確認して、インポートが正常に完了したことを確認します。</span><span class="sxs-lookup"><span data-stu-id="d21f2-135">Verify that the import was successful by placing a call to one of the response groups and verifying that the call is handled correctly.</span></span>

6.  <span data-ttu-id="d21f2-136">公式エージェント グループのメンバーであるエージェントに、移動先のプール内のエージェント グループにサインインするように要求します。</span><span class="sxs-lookup"><span data-stu-id="d21f2-136">Request agents who are members of formal agent groups to sign in to their agent groups in the destination pool.</span></span>

7.  <span data-ttu-id="d21f2-p111">前の手順で移動元のプールから応答グループを削除しなかった場合は、移動元のプールから応答グループを削除します。コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="d21f2-p111">If you did not previously remove response groups from the source pool, remove the response groups from the source pool. At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<source pool FQDN> -RemoveExportedConfiguration -FileName "<temporary export file name>"
    
    <span data-ttu-id="d21f2-139">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="d21f2-139">For example:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:source.contoso.com" -RemoveExportedConfiguration -FileName "C:\TempRGsConfiguration.zip"

</div>

</div>

<span> </span>

</div>

</div>

</div>

