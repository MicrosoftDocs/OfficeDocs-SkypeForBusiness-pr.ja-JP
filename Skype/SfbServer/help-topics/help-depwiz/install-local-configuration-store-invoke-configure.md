---
title: ローカル構成ストアのインストールの起動 (構成)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 中央管理ストアのローカル読み取り専用コピーを保持するデータベースのインストールを開始するには、既にインストールおよび構成されている中央管理ストアからトポロジ ビルダーを使用して公開された定義済みの構成を取得するか、定義された構成を他のメディアから読み取る方法を選択します。 組織の内部ネットワーク上にあるコンピューターの場合は、[中央管理ストアから構成を自動的に取得する] を選択します。
ms.openlocfilehash: f0e2f54e83831cf6ad626b5d83cf068f40110f07
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827207"
---
# <a name="install-local-configuration-store-invoke-configure"></a><span data-ttu-id="f0120-104">ローカル構成ストアの起動のインストール (構成)</span><span class="sxs-lookup"><span data-stu-id="f0120-104">Install Local Configuration Store Invoke (Configure)</span></span>
 
<span data-ttu-id="f0120-105">中央管理ストアのローカル読み取り専用コピーを保持するデータベースのインストールを開始するには、既にインストールおよび構成されている中央管理ストアからトポロジ ビルダーを使用して公開された定義済みの構成を取得するか、定義された構成を他のメディアから読み取る方法を選択します。</span><span class="sxs-lookup"><span data-stu-id="f0120-105">To begin the installation of the database that will hold the local read-only copy of the Central Management store, you select between retrieving the defined configuration published by using Topology Builder from the already installed and configured Central Management store, or reading the defined configuration from other media.</span></span> <span data-ttu-id="f0120-106">組織の内部ネットワーク上にあるコンピューターの場合は、[中央管理ストアから構成を自動的に取得する] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="f0120-106">For a machine that is on your organization's internal network, select **Retrieve configuration automatically from the Central Management Store**.</span></span>
  
<span data-ttu-id="f0120-107">エッジ サーバーに中央管理ストアのレプリカをインストールする場合は、USB フラッシュ ドライブ、USB ハード ディスク ドライブ、または CD-ROM その他のポータブル メディアから、構成ドキュメントのエクスポート コピーを読み取る方法を選択します。</span><span class="sxs-lookup"><span data-stu-id="f0120-107">If you are installing a replica of the Central Management store on an Edge Server, you select to read the exported copy of the configuration document from portable media, such as a USB flash drive, USB hard disk drive, CD-ROM, or other media.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="f0120-108">エッジ サーバーにローカル構成ストアをインストールする場合、構成情報は、次のコマンドレットを実行して中央管理ストアからエクスポートされた形式Windows PowerShellがあります。  `Export-CsConfiguration -FileName <ConfigurationFilePath.zip>`</span><span class="sxs-lookup"><span data-stu-id="f0120-108">If you are installing the Local Configuration store on an Edge Server, the configuration information must be in a format that was exported from the Central Management store by running the Windows PowerShell cmdlet:  `Export-CsConfiguration -FileName <ConfigurationFilePath.zip>`</span></span>
  
<span data-ttu-id="f0120-109">適切なオプションを選択したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f0120-109">After you have selected the appropriate option, click **Next**.</span></span>
  

