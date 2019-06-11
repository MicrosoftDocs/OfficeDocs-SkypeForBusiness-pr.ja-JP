---
title: 'Lync Server 2013: サーバーへの Kerberos 認証アカウント パスワードの設定'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Set a Kerberos authentication account password on a server
ms:assetid: 902d3292-678d-4512-9248-586053cb638b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398734(v=OCS.15)
ms:contentKeyID: 48184787
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bc4eefe4c1ef804b1deb06d056bfbd61ade35eb0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34821944"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-a-kerberos-authentication-account-password-on-a-server-in-lync-server-2013"></a>Lync Server 2013 でのサーバーへの Kerberos 認証アカウント パスワードの設定

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-01-16_

この手順を正常に完了するには、RTCUniversalServerAdmins グループのメンバーであるユーザーとしてログオンする必要があります。

フロントエンドサーバー、標準エディションサーバー、およびディレクターがある各サイトの Kerberos アカウントでパスワードを設定する必要があります。 パスワードを設定するには、サイト内の1つのサーバー (たとえば、1つのフロントエンドサーバー) に対して、 **set-cskerberosaccountpassword** Windows PowerShell コマンドレットを実行します。 各サイトについて、 **Set-csker"@ accountpassword** " コマンドレットを実行する必要があります。 Web サービス用のインターネットインフォメーションサービス (IIS) を構成し、Active Directory ドメインサービスのコンピューターアカウントにパスワードを設定します。 コマンドレットで使用されるパラメーターに基づいた代替メソッドは、Kerberos アカウントのパスワードのソースとして構成されている別のサーバーを使用しているときに、あるサーバーで IIS を構成します。

**Set-Cskerの**コマンドレットを使用してパスワードを設定すると、Kerberos はパスワードをランダムに生成された文字列に設定します。 このコマンドレットは、このアカウントが割り当てられているすべての Lync Server 2013 セントラルサイト内のすべての IIS インスタンスに接続します。

<div>

## <a name="to-set-a-password-for-a-kerberos-authentication-account"></a>Kerberos 認証アカウントのパスワードを設定するには

1.  RTCUniversalServerAdmins グループのメンバーとしてインストールされている Lync Server 管理シェルがインストールされている任意のドメインコンピューターにログオンします。

2.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

3.  コマンドラインで、次の2つのコマンドを実行します。
    
        Set-CsKerberosAccountPassword -UserAccount "Domain\UserAccount"
    
    次に例を示します。
    
        Set-CsKerberosAccountPassword -UserAccount "contoso\KerbAuth"
    
    <div>
    

    > [!NOTE]  
    > UserAccount パラメーターを指定するには、Domain\User 形式を使用する必要があります。 ユーザー @ ドメイン拡張子形式は、Kerberos 認証のために作成されたコンピューターオブジェクトを参照する場合はサポートされません。

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > アカウントの追加やアカウントの削除など、Kerberos 認証を変更した後は、Lync Server 管理シェルのコマンドプロンプトから、 <STRONG>Enable-CsTopology</STRONG>方法を実行する必要があります。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

