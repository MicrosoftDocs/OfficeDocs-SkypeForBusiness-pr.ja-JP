---
title: 会議ディレクトリを移動する
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Move conference directories
ms:assetid: 71a28308-1f3b-4717-b535-2f4bfe3499a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204994(v=OCS.15)
ms:contentKeyID: 48184463
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2de2b588d880600a4a7d8365f20423d3faf2653e
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756626"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-conference-directories"></a><span data-ttu-id="03f32-102">会議ディレクトリを移動する</span><span class="sxs-lookup"><span data-stu-id="03f32-102">Move conference directories</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="03f32-103">_**トピックの最終更新日:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="03f32-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="03f32-104">プールを使用停止にする前に、Office Communications Server 2007 R2 プール内の会議ディレクトリごとに次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="03f32-104">Before decommissioning a pool, you need to perform the following procedure for each conference directory in your Office Communications Server 2007 R2 pool.</span></span>

<div>

## <a name="to-move-a-conference-directory-to-lync-server-2013"></a><span data-ttu-id="03f32-105">会議ディレクトリを Lync Server 2013 に移動するには</span><span class="sxs-lookup"><span data-stu-id="03f32-105">To move a conference directory to Lync Server 2013</span></span>

1.  <span data-ttu-id="03f32-106">Lync Server 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="03f32-106">Open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="03f32-107">組織の会議ディレクトリの ID を取得するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="03f32-107">To obtain the identity of the conference directories in your organization, run the following commands:</span></span>
    
        Get-CsConferenceDirectory
    
    <span data-ttu-id="03f32-108">Because this cmdlet returns all the conference directories in your organization, you may want to limit the results to only the pool you want to decommission.</span><span class="sxs-lookup"><span data-stu-id="03f32-108">Because this cmdlet returns all the conference directories in your organization, you may want to limit the results to only the pool you want to decommission.</span></span> <span data-ttu-id="03f32-109">For example, if you want to decommission a pool with the fully qualified domain name (FQDN) pool01.contoso.net:</span><span class="sxs-lookup"><span data-stu-id="03f32-109">For example, if you want to decommission a pool with the fully qualified domain name (FQDN) pool01.contoso.net:</span></span>
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
    
    <span data-ttu-id="03f32-110">このコマンドレットでは、サービス ID に pool01.contoso.net という FQDN が含まれるすべての会議ディレクトリが返されます。</span><span class="sxs-lookup"><span data-stu-id="03f32-110">This cmdlet returns all the conference directories where service ID contains the FQDN pool01.contoso.net.</span></span>

3.  <span data-ttu-id="03f32-111">会議ディレクトリを移動するには、プール内の会議ディレクトリごとに次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="03f32-111">To move conference directories, run the following for each conference directory in the pool:</span></span>
    
        Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
    
    <span data-ttu-id="03f32-112">例:</span><span class="sxs-lookup"><span data-stu-id="03f32-112">For example:</span></span>
    
        Move-CsConferenceDirectory -Identity 3 -TargetPool pool02.contoso.net

<div>


> [!NOTE]  
> <span data-ttu-id="03f32-113">以下に示すようなエラーが発生することがあります。これは、Lync Server 管理シェルによって、Active Directory からの更新されたアクセス許可のセットが必要になることによって発生します。</span><span class="sxs-lookup"><span data-stu-id="03f32-113">You may experience an error, shown below, that is caused by the Lync Server Management Shell requiring an updated set of permissions from Active Directory.</span></span> <span data-ttu-id="03f32-114">エラーを解決するには、現在のウィンドウを閉じて、新しい Lync Server 管理シェルを開き、コマンドを再度実行します。</span><span class="sxs-lookup"><span data-stu-id="03f32-114">To resolve the error, closed the current window and open a new Lync Server Management Shell and run the command again.</span></span>



</div>

<span data-ttu-id="03f32-115">![Get-csconferencedirectory のエラー出力](images/JJ204994.4748b9e8-9651-4527-afe1-cbdc6d5ce4a8(OCS.15).jpg "Get-csconferencedirectory のエラー出力")</span><span class="sxs-lookup"><span data-stu-id="03f32-115">![Move-CsConferenceDirectory error output](images/JJ204994.4748b9e8-9651-4527-afe1-cbdc6d5ce4a8(OCS.15).jpg "Move-CsConferenceDirectory error output")</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

