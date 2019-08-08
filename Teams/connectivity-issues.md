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
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
description: ファイアウォールまたはプロキシ接続が主な原因である Microsoft Teams クライアントの接続性の問題をトラブルシューティングする方法について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 79718ebc58205cd63ab291f0985e4dd7e452be3e
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36236552"
---
<a name="troubleshoot-connectivity-issues-with-the-microsoft-teams-client"></a><span data-ttu-id="5e27c-103">Microsoft Teams クライアントの接続性の問題をトラブルシューティングする</span><span class="sxs-lookup"><span data-stu-id="5e27c-103">Troubleshoot connectivity issues with the Microsoft Teams client</span></span>
==============================================================

<span data-ttu-id="5e27c-104">Microsoft Teams クライアントで検出されたほとんどの問題は、ファイアウォールまたはプロキシ接続で追跡できます。</span><span class="sxs-lookup"><span data-stu-id="5e27c-104">Most issues discovered with the Microsoft Teams client can be traced back to firewall or proxy connectivity.</span></span> <span data-ttu-id="5e27c-105">必要な Url、IP アドレス、ポートがファイアウォールまたはプロキシで開かれていることを確認することで、不要なトラブルシューティングを最小限に抑えることができます。</span><span class="sxs-lookup"><span data-stu-id="5e27c-105">Verifying that the necessary URLs, IP addresses and ports are opened in your firewall or proxy will minimize unnecessary troubleshooting.</span></span> <span data-ttu-id="5e27c-106">Microsoft Teams に必要な Url と IPs の詳細については、「 [Office 365 の url と Ip アドレス](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2)のサポート」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e27c-106">For specific information on URLs and IPs required for Microsoft Teams, please see the [Office 365 URLs and IP Address](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) support article.</span></span> <span data-ttu-id="5e27c-107">次のシナリオでは、特定の Url とポートをファイアウォールで開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="5e27c-107">The following scenarios require specific URLs and ports to be opened in the firewall.</span></span>

-   <span data-ttu-id="5e27c-108">認証</span><span class="sxs-lookup"><span data-stu-id="5e27c-108">Authentication</span></span>

-   <span data-ttu-id="5e27c-109">Microsoft Teams クライアントの接続性</span><span class="sxs-lookup"><span data-stu-id="5e27c-109">Microsoft Teams Client Connectivity</span></span>

-   <span data-ttu-id="5e27c-110">コラボレーション</span><span class="sxs-lookup"><span data-stu-id="5e27c-110">Collaboration</span></span>

-   <span data-ttu-id="5e27c-111">メディア</span><span class="sxs-lookup"><span data-stu-id="5e27c-111">Media</span></span>

-   <span data-ttu-id="5e27c-112">共有サービス</span><span class="sxs-lookup"><span data-stu-id="5e27c-112">Shared Services</span></span>

-   <span data-ttu-id="5e27c-113">サードパーティ統合</span><span class="sxs-lookup"><span data-stu-id="5e27c-113">Third Party Integration</span></span>

-   <span data-ttu-id="5e27c-114">Skype For Business の相互運用</span><span class="sxs-lookup"><span data-stu-id="5e27c-114">Skype for Business Interoperability</span></span>

-   <span data-ttu-id="5e27c-115">Skype for Business クライアントの相互運用</span><span class="sxs-lookup"><span data-stu-id="5e27c-115">Skype for Business Client Interoperability</span></span>
