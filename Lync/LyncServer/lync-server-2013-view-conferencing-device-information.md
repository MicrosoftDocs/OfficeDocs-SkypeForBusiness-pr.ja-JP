---
title: 'Lync Server 2013: 会議デバイス情報の表示'
description: 'Lync Server 2013: 電話会議デバイス情報を表示します。'
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
ms.openlocfilehash: 9bbbdcecbc15ef59b2b9e22ffd2b28ff745d67a2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574773"
---
# <a name="view-conferencing-device-information-in-lync-server-2013"></a>Lync Server 2013 での会議デバイス情報の表示

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-20_

組織で使用するように構成されている会議デバイスに関する情報を表示するには、Windows PowerShell と、 **-Csroom room** コマンドレットを使用します。 Lync Server 2013 管理シェルまたは Windows PowerShell のリモートセッションから、 **Get-help room** コマンドレットを実行します。

<div>


> [!NOTE]  
> リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を<A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>で参照してください。



</div>

パラメーターを指定せずに **get-help** コマンドレットを使用すると、すべての会議デバイスに関する情報が戻されます。 オプションのパラメーターを使用すると、情報をフィルター処理する方法が異なります。 詳細については、「 [Get-help room](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingRoom)」の「Parameters」セクションを参照してください。

<div>


<div>

## <a name="viewing-information-about-all-your-conferencing-devices"></a>すべての会議デバイスに関する情報の表示

  - すべての電話会議デバイスの詳細を表示するには、Lync Server 管理シェルで次のコマンドを入力し、Enter キーを押します。
    
        Get-CsMeetingRoom
    
    このコマンドレットは、会議デバイスごとに次のような情報を返します。 この例では、このコマンドレットを実行するときに表示される情報の一部しか表示されないことに注意してください。
    
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

## <a name="viewing-information-about-a-specific-conferencing-device"></a>特定の会議デバイスに関する情報の表示

  - 特定の会議デバイスの情報を表示するには、Identity パラメーターに続けて、会議デバイス id (通常は Active Directory 表示名) を含めます。 以下に例を示します。
    
        Get-CsMeetingRoom -Identity "Room 1219"

</div>

詳細については、「 [get-help](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingRoom) 」コマンドレットのヘルプトピックを参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

