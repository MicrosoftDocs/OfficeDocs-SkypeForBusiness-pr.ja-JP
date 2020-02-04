---
title: 'Lync Server 2013: アドレス帳の管理用に CsClientPolicy を設定する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set-CsClientPolicy for Address Book management
ms:assetid: e7788bea-606f-481a-a3a4-1855ac028493
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429723(v=OCS.15)
ms:contentKeyID: 48185726
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 608f55660908a0fe6af3aa08aa8dd81f1fec0cf0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764683"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-csclientpolicy-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="5605b-102">Lync Server 2013 でのアドレス帳管理のための CsClientPolicy の設定</span><span class="sxs-lookup"><span data-stu-id="5605b-102">Set-CsClientPolicy for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5605b-103">_**最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="5605b-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="5605b-104">このコマンドレットを実行できるのはどのユーザーですか。既定では、次のグループのメンバーは、Set-CsClientPolicy コマンドレットをローカルで実行することを許可されています。 RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="5605b-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the Set-CsClientPolicy cmdlet locally: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="5605b-105">このコマンドレットが割り当てられているすべての役割ベースのアクセス制御 (RBAC) ロールのリストを返すには (自分自身で作成したカスタム RBAC ロールを含む)、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5605b-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClientPolicy"}

<span data-ttu-id="5605b-106">新しい CsClientPolicy と同じように、設定された Clientpolicy コマンドレットを使用して、既に配置されているクライアント設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="5605b-106">Similar to New-CsClientPolicy, the Set-CsClientPolicy cmdlet allows you to modify client settings that are already in place.</span></span>

<span data-ttu-id="5605b-107">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="5605b-107">For example:</span></span>

    Set-CsClientPolicy -Identity RedmondClientPolicy -WebServicePollInterval "00:15:00" -AddressBookAvailability "WebSearchAndFileDownload"

<div>

## <a name="see-also"></a><span data-ttu-id="5605b-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="5605b-108">See Also</span></span>


[<span data-ttu-id="5605b-109">Set-CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="5605b-109">Set-CsClientPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

