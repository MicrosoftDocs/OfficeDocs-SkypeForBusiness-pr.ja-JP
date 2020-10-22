---
title: Microsoft 365 および Office 365 の Url と IP アドレスの範囲
ms.reviewer: ''
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 08/21/2018
ms.topic: article
audience: admin
ms.service: msteams
description: Microsoft Teams サービスとの接続に可能な場合、Microsoft 365 または Office 365 Url と IP アドレス範囲を適切に構成し、転送プロキシをバイパスする方法について説明します。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingsettings.network.ports
- seo-marvel-mar2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1ad3ffdfd47b67ce21fb7f47a911afa67159f3e7
ms.sourcegitcommit: 3a577c07b4f399c81d8650a2bba8cfc00b695b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/21/2020
ms.locfileid: "48650820"
---
<a name="microsoft-365-and-office-365-urls-and-ip-address-ranges"></a><span data-ttu-id="2a077-103">Microsoft 365 および Office 365 の Url と IP アドレスの範囲</span><span class="sxs-lookup"><span data-stu-id="2a077-103">Microsoft 365 and Office 365 URLs and IP address ranges</span></span>
=======================================================

<span data-ttu-id="2a077-104">Office の Url、IP アドレス、ポート、プロトコルの詳細と最新の一覧を表示するには、 [Microsoft 365 および Office 365 の url と ip アドレスの範囲](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2a077-104">Go to [Microsoft 365 and Office 365 URLs and IP address ranges](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) for a detailed and up-to-date list of the URLs, IP addresses, ports, and protocols that must be correctly configured for Teams.</span></span> <span data-ttu-id="2a077-105">Microsoft は、必要なポート、URL、IP アドレスが時間の経過とともに変更する可能性があることを踏まえて、継続して Microsoft 365 サービスおよび Office 365 サービスを改善し、新機能を追加します。</span><span class="sxs-lookup"><span data-stu-id="2a077-105">Microsoft is continuously improving the Microsoft 365 and Office 365 services and adding new functionality, which means the required ports, URLs, and IP addresses may change over time.</span></span> <span data-ttu-id="2a077-106">お客様は、この情報が更新または変更されたときに通知を受け取れるように、[RSS で購読](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2a077-106">We recommend that you [subscribe via RSS](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) to receive notifications when this information is updated or changed.</span></span>

<span data-ttu-id="2a077-107">Teams は、Skype および Skype for Business でも使用されている次世代のクラウドベース インフラストラクチャに基づいて構築された通話および会議のエクスペリエンスも提供しています。</span><span class="sxs-lookup"><span data-stu-id="2a077-107">The Teams calling and meetings experience is built on the next generation cloud-based infrastructure that is also used by Skype and Skype for Business.</span></span> <span data-ttu-id="2a077-108">これらの技術投資には、Azure ベースのクラウド サービスを利用したメディア処理とシグナリング、H.264 ビデオ コーデック、SILK および Opus オーディオ コーデック、ネットワークの回復力、テレメトリ、および品質診断が含まれます。</span><span class="sxs-lookup"><span data-stu-id="2a077-108">These technology investments include Azure-based cloud services for media processing and signaling, H.264 video codec, SILK and Opus audio codec, network resiliency, telemetry, and quality diagnostics.</span></span> <span data-ttu-id="2a077-109">したがって、Skype および Skype for Business の両方に関連付けられる可能性がある必要な URL と IP があります。</span><span class="sxs-lookup"><span data-stu-id="2a077-109">As such, there are URLs and IPs that are required that may be associated with both Skype and Skype for Business.</span></span>

<span data-ttu-id="2a077-110">Microsoft 365 および Office 365 のすべてのワークロードについては、可能であれば、Teams サービスへの推奨される接続方法をバイパスすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2a077-110">For all Microsoft 365 and Office 365 workloads, the recommended connection method to Teams services is bypassing the forward proxy where possible.</span></span> <span data-ttu-id="2a077-111">プロキシ サーバーがクライアントと Office 365 データ センターとの間に位置している場合、メディアは UDP ではなく TCP 上を強制的に渡るようになり、メディアの品質に影響する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2a077-111">When a proxy server sits between a client and the Office 365 data centers, media might be forced over TCP instead of UDP, which would impact media quality.</span></span> <span data-ttu-id="2a077-112">[Microsoft 365 および Office 365 エンドポイントの管理](https://docs.microsoft.com/office365/enterprise/managing-office-365-endpoints)からのトラフィックのバイパスを構成するために使用できるサンプルのプロキシ PAC ファイルをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="2a077-112">Download sample proxy PAC files that can be used to configure traffic bypass from [Managing Microsoft 365 and Office 365 endpoints](https://docs.microsoft.com/office365/enterprise/managing-office-365-endpoints).</span></span>

<span data-ttu-id="2a077-113">ネットワークとセキュリティポリシーで、Microsoft 365 または Office 365 のトラフィックをプロキシサーバー経由で送信する必要がある場合は、前述の要件を既に満たしていることを確認してから、チームを運用環境に展開してください。</span><span class="sxs-lookup"><span data-stu-id="2a077-113">If your networking and security policies require Microsoft 365 or Office 365 traffic to flow through a proxy server, make sure that the above requirements are already met before deploying Teams into production.</span></span> <span data-ttu-id="2a077-114">詳細については、「 [Teams または Skype For Business Online のプロキシサーバー](proxy-servers-for-skype-for-business-online.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2a077-114">For more information, read [Proxy Servers for Teams or Skype for Business Online](proxy-servers-for-skype-for-business-online.md).</span></span>
