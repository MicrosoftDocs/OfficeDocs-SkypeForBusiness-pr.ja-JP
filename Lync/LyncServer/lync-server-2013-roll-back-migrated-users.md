---
title: 'Lync Server 2013: 移行したユーザーのロールバック'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Roll back migrated users
ms:assetid: bfabaf0b-9a42-4057-b729-a7ab9eee8c72
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205224(v=OCS.15)
ms:contentKeyID: 48185286
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 57462cee6c4996f0beb51290f8382a1736d3e635
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822441"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="roll-back-migrated-users-in-lync-server-2013"></a>Lync Server 2013 での移行したユーザーのロールバック

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-07_

ユニファイド連絡先ストアの機能をロールバックする必要がある場合は、ユーザーを Exchange 2010 または Lync Server 2010 に戻す場合にのみ、連絡先をロールバックします。 ロールバックするには、ユーザーのポリシーを無効にしてから、 **CsUcsRollback**コマンドレットを実行します。 **CsUcsRollback**のみを実行するだけでは、ポリシーが無効になっている場合に、統合された連絡先ストアの移行が再び開始されるため、永続的なロールバックを確実に行うことはできません。 たとえば、exchange 2013 が Exchange 2010 にロールバックされたためにユーザーがロールバックされた場合、ユーザーのメールボックスは Exchange 2013 に移動されます。統合連絡先ストアの移行は、統合連絡先ストアの場合、ロールバック後7日後に開始されます。は、ユーザーサービスポリシーのユーザーに対してまだ有効になっています。

<div>


> [!IMPORTANT]  
> <STRONG>ムーブグループのユーザー</STRONG>コマンドレットは、次のような場合に、ユーザーの連絡先ストアを Exchange 2013 から Lync Server 2013 に自動的にロールバックします。 
> <UL>
> <LI>
> <P>ユーザーが Lync Server 2013 から Lync Server 2010 に移動された場合。</P>
> <LI>
> <P>ユーザーが Lync Online からオンプレミスの Lync Server 2013 に移行される場合、またはその逆の場合。</P></LI></UL>



</div>

<div>


> [!IMPORTANT]  
> バックアップ データベースから統合連絡先ストアをインポートするときに、統合連絡先ストアのモードがエクスポートとインポートの間で変更されると、統合連絡先ストアのデータとユーザー データが破損する可能性があります。たとえば次のような例が挙げられます。 
> <UL>
> <LI>
> <P>ユーザーの連絡先が Exchange 2013 に移行される前に連絡先リストをエクスポートした後、移行後に同じデータをインポートすると、統合連絡先ストアのデータと連絡先リストが破損します。</P>
> <LI>
> <P>Exchange 2013 にユーザーを移行した後で userdata をエクスポートする場合は、移行をロールバックし、何らかの理由で移行後にデータをインポートすると、統合連絡先ストアのデータと連絡先リストが破損します。</P></LI></UL>



</div>

<div>


> [!IMPORTANT]  
> Exchange のメールボックスを exchange 2013 から Exchange 2010 に移動する前に、Exchange 管理者が、lync server のユーザーの連絡先を Exchange 2013 から Lync Server にロールバックしていることを確認する必要があります。 ユニファイド連絡先ストアの連絡先を Lync Server にロールバックするには、このセクションの後半の「ユニファイド連絡先ストアの連絡先を Exchange 2013 から Lync Server 2013 にロールバックする方法」を参照してください。



</div>

次の手順では、ユーザーの連絡先をロールバックする方法を説明します。 ユーザーコマンドレットを**** 使用して lync server 2013 と lync server 2010 の間でユーザーを移動する場合は、ユーザーが lync server 2013 から lync にユーザーを移行するときに、ユーザーの**移動**によって unifed の連絡先ストアが自動的にロールバックされるため、次の手順をスキップできます。サーバー2010。 **Move-CsUser**はユニファイド連絡先ストアポリシーを無効にしないため、ユーザーが Lync Server 2013 に戻ると、統合連絡先ストアへの移行が繰り返されます。

<div>

## <a name="to-roll-back-user-contacts-from-lync-server-2013-to-lync-server-2010"></a>Lync Server 2013 から Lync Server 2010 にユーザーの連絡先をロールバックするには

1.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

2.  ロールバックの後にユーザーが再移行しないように、統合連絡先ストアを無効にしてロールバックします。 (この手順は、ユーザーが今後 remigrate しないようにする場合にのみ実行してください。)個々のユーザーに対してユニファイド連絡先ストアを無効にするには、コマンドラインで次のように入力します。
    
        Set-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $False
    
    次に例を示します。
    
        Set-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $False

3.  Lync server 2013 から Lync Server 2010 にユーザーを移動する前に、Lync Server で指定したユーザーの友人リストをロールバックします。
    
    <div>
    

    > [!IMPORTANT]  
    > この手順を省略すると、友人リストは失われます。

    
    </div>

4.  指定したユーザーをロールバックします。 コマンドラインで、次のように入力します。
    
        Invoke-CsUcsRollback -Identity "<user display name>"
    
    例:
    
        Invoke-CsUcsRollback -Identity "Ken Myer"
    
    <div>
    

    > [!IMPORTANT]  
    > ロールバックを強制するには、– Force オプションを使用することはお勧めしません。 このオプションを使用すると、ユーザーの連絡先が失われます。

    
    </div>

</div>

<div>

## <a name="to-roll-back-unified-contact-store-contacts-from-exchange-2013-to-lync-server-2013"></a>統合連絡先ストアの連絡先を Exchange 2013 から Lync Server 2013 にロールバックするには

1.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

2.  ロールバックの後にユーザーが再移行しないように、統合連絡先ストアを無効にしてロールバックします。 個々のユーザーに対してユニファイド連絡先ストアを無効にするには、コマンドラインで次のように入力します。
    
        Set-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $False
    
    次に例を示します。
    
        Set-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $False

3.  指定したユーザーをロールバックします。 コマンドラインで、次のように入力します。
    
        Invoke-CsUcsRollback -Identity "<user display name>"
    
    例:
    
        Invoke-CsUcsRollback -Identity "Ken Myer"
    
    <div>
    

    > [!IMPORTANT]  
    > まず、Lync Server ユーザーをロールバックして、Exchange 2013 メールボックスを移動する必要があります。 Exchange 管理者は、Lync Server のロールバックが完了するまで、Exchange のロールバックがブロックされます。 ロールバックを強制するには、– Force オプションを使用することはお勧めしません。 このオプションを使用すると、ユーザーの連絡先が失われます。

    
    </div>

4.  ユーザーを Lync Server にロールバックすると、exchange 管理者は exchange 2013 から exchange 2010 に Exchange ユーザーをロールバックすることができます。

</div>

</div>

<span> </span>

</div>

</div>

</div>

