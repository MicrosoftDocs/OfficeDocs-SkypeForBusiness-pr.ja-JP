---
title: Kerberos 認証アカウント パスワードと IIS との同期
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
ms.openlocfilehash: 86e71f87c20064e542aa6a8db1d9b38048c5f736
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731657"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="synchronize-a-kerberos-authentication-account-password-to-iis-in-lync-server-2013"></a>Lync Server 2013 での Kerberos 認証アカウント パスワードと IIS との同期

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2010-11-08_

この手順を正常に完了するには、RTCUniversalServerAdmins グループのメンバーであるユーザーとしてログオンする必要があります。

サイトでは、フロントエンドサーバー、標準エディションサーバー、およびディレクターは、Web サービスサービスへの要求を認証するために、Kerberos 認証アカウントを使うことができます。 この手順では、Kerberos アカウントが割り当てられているサイトで Web サービスを実行している各サーバーを特定し、その Kerberos アカウントを使用するようにインターネットインフォメーションサービス (IIS) 構成設定を更新します。 詳細については、「 [Lync server 2013 でサーバー上の Kerberos 認証アカウントパスワードを設定する](lync-server-2013-set-a-kerberos-authentication-account-password-on-a-server.md)」を参照してください。

<div>

## <a name="to-set-and-configure-a-kerberos-authentication-account-password"></a>Kerberos 認証アカウントのパスワードを設定および構成するには

1.  ソースコンピューター (fe01.contoso.com など) に RTCUniversalServerAdmins グループのメンバーとしてログオンします。

2.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

3.  Lync Server 管理シェルコマンドラインから次の2つのコマンドを実行します。
    
        Set-CsKerberosAccountPassword -FromComputer SourceComputer -ToComputer DestinationComputer
    
    次に例を示します。
    
        Set-CsKerberosAccountPassword -FromComputer fe01.contoso.com -ToComputer dir01.contoso.com
    
    <div>
    

    > [!IMPORTANT]
    > ソースコンピューターとターゲットコンピューターの名前は、サーバーの完全修飾ドメイン (FQDN) 名である必要があります。 プール名は、ソースコンピューターまたは移行先コンピューターとして使用しているコンピューターの名前と同じである場合を除き、プールの FQDN は使用できません。

    
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

