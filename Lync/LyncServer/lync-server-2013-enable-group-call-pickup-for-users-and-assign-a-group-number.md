---
title: 'Lync Server 2013: ユーザーのグループ通話ピックアップの有効化とグループ番号の割り当て'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Group Call Pickup for users and assign a group number
ms:assetid: c33bb6c2-d43b-4fb6-a0fa-6d82a7b09abe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945650(v=OCS.15)
ms:contentKeyID: 51541517
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: edba55fcfdedc04eb2d8a8356c3d295c381d7c70
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528744"
---
# <a name="enable-group-call-pickup-for-users-in-lync-server-2013-and-assign-a-group-number"></a>Lync Server 2013 のユーザーのグループ通話ピックアップを有効にし、グループ番号を割り当てる

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-01-30_

呼び出しピックアップグループ番号をコールパークオービットテーブルに追加したら、グループ番号をユーザーに割り当て、グループ通話ピックアップを有効にします。 第2の拡張機能のアクティブ化 (SEFAUtil) リソースキットツールを使用して、グループ番号を割り当て、グループ通話ピックアップを有効にします。

<div>


> [!NOTE]  
> ハイブリッド展開では、online に所属しているユーザーにグループ通話ピックアップグループを割り当てないでください。 オンラインに所属しているユーザーは、グループ通話ピックアップに参加できません。 つまり、他のユーザーはその通話に応答できないため、他のユーザーの呼び出しに応答できません。



</div>

<div>

## <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a>グループ番号を割り当てて、ユーザーのグループ通話ピックアップを有効にするには

1.  SEFAUtil ツールをインストールしたコンピューターに管理者権限でログオンします。

2.  コマンド ラインで、次のコマンドを実行します。
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    たとえば、グループ番号199をユーザーに割り当てるには、次のようにします。
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199 

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でユーザーのグループ通話ピックアップを無効にする](lync-server-2013-disable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

