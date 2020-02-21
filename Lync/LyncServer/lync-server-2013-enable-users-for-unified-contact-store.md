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
ms.openlocfilehash: 5f4bd8e47259f7480f32e0fa6047657464a459de
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187800"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-users-for-unified-contact-store-in-lync-server-2013"></a>Lync Server 2013 で統合連絡先ストアに対してユーザーを有効にする

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-07_

Lync Server 2013 を展開してトポロジを公開すると、既定では、すべてのユーザーに対して統合連絡先ストアが有効になります。 Lync Server 2013 を展開した後に、統合連絡先ストアを有効にするために追加のアクションを実行する必要はありません。 ただし、**Set-CsUserServicesPolicy** コマンドレットを使用すると、どのユーザーが統合連絡先ストアを使用できるのかをカスタマイズできます。 この機能の有効化は、グローバルに行うことも、サイトごと、テナントごと、または個人やそのグループごとに行うこともできます。

<div>

## <a name="to-enable-users-for-unified-contact-store"></a>統合連絡先ストアでユーザーを有効にするには

1.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

2.  次のどちらかの操作を行います。
    
      - すべての Lync Server ユーザーに対して統合連絡先ストアをグローバルに有効にするには、コマンドラインで次のように入力します。
        
            Set-CsUserServicesPolicy -Identity global -UcsAllowed $True
    
      - 統合連絡先ストアを特定のサイトのユーザーに対して有効にするには、コマンドラインで次のように入力します。
        
            New-CsUserServicesPolicy -Identity site:<site name> -UcsAllowed $True
        
        次に例を示します。
        
            New-CsUserServicesPolicy -Identity site:Redmond -UcsAllowed $True
    
      - 統合連絡先ストアをテナントごとに有効にするには、コマンドラインで次のように入力します。
        
            Set-CsUserServicesPolicy -Tenant <tenantId> -UcsAllowed $True
        
        次に例を示します。
        
            Set-CsUserServicesPolicy -Tenant "38aad667-af54-4397-aaa7-e94c79ec2308" -UcsAllowed $True
    
      - 統合連絡先ストアを特定のユーザーに対して有効にするには、コマンドラインで次のように入力します。
        
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
        > 前記の例の最初のコマンドでは、UcsAllowed フラグを True に設定することで、新しいユーザーごとのポリシーを UCS Enabled Users<EM></EM> という名前で作成しています。2 番目のコマンドでは、Ken Myer という表示名のユーザーにこのポリシーを割り当てています。これは、Ken Myer が統合連絡先ストアで有効になったことを意味します。

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

