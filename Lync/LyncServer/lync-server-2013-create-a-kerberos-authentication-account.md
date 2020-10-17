---
title: 'Lync Server 2013: Kerberos 認証アカウントの作成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a Kerberos authentication account
ms:assetid: 63f0cef6-562a-4209-ae25-71f8dc7c7295
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398449(v=OCS.15)
ms:contentKeyID: 48184348
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 46e63b339f9a8d9705af47d9226adde88fe2d053
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507514"
---
# <a name="create-a-kerberos-authentication-account-in-lync-server-2013"></a>Lync Server 2013 で Kerberos 認証アカウントを作成する

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-01-02_

この手順を適切に完了するには、少なくとも Domain Admins グループのメンバーとしてサーバーまたはドメインにログオンする必要があります。

各サイトに Kerberos 認証アカウントを作成したり、単一の Kerberos 認証アカウントを作成してすべてのサイトで使用したりすることができます。 Windows PowerShell コマンドレットを使用して、各サイトに割り当てられたアカウントの識別を含む、アカウントの作成と管理を行います。 トポロジビルダーおよび Lync Server 2013 コントロールパネルに Kerberos 認証アカウントが表示されません。 1 つ以上のユーザー アカウントを作成して Kerberos 認証用に使用するには、次の手順を使用します。

<div>

## <a name="to-create-a-kerberos-account"></a>Kerberos アカウントを作成するには、次の手順を実行します。

1.  Domain Admins グループのメンバーとして、Lync Server 2013 を実行しているドメイン内のコンピューター、または管理ツールがインストールされているコンピューターにログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

3.  コマンド ラインで、次のコマンドを実行します。
    
        New-CsKerberosAccount -UserAccount "Domain\UserAccount" -ContainerDN "CN=Users,DC=DomainName,DC=DomainExtension"
    
    次にその例を示します。
    
        New-CsKerberosAccount -UserAccount "Contoso\KerbAuth" -ContainerDN "CN=Users,DC=contoso,DC=com"

4.  コンピューター オブジェクトが作成されていることを確認します。それには、[Active Directory ユーザーとコンピューター] を開いて、[**ユーザー**] コンテナーを展開し、ユーザー アカウントのコンピューター オブジェクトがコンテナー内にあることを確認します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

