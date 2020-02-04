---
title: 'Lync Server 2013: 応答グループの設定を復元する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring Response Group settings
ms:assetid: 4f8e1949-925d-4538-be1d-9ac7c06b2aca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202174(v=OCS.15)
ms:contentKeyID: 51541473
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 64bc766cf970e95ad03be65c490882dd3471955b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733057"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-response-group-settings-in-lync-server-2013"></a><span data-ttu-id="f3bb3-102">Lync Server 2013 での応答グループの設定の復元</span><span class="sxs-lookup"><span data-stu-id="f3bb3-102">Restoring Response Group settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f3bb3-103">_**最終更新日:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="f3bb3-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="f3bb3-104">応答グループアプリケーションを展開し、バックエンドサーバーまたは Standard Edition サーバーを復元する必要がある場合は、応答グループの構成設定も復元する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f3bb3-104">If you deployed the Response Group application and you need to restore a Back End Server or a Standard Edition server, you also need to restore the Response Group configuration settings.</span></span>

<div>

## <a name="to-restore-response-group-configuration-settings"></a><span data-ttu-id="f3bb3-105">応答グループの構成設定を復元するには</span><span class="sxs-lookup"><span data-stu-id="f3bb3-105">To restore Response Group configuration settings</span></span>

1.  <span data-ttu-id="f3bb3-106">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="f3bb3-106">At the command line, type:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<pool FQDN>" -OverwriteOwner -FileName "<path and file name of the backed up file at $Backup>"
    
    <span data-ttu-id="f3bb3-107">例:</span><span class="sxs-lookup"><span data-stu-id="f3bb3-107">For example:</span></span>
    
        Import-CsRgsConfiguration -Destination "service: ApplicationServer:pool01.contoso.com" -OverwriteOwner -FileName "C:\RgsConfiguration.zip"

</div>

</div>

<span> </span>

</div>

</div>

</div>

