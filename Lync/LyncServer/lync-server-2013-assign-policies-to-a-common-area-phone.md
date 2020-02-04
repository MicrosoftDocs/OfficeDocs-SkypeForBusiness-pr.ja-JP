---
title: 'Lync Server 2013: 共通の市外局番にポリシーを割り当てる'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign policies to a common area phone
ms:assetid: f0554fd1-b237-49b3-9eb4-26f4b91f5604
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994082(v=OCS.15)
ms:contentKeyID: 51803993
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e19e2fccabe4759f8cf4cf5eb55ade7e68e2b560
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734047"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assign-policies-in-lync-server-2013-to-a-common-area-phone"></a><span data-ttu-id="46095-102">Lync Server 2013 で共通の市外局番にポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="46095-102">Assign policies in Lync Server 2013 to a common area phone</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="46095-103">_**トピックの最終更新日:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="46095-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="46095-104">一般的なエリア電話のポリシーを作成したら (詳細については、「 [Lync Server 2013 で音声ポリシーを作成し、PSTN 使用状況レコードを構成](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)する」を参照してください)、Windows PowerShell と適切な**Grant**コマンドレットを使用して、共通の市外局番にポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="46095-104">After you create your policy for common area phones (for details, see [Create a voice policy and configure PSTN usage records in Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)), you can assign the policy to a common area phone by using Windows PowerShell and the appropriate **Grant-Cs** cmdlet.</span></span> <span data-ttu-id="46095-105">これらのコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="46095-105">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="46095-106">リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。</span><span class="sxs-lookup"><span data-stu-id="46095-106">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>


<div>

## <a name="assigning-a-policy-to-a-single-common-area-phone"></a><span data-ttu-id="46095-107">単一の一般的な市外局番にポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="46095-107">Assigning a Policy to a Single Common Area Phone</span></span>

  - <span data-ttu-id="46095-108">次のコマンドは、Id の建物14ロビーを持つ共通の市外局番に、ユーザーごとのボイスポリシー RedmondVoice を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="46095-108">The following command assigns the per-user voice policy RedmondVoice to the common area phone that has the Identity Building 14 Lobby.</span></span>
    
        Grant-CsVoicePolicy -Identity "Building 14 Lobby" -PolicyName "RedmondVoicePolicy"

</div>

<div>

## <a name="assigning-a-policy-to-multiple-common-area-phones"></a><span data-ttu-id="46095-109">複数の共通エリア電話にポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="46095-109">Assigning a Policy to Multiple Common Area Phones</span></span>

  - <span data-ttu-id="46095-110">この例では、組織で使用するために構成されているすべての共通エリア電話に、ユーザーごとのボイスポリシー RedmondVoice が割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="46095-110">In this example, the per-user voice policy RedmondVoice is assigned to all the common area phones configured for use in the organization.</span></span>
    
        Get-CsCommonAreaPhone | Grant-CsVoicePolicy  -PolicyName "RedmondVoicePolicy"

</div>

<span data-ttu-id="46095-111">詳細については、「 [Grant-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsVoicePolicy)のヘルプトピック」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="46095-111">For details, see the Help topics for the [Grant-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsVoicePolicy).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="46095-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="46095-112">See Also</span></span>


[<span data-ttu-id="46095-113">Get-CsCommonAreaPhone</span><span class="sxs-lookup"><span data-stu-id="46095-113">Get-CsCommonAreaPhone</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

