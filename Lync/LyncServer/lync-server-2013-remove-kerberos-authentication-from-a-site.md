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
ms.openlocfilehash: a4f7fa1160e7ff0afbbc4d8d4cc5ec96ab08e0f4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183142"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="in-lync-server-2013-remove-kerberos-authentication-from-a-site"></a>Lync Server 2013 で、サイトから Kerberos 認証を削除する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-01-16_

この手順を正常に完了させるには、RTCUniversalServerAdmins グループのメンバーであるユーザーとしてログオンする必要があります。

サイトから Kerberos 認証を削除する必要がある場合、またはサイトを廃止する必要がある場合は、 **get-cskerberosaccountassignment**コマンドレットを使用して、サイトから kerberos 認証アカウントの割り当てを削除する必要があります。 Kerberos 認証アカウントの割り当てを削除するには、次の手順を使用します。これにより、サイト内のすべてのコンピューターから割り当てが削除されます。

<div class=" ">


> [!WARNING]  
> Kerberos が有効なアカウントを完全に削除する場合は、割り当てを削除した後、Active directory のユーザーとコンピューターを使用して Active Directory ドメインサービスから削除する必要があります。 オブジェクトを後で使用する場合、Active Directory オブジェクトを保持しておくことができます。



</div>

<div>

## <a name="to-remove-kerberos-authentication-from-a-site"></a>サイトから Kerberos 認証を削除するには

1.  RTCUniversalServerAdmins グループのメンバーとして、Lync Server 2013 を実行しているドメイン内のコンピューター、または管理ツールがインストールされているコンピューターにログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

3.  コマンド ラインで次の 2 つのコマンドを実行します。
    
       ```PowerShell
        Remove-CsKerberosAccountAssignment -Identity "site:SiteName"
       ```
    
       ```PowerShell
        Enable-CsTopology
       ```
    
    次にその例を示します。
    
       ```PowerShell
        Remove-CsKerberosAccountAssignment -Identity "site:Redmond"
       ```
    
       ```PowerShell
        Enable-CsTopology
       ```
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > アカウントの追加、アカウントの削除など、Kerberos 認証に変更を加えた後、Lync Server 管理シェルコマンドプロンプトから<STRONG>Enable-CsTopology</STRONG>設定を実行する必要があります。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

