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
ms.openlocfilehash: e6137224f313238dae33462298931167ba7bb810
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529524"
---
# <a name="assign-a-kerberos-authentication-account-to-a-site-in-lync-server-2013"></a>Lync Server 2013 のサイトへの Kerberos 認証アカウントの割り当て

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2017-04-18_

この手順を正常に完了させるには、RTCUniversalServerAdmins グループのメンバーであるユーザーとしてログオンする必要があります。

Kerberos アカウントを作成した後、これをサイトに割り当てる必要があります。 これは、Active Directory サイトではなく、Lync Server 2013 サイトです。 1 つの展開に複数の Kerberos 認証アカウントを作成できますが、サイトに割り当てられるアカウントは 1 つだけです。 以前に作成した Kerberos 認証アカウントをサイトに割り当てるには、次の手順を使用します。 Kerberos アカウントの作成の詳細については、「 [Lync Server 2013 で kerberos 認証アカウントを作成する](lync-server-2013-create-a-kerberos-authentication-account.md)」を参照してください。

<div>

## <a name="to-assign-a-kerberos-authentication-account-to-a-site"></a>Kerberos 認証アカウントをサイトに割り当てるには

1.  RTCUniversalServerAdmins グループのメンバーとして、Lync Server 2013 を実行しているドメイン内のコンピューター、または管理ツールがインストールされているコンピューターにログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

3.  コマンド ラインで次の 2 つのコマンドを実行します。
    
       ```powershell
        New-CsKerberosAccountAssignment -UserAccount "Domain\UserAccount"
                  -Identity "site:SiteName"
       ```          
    
       ```powershell
        Enable-CsTopology
       ```
    
    次にその例を示します。
    
       ```powershell
        New-CsKerberosAccountAssignment -UserAccount "contoso\kerbauth"
                  -Identity "site:redmond"
       ```
    
       ```powershell
        Enable-CsTopology
       ```
    
    <div class="">
    

    > [!NOTE]  
    > UserAccount パラメーターは、ドメイン\ユーザーの形式で指定する必要があります。 ユーザー@ドメイン.拡張子の形式は、Kerberos 認証用に作成されたコンピューター オブジェクトの参照ではサポートされていません。

    
    </div>

4.  **オプション**: [Lync Server 2013 での Web サービス URL の変更](lync-server-2013-change-the-web-services-url.md)に応じて、WEB サービスの上書き FQDN (完全修飾ドメイン名) を構成した可能性があります。 その場合は、この FQDN の SPN も追加する必要があります。 たとえば、FQDN が [イントラネット] の場合は、次のように実行します。
    
    ```console
    setspn -S http/webservices.contoso.local kerbauth
    ```
5.     
    <div class="">
    

    > [!IMPORTANT]  
    > アカウントの追加、アカウントの削除など、Kerberos 認証に変更を加えた後、Lync Server 管理シェルコマンドプロンプトから <STRONG>Enable-CsTopology</STRONG> 設定を実行する必要があります。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

