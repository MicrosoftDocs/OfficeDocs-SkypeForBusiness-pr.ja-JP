---
title: 構成設定を確認します。
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 中央管理ストアに保存されている、またはいずれかの内部コンピューターの CsManagementStoreReplicationStatus-ビジネス サーバー 2019 Get コマンドレットの Skype を実行して、エッジ サーバーの構成情報のレプリケーションを検証することができます。ビジネス サーバー 2019 のコア ・ コンポーネント (OcsCore.msi) の Skype がインストールされているコンピューターをドメインに参加します。
ms.openlocfilehash: 23a5b4c3af8ac02ebfd620d3bbc46ddcba5bea11
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "25027810"
---
# <a name="verify-configuration-settings"></a><span data-ttu-id="aae34-103">構成設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="aae34-103">Verify configuration settings</span></span>

<span data-ttu-id="aae34-104">中央管理ストアに配置されて、内部コンピューターのビジネス サーバー 2019 **Get CsManagementStoreReplicationStatus**コマンドレットの Skype を実行して、エッジ サーバーに構成情報のレプリケーションを検証することができますかドメインに参加しているコンピューターはビジネス サーバー 2019 のコア ・ コンポーネント (OcsCore.msi) の Skype がインストールされています。</span><span class="sxs-lookup"><span data-stu-id="aae34-104">You can validate the replication of configuration information to the Edge server by running the Skype for Business Server 2019 **Get-CsManagementStoreReplicationStatus** cmdlet on the internal computer on which the Central Management store is located, or on any domain-joined computer on which Skype for Business Server 2019 Core Components (OcsCore.msi) is installed.</span></span> 
  
<span data-ttu-id="aae34-105">初期結果可能性があります状態"False"と"True"ではなくレプリケーション用です。</span><span class="sxs-lookup"><span data-stu-id="aae34-105">Initial results may indicate the status as "False" instead of "True" for replication.</span></span> <span data-ttu-id="aae34-106">場合は、**呼び出し CsManagementStoreReplication**コマンドレットを実行し、 **Get CsManagementStoreReplicationStatus**をもう一度実行する前に完了するのには、レプリケーションの時間を確保します。</span><span class="sxs-lookup"><span data-stu-id="aae34-106">If so, run the **Invoke-CsManagementStoreReplication** cmdlet and allow time for the replication to complete before running the **Get-CsManagementStoreReplicationStatus** again.</span></span> 
  

