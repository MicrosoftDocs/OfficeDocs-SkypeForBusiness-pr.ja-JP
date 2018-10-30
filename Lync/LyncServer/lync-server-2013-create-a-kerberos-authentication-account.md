---
title: 'Lync Server 2013: Kerberos 認証アカウントの作成'
TOCTitle: Kerberos 認証アカウントの作成
ms:assetid: 63f0cef6-562a-4209-ae25-71f8dc7c7295
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398449(v=OCS.15)
ms:contentKeyID: 48272318
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での Kerberos 認証アカウントの作成

 

_**トピックの最終更新日:** 2012-01-02_

この手順を適切に完了するには、少なくとも Domain Admins グループのメンバーとしてサーバーまたはドメインにログオンする必要があります。

各サイトに Kerberos 認証アカウントを作成したり、単一の Kerberos 認証アカウントを作成してすべてのサイトで使用したりすることができます。Windows PowerShell コマンドレットを使用すると、アカウントを作成して、各サイトに割り当てられたアカウントの識別などの管理を実行できます。トポロジ ビルダーおよび Lync Server 2013 コントロール パネルでは、Kerberos 認証アカウントは表示されません。 1 つ以上のユーザー アカウントを作成して Kerberos 認証用に使用するには、次の手順を使用します。

## Kerberos アカウントを作成するには、次の手順を実行します。

1.  Domain Admins グループのメンバーとして、Lync Server 2013 を実行するドメイン内のコンピューターまたは管理ツールがインストールされたコンピューターにログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

3.  コマンド ラインで、次のコマンドを実行します。
    
        New-CsKerberosAccount -UserAccount "Domain\UserAccount" -ContainerDN "CN=Users,DC=DomainName,DC=DomainExtension"
    
    次に例を示します。
    
        New-CsKerberosAccount -UserAccount "Contoso\KerbAuth" -ContainerDN "CN=Users,DC=contoso,DC=com"

4.  コンピューター オブジェクトが作成されていることを確認します。それには、\[Active Directory ユーザーとコンピューター\] を開いて、\[**ユーザー**\] コンテナーを展開し、ユーザー アカウントのコンピューター オブジェクトがコンテナー内にあることを確認します。

