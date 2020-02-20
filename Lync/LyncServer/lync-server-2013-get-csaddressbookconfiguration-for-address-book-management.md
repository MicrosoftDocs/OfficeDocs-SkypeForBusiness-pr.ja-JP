---
title: 'Lync Server 2013: アドレス帳管理用の Get-CsAddressBookConfiguration'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Get-CsAddressBookConfiguration for Address Book management
ms:assetid: bd62f916-caf3-4e10-ada4-631bbb331ef1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429721(v=OCS.15)
ms:contentKeyID: 48185264
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 36d6811dc410a37ac885bd569e0a1474bb9a4dd0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147450"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="get-csaddressbookconfiguration-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="dbf83-102">Lync Server 2013 でのアドレス帳管理用の-CsAddressBookConfiguration の取得</span><span class="sxs-lookup"><span data-stu-id="dbf83-102">Get-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dbf83-103">_**トピックの最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="dbf83-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="dbf83-p101">このコマンドレットを実行できる人は次のとおりです。 既定では、次のグループのメンバーが Get-CsAddressBookConfiguration コマンドレットをローカルで実行することを承認されています。 RTCUniversalServerAdmins。 このコマンドレットが割り当てられているすべての役割ベースのアクセス制御 (RBAC) の役割の一覧 (自身が作成したカスタムの RBAC の役割を含む) を戻すには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="dbf83-p101">Who can run this cmdlet: By default, members of the following groups are authorized to run the Get-CsAddressBookConfiguration cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsAddressBookConfiguration"}

<span data-ttu-id="dbf83-106">Get-CsAddressBookConfiguration コマンドレットは、既存の構成に関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="dbf83-106">The cmdlet Get-CsAddressBookConfiguration returns information about a configuration that already exists.</span></span>

<span data-ttu-id="dbf83-107">次にその例を示します。</span><span class="sxs-lookup"><span data-stu-id="dbf83-107">For example:</span></span>

    Get-CsAddressBookConfiguration -Identity site:Redmond

<span data-ttu-id="dbf83-p102">Get-CsAddressBookConfiguration と Set-CsAddressBookConfiguration の機能を組み合わせることで、管理者は変更する構成を定義して、変更を適用することができます。 たとえば、次のように組み合わせます。</span><span class="sxs-lookup"><span data-stu-id="dbf83-p102">Combining the functionality of Get-CsAddressBookConfiguration and Set-CsAddressBookConfiguration allows the administrator to define which configurations to modify and then apply the modifications. For example, this combined:</span></span>

    Get-CsAddressBookConfiguration -Filter site:* | Set-CsAddressBookConfiguration -RunTimeOfDay 23:00

<span data-ttu-id="dbf83-110">すべてのサイトの構成を返し、RunTimeOfDay を 23:00 にして、これらの構成に適用しています。</span><span class="sxs-lookup"><span data-stu-id="dbf83-110">Returns all configurations in all sites and applies the RunTimeOfDay of 23:00 hours to the configurations.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="dbf83-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="dbf83-111">See Also</span></span>


[<span data-ttu-id="dbf83-112">-CsAddressBookConfiguration の取得</span><span class="sxs-lookup"><span data-stu-id="dbf83-112">Get-CsAddressBookConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAddressBookConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

