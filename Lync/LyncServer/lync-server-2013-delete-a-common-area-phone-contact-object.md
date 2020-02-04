---
title: 'Lync Server 2013: 一般的なエリア電話の連絡先オブジェクトを削除する'
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
ms.openlocfilehash: 2a3088150c882a5ebca99318f7c85ddbddddc333
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741017"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-common-area-phone-contact-object-in-lync-server-2013"></a>Lync Server 2013 で一般的なエリア電話の連絡先オブジェクトを削除する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-20_

一般的な市外局番に関連付けられた連絡先オブジェクトを削除することができます。 たとえば、従業員 lounge から電話を削除した場合、その電話に連絡先オブジェクトを関連付ける必要はありません。 **CsCommonAreaPhone**コマンドレットを使用すると、一般的な市外局番のアカウントを削除することができます。 このコマンドレットを実行すると、 **CsCommonAreaPhone**によって返される一般的なエリアの携帯電話の一覧から電話が削除されます。 さらに、その電話に関連付けられている連絡先オブジェクトが Active Directory ドメインサービスから削除されます。

共通の市外局番を1つ、または、表示名や国番号、市外局番などの共通の市外局番を持つ携帯電話のいずれかを削除するには、 **CsCommonAreaPhone**を使用します。 このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。

<div>


<div>

## <a name="removing-a-specified-common-area-phone"></a>指定した共通の市外局番を削除する

  - 次のコマンドは、SIP アドレス sip:mainlobby@litwareinc.com を持つ一般的なエリアの電話を削除します。
    
        Remove-CsCommonAreaPhone -Identity "sip:mainlobby@litwareinc.com"

</div>

<div>

## <a name="removing-common-area-phones-based-on-their-display-name"></a>表示名に基づいて一般的なエリア電話を削除する

  - このコマンドは、表示名に "建物 14" という文字列値が含まれているすべての共通領域の電話を削除します。
    
        Get-CsCommonAreaPhone | Where-Object {$_.DisplayName -match "Building 14"} | Remove-CsCommonAreaPhone

</div>

<div>

## <a name="removing-common-area-phones-based-on-their-country-and-area-codes"></a>国と市外局番に基づいて一般的なエリア電話を削除する

  - このコマンドを実行すると、米国 (国コード 1) と市外局番425の一般的な市外局番がすべて削除されます。
    
        Get-CsCommonAreaPhone | Where-Object {$_.LineUri  -match "^tel:\+1425"} | Remove-CsCommonAreaPhone

</div>

詳細については、 [CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Remove-CsCommonAreaPhone)コマンドレットのヘルプトピックを参照してください。

</div>

<div>

## <a name="see-also"></a>関連項目


[Get-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

