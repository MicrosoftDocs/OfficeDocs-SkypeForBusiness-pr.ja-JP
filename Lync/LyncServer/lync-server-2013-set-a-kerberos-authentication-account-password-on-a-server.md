---
title: 'Lync Server 2013: サーバーで Kerberos 認証アカウントのパスワードを設定する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set a Kerberos authentication account password on a server
ms:assetid: 902d3292-678d-4512-9248-586053cb638b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398734(v=OCS.15)
ms:contentKeyID: 48184787
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9799be0fda2b1a3c5b7765774b1f9e3199cc61f3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051661"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-a-kerberos-authentication-account-password-on-a-server-in-lync-server-2013"></a>Lync Server 2013 のサーバーで Kerberos 認証アカウントのパスワードを設定する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-01-16_

この手順を正常に完了させるには、RTCUniversalServerAdmins グループのメンバーであるユーザーとしてログオンする必要があります。

フロントエンド サーバー、Standard Edition サーバー、およびディレクターが存在する各サイトの Kerberos アカウントにパスワードを設定する必要があります。 パスワードを設定するには、サイト内の1つのサーバー (たとえば、1つのフロントエンドサーバー) で、 **set-csker' osaccountpassword** Windows PowerShell コマンドレットを実行します。 サイトごとに、 **Set-cskerの osaccountpassword** コマンドレットを実行する必要があります。 このコマンドレットにより、Web サービスサービスのインターネットインフォメーションサービス (IIS) が構成され、Active Directory ドメインサービスのコンピューターアカウントのパスワードが設定されます。 Kerberos アカウント パスワードのソースとして構成された別のサーバーを使用しながら、コマンドレットと使用されるパラメーターに基づいて、別のメソッドが 1 台のサーバーで IIS を構成します。

**Set-CsKerberosAccountPassword** コマンドレットを使用してパスワードを設定する場合、Kerberos はランダムに生成されたストリングをパスワードに設定します。 このコマンドレットは、このアカウントが割り当てられているすべての Lync Server 2013 中央サイト内のすべての IIS インスタンスに接続します。

<div>

## <a name="to-set-a-password-for-a-kerberos-authentication-account"></a>Kerberos 認証アカウントのパスワードを設定するには

1.  Lync Server 管理シェルがインストールされている任意のドメインコンピュータに、RTCUniversalServerAdmins グループのメンバーとしてログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

3.  コマンド ラインで次の 2 つのコマンドを実行します。
    
        Set-CsKerberosAccountPassword -UserAccount "Domain\UserAccount"
    
    次にその例を示します。
    
        Set-CsKerberosAccountPassword -UserAccount "contoso\KerbAuth"
    
    <div>
    

    > [!NOTE]  
    > UserAccount パラメーターは、ドメイン\ユーザーの形式で指定する必要があります。 Kerberos 認証目的で作成されたコンピューター オブジェクトの参照には、「ユーザー@ドメイン.拡張子」形式はサポートされていません。

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > アカウントの追加、アカウントの削除など、Kerberos 認証に変更を加えた後、Lync Server 管理シェルコマンドプロンプトから<STRONG>Enable-CsTopology</STRONG>設定を実行する必要があります。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

