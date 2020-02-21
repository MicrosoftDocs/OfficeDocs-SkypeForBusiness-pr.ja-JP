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
ms.openlocfilehash: 30ee2dff06f2881906793043f1dc039f57919a67
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42216963"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="new-csclientpolicy-for-address-book-management-in-lync-server-2013"></a>Lync Server 2013 でのアドレス帳管理用の新しい-CsClientPolicy

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-11-01_

このコマンドレットを実行できるユーザー: 既定では、次のグループのメンバーが新しい-CsClientPolicy コマンドレットを実行することを承認されています: RTCUniversalServerAdmins。 このコマンドレットが割り当てられているすべての役割ベースのアクセス制御 (RBAC) の役割の一覧 (自身が作成したカスタムの RBAC の役割を含む) を戻すには、Windows PowerShell プロンプトから次のコマンドを実行します。

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "New-CsClientPolicy"}

コマンドレットの新しい Clientpolicy は、Lync Server 2013 で利用可能な機能のためのクライアントプロビジョニングのための多数の設定を定義します。 アドレス帳サービスの場合、関心の対象は AddressBookAvailability パラメーターです。 クライアントが利用できるオプションに直接影響するこのパラメーターには、次に示す 3 つの設定可能なオプションがあります。

  - WebSearchAndFileDownload

  - WebSearchOnly

  - FileDownloadOnly

定義すると、クライアントがアドレス帳にアクセスするときの方法が決まります。 このパラメーターを定義する場合は、オプションの 1 つを定義する必要があります。 この設定を変更しない場合は、既定の WebSearchAndFileDownload が有効なままになります。

次にその例を示します。

    New-CsClientPolicy -Identity RedmondClientPolicy -DisableCalendarPresence $True -DisablePhonePresence $True -DisplayPhoto "PhotosFromADOnly" -AddressBookAvailability "WebSearchOnly"

<div>

## <a name="see-also"></a>関連項目


[新しい-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

