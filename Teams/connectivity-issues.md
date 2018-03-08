---
title: "Microsoft チーム クライアントとの接続の問題のトラブルシューティングを行う"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "主に、ファイアウォールまたはプロキシ接続が原因で引き起こされる Microsoft チーム クライアントとの接続の問題のトラブルシューティングし、解決する方法について説明します。"
ms.openlocfilehash: 012bff35243030390ef618a5cf627e45d206c11d
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
<a name="troubleshoot-connectivity-issues-with-the-microsoft-teams-client"></a><span data-ttu-id="b2d1d-103">Microsoft チーム クライアントとの接続の問題のトラブルシューティングを行う</span><span class="sxs-lookup"><span data-stu-id="b2d1d-103">Troubleshoot connectivity issues with the Microsoft Teams client</span></span>
==============================================================

<span data-ttu-id="b2d1d-p101">Microsoft チーム クライアントで検出された問題のほとんどは、ファイアウォールまたはプロキシへの接続に戻るトレースことができます。必要な Url、IP アドレスし、ファイアウォールでポートを開くまたはプロキシが不要なトラブルシューティング最小化することを確認します。特定の情報の Url と ip アドレスが Microsoft チームに必要なのでは、 [Office 365 の Url と IP アドレス](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&rs=en-US&ad=US#bkmk_teams)のサポートの記事を参照してください。次のシナリオでは、特定の Url とポートをファイアウォールで開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2d1d-p101">Most issues discovered with the Microsoft Teams client can be traced back to firewall or proxy connectivity. Verifying that the necessary URLs, IP addresses and ports are opened in your firewall or proxy will minimize unnecessary troubleshooting. For specific information on URLs and IPs required for Microsoft Teams, please reference the [Office 365 URLs and IP Address](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&rs=en-US&ad=US#bkmk_teams) support article. The following scenarios require specific URLs and ports to be opened in the firewall.</span></span>

-   <span data-ttu-id="b2d1d-108">認証</span><span class="sxs-lookup"><span data-stu-id="b2d1d-108">Authentication</span></span>

-   <span data-ttu-id="b2d1d-109">Microsoft チーム クライアント接続</span><span class="sxs-lookup"><span data-stu-id="b2d1d-109">Microsoft Teams Client Connectivity</span></span>

-   <span data-ttu-id="b2d1d-110">グループ作業</span><span class="sxs-lookup"><span data-stu-id="b2d1d-110">Collaboration</span></span>

-   <span data-ttu-id="b2d1d-111">メディア</span><span class="sxs-lookup"><span data-stu-id="b2d1d-111">Media</span></span>

-   <span data-ttu-id="b2d1d-112">共有サービス</span><span class="sxs-lookup"><span data-stu-id="b2d1d-112">Shared Services</span></span>

-   <span data-ttu-id="b2d1d-113">サード パーティ製の統合</span><span class="sxs-lookup"><span data-stu-id="b2d1d-113">Third Party Integration</span></span>

-   <span data-ttu-id="b2d1d-114">Skype for Business の相互運用性</span><span class="sxs-lookup"><span data-stu-id="b2d1d-114">Skype for Business Interoperability</span></span>

-   <span data-ttu-id="b2d1d-115">Skype for Business クライアントの相互運用性</span><span class="sxs-lookup"><span data-stu-id="b2d1d-115">Skype for Business Client Interoperability</span></span>
