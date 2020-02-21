---
title: 'Lync Server 2013: 会議デバイスの連絡先オブジェクトを作成または変更する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a conferencing device Contact object
ms:assetid: 62ed64be-379c-417d-9453-511881cf5604
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994035(v=OCS.15)
ms:contentKeyID: 51803945
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 74808a2deae4f7fa52e1a48fcbd415205eca93cf
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180084"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-conferencing-device-contact-object-in-lync-server-2013"></a><span data-ttu-id="9e4fc-102">Lync Server 2013 で会議デバイスの連絡先オブジェクトを作成または変更する</span><span class="sxs-lookup"><span data-stu-id="9e4fc-102">Create or modify a conferencing device Contact object in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9e4fc-103">_**トピックの最終更新日:** 2013-10-02_</span><span class="sxs-lookup"><span data-stu-id="9e4fc-103">_**Topic Last Modified:** 2013-10-02_</span></span>

<span data-ttu-id="9e4fc-104">会議室オブジェクトを作成するには、まず、デバイスを表す Active Directory ユーザーアカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="9e4fc-104">To create a conferencing room object, first create an Active Directory user account to represent the device.</span></span> <span data-ttu-id="9e4fc-105">その後、この**コマンドレットを使用して**、そのアカウントを会議デバイスとして機能できるようにします。</span><span class="sxs-lookup"><span data-stu-id="9e4fc-105">Then, use the **Enable-CsMeetingRoom** cmdlet to enable that account to function as a conferencing device.</span></span> <span data-ttu-id="9e4fc-106">既存の会議デバイスのプロパティを変更する必要がある場合は、コマンドレットの**設定**を使用します。</span><span class="sxs-lookup"><span data-stu-id="9e4fc-106">If you need to change the properties of an existing conferencing device, use the **Set-CsMeetingRoom** cmdlet.</span></span>

<span data-ttu-id="9e4fc-107">これらのコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="9e4fc-107">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9e4fc-108">リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を<A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>で参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e4fc-108">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>


<div>

## <a name="creating-a-conferencing-device"></a><span data-ttu-id="9e4fc-109">会議デバイスの作成</span><span class="sxs-lookup"><span data-stu-id="9e4fc-109">Creating a Conferencing Device</span></span>

  - <span data-ttu-id="9e4fc-110">新しい会議デバイスを表す Active Directory ユーザーアカウントを作成した後、 **enable-csコンファレンスルーム**コマンドレットを使用して有効にします。</span><span class="sxs-lookup"><span data-stu-id="9e4fc-110">After you create the Active Directory user account that represents the new conferencing device, enable it by using the **Enable-CsMeetingRoom** cmdlet.</span></span> <span data-ttu-id="9e4fc-111">会議デバイス id、b) 会議室のアカウントが所属するレジストラープール、およびそのアカウントに割り当てる SIP アドレスは、必ず含めるようにしてください。</span><span class="sxs-lookup"><span data-stu-id="9e4fc-111">Be sure to include a) the conferencing device identity, b) the registrar pool where the room account will be homed, and c) the SIP address to be assigned to that account.</span></span> <span data-ttu-id="9e4fc-112">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="9e4fc-112">For example:</span></span>
    
        Enable-CsMeetingRoom -Identity "Redmond Conferencing device" -RegistrarPool "atl-cs-001.litwareinc.com" -SipAddress "sip:RedmondMeetingRoom@litwareinc.com"

</div>

<div>

## <a name="modifying-a-conferencing-device"></a><span data-ttu-id="9e4fc-113">会議デバイスの変更</span><span class="sxs-lookup"><span data-stu-id="9e4fc-113">Modifying a Conferencing Device</span></span>

  - <span data-ttu-id="9e4fc-114">既存の会議デバイスのプロパティ値を変更するには、コマンドレットの**設定**を使用します。</span><span class="sxs-lookup"><span data-stu-id="9e4fc-114">To modify the property values of an existing conferencing device, use the **Set-CsMeetingRoom** cmdlet.</span></span> <span data-ttu-id="9e4fc-115">たとえば、次のコマンドを実行すると、会議デバイスに関連付けられた電話番号 (LineUri) が更新されます。</span><span class="sxs-lookup"><span data-stu-id="9e4fc-115">For example, the following command updates the phone number (LineUri) associated with a conferencing device:</span></span>
    
        Set-CsMeetingRoom -Identity "Redmond Conferencing device" -LineUri "tel:+12065551219"

</div>

<span data-ttu-id="9e4fc-116">詳細については、を参照してください。[このコマンドレット](https://docs.microsoft.com/powershell/module/skype/Enable-CsMeetingRoom)[のヘルプ](https://docs.microsoft.com/powershell/module/skype/Set-CsMeetingRoom)トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e4fc-116">For details, see the Help topics for the [Enable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Enable-CsMeetingRoom) cmdlet and the [Set-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Set-CsMeetingRoom) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

