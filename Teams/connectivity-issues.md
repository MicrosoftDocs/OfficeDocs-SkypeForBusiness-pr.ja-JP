---
title: Teams クライアントとの接続の問題のトラブルシューティング
ms.reviewer: ''
author: SerdarSoysal
ms.author: serdars
manager: serdars
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
ms.openlocfilehash: 59041734887a667eca325a3d2650425d6d336b78
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918543"
---
<a name="troubleshoot-connectivity-issues-with-the-microsoft-teams-client"></a><span data-ttu-id="57555-103">Microsoft Teams クライアントとの接続に関するトラブルシューティングを行う</span><span class="sxs-lookup"><span data-stu-id="57555-103">Troubleshoot connectivity issues with the Microsoft Teams client</span></span>
==============================================================

<span data-ttu-id="57555-104">Microsoft Teams クライアントで発生する問題のほとんどは、ファイアウォールやプロキシ接続に原因があります。</span><span class="sxs-lookup"><span data-stu-id="57555-104">Most issues discovered with the Microsoft Teams client can be traced back to firewall or proxy connectivity.</span></span> <span data-ttu-id="57555-105">必要な URL、IP アドレス、ポートがファイアウォールやプロキシで開かれていることを確認することにより、不要なトラブルシューティングを最小限に抑えることができます。</span><span class="sxs-lookup"><span data-stu-id="57555-105">Verifying that the necessary URLs, IP addresses and ports are opened in your firewall or proxy will minimize unnecessary troubleshooting.</span></span> <span data-ttu-id="57555-106">Microsoft Teams に必要な URL と IP の詳細については [、Microsoft 365 および Office 365 の URL](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) と IP アドレスのサポート記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="57555-106">For specific information on URLs and IPs required for Microsoft Teams, please see the [Microsoft 365 and Office 365 URLs and IP Address](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) support article.</span></span> <span data-ttu-id="57555-107">次のシナリオでは、ファイアウォールで特定の URL とポートを開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="57555-107">The following scenarios require specific URLs and ports to be opened in the firewall.</span></span>

- <span data-ttu-id="57555-108">認証</span><span class="sxs-lookup"><span data-stu-id="57555-108">Authentication</span></span>

- <span data-ttu-id="57555-109">Microsoft Teams クライアントの接続性</span><span class="sxs-lookup"><span data-stu-id="57555-109">Microsoft Teams Client Connectivity</span></span>

- <span data-ttu-id="57555-110">グループ作業</span><span class="sxs-lookup"><span data-stu-id="57555-110">Collaboration</span></span>

- <span data-ttu-id="57555-111">メディア</span><span class="sxs-lookup"><span data-stu-id="57555-111">Media</span></span>

- <span data-ttu-id="57555-112">[共有サービス]</span><span class="sxs-lookup"><span data-stu-id="57555-112">Shared Services</span></span>

- <span data-ttu-id="57555-113">サードパーティ統合</span><span class="sxs-lookup"><span data-stu-id="57555-113">Third Party Integration</span></span>

- <span data-ttu-id="57555-114">Skype For Business の相互運用</span><span class="sxs-lookup"><span data-stu-id="57555-114">Skype for Business Interoperability</span></span>

- <span data-ttu-id="57555-115">Skype for Business クライアントの相互運用</span><span class="sxs-lookup"><span data-stu-id="57555-115">Skype for Business Client Interoperability</span></span>

## <a name="when-teams-is-offline-or-in-low-bandwidth-conditions"></a><span data-ttu-id="57555-116">Teams がオフラインまたは低帯域幅の状態の場合</span><span class="sxs-lookup"><span data-stu-id="57555-116">When Teams is offline or in low bandwidth conditions</span></span>

<span data-ttu-id="57555-117">良いニュースは、オフラインの場合や低帯域幅の状況でも Teams が実行を続けているという状況です。</span><span class="sxs-lookup"><span data-stu-id="57555-117">The good news is that Teams keeps running even when you're offline or running in low bandwidth conditions.</span></span> <span data-ttu-id="57555-118">Teams では、既存のチャットの未送信メッセージはすべて (最大 24 時間) 保存され、オンラインに戻るとすぐに送信されます。</span><span class="sxs-lookup"><span data-stu-id="57555-118">Teams saves all your unsent messages for existing chats (for up to 24 hours) and sends them as soon as you're back online.</span></span> <span data-ttu-id="57555-119">オフライン状態が 24 時間を超える場合、Teams では未送信メッセージの再送信または削除を選択できます。</span><span class="sxs-lookup"><span data-stu-id="57555-119">If you're offline for longer than 24 hours, Teams lets you choose to resend or delete unsent messages.</span></span> <span data-ttu-id="57555-120">この機能を新しいチャットに追加する作業を行っています。利用可能な場合は、このドキュメントを更新します。</span><span class="sxs-lookup"><span data-stu-id="57555-120">We're working on adding this functionality to new chats and will update this documentation when that's available.</span></span>

## <a name="related-topics"></a><span data-ttu-id="57555-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="57555-121">Related topics</span></span>

[<span data-ttu-id="57555-122">Teams のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="57555-122">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
