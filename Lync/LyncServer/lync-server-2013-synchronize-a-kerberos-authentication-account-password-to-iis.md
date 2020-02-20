---
title: Kerberos 認証アカウントのパスワードを IIS に同期させる
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Synchronize a Kerberos authentication account password to IIS
ms:assetid: 05925a66-2684-4c1b-adfa-69bd0da1bf38
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398107(v=OCS.15)
ms:contentKeyID: 48183296
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 255c1035809b69d5de1bb5e08fc770dc9a6b1c4d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142313"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="synchronize-a-kerberos-authentication-account-password-to-iis-in-lync-server-2013"></a>Lync Server 2013 で Kerberos 認証アカウントのパスワードを IIS に同期させる

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2010-11-08_

この手順を正常に完了させるには、RTCUniversalServerAdmins グループのメンバーであるユーザーとしてログオンする必要があります。

サイトでは、フロントエンドサーバー、Standard Edition サーバー、およびディレクターは、Web サービスへの要求を認証する目的で、Kerberos 認証アカウントを使用できます。 この手順では、Kerberos アカウントが割り当てられているサイトで Web サービスを実行している各サーバーを検索し、Kerberos アカウントを使用するようにインターネットインフォメーションサービス (IIS) の構成設定を更新します。 詳細については、「 [Lync server 2013 のサーバーでの Kerberos 認証アカウントパスワードの設定](lync-server-2013-set-a-kerberos-authentication-account-password-on-a-server.md)」を参照してください。

<div>

## <a name="to-set-and-configure-a-kerberos-authentication-account-password"></a>Kerberos 認証アカウントのパスワードを設定および構成するには

1.  ソース コンピューター (fe01.contoso.com など) に RTCUniversalServerAdmins グループのメンバーとしてログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

3.  Lync Server 管理シェルコマンドラインから、次の2つのコマンドを実行します。
    
        Set-CsKerberosAccountPassword -FromComputer SourceComputer -ToComputer DestinationComputer
    
    次にその例を示します。
    
        Set-CsKerberosAccountPassword -FromComputer fe01.contoso.com -ToComputer dir01.contoso.com
    
    <div>
    

    > [!IMPORTANT]
    > ソース コンピューターと宛先のコンピューターの名前は、サーバーの完全修飾ドメイン名 (FQDN) である必要があります。 プール名がソース コンピューターまたは宛先のコンピューターとして使用しているコンピューターの名前と同じでない限り、プール FQDN を使用することはできません。

    
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

