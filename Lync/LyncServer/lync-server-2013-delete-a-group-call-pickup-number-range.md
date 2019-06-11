---
title: 'Lync Server 2013: グループ通話の集配番号の範囲を削除する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete a Group Call Pickup number range
ms:assetid: 521891f3-7a5d-45de-92dc-d57025453159
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945629(v=OCS.15)
ms:contentKeyID: 51541475
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7429543c48018eb8fef45e372a4788968396f256
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833643"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-group-call-pickup-number-range-in-lync-server-2013"></a><span data-ttu-id="024bf-102">Lync Server 2013 でグループ通話の集配番号の範囲を削除する</span><span class="sxs-lookup"><span data-stu-id="024bf-102">Delete a Group Call Pickup number range in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="024bf-103">_**最終更新日:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="024bf-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="024bf-104">グループ通話の集配番号の範囲を削除するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="024bf-104">Use the following procedure to delete a Group Call Pickup number range.</span></span>

<div>

## <a name="to-delete-a-call-pickup-group-number-range"></a><span data-ttu-id="024bf-105">通話ピックアップグループの番号範囲を削除するには</span><span class="sxs-lookup"><span data-stu-id="024bf-105">To delete a call pickup group number range</span></span>

1.  <span data-ttu-id="024bf-106">Lync Server 管理シェルが RTCUniversalServerAdmins グループのメンバーとして、または「 [Lync server 2013 の委任セットアップの権限](lync-server-2013-delegate-setup-permissions.md)」で説明されているように、必要なユーザー権限を持つコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="024bf-106">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="024bf-107">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="024bf-107">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="024bf-108">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="024bf-108">At the command line, type:</span></span>
    
        Remove-CsCallParkOrbit -Identity "<group number range name>" 
    
    <span data-ttu-id="024bf-109">例:</span><span class="sxs-lookup"><span data-stu-id="024bf-109">For example:</span></span>
    
        Remove-CsCallParkOrbit -Identity "Redmond call pickup"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="024bf-110">その他のオプションの詳細については、「 <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsCallParkOrbit">Remove-CsCallParkOrbit</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="024bf-110">For details about more options, see <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsCallParkOrbit">Remove-CsCallParkOrbit</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="024bf-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="024bf-111">See Also</span></span>


[<span data-ttu-id="024bf-112">通話パークの作成または変更 Lync Server 2013 の範囲の軌道</span><span class="sxs-lookup"><span data-stu-id="024bf-112">Create or modify a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)  


[<span data-ttu-id="024bf-113">Remove-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="024bf-113">Remove-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsCallParkOrbit)  
[<span data-ttu-id="024bf-114">Get-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="024bf-114">Get-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCallParkOrbit)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

