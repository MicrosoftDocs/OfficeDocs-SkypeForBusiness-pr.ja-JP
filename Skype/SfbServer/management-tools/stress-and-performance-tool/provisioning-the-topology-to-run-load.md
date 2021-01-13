---
title: ストレスとパフォーマンスのシナリオで負荷を実行するトポロジのプロビジョニング
ms.reviewer: ''
ms.author: v-cichur
author: cichur
ms.date: 12/17/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 143cf9bd-b935-494d-817c-a8b0ccc61eb8
description: ユーザーが Stress and Performance ツールを正常に実行できる Skype for Business Server 2015 トポロジの変更またはプロビジョニング。
ms.openlocfilehash: 8d422497d11c9e56e4d5b205269a09f96dffc136
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814937"
---
# <a name="provisioning-the-topology-to-run-load-in-stress-and-performance-scenarios"></a><span data-ttu-id="41c4c-103">ストレスとパフォーマンスのシナリオで負荷を実行するトポロジのプロビジョニング</span><span class="sxs-lookup"><span data-stu-id="41c4c-103">Provisioning the topology to run load in Stress and Performance scenarios</span></span>
 
<span data-ttu-id="41c4c-104">ユーザーが Stress and Performance ツールを正常に実行できる Skype for Business Server 2015 トポロジの変更またはプロビジョニング。</span><span class="sxs-lookup"><span data-stu-id="41c4c-104">Skype for Business Server 2015 topology changes or provisioning to allow users to successfully run the Stress and Performance tool.</span></span>
  
<span data-ttu-id="41c4c-105">Skype for Business Server 2015 の展開に関する既存の設定と構成によっては、環境に変更を加える必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="41c4c-105">Depending on your existing settings and configuration for your deployment of Skype for Business Server 2015, you might need to make some changes in your environment.</span></span> <span data-ttu-id="41c4c-106">これらの変更の一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="41c4c-106">The following is a list of those changes:</span></span>
  
1. <span data-ttu-id="41c4c-107">実行ポリシー Windows PowerShell制限のないポリシーに設定します。</span><span class="sxs-lookup"><span data-stu-id="41c4c-107">Set the Windows PowerShell execution policy to Unrestricted.</span></span> <span data-ttu-id="41c4c-108">現在設定されている内容が不明な場合は、Skype for Business Server 管理シェルを開き、次のコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="41c4c-108">If you're not sure what it's set to currently, you can open the Skype for Business Server Management Shell and run this command:</span></span>
    
   ```PowerShell
   Get-ExecutionPolicy
   ```

   <span data-ttu-id="41c4c-109">値 Unrestricted が返されない場合は、次に実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="41c4c-109">If the value Unrestricted is not returned, you'll need to run this next:</span></span>
    
   ```PowerShell
   Set-ExecutionPolicy -Unrestricted
   ```

2. <span data-ttu-id="41c4c-110">Skype for Business Server を効果的に構成するには、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="41c4c-110">To effectively configure Skype for Business Server, you'll need to:</span></span>
    
    - <span data-ttu-id="41c4c-111">Skype for Business Server 2015 トポロジ (コンピューター名、サービス インスタンス、サイト名、ポリシーなど) に精通している。</span><span class="sxs-lookup"><span data-stu-id="41c4c-111">Be familiar with your Skype for Business Server 2015 topology (such as computer names, service instances, site names, and policies).</span></span>
    
    - <span data-ttu-id="41c4c-112">応答グループ ハント グループ (SIP URI など) など、グループに作成されたユーザーの一部を割り当てる。</span><span class="sxs-lookup"><span data-stu-id="41c4c-112">Assign some of the users that are created to groups, such as Response Group hunt groups (for example, SIP URIs).</span></span>
    
3. <span data-ttu-id="41c4c-113">コマンド ラインからスクリプトを実行するには、次のコマンドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="41c4c-113">To run a script from command line, you can use:</span></span>
    
   ```PowerShell
   PowerShell.exe -file <path to the file>
   ```

4. <span data-ttu-id="41c4c-114">通常、このパッケージからスクリプトを実行した後、結果のトレースは、スクリプトが実行されたパスと同じパスにあるファイルに格納されます。</span><span class="sxs-lookup"><span data-stu-id="41c4c-114">Typically, after you've run a script from this package, the resulting traces will be stored in a file in the same path from where the script was run.</span></span> <span data-ttu-id="41c4c-115">名前付け形式も \<scriptname\> $h$m$s.txt。</span><span class="sxs-lookup"><span data-stu-id="41c4c-115">There's a naming format as well, \<scriptname\>$h$m$s.txt.</span></span> <span data-ttu-id="41c4c-116">そのため、このArchivingPolicy.ps1 12:15 PM に実行した場合は、ArchivingPolicy121500.txt という名前のログ ファイルが表示ArchivingPolicy121500.txt。</span><span class="sxs-lookup"><span data-stu-id="41c4c-116">So if you ran the ArchivingPolicy.ps1 at 12:15 PM, you'll get a log file named ArchivingPolicy121500.txt.</span></span>
    
5. <span data-ttu-id="41c4c-117">サーバー構成の例を示しますが、ロード テストの実行が完了したら、構成の変更と復元またはロールバックの両方を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="41c4c-117">While we've provided these examples for your server configuration, it's up to you to both modify your configuration and restore or roll it back after you've finished running the load testing.</span></span>
    

