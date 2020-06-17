---
title: 通話受付管理のリセット
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
description: 従来のフロントエンドプールが通話受付管理 (CAC) をホストしている場合は、従来のフロントエンドプールを削除する前に、CAC ホスティングを Skype for Business Server 2019 プールに移動する必要があります。
ms.openlocfilehash: 850ab5c13483d024d52c483c63ef09468f8374b3
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753299"
---
# <a name="reset-call-admission-control"></a><span data-ttu-id="53ed0-103">通話受付管理のリセット</span><span class="sxs-lookup"><span data-stu-id="53ed0-103">Reset call admission control</span></span>

<span data-ttu-id="53ed0-104">従来のフロントエンドプールが通話受付管理 (CAC) をホストしている場合は、従来のフロントエンドプールを削除する前に、CAC ホスティングを Skype for Business Server 2019 プールに移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="53ed0-104">If a legacy Front End pool is hosting call admission control (CAC), you must move CAC hosting to a Skype for Business Server 2019 pool before you can remove the legacy Front End pool.</span></span>
  
### <a name="to-reset-cac"></a><span data-ttu-id="53ed0-105">CAC をリセットするには</span><span class="sxs-lookup"><span data-stu-id="53ed0-105">To reset CAC</span></span>

1. <span data-ttu-id="53ed0-106">トポロジ ビルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="53ed0-106">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="53ed0-107">サイト ノードを右クリックし、[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53ed0-107">Right-click the site node, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="53ed0-108">[**通話受付管理の設定**] で、[**通話受付管理の有効化**] が選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="53ed0-108">Under **Call Admission Control setting**, make sure **Enable Call Admission Control** is selected.</span></span> 
    
4. <span data-ttu-id="53ed0-109">[**フロントエンドプール] で通話受付管理 (cac) を実行する**には、cac をホストする Skype For business Server 2019 プールを選択し、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53ed0-109">Under **Front End pool to run call admission control (CAC)**, select the Skype for Business Server 2019 pool that is to host CAC, and then click **OK**.</span></span>
    
5. <span data-ttu-id="53ed0-110">トポロジを公開します。</span><span class="sxs-lookup"><span data-stu-id="53ed0-110">Publish the topology.</span></span>
    

