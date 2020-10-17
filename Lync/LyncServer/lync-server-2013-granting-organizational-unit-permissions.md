---
title: 'Lync Server 2013: 組織単位アクセス許可の付与'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Granting organizational unit permissions
ms:assetid: 95ee5ffa-39b1-4d80-87a2-27bb364f7396
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398763(v=OCS.15)
ms:contentKeyID: 48184849
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d17715718d66530686009fdc4b2b9e2acebfceaf
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498904"
---
# <a name="granting-organizational-unit-permissions-in-lync-server-2013"></a>Lync Server 2013 での組織単位アクセス許可の付与

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-05-14_

**付与-CsOuPermission**コマンドレットを使用して、フォレストの準備によって作成された RTC ユニバーサルグループのメンバーが Domain Admins グループのメンバーでない場合にアクセスできるように、指定された組織単位 (ou) 内のオブジェクトにアクセス許可を付与できます。 指定された OU に追加されるアクセス許可は、ドメインの準備中に、[有効にする] **-CsAdDomain** コマンドレットによってコンピューターとユーザーコンテナーに追加されるアクセス許可と同じです。

Permissions **-CsOuPermission**コマンドレットを使用して、設定したアクセス許可を確認するには、 **Test-csoupermission**コマンドレットを使用します。

**Revoke-CsOuPermission**コマンドレットを使用して、 **Grant-csoupermission**コマンドレットを使用して付与したアクセス許可を削除できます。

<div>

## <a name="to-grant-ou-permissions"></a>OU アクセス許可を付与するには

1.  OU アクセス許可を付与するドメインで、Lync Server 2013 を実行しているコンピューターにログオンします。 OU が別の子ドメインに存在する場合、Domain Admins グループまたは Enterprise Admins グループのメンバーであるアカウントを使用します。

2.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

3.  実行
    
        Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    Domain パラメーターを指定しない場合、既定値はローカル ドメインになります。

</div>

<div>

## <a name="to-verify-ou-permissions"></a>OU アクセス許可を確認するには

1.  **グラント-CsOuPermission**コマンドレットを使用して付与した OU アクセス許可を確認するドメイン内の、Lync Server 2013 を実行しているコンピューターにログオンします。 OU が別の子ドメインに存在する場合、Domain Admins グループまたは Enterprise Admins グループのメンバーであるアカウントを使用します。

2.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

3.  実行
    
        Test-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    Domain パラメーターを指定しない場合、既定値はローカル ドメインになります。

</div>

<div>

## <a name="to-revoke-ou-permissions"></a>OU アクセス許可を無効にするには

1.  **グラント-CsOuPermission**コマンドレットによって付与された OU アクセス許可を取り消すドメインで、Lync Server 2013 を実行しているコンピューターにログオンします。 OU が別の子ドメインに存在する場合、Domain Admins グループまたは Enterprise Admins グループのメンバーであるアカウントを使用します。

2.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

3.  実行
    
        Revoke-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    Domain パラメーターを指定しない場合、既定値はローカル ドメインになります。

</div>

</div>

<span> </span>

</div>

</div>

</div>

