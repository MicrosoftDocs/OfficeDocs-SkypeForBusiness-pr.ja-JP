---
title: Office 365 の URL と IP アドレスの範囲
ms.reviewer: ''
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/21/2018
ms.topic: article
ms.service: msteams
description: Office 365 URL と IP アドレスの範囲を正しく構成する方法と、Microsoft Teams サービスとの接続で利用可能な転送プロキシのバイパス方法と、ネットワークとセキュリティ ポリシーの要件について説明します。
localization_priority: Normal
search.appverid: MET150
f1keywords: ms.teamsadmincenter.meetingsettings.network.ports
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e375452e236e38e036a5fe2413ba0848845587ab
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30885815"
---
<a name="office-365-urls-and-ip-address-ranges"></a><span data-ttu-id="9d7d5-103">Office 365 の URL と IP アドレスの範囲</span><span class="sxs-lookup"><span data-stu-id="9d7d5-103">Office 365 URLs and IP address ranges</span></span>
=====================================

<span data-ttu-id="9d7d5-104">Teams のために正しく構成されている必要がある URL、IP アドレス、ポート、およびプロトコルの詳細な最新のリストについては、「[Office 365 URL および IP アドレス範囲](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9d7d5-104">Go to [Office 365 URLs and IP address ranges](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) for a detailed and up-to-date list of the URLs, IP addresses, ports, and protocols that must be correctly configured for Teams.</span></span> <span data-ttu-id="9d7d5-105">マイクロソフトは、必要なポート、URL、IP アドレスが時間の経過とともに変更する可能性があることを踏まえて、継続して Office 365 サービスを改善し、新機能を追加します。</span><span class="sxs-lookup"><span data-stu-id="9d7d5-105">Microsoft is continuously improving the Office 365 service and adding new functionality, which means the required ports, URLs, and IP addresses may change over time.</span></span> <span data-ttu-id="9d7d5-106">お客様は、この情報が更新または変更されたときに通知を受け取れるように、[RSS で購読](https://go.microsoft.com/fwlink/p/?linkid=236301)することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9d7d5-106">We recommend that you [subscribe via RSS](https://go.microsoft.com/fwlink/p/?linkid=236301) to receive notifications when this information is updated or changed.</span></span>

<span data-ttu-id="9d7d5-107">Teams は、Skype および Skype for Business でも使用されている次世代のクラウドベース インフラストラクチャに基づいて構築された通話および会議のエクスペリエンスも提供しています。</span><span class="sxs-lookup"><span data-stu-id="9d7d5-107">The Teams calling and meetings experience is built on the next generation cloud-based infrastructure that is also used by Skype and Skype for Business.</span></span> <span data-ttu-id="9d7d5-108">これらのテクノロジへの投資には、メディアの処理と通知、H.264 ビデオ コーデック、絹および著作オーディオ コーデック、ネットワークの復元機能、遠隔測定、および品質診断の Azure ベースのクラウド サービスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="9d7d5-108">These technology investments include Azure-based cloud services for media processing and signaling, H.264 video codec, SILK and Opus audio codec, network resiliency, telemetry, and quality diagnostics.</span></span> <span data-ttu-id="9d7d5-109">したがって、Skype および Skype for Business の両方に関連付けられる可能性がある必要な URL と IP があります。</span><span class="sxs-lookup"><span data-stu-id="9d7d5-109">As such, there are URLs and IPs that are required that may be associated with both Skype and Skype for Business.</span></span>

<span data-ttu-id="9d7d5-110">すべての Office 365 ワークロードで、推奨される Teams サービスへの接続方法は、可能な場合にフォワード プロキシをバイパスすることです。</span><span class="sxs-lookup"><span data-stu-id="9d7d5-110">For all Office 365 workloads, the recommended connection method to Teams services is bypassing the forward proxy where possible.</span></span> <span data-ttu-id="9d7d5-111">プロキシ サーバーがクライアントと Office 365 データ センターとの間に位置している場合、メディアは UDP ではなく TCP 上を強制的に渡るようになり、メディアの品質に影響する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9d7d5-111">When a proxy server sits between a client and the Office 365 data centers, media might be forced over TCP instead of UDP, which would impact media quality.</span></span> <span data-ttu-id="9d7d5-112">[Office 365 エンドポイントの管理](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)から、トラフィック バイパスを構成するために使用できるサンプルのプロキシ PAC ファイルをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="9d7d5-112">Download sample proxy PAC files that can be used to configure traffic bypass from [Managing Office 365 endpoints](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a).</span></span>

<span data-ttu-id="9d7d5-113">ネットワー キングとセキュリティ ポリシーには、Office 365 のトラフィックをプロキシ サーバー経由で配信が必要とする場合に、チームを (レビュー[チームやビジネス オンラインの Skype のプロキシ サーバー](proxy-servers-for-skype-for-business-online.md)を運用環境に展開する前に、上記の条件が既に満たされていることを確認します。参考)。</span><span class="sxs-lookup"><span data-stu-id="9d7d5-113">If your networking and security policies require Office 365 traffic to flow through a proxy server, make sure that the above requirements are already met before deploying Teams into production (review [Proxy Servers for Teams or Skype for Business Online](proxy-servers-for-skype-for-business-online.md) for guidance).</span></span>
