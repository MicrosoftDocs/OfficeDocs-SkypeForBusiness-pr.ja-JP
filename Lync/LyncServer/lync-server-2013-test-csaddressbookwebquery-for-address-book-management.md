---
title: 'Lync Server 2013: アドレス帳管理用のテスト-CsAddressBookWebQuery'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test-CsAddressBookWebQuery for Address Book management
ms:assetid: 977a9c1f-5f4e-4539-9a26-8748b61a57d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429716(v=OCS.15)
ms:contentKeyID: 48184865
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a2481ff48e1156bd0cbbb478db213dbb02d2912
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42021778"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-csaddressbookwebquery-for-address-book-management-in-lync-server-2013"></a>Lync Server 2013 でのアドレス帳管理用のテスト-CsAddressBookWebQuery

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-11-01_

このコマンドレットを実行できるユーザー: 既定では、次のグループのメンバーが、RTCUniversalServerAdmins コマンドレットの実行を承認されています。 このコマンドレットが割り当てられているすべての役割ベースのアクセス制御 (RBAC) の役割の一覧 (自身が作成したカスタムの RBAC の役割を含む) を戻すには、Windows PowerShell プロンプトから次のコマンドを実行します。

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Test-CsAddressBookService"}

Test-CsAddressBookWebQuery と同様に、Test-CsAddressBookWebQuery は、アドレス帳 Web クエリに対してクエリを実行して、正常に動作していることを確認します。 コマンドレットは、Web チケット認証に接続し、-UserCredential で指定された資格情報を提示します。 認証された場合、コマンドレットは– TargetSipAddress 情報を表示します。 このコマンドレットは、連絡先に関する情報を取得できた場合に成功を報告します。

次に例を示します。

    Test-CsAddressBookWebQuery -TargetFqdn atl-cs-001.contoso.com -UserCredential contoso\bob -UserSipAddress "sip:bob@contoso.com" -TargetSipAddress "sip:bob@contoso.com"

<div>

## <a name="see-also"></a>関連項目


[Test-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

