---
title: 'Lync Server 2013: アドレス帳の管理のための設定を取得する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Get-CsAddressBookConfiguration for Address Book management
ms:assetid: bd62f916-caf3-4e10-ada4-631bbb331ef1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429721(v=OCS.15)
ms:contentKeyID: 48185264
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 32cf7be49d38db8f0b5b520247830f65cac5a3c6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833133"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="get-csaddressbookconfiguration-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="bf2f8-102">Lync Server 2013 でのアドレス帳管理のための設定を取得する</span><span class="sxs-lookup"><span data-stu-id="bf2f8-102">Get-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bf2f8-103">_**最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="bf2f8-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="bf2f8-104">このコマンドレットを実行できるのはどのユーザーですか。既定では、次のグループのメンバーは、RTCUniversalServerAdmins コマンドレットをローカルで実行する権限を持っています。</span><span class="sxs-lookup"><span data-stu-id="bf2f8-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the Get-CsAddressBookConfiguration cmdlet locally: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="bf2f8-105">このコマンドレットが割り当てられているすべての役割ベースのアクセス制御 (RBAC) ロールのリストを返すには (自分自身で作成したカスタム RBAC ロールを含む)、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="bf2f8-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsAddressBookConfiguration"}

<span data-ttu-id="bf2f8-106">このコマンドレットは、既に存在する構成についての情報を返します。</span><span class="sxs-lookup"><span data-stu-id="bf2f8-106">The cmdlet Get-CsAddressBookConfiguration returns information about a configuration that already exists.</span></span>

<span data-ttu-id="bf2f8-107">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="bf2f8-107">For example:</span></span>

    Get-CsAddressBookConfiguration -Identity site:Redmond

<span data-ttu-id="bf2f8-108">Get-CsAddressBookConfiguration と Set-CsAddressBookConfiguration の機能を組み合わせると、管理者は、変更する構成を定義して、変更を適用することができます。</span><span class="sxs-lookup"><span data-stu-id="bf2f8-108">Combining the functionality of Get-CsAddressBookConfiguration and Set-CsAddressBookConfiguration allows the administrator to define which configurations to modify and then apply the modifications.</span></span> <span data-ttu-id="bf2f8-109">たとえば、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="bf2f8-109">For example, this combined:</span></span>

    Get-CsAddressBookConfiguration -Filter site:* | Set-CsAddressBookConfiguration -RunTimeOfDay 23:00

<span data-ttu-id="bf2f8-110">すべてのサイト内のすべての構成を返し、23:00 時間の RunTimeOfDay を構成に適用します。</span><span class="sxs-lookup"><span data-stu-id="bf2f8-110">Returns all configurations in all sites and applies the RunTimeOfDay of 23:00 hours to the configurations.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="bf2f8-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="bf2f8-111">See Also</span></span>


[<span data-ttu-id="bf2f8-112">CsAddressBookConfiguration の入手</span><span class="sxs-lookup"><span data-stu-id="bf2f8-112">Get-CsAddressBookConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAddressBookConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

