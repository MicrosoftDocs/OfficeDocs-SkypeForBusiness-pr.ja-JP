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
ms.openlocfilehash: 797e9216aed5d523e39dc4827d630e0cb1b857fd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740427"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-kerberos-authentication-account-in-lync-server-2013"></a>Lync Server 2013 での Kerberos 認証アカウントの作成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-01-02_

この手順を正常に完了するには、ドメイン管理者グループのメンバーとしてサーバーまたはドメインに最小でログオンしている必要があります。

各サイトに対して Kerberos 認証アカウントを作成することも、単一の Kerberos 認証アカウントを作成してすべてのサイトで使用することもできます。 各サイトに割り当てられているアカウントの識別など、アカウントの作成と管理には、Windows PowerShell コマンドレットを使用します。 トポロジビルダーと Lync Server 2013 コントロールパネルには、Kerberos 認証アカウントが表示されません。 Kerberos 認証に使用する1つ以上のユーザーアカウントを作成するには、次の手順を使用します。

<div>

## <a name="to-create-a-kerberos-account"></a>Kerberos アカウントを作成するには

1.  Domain Admins グループのメンバーとして、Lync Server 2013 を実行しているドメインのコンピューターにログオンするか、管理ツールがインストールされているコンピューターにログオンします。

2.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

3.  コマンドラインで、次のコマンドを実行します。
    
        New-CsKerberosAccount -UserAccount "Domain\UserAccount" -ContainerDN "CN=Users,DC=DomainName,DC=DomainExtension"
    
    次に例を示します。
    
        New-CsKerberosAccount -UserAccount "Contoso\KerbAuth" -ContainerDN "CN=Users,DC=contoso,DC=com"

4.  Active Directory ユーザーとコンピューターを開き、[**ユーザー** ] コンテナーを展開し、ユーザーアカウントのコンピューターオブジェクトがコンテナー内にあることを確認して、コンピューターオブジェクトが作成されたことを確認します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

