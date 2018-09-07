---
title: Office 365 の URL と IP アドレスの範囲
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/21/2018
ms.topic: article
ms.service: msteams
description: Office 365 URL と IP アドレスの範囲を正しく構成する方法と、Microsoft Teams サービスとの接続で利用可能な転送プロキシのバイパス方法と、ネットワークとセキュリティ ポリシーの要件について説明します。
localization_priority: Priority
search.appverid: MET150
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: a21130d3e1c2e81203bb409fc2a53c77645bf0ba
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23851924"
---
<a name="office-365-urls-and-ip-address-ranges"></a><span data-ttu-id="ba312-103">Office 365 の URL と IP アドレスの範囲</span><span class="sxs-lookup"><span data-stu-id="ba312-103">Office 365 URLs and IP address ranges</span></span>
=====================================

<span data-ttu-id="ba312-104">Url、IP アドレス、ポート、およびチームを正しく構成する必要があるプロトコルの詳細で最新の状態の一覧については、 [Office 365 の Url と IP アドレスの範囲](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)を移動します。</span><span class="sxs-lookup"><span data-stu-id="ba312-104">Go to [Office 365 URLs and IP address ranges](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges) for a detailed and up-to-date list of the URLs, IP addresses, ports, and protocols that must be correctly configured for Teams.</span></span> <span data-ttu-id="ba312-105">マイクロソフトが継続的に Office 365 のサービスを向上させることし、新しい機能を追加するには、必要なポート、Url、つまり時間の経過と共に IP アドレスを変更することがあります。</span><span class="sxs-lookup"><span data-stu-id="ba312-105">Microsoft is continuously improving the Office 365 service and adding new functionality, which means the required ports, URLs, and IP addresses may change over time.</span></span> <span data-ttu-id="ba312-106">そのを[RSS で購読](https://go.microsoft.com/fwlink/p/?linkid=236301)することをお勧めします。 この情報を更新または変更されたときに通知を受信します。</span><span class="sxs-lookup"><span data-stu-id="ba312-106">We recommend that you [subscribe via RSS](https://go.microsoft.com/fwlink/p/?linkid=236301) to receive notifications when this information is updated or changed.</span></span>

<span data-ttu-id="ba312-107">通話や会議の経験は、次世代クラウド ・ ベースのインフラストラクチャがまた使用する Skype、Skype ビジネスの上に構築されたチームです。</span><span class="sxs-lookup"><span data-stu-id="ba312-107">The Teams calling and meetings experience is built on the next generation cloud-based infrastructure that is also used by Skype and Skype for Business.</span></span> <span data-ttu-id="ba312-108">これらの技術投資には、Azure ベースのクラウド サービスを利用したメディア処理とシグナリング、H.264 ビデオ コーデック、SILK および Opus オーディオ コーデック、ネットワークの回復力、テレメトリ、および品質診断が含まれます。</span><span class="sxs-lookup"><span data-stu-id="ba312-108">These technology investments include Azure-based cloud services for media processing and signaling, H.264 video codec, SILK and Opus audio codec, network resiliency, telemetry, and quality diagnostics.</span></span> <span data-ttu-id="ba312-109">ように、Url が存在し、必要な可能性のあるは ip アドレス、Skype と Skype のビジネスの両方に関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="ba312-109">As such, there are URLs and IPs that are required that may be associated with both Skype and Skype for Business.</span></span>

<span data-ttu-id="ba312-110">、Office 365 のすべてのワークロードの可能な場合はチームのサービスに推奨される接続方法がフォワード プロキシをバイパスするが。</span><span class="sxs-lookup"><span data-stu-id="ba312-110">For all Office 365 workloads, the recommended connection method to Teams services is bypassing the forward proxy where possible.</span></span> <span data-ttu-id="ba312-111">プロキシ サーバーは、クライアントと Office 365 のデータ ・ センターとの間に配置、ときに UDP では、メディアの品質に影響するのではなく TCP 経由でメディアが強制される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ba312-111">When a proxy server sits between a client and the Office 365 data centers, media might be forced over TCP instead of UDP, which would impact media quality.</span></span> <span data-ttu-id="ba312-112">[Office 365 の管理のエンドポイント](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)からのトラフィックのバイパスの構成に使用できるサンプル プロキシの PAC ファイルをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="ba312-112">Download sample proxy PAC files that can be used to configure traffic bypass from [Managing Office 365 endpoints](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a).</span></span>

<span data-ttu-id="ba312-113">ネットワー キングとセキュリティ ポリシーには、Office 365 のトラフィックをプロキシ サーバー経由で配信が必要とする場合は、チームを運用環境に展開する前に、上記の条件が既に満たされていることを確認してください (の[オンライン ビジネスの Skype のプロキシ サーバー](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/proxy-servers-for-skype-for-business-online)を確認します。ガイダンス)。</span><span class="sxs-lookup"><span data-stu-id="ba312-113">If your networking and security policies require Office 365 traffic to flow through a proxy server, make sure that the above requirements are already met before deploying Teams into production (review [Proxy Servers for Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/proxy-servers-for-skype-for-business-online) for guidance).</span></span>
