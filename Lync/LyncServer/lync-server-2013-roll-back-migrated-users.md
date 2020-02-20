---
title: 'Lync Server 2013: 移行されたユーザーのロールバック'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Roll back migrated users
ms:assetid: bfabaf0b-9a42-4057-b729-a7ab9eee8c72
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205224(v=OCS.15)
ms:contentKeyID: 48185286
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dbc2c46b462ec50c1f5796a9a6a03cd39f7b44dc
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144553"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="roll-back-migrated-users-in-lync-server-2013"></a>Lync Server 2013 で移行されたユーザーのロールバック

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-07_

統合連絡先ストア機能をロールバックする必要がある場合は、ユーザーを Exchange 2010 または Lync Server 2010 に戻した場合にのみ、連絡先をロールバックします。 ロールバックするには、ユーザーのポリシーを無効にしてから、 **invoke-csucsrollback**コマンドレットを実行します。 **Invoke-csucsrollback**のみを実行するだけでは、ポリシーが無効になっていない場合に、統合連絡先ストアの移行が再び開始されるので、永続的なロールバックを保証するだけでは十分ではありません。 たとえば、Exchange 2013 が Exchange 2010 にロールバックされたためにユーザーがロールバックされた場合に、ユーザーのメールボックスが Exchange 2013 に移動されると、統合連絡先ストアの移行は、統合された後7日後に開始されます (統合連絡先ストア)は、ユーザーサービスポリシーのユーザーに対して引き続き有効になっています。

<div>


> [!IMPORTANT]  
> 次の状況では、<STRONG>移動-csuser</STRONG>コマンドレットによって、ユーザーの連絡先ストアが Exchange 2013 から Lync Server 2013 に自動的にロールバックされます。 
> <UL>
> <LI>
> <P>ユーザーが Lync Server 2013 から Lync Server 2010 に移動されたとき。</P>
> <LI>
> <P>ユーザーが Lync Online から社内の Lync Server 2013 に移動された場合や、その逆の場合など、ユーザーがクロスプレミスで移行されるとき。</P></LI></UL>



</div>

<div>


> [!IMPORTANT]  
> バックアップ データベースから統合連絡先ストアをインポートするときに、統合連絡先ストアのモードがエクスポートとインポートの間で変更されると、統合連絡先ストアのデータとユーザー データが破損する可能性があります。たとえば次のような例が挙げられます。 
> <UL>
> <LI>
> <P>ユーザーの連絡先が Exchange 2013 に移行される前に連絡先リストをエクスポートした後、移行後に同じデータをインポートすると、統合連絡先ストアのデータと連絡先リストが破損します。</P>
> <LI>
> <P>ユーザーを Exchange 2013 に移行した後に userdata をエクスポートする場合は、移行をロールバックし、何らかの理由で移行後にデータをインポートした後、統合連絡先ストアのデータと連絡先リストが破損します。</P></LI></UL>



</div>

<div>


> [!IMPORTANT]  
> Exchange 2013 から exchange 2010 に Exchange メールボックスを移動する前に、Exchange 管理者は、まず lync server ユーザーの連絡先を Exchange 2013 から Lync Server にロールバックしたことを確認する必要があります。 統合連絡先ストアの連絡先を Lync Server にロールバックするには、このセクションで後述する「統合連絡先ストアの連絡先を Exchange 2013 から Lync Server 2013 にロールバックするには」の手順を参照してください。



</div>

次の手順では、ユーザーの連絡先をロールバックする方法を説明します。 **Move-csuser**コマンドレットを使用して lync server 2013 と lync server 2010 間でユーザーを移動する場合は、lync server の2013から Lync 2010 server へのユーザーの移動時に、ユーザーコマンドレットが自動的に unifed 連絡先ストアをロール**バックするの**で、次の手順を省略できます。 **Move-CsUser**は、統合連絡先ストアポリシーを無効にしないので、ユーザーが Lync Server 2013 に戻った場合、統合連絡先ストアへの移行は繰り返されます。

<div>

## <a name="to-roll-back-user-contacts-from-lync-server-2013-to-lync-server-2010"></a>Lync Server 2013 から Lync Server 2010 にユーザーの連絡先をロールバックするには

1.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

2.  ロールバック後にユーザーの再移行が行われないように、ロールバックするユーザーに対して統合連絡先ストアを無効にします (この手順は、将来ユーザーが再移行されないようにしたい場合にだけ実行します)。統合連絡先ストアを個別のユーザーに対して無効にするには、コマンドラインで、次のように入力します。
    
        Set-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $False
    
    次に例を示します。
    
        Set-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $False

3.  Lync server 2013 から lync Server 2010 にユーザーを移動する前に、Lync Server で指定されたユーザーの友人リストをロールバックします。
    
    <div>
    

    > [!IMPORTANT]  
    > このステップを省略すると、バディ リストが失われます。

    
    </div>

4.  指定したユーザーをロールバックします。コマンドラインで、次のように入力します。
    
        Invoke-CsUcsRollback -Identity "<user display name>"
    
    次に例を示します。
    
        Invoke-CsUcsRollback -Identity "Ken Myer"
    
    <div>
    

    > [!IMPORTANT]  
    > –Force オプションを使用して強制的にロールバックすることはお勧めしません。このオプションを使用すると、ユーザーの連絡先が失われます。

    
    </div>

</div>

<div>

## <a name="to-roll-back-unified-contact-store-contacts-from-exchange-2013-to-lync-server-2013"></a>統合連絡先ストアの連絡先を Exchange 2013 から Lync Server 2013 にロールバックするには

1.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

2.  ロールバック後にユーザーの再移行が行われないように、ロールバックするユーザーに対して統合連絡先ストアを無効にします。統合連絡先ストアを個別のユーザーに対して無効にするには、コマンドラインで、次のように入力します。
    
        Set-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $False
    
    例:
    
        Set-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $False

3.  指定したユーザーをロールバックします。コマンドラインで、次のように入力します。
    
        Invoke-CsUcsRollback -Identity "<user display name>"
    
    次に例を示します。
    
        Invoke-CsUcsRollback -Identity "Ken Myer"
    
    <div>
    

    > [!IMPORTANT]  
    > 最初に、Lync Server ユーザーをロールバックしてから、Exchange 2013 メールボックスを移動する必要があります。 Exchange 管理者は、Lync Server のロールバックが完了するまで Exchange のロールバックをブロックされます。 –Force オプションを使用して強制的にロールバックすることはお勧めしません。 このオプションを使用すると、ユーザーの連絡先が失われます。

    
    </div>

4.  ユーザーを Lync Server にロールバックすると、exchange 管理者は exchange 2013 から exchange 2010 に Exchange ユーザーをロールバックすることができます。

</div>

</div>

<span> </span>

</div>

</div>

</div>

