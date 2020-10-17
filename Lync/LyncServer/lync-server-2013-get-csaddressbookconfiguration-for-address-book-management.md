---
title: 'Lync Server 2013: アドレス帳管理の Get-CsAddressBookConfiguration'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Get-CsAddressBookConfiguration for Address Book management
ms:assetid: bd62f916-caf3-4e10-ada4-631bbb331ef1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429721(v=OCS.15)
ms:contentKeyID: 48185264
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03a13705381c127a6c2c04e7c4ffa70214c49cb6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512644"
---
# <a name="get-csaddressbookconfiguration-for-address-book-management-in-lync-server-2013"></a>Lync Server 2013 でのアドレス帳管理の Get-CsAddressBookConfiguration

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-11-01_

このコマンドレットを実行できる人は次のとおりです。 既定では、次のグループのメンバーが Get-CsAddressBookConfiguration コマンドレットをローカルで実行することを承認されています。 RTCUniversalServerAdmins。 このコマンドレットが割り当てられているすべての役割ベースのアクセス制御 (RBAC) の役割の一覧 (自身が作成したカスタムの RBAC の役割を含む) を戻すには、Windows PowerShell プロンプトから次のコマンドを実行します。

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsAddressBookConfiguration"}

Get-CsAddressBookConfiguration コマンドレットは、既存の構成に関する情報を返します。

次にその例を示します。

    Get-CsAddressBookConfiguration -Identity site:Redmond

Get-CsAddressBookConfiguration と Set-CsAddressBookConfiguration の機能を組み合わせることで、管理者は変更する構成を定義して、変更を適用することができます。 たとえば、次のように組み合わせます。

    Get-CsAddressBookConfiguration -Filter site:* | Set-CsAddressBookConfiguration -RunTimeOfDay 23:00

すべてのサイトの構成を返し、RunTimeOfDay を 23:00 にして、これらの構成に適用しています。

<div>

## <a name="see-also"></a>関連項目


[-CsAddressBookConfiguration の取得](https://docs.microsoft.com/powershell/module/skype/Get-CsAddressBookConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

