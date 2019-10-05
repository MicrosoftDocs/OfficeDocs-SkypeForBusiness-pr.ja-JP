---
title: 'Lync Server 2013: Exchange UM コマンドレット'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Exchange UM cmdlets
ms:assetid: 32922b9f-590d-41cc-ba57-9ed5f1caa814
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415642(v=OCS.15)
ms:contentKeyID: 48183786
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e4c530095b69e8aadd07ad37e3fbe4a46b361a5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833189"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="exchange-um-cmdlets-in-lync-server-2013"></a><span data-ttu-id="1d844-102">Lync Server 2013 の Exchange UM コマンドレット</span><span class="sxs-lookup"><span data-stu-id="1d844-102">Hosted Exchange UM integration architecture in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1d844-103">_**トピックの最終更新日:** 2012-06-26_</span><span class="sxs-lookup"><span data-stu-id="1d844-103">_**Topic Last Modified:** 2012-06-26_</span></span>

<span data-ttu-id="1d844-104">Microsoft Lync Server 2013 は、Exchange ユニファイド メッセージング (UM) と連携して、ホストされたボイス メールの自動応答およびサブスクライバー アクセスを実装します。</span><span class="sxs-lookup"><span data-stu-id="1d844-104">Microsoft Lync Server 2013 works together with Exchange Unified Messaging (UM) to implement Auto Attendant and Subscriber Access for hosted voice mail.</span></span> <span data-ttu-id="1d844-105">これらの機能は、Lync Server 管理シェルのコマンドレットを使用して管理できます。</span><span class="sxs-lookup"><span data-stu-id="1d844-105">These features can be managed through cmdlets in the Lync Server Management Shell.</span></span>

<div>

## <a name="exchange-um-cmdlets"></a><span data-ttu-id="1d844-106">Exchange UM コマンドレット</span><span class="sxs-lookup"><span data-stu-id="1d844-106">Exchange UM Cmdlets</span></span>

<span data-ttu-id="1d844-107">次のコマンドレットを使用して、Exchange UM を管理できます。</span><span class="sxs-lookup"><span data-stu-id="1d844-107">The following cmdlets can be used to manage Response Group application.</span></span>

<span data-ttu-id="1d844-108">**Exchange UM**</span><span class="sxs-lookup"><span data-stu-id="1d844-108">**Exchange UM**</span></span>

  - <span></span>  
    <span data-ttu-id="1d844-109">[Get-CsExUmContact](https://technet.microsoft.com/en-us/library/Gg412725(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1d844-109">[Get-CsExUmContact](https://technet.microsoft.com/en-us/library/Gg412725(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="1d844-110">[Move-CsExUmContact](https://technet.microsoft.com/en-us/library/Gg425842(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1d844-110">[Move-CsExUmContact](https://technet.microsoft.com/en-us/library/Gg425842(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="1d844-111">[New-CsExUmContact](https://technet.microsoft.com/en-us/library/Gg398139(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1d844-111">[New-CsExUmContact](https://technet.microsoft.com/en-us/library/Gg398139(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="1d844-112">[Remove-CsExUmContact](rehttps://technet.microsoft.com/en-us/library/Gg425842(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1d844-112">[Remove-CsExUmContact](rehttps://technet.microsoft.com/en-us/library/Gg425842(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="1d844-113">[Set-CsExUmContact](https://technet.microsoft.com/en-us/library/Gg412944(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1d844-113">[Set-CsExUmContact](https://technet.microsoft.com/en-us/library/Gg412944(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="1d844-114">[Test-CsExStorageConnectivity](https://technet.microsoft.com/en-us/library/JJ204740(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1d844-114">[Test-CsExStorageConnectivity](https://technet.microsoft.com/en-us/library/JJ204740(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="1d844-115">[Test-CsExStorageNotification](https://technet.microsoft.com/en-us/library/JJ205331(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1d844-115">[Test-CsExStorageNotification](https://technet.microsoft.com/en-us/library/JJ205331(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="1d844-116">[Test-CsExUMConnectivity](https://technet.microsoft.com/en-us/library/JJ204784(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1d844-116">[Test-CsExUMConnectivity](https://technet.microsoft.com/en-us/library/JJ204784(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="1d844-117">[Test-CsExUMVoiceMail](https://technet.microsoft.com/en-us/library/JJ205058(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1d844-117">[Test-CsExUMVoiceMail](https://technet.microsoft.com/en-us/library/JJ205058(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="1d844-118">[Get-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/Gg398348(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1d844-118">[Get-CSHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/Gg398348(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="1d844-119">[Grant-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/Gg412829(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1d844-119">[Grant-CSHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/Gg412829(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="1d844-120">[New-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/Gg398653(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1d844-120">[New-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/Gg398653(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="1d844-121">[Remove-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/Gg398211(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1d844-121">[Remove-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/Gg398211(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="1d844-122">[Set-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/Gg412722(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1d844-122">[Set-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/Gg412722(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="1d844-123">[Get-CsVoicemailReroutingConfiguration](https://technet.microsoft.com/en-us/library/Gg425732(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1d844-123">[Get-CSVoicemailReroutingConfiguration](https://technet.microsoft.com/en-us/library/Gg425732(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="1d844-124">[New-CsVoicemailReroutingConfiguration](https://technet.microsoft.com/en-us/library/Gg425849(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1d844-124">[New-CsVoicemailReroutingConfiguration](https://technet.microsoft.com/en-us/library/Gg425849(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="1d844-125">[Remove-CsVoicemailReroutingConfiguration](https://technet.microsoft.com/en-us/library/Gg398573(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1d844-125">[Remove-CsVoicemailReroutingConfiguration](https://technet.microsoft.com/en-us/library/Gg398573(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="1d844-126">[Set-CsVoicemailReroutingConfiguration](https://technet.microsoft.com/en-us/library/Gg412948(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1d844-126">[Set-CsVoicemailReroutingConfiguration](https://technet.microsoft.com/en-us/library/Gg412948(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1d844-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="1d844-127">See Also</span></span>


[<span data-ttu-id="1d844-128">Lync Server PowerShell ブログ</span><span class="sxs-lookup"><span data-stu-id="1d844-128">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

