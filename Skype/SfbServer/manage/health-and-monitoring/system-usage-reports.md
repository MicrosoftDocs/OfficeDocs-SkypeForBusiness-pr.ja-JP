---
title: ビジネス サーバーの Skype でのシステム使用状況レポート
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 187d316d-2456-417e-b636-05527a18ef06
description: '概要: は、ビジネス サーバー、Skype のシステム使用状況レポートについて説明します。'
ms.openlocfilehash: 5e3bcca092eb1ab8e03a837455924320e3af5e9b
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32197507"
---
# <a name="system-usage-reports-in-skype-for-business-server"></a><span data-ttu-id="fc0c5-103">ビジネス サーバーの Skype でのシステム使用状況レポート</span><span class="sxs-lookup"><span data-stu-id="fc0c5-103">System usage reports in Skype for Business Server</span></span>
 
<span data-ttu-id="fc0c5-104">**の概要:** ビジネス サーバーは、Skype のシステム使用状況レポートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="fc0c5-104">**Summary:** Learn about the System Usage Reports in Skype for Business Server.</span></span>
  
<span data-ttu-id="fc0c5-105">システムの利用状況レポートは、通話の詳細記録 (CDR) データのビジネス サーバーは、Skype で収集されたに基づいてシステムの使用状況に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="fc0c5-105">The System Usage Reports provide system usage information based on call detail recording (CDR) data collected by the Skype for Business Server.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="fc0c5-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="fc0c5-106">In this section</span></span>

- [<span data-ttu-id="fc0c5-107">ビジネス サーバーの Skype のユーザー登録レポート</span><span class="sxs-lookup"><span data-stu-id="fc0c5-107">User Registration Report in Skype for Business Server</span></span>](user-registration-report.md)
    
    <span data-ttu-id="fc0c5-108">ビジネス サーバー配置ではユーザーのログオンなどのイベントの登録を基に、Skype へのユーザー接続の概要を提供します。</span><span class="sxs-lookup"><span data-stu-id="fc0c5-108">Provides a summary of user connectivity to the Skype for Business Server deployment based on registration events such as user logons.</span></span> <span data-ttu-id="fc0c5-109">レポートでは、内部および外部の両方のログオンを表示するのには、ビジネスのサーバーにログオンしたときに、サービスを実際に使用するユーザーの数で Skype にログオンします。 ユーザーの数を比較する方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="fc0c5-109">The report provides a way to view both internal and external logons, and to compare the number of users who logged on to Skype for Business Server with the number of users who actually used the service while they were logged on.</span></span>
    
- [<span data-ttu-id="fc0c5-110">ピア ツー ピア アクティビティの概要レポートに Skype ビジネス サーバー</span><span class="sxs-lookup"><span data-stu-id="fc0c5-110">Peer-to-Peer Activity Summary Report in Skype for Business Server</span></span>](peer-to-peer-activity-summary-report.md)
    
    <span data-ttu-id="fc0c5-p102">インスタント メッセージング (IM)、音声、ビデオ、ファイル送信、およびアプリケーション共有のピアツーピア セッションに関する概要が示されます。ピアツーピア セッションは、関係するユーザーが 2 人だけのセッションです。</span><span class="sxs-lookup"><span data-stu-id="fc0c5-p102">Provides a summary of peer-to-peer instant messaging (IM), audio, video, file transfer, and application sharing sessions. Peer-to-peer sessions are sessions involving just two users.</span></span>
    
- [<span data-ttu-id="fc0c5-113">ビジネス サーバーの Skype で会議の概要レポート</span><span class="sxs-lookup"><span data-stu-id="fc0c5-113">Conference Summary Report in Skype for Business Server</span></span>](conference-summary-report.md)
    
    <span data-ttu-id="fc0c5-114">すべての会議アクティビティに関する概要が示されます。</span><span class="sxs-lookup"><span data-stu-id="fc0c5-114">Provides a summary of all conference activities.</span></span> <span data-ttu-id="fc0c5-115">会議は 3 人以上のユーザーが関係するセッションです。</span><span class="sxs-lookup"><span data-stu-id="fc0c5-115">Conferences are sessions involving three or more people.</span></span>
    
