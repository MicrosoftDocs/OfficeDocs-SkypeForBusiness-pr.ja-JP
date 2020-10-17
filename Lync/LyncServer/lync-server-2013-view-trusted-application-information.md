---
title: 'Lync Server 2013: 信頼されたアプリケーション情報の表示'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View trusted application information
ms:assetid: 7b916323-96fb-4308-bc95-c178de41a3d3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688103(v=OCS.15)
ms:contentKeyID: 49733702
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b978d8184c9b5297fc8aa504fcaeca46810ff1eb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518364"
---
# <a name="view-trusted-application-information-in-lync-server-2013"></a><span data-ttu-id="b111d-102">Lync Server 2013 での信頼されたアプリケーション情報の表示</span><span class="sxs-lookup"><span data-stu-id="b111d-102">View trusted application information in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b111d-103">_**トピックの最終更新日:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="b111d-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="b111d-104">Windows PowerShell と **「new-cstrustedapplication** コマンドレットを使用して、信頼されたアプリケーションに関する情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="b111d-104">You can view information about your trusted applications by using Windows PowerShell and the **Get-CsTrustedApplication** cmdlet.</span></span> <span data-ttu-id="b111d-105">このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="b111d-105">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="b111d-106">リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。</span><span class="sxs-lookup"><span data-stu-id="b111d-106">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-trusted-applications"></a><span data-ttu-id="b111d-107">信頼されたアプリケーションを表示するには</span><span class="sxs-lookup"><span data-stu-id="b111d-107">To view trusted applications</span></span>

  - <span data-ttu-id="b111d-108">信頼されているすべてのアプリケーションを表示するには、Lync Server 管理シェルで次のコマンドを入力し、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="b111d-108">To view all of your trusted applications, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsConferenceDisclaimer
    
    <span data-ttu-id="b111d-109">このコマンドは、信頼されたアプリケーションごとに次のような情報を戻します。</span><span class="sxs-lookup"><span data-stu-id="b111d-109">This command returns information similar to the following for each trusted application:</span></span>
    
        Identity               : CN={5dedf4b0-a590-49b3-80cf-f16f914bbef9},CN=Application Contacts,CN=RTC
                                 Service,CN=Services,CN=Configuration,DC=litware,DC=com
        RegistrarPool          : 487279971
        HomeServer             : CN=Lc Services,CN=Microsoft,CN=co1:2,CN=Pools,CN=RTC
                                 Service,CN=Services,CN=Configuration,DC=litware,DC=com
        OwnerUrn               : urn:application:helpdesk
        SipAddress             : sip:RtcApplication-dbf5142f-2bb2-4c4f-9531-b7fea45c5000@litware.com
        DisplayName            :
        DisplayNumber          :
        LineURI                :
        PrimaryLanguage        : 0
        SecondaryLanguages     : {}
        EnterpriseVoiceEnabled : True
        ExUmEnabled            : False
        Enabled                : True
    
    <span data-ttu-id="b111d-110">詳細については、「[Get-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/Get-CsTrustedApplication)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b111d-110">For details, see [Get-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/Get-CsTrustedApplication).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

