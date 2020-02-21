---
title: 'Lync Server 2013: アドレス帳管理用に設定-CsAddressBookConfiguration'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set-CsAddressBookConfiguration for Address Book management
ms:assetid: 3a64ceb1-9f79-4f3b-bf33-eaf346dbd60d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429700(v=OCS.15)
ms:contentKeyID: 48183913
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b728ee5a1c644b18a90345a660592e010ea791a5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182250"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="set-csaddressbookconfiguration-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="1285d-102">Lync Server 2013 でのアドレス帳管理用の設定-CsAddressBookConfiguration</span><span class="sxs-lookup"><span data-stu-id="1285d-102">Set-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1285d-103">_**トピックの最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="1285d-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="1285d-p101">このコマンドレットを実行できる人は次のとおりです。 既定では、次のグループのメンバーは Set-CsAddressBookConfiguration コマンドレットのローカル実行を承認されています。 RTCUniversalServerAdmins。 このコマンドレットが割り当てられているすべての役割ベースのアクセス制御 (RBAC) の役割の一覧 (自身が作成したカスタムの RBAC の役割を含む) を戻すには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="1285d-p101">Who can run this cmdlet: By default, members of the following groups are authorized to run the Set-CsAddressBookConfiguration cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsAddressBookConfiguration"}

<span data-ttu-id="1285d-106">Set-CsAddressBookConfiguration は、既存の構成を変更するために使用するという点を除けば、New-CsAddressBookConfiguration コマンドレットによく似ています。</span><span class="sxs-lookup"><span data-stu-id="1285d-106">Set-CsAddressBookConfiguration is similar to the New-CsAddressBookConfiguration cmdlet, except it is used to modify an existing configuration.</span></span>

<span data-ttu-id="1285d-107">次にその例を示します。</span><span class="sxs-lookup"><span data-stu-id="1285d-107">For example:</span></span>

    Set-CsAddressBookConfiguration -identity site:Redmond -RunTimeOfDay 23:00

<div>

## <a name="see-also"></a><span data-ttu-id="1285d-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="1285d-108">See Also</span></span>


[<span data-ttu-id="1285d-109">設定-CsAddressBookConfiguration</span><span class="sxs-lookup"><span data-stu-id="1285d-109">Set-CsAddressBookConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsAddressBookConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

