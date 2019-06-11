---
title: 'Lync Server 2013: 会議デバイス情報を表示する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View conferencing device information
ms:assetid: 838bdbf8-8b68-4eb6-8fa3-45bfd5b0b1cd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994043(v=OCS.15)
ms:contentKeyID: 51803954
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b4b40e0ee28f13aa6be52009b750258c5cdadffe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848213"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-conferencing-device-information-in-lync-server-2013"></a>Lync Server 2013 で会議デバイス情報を表示する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-20_

組織で使用できるように構成されている会議デバイスについての情報を表示するには、Windows PowerShell を使用するか、または**Csroom room**コマンドレットを使用します。 Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから、 **Csroom room**コマンドレットを実行します。

<div>


> [!NOTE]  
> リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、「Lync Server Windows PowerShell のブログ記事」を参照してください<A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>。「リモート PowerShell を使用して Microsoft Lync Server 2010 を管理する」を参照してください。



</div>

パラメーターを指定せずに、 **Csroom room**コマンドレットを使用すると、すべての会議デバイスについての情報が返されます。 オプションのパラメーターを使うと、情報をフィルター処理する方法が異なります。 詳細については、「 [Csroom 会議室](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingRoom)」の「パラメーター」セクションを参照してください。

<div>


<div>

## <a name="viewing-information-about-all-your-conferencing-devices"></a>すべての会議デバイスに関する情報を表示する

  - すべての会議デバイスの詳細を表示するには、Lync Server 管理シェルで次のコマンドを入力し、enter キーを押します。
    
        Get-CsMeetingRoom
    
    このコマンドレットは、会議デバイスごとに次のような情報を返します。 この例では、このコマンドレットを実行したときに表示されるいくつかの情報のみを示しています。
    
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

## <a name="viewing-information-about-a-specific-conferencing-device"></a>特定の会議デバイスに関する情報を表示する

  - 特定の会議デバイスの情報を表示するには、Id パラメーターに続けて会議デバイス id (通常は Active Directory 表示名) を含めます。 次に例を示します。
    
        Get-CsMeetingRoom -Identity "Room 1219"

</div>

詳細については、「 [Csroom room room](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingRoom) 」コマンドレットのヘルプトピックを参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

