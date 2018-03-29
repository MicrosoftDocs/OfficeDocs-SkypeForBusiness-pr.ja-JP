---
title: Skype for Business Server 2015 での VIS サーバーの役割の展開
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b6401e67-59fe-4419-a0ab-ffac88e67632
description: '概要: ビジネス サーバー 2015 の Skype でのビデオの相互運用機能サーバー (VIS) の役割を展開します。'
ms.openlocfilehash: 4df688fa3c94f287269297ee895db192c1b924ea
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-the-vis-server-role-in-skype-for-business-server-2015"></a><span data-ttu-id="20106-103">Skype for Business Server 2015 での VIS サーバーの役割の展開</span><span class="sxs-lookup"><span data-stu-id="20106-103">Deploy the VIS server role in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="20106-104">**の概要:**ビジネス サーバー 2015 の Skype でビデオの相互運用機能サーバー (VIS) の役割を展開します。</span><span class="sxs-lookup"><span data-stu-id="20106-104">**Summary:** Deploy the Video Interop Server (VIS) role in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="20106-105">トポロジ ビルダーで作成したサーバーの VIS サービスを設定するにビジネス サーバーの展開ウィザードの Skype を起動、**インストールまたは更新の Skype ビジネス サーバー システム**を押し、ウィザードでこれらの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="20106-105">To set up the VIS service on the server just created in Topology Builder, start the Skype for Business Server deployment wizard, press **Install or Update Skype for Business Server System** and follow these steps in the wizard:</span></span>
  
1.  <span data-ttu-id="20106-106">[**ローカル構成ストアのインストール**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="20106-106">Select **Install Local Configuration Store**.</span></span>
    
2. <span data-ttu-id="20106-107">**セットアップまたは Skype ビジネス サーバー コンポーネントの削除**を選択します。</span><span class="sxs-lookup"><span data-stu-id="20106-107">Select **Setup or Remove Skype for Business Server Components**.</span></span>
    
3. <span data-ttu-id="20106-108">[**証明書の要求、インストール、または割り当て**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="20106-108">Select **Request, Install or Assign Certificates**.</span></span>
    
4. <span data-ttu-id="20106-109">[**サービスの開始**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="20106-109">Select **Start services**.</span></span>
    
<span data-ttu-id="20106-110">これで、このサービスのソフトウェアがインストールされ、稼動状態になります。</span><span class="sxs-lookup"><span data-stu-id="20106-110">The software for this service is now installed and running.</span></span> <span data-ttu-id="20106-111">ビジネス サーバー サービスの他の Skype と**Skype**ビジネス サーバー ビデオの相互運用機能のサービスが実行されているかどうかを確認する [サービス] mmc ツールを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="20106-111">You may open the Services mmc tool to see if the **Skype for Business Server Video Interop Server** service is running along with other Skype for Business Server services.</span></span> <span data-ttu-id="20106-112">次に、VIS サーバーまたはプールを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="20106-112">Next, you must configure the VIS server or pool.</span></span>
## <a name="see-also"></a><span data-ttu-id="20106-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="20106-113">See also</span></span>

#### 

[<span data-ttu-id="20106-114">ビジネス サーバー 2015 の Skype でビデオの相互運用機能のサーバーを構成します。</span><span class="sxs-lookup"><span data-stu-id="20106-114">Configure the Video Interop Server in Skype for Business Server 2015</span></span>](configure-the-vis.md)

