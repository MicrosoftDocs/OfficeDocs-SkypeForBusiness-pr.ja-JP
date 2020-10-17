---
title: 'Lync Server 2013: パッシブ認証の構成'
description: 'Lync Server 2013: パッシブ認証の構成。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Lync Server passive authentication
ms:assetid: 9a904b8d-9fce-4abf-be73-5c8e48cfb53a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308569(v=OCS.15)
ms:contentKeyID: 54973690
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 52a83c1413dcac18fb37ff0fe308266a3d7aeab4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548293"
---
# <a name="configuring-lync-server-2013-passive-authentication"></a>Lync Server 2013 のパッシブ認証の構成

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-07-11_

次のセクションでは、累積的な更新プログラムで Lync Server 2013 を構成する方法について説明します。7月2013はパッシブ認証をサポートします。 有効にした場合、2要素認証が有効になっている Lync ユーザーは、累積的な更新プログラム (7 月2013クライアント) で Lync 2013 を使用してサインインするために、物理または仮想スマートカードと有効な PIN を使用する必要があります。

<div class="">


> [!NOTE]  
> ユーザーがサービスレベルでレジストラーと Web サービスのパッシブ認証を有効にすることを強くお勧めします。 グローバルレベルでレジストラーと Web サービスのパッシブ認証が有効になっている場合は、累積更新プログラム (7 月2013クライアントデスクトップクライアント) で Lync 2013 を使用してサインインしていないユーザーに対して、組織全体の認証エラーが発生する可能性があります。



</div>

<div>

## <a name="web-service-configuration"></a>Web サービスの構成

次の手順では、パッシブ認証を有効にするディレクター、エンタープライズプール、Standard Edition サーバー用のカスタム web サービス構成を作成する方法について説明します。

**カスタム web サービス構成を作成するには**

1.  累積的な更新プログラム (Lync 管理者アカウントを使用した7月2013のフロントエンドサーバー) で Lync Server 2013 にログインします。

2.  Lync Server 2013 管理シェルを起動します。

3.  Lync Server 管理シェルコマンドラインから、次のコマンドを実行することによって、パッシブ認証が有効になるディレクター、エンタープライズプール、Standard Edition サーバーごとに新しい Web サービス構成を作成します。
    ```powershell
    New-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
    ```

    <div class="">
    

    > [!WARNING]  
    > WsFedPassiveMetadataUri FQDN の値は、AD FS 2.0 サーバーのフェデレーションサービス名です。 フェデレーションサービス名の値は、AD FS 2.0 管理コンソールで、ナビゲーションウィンドウの [ <STRONG>サービス</STRONG> ] を右クリックし、[ <STRONG>フェデレーションサービスのプロパティの編集</STRONG>] を選択すると表示されます。

    
    </div>

4.  UseWsFedPassiveAuth および WsFedPassiveMetadataUri の値が正しく設定されていることを確認するには、次のコマンドを実行します。
     ```powershell
     Get-CsWebServiceConfiguration -identity "Service:WebServer:LyncPool01.contoso.com" | format-list UseWsFedPassiveAuth, WsFedPassiveMetadataUri
     ```
5.  クライアントの場合、パッシブ認証は、webticket 認証で最も推奨される認証方法です。 パッシブ認証を有効にするすべてのディレクター、エンタープライズプール、Standard Edition サーバーでは、次のコマンドを実行することによって、Lync Web サービスで他のすべての認証の種類を無効にする必要があります。
    ```powershell
    Set-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" -UseCertificateAuth $false -UsePinAuth $false -UseWindowsAuth NONE
     ```
6.  次のコマンドを実行して、他のすべての認証の種類が正常に無効になっていることを確認します。
    ```powershell
    Get-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" | format-list UseCertificateAuth, UsePinAuth, UseWindowsAuth
     ```
</div>

<div>

## <a name="proxy-configuration"></a>プロキシの構成

Lync Web サービスで証明書認証が無効になっている場合、Lync クライアントは、レジストラーサービスへの認証に、Kerberos や NTLM などの優先度の低い認証の種類を使用します。 ただし、Lync クライアントが webticket を取得できるようにするには、証明書認証が必要ですが、レジストラーサービスについては Kerberos と NTLM を無効にする必要があります。

次の手順では、パッシブ認証を有効にするエッジプール、エンタープライズプール、Standard Edition サーバーのカスタムプロキシ構成を作成する方法について説明します。

**カスタムプロキシ構成を作成するには**

1.  Lync Server 管理シェルコマンドラインから、累積的な更新プログラム (次のコマンドを実行することにより、7月2013エッジプール、エンタープライズプール、Standard Edition サーバー) 2013 の新しいプロキシ構成を作成し、パッシブ認証を有効にします。
    
       ```powershell
        New-CsProxyConfiguration -Identity "Service:EdgeServer:EdgePool01.contoso.com" 
        -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
       ```
    
       ```powershell
        New-CsProxyConfiguration -Identity "Service:Registrar:LyncPool01.contoso.com" 
        -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
       ```

2.  次のコマンドを実行して、他のすべてのプロキシ認証の種類が正常に無効になっていることを確認します。
    ```powershell
    Get-CsProxyConfiguration -Identity "Service:Registrar:LyncPool01.contoso.com"
         | format-list UseKerberosForClientToProxyAuth, UseNtlmForClientToProxyAuth, UseCertifcateForClientToProxyAuth
     ```
</div>

</div>

<span> </span>

</div>

</div>

</div>

