---
title: Lync Server 2010 会議ディレクトリを Lync Server 2013 に移動する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move Conference Directories
ms:assetid: 659867e0-ce91-4a95-9787-b1c1566460a8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727126(v=OCS.15)
ms:contentKeyID: 62387565
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6712e22ffcdc2eaea9ae39be961bb50316beed5b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034567"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-conference-directories"></a><span data-ttu-id="6e525-102">会議ディレクトリの移動</span><span class="sxs-lookup"><span data-stu-id="6e525-102">Move Conference Directories</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6e525-103">_**トピックの最終更新日:** 2014-05-28_</span><span class="sxs-lookup"><span data-stu-id="6e525-103">_**Topic Last Modified:** 2014-05-28_</span></span>

<span data-ttu-id="6e525-104">プールを使用停止にする前に、Lync Server 2010 プール内の会議ディレクトリごとに次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e525-104">Before decommissioning a pool you must perform the following procedure for each conference directory in your Lync Server 2010 pool.</span></span>

<div>

## <a name="to-move-a-conference-directory-to-lync-server-2013"></a><span data-ttu-id="6e525-105">会議ディレクトリを Lync Server 2013 に移動するには</span><span class="sxs-lookup"><span data-stu-id="6e525-105">To Move a Conference Directory to Lync Server 2013</span></span>

1.  <span data-ttu-id="6e525-106">Lync Server 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="6e525-106">Open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="6e525-107">組織内の会議ディレクトリの id を取得するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="6e525-107">To obtain the identity of the conference directories in your organization, run the following command:</span></span>
    
        Get-CsConferenceDirectory
    
    <span data-ttu-id="6e525-108">上記のコマンドは、組織内のすべての会議ディレクトリを返します。</span><span class="sxs-lookup"><span data-stu-id="6e525-108">The preceding command returns all the conference directories in your organization.</span></span> <span data-ttu-id="6e525-109">そのため、廃棄されたプールに対して結果を制限する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="6e525-109">Because of that, you might want to limit the results to the pool being decommissioned.</span></span> <span data-ttu-id="6e525-110">たとえば、完全修飾ドメイン名 (FQDN) pool01.contoso.net でプールを使用停止にする場合は、次のコマンドを使用して、返されるデータをそのプールからの会議ディレクトリに制限します。</span><span class="sxs-lookup"><span data-stu-id="6e525-110">For example, if you are decommissioning the pool with the fully qualified domain name (FQDN) pool01.contoso.net, use this command to limit the returned data to conference directories from that pool:</span></span>
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
    
    <span data-ttu-id="6e525-111">このコマンドは、ServiceID プロパティに FQDN pool01.contoso.net が含まれている会議ディレクトリのみを返します。</span><span class="sxs-lookup"><span data-stu-id="6e525-111">That command returns only the conference directories where the ServiceID property contains the FQDN pool01.contoso.net.</span></span>

3.  <span data-ttu-id="6e525-112">会議ディレクトリを移動するには、プール内の会議ディレクトリごとに次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="6e525-112">To move conference directories, run the following command for each conference directory in the pool:</span></span>
    
        Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
    
    <span data-ttu-id="6e525-113">たとえば、会議ディレクトリ3を移動するには、次のコマンドを使用します。 Lync Server 2013 プールを TargetPool として指定します。</span><span class="sxs-lookup"><span data-stu-id="6e525-113">For example, to move conference directory 3 use this command, specifying a Lync Server 2013 pool as the TargetPool:</span></span>
    
        Move-CsConferenceDirectory -Identity 3 -TargetPool "pool02.contoso.net"
    
    <span data-ttu-id="6e525-114">プール上のすべての会議ディレクトリを移動するには、次のようなコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="6e525-114">If you want to move all the conference directories on a pool then use a command similar to the following:</span></span>
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"} | Move-CsConferenceDirectory -TargetPool "pool02.contoso.net"

<span data-ttu-id="6e525-115">Lync 2010 プールを使用停止にするための包括的な手順については、「Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=246227](http://go.microsoft.com/fwlink/p/?linkid=246227)Server 2010 のアンインストールとサーバーの役割の削除」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6e525-115">Please see the document "Uninstalling Microsoft Lync Server 2010 and Removing Server Roles" (which can be downloaded from [http://go.microsoft.com/fwlink/p/?linkId=246227](http://go.microsoft.com/fwlink/p/?linkid=246227)) for comprehensive, step-by-step instructions on decommissioning Lync 2010 pools.</span></span>

<span data-ttu-id="6e525-116">会議ディレクトリを移動すると、次のエラーが発生する場合があります。</span><span class="sxs-lookup"><span data-stu-id="6e525-116">When moving conference directories you might encounter the following error:</span></span>

    WARNING: Move operation failed for conference directory with ID "5". Cannot perform a rollback because data migration might have already started. Retry the operation.
    WARNING: Before using the -Force parameter, ensure that you have exported the conference directory data using DBImpExp.exe and imported the data on the target pool. Refer to the DBImpExp-Readme.htm file for more information.
    Move-CsConferenceDirectory : Unable to cast COM object of type 'System._ComObject' to interface type 'Microsoft.Rtc.Interop.User.IRtcConfDirManagement'. 
    This operation failed because the QueryInterface call on the COM component for the interface with SID '{4262B886-503F-4BEA-868C-04E8DF562CEB}' failed due to the following error: The specified module could not be found.

<span data-ttu-id="6e525-117">通常、このエラーは、タスクを完了するために Lync Server 管理シェルで、更新された Active Directory のアクセス許可セットが必要な場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="6e525-117">This error typically occurs when the Lync Server Management Shell requires an updated set of Active Directory permissions in order to complete a task.</span></span> <span data-ttu-id="6e525-118">この問題を解決するには、管理シェルの現在のインスタンスを閉じてから、シェルの新しいインスタンスを開き、コマンドを再実行して会議ディレクトリを移動します。</span><span class="sxs-lookup"><span data-stu-id="6e525-118">To resolve the problem, close the current instance of the Management Shell, then open a new instance of the shell and re-run the command in order to move the conference directory.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

