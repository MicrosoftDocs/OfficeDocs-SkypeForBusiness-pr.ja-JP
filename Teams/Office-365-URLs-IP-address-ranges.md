---
title: "Office 365 の URL と IP アドレスの範囲 | Microsoft サポート"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Office 365 URL と IP アドレスの範囲を正しく構成する方法と、Microsoft Teams サービスとの接続で利用可能な転送プロキシのバイパス方法と、ネットワークとセキュリティ ポリシーの要件について説明します。"
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: a226a2d541119c61a3538c86f3502defb739147d
ms.sourcegitcommit: 2e557e90b4e30fe99ff9df3897b8e54f38ea2f2e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2017
---
<a name="office-365-urls-and-ip-address-ranges"></a><span data-ttu-id="f1c4f-103">Office 365 の URL と IP アドレスの範囲</span><span class="sxs-lookup"><span data-stu-id="f1c4f-103">Office 365 URLs and IP address ranges</span></span>
=====================================

<span data-ttu-id="f1c4f-p101">正しく構成する必要のある IP とポートの詳細かつ最新のリストについては、「[Office 365 の URL と IP アドレスの範囲](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&rs=en-US&ad=US)」をご覧ください。Microsoft は、Office 365 サービスの向上に継続的に取り組み、新しい機能を追加しています。そのため必須のポート、URL、IP アドレスが時間の経過とともに変更される場合があります。最新のポートやプロトコルに関するガイドについては、「[Office 365 の URL と IP アドレスの範囲](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2)」をご覧ください。[RSS 経由で購読](https://go.microsoft.com/fwlink/p/?linkid=236301)して、エンドポイントが更新または変更されたときに通知を受信できるようにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f1c4f-p101">Please review the following link for a detailed and up to date list of the exact IP’s and ports that must be correctly configured: [Office 365 URLs and IP address ranges](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&rs=en-US&ad=US). Microsoft is continuously improving the Office 365 service and adding new functionalities, therefore the required ports, URLs and IP addresses may change over time. Please refer to [Office 365 URLs and IP address ranges](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) guide for the latest versions of ports and protocols. It is also highly recommended to [subscribe via RSS](https://go.microsoft.com/fwlink/p/?linkid=236301) to receive notifications when endpoints are updated or changed.</span></span>

<span data-ttu-id="f1c4f-p102">既に説明したとおり、Microsoft Teams の通話と会議は次世代のクラウドベースインフラストラクチャに基づいて構築されています。このインフラストラクチャは Skype および Skype for Business でも採用されています。この技術的投資には、メディア処理および信号用のAzure ベースのクラウド サービス、H.264 ビデオ コーデック、SILK および Opus オーディオ コーデック、ネットワーク回復、テレメトリー、品質診断が含まれます。そのため、一部の必須 URL および IP は Skype と Skype for Business の両方に関連付けられている場合があります。</span><span class="sxs-lookup"><span data-stu-id="f1c4f-p102">As mentioned, Microsoft Teams calling and meetings experience is built on the next generation cloud based infrastructure that is also used by Skype and Skype for Business. These technology investments include Azure-based cloud services for media processing and signaling, H.264 video codec, SILK and Opus audio codec, network resiliency, telemetry and quality diagnostics. As such, there are URLs and IPs that are required that may be associated with both Skype and Skype for Business.</span></span>

<span data-ttu-id="f1c4f-p103">すべての Office 365 ワークロードについて、Microsoft Teams サービスへの推奨接続方法は、可能な場合に転送プロキシをバイパスする方法です。プロキシ サーバーがクライアントと Office 365 データセンター間に存在する場合は、UDP ではなく、メディアの品質が低下する TCP 上に強制される場合があります。トラフィック バイパスを構成するために使用できるサンプルのプロキシ PAC ファイルを「[Managing Office 365 endpoints (Office 365 エンドポイントの管理)](https://support.office.com/article/managing-Office-365-endpoints-99cab9d4-ef59-4207-9f2b-3728eb46bf9a)」ガイドからダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="f1c4f-p103">For all Office 365 workloads, the recommended connection method to Microsoft Teams services is bypassing the forward proxy where possible. When a proxy server sits between a client and the Office 365 datacenters, media might be forced over TCP instead of UDP, that would impact media quality. A sample proxy PAC files that can be used to configure traffic bypass can be downloaded from [Managing Office 365 endpoints](https://support.office.com/article/managing-Office-365-endpoints-99cab9d4-ef59-4207-9f2b-3728eb46bf9a) guide.</span></span>

<span data-ttu-id="f1c4f-114">ネットワークおよびセキュリティ ポリシーで、Office 365 トラフィックがプロキシ サーバーを経由することが求められている場合は、Microsoft Teams を実稼動に展開する前に上記の要件を満たしていることを確認してください (詳しくは、「[Skype for Business Online 向けのプロキシ サーバー](https://support.office.com/en-us/article/Proxy-Servers-for-Skype-for-Business-Online-7acaf2c2-35fa-490f-84cd-822e446e0fc7?ui=en-US&rs=en-US&ad=US)」をご覧ください)。</span><span class="sxs-lookup"><span data-stu-id="f1c4f-114">If your networking and security policies require Office 365 traffic to flow through a proxy server, then make sure that the above requirements are already met before deploying Microsoft Teams into production (review [Proxy Servers for Skype for Business Online](https://support.office.com/en-us/article/Proxy-Servers-for-Skype-for-Business-Online-7acaf2c2-35fa-490f-84cd-822e446e0fc7?ui=en-US&rs=en-US&ad=US) for guidance.)</span></span>
