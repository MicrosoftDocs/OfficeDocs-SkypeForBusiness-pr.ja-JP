---
title: 'Lync Server 2013: アドレス帳管理用のテスト-CsAddressBookService'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test-CsAddressBookService for Address Book management
ms:assetid: b88cea74-41fd-4c0e-9284-7135bff27a27
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429720(v=OCS.15)
ms:contentKeyID: 48185206
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 91df3f20d93ce6ee948f385bb46e8b2a0830ca31
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "41985062"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-csaddressbookservice-for-address-book-management-in-lync-server-2013"></a>Lync Server 2013 でのアドレス帳管理用のテスト-CsAddressBookService

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-11-01_

このコマンドレットを実行できる人は次のとおりです。 既定では、次のグループのメンバーが Test-CsAddressBookService コマンドレットの実行を承認されています。 RTCUniversalServerAdmins。 このコマンドレットが割り当てられているすべての役割ベースのアクセス制御 (RBAC) の役割の一覧 (自身が作成したカスタムの RBAC の役割を含む) を戻すには、Windows PowerShell プロンプトから次のコマンドを実行します。

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Test-CsAddressBookService"}

Lync Server 2013 には、固有の機能が正しく動作していることを確認するために、合成コマンドを開始する多数のコマンドレットが含まれています。 Test-CsAddressBookService は、定義済みのユーザーがアドレス帳 Web サービスからローカルファイルに接続して要求できることを確認します。

次にその例を示します。

    Test-CsAddressBookService -TargetFqdn atl-cs-001.contoso.com -UserCredential contoso\bob -UserSipAddress "sip:bob@contoso.com"

<div>

## <a name="see-also"></a>関連項目


[Test-CsAddressBookService](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

