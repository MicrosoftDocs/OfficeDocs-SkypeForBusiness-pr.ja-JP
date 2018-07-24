---
title: Skype のビジネス サーバーの診断レポートを呼び出す
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8d362dd9-a119-4601-a3b4-3e7ed0aaa92e
description: '概要: は、Skype のビジネスのサーバーが使用する、マルチ ユーザーの呼び出しの診断レポートについて説明します。'
ms.openlocfilehash: 26350a48c5b7073af9af6fe5589d6a56a2b5b60e
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "21004490"
---
# <a name="call-diagnostic-reports-in-skype-for-business-server"></a><span data-ttu-id="f640a-103">Skype のビジネス サーバーの診断レポートを呼び出す</span><span class="sxs-lookup"><span data-stu-id="f640a-103">Call Diagnostic Reports in Skype for Business Server</span></span>
 
<span data-ttu-id="f640a-104">**の概要:** Skype のビジネスのサーバーが使用する、マルチ ユーザーの呼び出しの診断レポートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="f640a-104">**Summary:** Learn about the multi-user Call Diagnostic Reports used in Skype for Business Server.</span></span>
  
<span data-ttu-id="f640a-105">通話診断レポートは、エラーが発生したピアツーピア セッションと電話会議セッションに関する概要情報と診断データを提供します。</span><span class="sxs-lookup"><span data-stu-id="f640a-105">The Call Diagnostic Reports provide summary information and diagnostic data for failed peer-to-peer and conferencing sessions.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="f640a-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="f640a-106">In this section</span></span>

- <span data-ttu-id="f640a-107">[ビジネス サーバーの Skype での診断の概要レポートを呼び出す](summary-report.md)失敗したピア ツー ピア セッションや会議セッションの概要を記載します。</span><span class="sxs-lookup"><span data-stu-id="f640a-107">[Call Diagnostic Summary Report in Skype for Business Server](summary-report.md) Provides an overall summary of failed peer-to-peer sessions and conference sessions.</span></span> <span data-ttu-id="f640a-108">ピア ツー ピア セッションとは、2 つの関係者が関与するセッションです。</span><span class="sxs-lookup"><span data-stu-id="f640a-108">Peer-to-peer sessions are sessions that involve just two participants.</span></span> <span data-ttu-id="f640a-109">会議セッションには、3 つ以上の関係者が関与します。</span><span class="sxs-lookup"><span data-stu-id="f640a-109">Conferencing sessions involve three or more participants.</span></span>
    
- <span data-ttu-id="f640a-110">[ビジネス サーバーの Skype でのピア ツー ピア アクティビティ診断レポート](peer-to-peer-activity-diagnostic-report.md)失敗したピア ツー ピア セッションの全体の傾向のビューを提供します。</span><span class="sxs-lookup"><span data-stu-id="f640a-110">[Peer-to-Peer Activity Diagnostic Report in Skype for Business Server](peer-to-peer-activity-diagnostic-report.md) Provides an overall trend view of failed peer-to-peer sessions.</span></span> <span data-ttu-id="f640a-111">ピア ツー ピア セッションには、2 つの参加者が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f640a-111">A peer-to-peer session involves just two participants.</span></span>
    
- <span data-ttu-id="f640a-112">[ビジネス サーバーの Skype での会議診断レポート](conference-diagnostic-report.md)各会議のモーダルかどうかの障害が発生した会議セッションの全体の傾向の表示とトレンドのビューを提供します。</span><span class="sxs-lookup"><span data-stu-id="f640a-112">[Conference Diagnostic Report in Skype for Business Server](conference-diagnostic-report.md) Provides an overall trend view of failed conferencing sessions and trend views for each conference modality.</span></span> <span data-ttu-id="f640a-113">会議セッションには、少なくとも 3 人の参加者が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f640a-113">Conferencing sessions involve at least three participants.</span></span>
    
- <span data-ttu-id="f640a-114">[Skype ビジネス サーバーの最上位のエラー レポート](top-failures-report.md)時間の経過とともに、最も頻繁に障害が発生し、その傾向の一覧を提供します。</span><span class="sxs-lookup"><span data-stu-id="f640a-114">[Top Failures Report in Skype for Business Server](top-failures-report.md) Provides a list of the most frequent failures and their trends over time.</span></span>
    
- <span data-ttu-id="f640a-115">[ビジネス サーバーの Skype でのエラー分布レポート](failure-distribution-report.md)失敗したセッションの分析を提供します。</span><span class="sxs-lookup"><span data-stu-id="f640a-115">[Failure Distribution Report in Skype for Business Server](failure-distribution-report.md) Provides an analysis of failed sessions.</span></span>
    
- <span data-ttu-id="f640a-116">[Skype ビジネス サーバー用のエラー] ボックスの一覧レポート](failure-list-report.md)障害が発生した会議に関連する個々 の参加者についての詳細な情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="f640a-116">[Failure List Report in Skype for Business Server](failure-list-report.md) Provides detailed information about the individual participants involved in a failed conference.</span></span>
    
- <span data-ttu-id="f640a-117">[Skype ビジネス サーバーの診断レポート](diagnostic-report.md)失敗したセッションの診断およびトラブルシューティングの情報 (SIP 応答コード、診断ヘッダー Id など) を提供します。</span><span class="sxs-lookup"><span data-stu-id="f640a-117">[Diagnostic Report in Skype for Business Server](diagnostic-report.md) Provides diagnostic and troubleshooting information (including SIP response codes and diagnostic headers and IDs) for failed sessions.</span></span>
    

