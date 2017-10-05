---
title: "Microsoft Teams クライアントの接続性の問題をトラブルシューティングする | Microsoft サポート"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "ファイアウォールまたはプロキシ接続が主な原因である Microsoft Teams クライアントの接続性の問題をトラブルシューティングする方法について説明します。"
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: fdba24620fca80b12b4e86780b19203436e7c9f4
ms.sourcegitcommit: 2e557e90b4e30fe99ff9df3897b8e54f38ea2f2e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2017
---
<a name="troubleshoot-connectivity-issues-with-the-microsoft-teams-client"></a><span data-ttu-id="b5b9f-103">Microsoft Teams クライアントの接続性の問題をトラブルシューティングする</span><span class="sxs-lookup"><span data-stu-id="b5b9f-103">Troubleshoot connectivity issues with the Microsoft Teams client</span></span>
==============================================================

<span data-ttu-id="b5b9f-p101">Microsoft Teams クライアントで検出される問題のほとんどはファイアウォールまたはプロキシ接続でその原因を究明できます。ファイアウォールまたはプロキシで必要な URL、IP アドレス、ポートが開かれていることを確認することで不要なトラブルシューティングを最小限に抑えることができます。Microsoft Teams で必要とされる URL と IP についての具体的な情報は、「[Office 365 の URL と IP アドレスの範囲](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&rs=en-US&ad=US#bkmk_teams)」のサポート記事をご覧ください。次のシナリオでは、ファイアウォールで特定の URL とポートを開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="b5b9f-p101">Most issues discovered with the Microsoft Teams client can be traced back to firewall or proxy connectivity. Verifying that the necessary URLs, IP addresses and ports are opened in your firewall or proxy will minimize unnecessary troubleshooting. For specific information on URLs and IPs required for Microsoft Teams, please reference the [Office 365 URLs and IP Address](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&rs=en-US&ad=US#bkmk_teams) support article. The following scenarios require specific URLs and ports to be opened in the firewall.</span></span>

-   <span data-ttu-id="b5b9f-108">認証</span><span class="sxs-lookup"><span data-stu-id="b5b9f-108">Authentication</span></span>

-   <span data-ttu-id="b5b9f-109">Microsoft Teams クライアントの接続性</span><span class="sxs-lookup"><span data-stu-id="b5b9f-109">Microsoft Teams Client Connectivity</span></span>

-   <span data-ttu-id="b5b9f-110">コラボレーション</span><span class="sxs-lookup"><span data-stu-id="b5b9f-110">Collaboration</span></span>

-   <span data-ttu-id="b5b9f-111">メディア</span><span class="sxs-lookup"><span data-stu-id="b5b9f-111">Media</span></span>

-   <span data-ttu-id="b5b9f-112">共有サービス</span><span class="sxs-lookup"><span data-stu-id="b5b9f-112">Shared Services</span></span>

-   <span data-ttu-id="b5b9f-113">サードパーティ統合</span><span class="sxs-lookup"><span data-stu-id="b5b9f-113">Third Party Integration</span></span>

-   <span data-ttu-id="b5b9f-114">Skype For Business の相互運用</span><span class="sxs-lookup"><span data-stu-id="b5b9f-114">Skype for Business Interoperability</span></span>

-   <span data-ttu-id="b5b9f-115">Skype for Business クライアントの相互運用</span><span class="sxs-lookup"><span data-stu-id="b5b9f-115">Skype for Business Client Interoperability</span></span>
