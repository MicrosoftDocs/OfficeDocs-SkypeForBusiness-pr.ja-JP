---
title: Skype for Business Server 2015 計画ツール
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 2a352f62-c5cb-4ef1-9aa9-7f0c1ab47455
description: Skype for Business Server 2015 計画ツールの使用に関するガイダンス。
ms.openlocfilehash: aef46fac65ba1d5651cada81bc79cfc21021bf54
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832387"
---
# <a name="skype-for-business-server-2015-planning-tool"></a><span data-ttu-id="086a0-103">Skype for Business Server 2015 計画ツール</span><span class="sxs-lookup"><span data-stu-id="086a0-103">Skype for Business Server 2015 Planning Tool</span></span>
 
<span data-ttu-id="086a0-104">Skype for Business Server 2015 計画ツールの使用に関するガイダンス。</span><span class="sxs-lookup"><span data-stu-id="086a0-104">Guidance on using the Skype for Business Server 2015 Planning Tool.</span></span>
  
<span data-ttu-id="086a0-105">Skype for Business Server 2015 計画ツールは、設計中の Skype for Business Server 2015 トポロジに関する質問を行うウィザード駆動型のインタビュー形式のツールです。</span><span class="sxs-lookup"><span data-stu-id="086a0-105">The Skype for Business Server 2015 Planning Tool is a wizard driven, interview-like tool that asks questions about the Skype for Business Server 2015 topology that you are designing.</span></span> <span data-ttu-id="086a0-106">計画ツールは、提供された情報をトポロジの設計と容量の推奨プラクティスと組み合って使用し、提供された回答に基づいて推奨トポロジを提示します。</span><span class="sxs-lookup"><span data-stu-id="086a0-106">The Planning Tool uses the information supplied, coupled with preferred practices for topology design and capacity, to present a recommended topology based on the answers supplied.</span></span> <span data-ttu-id="086a0-107">計画ツールは [、Skype for Business Server 2015 計画ツールからダウンロードできます](https://go.microsoft.com/fwlink/p/?LinkID=282725)。</span><span class="sxs-lookup"><span data-stu-id="086a0-107">You can download the Planning Tool from the [Skype for Business Server 2015 Planning Tool](https://go.microsoft.com/fwlink/p/?LinkID=282725).</span></span>
  
<span data-ttu-id="086a0-108">最終的には、計画ツールの目標は、完全な Skype for Business Server 2015 トポロジを設計する場合の潜在的な複雑さを緩和します。</span><span class="sxs-lookup"><span data-stu-id="086a0-108">Ultimately, the goal of the Planning Tool is to ease the potential complexity of designing a complete Skype for Business Server 2015 topology.</span></span> <span data-ttu-id="086a0-109">また、このツールは、Microsoft Web サイトへの接続にインターネット接続が可能な場合に、ツール内の計画と展開に関するドキュメントへのコンテキスト参照も提供します。</span><span class="sxs-lookup"><span data-stu-id="086a0-109">The tool also provides contextual references to planning and deployment documentation inside the tool, provided that an Internet connection is available to connect to the Microsoft  website.</span></span>
  
<span data-ttu-id="086a0-110">インフラストラクチャの TCP/IP アドレスと完全修飾ドメイン名 (FQDN) を使用してトポロジをカスタマイズした後、計画ツールは、ドメイン ネーム システム (DNS) の名前付け、ファイアウォール規則、証明書などの一連のレポートを利用できます。</span><span class="sxs-lookup"><span data-stu-id="086a0-110">After customizing the topology with the infrastructure's TCP/IP addresses and fully qualified domain names (FQDNs), the Planning Tool makes available a series of reports that cover Domain Name System (DNS) naming, firewall rules, certificates, and more.</span></span> 
  
<span data-ttu-id="086a0-111">このツールの使用は、実装を計画する最初の手順です。</span><span class="sxs-lookup"><span data-stu-id="086a0-111">Using this tool is the first step in planning your implementation.</span></span> <span data-ttu-id="086a0-112">次の手順では [、Skype for Business Server 2015](https://www.microsoft.com/download/details.aspx?id=51196)容量計算機にサイト情報の詳細を入力し、必要に応じて調整してから [、Skype for Business Server 2015 Stress and Performance Tool](https://www.microsoft.com/download/details.aspx?id=50367) を使用して、実装がニーズに応じて機能することをシミュレートおよび検証します。</span><span class="sxs-lookup"><span data-stu-id="086a0-112">The next step would be to input your site information specifics into the [Skype for Business Server 2015 Capacity Calculator](https://www.microsoft.com/download/details.aspx?id=51196), adjust as needed, then use the [Skype for Business Server 2015 Stress and Performance Tool](https://www.microsoft.com/download/details.aspx?id=50367) to simulate and verify the implementation will serve your needs.</span></span>
  
<span data-ttu-id="086a0-113">計画ツールでは、次の 2 つの形式で情報をエクスポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="086a0-113">The Planning Tool also provides the ability to export information in two formats:</span></span>
  
- <span data-ttu-id="086a0-114">Microsoft Excel (.xml スプレッドシート)</span><span class="sxs-lookup"><span data-stu-id="086a0-114">Microsoft Excel (.xml spreadsheet)</span></span>
    
- <span data-ttu-id="086a0-115">Microsoft Visio (.vdx)</span><span class="sxs-lookup"><span data-stu-id="086a0-115">Microsoft Visio (.vdx)</span></span>
    
<span data-ttu-id="086a0-116">以下のトピックでは、計画ツールについて説明し、詳細を説明します。</span><span class="sxs-lookup"><span data-stu-id="086a0-116">The following topics introduce and detail the Planning Tool.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="086a0-117">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="086a0-117">In this section</span></span>

- [<span data-ttu-id="086a0-118">Skype for Business Server 2015 での計画ツールのインストール</span><span class="sxs-lookup"><span data-stu-id="086a0-118">Install the Planning Tool in Skype for Business Server 2015</span></span>](install.md)
    
- [<span data-ttu-id="086a0-119">オプションのソフトウェア</span><span class="sxs-lookup"><span data-stu-id="086a0-119">Optional Software</span></span>](install.md#Optional_Software)
    
- [<span data-ttu-id="086a0-120">Skype for Business Server 2015 の計画ツールを移動する</span><span class="sxs-lookup"><span data-stu-id="086a0-120">Navigate the Planning Tool in Skype for Business Server 2015</span></span>](navigate.md)
    
- [<span data-ttu-id="086a0-121">Skype for Business Server 2015 の初期トポロジ設計を作成する</span><span class="sxs-lookup"><span data-stu-id="086a0-121">Create the initial topology design for Skype for Business Server 2015</span></span>](create-the-initial-design.md)
    
- [<span data-ttu-id="086a0-122">Skype for Business Server 2015 でのトポロジの編集</span><span class="sxs-lookup"><span data-stu-id="086a0-122">Edit the topology in Skype for Business Server 2015</span></span>](edit-the-topology.md)
    
- [<span data-ttu-id="086a0-123">ネットワーク構成図を編集する</span><span class="sxs-lookup"><span data-stu-id="086a0-123">Edit the network configuration diagram</span></span>](edit-the-topology.md#Edit_Network_diagram)
    
- [<span data-ttu-id="086a0-124">Skype for Business Server 2015 の管理者レポートを確認する</span><span class="sxs-lookup"><span data-stu-id="086a0-124">Review the Administrator Reports in Skype for Business Server 2015</span></span>](review-the-administrator-reports.md)
    
## <a name="see-also"></a><span data-ttu-id="086a0-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="086a0-125">See also</span></span>

[<span data-ttu-id="086a0-126">Skype for Business Server 2015 のインストール</span><span class="sxs-lookup"><span data-stu-id="086a0-126">Install Skype for Business Server 2015</span></span>](../../deploy/install/install.md)
  
[<span data-ttu-id="086a0-127">Skype for Business Server 2015 でのインスタント メッセージングとプレゼンスの計画</span><span class="sxs-lookup"><span data-stu-id="086a0-127">Plan for instant messaging and presence in Skype for Business Server 2015</span></span>](../../plan-your-deployment/instant-messaging-and-presence.md)
