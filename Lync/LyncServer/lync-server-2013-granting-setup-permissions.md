---
title: 'Lync Server 2013: セットアップのアクセス許可の付与'
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
ms.openlocfilehash: 014af4f0e03a8d49e3d08c68cff169283bd007bd
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146110"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="granting-setup-permissions-in-lync-server-2013"></a>Lync Server 2013 でのセットアップのアクセス許可の付与

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-08-27_

**Grant-CsSetupPermission** コマンドレットを使用して、Read、Write、ReadSPN、および WriteSPN のアクセス許可を特定の Active Directory 組織単位 (OU) の RTCUniversalServerAdmins グループに追加できます。 その OU の RTCUniversalServerAdmins グループのメンバーは、Domain Admins グループのメンバーではなく、指定されたドメイン内の Lync Server 2013 を実行しているサーバーをインストールすることができます。

**Grant-CsSetupPermission** コマンドレットを使用して設定したアクセス許可は、**Test-CsSetupPermission** コマンドレットを使用して確認できます。

**Grant-CsSetupPermission** コマンドレットを使用して付与したアクセス許可は、**Revoke-CsSetupPermission** コマンドレットを使用して削除できます。

<div>

## <a name="to-grant-setup-permissions"></a>セットアップのアクセス許可を付与するには

1.  セットアップのアクセス許可を付与するドメインで、Lync Server 2013 を実行しているコンピューターにログオンします。 OU が別の子ドメインに存在する場合、Domain Admins グループまたは Enterprise Admins グループのメンバーであるアカウントを使用します。

2.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

3.  実行
    
        Grant-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    指定したドメインの既定の名前付けコンテキストに相対的な ComputerOu パラメーターを指定できます (CN=computer など)。または、このパラメーターに完全な OU 識別名 (DN) を指定することもできます ("CN=computers,DC=Contoso,DC=com" など)。後者の場合、指定するドメインに一致する OU DN を指定する必要があります。
    
    Domain パラメーターを指定しない場合、既定値はローカル ドメインになります。

</div>

<div>

## <a name="to-verify-setup-permissions"></a>セットアップのアクセス許可を確認するには

1.  **Grant-CsSetupPermission**コマンドレットを使用して付与したセットアップのアクセス許可を確認するドメイン内の、Lync Server 2013 を実行しているコンピューターにログオンします。 OU が別の子ドメインに存在する場合、Domain Admins グループまたは Enterprise Admins グループのメンバーであるアカウントを使用します。

2.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

3.  実行
    
        Test-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside> [-Domain <Domain FQDN>]
    
    指定したドメインの既定の名前付けコンテキストに相対的な ComputerOu パラメーターを指定できます (CN=computer など)。または、このパラメーターに完全な OU 識別名 (DN) を指定することもできます ("CN=computers,DC=Contoso,DC=com" など)。後者の場合、指定するドメインに一致する OU DN を指定する必要があります。
    
    Domain パラメーターを指定しない場合、既定値はローカル ドメインになります。

</div>

<div>

## <a name="to-revoke-setup-permissions"></a>セットアップのアクセス許可を無効にするには

1.  **グラント-CsSetupPermission**コマンドレットによって付与されたセットアップのアクセス許可を取り消すドメインで、Lync Server 2013 を実行しているコンピューターにログオンします。 OU が別の子ドメインに存在する場合、Domain Admins グループまたは Enterprise Admins グループのメンバーであるアカウントを使用します。

2.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

3.  実行
    
        Revoke-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    指定したドメインの既定の名前付けコンテキストに相対的な ComputerOu パラメーターを指定できます (CN=computer など)。または、このパラメーターに完全な OU 識別名 (DN) を指定することもできます ("CN=computers,DC=Contoso,DC=com" など)。後者の場合、指定するドメインに一致する OU DN を指定する必要があります。
    
    Domain パラメーターを指定しない場合、既定値はローカル ドメインになります。

</div>

</div>

<span> </span>

</div>

</div>

</div>

