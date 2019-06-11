---
title: 'Lync Server 2013: グループ通話のピックアップをユーザーに対して無効にする'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Disable Group Call Pickup for users
ms:assetid: 91b06f9e-2840-45a2-bbb3-6a29179b9a9f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945638(v=OCS.15)
ms:contentKeyID: 51541492
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 76b7e0d17b91accdab0f1590d9fc505dec42f430
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833385"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disable-group-call-pickup-for-users-in-lync-server-2013"></a>Lync Server 2013 のユーザーに対してグループ通話のピックアップを無効にする

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-01-30_

次の手順を使用して、ユーザーのグループ通話のピックアップを無効にします。

<div>


> [!NOTE]  
> グループ通話のピックアップをユーザーに対して無効にしても、そのユーザーに割り当てられていた通話ピックアップグループ番号は保持されません。 そのユーザに対してグループ通話のピックアップを再び有効にする必要がある場合は、/enablegrouppickup パラメーターを使用して、もう一度通話ピックアップグループ番号を割り当てる必要があります。



</div>

<div>

## <a name="to-disable-group-call-pickup-for-a-user"></a>グループ通話のピックアップをユーザーに対して無効にするには

1.  SEFAUtil ツールをインストールしたコンピューターに管理者権限でログオンします。

2.  コマンド ラインで、次のコマンドを実行します。
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /disablegrouppickup
    
    例:
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /disablegrouppickup

</div>

<div>

## <a name="see-also"></a>関連項目


[グループ通話の集配番号を Lync Server 2013 のユーザーに割り当てる](lync-server-2013-assign-group-call-pickup-numbers-to-users.md)  
[Lync Server 2013 のユーザーに対してグループ通話のピックアップを有効にする](lync-server-2013-enable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

