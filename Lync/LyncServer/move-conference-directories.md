---
title: 会議ディレクトリを移動する
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Move conference directories
ms:assetid: 71a28308-1f3b-4717-b535-2f4bfe3499a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204994(v=OCS.15)
ms:contentKeyID: 48184463
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1ae7633d638571410c93cfefe87d9e333731a4bb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727587"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-conference-directories"></a><span data-ttu-id="aeaf5-102">会議ディレクトリを移動する</span><span class="sxs-lookup"><span data-stu-id="aeaf5-102">Move conference directories</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aeaf5-103">_**最終更新日:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="aeaf5-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="aeaf5-104">プールを解除する前に、Office Communications Server 2007 R2 プールの各会議ディレクトリに対して、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aeaf5-104">Before decommissioning a pool, you need to perform the following procedure for each conference directory in your Office Communications Server 2007 R2 pool.</span></span>

<div>

## <a name="to-move-a-conference-directory-to-lync-server-2013"></a><span data-ttu-id="aeaf5-105">会議ディレクトリを Lync Server 2013 に移動するには</span><span class="sxs-lookup"><span data-stu-id="aeaf5-105">To move a conference directory to Lync Server 2013</span></span>

1.  <span data-ttu-id="aeaf5-106">Lync Server 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="aeaf5-106">Open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="aeaf5-107">組織内の会議ディレクトリの id を取得するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="aeaf5-107">To obtain the identity of the conference directories in your organization, run the following commands:</span></span>
    
        Get-CsConferenceDirectory
    
    <span data-ttu-id="aeaf5-108">このコマンドレットでは、組織内のすべての会議ディレクトリが返されるため、使用停止するプールのみに結果を制限することができます。</span><span class="sxs-lookup"><span data-stu-id="aeaf5-108">Because this cmdlet returns all the conference directories in your organization, you may want to limit the results to only the pool you want to decommission.</span></span> <span data-ttu-id="aeaf5-109">たとえば、完全修飾ドメイン名 (FQDN) pool01.contoso.net を使ってプールを撤去する場合は、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="aeaf5-109">For example, if you want to decommission a pool with the fully qualified domain name (FQDN) pool01.contoso.net:</span></span>
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
    
    <span data-ttu-id="aeaf5-110">このコマンドレットは、サービス ID に FQDN pool01.contoso.net が含まれているすべての会議ディレクトリを返します。</span><span class="sxs-lookup"><span data-stu-id="aeaf5-110">This cmdlet returns all the conference directories where service ID contains the FQDN pool01.contoso.net.</span></span>

3.  <span data-ttu-id="aeaf5-111">会議ディレクトリを移動するには、プール内の各会議ディレクトリに対して次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="aeaf5-111">To move conference directories, run the following for each conference directory in the pool:</span></span>
    
        Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
    
    <span data-ttu-id="aeaf5-112">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="aeaf5-112">For example:</span></span>
    
        Move-CsConferenceDirectory -Identity 3 -TargetPool pool02.contoso.net

<div>


> [!NOTE]  
> <span data-ttu-id="aeaf5-113">次のようなエラーが表示されることがあります。これは、Lync Server 管理シェルで、Active Directory に対するアクセス許可の更新されたセットが必要であることが原因で発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="aeaf5-113">You may experience an error, shown below, that is caused by the Lync Server Management Shell requiring an updated set of permissions from Active Directory.</span></span> <span data-ttu-id="aeaf5-114">エラーを解決するには、現在のウィンドウを閉じて、新しい Lync Server 管理シェルを開き、コマンドをもう一度実行します。</span><span class="sxs-lookup"><span data-stu-id="aeaf5-114">To resolve the error, closed the current window and open a new Lync Server Management Shell and run the command again.</span></span>



</div>

<span data-ttu-id="aeaf5-115">![CsConferenceDirectory の移動エラーの出力](images/JJ204994.4748b9e8-9651-4527-afe1-cbdc6d5ce4a8(OCS.15).jpg "CsConferenceDirectory の移動エラーの出力")</span><span class="sxs-lookup"><span data-stu-id="aeaf5-115">![Move-CsConferenceDirectory error output](images/JJ204994.4748b9e8-9651-4527-afe1-cbdc6d5ce4a8(OCS.15).jpg "Move-CsConferenceDirectory error output")</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

