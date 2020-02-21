---
title: 'Lync Server 2013: Set-cswebserviceconfiguration のアドレス帳管理のための削除'
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
ms.openlocfilehash: 960d0e6cc392af3189cfe2602657cafd434d47a7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183190"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-cswebserviceconfiguration-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="a15d0-102">Set-cswebserviceconfiguration Lync Server 2013 でのアドレス帳管理のための削除</span><span class="sxs-lookup"><span data-stu-id="a15d0-102">Remove-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a15d0-103">_**トピックの最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="a15d0-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="a15d0-p101">このコマンドレットを実行できる人は次のとおりです。 既定では、次のグループのメンバーが、Remove-CsWebServiceConfiguration コマンドレットをローカルで実行することを承認されています。 RTCUniversalServerAdmins。 このコマンドレットが割り当てられているすべての役割ベースのアクセス制御 (RBAC) の役割の一覧 (自身が作成したカスタムの RBAC の役割を含む) を戻すには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="a15d0-p101">Who can run this cmdlet: By default, members of the following groups are authorized to run the Remove-CsWebServiceConfiguration cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Remove-CsWebServiceConfiguration"}

<span data-ttu-id="a15d0-p102">Remove-CsWebServiceConfiguration コマンドレットを使用して、管理者は以前に作成した Web サービス構成を削除できます。 このコマンドレットで、グローバル Web サービス構成を削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="a15d0-p102">The Remove-CsWebServiceConfiguration cmdlet allows an administrator to remove a previously created Web Services configuration. The cmdlet cannot remove the global Web Services configuration.</span></span>

<span data-ttu-id="a15d0-108">次にその例を示します。</span><span class="sxs-lookup"><span data-stu-id="a15d0-108">For example:</span></span>

    Remove-CsWebServiceConfiguration -Identity site:Redmond

<div>

## <a name="see-also"></a><span data-ttu-id="a15d0-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="a15d0-109">See Also</span></span>


[<span data-ttu-id="a15d0-110">Set-cswebserviceconfiguration</span><span class="sxs-lookup"><span data-stu-id="a15d0-110">Remove-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsWebServiceConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

