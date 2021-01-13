---
title: Skype for Business Server でのビデオ相互運用サーバーの展開
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
ms.assetid: bb7d2abd-d033-4d7d-b588-6d9228c3eccf
description: '概要: Skype for Business Server に VIS サーバーの役割を展開します。'
ms.openlocfilehash: 7b3ee96b1ff2e6c633efa9e1cc98aa14bb5babc3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801957"
---
# <a name="deploy-video-interop-server-in-skype-for-business-server"></a><span data-ttu-id="ae470-103">Skype for Business Server でのビデオ相互運用サーバーの展開</span><span class="sxs-lookup"><span data-stu-id="ae470-103">Deploy Video Interop Server in Skype for Business Server</span></span>
 
<span data-ttu-id="ae470-104">**概要:** Skype for Business Server に VIS サーバーの役割を展開します。</span><span class="sxs-lookup"><span data-stu-id="ae470-104">**Summary:** Deploy the VIS server role in Skype for Business Server.</span></span>
  
<span data-ttu-id="ae470-105">Skype for Business Server は、Cisco C60 や Cisco MX300 などの Cisco 電話会議システム (VTC) と直接統合できます。</span><span class="sxs-lookup"><span data-stu-id="ae470-105">Skype for Business Server can now integrate directly with Cisco teleconferencing systems (VTCs) such as the Cisco C60 or Cisco MX300.</span></span> <span data-ttu-id="ae470-106">これには、ビデオ相互運用サーバー (VIS) と呼ばれる新しいサーバーの役割を導入し、VIS と相互運用する機器の両方を正しく構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae470-106">This requires the introduction of a new server role called the Video Interop Server (VIS), and correct configuration of both the VIS and the equipment it will interoperate with.</span></span> <span data-ttu-id="ae470-107">VTC は、Cisco Unified Communication Manager (CUCM) などの既存の Cisco インフラストラクチャに登録され、CUCM と VIS プールの間でビデオ SIP トランクが使用されます。</span><span class="sxs-lookup"><span data-stu-id="ae470-107">A VTC registers with existing Cisco infrastructure such as Cisco Unified Communication Manager (CUCM), and a video SIP trunk is used between CUCM and the VIS pool.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="ae470-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="ae470-108">In this section</span></span>

<span data-ttu-id="ae470-109">VIS サーバーまたはプールと VTC システム間の相互運用性を構成するには、次の 5 つの手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae470-109">Configuring interoperability between a VIS server or pool and VTC systems requires performing the following five procedures:</span></span> 
  
- [<span data-ttu-id="ae470-110">Skype for Business Server で VIS プールを作成する</span><span class="sxs-lookup"><span data-stu-id="ae470-110">Create a VIS pool in Skype for Business Server</span></span>](create-a-vis-pool.md)
    
- [<span data-ttu-id="ae470-111">Skype for Business Server での VIS サーバーの役割の展開</span><span class="sxs-lookup"><span data-stu-id="ae470-111">Deploy the VIS server role in Skype for Business Server</span></span>](deploy-the-vis-server-role.md)
    
- [<span data-ttu-id="ae470-112">Skype for Business Server でビデオ相互運用サーバーを構成する</span><span class="sxs-lookup"><span data-stu-id="ae470-112">Configure the Video Interop Server in Skype for Business Server</span></span>](configure-the-vis.md)
    
- [<span data-ttu-id="ae470-113">Skype for Business Server との相互運用のための CUCM の構成</span><span class="sxs-lookup"><span data-stu-id="ae470-113">Configure CUCM for Interoperation with Skype for Business Server</span></span>](configure-cucm-for-interoperation.md)
    
- [<span data-ttu-id="ae470-114">Skype for Business Server との相互運用のための VTC の構成</span><span class="sxs-lookup"><span data-stu-id="ae470-114">Configure a VTC for Interoperation with Skype for Business Server</span></span>](configure-a-vtc-for-interoperation.md)
    
## <a name="related-sections"></a><span data-ttu-id="ae470-115">関連情報</span><span class="sxs-lookup"><span data-stu-id="ae470-115">Related sections</span></span>

[<span data-ttu-id="ae470-116">Skype for Business Server でのビデオ相互運用サーバーの計画</span><span class="sxs-lookup"><span data-stu-id="ae470-116">Plan for Video Interop Server in Skype for Business Server</span></span>](../../plan-your-deployment/video-interop-server.md)
  

