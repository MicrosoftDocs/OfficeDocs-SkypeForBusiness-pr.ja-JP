---
title: ローカル構成ストアのインストールの起動 (構成)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployReplicaConfig
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 92dccbca-7a5b-4064-9f2e-964b8e62433c
description: 既にインストールされ構成されているセントラル サイトからトポロジ ビルダーを使用して発行する定義済みの構成を取得するとの間の中央管理ストアの読み取り専用のローカル コピーを保持するデータベースのインストールを開始するには、を選択します。管理ストア、またはその他のメディアから定義済みの構成を読み取り中です。 組織の内部ネットワーク上にあるマシンは、中央管理ストアから取得の構成を自動的に選択します。
ms.openlocfilehash: e9a5744d9a73c1f7263a78f3852d5915f5703066
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33910982"
---
# <a name="install-local-configuration-store-invoke-configure"></a><span data-ttu-id="57b81-104">ローカル構成ストアのインストールの起動 (構成)</span><span class="sxs-lookup"><span data-stu-id="57b81-104">Install Local Configuration Store Invoke (Configure)</span></span>
 
<span data-ttu-id="57b81-105">既にインストールされ構成されているセントラル サイトからトポロジ ビルダーを使用して発行する定義済みの構成を取得するとの間の中央管理ストアの読み取り専用のローカル コピーを保持するデータベースのインストールを開始するには、を選択します。管理ストア、またはその他のメディアから定義済みの構成を読み取り中です。</span><span class="sxs-lookup"><span data-stu-id="57b81-105">To begin the installation of the database that will hold the local read-only copy of the Central Management store, you select between retrieving the defined configuration published by using Topology Builder from the already installed and configured Central Management store, or reading the defined configuration from other media.</span></span> <span data-ttu-id="57b81-106">組織の内部ネットワーク上にあるコンピューターでは、**中央管理ストアから自動的に構成を取得する**を選択します。</span><span class="sxs-lookup"><span data-stu-id="57b81-106">For a machine that is on your organization's internal network, select **Retrieve configuration automatically from the Central Management Store**.</span></span>
  
<span data-ttu-id="57b81-107">エッジ サーバーを中央管理ストアのレプリカをインストールする場合は、USB フラッシュ ドライブ、USB ハード ディスク ドライブ、CD-ROM、またはその他のメディアなどのポータブル メディアからエクスポートされた構成の文書のコピーを読み取りが選択します。</span><span class="sxs-lookup"><span data-stu-id="57b81-107">If you are installing a replica of the Central Management store on an Edge Server, you select to read the exported copy of the configuration document from portable media, such as a USB flash drive, USB hard disk drive, CD-ROM, or other media.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="57b81-108">エッジ サーバーのローカル構成ストアをインストールする場合の構成については、必要があるサーバーの全体管理からエクスポートされた形式で保存 Windows PowerShell コマンドレットを実行しています。`Export-CsConfiguration -FileName <ConfigurationFilePath.zip>`</span><span class="sxs-lookup"><span data-stu-id="57b81-108">If you are installing the Local Configuration store on an Edge Server, the configuration information must be in a format that was exported from the Central Management store by running the Windows PowerShell cmdlet:  `Export-CsConfiguration -FileName <ConfigurationFilePath.zip>`</span></span>
  
<span data-ttu-id="57b81-109">適切なオプションを選択した後は、**次へ**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="57b81-109">After you have selected the appropriate option, click **Next**.</span></span>
  

