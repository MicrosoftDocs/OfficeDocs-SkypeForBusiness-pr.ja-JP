---
title: 通話受付管理のリセット
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 従来のフロントエンドプールが通話受付制御 (CAC) をホストしている場合は、従来のフロントエンドプールを削除する前に、CAC ホスティングを Skype for Business Server 2019 プールに移動する必要があります。
ms.openlocfilehash: cbc481e55d044ef196bd91dbfa8f7ebc796f28b5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812805"
---
# <a name="reset-call-admission-control"></a><span data-ttu-id="2c2a6-103">通話受付管理のリセット</span><span class="sxs-lookup"><span data-stu-id="2c2a6-103">Reset call admission control</span></span>

<span data-ttu-id="2c2a6-104">従来のフロントエンドプールが通話受付制御 (CAC) をホストしている場合は、従来のフロントエンドプールを削除する前に、CAC ホスティングを Skype for Business Server 2019 プールに移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2c2a6-104">If a legacy Front End pool is hosting call admission control (CAC), you must move CAC hosting to a Skype for Business Server 2019 pool before you can remove the legacy Front End pool.</span></span>
  
### <a name="to-reset-cac"></a><span data-ttu-id="2c2a6-105">CAC をリセットするには</span><span class="sxs-lookup"><span data-stu-id="2c2a6-105">To reset CAC</span></span>

1. <span data-ttu-id="2c2a6-106">トポロジビルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="2c2a6-106">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="2c2a6-107">サイトノードを右クリックし、[プロパティの**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2c2a6-107">Right-click the site node, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="2c2a6-108">「**通話受付制御の設定**」で、「**通話受付制御を有効にする**」が選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2c2a6-108">Under **Call Admission Control setting**, make sure **Enable Call Admission Control** is selected.</span></span> 
    
4. <span data-ttu-id="2c2a6-109">[**フロントエンドプール] で通話受付制御 (cac) を実行する**には、cac をホストする Skype For business Server 2019 プールを選び、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2c2a6-109">Under **Front End pool to run call admission control (CAC)**, select the Skype for Business Server 2019 pool that is to host CAC, and then click **OK**.</span></span>
    
5. <span data-ttu-id="2c2a6-110">トポロジを公開します。</span><span class="sxs-lookup"><span data-stu-id="2c2a6-110">Publish the topology.</span></span>
    

