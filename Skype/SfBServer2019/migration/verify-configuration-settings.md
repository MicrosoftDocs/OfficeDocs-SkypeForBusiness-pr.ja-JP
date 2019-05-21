---
title: 構成の設定の確認
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 中央管理ストアが配置されている内部コンピューターで、または任意の場所で Skype for Business Server 2019 CsManagementStoreReplicationStatus コマンドレットを実行して、構成情報のレプリケーションをエッジサーバーに対して検証することができます。Skype for Business Server 2019 コアコンポーネント (OcsCore) がインストールされているドメインに参加しているコンピューター。
ms.openlocfilehash: 0ea966652972a97dac3e807cef42ddeaa5136322
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34307036"
---
# <a name="verify-configuration-settings"></a><span data-ttu-id="e661b-103">構成の設定の確認</span><span class="sxs-lookup"><span data-stu-id="e661b-103">Verify configuration settings</span></span>

<span data-ttu-id="e661b-104">中央管理ストアが配置されている内部コンピューターで Skype for Business Server 2019 **CsManagementStoreReplicationStatus**コマンドレットを実行して、構成情報のレプリケーションをエッジサーバーに対して検証することができます。Skype for Business Server 2019 コアコンポーネント (OcsCore) がインストールされている任意のドメインに参加しているコンピューターの場合。</span><span class="sxs-lookup"><span data-stu-id="e661b-104">You can validate the replication of configuration information to the Edge server by running the Skype for Business Server 2019 **Get-CsManagementStoreReplicationStatus** cmdlet on the internal computer on which the Central Management store is located, or on any domain-joined computer on which Skype for Business Server 2019 Core Components (OcsCore.msi) is installed.</span></span> 
  
<span data-ttu-id="e661b-105">初期結果では、レプリケーションに "True" ではなく "False" と表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="e661b-105">Initial results may indicate the status as "False" instead of "True" for replication.</span></span> <span data-ttu-id="e661b-106">その場合は、 **CsManagementStoreReplication**コマンドレットを実行して、 **CsManagementStoreReplicationStatus**をもう一度実行する前に複製処理が完了するまで待ちます。</span><span class="sxs-lookup"><span data-stu-id="e661b-106">If so, run the **Invoke-CsManagementStoreReplication** cmdlet and allow time for the replication to complete before running the **Get-CsManagementStoreReplicationStatus** again.</span></span> 
  

