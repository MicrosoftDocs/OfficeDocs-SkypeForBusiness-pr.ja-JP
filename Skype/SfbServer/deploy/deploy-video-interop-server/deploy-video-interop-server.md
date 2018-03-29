---
title: Skype for Business Server 2015 でのビデオ相互運用サーバーの展開
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bb7d2abd-d033-4d7d-b588-6d9228c3eccf
description: '概要: ビジネス サーバー 2015 の Skype で VIS のサーバーの役割を展開します。'
ms.openlocfilehash: 0716ce427814c7cf17385074727a7af4f45cfd66
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-video-interop-server-in-skype-for-business-server-2015"></a><span data-ttu-id="b9118-103">Skype for Business Server 2015 でのビデオ相互運用サーバーの展開</span><span class="sxs-lookup"><span data-stu-id="b9118-103">Deploy Video Interop Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="b9118-104">**の概要:**ビジネス サーバー 2015 の Skype で VIS のサーバーの役割を展開します。</span><span class="sxs-lookup"><span data-stu-id="b9118-104">**Summary:** Deploy the VIS server role in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="b9118-105">Skype ビジネス サーバーの Cisco C60 または Cisco MX300 のような Cisco 遠隔会議システム (VTCs) と直接統合できます。</span><span class="sxs-lookup"><span data-stu-id="b9118-105">Skype for Business Server can now integrate directly with Cisco teleconferencing systems (VTCs) such as the Cisco C60 or Cisco MX300.</span></span> <span data-ttu-id="b9118-106">これには、新しいサーバーの役割、ビデオの相互運用機能サーバー (VIS)、および、VIS と機器の両方の構成が正しいと呼ばれることと相互作用の導入が必要です。</span><span class="sxs-lookup"><span data-stu-id="b9118-106">This requires the introduction of a new server role called the Video Interop Server (VIS), and correct configuration of both the VIS and the equipment it will interoperate with.</span></span> <span data-ttu-id="b9118-107">などシスコ ユニファイド コミュニケーション マネージャー (CUCM)、既存の Cisco インフラストラクチャと、VTC を登録し、CUCM と VIS のプールとの間にビデオの SIP トランクを使用します。</span><span class="sxs-lookup"><span data-stu-id="b9118-107">A VTC registers with existing Cisco infrastructure such as Cisco Unified Communication Manager (CUCM), and a video SIP trunk is used between CUCM and the VIS pool.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="b9118-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="b9118-108">In this section</span></span>

<span data-ttu-id="b9118-109">VIS サーバーまたはプールと VTC システムの間の相互運用を構成するには、次の 5 つの手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b9118-109">Configuring interoperability between a VIS server or pool and VTC systems requires performing the following five procedures:</span></span> 
  
- [<span data-ttu-id="b9118-110">ビジネス サーバー 2015 の Skype で VIS プールを作成する.</span><span class="sxs-lookup"><span data-stu-id="b9118-110">Create a VIS pool in Skype for Business Server 2015</span></span>](create-a-vis-pool.md)
    
- [<span data-ttu-id="b9118-111">ビジネス サーバー 2015 用 Skype で VIS のサーバーの役割を展開します。</span><span class="sxs-lookup"><span data-stu-id="b9118-111">Deploy the VIS server role in Skype for Business Server 2015</span></span>](deploy-the-vis-server-role.md)
    
- [<span data-ttu-id="b9118-112">ビジネス サーバー 2015 の Skype でビデオの相互運用機能のサーバーを構成します。</span><span class="sxs-lookup"><span data-stu-id="b9118-112">Configure the Video Interop Server in Skype for Business Server 2015</span></span>](configure-the-vis.md)
    
- [<span data-ttu-id="b9118-113">ビジネス サーバー 2015 の Skype での相互運用のため CUCM を構成します。</span><span class="sxs-lookup"><span data-stu-id="b9118-113">Configure CUCM for Interoperation with Skype for Business Server 2015</span></span>](configure-cucm-for-interoperation.md)
    
- [<span data-ttu-id="b9118-114">ビジネス サーバー 2015 の Skype での相互運用のため、VTC を構成します。</span><span class="sxs-lookup"><span data-stu-id="b9118-114">Configure a VTC for Interoperation with Skype for Business Server 2015</span></span>](configure-a-vtc-for-interoperation.md)
    
## <a name="related-sections"></a><span data-ttu-id="b9118-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="b9118-115">Related sections</span></span>

[<span data-ttu-id="b9118-116">ビジネス サーバー 2015 の Skype でのビデオの相互運用サーバーの計画</span><span class="sxs-lookup"><span data-stu-id="b9118-116">Plan for Video Interop Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/video-interop-server.md)
  

