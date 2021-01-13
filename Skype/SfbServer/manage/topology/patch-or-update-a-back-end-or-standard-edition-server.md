---
title: Skype for Business Server でバック エンド サーバーまたは Standard Edition サーバーにパッチを適用または更新する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: f95f8d3a-e039-484e-97bd-d727db21a12b
description: '概要: Skype for Business Server のバック エンド サーバーに更新プログラムまたは更新プログラムをインストールする方法について学習します。'
ms.openlocfilehash: 3e5e0cda1604f3144e853cfa3bf7bcc45e7d0c2f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826307"
---
# <a name="patch-or-update-a-back-end-server-or-standard-edition-server-in-skype-for-business-server"></a><span data-ttu-id="d2718-103">Skype for Business Server のバック エンド サーバーまたは Standard Edition サーバーにパッチを適用または更新する</span><span class="sxs-lookup"><span data-stu-id="d2718-103">Patch or update a Back End Server or Standard Edition server in Skype for Business Server</span></span>
 
<span data-ttu-id="d2718-104">**概要:** Skype for Business Server のバック エンド サーバーに更新プログラムまたは更新プログラムをインストールする方法について学習します。</span><span class="sxs-lookup"><span data-stu-id="d2718-104">**Summary:** Learn how to install an update or patch on a Back End Server in Skype for Business Server.</span></span>
  
<span data-ttu-id="d2718-105">このトピックでは、Enterprise Edition のバック エンド サーバーまたは Standard Edition サーバーに更新プログラムをインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d2718-105">This topic explains how to install an update on an Enterprise Edition Back End Server or a Standard Edition server.</span></span>
  
<span data-ttu-id="d2718-106">アップグレード中に少なくとも 30 分間、バック エンド サーバーがダウンした場合、ユーザーは復元モードになります。</span><span class="sxs-lookup"><span data-stu-id="d2718-106">If a Back End Server is down for at least 30 minutes while you are upgrading it, users may then go into resiliency mode.</span></span> <span data-ttu-id="d2718-107">アップグレードが完了し、バック エンド サーバーがプール内のフロントエンド サーバーに再度接続されると、ユーザーは完全な機能に戻ります。</span><span class="sxs-lookup"><span data-stu-id="d2718-107">When the upgrade is finished and the Back End Servers has again connected with the Front End Servers in the pool, users are returned to full functionality.</span></span> <span data-ttu-id="d2718-108">アップグレードにかかる時間が 30 分未満の場合、ユーザーに影響は与えされません。</span><span class="sxs-lookup"><span data-stu-id="d2718-108">If the upgrade takes less than 30 minutes, users will not be affected.</span></span>
  
### <a name="to-update-a-back-end-server-or-standard-edition-server"></a><span data-ttu-id="d2718-109">バック エンド サーバーまたは Standard Edition サーバーを更新するには</span><span class="sxs-lookup"><span data-stu-id="d2718-109">To update a back end server or Standard Edition server</span></span>

1. <span data-ttu-id="d2718-110">CsAdministrator の役割のメンバーとして、アップグレードするサーバーにログオンします。</span><span class="sxs-lookup"><span data-stu-id="d2718-110">Log on to the server you are upgrading as a member of the CsAdministrator role.</span></span>
    
2. <span data-ttu-id="d2718-111">更新プログラムをダウンロードし、ローカル ハード ディスクに展開します。</span><span class="sxs-lookup"><span data-stu-id="d2718-111">Download the update and extract it to the local hard disk.</span></span>
    
3. <span data-ttu-id="d2718-112">Skype for Business Server 管理シェルを起動します。[スタート] ボタン、[すべてのプログラム] の順にクリックし **、[Skype for Business]** をクリックして **、[Skype for Business Server 管理** シェル] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d2718-112">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**..</span></span>
    
4. <span data-ttu-id="d2718-113">Skype for Business Server サービスを停止します。</span><span class="sxs-lookup"><span data-stu-id="d2718-113">Stop Skype for Business Server services.</span></span> <span data-ttu-id="d2718-114">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="d2718-114">At the command line, type:</span></span>
    
    ```PowerShell
    Stop-CsWindowsService
    ```

5. <span data-ttu-id="d2718-115">World Wide Web サービスを停止します。</span><span class="sxs-lookup"><span data-stu-id="d2718-115">Stop the World Wide Web service.</span></span> <span data-ttu-id="d2718-116">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="d2718-116">At the command line, type:</span></span>
    
    ```PowerShell
    net stop w3svc
   ```

6. <span data-ttu-id="d2718-117">すべての Skype for Business Server 管理シェル ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="d2718-117">Close all Skype for Business Server Management Shell windows.</span></span>
    
7. <span data-ttu-id="d2718-118">更新プログラムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="d2718-118">Install the update.</span></span>
    
8. <span data-ttu-id="d2718-119">Skype for Business Server 管理シェルを起動します **。[スタート**] ボタン、[すべてのプログラム] の順にクリックし **、[Skype for Business]** をクリックして **、[Skype for Business Server 管理** シェル] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d2718-119">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**.</span></span>
    
9. <span data-ttu-id="d2718-120">Skype for Business Server サービスを再度停止して、グローバル アセンブリ キャッシュ (GAC) -d アセンブリをキャッチします。</span><span class="sxs-lookup"><span data-stu-id="d2718-120">Stop Skype for Business Server services again to catch Global Assembly Cache (GAC) -d assemblies.</span></span> <span data-ttu-id="d2718-121">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="d2718-121">At the command line, type:</span></span>
    
    ```PowerShell
    Stop-CsWindowsService
    ```

10. <span data-ttu-id="d2718-122">World Wide Web サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="d2718-122">Restart the World Wide Web service.</span></span> <span data-ttu-id="d2718-123">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="d2718-123">At the command line, type:</span></span>
    
    ```PowerShell
    net start w3svc
    ```

11. <span data-ttu-id="d2718-124">次のいずれかの方法で、SQL Serverデータベースに加えた変更を適用します。</span><span class="sxs-lookup"><span data-stu-id="d2718-124">Apply the changes made to the SQL Server databases by doing one of the following:</span></span>
    
    - <span data-ttu-id="d2718-125">Enterprise Edition のバック エンド サーバーで、アーカイブ データベースや監視データベースなど、このサーバーにデータベースが一覧に表示されなき場合は、コマンド ラインで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="d2718-125">If this is an Enterprise Edition Back End Server and there are no collocated databases on this server, such as Archiving or Monitoring databases, then type the following at a command line:</span></span>
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    ```

    - <span data-ttu-id="d2718-126">Enterprise Edition のバック エンド サーバーで、このサーバーにデータベースが一覧に表示されている場合は、コマンド ラインで次を入力します。</span><span class="sxs-lookup"><span data-stu-id="d2718-126">If this is an Enterprise Edition Back End Server and there are collocated databases on this server, then type the following at a command line:</span></span>
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    ```

    - <span data-ttu-id="d2718-127">これが Standard Edition サーバーの場合は、コマンド ラインで次を入力します。</span><span class="sxs-lookup"><span data-stu-id="d2718-127">If this is an Standard Edition server, type the following at a command line:</span></span>
    
    ```PowerShell
    Install-CsDatabase -Update -LocalDatabases

    ```
