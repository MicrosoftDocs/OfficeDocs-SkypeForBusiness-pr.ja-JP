---
title: 'Lync Server 2013: 共通領域電話へのポリシーの割り当て'
description: 'Lync Server 2013: 共通領域電話にポリシーを割り当てます。'
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
ms.openlocfilehash: fe437ec87ba30eff834239db2b4815adb2d5718c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559823"
---
# <a name="assign-policies-in-lync-server-2013-to-a-common-area-phone"></a><span data-ttu-id="8086b-103">Lync Server 2013 のポリシーを共通領域電話に割り当てる</span><span class="sxs-lookup"><span data-stu-id="8086b-103">Assign policies in Lync Server 2013 to a common area phone</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8086b-104">_**トピックの最終更新日:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="8086b-104">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="8086b-105">共通領域電話のポリシーを作成した後 (詳細については、「 [create a voice policy and CONFIGURE PSTN usage records In Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)」を参照してください)、Windows PowerShell と適切な **付与/Cs** コマンドレットを使用して、ポリシーを共通領域電話に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="8086b-105">After you create your policy for common area phones (for details, see [Create a voice policy and configure PSTN usage records in Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)), you can assign the policy to a common area phone by using Windows PowerShell and the appropriate **Grant-Cs** cmdlet.</span></span> <span data-ttu-id="8086b-106">これらのコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="8086b-106">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="8086b-107">リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。</span><span class="sxs-lookup"><span data-stu-id="8086b-107">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>


<div>

## <a name="assigning-a-policy-to-a-single-common-area-phone"></a><span data-ttu-id="8086b-108">単一の共通領域電話へのポリシーの割り当て</span><span class="sxs-lookup"><span data-stu-id="8086b-108">Assigning a Policy to a Single Common Area Phone</span></span>

  - <span data-ttu-id="8086b-109">次のコマンドは、ユーザーごとの音声ポリシー RedmondVoice を、Identity を作成14ロビーの共通領域電話に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="8086b-109">The following command assigns the per-user voice policy RedmondVoice to the common area phone that has the Identity Building 14 Lobby.</span></span>
    
        Grant-CsVoicePolicy -Identity "Building 14 Lobby" -PolicyName "RedmondVoicePolicy"

</div>

<div>

## <a name="assigning-a-policy-to-multiple-common-area-phones"></a><span data-ttu-id="8086b-110">複数の共通領域電話へのポリシーの割り当て</span><span class="sxs-lookup"><span data-stu-id="8086b-110">Assigning a Policy to Multiple Common Area Phones</span></span>

  - <span data-ttu-id="8086b-111">この例では、ユーザーごとの音声ポリシー RedmondVoice は、組織での使用が構成されているすべての共通領域電話に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="8086b-111">In this example, the per-user voice policy RedmondVoice is assigned to all the common area phones configured for use in the organization.</span></span>
    
        Get-CsCommonAreaPhone | Grant-CsVoicePolicy  -PolicyName "RedmondVoicePolicy"

</div>

<span data-ttu-id="8086b-112">詳細については、 [set-csvoicepolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsVoicePolicy)のヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8086b-112">For details, see the Help topics for the [Grant-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsVoicePolicy).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8086b-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="8086b-113">See Also</span></span>


[<span data-ttu-id="8086b-114">Move-cscommonareaphone</span><span class="sxs-lookup"><span data-stu-id="8086b-114">Get-CsCommonAreaPhone</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

