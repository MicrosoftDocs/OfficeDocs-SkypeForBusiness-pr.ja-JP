---
title: ストレスおよびパフォーマンスのシナリオで負荷を実行するのにはトポロジの準備
ms.author: heidip
author: microsoftheidi
ms.date: 12/17/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 143cf9bd-b935-494d-817c-a8b0ccc61eb8
description: ビジネス サーバー 2015 トポロジの変更やプロビジョニングのストレスおよびパフォーマンス ツールが正常に実行できるようにする Skype。
ms.openlocfilehash: 6ff08a3b99f4dc1f05b56c2a1fa86733ccf4f852
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2018
ms.locfileid: "25373779"
---
# <a name="provisioning-the-topology-to-run-load-in-stress-and-performance-scenarios"></a><span data-ttu-id="3ca8f-103">ストレスおよびパフォーマンスのシナリオで負荷を実行するのにはトポロジの準備</span><span class="sxs-lookup"><span data-stu-id="3ca8f-103">Provisioning the topology to run load in Stress and Performance scenarios</span></span>
 
<span data-ttu-id="3ca8f-104">ビジネス サーバー 2015 トポロジの変更やプロビジョニングのストレスおよびパフォーマンス ツールが正常に実行できるようにする Skype。</span><span class="sxs-lookup"><span data-stu-id="3ca8f-104">Skype for Business Server 2015 topology changes or provisioning to allow users to successfully run the Stress and Performance tool.</span></span>
  
<span data-ttu-id="3ca8f-105">既存の設定およびビジネス サーバー 2015 の Skype の配置の構成によっては、環境内の一部を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ca8f-105">Depending on your existing settings and configuration for your deployment of Skype for Business Server 2015, you might need to make some changes in your environment.</span></span> <span data-ttu-id="3ca8f-106">これらの変更の一覧は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="3ca8f-106">The following is a list of those changes:</span></span>
  
1. <span data-ttu-id="3ca8f-107">Windows PowerShell 実行ポリシーは、[制限しない] に設定します。</span><span class="sxs-lookup"><span data-stu-id="3ca8f-107">Set the Windows PowerShell execution policy to Unrestricted.</span></span> <span data-ttu-id="3ca8f-108">かわからないことが現時点に設定するは、ビジネス サーバー管理シェルには、Skype を開くし、このコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="3ca8f-108">If you're not sure what it's set to currently, you can open the Skype for Business Server Management Shell and run this command:</span></span>
    
   ```
   Get-ExecutionPolicy
   ```

   <span data-ttu-id="3ca8f-109">[制限しない] の値が返されない場合は、次にこのを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ca8f-109">If the value Unrestricted is not returned, you'll need to run this next:</span></span>
    
   ```
   Set-ExecutionPolicy -Unrestricted
   ```

2. <span data-ttu-id="3ca8f-110">効果的なビジネス サーバーの Skype を構成するにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ca8f-110">To effectively configure Skype for Business Server, you'll need to:</span></span>
    
    - <span data-ttu-id="3ca8f-111">(コンピューター名、サービス インスタンス、サイト名、ポリシーなど) ビジネス サーバー 2015 トポロジの場合、Skype を理解します。</span><span class="sxs-lookup"><span data-stu-id="3ca8f-111">Be familiar with your Skype for Business Server 2015 topology (such as computer names, service instances, site names, and policies).</span></span>
    
    - <span data-ttu-id="3ca8f-112">応答のグループのハント グループ (たとえば、SIP Uri) など、一部のグループに作成されるユーザーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="3ca8f-112">Assign some of the users that are created to groups, such as Response Group hunt groups (for example, SIP URIs).</span></span>
    
3. <span data-ttu-id="3ca8f-113">コマンドラインからスクリプトを実行するには、次の使用できます。</span><span class="sxs-lookup"><span data-stu-id="3ca8f-113">To run a script from command line, you can use:</span></span>
    
   ```
   PowerShell.exe -file <path to the file>
   ```

4. <span data-ttu-id="3ca8f-114">通常、スクリプトを実行すると、このパッケージからして、結果のトレースはスクリプトが実行された場所から同じパス内のファイルに保存されます。</span><span class="sxs-lookup"><span data-stu-id="3ca8f-114">Typically, after you've run a script from this package, the resulting traces will be stored in a file in the same path from where the script was run.</span></span> <span data-ttu-id="3ca8f-115">名前付け形式を同様に、\<移動し、scriptname\>$h$m$s.txt。</span><span class="sxs-lookup"><span data-stu-id="3ca8f-115">There's a naming format as well, \<scriptname\>$h$m$s.txt.</span></span> <span data-ttu-id="3ca8f-116">午後 12時 15分、ArchivingPolicy.ps1 を実行すると、ArchivingPolicy121500.txt をという名前のログ ファイルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3ca8f-116">So if you ran the ArchivingPolicy.ps1 at 12:15 PM, you'll get a log file named ArchivingPolicy121500.txt.</span></span>
    
5. <span data-ttu-id="3ca8f-117">サーバー構成のこれらの例を提供してきました、両方の構成を変更し、復元またはロード テストの実行が終了したら後にロールバックするです。</span><span class="sxs-lookup"><span data-stu-id="3ca8f-117">While we've provided these examples for your server configuration, it's up to you to both modify your configuration and restore or roll it back after you've finished running the load testing.</span></span>
    

