---
title: 会議ディレクトリを移動する
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: プールの使用を停止する前に、レガシ プール内に、会議ディレクトリごとに以下の手順を行う必要があります。
ms.openlocfilehash: 18cbada5833a5160fc1eb81560c56bc9fcff3e2a
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "25028013"
---
# <a name="move-conference-directories"></a><span data-ttu-id="ea2e1-103">会議ディレクトリを移動する</span><span class="sxs-lookup"><span data-stu-id="ea2e1-103">Move Conference Directories</span></span>

<span data-ttu-id="ea2e1-104">プールの使用を停止する前に、レガシ プール内に、会議ディレクトリごとに以下の手順を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="ea2e1-104">Before decommissioning a pool, you must perform the following procedure for each conference directory in your legacy pool.</span></span>
  
### <a name="to-move-a-conference-directory-to-skype-for-business-server-2019"></a><span data-ttu-id="ea2e1-105">Skype をビジネス サーバー 2019 の会議ディレクトリを移動するには</span><span class="sxs-lookup"><span data-stu-id="ea2e1-105">To Move a Conference Directory to Skype for Business Server 2019</span></span>

1. <span data-ttu-id="ea2e1-106">Skype をビジネス サーバー管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="ea2e1-106">Open the Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="ea2e1-107">組織内の会議ディレクトリの id を取得するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="ea2e1-107">To obtain the identity of the conference directories in your organization, run the following command:</span></span>
    
  ```
  Get-CsConferenceDirectory
  ```

    <span data-ttu-id="ea2e1-108">上記のコマンドは、組織のすべての会議ディレクトリを返します。</span><span class="sxs-lookup"><span data-stu-id="ea2e1-108">The preceding command returns all the conference directories in your organization.</span></span> <span data-ttu-id="ea2e1-109">このため、プールの使用を中止するのに結果を制限する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ea2e1-109">Because of that, you might want to limit the results to the pool being decommissioned.</span></span> <span data-ttu-id="ea2e1-110">などの完全修飾ドメイン名 (FQDN) の pool01.contoso.net のプールを廃止する場合は、会議ディレクトリをそのプールから返されたデータを制限するのにはこのコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="ea2e1-110">For example, if you are decommissioning the pool with the fully qualified domain name (FQDN) pool01.contoso.net, use this command to limit the returned data to conference directories from that pool:</span></span>
    
  ```
  Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
  ```

    <span data-ttu-id="ea2e1-111">そのコマンドは、ServiceID プロパティが FQDN の pool01.contoso.net を含む会議ディレクトリのみを返します。</span><span class="sxs-lookup"><span data-stu-id="ea2e1-111">That command returns only the conference directories where the ServiceID property contains the FQDN pool01.contoso.net.</span></span>
    
3. <span data-ttu-id="ea2e1-112">会議ディレクトリを移動するには、プールで会議の各ディレクトリに対して次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="ea2e1-112">To move conference directories, run the following command for each conference directory in the pool:</span></span>
    
  ```
  Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
  ```

    <span data-ttu-id="ea2e1-113">たとえば、3 の会議ディレクトリを移動するに、TargetPool として、Skype のビジネス サーバー 2019 プールを指定する、このコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="ea2e1-113">For example, to move conference directory 3, use this command, specifying a Skype for Business Server 2019 pool as the TargetPool:</span></span>
    
  ```
  Move-CsConferenceDirectory -Identity 3 -TargetPool "pool02.contoso.net"
  ```

    <span data-ttu-id="ea2e1-114">プール上のすべての会議ディレクトリを移動する場合は、次のようなコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="ea2e1-114">If you want to move all the conference directories on a pool, use a command similar to the following:</span></span>
    
  ```
  Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"} | Move-CsConferenceDirectory -TargetPool "pool02.contoso.net"
  ```

<span data-ttu-id="ea2e1-115">従来のプールを使用停止に包括的なステップバイ ステップの手順については、 [Microsoft レガシーをアンインストールしてサーバーの役割を削除すること](https://go.microsoft.com/fwlink/p/?linkId=246227)をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="ea2e1-115">Download [Uninstalling Microsoft legacy and Removing Server Roles](https://go.microsoft.com/fwlink/p/?linkId=246227) for comprehensive, step-by-step instructions on decommissioning legacy pools.</span></span>
  
<span data-ttu-id="ea2e1-116">会議ディレクトリを移動するには、次のエラーが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ea2e1-116">When moving conference directories, you might encounter the following error:</span></span>
  
```
WARNING: Move operation failed for conference directory with ID "5". Cannot perform a rollback because data migration might have already started. Retry the operation.
WARNING: Before using the -Force parameter, ensure that you have exported the conference directory data using DBImpExp.exe and imported the data on the target pool. Refer to the DBImpExp-Readme.htm file for more information.
Move-CsConferenceDirectory : Unable to cast COM object of type 'System._ComObject' to interface type 'Microsoft.Rtc.Interop.User.IRtcConfDirManagement'. 
This operation failed because the QueryInterface call on the COM component for the interface with SID '{4262B886-503F-4BEA-868C-04E8DF562CEB}' failed due to the following error: The specified module could not be found.
```

<span data-ttu-id="ea2e1-117">このエラーは、ビジネスのサーバー管理シェルの Skype は、更新されたタスクを完了するために Active Directory アクセス許可のセットを必要とする場合に通常発生します。</span><span class="sxs-lookup"><span data-stu-id="ea2e1-117">This error typically occurs when the Skype for Business Server Management Shell requires an updated set of Active Directory permissions in order to complete a task.</span></span> <span data-ttu-id="ea2e1-118">問題を解決するには、管理シェルの現在のインスタンスを閉じる、シェルの新しいインスタンスを開くし、会議ディレクトリを移動するコマンドを再実行します。</span><span class="sxs-lookup"><span data-stu-id="ea2e1-118">To resolve the problem, close the current instance of the Management Shell, then open a new instance of the shell and re-run the command to move the conference directory.</span></span>
  

