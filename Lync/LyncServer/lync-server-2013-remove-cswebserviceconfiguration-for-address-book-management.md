---
title: 'Lync Server 2013: アドレス帳管理の Remove-CsWebServiceConfiguration'
description: 'Lync Server 2013: アドレス帳管理用に Remove-CsWebServiceConfiguration します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remove-CsWebServiceConfiguration for Address Book management
ms:assetid: 91947cad-5cdd-41b9-83e1-650703c55879
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429713(v=OCS.15)
ms:contentKeyID: 48184848
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 145cb1cb98bcb4c988a8fdaea74a4eae86d5fc4f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553513"
---
# <a name="remove-cswebserviceconfiguration-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="5d46e-103">Lync Server 2013 でのアドレス帳管理の Remove-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="5d46e-103">Remove-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5d46e-104">_**トピックの最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="5d46e-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="5d46e-p101">このコマンドレットを実行できる人は次のとおりです。 既定では、次のグループのメンバーが、Remove-CsWebServiceConfiguration コマンドレットをローカルで実行することを承認されています。 RTCUniversalServerAdmins。 このコマンドレットが割り当てられているすべての役割ベースのアクセス制御 (RBAC) の役割の一覧 (自身が作成したカスタムの RBAC の役割を含む) を戻すには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5d46e-p101">Who can run this cmdlet: By default, members of the following groups are authorized to run the Remove-CsWebServiceConfiguration cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Remove-CsWebServiceConfiguration"}

<span data-ttu-id="5d46e-p102">Remove-CsWebServiceConfiguration コマンドレットを使用して、管理者は以前に作成した Web サービス構成を削除できます。 このコマンドレットで、グローバル Web サービス構成を削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="5d46e-p102">The Remove-CsWebServiceConfiguration cmdlet allows an administrator to remove a previously created Web Services configuration. The cmdlet cannot remove the global Web Services configuration.</span></span>

<span data-ttu-id="5d46e-109">次にその例を示します。</span><span class="sxs-lookup"><span data-stu-id="5d46e-109">For example:</span></span>

    Remove-CsWebServiceConfiguration -Identity site:Redmond

<div>

## <a name="see-also"></a><span data-ttu-id="5d46e-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="5d46e-110">See Also</span></span>


[<span data-ttu-id="5d46e-111">Set-cswebserviceconfiguration</span><span class="sxs-lookup"><span data-stu-id="5d46e-111">Remove-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsWebServiceConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

