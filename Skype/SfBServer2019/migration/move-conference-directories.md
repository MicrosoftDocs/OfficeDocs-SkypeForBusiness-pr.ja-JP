---
title: 会議ディレクトリを移動する
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: プールの使用を停止する前に、従来のプールの各会議ディレクトリについて、次の手順を実行する必要があります。
ms.openlocfilehash: c3bee8160e7387102f6d45fc39fa821d2f0df161
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34298142"
---
# <a name="move-conference-directories"></a><span data-ttu-id="aadf7-103">会議ディレクトリを移動する</span><span class="sxs-lookup"><span data-stu-id="aadf7-103">Move Conference Directories</span></span>

<span data-ttu-id="aadf7-104">プールを解除する前に、従来のプールの各会議ディレクトリに対して、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aadf7-104">Before decommissioning a pool, you must perform the following procedure for each conference directory in your legacy pool.</span></span>
  
### <a name="to-move-a-conference-directory-to-skype-for-business-server-2019"></a><span data-ttu-id="aadf7-105">会議ディレクトリを Skype for Business Server 2019 に移動するには</span><span class="sxs-lookup"><span data-stu-id="aadf7-105">To Move a Conference Directory to Skype for Business Server 2019</span></span>

1. <span data-ttu-id="aadf7-106">Skype for Business Server 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="aadf7-106">Open the Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="aadf7-107">組織内の会議ディレクトリの id を取得するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="aadf7-107">To obtain the identity of the conference directories in your organization, run the following command:</span></span>
    
   ```
   Get-CsConferenceDirectory
   ```

    <span data-ttu-id="aadf7-108">上のコマンドは、組織内のすべての会議ディレクトリを返します。</span><span class="sxs-lookup"><span data-stu-id="aadf7-108">The preceding command returns all the conference directories in your organization.</span></span> <span data-ttu-id="aadf7-109">そのため、廃棄されたプールに結果を制限することができます。</span><span class="sxs-lookup"><span data-stu-id="aadf7-109">Because of that, you might want to limit the results to the pool being decommissioned.</span></span> <span data-ttu-id="aadf7-110">たとえば、完全修飾ドメイン名 (FQDN) pool01.contoso.net を使用してプールを廃止する場合は、このコマンドを使用して、返されるデータをそのプールの会議ディレクトリに制限します。</span><span class="sxs-lookup"><span data-stu-id="aadf7-110">For example, if you are decommissioning the pool with the fully qualified domain name (FQDN) pool01.contoso.net, use this command to limit the returned data to conference directories from that pool:</span></span>
    
   ```
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
   ```

    <span data-ttu-id="aadf7-111">このコマンドは、ServiceID プロパティに FQDN pool01.contoso.net が含まれている会議ディレクトリだけを返します。</span><span class="sxs-lookup"><span data-stu-id="aadf7-111">That command returns only the conference directories where the ServiceID property contains the FQDN pool01.contoso.net.</span></span>
    
3. <span data-ttu-id="aadf7-112">会議ディレクトリを移動するには、プール内の各会議ディレクトリに対して、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="aadf7-112">To move conference directories, run the following command for each conference directory in the pool:</span></span>
    
   ```
   Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
   ```

    <span data-ttu-id="aadf7-113">たとえば、会議ディレクトリ3を移動するには、次のコマンドを使用します。 Skype for Business Server 2019 プールを TargetPool として指定します。</span><span class="sxs-lookup"><span data-stu-id="aadf7-113">For example, to move conference directory 3, use this command, specifying a Skype for Business Server 2019 pool as the TargetPool:</span></span>
    
   ```
   Move-CsConferenceDirectory -Identity 3 -TargetPool "pool02.contoso.net"
   ```

    <span data-ttu-id="aadf7-114">プール上のすべての会議ディレクトリを移動する場合は、次のようなコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="aadf7-114">If you want to move all the conference directories on a pool, use a command similar to the following:</span></span>
    
   ```
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"} | Move-CsConferenceDirectory -TargetPool "pool02.contoso.net"
   ```

<span data-ttu-id="aadf7-115">レガシプールを廃止するための包括的な手順については、「 [Microsoft レガシーをアンインストールし、サーバーの役割を削除](https://go.microsoft.com/fwlink/p/?linkId=246227)する」をダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="aadf7-115">Download [Uninstalling Microsoft legacy and Removing Server Roles](https://go.microsoft.com/fwlink/p/?linkId=246227) for comprehensive, step-by-step instructions on decommissioning legacy pools.</span></span>
  
<span data-ttu-id="aadf7-116">会議ディレクトリを移動すると、次のようなエラーが発生する場合があります。</span><span class="sxs-lookup"><span data-stu-id="aadf7-116">When moving conference directories, you might encounter the following error:</span></span>
  
```
WARNING: Move operation failed for conference directory with ID "5". Cannot perform a rollback because data migration might have already started. Retry the operation.
WARNING: Before using the -Force parameter, ensure that you have exported the conference directory data using DBImpExp.exe and imported the data on the target pool. Refer to the DBImpExp-Readme.htm file for more information.
Move-CsConferenceDirectory : Unable to cast COM object of type 'System._ComObject' to interface type 'Microsoft.Rtc.Interop.User.IRtcConfDirManagement'. 
This operation failed because the QueryInterface call on the COM component for the interface with SID '{4262B886-503F-4BEA-868C-04E8DF562CEB}' failed due to the following error: The specified module could not be found.
```

<span data-ttu-id="aadf7-117">このエラーは通常、タスクを完了するために、Skype for Business Server の管理シェルで、更新された Active Directory のアクセス許可セットが必要な場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="aadf7-117">This error typically occurs when the Skype for Business Server Management Shell requires an updated set of Active Directory permissions in order to complete a task.</span></span> <span data-ttu-id="aadf7-118">この問題を解決するには、管理シェルの現在のインスタンスを閉じてから、シェルの新しいインスタンスを開き、コマンドを再実行して会議ディレクトリを移動します。</span><span class="sxs-lookup"><span data-stu-id="aadf7-118">To resolve the problem, close the current instance of the Management Shell, then open a new instance of the shell and re-run the command to move the conference directory.</span></span>
  