- [<span data-ttu-id="fc0c5-116">PSTN 会議の概要レポートでは、Skype ビジネス サーバー</span><span class="sxs-lookup"><span data-stu-id="fc0c5-116">PSTN Conference Summary Report in Skype for Business Server</span></span>](pstn-conference-summary-report.md)
    
    <span data-ttu-id="fc0c5-117">すべての PSTN 会議の概要を提供します。</span><span class="sxs-lookup"><span data-stu-id="fc0c5-117">Provides a summary of all PSTN conferences.</span></span> <span data-ttu-id="fc0c5-118">これらは、少なくとも 1 人のユーザーがダイヤルイン会議と呼ばれることも、公衆交換電話網 (PSTN) を使用してダイヤルイン会議です。</span><span class="sxs-lookup"><span data-stu-id="fc0c5-118">These are conferences where at least one user dials in using the public switched telephone network (PSTN), which is also referred to as dial-in conferencing.</span></span>
    
- [<span data-ttu-id="fc0c5-119">Skype のビジネス サーバーの応答のグループの使用状況をレポート</span><span class="sxs-lookup"><span data-stu-id="fc0c5-119">Response Group Usage Report in Skype for Business Server</span></span>](response-group-usage-report.md)
    
    <span data-ttu-id="fc0c5-120">応答グループの使用の概要を提供します。</span><span class="sxs-lookup"><span data-stu-id="fc0c5-120">Provides a summary of Response Group usage.</span></span> <span data-ttu-id="fc0c5-121">応答グループ アプリケーションによりのヘルプなどのエンティティに自動的に工順電話をかけるデスクや顧客のサポート ラインです。</span><span class="sxs-lookup"><span data-stu-id="fc0c5-121">The Response Group application provides a way for you to automatically route phone calls to entities such as a help desk or customer support line.</span></span>
    
- [<span data-ttu-id="fc0c5-122">ビジネス サーバの Skype で IP 電話インベントリ レポート</span><span class="sxs-lookup"><span data-stu-id="fc0c5-122">IP Phone Inventory Report in Skype for Business Server</span></span>](ip-phone-inventory-report.md)
    
    <span data-ttu-id="fc0c5-123">組織で現在使用されている IP 電話に関する情報が示されます。</span><span class="sxs-lookup"><span data-stu-id="fc0c5-123">Provides information about the IP phones currently in use in the organization.</span></span> <span data-ttu-id="fc0c5-124">レポートは電話の登録とログオンに基づいています。</span><span class="sxs-lookup"><span data-stu-id="fc0c5-124">The report is based on phone registrations and logons.</span></span> <span data-ttu-id="fc0c5-125">完全な在庫とは考えないでください。</span><span class="sxs-lookup"><span data-stu-id="fc0c5-125">It should not be considered a complete inventory.</span></span> <span data-ttu-id="fc0c5-126">たとえば、少なくとも 1 回はログオンしたため、レポートにまだ含まれている電話が廃棄されている場合があります。</span><span class="sxs-lookup"><span data-stu-id="fc0c5-126">For example, you might have removed phones that are still listed in the report because they logged on at least once.</span></span> <span data-ttu-id="fc0c5-127">同様に、示していないことレポートにするだけで新しい電話にも、ユーザーがログオンしていない Skype をビジネス サーバーの新しい電話をまだするためです。</span><span class="sxs-lookup"><span data-stu-id="fc0c5-127">Likewise, you might also have new phones that do not show up in the report simply because users have not logged on to Skype for Business Server with their new phones yet.</span></span>
    
- [<span data-ttu-id="fc0c5-128">ビジネス サーバーの Skype での受付管理レポートを呼び出す</span><span class="sxs-lookup"><span data-stu-id="fc0c5-128">Call Admission Control Report in Skype for Business Server</span></span>](call-admission-control-report.md)
    
    <span data-ttu-id="fc0c5-p107">通話受付管理を使用するピアツーピア アクティビティおよび会議アクティビティの一覧が示されます。通話受付管理 (CAC) を利用すると、帯域幅の制約に基づいて、音声通話、ビデオ通話などのリアルタイム通信セッションを許可する必要があるかどうかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="fc0c5-p107">Provides a list of peer-to-peer and conference activities that use call admission control. Call admission control (CAC) is a way of determining whether you should allow real-time communications sessions, such as voice or video calls, based on bandwidth constraints.</span></span>
    

