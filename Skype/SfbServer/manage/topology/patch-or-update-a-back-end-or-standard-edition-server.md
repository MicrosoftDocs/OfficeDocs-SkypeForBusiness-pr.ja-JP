---
title: Skype for Business Server 2015 のバックエンド サーバーまたは Standard Edition サーバーのパッチまたは更新
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f95f8d3a-e039-484e-97bd-d727db21a12b
description: '概要: ビジネス サーバーの Skype のバック エンド サーバー上の更新プログラムまたは修正プログラムをインストールする方法を説明します。'
ms.openlocfilehash: 14acff1aea501bf47dff95053259187570d2f990
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="patch-or-update-a-back-end-server-or-standard-edition-server-in-skype-for-business-server-2015"></a><span data-ttu-id="766dd-103">Skype for Business Server 2015 のバックエンド サーバーまたは Standard Edition サーバーのパッチまたは更新</span><span class="sxs-lookup"><span data-stu-id="766dd-103">Patch or update a Back End Server or Standard Edition server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="766dd-104">**の概要:**ビジネス サーバーの Skype のバック エンド サーバー上の更新プログラムまたは修正プログラムをインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="766dd-104">**Summary:** Learn how to install an update or patch on a Back End Server in Skype for Business Server.</span></span>
  
<span data-ttu-id="766dd-105">このトピックでは、エンタープライズ エディション バック エンド サーバーまたは Standard Edition サーバーに更新プログラムをインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="766dd-105">This topic explains how to install an update on an Enterprise Edition Back End Server or a Standard Edition server.</span></span>
  
<span data-ttu-id="766dd-106">場合は、バック エンド サーバーを 30 分以上にアップグレードするときに、ユーザーが復元モードに進みます。</span><span class="sxs-lookup"><span data-stu-id="766dd-106">If a Back End Server is down for at least 30 minutes while you are upgrading it, users may then go into resiliency mode.</span></span> <span data-ttu-id="766dd-107">アップグレードが完了すると、バック エンド サーバーがプール内のフロント エンド サーバーと接続がもう一度、すべての機能にユーザーが返されます。</span><span class="sxs-lookup"><span data-stu-id="766dd-107">When the upgrade is finished and the Back End Servers has again connected with the Front End Servers in the pool, users are returned to full functionality.</span></span> <span data-ttu-id="766dd-108">アップグレードが 30 分未満の場合、ユーザーには影響ありません。</span><span class="sxs-lookup"><span data-stu-id="766dd-108">If the upgrade takes less than 30 minutes, users will not be affected.</span></span>
  
### <a name="to-update-a-back-end-server-or-standard-edition-server"></a><span data-ttu-id="766dd-109">バックエンド サーバーまたは Standard Edition サーバーを更新するには</span><span class="sxs-lookup"><span data-stu-id="766dd-109">To update a back end server or Standard Edition server</span></span>

1. <span data-ttu-id="766dd-110">アップグレードするサーバーに CsAdministrator の役割のメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="766dd-110">Log on to the server you are upgrading as a member of the CsAdministrator role.</span></span>
    
2. <span data-ttu-id="766dd-111">更新をダウンロードして、ローカル ハードディスクに抽出します。</span><span class="sxs-lookup"><span data-stu-id="766dd-111">Download the update and extract it to the local hard disk.</span></span>
    
3. <span data-ttu-id="766dd-112">ビジネス サーバー管理シェルには、Skype を起動する: [**スタート**] ボタン、[**すべてのプログラム**] をクリックして、**ビジネス 2015年の Skype**をクリック**ビジネス サーバー管理シェルの Skype**.</span><span class="sxs-lookup"><span data-stu-id="766dd-112">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**..</span></span>
    
4. <span data-ttu-id="766dd-113">Skype をビジネス サーバー サービスを停止します。</span><span class="sxs-lookup"><span data-stu-id="766dd-113">Stop Skype for Business Server services.</span></span> <span data-ttu-id="766dd-114">コマンド ラインで次を入力します。</span><span class="sxs-lookup"><span data-stu-id="766dd-114">At the command line, type:</span></span>
    
    ```
    Stop-CsWindowsService
    ```

5. <span data-ttu-id="766dd-p103">World Wide Web サービスを停止します。コマンド ラインで次を入力します。</span><span class="sxs-lookup"><span data-stu-id="766dd-p103">Stop the World Wide Web service. At the command line, type:</span></span>
    
    ```
    net stop w3svc
   ```

6. <span data-ttu-id="766dd-117">すべての Skype ビジネス サーバー管理シェル ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="766dd-117">Close all Skype for Business Server Management Shell windows.</span></span>
    
7. <span data-ttu-id="766dd-118">更新をインストールします。</span><span class="sxs-lookup"><span data-stu-id="766dd-118">Install the update.</span></span>
    
8. <span data-ttu-id="766dd-119">ビジネス サーバー管理シェルには、Skype を起動する: [**スタート**] ボタン、[**すべてのプログラム**] をクリックして、**ビジネス 2015年の Skype**をクリック**ビジネス サーバー管理シェルの Skype**.</span><span class="sxs-lookup"><span data-stu-id="766dd-119">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**..</span></span>
    
9. <span data-ttu-id="766dd-120">-D のアセンブリをグローバル アセンブリ キャッシュ (GAC) をキャッチするには、もう一度ビジネス サーバー サービスの Skype を停止します。</span><span class="sxs-lookup"><span data-stu-id="766dd-120">Stop Skype for Business Server services again to catch Global Assembly Cache (GAC) -d assemblies.</span></span> <span data-ttu-id="766dd-121">コマンド ラインで次を入力します。</span><span class="sxs-lookup"><span data-stu-id="766dd-121">At the command line, type:</span></span>
    
    ```
    Stop-CsWindowsService
    ```

10. <span data-ttu-id="766dd-p105">World Wide Web サービスを再起動します。コマンド ラインで次を入力します。</span><span class="sxs-lookup"><span data-stu-id="766dd-p105">Restart the World Wide Web service. At the command line, type:</span></span>
    
    ```
    net start w3svc
    ```

11. <span data-ttu-id="766dd-124">次のいずれかを実行して、SQL Server データベースに対する変更を適用します。</span><span class="sxs-lookup"><span data-stu-id="766dd-124">Apply the changes made to the SQL Server databases by doing one of the following:</span></span>
    
    - <span data-ttu-id="766dd-125">エンタープライズ エディション バック エンド サーバー、アーカイブなど、サーバー上に配置されているデータベースやデータベースの監視が存在しない、する場合は、コマンド ・ ラインで次を入力します。</span><span class="sxs-lookup"><span data-stu-id="766dd-125">If this is an Enterprise Edition Back End Server and there are no collocated databases on this server, such as Archiving or Monitoring databases, then type the following at a command line:</span></span>
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    ```

    - <span data-ttu-id="766dd-126">これは、エンタープライズ エディション バック エンド サーバーであり、このサーバー上に配置されているデータベースがある場合、は、コマンド ・ ラインで次を入力します。</span><span class="sxs-lookup"><span data-stu-id="766dd-126">If this is an Enterprise Edition Back End Server and there are collocated databases on this server, then type the following at a command line:</span></span>
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    ```

    - <span data-ttu-id="766dd-127">Standard Edition サーバーの場合は、コマンド ・ ラインで次を入力します。</span><span class="sxs-lookup"><span data-stu-id="766dd-127">If this is an Standard Edition server, type the following at a command line:</span></span>
    
    ```
    Install-CsDatabase -Update -LocalDatabases

    ```


