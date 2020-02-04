---
title: 'Lync Server 2013: サイトからの Kerberos 認証の削除'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remove Kerberos authentication from a site
ms:assetid: 93171b02-bb36-42dc-943d-86d9dde45b59
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398749(v=OCS.15)
ms:contentKeyID: 48184806
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e88f3de6f653354087d1abd0f7884ee09eda2f36
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746817"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="in-lync-server-2013-remove-kerberos-authentication-from-a-site"></a>Lync Server 2013 でのサイトからの Kerberos 認証の削除

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-01-16_

この手順を正常に完了するには、RTCUniversalServerAdmins グループのメンバーであるユーザーとしてログオンする必要があります。

サイトからの Kerberos 認証を削除する必要がある場合、またはサイトを削除する必要がある場合は、 **CsKerberosAccountAssignment**コマンドレットを使用して、サイトから kerberos 認証アカウントの割り当てを削除する必要があります。 次の手順を使用して、Kerberos 認証アカウントの割り当てを削除します。これにより、サイト内のすべてのコンピューターから課題が削除されます。

<div class=" ">


> [!WARNING]  
> Kerberos 対応のアカウントを完全に無効にする場合は、割り当てを削除した後で Active Directory ユーザーとコンピューターを使用して Active Directory ドメインサービスから削除する必要があります。 今後このオブジェクトを使う予定がある場合は、Active Directory オブジェクトを保持しておくことをお勧めします。



</div>

<div>

## <a name="to-remove-kerberos-authentication-from-a-site"></a>サイトから Kerberos 認証を削除するには

1.  RTCUniversalServerAdmins グループのメンバーとして、Lync Server 2013 を実行しているドメイン内のコンピューター、または管理ツールがインストールされているコンピューターにログオンします。

2.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

3.  コマンドラインで、次の2つのコマンドを実行します。
    
       ```PowerShell
        Remove-CsKerberosAccountAssignment -Identity "site:SiteName"
       ```
    
       ```PowerShell
        Enable-CsTopology
       ```
    
    次に例を示します。
    
       ```PowerShell
        Remove-CsKerberosAccountAssignment -Identity "site:Redmond"
       ```
    
       ```PowerShell
        Enable-CsTopology
       ```
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > アカウントの追加やアカウントの削除など、Kerberos 認証を変更した後は、Lync Server 管理シェルのコマンドプロンプトから、 <STRONG>Enable-CsTopology</STRONG>方法を実行する必要があります。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

