---
title: Microsoft Teams クライアントの接続性の問題をトラブルシューティングする
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
description: ファイアウォールまたはプロキシ接続が主な原因である Microsoft Teams クライアントの接続性の問題をトラブルシューティングする方法について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7779e46fc0a1c8a282c5cde38ecac6389824a268
ms.sourcegitcommit: 5695ce88d4a6a8fb9594df8dd1c207e45be067be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "37516462"
---
<a name="troubleshoot-connectivity-issues-with-the-microsoft-teams-client"></a><span data-ttu-id="eed7f-103">Microsoft Teams クライアントの接続性の問題をトラブルシューティングする</span><span class="sxs-lookup"><span data-stu-id="eed7f-103">Troubleshoot connectivity issues with the Microsoft Teams client</span></span>
==============================================================

<span data-ttu-id="eed7f-104">Microsoft Teams クライアントで検出されたほとんどの問題は、ファイアウォールまたはプロキシ接続で追跡できます。</span><span class="sxs-lookup"><span data-stu-id="eed7f-104">Most issues discovered with the Microsoft Teams client can be traced back to firewall or proxy connectivity.</span></span> <span data-ttu-id="eed7f-105">必要な Url、IP アドレス、ポートがファイアウォールまたはプロキシで開かれていることを確認することで、不要なトラブルシューティングを最小限に抑えることができます。</span><span class="sxs-lookup"><span data-stu-id="eed7f-105">Verifying that the necessary URLs, IP addresses and ports are opened in your firewall or proxy will minimize unnecessary troubleshooting.</span></span> <span data-ttu-id="eed7f-106">Microsoft Teams に必要な Url と IPs の詳細については、「 [Office 365 の url と Ip アドレス](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2)のサポート」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eed7f-106">For specific information on URLs and IPs required for Microsoft Teams, please see the [Office 365 URLs and IP Address](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) support article.</span></span> <span data-ttu-id="eed7f-107">次のシナリオでは、特定の Url とポートをファイアウォールで開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="eed7f-107">The following scenarios require specific URLs and ports to be opened in the firewall.</span></span>

-   <span data-ttu-id="eed7f-108">認証</span><span class="sxs-lookup"><span data-stu-id="eed7f-108">Authentication</span></span>

-   <span data-ttu-id="eed7f-109">Microsoft Teams クライアントの接続性</span><span class="sxs-lookup"><span data-stu-id="eed7f-109">Microsoft Teams Client Connectivity</span></span>

-   <span data-ttu-id="eed7f-110">コラボレーション</span><span class="sxs-lookup"><span data-stu-id="eed7f-110">Collaboration</span></span>

-   <span data-ttu-id="eed7f-111">メディア</span><span class="sxs-lookup"><span data-stu-id="eed7f-111">Media</span></span>

-   <span data-ttu-id="eed7f-112">共有サービス</span><span class="sxs-lookup"><span data-stu-id="eed7f-112">Shared Services</span></span>

-   <span data-ttu-id="eed7f-113">サードパーティ統合</span><span class="sxs-lookup"><span data-stu-id="eed7f-113">Third Party Integration</span></span>

-   <span data-ttu-id="eed7f-114">Skype For Business の相互運用</span><span class="sxs-lookup"><span data-stu-id="eed7f-114">Skype for Business Interoperability</span></span>

-   <span data-ttu-id="eed7f-115">Skype for Business クライアントの相互運用</span><span class="sxs-lookup"><span data-stu-id="eed7f-115">Skype for Business Client Interoperability</span></span>
