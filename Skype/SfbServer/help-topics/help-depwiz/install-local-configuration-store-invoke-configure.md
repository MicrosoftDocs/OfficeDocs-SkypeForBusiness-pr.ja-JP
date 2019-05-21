---
title: ローカル構成ストアのインストールの起動 (構成)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployReplicaConfig
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 92dccbca-7a5b-4064-9f2e-964b8e62433c
description: 中央管理ストアのローカルの読み取り専用コピーを保持するデータベースのインストールを開始するには、既にインストールされている構成済みのセントラルで、トポロジビルダーを使用して発行された定義済みの構成を取得するように選択します。管理ストア、または他のメディアから定義された構成を読み取ります。 組織の内部ネットワーク上にあるコンピューターの場合は、[セントラル管理ストアから自動的に構成を取得する] を選択します。
ms.openlocfilehash: a9f72ca18c1e8848c52545ecc254dd2b142b8137
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34302949"
---
# <a name="install-local-configuration-store-invoke-configure"></a><span data-ttu-id="99522-104">ローカル構成ストアのインストールの起動 (構成)</span><span class="sxs-lookup"><span data-stu-id="99522-104">Install Local Configuration Store Invoke (Configure)</span></span>
 
<span data-ttu-id="99522-105">中央管理ストアのローカルの読み取り専用コピーを保持するデータベースのインストールを開始するには、既にインストールされている構成済みのセントラルで、トポロジビルダーを使用して発行された定義済みの構成を取得するように選択します。管理ストア、または他のメディアから定義された構成を読み取ります。</span><span class="sxs-lookup"><span data-stu-id="99522-105">To begin the installation of the database that will hold the local read-only copy of the Central Management store, you select between retrieving the defined configuration published by using Topology Builder from the already installed and configured Central Management store, or reading the defined configuration from other media.</span></span> <span data-ttu-id="99522-106">組織の内部ネットワーク上にあるコンピューターの場合は、[**セントラル管理ストアから自動的に構成を取得**する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="99522-106">For a machine that is on your organization's internal network, select **Retrieve configuration automatically from the Central Management Store**.</span></span>
  
<span data-ttu-id="99522-107">エッジサーバーに中央管理ストアの複製をインストールする場合は、USB フラッシュドライブ、USB ハードディスクドライブ、CD-ROM などのメディアから、エクスポートした構成ドキュメントのコピーをポータブルメディアから読み取ることを選択します。</span><span class="sxs-lookup"><span data-stu-id="99522-107">If you are installing a replica of the Central Management store on an Edge Server, you select to read the exported copy of the configuration document from portable media, such as a USB flash drive, USB hard disk drive, CD-ROM, or other media.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="99522-108">エッジサーバーにローカル構成ストアをインストールする場合、構成情報は、Windows PowerShell コマンドレットを実行して、中央管理ストアからエクスポートした形式である必要があります。`Export-CsConfiguration -FileName <ConfigurationFilePath.zip>`</span><span class="sxs-lookup"><span data-stu-id="99522-108">If you are installing the Local Configuration store on an Edge Server, the configuration information must be in a format that was exported from the Central Management store by running the Windows PowerShell cmdlet:  `Export-CsConfiguration -FileName <ConfigurationFilePath.zip>`</span></span>
  
<span data-ttu-id="99522-109">適切なオプションを選んだら、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="99522-109">After you have selected the appropriate option, click **Next**.</span></span>
  

