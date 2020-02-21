---
title: 'Lync Server 2013: Set-cswebserviceconfiguration のアドレス帳管理用に設定します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set-CsWebServiceConfiguration for Address Book management
ms:assetid: 79d0edf5-23f3-4845-a7b7-e11b5a928bab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429709(v=OCS.15)
ms:contentKeyID: 48184572
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2ddd099b9705e2ec92ebd3e3f177755aed135d9b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182210"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="set-cswebserviceconfiguration-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="1d202-102">Set-cswebserviceconfiguration Lync Server 2013 でのアドレス帳管理用の設定</span><span class="sxs-lookup"><span data-stu-id="1d202-102">Set-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1d202-103">_**トピックの最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="1d202-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="1d202-p101">このコマンドレットを実行できる人は次のとおりです。 既定では、次のグループのメンバーが Set-CsWebServiceConfiguration コマンドレットをローカルで実行することを承認されています。 RTCUniversalServerAdmins。 このコマンドレットが割り当てられているすべての役割ベースのアクセス制御 (RBAC) の役割の一覧 (自身が作成したカスタムの RBAC の役割を含む) を戻すには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="1d202-p101">Who can run this cmdlet: By default, members of the following groups are authorized to run the Set-CsWebServiceConfiguration cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsWebServiceConfiguration"}

<span data-ttu-id="1d202-106">Set-CsWebServiceConfiguration コマンドレットを使用すると、管理者は Web サービスの構成内の既存の属性を再定義できます。</span><span class="sxs-lookup"><span data-stu-id="1d202-106">The Set-CsWebServiceConfiguration cmdlet allows the administrator to redefine an existing attribute in the configuration of the Web Services.</span></span>

<span data-ttu-id="1d202-107">次にその例を示します。</span><span class="sxs-lookup"><span data-stu-id="1d202-107">For example:</span></span>

    Set-CsWebServiceConfiguration -Identity site:Redmond -EnableGroupExpansion $True

<div>

## <a name="see-also"></a><span data-ttu-id="1d202-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="1d202-108">See Also</span></span>


[<span data-ttu-id="1d202-109">Set-cswebserviceconfiguration</span><span class="sxs-lookup"><span data-stu-id="1d202-109">Set-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

