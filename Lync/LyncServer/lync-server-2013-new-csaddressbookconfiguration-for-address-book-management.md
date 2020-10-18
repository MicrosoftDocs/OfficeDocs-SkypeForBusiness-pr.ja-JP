---
title: 'Lync Server 2013: アドレス帳管理の New-CsAddressBookConfiguration'
description: 'Lync Server 2013: アドレス帳管理用に New-CsAddressBookConfiguration します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New-CsAddressBookConfiguration for Address Book management
ms:assetid: a58ddc8c-ae04-4141-b69e-e45374a67d72
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429718(v=OCS.15)
ms:contentKeyID: 48184985
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c85d85fefe701456ad253f1afc69b73093b30996
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578953"
---
# <a name="new-csaddressbookconfiguration-for-address-book-management-in-lync-server-2013"></a>Lync Server 2013 でのアドレス帳管理の New-CsAddressBookConfiguration

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-11-01_

このコマンドレットを実行できる人は次のとおりです。 既定では、次のグループのメンバーが New-CsAddressBookConfiguration コマンドレットをローカルで実行することを承認されています。 RTCUniversalServerAdmins。 このコマンドレットが割り当てられているすべての役割ベースのアクセス制御 (RBAC) の役割の一覧 (自身が作成したカスタムの RBAC の役割を含む) を戻すには、Windows PowerShell プロンプトから次のコマンドを実行します。

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "New-CsAddressBookConfiguration"}

New-CsAddressBookConfiguration コマンドレットは、アドレス帳の動作を管理する新しい構成を作成します。 アドレス帳サービスによるクライアント ダウンロード ファイルの作成の有無、正規化ルールの使用方法と使用の有無、差分ファイルと圧縮差分ファイルの保持期間、新しい完全なファイルを作成する前の圧縮ファイル サイズ、完全なファイルのアドレス帳の作成時刻、ユーザー データベース情報の同期間隔は、このコマンドレットでのみ定義できます。

次にその例を示します。

    New-CsAddressBookConfiguration -Identity site:Redmond -KeepDuration 15 -SynchronizePollingInterval 00:10:00

<div>

## <a name="see-also"></a>関連項目


[新しい-CsAddressBookConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsAddressBookConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

