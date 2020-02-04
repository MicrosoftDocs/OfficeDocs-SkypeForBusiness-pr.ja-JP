---
title: 'Lync Server 2013: サイトへの Kerberos 認証アカウントの割り当て'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a Kerberos authentication account to a site
ms:assetid: 3d9c587c-c8b8-4f81-8ed9-1458a31fc292
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425901(v=OCS.15)
ms:contentKeyID: 48183929
ms.date: 04/18/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 230341bfc6b26bebd22b55195280ffdff130873d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738387"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assign-a-kerberos-authentication-account-to-a-site-in-lync-server-2013"></a>Lync Server 2013 での、サイトへの Kerberos 認証アカウントの割り当て

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2017-04-18_

この手順を正常に完了するには、RTCUniversalServerAdmins グループのメンバーであるユーザーとしてログオンする必要があります。

Kerberos アカウントを作成したら、それをサイトに割り当てる必要があります。 これは、Active Directory サイトではなく、Lync Server 2013 サイトです。 展開ごとに複数の Kerberos 認証アカウントを作成することはできますが、1つのサイトに割り当てることができるアカウントは1つだけです。 以前に作成した Kerberos 認証アカウントをサイトに割り当てるには、次の手順を使用します。 Kerberos アカウントの作成の詳細については、「 [Lync Server 2013 で kerberos 認証アカウントを作成](lync-server-2013-create-a-kerberos-authentication-account.md)する」を参照してください。

<div>

## <a name="to-assign-a-kerberos-authentication-account-to-a-site"></a>サイトに Kerberos 認証アカウントを割り当てるには

1.  RTCUniversalServerAdmins グループのメンバーとして、Lync Server 2013 を実行しているドメイン内のコンピューター、または管理ツールがインストールされているコンピューターにログオンします。

2.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

3.  コマンドラインで、次の2つのコマンドを実行します。
    
       ```powershell
        New-CsKerberosAccountAssignment -UserAccount "Domain\UserAccount"
                  -Identity "site:SiteName"
       ```          
    
       ```powershell
        Enable-CsTopology
       ```
    
    次に例を示します。
    
       ```powershell
        New-CsKerberosAccountAssignment -UserAccount "contoso\kerbauth"
                  -Identity "site:redmond"
       ```
    
       ```powershell
        Enable-CsTopology
       ```
    
    <div class="">
    

    > [!NOTE]  
    > UserAccount パラメーターを指定するには、Domain\User 形式を使用する必要があります。 Kerberos 認証のために作成されたコンピューターオブジェクトを参照する場合、User@Domain 拡張子形式はサポートされません。

    
    </div>

4.  **オプション**: [Lync Server 2013 で WEB サービスの URL を変更](lync-server-2013-change-the-web-services-url.md)すると、WEB サイトの上書き FQDN (完全修飾ドメイン名) が設定されている可能性があります。 その場合は、この FQDN の SPN も追加する必要があります。 たとえば、FQDN が .local の場合は、次のように実行します。
    
    ```console
    setspn -S http/webservices.contoso.local kerbauth
    ```
5.     
    <div class="">
    

    > [!IMPORTANT]  
    > アカウントの追加やアカウントの削除など、Kerberos 認証を変更した後は、Lync Server 管理シェルのコマンドプロンプトから、 <STRONG>Enable-CsTopology</STRONG>方法を実行する必要があります。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

