---
title: Microsoft Teams クライアントとの接続に関するトラブルシューティングを行う
ms.reviewer: ''
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/21/2018
ms.topic: troubleshooting
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
f1.keywords:
- NOCSH
description: ファイアウォールまたはプロキシ接続が主な原因である Microsoft Teams クライアントの接続性の問題をトラブルシューティングする方法について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: a12be097d0609f3631b6761f31350603b283faa2
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41825355"
---
<a name="troubleshoot-connectivity-issues-with-the-microsoft-teams-client"></a><span data-ttu-id="afaf9-103">Microsoft Teams クライアントとの接続に関するトラブルシューティングを行う</span><span class="sxs-lookup"><span data-stu-id="afaf9-103">Troubleshoot connectivity issues with the Microsoft Teams client</span></span>
==============================================================

<span data-ttu-id="afaf9-104">Microsoft Teams クライアントで発生する問題のほとんどは、ファイアウォールやプロキシ接続に原因があります。</span><span class="sxs-lookup"><span data-stu-id="afaf9-104">Most issues discovered with the Microsoft Teams client can be traced back to firewall or proxy connectivity.</span></span> <span data-ttu-id="afaf9-105">必要な URL、IP アドレス、ポートがファイアウォールやプロキシで開かれていることを確認することにより、不要なトラブルシューティングを最小限に抑えることができます。</span><span class="sxs-lookup"><span data-stu-id="afaf9-105">Verifying that the necessary URLs, IP addresses and ports are opened in your firewall or proxy will minimize unnecessary troubleshooting.</span></span> <span data-ttu-id="afaf9-106">Microsoft Teams に必要な URL と IP に関する具体的な情報については、サポート記事の「[Office 365 の URL と IP アドレス](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="afaf9-106">For specific information on URLs and IPs required for Microsoft Teams, please see the [Office 365 URLs and IP Address](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) support article.</span></span> <span data-ttu-id="afaf9-107">次のシナリオでは、ファイアウォールで特定の URL とポートを開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="afaf9-107">The following scenarios require specific URLs and ports to be opened in the firewall.</span></span>

-   <span data-ttu-id="afaf9-108">認証</span><span class="sxs-lookup"><span data-stu-id="afaf9-108">Authentication</span></span>

-   <span data-ttu-id="afaf9-109">Microsoft Teams クライアントの接続性</span><span class="sxs-lookup"><span data-stu-id="afaf9-109">Microsoft Teams Client Connectivity</span></span>

-   <span data-ttu-id="afaf9-110">グループ作業</span><span class="sxs-lookup"><span data-stu-id="afaf9-110">Collaboration</span></span>

-   <span data-ttu-id="afaf9-111">メディア</span><span class="sxs-lookup"><span data-stu-id="afaf9-111">Media</span></span>

-   <span data-ttu-id="afaf9-112">[共有サービス]</span><span class="sxs-lookup"><span data-stu-id="afaf9-112">Shared Services</span></span>

-   <span data-ttu-id="afaf9-113">サードパーティ統合</span><span class="sxs-lookup"><span data-stu-id="afaf9-113">Third Party Integration</span></span>

-   <span data-ttu-id="afaf9-114">Skype For Business の相互運用</span><span class="sxs-lookup"><span data-stu-id="afaf9-114">Skype for Business Interoperability</span></span>

-   <span data-ttu-id="afaf9-115">Skype for Business クライアントの相互運用</span><span class="sxs-lookup"><span data-stu-id="afaf9-115">Skype for Business Client Interoperability</span></span>
