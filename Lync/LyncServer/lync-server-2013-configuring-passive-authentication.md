---
title: 'Lync Server 2013: パッシブ認証を構成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Lync Server passive authentication
ms:assetid: 9a904b8d-9fce-4abf-be73-5c8e48cfb53a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308569(v=OCS.15)
ms:contentKeyID: 54973690
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 590a196ca0e34c0c063b10703c7edd131eb82c50
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "40971108"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-lync-server-2013-passive-authentication"></a>Lync Server 2013 のパッシブ認証を構成する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-07-11_

以下のセクションでは、累積更新プログラムを使って Lync Server 2013 を構成する方法について説明します。2013年7月パッシブ認証をサポートします。 有効にした後、2要素認証が有効になっている Lync ユーザーは、物理または仮想スマートカードと有効な PIN を使用して、Lync 2013 で累積更新プログラムを使ってサインインする必要があります。これは、2013年7月のクライアントです。

<div class="">


> [!NOTE]  
> レジストラーと Web サービスのパッシブ認証はサービス レベルで有効にすることを強くお勧めします。 グローバルレベルでレジストラーと Web サービスのパッシブ認証が有効になっている場合、累積更新プログラムを使って Lync 2013 でサインインしていないユーザーに対して、組織全体の認証エラーが発生する可能性があります。これは、2013年7月のクライアントデスクトップクライアントです。



</div>

<div>

## <a name="web-service-configuration"></a>Web サービス構成設定

次の手順では、パッシブ認証を有効にするディレクター、エンタープライズ プール、Standard Edition サーバーにカスタムの Web サービス構成設定を作成する方法について説明します。

**カスタムの Web サービス構成設定を作成するには**

1.  累積更新プログラムで Lync Server 2013 にログインします。 Lync 管理者アカウントを使用して、2013年7月のフロントエンドサーバーにログインします。

2.  Lync Server 2013 Management Shell を起動します。

3.  Lync Server 管理シェルコマンドラインで、次のコマンドを実行して、各ディレクター、エンタープライズプール、および標準エディションサーバー用の新しい Web サービス構成を作成します。これにより、パッシブ認証が有効になります。
    ```powershell
    New-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
    ```

    <div class="">
    

    > [!WARNING]  
    > WsFedPassiveMetadataUri の FQDN の値は、AD FS 2.0 サーバーのフェデレーション サービス名です。フェデレーション サービス名の値は、AD FS 2.0 管理コンソールでナビゲーション ウィンドウの [<STRONG>サービス</STRONG>] を右クリックし、[<STRONG>Edit Federation Service Properties</STRONG>] を選択すると確認できます。

    
    </div>

4.  次のコマンドを実行して、UseWsFedPassiveAuth と WsFedPassiveMetadataUri の値が正しく設定されたことを確認します。
     ```powershell
     Get-CsWebServiceConfiguration -identity "Service:WebServer:LyncPool01.contoso.com" | format-list UseWsFedPassiveAuth, WsFedPassiveMetadataUri
     ```
5.  クライアントでは、パッシブ認証は WebTicket 認証の最も望ましくない方法です。 パッシブ認証を有効にするすべてのディレクター、エンタープライズプール、および標準エディションのサーバーについては、次のコマンドを実行して、Lync Web サービスで他のすべての認証の種類を無効にする必要があります。
    ```powershell
    Set-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" -UseCertificateAuth $false -UsePinAuth $false -UseWindowsAuth NONE
     ```
6.  次のコマンドを実行して、他のすべての認証の種類が正常に無効になっていることを確認します。
    ```powershell
    Get-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" | format-list UseCertificateAuth, UsePinAuth, UseWindowsAuth
     ```
</div>

<div>

## <a name="proxy-configuration"></a>プロキシ構成設定

Lync Web サービスの証明書認証が無効になっている場合、Lync クライアントは、より優先度の低い認証の種類 (Kerberos、NTLM など) を使用してレジストラーサービスを認証します。 ただし、証明書の認証は、Lync クライアントが webticket を取得できるようにするために必要ですが、レジストラーサービスについては、Kerberos と NTLM を無効にする必要があります。

次の手順では、パッシブ認証を有効にするエッジ プール、エンタープライズ プール、Standard Edition サーバーにカスタムのプロキシ構成設定を作成する方法について説明します。

**カスタムのプロキシ構成設定を作成するには**

1.  Lync Server 管理シェルコマンドラインから、累積更新プログラムを使用して、各 Lync Server 2013 に対して新しいプロキシ構成を作成します。 2013 Edge プール、エンタープライズプール、Standard Edition Server は、以下のコマンドを実行します。
    
       ```powershell
        New-CsProxyConfiguration -Identity "Service:EdgeServer:EdgePool01.contoso.com" 
        -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
       ```
    
       ```powershell
        New-CsProxyConfiguration -Identity "Service:Registrar:LyncPool01.contoso.com" 
        -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
       ```

2.  次のコマンドを実行して、他のすべてのプロキシ認証の種類が無効になっていることを確認します。
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

