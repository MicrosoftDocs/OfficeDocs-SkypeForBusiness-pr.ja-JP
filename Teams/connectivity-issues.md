---
title: "Microsoft Teams クライアントの接続性の問題をトラブルシューティングする"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "ファイアウォールまたはプロキシ接続が主な原因である Microsoft Teams クライアントの接続性の問題をトラブルシューティングする方法について説明します。"
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1e1c194978d0a265eb964e3bcf288275492a6c1d
ms.sourcegitcommit: 85105cb4e42ae8eb6e7e76eaf6d4dd5b9568cf41
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2018
---
<a name="troubleshoot-connectivity-issues-with-the-microsoft-teams-client"></a><span data-ttu-id="49f24-103">Microsoft Teams クライアントの接続性の問題をトラブルシューティングする</span><span class="sxs-lookup"><span data-stu-id="49f24-103">Troubleshoot connectivity issues with the Microsoft Teams client</span></span>
==============================================================

<span data-ttu-id="49f24-p101">Microsoft Teams クライアントで検出される問題のほとんどはファイアウォールまたはプロキシ接続でその原因を究明できます。ファイアウォールまたはプロキシで必要な URL、IP アドレス、ポートが開かれていることを確認することで不要なトラブルシューティングを最小限に抑えることができます。Microsoft Teams で必要とされる URL と IP についての具体的な情報は、「[Office 365 の URL と IP アドレスの範囲](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&rs=en-US&ad=US#bkmk_teams)」のサポート記事をご覧ください。次のシナリオでは、ファイアウォールで特定の URL とポートを開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="49f24-p101">Most issues discovered with the Microsoft Teams client can be traced back to firewall or proxy connectivity. Verifying that the necessary URLs, IP addresses and ports are opened in your firewall or proxy will minimize unnecessary troubleshooting. For specific information on URLs and IPs required for Microsoft Teams, please reference the [Office 365 URLs and IP Address](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&rs=en-US&ad=US#bkmk_teams) support article. The following scenarios require specific URLs and ports to be opened in the firewall.</span></span>

-   <span data-ttu-id="49f24-108">認証</span><span class="sxs-lookup"><span data-stu-id="49f24-108">Authentication</span></span>

-   <span data-ttu-id="49f24-109">Microsoft Teams クライアントの接続性</span><span class="sxs-lookup"><span data-stu-id="49f24-109">Microsoft Teams Client Connectivity</span></span>

-   <span data-ttu-id="49f24-110">コラボレーション</span><span class="sxs-lookup"><span data-stu-id="49f24-110">Collaboration</span></span>

-   <span data-ttu-id="49f24-111">メディア</span><span class="sxs-lookup"><span data-stu-id="49f24-111">Media</span></span>

-   <span data-ttu-id="49f24-112">共有サービス</span><span class="sxs-lookup"><span data-stu-id="49f24-112">Shared Services</span></span>

-   <span data-ttu-id="49f24-113">サードパーティ統合</span><span class="sxs-lookup"><span data-stu-id="49f24-113">Third Party Integration</span></span>

-   <span data-ttu-id="49f24-114">Skype For Business の相互運用</span><span class="sxs-lookup"><span data-stu-id="49f24-114">Skype for Business Interoperability</span></span>

-   <span data-ttu-id="49f24-115">Skype for Business クライアントの相互運用</span><span class="sxs-lookup"><span data-stu-id="49f24-115">Skype for Business Client Interoperability</span></span>
