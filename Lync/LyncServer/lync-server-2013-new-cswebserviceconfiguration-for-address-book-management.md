---
title: 'Lync Server 2013: 新しい-アドレス帳管理のための CsWebServiceConfiguration'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: New-CsWebServiceConfiguration for Address Book management
ms:assetid: 49e4ecc5-aa3e-4dd4-a32c-b0dea3758fab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429703(v=OCS.15)
ms:contentKeyID: 48184067
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03a973ca1086a9d2ca1ce2d8f19bbb64ba8aae19
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826263"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-cswebserviceconfiguration-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="4e3ce-102">Lync Server 2013 でのアドレス帳管理のための CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="4e3ce-102">New-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4e3ce-103">_**最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="4e3ce-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="4e3ce-104">このコマンドレットを実行できるユーザー: 既定では、次のグループのメンバーは、CsWebServiceConfiguration コマンドレットをローカルで実行することを許可されています。 RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="4e3ce-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the New-CsWebServiceConfiguration cmdlet locally: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="4e3ce-105">このコマンドレットが割り当てられているすべての役割ベースのアクセス制御 (RBAC) ロールのリストを返すには (自分自身で作成したカスタム RBAC ロールを含む)、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="4e3ce-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "New-CsWebServiceConfiguration"}

<span data-ttu-id="4e3ce-106">CsWebServiceConfiguration コマンドレットの新規作成では、組織内の Web サービスの新しい構成が定義されます。</span><span class="sxs-lookup"><span data-stu-id="4e3ce-106">The cmdlet New-CsWebServiceConfiguration defines a new configuration for Web Services in your organization.</span></span> <span data-ttu-id="4e3ce-107">Web サービス構成のスコープは、サイトまたはサービスレベルでのみ利用できます。</span><span class="sxs-lookup"><span data-stu-id="4e3ce-107">The scope for the Web Services configuration can only be at the site or service level.</span></span> <span data-ttu-id="4e3ce-108">グローバルレベルで新しい Web サービス構成を作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="4e3ce-108">It cannot create a new Web Services configuration at the global level.</span></span> <span data-ttu-id="4e3ce-109">特にアドレス帳に関連するものは EnableGroupExansion 属性です。</span><span class="sxs-lookup"><span data-stu-id="4e3ce-109">Specifically of interest to the Address Book is the EnableGroupExansion attribute.</span></span> <span data-ttu-id="4e3ce-110">True に設定されている場合、Web サービスはグループ展開の要求に応答できます。</span><span class="sxs-lookup"><span data-stu-id="4e3ce-110">If set to True, the Web Services can respond to requests for group expansion.</span></span>

<span data-ttu-id="4e3ce-111">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="4e3ce-111">For example:</span></span>

    New-CsWebServiceConfiguration -Identity site:Redmond -EnableGroupExpansion $False -UseCertificateAuth $True

<div>

## <a name="see-also"></a><span data-ttu-id="4e3ce-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="4e3ce-112">See Also</span></span>


[<span data-ttu-id="4e3ce-113">New-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="4e3ce-113">New-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsWebServiceConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

