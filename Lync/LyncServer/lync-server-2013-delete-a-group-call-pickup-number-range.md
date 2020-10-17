---
title: 'Lync Server 2013: グループ通話ピックアップ番号の範囲の削除'
description: 'Lync Server 2013: グループ通話ピックアップ番号の範囲を削除します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a Group Call Pickup number range
ms:assetid: 521891f3-7a5d-45de-92dc-d57025453159
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945629(v=OCS.15)
ms:contentKeyID: 51541475
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b40d423b64d29300741c55433864128897c3ac8f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566553"
---
# <a name="delete-a-group-call-pickup-number-range-in-lync-server-2013"></a><span data-ttu-id="bfc23-103">Lync Server 2013 でグループ通話ピックアップ番号の範囲を削除する</span><span class="sxs-lookup"><span data-stu-id="bfc23-103">Delete a Group Call Pickup number range in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bfc23-104">_**トピックの最終更新日:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="bfc23-104">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="bfc23-105">グループ通話ピックアップ番号の範囲を削除するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="bfc23-105">Use the following procedure to delete a Group Call Pickup number range.</span></span>

<div>

## <a name="to-delete-a-call-pickup-group-number-range"></a><span data-ttu-id="bfc23-106">通話ピックアップグループの番号範囲を削除するには</span><span class="sxs-lookup"><span data-stu-id="bfc23-106">To delete a call pickup group number range</span></span>

1.  <span data-ttu-id="bfc23-107">Lync Server 管理シェルがインストールされているコンピューターに、RTCUniversalServerAdmins グループのメンバーとして、または「 [Lync server 2013 のセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)」に説明されている必要なユーザー権限を使用してログオンします。</span><span class="sxs-lookup"><span data-stu-id="bfc23-107">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="bfc23-108">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="bfc23-108">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="bfc23-109">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="bfc23-109">At the command line, type:</span></span>
    
        Remove-CsCallParkOrbit -Identity "<group number range name>" 
    
    <span data-ttu-id="bfc23-110">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="bfc23-110">For example:</span></span>
    
        Remove-CsCallParkOrbit -Identity "Redmond call pickup"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bfc23-111">その他のオプションの詳細については、「 <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsCallParkOrbit">get-cscallparkorbit</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bfc23-111">For details about more options, see <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsCallParkOrbit">Remove-CsCallParkOrbit</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bfc23-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="bfc23-112">See Also</span></span>


[<span data-ttu-id="bfc23-113">Lync Server 2013 でのコールパークオービット範囲の作成または変更</span><span class="sxs-lookup"><span data-stu-id="bfc23-113">Create or modify a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)  


[<span data-ttu-id="bfc23-114">Get-cscallparkorbit</span><span class="sxs-lookup"><span data-stu-id="bfc23-114">Remove-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsCallParkOrbit)  
[<span data-ttu-id="bfc23-115">Get-cscallparkorbit</span><span class="sxs-lookup"><span data-stu-id="bfc23-115">Get-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCallParkOrbit)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

