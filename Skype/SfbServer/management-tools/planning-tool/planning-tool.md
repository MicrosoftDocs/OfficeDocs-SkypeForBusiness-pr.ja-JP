---
title: Skype for Business Server 2015 計画ツール
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 2a352f62-c5cb-4ef1-9aa9-7f0c1ab47455
description: Skype for Business Server 2015 計画ツールの使用に関するガイダンス。
ms.openlocfilehash: b130ca05200ea30bed8008399050affa96438644
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34288951"
---
# <a name="skype-for-business-server-2015-planning-tool"></a><span data-ttu-id="55560-103">Skype for Business Server 2015 計画ツール</span><span class="sxs-lookup"><span data-stu-id="55560-103">Skype for Business Server 2015 Planning Tool</span></span>
 
<span data-ttu-id="55560-104">Skype for Business Server 2015 計画ツールの使用に関するガイダンス。</span><span class="sxs-lookup"><span data-stu-id="55560-104">Guidance on using the Skype for Business Server 2015 Planning Tool.</span></span>
  
<span data-ttu-id="55560-105">Skype for Business Server 2015 計画ツールは、設計している Skype for Business Server 2015 トポロジについて質問するための、ウィザードベースのインタビュー型ツールです。</span><span class="sxs-lookup"><span data-stu-id="55560-105">The Skype for Business Server 2015 Planning Tool is a wizard driven, interview-like tool that asks questions about the Skype for Business Server 2015 topology that you are designing.</span></span> <span data-ttu-id="55560-106">計画ツールでは、提供された情報を使用して、トポロジの設計とキャパシティの推奨される方法と共に、指定された回答に基づいて推奨されるトポロジを提示します。</span><span class="sxs-lookup"><span data-stu-id="55560-106">The Planning Tool uses the information supplied, coupled with preferred practices for topology design and capacity, to present a recommended topology based on the answers supplied.</span></span> <span data-ttu-id="55560-107">計画ツールは、 [Skype For Business Server 2015 計画ツール](https://go.microsoft.com/fwlink/p/?LinkID=282725)からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="55560-107">You can download the Planning Tool from the [Skype for Business Server 2015 Planning Tool](https://go.microsoft.com/fwlink/p/?LinkID=282725).</span></span>
  
<span data-ttu-id="55560-108">最終的に、計画ツールの目標は、完成した Skype for Business Server 2015 トポロジの設計の複雑さを簡単にすることです。</span><span class="sxs-lookup"><span data-stu-id="55560-108">Ultimately, the goal of the Planning Tool is to ease the potential complexity of designing a complete Skype for Business Server 2015 topology.</span></span> <span data-ttu-id="55560-109">このツールは、Microsoft の web サイトに接続するためにインターネット接続が利用可能であることを考慮して、ツール内の計画および展開ドキュメントへのコンテキスト参照も提供します。</span><span class="sxs-lookup"><span data-stu-id="55560-109">The tool also provides contextual references to planning and deployment documentation inside the tool, provided that an Internet connection is available to connect to the Microsoft  website.</span></span>
  
<span data-ttu-id="55560-110">インフラストラクチャの TCP/IP アドレスと完全修飾ドメイン名 (Fqdn) を使用してトポロジをカスタマイズすると、計画ツールによって、ドメインネームシステム (DNS) 名前付け、ファイアウォールルール、証明書などの一連のレポートが利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="55560-110">After customizing the topology with the infrastructure's TCP/IP addresses and fully qualified domain names (FQDNs), the Planning Tool makes available a series of reports that cover Domain Name System (DNS) naming, firewall rules, certificates, and more.</span></span> 
  
<span data-ttu-id="55560-111">このツールを使用することは、実装計画における最初の手順になります。</span><span class="sxs-lookup"><span data-stu-id="55560-111">Using this tool is the first step in planning your implementation.</span></span> <span data-ttu-id="55560-112">次の手順では、 [skype For Business server 2015 キャパシティ電卓](https://www.microsoft.com/en-us/download/details.aspx?id=51196)にサイト情報の詳細を入力し、必要に応じて調整して、 [Skype for business Server 2015 のストレスとパフォーマンスツール](https://www.microsoft.com/en-us/download/details.aspx?id=50367)を使って、お客様のニーズに応じて実装されます。</span><span class="sxs-lookup"><span data-stu-id="55560-112">The next step would be to input your site information specifics into the [Skype for Business Server 2015 Capacity Calculator](https://www.microsoft.com/en-us/download/details.aspx?id=51196), adjust as needed, then use the [Skype for Business Server 2015 Stress and Performance Tool](https://www.microsoft.com/en-us/download/details.aspx?id=50367) to simulate and verify the implementation will serve your needs.</span></span>
  
<span data-ttu-id="55560-113">計画ツールでは、次の2つの形式で情報をエクスポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="55560-113">The Planning Tool also provides the ability to export information in two formats:</span></span>
  
- <span data-ttu-id="55560-114">Microsoft Excel (.xml スプレッドシート)</span><span class="sxs-lookup"><span data-stu-id="55560-114">Microsoft Excel (.xml spreadsheet)</span></span>
    
- <span data-ttu-id="55560-115">Microsoft Visio (.vdx)</span><span class="sxs-lookup"><span data-stu-id="55560-115">Microsoft Visio (.vdx)</span></span>
    
<span data-ttu-id="55560-116">次のトピックでは、計画ツールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="55560-116">The following topics introduce and detail the Planning Tool.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="55560-117">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="55560-117">In this section</span></span>

- [<span data-ttu-id="55560-118">Install the Planning Tool in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="55560-118">Install the Planning Tool in Skype for Business Server 2015</span></span>](install.md)
    
- [<span data-ttu-id="55560-119">Optional Software</span><span class="sxs-lookup"><span data-stu-id="55560-119">Optional Software</span></span>](install.md#Optional_Software)
    
- [<span data-ttu-id="55560-120">Navigate the Planning Tool in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="55560-120">Navigate the Planning Tool in Skype for Business Server 2015</span></span>](navigate.md)
    
- [<span data-ttu-id="55560-121">Create the initial topology design for Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="55560-121">Create the initial topology design for Skype for Business Server 2015</span></span>](create-the-initial-design.md)
    
- [<span data-ttu-id="55560-122">Edit the topology in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="55560-122">Edit the topology in Skype for Business Server 2015</span></span>](edit-the-topology.md)
    
- [<span data-ttu-id="55560-123">Edit the network configuration diagram</span><span class="sxs-lookup"><span data-stu-id="55560-123">Edit the network configuration diagram</span></span>](edit-the-topology.md#Edit_Network_diagram)
    
- [<span data-ttu-id="55560-124">Review the Administrator Reports in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="55560-124">Review the Administrator Reports in Skype for Business Server 2015</span></span>](review-the-administrator-reports.md)
    
## <a name="see-also"></a><span data-ttu-id="55560-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="55560-125">See also</span></span>

[<span data-ttu-id="55560-126">Skype for Business Server 2015 のインストール</span><span class="sxs-lookup"><span data-stu-id="55560-126">Install Skype for Business Server 2015</span></span>](../../deploy/install/install.md)
  
[<span data-ttu-id="55560-127">Plan for instant messaging and presence in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="55560-127">Plan for instant messaging and presence in Skype for Business Server 2015</span></span>](../../plan-your-deployment/instant-messaging-and-presence.md)
