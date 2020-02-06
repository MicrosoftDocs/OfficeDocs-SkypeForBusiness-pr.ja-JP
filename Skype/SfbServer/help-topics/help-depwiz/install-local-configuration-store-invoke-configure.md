---
title: ローカル構成ストアのインストールの起動 (構成)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployReplicaConfig
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 92dccbca-7a5b-4064-9f2e-964b8e62433c
description: 中央管理ストアのローカルの読み取り専用コピーを保持するデータベースのインストールを開始するには、既にインストールされている構成済みのセントラルで、トポロジビルダーを使用して発行された定義済みの構成を取得するように選択します。管理ストア、または他のメディアから定義された構成を読み取ります。 組織の内部ネットワーク上にあるコンピューターの場合は、[セントラル管理ストアから自動的に構成を取得する] を選択します。
ms.openlocfilehash: 7638ab56e2ddcc8951ae989de11e72e0817a20bc
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41823641"
---
# <a name="install-local-configuration-store-invoke-configure"></a><span data-ttu-id="2a9dc-104">ローカル構成ストアのインストールの起動 (構成)</span><span class="sxs-lookup"><span data-stu-id="2a9dc-104">Install Local Configuration Store Invoke (Configure)</span></span>
 
<span data-ttu-id="2a9dc-105">中央管理ストアのローカルの読み取り専用コピーを保持するデータベースのインストールを開始するには、既にインストールされている構成済みのセントラルで、トポロジビルダーを使用して発行された定義済みの構成を取得するように選択します。管理ストア、または他のメディアから定義された構成を読み取ります。</span><span class="sxs-lookup"><span data-stu-id="2a9dc-105">To begin the installation of the database that will hold the local read-only copy of the Central Management store, you select between retrieving the defined configuration published by using Topology Builder from the already installed and configured Central Management store, or reading the defined configuration from other media.</span></span> <span data-ttu-id="2a9dc-106">組織の内部ネットワーク上にあるコンピューターの場合は、[**セントラル管理ストアから自動的に構成を取得**する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2a9dc-106">For a machine that is on your organization's internal network, select **Retrieve configuration automatically from the Central Management Store**.</span></span>
  
<span data-ttu-id="2a9dc-107">エッジサーバーに中央管理ストアの複製をインストールする場合は、USB フラッシュドライブ、USB ハードディスクドライブ、CD-ROM などのメディアから、エクスポートした構成ドキュメントのコピーをポータブルメディアから読み取ることを選択します。</span><span class="sxs-lookup"><span data-stu-id="2a9dc-107">If you are installing a replica of the Central Management store on an Edge Server, you select to read the exported copy of the configuration document from portable media, such as a USB flash drive, USB hard disk drive, CD-ROM, or other media.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="2a9dc-108">エッジサーバーにローカル構成ストアをインストールする場合、構成情報は、Windows PowerShell コマンドレットを実行して、中央管理ストアからエクスポートした形式である必要があります。`Export-CsConfiguration -FileName <ConfigurationFilePath.zip>`</span><span class="sxs-lookup"><span data-stu-id="2a9dc-108">If you are installing the Local Configuration store on an Edge Server, the configuration information must be in a format that was exported from the Central Management store by running the Windows PowerShell cmdlet:  `Export-CsConfiguration -FileName <ConfigurationFilePath.zip>`</span></span>
  
<span data-ttu-id="2a9dc-109">適切なオプションを選んだら、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2a9dc-109">After you have selected the appropriate option, click **Next**.</span></span>
  

