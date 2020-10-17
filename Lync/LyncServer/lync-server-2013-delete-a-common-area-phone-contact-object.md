---
title: 'Lync Server 2013: 共通領域電話の連絡先オブジェクトを削除する'
description: 'Lync Server 2013: 共通領域電話の連絡先オブジェクトを削除します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a common area phone Contact object
ms:assetid: f4c139dc-f07c-4c75-9345-e291aea41173
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994087(v=OCS.15)
ms:contentKeyID: 51803999
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e918f7a46269f70577f28b2c3e55297959430721
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566603"
---
# <a name="delete-a-common-area-phone-contact-object-in-lync-server-2013"></a>Lync Server 2013 で共通領域電話の連絡先オブジェクトを削除する

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-20_

共通領域電話に関連付けられた連絡先オブジェクトを削除することができます。 たとえば、従業員 lounge から電話を削除した場合、その電話に連絡先オブジェクトが関連付けられている必要はありません。 **Move-cscommonareaphone**コマンドレットを使用すると、共通領域電話のアカウントを削除することができます。 このコマンドレットを実行すると、 **move-cscommonareaphone**によって返される共通領域電話の一覧から電話が削除されます。 さらに、その電話に関連付けられている連絡先オブジェクトが Active Directory ドメインサービスから削除されます。

**Move-cscommonareaphone**を使用して、1つの共通領域電話または、表示名、国番号、市外局番などの共通要素を持つすべての共通領域電話を削除します。 このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモートセッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。

<div>


<div>

## <a name="removing-a-specified-common-area-phone"></a>指定された共通領域電話の削除

  - 次のコマンドは、SIP アドレス sip:mainlobby@litwareinc.com を使用して共通領域電話を削除します。
    
        Remove-CsCommonAreaPhone -Identity "sip:mainlobby@litwareinc.com"

</div>

<div>

## <a name="removing-common-area-phones-based-on-their-display-name"></a>表示名に基づいて共通領域電話を削除する

  - このコマンドは、表示名に文字列値 "ビルディング 14" が含まれているすべての共通領域電話を削除します。
    
        Get-CsCommonAreaPhone | Where-Object {$_.DisplayName -match "Building 14"} | Remove-CsCommonAreaPhone

</div>

<div>

## <a name="removing-common-area-phones-based-on-their-country-and-area-codes"></a>国およびエリアコードに基づいて共通領域電話を削除する

  - このコマンドは、米国 (国コード 1) と市外局番425の共通領域電話をすべて削除します。
    
        Get-CsCommonAreaPhone | Where-Object {$_.LineUri  -match "^tel:\+1425"} | Remove-CsCommonAreaPhone

</div>

詳細については、 [move-cscommonareaphone](https://docs.microsoft.com/powershell/module/skype/Remove-CsCommonAreaPhone) コマンドレットのヘルプトピックを参照してください。

</div>

<div>

## <a name="see-also"></a>関連項目


[Move-cscommonareaphone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

