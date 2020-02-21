---
title: 'Lync Server 2013: トポロジビルダーでのトランクの変更'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify a trunk in Topology Builder
ms:assetid: 81055a82-c6f8-47b2-9779-223b1d842f36
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688110(v=OCS.15)
ms:contentKeyID: 49733709
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 936de680a13a3f9ec851181876ce7a80c1784e52
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184960"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="modify-a-trunk-in-topology-builder-in-lync-server-2013"></a><span data-ttu-id="3833f-102">Lync Server 2013 のトポロジビルダーでのトランクの変更</span><span class="sxs-lookup"><span data-stu-id="3833f-102">Modify a trunk in Topology Builder in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3833f-103">_**トピックの最終更新日:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="3833f-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="3833f-104">トランクの代替メディア IP アドレスおよび代替バイパス ID を変更するには、以下の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="3833f-104">Follow these steps to modify the alternate media IP address and alternate bypass identifier of a trunk.</span></span>

<div>

## <a name="to-modify-the-alternate-media-ip-address-of-a-trunk"></a><span data-ttu-id="3833f-105">トランクの代替メディア IP アドレスを変更するには</span><span class="sxs-lookup"><span data-stu-id="3833f-105">To Modify the Alternate Media IP Address of a Trunk</span></span>

1.  <span data-ttu-id="3833f-106">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="3833f-106">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="3833f-107">Set-CsPstnGateway コマンドレットを実行し、Lync Server 管理シェルの Nm-server-w15-mgmtshell-short で alternatebypassid フィールドを変更します。</span><span class="sxs-lookup"><span data-stu-id="3833f-107">Run the Set-CsPstnGateway cmdlet and modify the AlternateBypassId field in the Lync Server Management Shell.</span></span>
    
        Set-CsPstnGateway -Identity "PstnGateway:<peer FQDN> -RepresentativeMediaIP <IP address>

</div>

<div>

## <a name="to-modify-the-alternate-bypassid-of-a-trunk"></a><span data-ttu-id="3833f-108">トランクの代替バイパス ID を変更するには</span><span class="sxs-lookup"><span data-stu-id="3833f-108">To Modify the Alternate BypassID of a Trunk</span></span>

1.  <span data-ttu-id="3833f-109">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="3833f-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="3833f-110">Set-CsPstnGateway コマンドレットを実行し、Lync Server 管理シェルの Nm-server-w15-mgmtshell-short で alternatebypassid フィールドを変更します。</span><span class="sxs-lookup"><span data-stu-id="3833f-110">Run the Set-CsPstnGateway cmdlet and modify the AlternateBypassId field in the Lync Server Management Shell.</span></span>
    
        Set-CsPstnGateway -Identity "PstnGateway:<peer FQDN> -AlternateBypassID <identifier>

</div>

</div>

<span> </span>

</div>

</div>

</div>

