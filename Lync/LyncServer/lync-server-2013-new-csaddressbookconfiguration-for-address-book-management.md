---
title: 'Lync Server 2013: アドレス帳管理用の新しい-CsAddressBookConfiguration'
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
ms.openlocfilehash: e69c1ea9c68dfacb68ada70d4f7643b2777f062f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765768"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-csaddressbookconfiguration-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="15faf-102">Lync Server 2013 でのアドレス帳管理用の新しい CsAddressBookConfiguration</span><span class="sxs-lookup"><span data-stu-id="15faf-102">New-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="15faf-103">_**最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="15faf-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="15faf-104">このコマンドレットを実行できるユーザー: 既定では、次のグループのメンバーは、新しい-CsAddressBookConfiguration コマンドレットをローカルで実行することを許可されています。 RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="15faf-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the New-CsAddressBookConfiguration cmdlet locally: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="15faf-105">このコマンドレットが割り当てられているすべての役割ベースのアクセス制御 (RBAC) ロールのリストを返すには (自分自身で作成したカスタム RBAC ロールを含む)、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="15faf-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "New-CsAddressBookConfiguration"}

<span data-ttu-id="15faf-106">新しい-CsAddressBookConfiguration コマンドレットは、アドレス帳の動作を管理するための新しい構成を作成します。</span><span class="sxs-lookup"><span data-stu-id="15faf-106">The New-CsAddressBookConfiguration cmdlet creates a new configuration to manage the behavior of the Address book.</span></span> <span data-ttu-id="15faf-107">このコマンドレットに固有の機能は、アドレス帳サービスがクライアントのダウンロードファイルを作成するかどうか、正規化ルールを使用するかどうか、デルタとコンパクトな差分ファイルの保持期間、新しいフルファイル作成を組み込む前のファイルサイズを定義することです。ファイルの完全なアドレス帳が作成され、ユーザーデータベース内の情報がどのように同期されるか。</span><span class="sxs-lookup"><span data-stu-id="15faf-107">Specific to this cmdlet is the ability to define if the Address Book Service creates the client download files, how and if normalization rules are used, how long to retain delta and compact delta files, delta file size before incorporating a new full file creation, what time of day the full file Address Book is created, and what the internal should be for synchronization of information in the User database.</span></span>

<span data-ttu-id="15faf-108">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="15faf-108">For example:</span></span>

    New-CsAddressBookConfiguration -Identity site:Redmond -KeepDuration 15 -SynchronizePollingInterval 00:10:00

<div>

## <a name="see-also"></a><span data-ttu-id="15faf-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="15faf-109">See Also</span></span>


[<span data-ttu-id="15faf-110">New-CsAddressBookConfiguration</span><span class="sxs-lookup"><span data-stu-id="15faf-110">New-CsAddressBookConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAddressBookConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

