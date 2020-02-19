---
title: 'Lync Server 2013: 会議デバイス情報の表示'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View conferencing device information
ms:assetid: 838bdbf8-8b68-4eb6-8fa3-45bfd5b0b1cd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994043(v=OCS.15)
ms:contentKeyID: 51803954
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4fd7b840e03410069c59c30e46ec22902f96ce3a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136805"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-conferencing-device-information-in-lync-server-2013"></a><span data-ttu-id="8c8c4-102">Lync Server 2013 での会議デバイス情報の表示</span><span class="sxs-lookup"><span data-stu-id="8c8c4-102">View conferencing device information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8c8c4-103">_**トピックの最終更新日:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="8c8c4-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="8c8c4-104">組織で使用するように構成されている会議デバイスに関する情報を表示するには、Windows PowerShell と、 **-Csroom room**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="8c8c4-104">You can view information about the conferencing devices configured for use in your organization by using Windows PowerShell and the **Get-CsMeetingRoom** cmdlet.</span></span> <span data-ttu-id="8c8c4-105">Lync Server 2013 管理シェルまたは Windows PowerShell のリモートセッションから、 **Get-help room**コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="8c8c4-105">Run the **Get-CsMeetingRoom** cmdlet from either the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8c8c4-106">リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を<A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>で参照してください。</span><span class="sxs-lookup"><span data-stu-id="8c8c4-106">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<span data-ttu-id="8c8c4-107">パラメーターを指定せずに**get-help**コマンドレットを使用すると、すべての会議デバイスに関する情報が戻されます。</span><span class="sxs-lookup"><span data-stu-id="8c8c4-107">If you use the **Get-CsMeetingRoom** cmdlet without any parameters, it returns information about all your conferencing devices.</span></span> <span data-ttu-id="8c8c4-108">オプションのパラメーターを使用すると、情報をフィルター処理する方法が異なります。</span><span class="sxs-lookup"><span data-stu-id="8c8c4-108">Optional parameters provide different ways for you to filter information.</span></span> <span data-ttu-id="8c8c4-109">詳細については、「 [Get-help room](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingRoom)」の「Parameters」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8c8c4-109">For details, see the Parameters section of [Get-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingRoom).</span></span>

<div>


<div>

## <a name="viewing-information-about-all-your-conferencing-devices"></a><span data-ttu-id="8c8c4-110">すべての会議デバイスに関する情報の表示</span><span class="sxs-lookup"><span data-stu-id="8c8c4-110">Viewing Information about All Your Conferencing Devices</span></span>

  - <span data-ttu-id="8c8c4-111">すべての電話会議デバイスの詳細を表示するには、Lync Server 管理シェルで次のコマンドを入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="8c8c4-111">To view details about all your conferencing devices, type the following command in the Lync Server Management Shell, and then press Enter:</span></span>
    
        Get-CsMeetingRoom
    
    <span data-ttu-id="8c8c4-112">このコマンドレットは、会議デバイスごとに次のような情報を返します。</span><span class="sxs-lookup"><span data-stu-id="8c8c4-112">This cmdlet returns information similar to the following for each conferencing device.</span></span> <span data-ttu-id="8c8c4-113">この例では、このコマンドレットを実行するときに表示される情報の一部しか表示されないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="8c8c4-113">Note that this example shows only some of the information that you’ll see when you run this cmdlet:</span></span>
    
        ContactOptionFlags                : 64
        OwnerUrn                          : urn:device:roomsystem
        OriginatorSid                     :
        SamAccountName                    : room12129
        UserPrincipalName                 : room1219@litwareinc.com
        FirstName                         : 
        LastName                          :
        WindowsEmailAddress               :
        Sid                               : S-1-5-21-2831376166-2963252556-2165051629-1257
        LineServerURI                     :
        AudioVideoDisabled                : False
        IPPBXSoftPhoneRoutingEnabled      : False
        RemoteCallControlTelephonyEnabled : False
        PrivateLine                       :
        AcpInfo                           : {}
        HostedVoiceMail                   :
        DisplayName                       : Room 1219

</div>

<div>

## <a name="viewing-information-about-a-specific-conferencing-device"></a><span data-ttu-id="8c8c4-114">特定の会議デバイスに関する情報の表示</span><span class="sxs-lookup"><span data-stu-id="8c8c4-114">Viewing Information about a Specific Conferencing Device</span></span>

  - <span data-ttu-id="8c8c4-115">特定の会議デバイスの情報を表示するには、Identity パラメーターに続けて、会議デバイス id (通常は Active Directory 表示名) を含めます。</span><span class="sxs-lookup"><span data-stu-id="8c8c4-115">To view information for a specific conferencing device, include the Identity parameter followed by the conferencing device identity (typically, the Active Directory display name).</span></span> <span data-ttu-id="8c8c4-116">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="8c8c4-116">For example:</span></span>
    
        Get-CsMeetingRoom -Identity "Room 1219"

</div>

<span data-ttu-id="8c8c4-117">詳細については、「 [get-help](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingRoom) 」コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8c8c4-117">For details, see the Help topic for the [Get-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingRoom) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

