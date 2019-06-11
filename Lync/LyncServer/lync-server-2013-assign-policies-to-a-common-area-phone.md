---
title: 'Lync Server 2013: 共通の市外局番にポリシーを割り当てる'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign policies to a common area phone
ms:assetid: f0554fd1-b237-49b3-9eb4-26f4b91f5604
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994082(v=OCS.15)
ms:contentKeyID: 51803993
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b792d6ae14ee13fd1d95761d2a0d6b0af7bbdfae
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848806"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assign-policies-in-lync-server-2013-to-a-common-area-phone"></a><span data-ttu-id="adf82-102">Lync Server 2013 で共通の市外局番にポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="adf82-102">Assign policies in Lync Server 2013 to a common area phone</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="adf82-103">_**最終更新日:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="adf82-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="adf82-104">一般的なエリア電話のポリシーを作成した後 (詳細については、「 [Lync Server 2013 でボイスポリシーを作成し、PSTN 使用状況レコードを構成](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)する)」を参照してください。このポリシーは、Windows PowerShell と適切な許可 (Cs) を使って共通の市外局番に割り当てることができます。 \*\*\*\* コマンドレット。</span><span class="sxs-lookup"><span data-stu-id="adf82-104">After you create your policy for common area phones (for details, see [Create a voice policy and configure PSTN usage records in Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)), you can assign the policy to a common area phone by using Windows PowerShell and the appropriate **Grant-Cs** cmdlet.</span></span> <span data-ttu-id="adf82-105">これらのコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="adf82-105">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="adf82-106">リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、「Lync Server Windows PowerShell のブログ記事」を参照してください[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。「リモート PowerShell を使用して Microsoft Lync Server 2010 を管理する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="adf82-106">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>


<div>

## <a name="assigning-a-policy-to-a-single-common-area-phone"></a><span data-ttu-id="adf82-107">単一の一般的な市外局番にポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="adf82-107">Assigning a Policy to a Single Common Area Phone</span></span>

  - <span data-ttu-id="adf82-108">次のコマンドは、Id の建物14ロビーを持つ共通の市外局番に、ユーザーごとのボイスポリシー RedmondVoice を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="adf82-108">The following command assigns the per-user voice policy RedmondVoice to the common area phone that has the Identity Building 14 Lobby.</span></span>
    
        Grant-CsVoicePolicy -Identity "Building 14 Lobby" -PolicyName "RedmondVoicePolicy"

</div>

<div>

## <a name="assigning-a-policy-to-multiple-common-area-phones"></a><span data-ttu-id="adf82-109">複数の共通エリア電話にポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="adf82-109">Assigning a Policy to Multiple Common Area Phones</span></span>

  - <span data-ttu-id="adf82-110">この例では、組織で使用するために構成されているすべての共通エリア電話に、ユーザーごとのボイスポリシー RedmondVoice が割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="adf82-110">In this example, the per-user voice policy RedmondVoice is assigned to all the common area phones configured for use in the organization.</span></span>
    
        Get-CsCommonAreaPhone | Grant-CsVoicePolicy  -PolicyName "RedmondVoicePolicy"

</div>

<span data-ttu-id="adf82-111">詳細については、「 [Grant-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsVoicePolicy)のヘルプトピック」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="adf82-111">For details, see the Help topics for the [Grant-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsVoicePolicy).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="adf82-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="adf82-112">See Also</span></span>


[<span data-ttu-id="adf82-113">Get-CsCommonAreaPhone</span><span class="sxs-lookup"><span data-stu-id="adf82-113">Get-CsCommonAreaPhone</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

