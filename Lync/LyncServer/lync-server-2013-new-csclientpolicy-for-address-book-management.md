---
title: 'Lync Server 2013: アドレス帳管理の New-CsClientPolicy'
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
ms.openlocfilehash: a253fb46dfdfe63957efa97ffa68d97ead65ed87
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508824"
---
# <a name="new-csclientpolicy-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="9fb9c-102">Lync Server 2013 でのアドレス帳管理の New-CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="9fb9c-102">New-CsClientPolicy for Address Book management in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9fb9c-103">_**トピックの最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="9fb9c-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="9fb9c-104">このコマンドレットを実行できるユーザー: 既定では、次のグループのメンバーが、New-CsClientPolicy コマンドレットを実行することを承認されています。 RTCUniversalServerAdmins。</span><span class="sxs-lookup"><span data-stu-id="9fb9c-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the New-CsClientPolicy cmdlet: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="9fb9c-105">このコマンドレットが割り当てられているすべての役割ベースのアクセス制御 (RBAC) の役割の一覧 (自身が作成したカスタムの RBAC の役割を含む) を戻すには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9fb9c-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "New-CsClientPolicy"}

<span data-ttu-id="9fb9c-106">コマンドレット New-CsClientPolicy は、Lync Server 2013 で利用可能な機能のためのプロビジョニングクライアントに対して多数の設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="9fb9c-106">The cmdlet New-CsClientPolicy defines a large number of settings for provisioning clients for features that are available in Lync Server 2013.</span></span> <span data-ttu-id="9fb9c-107">アドレス帳サービスの場合、関心の対象は AddressBookAvailability パラメーターです。</span><span class="sxs-lookup"><span data-stu-id="9fb9c-107">For the Address Book Service, the parameter AddressBookAvailability is of interest.</span></span> <span data-ttu-id="9fb9c-108">クライアントが利用できるオプションに直接影響するこのパラメーターには、次に示す 3 つの設定可能なオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="9fb9c-108">This parameter, which directly impacts the options available to clients, has three possible options:</span></span>

  - <span data-ttu-id="9fb9c-109">WebSearchAndFileDownload</span><span class="sxs-lookup"><span data-stu-id="9fb9c-109">WebSearchAndFileDownload</span></span>

  - <span data-ttu-id="9fb9c-110">WebSearchOnly</span><span class="sxs-lookup"><span data-stu-id="9fb9c-110">WebSearchOnly</span></span>

  - <span data-ttu-id="9fb9c-111">FileDownloadOnly</span><span class="sxs-lookup"><span data-stu-id="9fb9c-111">FileDownloadOnly</span></span>

<span data-ttu-id="9fb9c-p103">定義すると、クライアントがアドレス帳にアクセスするときの方法が決まります。 このパラメーターを定義する場合は、オプションの 1 つを定義する必要があります。 この設定を変更しない場合は、既定の WebSearchAndFileDownload が有効なままになります。</span><span class="sxs-lookup"><span data-stu-id="9fb9c-p103">When defined, it determines how the Address Book is accessed by clients. If you define this parameter, you must define one of the options. If you do not modify this setting, the default WebSearchAndFileDownload remains in effect.</span></span>

<span data-ttu-id="9fb9c-115">次にその例を示します。</span><span class="sxs-lookup"><span data-stu-id="9fb9c-115">For example:</span></span>

    New-CsClientPolicy -Identity RedmondClientPolicy -DisableCalendarPresence $True -DisablePhonePresence $True -DisplayPhoto "PhotosFromADOnly" -AddressBookAvailability "WebSearchOnly"

<div>

## <a name="see-also"></a><span data-ttu-id="9fb9c-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="9fb9c-116">See Also</span></span>


[<span data-ttu-id="9fb9c-117">新しい-CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="9fb9c-117">New-CsClientPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

