---
title: チームクライアントとの接続の問題のトラブルシューティング
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
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 116ce1afef08a6f1639ed011b799f9ca43ea57f5
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085233"
---
<a name="troubleshoot-connectivity-issues-with-the-microsoft-teams-client"></a><span data-ttu-id="5a726-103">Microsoft Teams クライアントとの接続に関するトラブルシューティングを行う</span><span class="sxs-lookup"><span data-stu-id="5a726-103">Troubleshoot connectivity issues with the Microsoft Teams client</span></span>
==============================================================

<span data-ttu-id="5a726-104">Microsoft Teams クライアントで発生する問題のほとんどは、ファイアウォールやプロキシ接続に原因があります。</span><span class="sxs-lookup"><span data-stu-id="5a726-104">Most issues discovered with the Microsoft Teams client can be traced back to firewall or proxy connectivity.</span></span> <span data-ttu-id="5a726-105">必要な URL、IP アドレス、ポートがファイアウォールやプロキシで開かれていることを確認することにより、不要なトラブルシューティングを最小限に抑えることができます。</span><span class="sxs-lookup"><span data-stu-id="5a726-105">Verifying that the necessary URLs, IP addresses and ports are opened in your firewall or proxy will minimize unnecessary troubleshooting.</span></span> <span data-ttu-id="5a726-106">Microsoft Teams に必要な Url と IPs の詳細については、「 [microsoft 365 および Office 365 の url と IP アドレス](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2)のサポート」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a726-106">For specific information on URLs and IPs required for Microsoft Teams, please see the [Microsoft 365 and Office 365 URLs and IP Address](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) support article.</span></span> <span data-ttu-id="5a726-107">次のシナリオでは、ファイアウォールで特定の URL とポートを開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a726-107">The following scenarios require specific URLs and ports to be opened in the firewall.</span></span>

-   <span data-ttu-id="5a726-108">認証</span><span class="sxs-lookup"><span data-stu-id="5a726-108">Authentication</span></span>

-   <span data-ttu-id="5a726-109">Microsoft Teams クライアントの接続性</span><span class="sxs-lookup"><span data-stu-id="5a726-109">Microsoft Teams Client Connectivity</span></span>

-   <span data-ttu-id="5a726-110">グループ作業</span><span class="sxs-lookup"><span data-stu-id="5a726-110">Collaboration</span></span>

-   <span data-ttu-id="5a726-111">メディア</span><span class="sxs-lookup"><span data-stu-id="5a726-111">Media</span></span>

-   <span data-ttu-id="5a726-112">[共有サービス]</span><span class="sxs-lookup"><span data-stu-id="5a726-112">Shared Services</span></span>

-   <span data-ttu-id="5a726-113">サードパーティ統合</span><span class="sxs-lookup"><span data-stu-id="5a726-113">Third Party Integration</span></span>

-   <span data-ttu-id="5a726-114">Skype For Business の相互運用</span><span class="sxs-lookup"><span data-stu-id="5a726-114">Skype for Business Interoperability</span></span>

-   <span data-ttu-id="5a726-115">Skype for Business クライアントの相互運用</span><span class="sxs-lookup"><span data-stu-id="5a726-115">Skype for Business Client Interoperability</span></span>


## <a name="related-topics"></a><span data-ttu-id="5a726-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="5a726-116">Related topics</span></span>

[<span data-ttu-id="5a726-117">チームのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="5a726-117">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)