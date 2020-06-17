---
title: 構成の設定を確認する
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 中央管理ストアが配置されている内部コンピューターで、または Skype for Business Server 2019 コアコンポーネント (OcsCore.msi) がインストールされているドメインに参加しているコンピューターで、Skype for Business Server 2019 コマンドレットを実行することによって、エッジサーバーへの構成情報のレプリケーションを検証できます。
ms.openlocfilehash: dd270bd54bb427cf3fc74fe0081ef2e383a58589
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752149"
---
# <a name="verify-configuration-settings"></a><span data-ttu-id="48eb5-103">構成の設定を確認する</span><span class="sxs-lookup"><span data-stu-id="48eb5-103">Verify configuration settings</span></span>

<span data-ttu-id="48eb5-104">中央管理ストアが配置されている内部コンピューターで、または Skype for business Server 2019 コアコンポーネント (OcsCore.msi) がインストールされている任意のドメインに参加しているコンピューターで、Skype for Business **server 2019 コマンド**レットを実行して、エッジサーバーへの構成情報のレプリケーションを検証できます。</span><span class="sxs-lookup"><span data-stu-id="48eb5-104">You can validate the replication of configuration information to the Edge server by running the Skype for Business Server 2019 **Get-CsManagementStoreReplicationStatus** cmdlet on the internal computer on which the Central Management store is located, or on any domain-joined computer on which Skype for Business Server 2019 Core Components (OcsCore.msi) is installed.</span></span> 
  
<span data-ttu-id="48eb5-105">最初の結果では、レプリケーションに関する状態が "True" ではなく "False" と示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="48eb5-105">Initial results may indicate the status as "False" instead of "True" for replication.</span></span> <span data-ttu-id="48eb5-106">その場合、**Invoke-CsManagementStoreReplication** コマンドレットを実行し、時間をおいて、レプリケーションが完了してから再び **Get-CsManagementStoreReplicationStatus** コマンドレットを実行してください。</span><span class="sxs-lookup"><span data-stu-id="48eb5-106">If so, run the **Invoke-CsManagementStoreReplication** cmdlet and allow time for the replication to complete before running the **Get-CsManagementStoreReplicationStatus** again.</span></span> 
  

