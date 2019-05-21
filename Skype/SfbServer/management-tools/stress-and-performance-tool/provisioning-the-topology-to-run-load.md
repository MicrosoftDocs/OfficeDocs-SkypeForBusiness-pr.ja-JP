---
title: ストレスとパフォーマンスのシナリオでのロードを実行するためのトポロジのプロビジョニング
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 12/17/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 143cf9bd-b935-494d-817c-a8b0ccc61eb8
description: Skype for Business Server 2015 のトポロジの変更またはプロビジョニングを行うと、ユーザーはストレスとパフォーマンスのツールを正常に実行することができます。
ms.openlocfilehash: c7cdc10b3667ac99376904c81309df739e49844a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34299703"
---
# <a name="provisioning-the-topology-to-run-load-in-stress-and-performance-scenarios"></a><span data-ttu-id="66aa3-103">ストレスとパフォーマンスのシナリオでのロードを実行するためのトポロジのプロビジョニング</span><span class="sxs-lookup"><span data-stu-id="66aa3-103">Provisioning the topology to run load in Stress and Performance scenarios</span></span>
 
<span data-ttu-id="66aa3-104">Skype for Business Server 2015 のトポロジの変更またはプロビジョニングを行うと、ユーザーはストレスとパフォーマンスのツールを正常に実行することができます。</span><span class="sxs-lookup"><span data-stu-id="66aa3-104">Skype for Business Server 2015 topology changes or provisioning to allow users to successfully run the Stress and Performance tool.</span></span>
  
<span data-ttu-id="66aa3-105">Skype for Business Server 2015 の展開に関する既存の設定と構成によっては、お使いの環境にいくつかの変更を加える必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="66aa3-105">Depending on your existing settings and configuration for your deployment of Skype for Business Server 2015, you might need to make some changes in your environment.</span></span> <span data-ttu-id="66aa3-106">これらの変更の一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="66aa3-106">The following is a list of those changes:</span></span>
  
1. <span data-ttu-id="66aa3-107">Windows PowerShell の実行ポリシーを無制限に設定します。</span><span class="sxs-lookup"><span data-stu-id="66aa3-107">Set the Windows PowerShell execution policy to Unrestricted.</span></span> <span data-ttu-id="66aa3-108">現在設定されている内容がわからない場合は、Skype for Business Server 管理シェルを開き、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="66aa3-108">If you're not sure what it's set to currently, you can open the Skype for Business Server Management Shell and run this command:</span></span>
    
   ```
   Get-ExecutionPolicy
   ```

   <span data-ttu-id="66aa3-109">制限なしの値が返されない場合は、次の操作を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="66aa3-109">If the value Unrestricted is not returned, you'll need to run this next:</span></span>
    
   ```
   Set-ExecutionPolicy -Unrestricted
   ```

2. <span data-ttu-id="66aa3-110">Skype for Business Server を効果的に構成するには、次のことを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="66aa3-110">To effectively configure Skype for Business Server, you'll need to:</span></span>
    
    - <span data-ttu-id="66aa3-111">Skype for Business Server 2015 トポロジ (コンピューター名、サービスインスタンス、サイト名、ポリシーなど) について理解している必要があります。</span><span class="sxs-lookup"><span data-stu-id="66aa3-111">Be familiar with your Skype for Business Server 2015 topology (such as computer names, service instances, site names, and policies).</span></span>
    
    - <span data-ttu-id="66aa3-112">応答グループのハントグループ (SIP Uri など) など、グループに作成されたユーザーの一部を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="66aa3-112">Assign some of the users that are created to groups, such as Response Group hunt groups (for example, SIP URIs).</span></span>
    
3. <span data-ttu-id="66aa3-113">コマンドラインからスクリプトを実行するには、次のように使用できます。</span><span class="sxs-lookup"><span data-stu-id="66aa3-113">To run a script from command line, you can use:</span></span>
    
   ```
   PowerShell.exe -file <path to the file>
   ```

4. <span data-ttu-id="66aa3-114">通常、このパッケージからスクリプトを実行すると、スクリプトが実行された場所と同じパスのファイルに結果のトレースが格納されます。</span><span class="sxs-lookup"><span data-stu-id="66aa3-114">Typically, after you've run a script from this package, the resulting traces will be stored in a file in the same path from where the script was run.</span></span> <span data-ttu-id="66aa3-115">\<Scriptname\>$h $ m $ s .txt という名前の書式もあります。</span><span class="sxs-lookup"><span data-stu-id="66aa3-115">There's a naming format as well, \<scriptname\>$h$m$s.txt.</span></span> <span data-ttu-id="66aa3-116">そのため、12:15 PM で ArchivingPolicy を実行すると、ArchivingPolicy121500 という名前のログファイルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="66aa3-116">So if you ran the ArchivingPolicy.ps1 at 12:15 PM, you'll get a log file named ArchivingPolicy121500.txt.</span></span>
    
5. <span data-ttu-id="66aa3-117">これらの例は、サーバー構成のために用意されていますが、ロードテストの実行が完了したら、構成を変更し、復元またはロールバックすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="66aa3-117">While we've provided these examples for your server configuration, it's up to you to both modify your configuration and restore or roll it back after you've finished running the load testing.</span></span>
    

