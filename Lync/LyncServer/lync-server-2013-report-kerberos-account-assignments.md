---
title: 'Lync Server 2013: Kerberos アカウント割り当てのレポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Report Kerberos account assignments
ms:assetid: 523231f6-81b3-454b-996d-663d9bd5cf83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398343(v=OCS.15)
ms:contentKeyID: 48184151
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 608757b71903ce5290f5f75936b5e5a3904f07fb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536334"
---
# <a name="report-kerberos-account-assignments-in-lync-server-2013"></a>Lync Server 2013 での Kerberos アカウント割り当てのレポート

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-01-16_

この手順を正常に完了させるには、RTCUniversalServerAdmins グループのメンバーであるユーザーとしてログオンする必要があります。

**Get-CsKerberosAccountAssignment** コマンドレットを使用して、Kerberos 認証アカウントの割り当てに関する情報を照会したり、展開の現在の割り当てに関する情報をレポートしたりできます。

<div>

## <a name="to-query-kerberos-authentication-account-assignments-for-a-site"></a>サイトの Kerberos 認証アカウントの割り当てを照会するには

1.  RTCUniversalServerAdmins グループのメンバーとして、Lync Server 2013 を実行しているドメイン内のコンピューター、または管理ツールがインストールされているコンピューターにログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

3.  コマンド ラインで、次のいずれかのコマンドを実行します。
    
      - 組織の Kerberos 認証アカウントの割り当てをすべて照会し、それぞれの割り当て情報を戻すには、パラメーターを指定せずにコマンドレットを実行します。
        
            Get-CsKerberosAccountAssignment
    
      - 展開の Kerberos 認証アカウントの割り当てをすべて照会し、それぞれのサイト割り当て情報を戻すには、Identity パラメーターを指定してコマンドレットを実行します。
        
            Get-CsKerberosAccountAssignment -Identity "site:SiteName"
        
        次にその例を示します。
        
            Get-CsKerberosAccountAssignment -Identity "site:Redmond"
    
      - 1 つのサイトの Kerberos 認証アカウントの割り当てをすべて照会し、それぞれの割り当て情報を戻すには、Filter パラメーターを指定してコマンドレットを実行します。
        
            Get-CsKerberosAccountAssignment -Filter "SiteName"
        
        次にその例を示します。
        
            Get-CsKerberosAccountAssignment -Filter "*Redmond"
        
        <div>
        

        > [!NOTE]  
        > Filter パラメーターに *SiteName を指定すると、指定したサイト名がサイト ID に含まれるすべてのサイトの情報が戻されます (サイト ID に Redmond という文字列が含まれるすべてのサイトなど)。

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

