---
title: Lync Server のパッシブ認証の構成
TOCTitle: Lync Server のパッシブ認証の構成
ms:assetid: 9a904b8d-9fce-4abf-be73-5c8e48cfb53a
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Dn308569(v=OCS.15)
ms:contentKeyID: 56270113
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server のパッシブ認証の構成

 

_**トピックの最終更新日:** 2013-07-11_

次のセクションでは、パッシブ認証をサポートするように、累積更新プログラム: 2013 年 7 月を適用した Lync Server 2013 を構成する方法について説明します。パッシブ認証を有効にすると、2 要素認証で有効になっている Lync ユーザーは、累積更新プログラム: 2013 年 7 月を適用した Lync 2013 クライアントを使用する際に、物理的または仮想のスマート カードと有効な PIN を使ってサインインすることが必要になります。

> [!NOTE]
> レジストラーと Web サービスのパッシブ認証はサービス レベルで有効にすることを強くお勧めします。レジストラーと Web サービスのパッシブ認証をグローバル レベルで有効にすると、累積更新プログラム: 2013 年 7 月を適用した Lync 2013 クライアントのデスクトップ クライアントでサインインしていないユーザーが組織全体で認証エラーになる可能性があります。


## Web サービス構成設定

次の手順では、パッシブ認証を有効にするディレクター、エンタープライズ プール、Standard Edition サーバーにカスタムの Web サービス構成設定を作成する方法について説明します。

**カスタムの Web サービス構成設定を作成するには**

1.  累積した更新プログラム: 2013 年 7 月を適用した Lync Server 2013 フロント エンド サーバーに Lync 管理者アカウントでログインします。

2.  Lync Server 2013 管理シェル を起動します。

3.  Lync Server 管理シェル コマンドラインから次のコマンドを実行して、パッシブ認証を有効にするディレクター、エンタープライズ プール、Standard Edition サーバーそれぞれに新しい Web サービス構成設定を作成します。
    
        New-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
    

    > [!WARNING]
    > WsFedPassiveMetadataUri の FQDN の値は、AD FS 2.0 サーバーのフェデレーション サービス名です。フェデレーション サービス名の値は、AD FS 2.0 管理コンソールでナビゲーション ウィンドウの [<STRONG>サービス</STRONG>] を右クリックし、[<STRONG>Edit Federation Service Properties</STRONG>] を選択すると確認できます。



4.  次のコマンドを実行して、UseWsFedPassiveAuth と WsFedPassiveMetadataUri の値が正しく設定されたことを確認します。
    
        Get-CsWebServiceConfiguration -identity "Service:WebServer:LyncPool01.contoso.com" | format-list UseWsFedPassiveAuth, WsFedPassiveMetadataUri

5.  クライアントでは、パッシブ認証は WebTicket 認証の最も望ましくない方法です。次のコマンドを実行して、パッシブ認証を有効にするすべてのディレクター、エンタープライズ プール、Standard Edition サーバーについて、Lync Web サービスで他のすべての認証の種類を無効にする必要があります。
    
        Set-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" -UseCertificateAuth $false -UsePinAuth $false -UseWindowsAuth NONE

6.  次のコマンドを実行して、他のすべての認証の種類が無効になっていることを確認します。
    
        Get-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" | format-list UseCertificateAuth, UsePinAuth, UseWindowsAuth

## プロキシ構成設定

Lync Web サービスで証明書認証が無効になっている場合、Lync クライアントは Kerberos や NTLM などの推奨度の低い認証の種類を使ってレジストラー サービスの認証を受けます。ただし、Lync クライアントが WebTicket を取得するには、やはり証明書認証が必要です。その場合、レジストラー サービスで Kerberos と NTLM を無効にする必要があります。

次の手順では、パッシブ認証を有効にするエッジ プール、エンタープライズ プール、Standard Edition サーバーにカスタムのプロキシ構成設定を作成する方法について説明します。

**カスタムのプロキシ構成設定を作成するには**

1.  Lync Server 管理シェル コマンドラインから次のコマンドを実行して、累積した更新プログラム: 2013 年 7 月を適用した Lync Server 2013 の、パッシブ認証を有効にするエッジ プール、エンタープライズ プール、Standard Edition サーバーのそれぞれに新しいプロキシ構成設定を作成します。
    
        New-CsProxyConfiguration -Identity "Service:EdgeServer:EdgePool01.contoso.com" 
        -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False

       &nbsp;
    
        New-CsProxyConfiguration -Identity "Service:Registrar:LyncPool01.contoso.com" 
        -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False

2.  次のコマンドを実行して、他のすべてのプロキシ認証の種類が無効になっていることを確認します。
    
        Get-CsProxyConfiguration -Identity "Service:Registrar:LyncPool01.contoso.com"
         | format-list UseKerberosForClientToProxyAuth, UseNtlmForClientToProxyAuth, UseCertifcateForClientToProxyAuth

