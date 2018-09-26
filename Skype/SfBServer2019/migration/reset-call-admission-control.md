---
title: 通話受付管理のリセット
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 従来のフロント エンド プールは、呼受付制御 (CAC) でホストされている場合、CAC は、従来のフロント エンド プールを削除する前に、Skype のビジネス サーバー 2019 プールにホストを移動する必要があります。
ms.openlocfilehash: 65d56d000c5bcec5f7aae73413c287dee8ab29ca
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "25027320"
---
# <a name="reset-call-admission-control"></a><span data-ttu-id="d418a-103">通話受付管理のリセット</span><span class="sxs-lookup"><span data-stu-id="d418a-103">Reset call admission control</span></span>

<span data-ttu-id="d418a-104">従来のフロント エンド プールは、呼受付制御 (CAC) でホストされている場合、CAC は、従来のフロント エンド プールを削除する前に、Skype のビジネス サーバー 2019 プールにホストを移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d418a-104">If a legacy Front End pool is hosting call admission control (CAC), you must move CAC hosting to a Skype for Business Server 2019 pool before you can remove the legacy Front End pool.</span></span>
  
### <a name="to-reset-cac"></a><span data-ttu-id="d418a-105">CAC をリセットするのには</span><span class="sxs-lookup"><span data-stu-id="d418a-105">To reset CAC</span></span>

1. <span data-ttu-id="d418a-106">トポロジ ビルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="d418a-106">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="d418a-107">[サイト] ノードを右クリックし、**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d418a-107">Right-click the site node, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="d418a-108">**呼の受付制御の設定**、[**電話受付制御を有効にする**が選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d418a-108">Under **Call Admission Control setting**, make sure **Enable Call Admission Control** is selected.</span></span> 
    
4. <span data-ttu-id="d418a-109">**呼受付制御 (CAC) を実行するフロント エンド プール**] の下には、CAC をホストするビジネス サーバー 2019 プールの Skype を選択し、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d418a-109">Under **Front End pool to run call admission control (CAC)**, select the Skype for Business Server 2019 pool that is to host CAC, and then click **OK**.</span></span>
    
5. <span data-ttu-id="d418a-110">トポロジを公開します。</span><span class="sxs-lookup"><span data-stu-id="d418a-110">Publish the topology.</span></span>
    

