---
title: 'Lync Server 2013: CsWebServiceConfiguration のアドレス帳の管理'
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
ms.openlocfilehash: e5c66339ba7f5efaa12ebe684d612280b50a49df
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732277"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-cswebserviceconfiguration-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="709cc-102">Lync Server 2013 でのアドレス帳管理用に CsWebServiceConfiguration を設定する</span><span class="sxs-lookup"><span data-stu-id="709cc-102">Set-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="709cc-103">_**最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="709cc-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="709cc-104">このコマンドレットを実行できるユーザー: 既定では、次のグループのメンバーは、CsWebServiceConfiguration コマンドレットをローカルで実行することを許可されています。 RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="709cc-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the Set-CsWebServiceConfiguration cmdlet locally: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="709cc-105">このコマンドレットが割り当てられているすべての役割ベースのアクセス制御 (RBAC) ロールのリストを返すには (自分自身で作成したカスタム RBAC ロールを含む)、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="709cc-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsWebServiceConfiguration"}

<span data-ttu-id="709cc-106">CsWebServiceConfiguration コマンドレットを使うと、管理者は、Web サービスの構成で既存の属性を再定義することができます。</span><span class="sxs-lookup"><span data-stu-id="709cc-106">The Set-CsWebServiceConfiguration cmdlet allows the administrator to redefine an existing attribute in the configuration of the Web Services.</span></span>

<span data-ttu-id="709cc-107">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="709cc-107">For example:</span></span>

    Set-CsWebServiceConfiguration -Identity site:Redmond -EnableGroupExpansion $True

<div>

## <a name="see-also"></a><span data-ttu-id="709cc-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="709cc-108">See Also</span></span>


[<span data-ttu-id="709cc-109">Set-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="709cc-109">Set-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

