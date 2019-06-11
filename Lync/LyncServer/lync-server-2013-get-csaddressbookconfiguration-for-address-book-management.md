---
title: 'Lync Server 2013: アドレス帳の管理のための設定を取得する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Get-CsAddressBookConfiguration for Address Book management
ms:assetid: bd62f916-caf3-4e10-ada4-631bbb331ef1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429721(v=OCS.15)
ms:contentKeyID: 48185264
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 32cf7be49d38db8f0b5b520247830f65cac5a3c6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833133"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="get-csaddressbookconfiguration-for-address-book-management-in-lync-server-2013"></a>Lync Server 2013 でのアドレス帳管理のための設定を取得する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-11-01_

このコマンドレットを実行できるのはどのユーザーですか。既定では、次のグループのメンバーは、RTCUniversalServerAdmins コマンドレットをローカルで実行する権限を持っています。 このコマンドレットが割り当てられているすべての役割ベースのアクセス制御 (RBAC) ロールのリストを返すには (自分自身で作成したカスタム RBAC ロールを含む)、Windows PowerShell プロンプトから次のコマンドを実行します。

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsAddressBookConfiguration"}

このコマンドレットは、既に存在する構成についての情報を返します。

次に例を示します。

    Get-CsAddressBookConfiguration -Identity site:Redmond

Get-CsAddressBookConfiguration と Set-CsAddressBookConfiguration の機能を組み合わせると、管理者は、変更する構成を定義して、変更を適用することができます。 たとえば、次のようになります。

    Get-CsAddressBookConfiguration -Filter site:* | Set-CsAddressBookConfiguration -RunTimeOfDay 23:00

すべてのサイト内のすべての構成を返し、23:00 時間の RunTimeOfDay を構成に適用します。

<div>

## <a name="see-also"></a>関連項目


[CsAddressBookConfiguration の入手](https://docs.microsoft.com/powershell/module/skype/Get-CsAddressBookConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

