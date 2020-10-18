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
# <a name="new-csaddressbookconfiguration-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="e126b-103">Lync Server 2013 でのアドレス帳管理の New-CsAddressBookConfiguration</span><span class="sxs-lookup"><span data-stu-id="e126b-103">New-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e126b-104">_**トピックの最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="e126b-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="e126b-p101">このコマンドレットを実行できる人は次のとおりです。 既定では、次のグループのメンバーが New-CsAddressBookConfiguration コマンドレットをローカルで実行することを承認されています。 RTCUniversalServerAdmins。 このコマンドレットが割り当てられているすべての役割ベースのアクセス制御 (RBAC) の役割の一覧 (自身が作成したカスタムの RBAC の役割を含む) を戻すには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e126b-p101">Who can run this cmdlet: By default, members of the following groups are authorized to run the New-CsAddressBookConfiguration cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "New-CsAddressBookConfiguration"}

<span data-ttu-id="e126b-p102">New-CsAddressBookConfiguration コマンドレットは、アドレス帳の動作を管理する新しい構成を作成します。 アドレス帳サービスによるクライアント ダウンロード ファイルの作成の有無、正規化ルールの使用方法と使用の有無、差分ファイルと圧縮差分ファイルの保持期間、新しい完全なファイルを作成する前の圧縮ファイル サイズ、完全なファイルのアドレス帳の作成時刻、ユーザー データベース情報の同期間隔は、このコマンドレットでのみ定義できます。</span><span class="sxs-lookup"><span data-stu-id="e126b-p102">The New-CsAddressBookConfiguration cmdlet creates a new configuration to manage the behavior of the Address book. Specific to this cmdlet is the ability to define if the Address Book Service creates the client download files, how and if normalization rules are used, how long to retain delta and compact delta files, delta file size before incorporating a new full file creation, what time of day the full file Address Book is created, and what the internal should be for synchronization of information in the User database.</span></span>

<span data-ttu-id="e126b-109">次にその例を示します。</span><span class="sxs-lookup"><span data-stu-id="e126b-109">For example:</span></span>

    New-CsAddressBookConfiguration -Identity site:Redmond -KeepDuration 15 -SynchronizePollingInterval 00:10:00

<div>

## <a name="see-also"></a><span data-ttu-id="e126b-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="e126b-110">See Also</span></span>


[<span data-ttu-id="e126b-111">新しい-CsAddressBookConfiguration</span><span class="sxs-lookup"><span data-stu-id="e126b-111">New-CsAddressBookConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAddressBookConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

