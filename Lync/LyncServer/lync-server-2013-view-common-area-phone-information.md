---
title: 'Lync Server 2013: 共通領域電話の情報の表示'
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
ms.openlocfilehash: 5b3fbf748569e12e0801f727ecfc0ad6372f4af2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136815"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-common-area-phone-information-in-lync-server-2013"></a>Lync Server 2013 で共通領域電話の情報を表示する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-20_

組織で使用するために構成されている共通領域電話の情報は、 **move-cscommonareaphone**コマンドレットを使用して確認できます。 パラメーターを指定せずにこのコマンドレットを実行すると、すべての共通領域電話に関する情報が戻されます。 オプションのパラメーターを使用すると、情報をフィルター処理する方法が異なります。 たとえば、指定された組織単位 (OU) または指定した建物にあるすべての連絡先オブジェクトを含む共通領域電話をすべて返すことができます。 **Move-cscommonareaphone**パラメーターの詳細については、「 [move-cscommonareaphone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone)」を参照してください。

**Move-cscommonareaphone**を Lync Server 2013 管理シェルから実行するか、Windows PowerShell のリモートセッションから実行します。

<div>


<div>

## <a name="viewing-information-about-all-your-common-area-phones"></a>すべての共通領域電話に関する情報の表示

  - すべての共通領域電話に関する情報を表示するには、Lync Server 管理シェルで次のコマンドを入力し、Enter キーを押します。
    
        Get-CsCommonAreaPhone
    
    次のような情報が表示されることになります。
    
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

詳細については、 [move-cscommonareaphone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone)コマンドレットのヘルプトピックを参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

