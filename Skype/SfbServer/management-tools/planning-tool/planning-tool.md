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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 2a352f62-c5cb-4ef1-9aa9-7f0c1ab47455
description: Skype for Business Server 2015 計画ツールの使用に関するガイダンス。
ms.openlocfilehash: 8eec7865b74640cf6dfe4f5a5122f4c7091cc5ae
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050099"
---
# <a name="skype-for-business-server-2015-planning-tool"></a><span data-ttu-id="db250-103">Skype for Business Server 2015 計画ツール</span><span class="sxs-lookup"><span data-stu-id="db250-103">Skype for Business Server 2015 Planning Tool</span></span>
 
<span data-ttu-id="db250-104">Skype for Business Server 2015 計画ツールの使用に関するガイダンス。</span><span class="sxs-lookup"><span data-stu-id="db250-104">Guidance on using the Skype for Business Server 2015 Planning Tool.</span></span>
  
<span data-ttu-id="db250-105">Skype for Business Server 2015 の計画ツールは、設計している Skype for Business Server 2015 トポロジに関する質問をする、ウィザードに基づくインタビューのようなツールです。</span><span class="sxs-lookup"><span data-stu-id="db250-105">The Skype for Business Server 2015 Planning Tool is a wizard driven, interview-like tool that asks questions about the Skype for Business Server 2015 topology that you are designing.</span></span> <span data-ttu-id="db250-106">計画ツールは、提供された情報を使用して、トポロジ設計および容量の推奨プラクティスと組み合わせ、指定された回答に基づいて推奨されるトポロジを提示します。</span><span class="sxs-lookup"><span data-stu-id="db250-106">The Planning Tool uses the information supplied, coupled with preferred practices for topology design and capacity, to present a recommended topology based on the answers supplied.</span></span> <span data-ttu-id="db250-107">計画ツールは、 [Skype For Business Server 2015 Planning tool](https://go.microsoft.com/fwlink/p/?LinkID=282725)からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="db250-107">You can download the Planning Tool from the [Skype for Business Server 2015 Planning Tool](https://go.microsoft.com/fwlink/p/?LinkID=282725).</span></span>
  
<span data-ttu-id="db250-108">最終的には、計画ツールの目的は、完全な Skype for Business Server 2015 トポロジ設計の複雑さを軽減することです。</span><span class="sxs-lookup"><span data-stu-id="db250-108">Ultimately, the goal of the Planning Tool is to ease the potential complexity of designing a complete Skype for Business Server 2015 topology.</span></span> <span data-ttu-id="db250-109">また、このツールは、Microsoft web サイトに接続できるインターネット接続が提供されている場合に、ツール内の計画および展開に関するドキュメントへのコンテキスト参照も提供します。</span><span class="sxs-lookup"><span data-stu-id="db250-109">The tool also provides contextual references to planning and deployment documentation inside the tool, provided that an Internet connection is available to connect to the Microsoft  website.</span></span>
  
<span data-ttu-id="db250-110">インフラストラクチャの TCP/IP アドレスと完全修飾ドメイン名 (Fqdn) を使用してトポロジをカスタマイズした後、計画ツールでは、ドメインネームシステム (DNS) の名前付け、ファイアウォールルール、証明書などをカバーする一連のレポートを利用できます。</span><span class="sxs-lookup"><span data-stu-id="db250-110">After customizing the topology with the infrastructure's TCP/IP addresses and fully qualified domain names (FQDNs), the Planning Tool makes available a series of reports that cover Domain Name System (DNS) naming, firewall rules, certificates, and more.</span></span> 
  
<span data-ttu-id="db250-111">このツールの使用は、実装を計画する際の最初の手順です。</span><span class="sxs-lookup"><span data-stu-id="db250-111">Using this tool is the first step in planning your implementation.</span></span> <span data-ttu-id="db250-112">次の手順として、 [skype For Business server 2015 容量計算機](https://www.microsoft.com/download/details.aspx?id=51196)にサイト情報の詳細を入力し、必要に応じて調整した後、 [Skype for business Server の2015ストレスおよびパフォーマンスツール](https://www.microsoft.com/download/details.aspx?id=50367)を使用して、実装が自分のニーズを満たすようにシミュレーションし、検証します。</span><span class="sxs-lookup"><span data-stu-id="db250-112">The next step would be to input your site information specifics into the [Skype for Business Server 2015 Capacity Calculator](https://www.microsoft.com/download/details.aspx?id=51196), adjust as needed, then use the [Skype for Business Server 2015 Stress and Performance Tool](https://www.microsoft.com/download/details.aspx?id=50367) to simulate and verify the implementation will serve your needs.</span></span>
  
<span data-ttu-id="db250-113">また、計画ツールでは、次の2つの形式で情報をエクスポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="db250-113">The Planning Tool also provides the ability to export information in two formats:</span></span>
  
- <span data-ttu-id="db250-114">Microsoft Excel (.xml スプレッドシート)</span><span class="sxs-lookup"><span data-stu-id="db250-114">Microsoft Excel (.xml spreadsheet)</span></span>
    
- <span data-ttu-id="db250-115">Microsoft Visio (.vdx)</span><span class="sxs-lookup"><span data-stu-id="db250-115">Microsoft Visio (.vdx)</span></span>
    
<span data-ttu-id="db250-116">次のトピックでは、計画ツールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="db250-116">The following topics introduce and detail the Planning Tool.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="db250-117">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="db250-117">In this section</span></span>

- [<span data-ttu-id="db250-118">Skype for Business Server 2015 に計画ツールをインストールする</span><span class="sxs-lookup"><span data-stu-id="db250-118">Install the Planning Tool in Skype for Business Server 2015</span></span>](install.md)
    
- [<span data-ttu-id="db250-119">オプションのソフトウェア</span><span class="sxs-lookup"><span data-stu-id="db250-119">Optional Software</span></span>](install.md#Optional_Software)
    
- [<span data-ttu-id="db250-120">Skype for Business Server 2015 の計画ツールに移動する</span><span class="sxs-lookup"><span data-stu-id="db250-120">Navigate the Planning Tool in Skype for Business Server 2015</span></span>](navigate.md)
    
- [<span data-ttu-id="db250-121">Skype for Business Server 2015 の初期トポロジ設計を作成する</span><span class="sxs-lookup"><span data-stu-id="db250-121">Create the initial topology design for Skype for Business Server 2015</span></span>](create-the-initial-design.md)
    
- [<span data-ttu-id="db250-122">Skype for Business Server 2015 でトポロジを編集する</span><span class="sxs-lookup"><span data-stu-id="db250-122">Edit the topology in Skype for Business Server 2015</span></span>](edit-the-topology.md)
    
- [<span data-ttu-id="db250-123">ネットワーク構成図を編集する</span><span class="sxs-lookup"><span data-stu-id="db250-123">Edit the network configuration diagram</span></span>](edit-the-topology.md#Edit_Network_diagram)
    
- [<span data-ttu-id="db250-124">Skype for Business Server 2015 での管理者レポートの確認</span><span class="sxs-lookup"><span data-stu-id="db250-124">Review the Administrator Reports in Skype for Business Server 2015</span></span>](review-the-administrator-reports.md)
    
## <a name="see-also"></a><span data-ttu-id="db250-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="db250-125">See also</span></span>

[<span data-ttu-id="db250-126">Skype for Business Server 2015 のインストール</span><span class="sxs-lookup"><span data-stu-id="db250-126">Install Skype for Business Server 2015</span></span>](../../deploy/install/install.md)
  
[<span data-ttu-id="db250-127">Skype for Business Server 2015 でのインスタントメッセージングおよびプレゼンスの計画</span><span class="sxs-lookup"><span data-stu-id="db250-127">Plan for instant messaging and presence in Skype for Business Server 2015</span></span>](../../plan-your-deployment/instant-messaging-and-presence.md)
