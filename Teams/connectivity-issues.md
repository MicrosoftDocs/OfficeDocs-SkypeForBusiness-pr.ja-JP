---
title: Microsoft Teams クライアントの接続性の問題をトラブルシューティングする
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/21/2018
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
description: ファイアウォールまたはプロキシ接続が主な原因である Microsoft Teams クライアントの接続性の問題をトラブルシューティングする方法について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5204c745da00535b0838d06a00709ffa31146a3e
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/07/2019
ms.locfileid: "30461661"
---
<a name="troubleshoot-connectivity-issues-with-the-microsoft-teams-client"></a><span data-ttu-id="8df26-103">Microsoft Teams クライアントの接続性の問題をトラブルシューティングする</span><span class="sxs-lookup"><span data-stu-id="8df26-103">Troubleshoot connectivity issues with the Microsoft Teams client</span></span>
==============================================================

<span data-ttu-id="8df26-104">マイクロソフト チーム クライアントで検出された問題のほとんどは、ファイアウォールまたはプロキシへの接続に戻るトレースできます。</span><span class="sxs-lookup"><span data-stu-id="8df26-104">Most issues discovered with the Microsoft Teams client can be traced back to firewall or proxy connectivity.</span></span> <span data-ttu-id="8df26-105">必要な Url、IP アドレスしポートをファイアウォールで開くまたはプロキシの不要なトラブルシューティングが最小限に抑えられますことを確認しています。</span><span class="sxs-lookup"><span data-stu-id="8df26-105">Verifying that the necessary URLs, IP addresses and ports are opened in your firewall or proxy will minimize unnecessary troubleshooting.</span></span> <span data-ttu-id="8df26-106">マイクロソフトのチームに必要な ip アドレスおよび Url の特定について[Office 365 の Url と IP アドレス](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2)をサポート資料を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8df26-106">For specific information on URLs and IPs required for Microsoft Teams, please see the [Office 365 URLs and IP Address](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) support article.</span></span> <span data-ttu-id="8df26-107">次のシナリオでは、特定の Url とポートをファイアウォールで開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="8df26-107">The following scenarios require specific URLs and ports to be opened in the firewall.</span></span>

-   <span data-ttu-id="8df26-108">認証</span><span class="sxs-lookup"><span data-stu-id="8df26-108">Authentication</span></span>

-   <span data-ttu-id="8df26-109">Microsoft Teams クライアントの接続性</span><span class="sxs-lookup"><span data-stu-id="8df26-109">Microsoft Teams Client Connectivity</span></span>

-   <span data-ttu-id="8df26-110">コラボレーション</span><span class="sxs-lookup"><span data-stu-id="8df26-110">Collaboration</span></span>

-   <span data-ttu-id="8df26-111">メディア</span><span class="sxs-lookup"><span data-stu-id="8df26-111">Media</span></span>

-   <span data-ttu-id="8df26-112">共有サービス</span><span class="sxs-lookup"><span data-stu-id="8df26-112">Shared Services</span></span>

-   <span data-ttu-id="8df26-113">サードパーティ統合</span><span class="sxs-lookup"><span data-stu-id="8df26-113">Third Party Integration</span></span>

-   <span data-ttu-id="8df26-114">Skype For Business の相互運用</span><span class="sxs-lookup"><span data-stu-id="8df26-114">Skype for Business Interoperability</span></span>

-   <span data-ttu-id="8df26-115">Skype for Business クライアントの相互運用</span><span class="sxs-lookup"><span data-stu-id="8df26-115">Skype for Business Client Interoperability</span></span>
