---
title: 'Lync Server 2013: Kerberos アカウント割り当てのレポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Report Kerberos account assignments
ms:assetid: 523231f6-81b3-454b-996d-663d9bd5cf83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398343(v=OCS.15)
ms:contentKeyID: 48184151
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1b02eb3cae7a7d2bbeb4cc3b9dce0a7daa8ee5c3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823225"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="report-kerberos-account-assignments-in-lync-server-2013"></a>Lync Server 2013 での Kerberos アカウント割り当てのレポート

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-01-16_

この手順を正常に完了するには、RTCUniversalServerAdmins グループのメンバーであるユーザーとしてログオンする必要があります。

**CsKerberosAccountAssignment**コマンドレットを使用して、Kerberos 認証アカウントの割り当てに関する情報を照会し、展開内の現在の課題に関する情報を報告することができます。

<div>

## <a name="to-query-kerberos-authentication-account-assignments-for-a-site"></a>サイトの Kerberos 認証アカウントの割り当てを照会するには

1.  RTCUniversalServerAdmins グループのメンバーとして、Lync Server 2013 を実行しているドメイン内のコンピューター、または管理ツールがインストールされているコンピューターにログオンします。

2.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

3.  コマンドラインで、次のいずれかのコマンドを実行します。
    
      - 組織内のすべての Kerberos 認証アカウントの割り当てを照会し、それぞれの割り当て情報を返すには、パラメーターを指定せずにコマンドレットを実行します。
        
            Get-CsKerberosAccountAssignment
    
      - 展開ですべての Kerberos 認証アカウントの割り当てを照会し、それぞれのサイト割り当て情報を返すには、Identity パラメーターを指定してコマンドレットを実行します。
        
            Get-CsKerberosAccountAssignment -Identity "site:SiteName"
        
        次に例を示します。
        
            Get-CsKerberosAccountAssignment -Identity "site:Redmond"
    
      - 1つのサイトですべての Kerberos 認証アカウントの割り当てを照会し、それぞれの割り当て情報を返すには、Filter パラメーターを指定してコマンドレットを実行します。
        
            Get-CsKerberosAccountAssignment -Filter "SiteName"
        
        次に例を示します。
        
            Get-CsKerberosAccountAssignment -Filter "*Redmond"
        
        <div>
        

        > [!NOTE]  
        > * SiteName を Filter パラメーターとして指定すると、指定したサイト名を含むすべてのサイトに関する情報 (サイト識別子に Redmond という文字列が含まれるすべてのサイトなど) が返されます。

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

