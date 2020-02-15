---
title: 'Lync Server 2013: ユーザーのグループ通話ピックアップを有効にする'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Group Call Pickup for users
ms:assetid: 20ec5f41-6ba2-4156-82ed-b91d05b62a6d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945620(v=OCS.15)
ms:contentKeyID: 51541457
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a7e744f42368cd02b197533b84352f8f0477d848
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42033766"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-group-call-pickup-for-users-in-lync-server-2013"></a>Lync Server 2013 でユーザーのグループ通話ピックアップを有効にする

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-01-30_

SEFAUtil リソースキットツールを使用して、ユーザーのグループ通話ピックアップを有効にします。 グループ通話ピックアップを有効にするには、コールパークオービットテーブルで種類が GroupPickup のグループ番号がユーザーに割り当てられている必要があります。 SEFAUtil を実行するときに、/enablegrouppickup パラメーターを使用して、通話ピックアップグループ番号を割り当て、グループ通話ピックアップを同時に有効にします。

<div>

## <a name="to-enable-group-call-pickup-for-a-user"></a>ユーザーのグループ通話ピックアップを有効にするには

1.  SEFAUtil ツールをインストールしたコンピューターに管理者権限でログオンします。

2.  コマンド ラインで、次のコマンドを実行します。
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    次に例を示します。
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でグループ通話ピックアップ番号をユーザーに割り当てる](lync-server-2013-assign-group-call-pickup-numbers-to-users.md)  
[Lync Server 2013 でユーザーのグループ通話ピックアップを無効にする](lync-server-2013-disable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

