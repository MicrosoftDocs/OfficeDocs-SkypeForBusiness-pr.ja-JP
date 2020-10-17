---
title: 'Lync Server 2013: 共通領域電話の情報の表示'
description: 'Lync Server 2013: 共通領域電話の情報を表示します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View common area phone information
ms:assetid: e652240c-6a3f-4be7-a083-32f24c08e655
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994081(v=OCS.15)
ms:contentKeyID: 51803992
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e4debe9a76118ac0bf1ca711426ce5487009a053
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572473"
---
# <a name="view-common-area-phone-information-in-lync-server-2013"></a><span data-ttu-id="b48e6-103">Lync Server 2013 で共通領域電話の情報を表示する</span><span class="sxs-lookup"><span data-stu-id="b48e6-103">View common area phone information in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b48e6-104">_**トピックの最終更新日:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="b48e6-104">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="b48e6-105">組織で使用するために構成されている共通領域電話の情報は、 **move-cscommonareaphone** コマンドレットを使用して確認できます。</span><span class="sxs-lookup"><span data-stu-id="b48e6-105">You can view information about the common area phones configured for use in your organization by using the **Get-CsCommonAreaPhone** cmdlet.</span></span> <span data-ttu-id="b48e6-106">パラメーターを指定せずにこのコマンドレットを実行すると、すべての共通領域電話に関する情報が戻されます。</span><span class="sxs-lookup"><span data-stu-id="b48e6-106">Used without any parameters, this cmdlet returns information about all your common area phones.</span></span> <span data-ttu-id="b48e6-107">オプションのパラメーターを使用すると、情報をフィルター処理する方法が異なります。</span><span class="sxs-lookup"><span data-stu-id="b48e6-107">Optional parameters provide different ways for you to filter information.</span></span> <span data-ttu-id="b48e6-108">たとえば、指定された組織単位 (OU) または指定した建物にあるすべての連絡先オブジェクトを含む共通領域電話をすべて返すことができます。</span><span class="sxs-lookup"><span data-stu-id="b48e6-108">For example, you can return all the common area phones that have contact objects in a specified organizational unit (OU) or all the contacts objects located in a specified building.</span></span> <span data-ttu-id="b48e6-109">**Move-cscommonareaphone**パラメーターの詳細については、「 [move-cscommonareaphone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b48e6-109">For details about **Get-CsCommonAreaPhone** parameters, see [Get-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone).</span></span>

<span data-ttu-id="b48e6-110">**Move-cscommonareaphone**を Lync Server 2013 管理シェルから実行するか、Windows PowerShell のリモートセッションから実行します。</span><span class="sxs-lookup"><span data-stu-id="b48e6-110">Run **Get-CsCommonAreaPhone** either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


<div>

## <a name="viewing-information-about-all-your-common-area-phones"></a><span data-ttu-id="b48e6-111">すべての共通領域電話に関する情報の表示</span><span class="sxs-lookup"><span data-stu-id="b48e6-111">Viewing Information about All Your Common Area Phones</span></span>

  - <span data-ttu-id="b48e6-112">すべての共通領域電話に関する情報を表示するには、Lync Server 管理シェルで次のコマンドを入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="b48e6-112">To view information about all your common area phones, type the following command in the Lync Server Management Shell, and then press Enter:</span></span>
    
        Get-CsCommonAreaPhone
    
    <span data-ttu-id="b48e6-113">次のような情報が表示されることになります。</span><span class="sxs-lookup"><span data-stu-id="b48e6-113">You’ll get information similar to this:</span></span>
    
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

<span data-ttu-id="b48e6-114">詳細については、 [move-cscommonareaphone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone) コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b48e6-114">For details, see the Help topic for the [Get-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

