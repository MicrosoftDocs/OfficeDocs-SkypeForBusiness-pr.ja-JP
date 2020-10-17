---
title: 'Lync Server 2013: アドレス帳管理の Get-CsWebServiceConfiguration'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Get-CsWebServiceConfiguration for Address Book management
ms:assetid: 0b223733-5224-47d1-9b47-2109e6f135c9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429692(v=OCS.15)
ms:contentKeyID: 48183372
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 143b4964de91c10f2fce0272d6e882ff68c9f862
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512634"
---
# <a name="get-cswebserviceconfiguration-for-address-book-management-in-lync-server-2013"></a>Lync Server 2013 でのアドレス帳管理の Get-CsWebServiceConfiguration

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-11-01_

このコマンドレットを実行できる人は次のとおりです。 既定では、次のグループのメンバーが、Get-CsWebServiceConfiguration コマンドレットのローカル実行を承認されています。 RTCUniversalUserAdmins、RTCUniversalServerAdmins。 このコマンドレットが割り当てられているすべての役割ベースのアクセス制御 (RBAC) の役割の一覧 (自身が作成したカスタムの RBAC の役割を含む) を戻すには、Windows PowerShell プロンプトから次のコマンドを実行します。

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsWebServiceConfiguration"}

Get-CsWebServiceConfiguration は、現在組織で使用されている Web サービス構成の情報を戻します。 アドレス帳サービスにとって、配布リスト拡張機能のステータスは重要です。 EnableGroupExpansion 属性が True の場合、現在、ユーザーの組織はグループ拡張を許可しています。

次にその例を示します。

    Get-CsWebServiceConfiguration -Identity site:Redmond

<div>

## <a name="see-also"></a>関連項目


[Set-cswebserviceconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsWebServiceConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

