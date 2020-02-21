---
title: 'Lync Server 2013: Set-cswebserviceconfiguration のアドレス帳管理のための取得'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Get-CsWebServiceConfiguration for Address Book management
ms:assetid: 0b223733-5224-47d1-9b47-2109e6f135c9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429692(v=OCS.15)
ms:contentKeyID: 48183372
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc131bdcd4713b4bdf5971825675dc770da8ec3f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213953"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="get-cswebserviceconfiguration-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="ae5d2-102">Set-cswebserviceconfiguration Lync Server 2013 でのアドレス帳管理のための取得</span><span class="sxs-lookup"><span data-stu-id="ae5d2-102">Get-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ae5d2-103">_**トピックの最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="ae5d2-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="ae5d2-p101">このコマンドレットを実行できる人は次のとおりです。 既定では、次のグループのメンバーが、Get-CsWebServiceConfiguration コマンドレットのローカル実行を承認されています。 RTCUniversalUserAdmins、RTCUniversalServerAdmins。 このコマンドレットが割り当てられているすべての役割ベースのアクセス制御 (RBAC) の役割の一覧 (自身が作成したカスタムの RBAC の役割を含む) を戻すには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="ae5d2-p101">Who can run this cmdlet: By default, members of the following groups are authorized to run the Get-CsWebServiceConfiguration cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsWebServiceConfiguration"}

<span data-ttu-id="ae5d2-p102">Get-CsWebServiceConfiguration は、現在組織で使用されている Web サービス構成の情報を戻します。 アドレス帳サービスにとって、配布リスト拡張機能のステータスは重要です。 EnableGroupExpansion 属性が True の場合、現在、ユーザーの組織はグループ拡張を許可しています。</span><span class="sxs-lookup"><span data-stu-id="ae5d2-p102">Get-CsWebServiceConfiguration returns information of the Web Services configuration currently in use in your organization. Of interest to the Address Book Services is the status of Distribution List Expansion function. If the attribute EnableGroupExpansion is True, your organization currently allows group expansion.</span></span>

<span data-ttu-id="ae5d2-109">次にその例を示します。</span><span class="sxs-lookup"><span data-stu-id="ae5d2-109">For example:</span></span>

    Get-CsWebServiceConfiguration -Identity site:Redmond

<div>

## <a name="see-also"></a><span data-ttu-id="ae5d2-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="ae5d2-110">See Also</span></span>


[<span data-ttu-id="ae5d2-111">Set-cswebserviceconfiguration</span><span class="sxs-lookup"><span data-stu-id="ae5d2-111">Get-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsWebServiceConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

