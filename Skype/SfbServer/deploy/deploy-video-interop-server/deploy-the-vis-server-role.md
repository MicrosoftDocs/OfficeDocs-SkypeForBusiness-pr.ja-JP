---
title: Skype for Business Server で VIS サーバーの役割を展開する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b6401e67-59fe-4419-a0ab-ffac88e67632
description: '概要: Skype for Business Server にビデオ相互運用サーバー (VIS) の役割を展開します。'
ms.openlocfilehash: 773e2ddf790aa1b6c36ff6926d8bc4d16ea613f5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801967"
---
# <a name="deploy-the-vis-server-role-in-skype-for-business-server"></a><span data-ttu-id="53762-103">Skype for Business Server で VIS サーバーの役割を展開する</span><span class="sxs-lookup"><span data-stu-id="53762-103">Deploy the VIS server role in Skype for Business Server</span></span>
 
<span data-ttu-id="53762-104">**概要:** Skype for Business Server にビデオ相互運用サーバー (VIS) の役割を展開します。</span><span class="sxs-lookup"><span data-stu-id="53762-104">**Summary:** Deploy the Video Interop Server (VIS) role in Skype for Business Server.</span></span>
  
<span data-ttu-id="53762-105">トポロジ ビルダーで作成したサーバーで VIS サービスをセットアップするには、Skype for Business Server 展開ウィザードを起動し **、Skype for Business Server システム** のインストールまたは更新を押し、ウィザードで次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="53762-105">To set up the VIS service on the server just created in Topology Builder, start the Skype for Business Server deployment wizard, press **Install or Update Skype for Business Server System** and follow these steps in the wizard:</span></span>
  
1.  <span data-ttu-id="53762-106">[ローカル **構成ストアのインストール] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="53762-106">Select **Install Local Configuration Store**.</span></span>
    
2. <span data-ttu-id="53762-107">[セットアップ **] または [Skype for Business Server コンポーネントの削除] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="53762-107">Select **Setup or Remove Skype for Business Server Components**.</span></span>
    
3. <span data-ttu-id="53762-108">[証明書 **の要求、インストール、または割り当て] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="53762-108">Select **Request, Install or Assign Certificates**.</span></span>
    
4. <span data-ttu-id="53762-109">[サービス **の開始] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="53762-109">Select **Start services**.</span></span>
    
<span data-ttu-id="53762-110">このサービスのソフトウェアがインストールされ、実行されています。</span><span class="sxs-lookup"><span data-stu-id="53762-110">The software for this service is now installed and running.</span></span> <span data-ttu-id="53762-111">サービス mmc ツールを開き **、Skype for Business Server ビデオ** 相互運用サーバー サービスが他の Skype for Business Server サービスと共に実行されていないか確認できます。</span><span class="sxs-lookup"><span data-stu-id="53762-111">You may open the Services mmc tool to see if the **Skype for Business Server Video Interop Server** service is running along with other Skype for Business Server services.</span></span> <span data-ttu-id="53762-112">次に、VIS サーバーまたはプールを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="53762-112">Next, you must configure the VIS server or pool.</span></span>
## <a name="see-also"></a><span data-ttu-id="53762-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="53762-113">See also</span></span>

[<span data-ttu-id="53762-114">Skype for Business Server でビデオ相互運用サーバーを構成する</span><span class="sxs-lookup"><span data-stu-id="53762-114">Configure the Video Interop Server in Skype for Business Server</span></span>](configure-the-vis.md)
