---
title: ローカル構成ストアのインストールを起動 (設定)
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployReplicaConfig
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 92dccbca-7a5b-4064-9f2e-964b8e62433c
ROBOTS: NOINDEX, NOFOLLOW
description: 既にインストールされ構成されているセントラル サイトからトポロジ ビルダーを使用して発行する定義済みの構成を取得するとの間の中央管理ストアの読み取り専用のローカル コピーを保持するデータベースのインストールを開始するには、を選択します。管理ストア、またはその他のメディアから定義済みの構成を読み取り中です。 組織の内部ネットワーク上にあるマシンは、中央管理ストアから取得の構成を自動的に選択します。
ms.openlocfilehash: 87d2620b6b4b9eb36ee96e7f9b693016620d3a49
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "21003146"
---
# <a name="install-local-configuration-store-invoke-configure"></a><span data-ttu-id="da28b-104">ローカル構成ストアのインストールを起動 (設定)</span><span class="sxs-lookup"><span data-stu-id="da28b-104">Install Local Configuration Store Invoke (Configure)</span></span>
 
<span data-ttu-id="da28b-105">既にインストールされ構成されているセントラル サイトからトポロジ ビルダーを使用して発行する定義済みの構成を取得するとの間の中央管理ストアの読み取り専用のローカル コピーを保持するデータベースのインストールを開始するには、を選択します。管理ストア、またはその他のメディアから定義済みの構成を読み取り中です。</span><span class="sxs-lookup"><span data-stu-id="da28b-105">To begin the installation of the database that will hold the local read-only copy of the Central Management store, you select between retrieving the defined configuration published by using Topology Builder from the already installed and configured Central Management store, or reading the defined configuration from other media.</span></span> <span data-ttu-id="da28b-106">組織の内部ネットワーク上にあるコンピューターでは、**中央管理ストアから自動的に構成を取得する**を選択します。</span><span class="sxs-lookup"><span data-stu-id="da28b-106">For a machine that is on your organization's internal network, select **Retrieve configuration automatically from the Central Management Store**.</span></span>
  
<span data-ttu-id="da28b-107">エッジ サーバーを中央管理ストアのレプリカをインストールする場合は、USB フラッシュ ドライブ、USB ハード ディスク ドライブ、CD-ROM、またはその他のメディアなどのポータブル メディアからエクスポートされた構成の文書のコピーを読み取りが選択します。</span><span class="sxs-lookup"><span data-stu-id="da28b-107">If you are installing a replica of the Central Management store on an Edge Server, you select to read the exported copy of the configuration document from portable media, such as a USB flash drive, USB hard disk drive, CD-ROM, or other media.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="da28b-108">エッジ サーバーのローカル構成ストアをインストールする場合の構成については、必要があるサーバーの全体管理からエクスポートされた形式で保存 Windows PowerShell コマンドレットを実行しています。`Export-CsConfiguration -FileName <ConfigurationFilePath.zip>`</span><span class="sxs-lookup"><span data-stu-id="da28b-108">If you are installing the Local Configuration store on an Edge Server, the configuration information must be in a format that was exported from the Central Management store by running the Windows PowerShell cmdlet:  `Export-CsConfiguration -FileName <ConfigurationFilePath.zip>`</span></span>
  
<span data-ttu-id="da28b-109">適切なオプションを選択した後は、**次へ**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="da28b-109">After you have selected the appropriate option, click **Next**.</span></span>
  

