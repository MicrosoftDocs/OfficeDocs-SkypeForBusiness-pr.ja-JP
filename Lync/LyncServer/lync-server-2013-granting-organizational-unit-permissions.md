---
title: 'Lync Server 2013: 組織単位アクセス許可の付与'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Granting organizational unit permissions
ms:assetid: 95ee5ffa-39b1-4d80-87a2-27bb364f7396
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398763(v=OCS.15)
ms:contentKeyID: 48184849
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c65ff483fbb9c63d4eaca31eca47c9093d229438
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833120"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="granting-organizational-unit-permissions-in-lync-server-2013"></a>Lync Server 2013 での組織単位アクセス許可の付与

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-05-14_

**Grant-CsOuPermission**コマンドレットを使用して、指定した組織単位 (ou) 内のオブジェクトにアクセス許可を付与することで、フォレストの準備で作成された RTC ユニバーサルグループのメンバーが Domain Admins グループのメンバーにならずにアクセスできるようにします。. 指定した OU に追加されたアクセス許可は、 **** ドメインの準備中に [コンピューターとユーザー] コンテナーに追加される [権限の付与] のアクセス許可と同じです。

ユーザー権限の**付与**コマンドレットを使用して、設定したアクセス許可を確認するには、 **csoupermission**コマンドレットを使用します。

**Revoke-csoupermission**コマンドレットを使用して、**グラント-csoupermission**コマンドレットを使用して付与したアクセス許可を削除できます。

<div>

## <a name="to-grant-ou-permissions"></a>OU 権限を付与するには

1.  OU 権限を付与するドメインの、Lync Server 2013 を実行しているコンピューターにログオンします。 OU が別の子ドメインにある場合は、Domain Admins グループまたは Enterprise Admins グループのメンバーであるアカウントを使用します。

2.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

3.  次のコマンドレットを実行します。
    
        Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    Domain パラメーターを指定しない場合、既定値はローカルドメインです。

</div>

<div>

## <a name="to-verify-ou-permissions"></a>OU 権限を確認するには

1.  **Grant-CsOuPermission**コマンドレットを使用して付与した OU 権限を確認するドメインの、Lync Server 2013 を実行しているコンピューターにログオンします。 OU が別の子ドメインにある場合は、Domain Admins グループまたは Enterprise Admins グループのメンバーであるアカウントを使用します。

2.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

3.  次のコマンドレットを実行します。
    
        Test-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    Domain パラメーターを指定しない場合、既定値はローカルドメインです。

</div>

<div>

## <a name="to-revoke-ou-permissions"></a>OU 権限を取り消すには

1.  **Grant-CsOuPermission**コマンドレットによって付与された OU 権限を取り消すドメインで、Lync Server 2013 を実行しているコンピューターにログオンします。 OU が別の子ドメインにある場合は、Domain Admins グループまたは Enterprise Admins グループのメンバーであるアカウントを使用します。

2.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

3.  次のコマンドレットを実行します。
    
        Revoke-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    Domain パラメーターを指定しない場合、既定値はローカルドメインです。

</div>

</div>

<span> </span>

</div>

</div>

</div>

