---
title: Skype for Business Server のバックエンドサーバーまたは Standard Edition サーバーを修正または更新する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f95f8d3a-e039-484e-97bd-d727db21a12b
description: '概要: Skype for Business Server のバックエンドサーバーに更新プログラムまたは更新プログラムをインストールする方法について説明します。'
ms.openlocfilehash: b8a0280577147e37c52ab11aa3061541bae27610
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34275123"
---
# <a name="patch-or-update-a-back-end-server-or-standard-edition-server-in-skype-for-business-server"></a><span data-ttu-id="98472-103">Skype for Business Server のバックエンドサーバーまたは Standard Edition サーバーを修正または更新する</span><span class="sxs-lookup"><span data-stu-id="98472-103">Patch or update a Back End Server or Standard Edition server in Skype for Business Server</span></span>
 
<span data-ttu-id="98472-104">**概要:** Skype for Business Server のバックエンドサーバーに更新プログラムまたは更新プログラムをインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="98472-104">**Summary:** Learn how to install an update or patch on a Back End Server in Skype for Business Server.</span></span>
  
<span data-ttu-id="98472-105">このトピックでは、Enterprise Edition バックエンドサーバーまたは Standard Edition サーバーに更新プログラムをインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="98472-105">This topic explains how to install an update on an Enterprise Edition Back End Server or a Standard Edition server.</span></span>
  
<span data-ttu-id="98472-106">アップグレード中に少なくとも30分間バックエンドサーバーが停止している場合、ユーザーは回復性モードに移行することがあります。</span><span class="sxs-lookup"><span data-stu-id="98472-106">If a Back End Server is down for at least 30 minutes while you are upgrading it, users may then go into resiliency mode.</span></span> <span data-ttu-id="98472-107">アップグレードが完了し、バックエンドサーバーがプール内のフロントエンドサーバーに再度接続されると、ユーザーは完全な機能に戻ります。</span><span class="sxs-lookup"><span data-stu-id="98472-107">When the upgrade is finished and the Back End Servers has again connected with the Front End Servers in the pool, users are returned to full functionality.</span></span> <span data-ttu-id="98472-108">アップグレードが 30 分未満の場合、ユーザーには影響ありません。</span><span class="sxs-lookup"><span data-stu-id="98472-108">If the upgrade takes less than 30 minutes, users will not be affected.</span></span>
  
### <a name="to-update-a-back-end-server-or-standard-edition-server"></a><span data-ttu-id="98472-109">バックエンド サーバーまたは Standard Edition サーバーを更新するには</span><span class="sxs-lookup"><span data-stu-id="98472-109">To update a back end server or Standard Edition server</span></span>

1. <span data-ttu-id="98472-110">アップグレードするサーバーに CsAdministrator の役割のメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="98472-110">Log on to the server you are upgrading as a member of the CsAdministrator role.</span></span>
    
2. <span data-ttu-id="98472-111">更新をダウンロードして、ローカル ハードディスクに抽出します。</span><span class="sxs-lookup"><span data-stu-id="98472-111">Download the update and extract it to the local hard disk.</span></span>
    
3. <span data-ttu-id="98472-112">Skype for Business Server 管理シェルを開始します。 [**スタート**]、[**すべてのプログラム**]、[ **skype For business**]、[ **skype for business server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="98472-112">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**..</span></span>
    
4. <span data-ttu-id="98472-113">Skype for Business Server サービスを停止します。</span><span class="sxs-lookup"><span data-stu-id="98472-113">Stop Skype for Business Server services.</span></span> <span data-ttu-id="98472-114">コマンド ラインで次を入力します。</span><span class="sxs-lookup"><span data-stu-id="98472-114">At the command line, type:</span></span>
    
    ```
    Stop-CsWindowsService
    ```

5. <span data-ttu-id="98472-115">World Wide Web サービスを停止します。</span><span class="sxs-lookup"><span data-stu-id="98472-115">Stop the World Wide Web service.</span></span> <span data-ttu-id="98472-116">コマンド ラインで次を入力します。</span><span class="sxs-lookup"><span data-stu-id="98472-116">At the command line, type:</span></span>
    
    ```
    net stop w3svc
   ```

6. <span data-ttu-id="98472-117">すべての Skype for Business Server 管理シェルウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="98472-117">Close all Skype for Business Server Management Shell windows.</span></span>
    
7. <span data-ttu-id="98472-118">更新をインストールします。</span><span class="sxs-lookup"><span data-stu-id="98472-118">Install the update.</span></span>
    
8. <span data-ttu-id="98472-119">Skype for Business Server 管理シェルを開始します。 [**スタート**]、[**すべてのプログラム**]、[ **skype For business**]、[ **skype for business server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="98472-119">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**.</span></span>
    
9. <span data-ttu-id="98472-120">Skype for Business Server サービスをもう一度停止して、グローバルアセンブリキャッシュ (GAC) アセンブリをキャッチします。</span><span class="sxs-lookup"><span data-stu-id="98472-120">Stop Skype for Business Server services again to catch Global Assembly Cache (GAC) -d assemblies.</span></span> <span data-ttu-id="98472-121">コマンド ラインで次を入力します。</span><span class="sxs-lookup"><span data-stu-id="98472-121">At the command line, type:</span></span>
    
    ```
    Stop-CsWindowsService
    ```

10. <span data-ttu-id="98472-p105">World Wide Web サービスを再起動します。コマンド ラインで次を入力します。</span><span class="sxs-lookup"><span data-stu-id="98472-p105">Restart the World Wide Web service. At the command line, type:</span></span>
    
    ```
    net start w3svc
    ```

11. <span data-ttu-id="98472-124">次のいずれかを実行して、SQL Server データベースに対する変更を適用します。</span><span class="sxs-lookup"><span data-stu-id="98472-124">Apply the changes made to the SQL Server databases by doing one of the following:</span></span>
    
    - <span data-ttu-id="98472-125">Enterprise Edition バックエンドサーバーで、データベースのアーカイブや監視など、このサーバー上に併置されたデータベースがない場合は、コマンドラインで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="98472-125">If this is an Enterprise Edition Back End Server and there are no collocated databases on this server, such as Archiving or Monitoring databases, then type the following at a command line:</span></span>
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    ```

    - <span data-ttu-id="98472-126">Enterprise Edition バックエンドサーバーで、このサーバーに併置されたデータベースがある場合は、コマンドラインで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="98472-126">If this is an Enterprise Edition Back End Server and there are collocated databases on this server, then type the following at a command line:</span></span>
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    ```

    - <span data-ttu-id="98472-127">Standard Edition サーバーの場合は、コマンドラインで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="98472-127">If this is an Standard Edition server, type the following at a command line:</span></span>
    
    ```
    Install-CsDatabase -Update -LocalDatabases

    ```
