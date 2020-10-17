---
title: 'Lync Server 2013: ユーザーのグループ通話ピックアップを無効にする'
description: 'Lync Server 2013: ユーザーのグループ通話ピックアップを無効にします。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disable Group Call Pickup for users
ms:assetid: 91b06f9e-2840-45a2-bbb3-6a29179b9a9f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945638(v=OCS.15)
ms:contentKeyID: 51541492
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b3f5b4542cf7bb8ea5be524d2695701979ec2987
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568193"
---
# <a name="disable-group-call-pickup-for-users-in-lync-server-2013"></a>Lync Server 2013 でユーザーのグループ通話ピックアップを無効にする

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-01-30_

ユーザーのグループ通話ピックアップを無効にするには、次の手順を使用します。

<div>


> [!NOTE]  
> ユーザーのグループ通話ピックアップを無効にしても、ユーザーに割り当てられていた通話ピックアップグループ番号は保持されません。 その後、そのユーザーのグループ通話ピックアップを再度有効にする場合は、もう一度、/enablegrouppickup パラメーターを使用して、通話ピックアップグループ番号を割り当てる必要があります。



</div>

<div>

## <a name="to-disable-group-call-pickup-for-a-user"></a>ユーザーのグループ通話ピックアップを無効にするには

1.  SEFAUtil ツールをインストールしたコンピューターに管理者権限でログオンします。

2.  コマンド ラインで、次のコマンドを実行します。
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /disablegrouppickup
    
    次に例を示します。
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /disablegrouppickup

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でグループ通話ピックアップ番号をユーザーに割り当てる](lync-server-2013-assign-group-call-pickup-numbers-to-users.md)  
[Lync Server 2013 でユーザーのグループ通話ピックアップを有効にする](lync-server-2013-enable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

