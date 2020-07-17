---
title: 会議ディレクトリの移動
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: プールを使用停止にする前に、従来のプール内の会議ディレクトリごとに次の手順を実行する必要があります。
ms.openlocfilehash: 8a25b955ae769a712750ff08325b3fa29538be8a
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752499"
---
# <a name="move-conference-directories"></a><span data-ttu-id="fc715-103">会議ディレクトリの移動</span><span class="sxs-lookup"><span data-stu-id="fc715-103">Move Conference Directories</span></span>

<span data-ttu-id="fc715-104">プールを使用停止にする前に、従来のプール内の会議ディレクトリごとに次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fc715-104">Before decommissioning a pool, you must perform the following procedure for each conference directory in your legacy pool.</span></span>
  
### <a name="to-move-a-conference-directory-to-skype-for-business-server-2019"></a><span data-ttu-id="fc715-105">会議ディレクトリを Skype for Business Server 2019 に移動するには</span><span class="sxs-lookup"><span data-stu-id="fc715-105">To Move a Conference Directory to Skype for Business Server 2019</span></span>

1. <span data-ttu-id="fc715-106">Skype for Business Server 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="fc715-106">Open the Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="fc715-107">組織内の会議ディレクトリの id を取得するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="fc715-107">To obtain the identity of the conference directories in your organization, run the following command:</span></span>
    
   ```PowerShell
   Get-CsConferenceDirectory
   ```

    <span data-ttu-id="fc715-108">上記のコマンドは、組織内のすべての会議ディレクトリを返します。</span><span class="sxs-lookup"><span data-stu-id="fc715-108">The preceding command returns all the conference directories in your organization.</span></span> <span data-ttu-id="fc715-109">そのため、廃棄されたプールに対して結果を制限する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="fc715-109">Because of that, you might want to limit the results to the pool being decommissioned.</span></span> <span data-ttu-id="fc715-110">たとえば、完全修飾ドメイン名 (FQDN) pool01.contoso.net でプールを使用停止にする場合は、次のコマンドを使用して、返されるデータをそのプールからの会議ディレクトリに制限します。</span><span class="sxs-lookup"><span data-stu-id="fc715-110">For example, if you are decommissioning the pool with the fully qualified domain name (FQDN) pool01.contoso.net, use this command to limit the returned data to conference directories from that pool:</span></span>
    
   ```PowerShell
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
   ```

    <span data-ttu-id="fc715-111">このコマンドは、ServiceID プロパティに FQDN pool01.contoso.net が含まれている会議ディレクトリのみを返します。</span><span class="sxs-lookup"><span data-stu-id="fc715-111">That command returns only the conference directories where the ServiceID property contains the FQDN pool01.contoso.net.</span></span>
    
3. <span data-ttu-id="fc715-112">会議ディレクトリを移動するには、プール内の会議ディレクトリごとに次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="fc715-112">To move conference directories, run the following command for each conference directory in the pool:</span></span>
    
   ```PowerShell
   Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
   ```

    <span data-ttu-id="fc715-113">たとえば、会議ディレクトリ3を移動するには、次のコマンドを使用します。 Skype for Business Server 2019 プールを TargetPool として指定します。</span><span class="sxs-lookup"><span data-stu-id="fc715-113">For example, to move conference directory 3, use this command, specifying a Skype for Business Server 2019 pool as the TargetPool:</span></span>
    
   ```PowerShell
   Move-CsConferenceDirectory -Identity 3 -TargetPool "pool02.contoso.net"
   ```

    <span data-ttu-id="fc715-114">プール上のすべての会議ディレクトリを移動する場合は、次のようなコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="fc715-114">If you want to move all the conference directories on a pool, use a command similar to the following:</span></span>
    
   ```PowerShell
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"} | Move-CsConferenceDirectory -TargetPool "pool02.contoso.net"
   ```

<span data-ttu-id="fc715-115">レガシプールを使用停止にするための包括的な手順については、「 [Microsoft レガシーのアンインストールとサーバーの役割の削除](https://go.microsoft.com/fwlink/p/?linkId=246227)」をダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="fc715-115">Download [Uninstalling Microsoft legacy and Removing Server Roles](https://go.microsoft.com/fwlink/p/?linkId=246227) for comprehensive, step-by-step instructions on decommissioning legacy pools.</span></span>
  
<span data-ttu-id="fc715-116">会議ディレクトリを移動するときに、次のエラーが発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="fc715-116">When moving conference directories, you might encounter the following error:</span></span>
  
```console
WARNING: Move operation failed for conference directory with ID "5". Cannot perform a rollback because data migration might have already started. Retry the operation.
WARNING: Before using the -Force parameter, ensure that you have exported the conference directory data using DBImpExp.exe and imported the data on the target pool. Refer to the DBImpExp-Readme.htm file for more information.
Move-CsConferenceDirectory : Unable to cast COM object of type 'System._ComObject' to interface type 'Microsoft.Rtc.Interop.User.IRtcConfDirManagement'. 
This operation failed because the QueryInterface call on the COM component for the interface with SID '{4262B886-503F-4BEA-868C-04E8DF562CEB}' failed due to the following error: The specified module could not be found.
```

<span data-ttu-id="fc715-117">通常、このエラーは、Skype for Business Server 管理シェルで、タスクを完了するために、更新された Active Directory のアクセス許可セットが必要な場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="fc715-117">This error typically occurs when the Skype for Business Server Management Shell requires an updated set of Active Directory permissions in order to complete a task.</span></span> <span data-ttu-id="fc715-118">この問題を解決するには、管理シェルの現在のインスタンスを閉じてから、シェルの新しいインスタンスを開き、コマンドを再実行して会議ディレクトリを移動します。</span><span class="sxs-lookup"><span data-stu-id="fc715-118">To resolve the problem, close the current instance of the Management Shell, then open a new instance of the shell and re-run the command to move the conference directory.</span></span>
  

