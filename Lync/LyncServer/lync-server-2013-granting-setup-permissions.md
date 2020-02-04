---
title: 'Lync Server 2013: セットアップ アクセス許可の付与'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Granting setup permissions
ms:assetid: 15982bfe-6844-44f6-815a-72dcaf0e4d21
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398225(v=OCS.15)
ms:contentKeyID: 48183491
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2a4642a9e0c77d9cf3aa77c146ff692a7fa7a6c2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763891"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="granting-setup-permissions-in-lync-server-2013"></a>Lync Server 2013 でのセットアップ アクセス許可の付与

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-08-27_

WriteSPN アクセス許可コマンドレットを使用**して、** 指定した Active Directory 組織単位 (OU) の RTCUniversalServerAdmins グループに読み取り、書き込み、readspn、およびのアクセス許可を追加することができます。 その後、その OU の RTCUniversalServerAdmins グループのメンバーは、ドメイン管理者グループのメンバーにならずに、指定したドメインで Lync Server 2013 を実行しているサーバーをインストールできます。

**Cssetuppermission**コマンドレットを使用して、設定したアクセス許可を確認します。これには、**グラント setuppermission**コマンドレットを使用します。

無効にした場合は、 **Revoke setuppermissions**コマンドレットを使用して、**付与**したアクセス許可を削除できます。

<div>

## <a name="to-grant-setup-permissions"></a>セットアップのアクセス許可を付与するには

1.  セットアップのアクセス許可を付与するドメインの、Lync Server 2013 を実行しているコンピューターにログオンします。 OU が別の子ドメインにある場合は、Domain Admins グループまたは Enterprise Admins グループのメンバーであるアカウントを使用します。

2.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

3.  次のコマンドレットを実行します。
    
        Grant-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    指定したドメインの既定の名前付けコンテキスト (たとえば、CN = computers) を基準として、ComputerOu パラメーターを指定できます。 または、このパラメーターを完全な OU 識別名 (DN) として指定することもできます (たとえば、"CN = computers, DC = Contoso, DC = com")。 後者の場合、指定したドメインと一貫性のある OU DN を指定する必要があります。
    
    Domain パラメーターを指定しない場合、既定値はローカルドメインです。

</div>

<div>

## <a name="to-verify-setup-permissions"></a>セットアップのアクセス許可を確認するには

1.  アクセス許可を**付与**したドメイン内の Lync Server 2013 を実行しているコンピューターにログオンします。このコマンドレットを使用して、付与したセットアップのアクセス許可を確認します。 OU が別の子ドメインにある場合は、Domain Admins グループまたは Enterprise Admins グループのメンバーであるアカウントを使用します。

2.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

3.  次のコマンドレットを実行します。
    
        Test-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside> [-Domain <Domain FQDN>]
    
    指定したドメインの既定の名前付けコンテキスト (たとえば、CN = computers) を基準として、ComputerOu パラメーターを指定できます。 または、このパラメーターを完全な OU 識別名 (DN) として指定することもできます (たとえば、"CN = computers, DC = Contoso, DC = com")。 後者の場合、指定したドメインと一貫性のある OU DN を指定する必要があります。
    
    Domain パラメーターを指定しない場合、既定値はローカルドメインです。

</div>

<div>

## <a name="to-revoke-setup-permissions"></a>セットアップのアクセス許可を取り消すには

1.  **グラント Setuppermission**コマンドレットによって付与されたセットアップのアクセス許可を取り消すドメインで、Lync Server 2013 を実行しているコンピューターにログオンします。 OU が別の子ドメインにある場合は、Domain Admins グループまたは Enterprise Admins グループのメンバーであるアカウントを使用します。

2.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

3.  次のコマンドレットを実行します。
    
        Revoke-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    指定したドメインの既定の名前付けコンテキスト (たとえば、CN = computers) を基準として、ComputerOu パラメーターを指定できます。 または、このパラメーターを完全な OU 識別名 (DN) として指定することもできます (たとえば、"CN = computers, DC = Contoso, DC = com")。 後者の場合、指定したドメインと一貫性のある OU DN を指定する必要があります。
    
    Domain パラメーターを指定しない場合、既定値はローカルドメインです。

</div>

</div>

<span> </span>

</div>

</div>

</div>

