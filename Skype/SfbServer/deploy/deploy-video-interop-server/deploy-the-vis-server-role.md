---
title: VIS server の役割を Skype for Business Server に展開する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b6401e67-59fe-4419-a0ab-ffac88e67632
description: '概要: Skype for Business Server で、ビデオ相互運用機能サーバー (VIS) の役割を展開します。'
ms.openlocfilehash: 1fadab718a37dba2ffee5338d4dc898316b4d24d
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41798044"
---
# <a name="deploy-the-vis-server-role-in-skype-for-business-server"></a><span data-ttu-id="79611-103">VIS server の役割を Skype for Business Server に展開する</span><span class="sxs-lookup"><span data-stu-id="79611-103">Deploy the VIS server role in Skype for Business Server</span></span>
 
<span data-ttu-id="79611-104">**概要:** Skype for Business Server にビデオ相互運用サーバー (VIS) の役割を展開します。</span><span class="sxs-lookup"><span data-stu-id="79611-104">**Summary:** Deploy the Video Interop Server (VIS) role in Skype for Business Server.</span></span>
  
<span data-ttu-id="79611-105">Topology Builder で作成したばかりのサーバー上で VIS サービスを設定するには、Skype for Business Server 展開ウィザードを起動し、[ **skype For Business Server システムのインストールまたは更新**] をクリックして、ウィザードの次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="79611-105">To set up the VIS service on the server just created in Topology Builder, start the Skype for Business Server deployment wizard, press **Install or Update Skype for Business Server System** and follow these steps in the wizard:</span></span>
  
1.  <span data-ttu-id="79611-106">[**ローカル構成ストアのインストール**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="79611-106">Select **Install Local Configuration Store**.</span></span>
    
2. <span data-ttu-id="79611-107">[ **Skype For Business Server コンポーネントのセットアップまたは削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="79611-107">Select **Setup or Remove Skype for Business Server Components**.</span></span>
    
3. <span data-ttu-id="79611-108">[**証明書の要求、インストール、または割り当て**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="79611-108">Select **Request, Install or Assign Certificates**.</span></span>
    
4. <span data-ttu-id="79611-109">[**サービスの開始**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="79611-109">Select **Start services**.</span></span>
    
<span data-ttu-id="79611-110">The software for this service is now installed and running.</span><span class="sxs-lookup"><span data-stu-id="79611-110">The software for this service is now installed and running.</span></span> <span data-ttu-id="79611-111">[サービス] mmc ツールを開いて、Skype for business **server のビデオ相互運用機能サーバー**サービスが他の Skype For business server サービスと共に実行されているかどうかを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="79611-111">You may open the Services mmc tool to see if the **Skype for Business Server Video Interop Server** service is running along with other Skype for Business Server services.</span></span> <span data-ttu-id="79611-112">Next, you must configure the VIS server or pool.</span><span class="sxs-lookup"><span data-stu-id="79611-112">Next, you must configure the VIS server or pool.</span></span>
## <a name="see-also"></a><span data-ttu-id="79611-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="79611-113">See also</span></span>

[<span data-ttu-id="79611-114">Skype for Business Server でビデオ相互運用機能サーバーを構成する</span><span class="sxs-lookup"><span data-stu-id="79611-114">Configure the Video Interop Server in Skype for Business Server</span></span>](configure-the-vis.md)
