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

# <a name="new-csclientpolicy-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="b181f-102">Lync Server 2013 でのアドレス帳管理用の新しい CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="b181f-102">New-CsClientPolicy for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b181f-103">_**最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="b181f-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="b181f-104">このコマンドレットを実行できるのはどのユーザーですか。既定では、次のグループのメンバーは、新しい-CsClientPolicy コマンドレット: RTCUniversalServerAdmins を実行することを許可されています。</span><span class="sxs-lookup"><span data-stu-id="b181f-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the New-CsClientPolicy cmdlet: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="b181f-105">このコマンドレットが割り当てられているすべての役割ベースのアクセス制御 (RBAC) ロールのリストを返すには (自分自身で作成したカスタム RBAC ロールを含む)、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="b181f-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "New-CsClientPolicy"}

<span data-ttu-id="b181f-106">このコマンドレットの新しい Clientpolicy によって、Lync Server 2013 で利用できる機能のクライアントプロビジョニングのための多数の設定が定義されます。</span><span class="sxs-lookup"><span data-stu-id="b181f-106">The cmdlet New-CsClientPolicy defines a large number of settings for provisioning clients for features that are available in Lync Server 2013.</span></span> <span data-ttu-id="b181f-107">アドレス帳サービスの場合は、パラメーター住所録の可用性が重要です。</span><span class="sxs-lookup"><span data-stu-id="b181f-107">For the Address Book Service, the parameter AddressBookAvailability is of interest.</span></span> <span data-ttu-id="b181f-108">このパラメーターは、クライアントで利用できるオプションに直接影響を与えます。次の3つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="b181f-108">This parameter, which directly impacts the options available to clients, has three possible options:</span></span>

  - <span data-ttu-id="b181f-109">WebSearchAndFileDownload</span><span class="sxs-lookup"><span data-stu-id="b181f-109">WebSearchAndFileDownload</span></span>

  - <span data-ttu-id="b181f-110">WebSearchOnly</span><span class="sxs-lookup"><span data-stu-id="b181f-110">WebSearchOnly</span></span>

  - <span data-ttu-id="b181f-111">FileDownloadOnly</span><span class="sxs-lookup"><span data-stu-id="b181f-111">FileDownloadOnly</span></span>

<span data-ttu-id="b181f-112">定義すると、クライアントがアドレス帳にどのようにアクセスするかを決定します。</span><span class="sxs-lookup"><span data-stu-id="b181f-112">When defined, it determines how the Address Book is accessed by clients.</span></span> <span data-ttu-id="b181f-113">このパラメーターを定義する場合は、いずれかのオプションを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b181f-113">If you define this parameter, you must define one of the options.</span></span> <span data-ttu-id="b181f-114">この設定を変更しない場合、既定の WebSearchAndFileDownload は有効なままになります。</span><span class="sxs-lookup"><span data-stu-id="b181f-114">If you do not modify this setting, the default WebSearchAndFileDownload remains in effect.</span></span>

<span data-ttu-id="b181f-115">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="b181f-115">For example:</span></span>

    New-CsClientPolicy -Identity RedmondClientPolicy -DisableCalendarPresence $True -DisablePhonePresence $True -DisplayPhoto "PhotosFromADOnly" -AddressBookAvailability "WebSearchOnly"

<div>

## <a name="see-also"></a><span data-ttu-id="b181f-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="b181f-116">See Also</span></span>


[<span data-ttu-id="b181f-117">New-CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="b181f-117">New-CsClientPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

