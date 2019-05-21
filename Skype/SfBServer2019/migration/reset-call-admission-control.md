---
title: 通話受付管理のリセット
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 従来のフロントエンドプールが通話受付制御 (CAC) をホストしている場合は、従来のフロントエンドプールを削除する前に、CAC ホスティングを Skype for Business Server 2019 プールに移動する必要があります。
ms.openlocfilehash: 7b4aa42b20bfad5506d47c16038d1765f3ac8571
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34307099"
---
# <a name="reset-call-admission-control"></a><span data-ttu-id="d9e1d-103">通話受付管理のリセット</span><span class="sxs-lookup"><span data-stu-id="d9e1d-103">Reset call admission control</span></span>

<span data-ttu-id="d9e1d-104">従来のフロントエンドプールが通話受付制御 (CAC) をホストしている場合は、従来のフロントエンドプールを削除する前に、CAC ホスティングを Skype for Business Server 2019 プールに移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9e1d-104">If a legacy Front End pool is hosting call admission control (CAC), you must move CAC hosting to a Skype for Business Server 2019 pool before you can remove the legacy Front End pool.</span></span>
  
### <a name="to-reset-cac"></a><span data-ttu-id="d9e1d-105">CAC をリセットするには</span><span class="sxs-lookup"><span data-stu-id="d9e1d-105">To reset CAC</span></span>

1. <span data-ttu-id="d9e1d-106">トポロジビルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="d9e1d-106">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="d9e1d-107">サイトノードを右クリックし、[プロパティの**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d9e1d-107">Right-click the site node, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="d9e1d-108">「**通話受付制御の設定**」で、「**通話受付制御を有効にする**」が選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d9e1d-108">Under **Call Admission Control setting**, make sure **Enable Call Admission Control** is selected.</span></span> 
    
4. <span data-ttu-id="d9e1d-109">[**フロントエンドプール] で通話受付制御 (cac) を実行する**には、cac をホストする Skype For business Server 2019 プールを選び、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d9e1d-109">Under **Front End pool to run call admission control (CAC)**, select the Skype for Business Server 2019 pool that is to host CAC, and then click **OK**.</span></span>
    
5. <span data-ttu-id="d9e1d-110">トポロジを公開します。</span><span class="sxs-lookup"><span data-stu-id="d9e1d-110">Publish the topology.</span></span>
    

