---
title: 'Lync Server 2013: グループ通話ピックアップ番号をユーザーに割り当てる'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign Group Call Pickup numbers to users
ms:assetid: b8e79275-8e7e-4799-b908-f34f61df22f0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945647(v=OCS.15)
ms:contentKeyID: 51541508
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5a27746909a5a4baa5ea6c3c6d050393e66dab05
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030080"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assign-group-call-pickup-numbers-to-users-in-lync-server-2013"></a>Lync Server 2013 でグループ通話ピックアップ番号をユーザーに割り当てる

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-01-30_

グループ通話ピックアップグループ番号をコールパークオービットテーブルに追加すると、グループをユーザーに割り当てることができます。 代理の拡張機能のアクティブ化 (SEFAUtil) リソースキットツールを使用して、ユーザーに通話ピックアップグループを割り当てます。

<div>


> [!NOTE]  
> ハイブリッド展開では、online に所属しているユーザーにグループ通話ピックアップグループを割り当てないでください。 オンラインに所属しているユーザーは、グループ通話ピックアップに参加できません。 つまり、他のユーザーはその通話に応答できないため、他のユーザーの呼び出しに応答できません。



</div>

<div>

## <a name="to-assign-a-group-call-pickup-group-to-a-user"></a>グループの通話ピックアップグループをユーザーに割り当てるには

1.  SEFAUtil ツールをインストールしたコンピューターに管理者権限でログオンします。

2.  コマンド ラインで、次のコマンドを実行します。
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    次に例を示します。
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でユーザーのグループ通話ピックアップを有効にする](lync-server-2013-enable-group-call-pickup-for-users.md)  
[Lync Server 2013 でユーザーのグループ通話ピックアップを無効にする](lync-server-2013-disable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

