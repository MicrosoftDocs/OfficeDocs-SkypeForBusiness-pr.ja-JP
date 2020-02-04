---
title: 'Lync Server 2013: アドレス帳管理用の新しい CsClientPolicy'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New-CsClientPolicy for Address Book management
ms:assetid: ef4415fc-82c4-4dc8-97d1-37a084553343
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429726(v=OCS.15)
ms:contentKeyID: 48185771
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f68f6cfa2fde4d1e5a2bc58a36478a60060dd5e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765758"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-csclientpolicy-for-address-book-management-in-lync-server-2013"></a>Lync Server 2013 でのアドレス帳管理用の新しい CsClientPolicy

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-11-01_

このコマンドレットを実行できるのはどのユーザーですか。既定では、次のグループのメンバーは、新しい-CsClientPolicy コマンドレット: RTCUniversalServerAdmins を実行することを許可されています。 このコマンドレットが割り当てられているすべての役割ベースのアクセス制御 (RBAC) ロールのリストを返すには (自分自身で作成したカスタム RBAC ロールを含む)、Windows PowerShell プロンプトから次のコマンドを実行します。

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "New-CsClientPolicy"}

このコマンドレットの新しい Clientpolicy によって、Lync Server 2013 で利用できる機能のクライアントプロビジョニングのための多数の設定が定義されます。 アドレス帳サービスの場合は、パラメーター住所録の可用性が重要です。 このパラメーターは、クライアントで利用できるオプションに直接影響を与えます。次の3つのオプションがあります。

  - WebSearchAndFileDownload

  - WebSearchOnly

  - FileDownloadOnly

定義すると、クライアントがアドレス帳にどのようにアクセスするかを決定します。 このパラメーターを定義する場合は、いずれかのオプションを定義する必要があります。 この設定を変更しない場合、既定の WebSearchAndFileDownload は有効なままになります。

次に例を示します。

    New-CsClientPolicy -Identity RedmondClientPolicy -DisableCalendarPresence $True -DisablePhonePresence $True -DisplayPhoto "PhotosFromADOnly" -AddressBookAvailability "WebSearchOnly"

<div>

## <a name="see-also"></a>関連項目


[New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

