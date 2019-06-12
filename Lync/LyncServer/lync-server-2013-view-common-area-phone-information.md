---
title: 'Lync Server 2013: 一般的な市外局番の情報を表示する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View common area phone information
ms:assetid: e652240c-6a3f-4be7-a083-32f24c08e655
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994081(v=OCS.15)
ms:contentKeyID: 51803992
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 900beb4f96fd71e0e6a4ded40d776f1e7d356529
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848219"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-common-area-phone-information-in-lync-server-2013"></a><span data-ttu-id="d4563-102">Lync Server 2013 で一般的な市外局番情報を表示する</span><span class="sxs-lookup"><span data-stu-id="d4563-102">View common area phone information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d4563-103">_**最終更新日:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="d4563-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="d4563-104">組織で使用できるように構成されている一般的なエリア電話に関する情報を表示するには、 **CsCommonAreaPhone**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="d4563-104">You can view information about the common area phones configured for use in your organization by using the **Get-CsCommonAreaPhone** cmdlet.</span></span> <span data-ttu-id="d4563-105">パラメーターを指定せずにこのコマンドレットを使うと、すべての共通エリア電話に関する情報が返されます。</span><span class="sxs-lookup"><span data-stu-id="d4563-105">Used without any parameters, this cmdlet returns information about all your common area phones.</span></span> <span data-ttu-id="d4563-106">オプションのパラメーターを使うと、情報をフィルター処理する方法が異なります。</span><span class="sxs-lookup"><span data-stu-id="d4563-106">Optional parameters provide different ways for you to filter information.</span></span> <span data-ttu-id="d4563-107">たとえば、指定した組織単位 (OU) 内の連絡先オブジェクト、または指定した建物内のすべての連絡先オブジェクトを持つ共通の市外電話をすべて取得できます。</span><span class="sxs-lookup"><span data-stu-id="d4563-107">For example, you can return all the common area phones that have contact objects in a specified organizational unit (OU) or all the contacts objects located in a specified building.</span></span> <span data-ttu-id="d4563-108">**CsCommonAreaPhone**パラメーターの詳細については、「 [get-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d4563-108">For details about **Get-CsCommonAreaPhone** parameters, see [Get-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone).</span></span>

<span data-ttu-id="d4563-109">**CsCommonAreaPhone**は、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行します。</span><span class="sxs-lookup"><span data-stu-id="d4563-109">Run **Get-CsCommonAreaPhone** either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


<div>

## <a name="viewing-information-about-all-your-common-area-phones"></a><span data-ttu-id="d4563-110">共通のエリア電話に関する情報を表示する</span><span class="sxs-lookup"><span data-stu-id="d4563-110">Viewing Information about All Your Common Area Phones</span></span>

  - <span data-ttu-id="d4563-111">一般的なすべての地域電話に関する情報を表示するには、Lync Server 管理シェルで次のコマンドを入力し、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="d4563-111">To view information about all your common area phones, type the following command in the Lync Server Management Shell, and then press Enter:</span></span>
    
        Get-CsCommonAreaPhone
    
    <span data-ttu-id="d4563-112">次のような情報が表示できます。</span><span class="sxs-lookup"><span data-stu-id="d4563-112">You’ll get information similar to this:</span></span>
    
        Identity           : CN=Building 14 Lobby,OU=Redmond,
                             DC=litwareinc,DC=com
        RegistrarPool      : atl-cs-001.litwareinc.com
        Enabled            : True
        SipAddress         : sip:4714e34b-9781-421d-b07a-
                             52056b5b4a56@litwareinc.com
        ClientPolicy       :
        PinPolicy          :
        VoicePolicy        :
        MobilityPolicy     :
        GroupChatPolicy    :
        ConferencingPolicy :
        LineURI            : tel:+14255550712
        DisplayNumber      : 1-425-555-0712
        DisplayName        : Building 14 Lobby
        Description        :
        ExUmEnabled        : False

</div>

<span data-ttu-id="d4563-113">詳細については、 [CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone)コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d4563-113">For details, see the Help topic for the [Get-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

