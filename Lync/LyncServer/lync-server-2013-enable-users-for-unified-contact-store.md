---
title: 'Lync Server 2013: 統合連絡先ストアでユーザーを有効にする'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable users for unified contact store
ms:assetid: 7b46a01f-beb5-4a33-adb0-35f0502b168d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205024(v=OCS.15)
ms:contentKeyID: 48184599
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3df3cbd4d71a1decc3607263f2e98b159dc29b2e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735867"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-users-for-unified-contact-store-in-lync-server-2013"></a>Lync Server 2013 の統合連絡先ストアでユーザーを有効にする

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-07_

Lync Server 2013 を展開してトポロジを公開すると、既定では、統合連絡先ストアがすべてのユーザーに対して有効になります。 Lync Server 2013 を展開した後、ユニファイド連絡先ストアを有効にするために、追加の操作を行う必要はありません。 ただし、**Set-CsUserServicesPolicy** コマンドレットを使用すると、どのユーザーが統合連絡先ストアを使用できるのかをカスタマイズできます。 この機能の有効化は、グローバルに行うことも、サイトごと、テナントごと、または個人やそのグループごとに行うこともできます。

<div>

## <a name="to-enable-users-for-unified-contact-store"></a>統合連絡先ストアでユーザーを有効にするには

1.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

2.  次のいずれかの操作を実行します。
    
      - すべての Lync Server ユーザーに対して、統合された連絡先ストアをグローバルに有効にするには、コマンドラインで次のように入力します。
        
            Set-CsUserServicesPolicy -Identity global -UcsAllowed $True
    
      - 特定のサイトのユーザーに対してユニファイド連絡先ストアを有効にするには、コマンドラインで次のように入力します。
        
            New-CsUserServicesPolicy -Identity site:<site name> -UcsAllowed $True
        
        次に例を示します。
        
            New-CsUserServicesPolicy -Identity site:Redmond -UcsAllowed $True
    
      - テナントを使用してユニファイド連絡先ストアを有効にするには、コマンドラインで次のように入力します。
        
            Set-CsUserServicesPolicy -Tenant <tenantId> -UcsAllowed $True
        
        次に例を示します。
        
            Set-CsUserServicesPolicy -Tenant "38aad667-af54-4397-aaa7-e94c79ec2308" -UcsAllowed $True
    
      - 特定のユーザーに対してユニファイド連絡先ストアを有効にするには、コマンドラインで次のように入力します。
        
            New-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $True
            Grant-CsUserServicesPolicy -Identity "<user display name>" -PolicyName <"policy name">
        
        <div>
        

        > [!NOTE]  
        > ユーザーの表示名の代わりに、ユーザー エイリアスや SIP URI を使用することもできます。

        
        </div>
        
        例:
        
            New-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $True
            Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "UCS Enabled Users"
        
        <div>
        

        > [!NOTE]  
        > 前記の例の最初のコマンドでは、UcsAllowed フラグを True に設定することで、新しいユーザーごとのポリシーを <EM>UCS Enabled Users</EM> という名前で作成しています。2 番目のコマンドでは、Ken Myer という表示名のユーザーにこのポリシーを割り当てています。これは、Ken Myer が統合連絡先ストアで有効になったことを意味します。

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

