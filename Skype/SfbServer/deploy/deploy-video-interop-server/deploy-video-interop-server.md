---
title: Skype for Business Server でビデオ相互運用機能サーバーを展開する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bb7d2abd-d033-4d7d-b588-6d9228c3eccf
description: '概要: VIS server の役割を Skype for Business Server に展開します。'
ms.openlocfilehash: c6ee0e52a4ac84622fee9ba281a64d1094c38c4c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34302736"
---
# <a name="deploy-video-interop-server-in-skype-for-business-server"></a><span data-ttu-id="f404a-103">Skype for Business Server でビデオ相互運用機能サーバーを展開する</span><span class="sxs-lookup"><span data-stu-id="f404a-103">Deploy Video Interop Server in Skype for Business Server</span></span>
 
<span data-ttu-id="f404a-104">**概要:** VIS server の役割を Skype for Business Server に展開します。</span><span class="sxs-lookup"><span data-stu-id="f404a-104">**Summary:** Deploy the VIS server role in Skype for Business Server.</span></span>
  
<span data-ttu-id="f404a-105">Skype for Business Server は、cisco C60 や Cisco MX300 などの Cisco の会議システム (VTCs) と直接統合できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="f404a-105">Skype for Business Server can now integrate directly with Cisco teleconferencing systems (VTCs) such as the Cisco C60 or Cisco MX300.</span></span> <span data-ttu-id="f404a-106">これには、ビデオ相互運用サーバー (VIS) と呼ばれる新しいサーバーの役割が導入され、VIS と相互運用する機器の両方が適切に構成されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f404a-106">This requires the introduction of a new server role called the Video Interop Server (VIS), and correct configuration of both the VIS and the equipment it will interoperate with.</span></span> <span data-ttu-id="f404a-107">Cisco ユニファイドコミュニケーションマネージャー (CUCM) などの既存の Cisco インフラストラクチャとの VTC レジスタ、およびビデオ SIP トランクは、CUCM と VIS プールの間で使用されます。</span><span class="sxs-lookup"><span data-stu-id="f404a-107">A VTC registers with existing Cisco infrastructure such as Cisco Unified Communication Manager (CUCM), and a video SIP trunk is used between CUCM and the VIS pool.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="f404a-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="f404a-108">In this section</span></span>

<span data-ttu-id="f404a-109">VIS サーバーまたはプールと VTC システムの間の相互運用を構成するには、次の 5 つの手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f404a-109">Configuring interoperability between a VIS server or pool and VTC systems requires performing the following five procedures:</span></span> 
  
- [<span data-ttu-id="f404a-110">Skype for Business Server で VIS プールを作成する</span><span class="sxs-lookup"><span data-stu-id="f404a-110">Create a VIS pool in Skype for Business Server</span></span>](create-a-vis-pool.md)
    
- [<span data-ttu-id="f404a-111">VIS server の役割を Skype for Business Server に展開する</span><span class="sxs-lookup"><span data-stu-id="f404a-111">Deploy the VIS server role in Skype for Business Server</span></span>](deploy-the-vis-server-role.md)
    
- [<span data-ttu-id="f404a-112">Skype for Business Server でビデオ相互運用機能サーバーを構成する</span><span class="sxs-lookup"><span data-stu-id="f404a-112">Configure the Video Interop Server in Skype for Business Server</span></span>](configure-the-vis.md)
    
- [<span data-ttu-id="f404a-113">Skype for Business Server との相互運用用に CUCM を構成する</span><span class="sxs-lookup"><span data-stu-id="f404a-113">Configure CUCM for Interoperation with Skype for Business Server</span></span>](configure-cucm-for-interoperation.md)
    
- [<span data-ttu-id="f404a-114">Skype for Business Server との相互運用用に VTC を構成する</span><span class="sxs-lookup"><span data-stu-id="f404a-114">Configure a VTC for Interoperation with Skype for Business Server</span></span>](configure-a-vtc-for-interoperation.md)
    
## <a name="related-sections"></a><span data-ttu-id="f404a-115">関連セクション</span><span class="sxs-lookup"><span data-stu-id="f404a-115">Related sections</span></span>

[<span data-ttu-id="f404a-116">Skype for Business Server のビデオ相互運用機能サーバーを計画する</span><span class="sxs-lookup"><span data-stu-id="f404a-116">Plan for Video Interop Server in Skype for Business Server</span></span>](../../plan-your-deployment/video-interop-server.md)
  

