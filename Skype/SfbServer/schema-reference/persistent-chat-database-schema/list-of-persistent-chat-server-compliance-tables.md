---
title: Skype for Business Server の常設チャット サーバー コンプライアンス テーブルの一覧
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8563446e-90cc-47cc-8a8e-4883decfe195
description: 常設チャット コンプライアンス データベース スキーマは、次の表で構成されます。
ms.openlocfilehash: 8fa9c47c2abd28922716cd42c5ff150ddd975393
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813057"
---
# <a name="list-of-persistent-chat-server-compliance-tables-in-skype-for-business-server"></a><span data-ttu-id="edd57-103">Skype for Business Server の常設チャット サーバー コンプライアンス テーブルの一覧</span><span class="sxs-lookup"><span data-stu-id="edd57-103">List of Persistent Chat Server compliance tables in Skype for Business Server</span></span>
 
<span data-ttu-id="edd57-104">常設チャット コンプライアンス データベース スキーマは、次の表で構成されます。</span><span class="sxs-lookup"><span data-stu-id="edd57-104">The Persistent Chat compliance database schema consists of the following tables.</span></span>
  
## <a name="list-of-persistent-chat-server-compliance-tables"></a><span data-ttu-id="edd57-105">常設チャット サーバーのコンプライアンス テーブルのリスト</span><span class="sxs-lookup"><span data-stu-id="edd57-105">List of Persistent Chat Server Compliance Tables</span></span>

|<span data-ttu-id="edd57-106">**Table**</span><span class="sxs-lookup"><span data-stu-id="edd57-106">**Table**</span></span>|<span data-ttu-id="edd57-107">**説明**</span><span class="sxs-lookup"><span data-stu-id="edd57-107">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="edd57-108">tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="edd57-108">tblComplianceData</span></span>](tblcompliancedata.md) <br/> |<span data-ttu-id="edd57-109">構成済みのアダプターによってまだ処理されていないコンプライアンス イベントが格納されます。</span><span class="sxs-lookup"><span data-stu-id="edd57-109">Contains the compliance events that have not yet been processed by the configured adapter.</span></span>  <br/> <span data-ttu-id="edd57-110">この表には、チャット メッセージやファイルのダウンロードなど、常設チャット関連のイベントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="edd57-110">This table includes Persistent Chat-related events, such as chat messages and file downloads.</span></span> <span data-ttu-id="edd57-111">(参加者イベントは tblComplianceParticipant テーブルによって追跡されます)。</span><span class="sxs-lookup"><span data-stu-id="edd57-111">(Participant events are tracked by the tblComplianceParticipant table.)</span></span>  <br/> <span data-ttu-id="edd57-112">(このテーブルのイベントを処理したサーバーは、tblComplianceFanout テーブルに含まれます)</span><span class="sxs-lookup"><span data-stu-id="edd57-112">(The servers that processed the events in this table are listed in the tblComplianceFanout table.)</span></span>  <br/> |
|[<span data-ttu-id="edd57-113">tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="edd57-113">tblComplianceFanout</span></span>](tblcompliancefanout.md) <br/> |<span data-ttu-id="edd57-114">コンプライアンス イベントを処理したサーバーが格納されます。</span><span class="sxs-lookup"><span data-stu-id="edd57-114">Contains the servers that processed a compliance event.</span></span> <span data-ttu-id="edd57-115">このテーブルは tblComplianceData テーブルと緊密に結び付けられています。</span><span class="sxs-lookup"><span data-stu-id="edd57-115">This table is tightly coupled with the tblComplianceData table.</span></span>  <br/> |
|[<span data-ttu-id="edd57-116">tblComplianceParticipant</span><span class="sxs-lookup"><span data-stu-id="edd57-116">tblComplianceParticipant</span></span>](tblcomplianceparticipant.md) <br/> |<span data-ttu-id="edd57-117">チャット サービス別およびサーバー別に現在の参加者が格納されます。</span><span class="sxs-lookup"><span data-stu-id="edd57-117">Contains current participants per chat service and per server.</span></span> <span data-ttu-id="edd57-118">常設チャット サービスから受信した参加イベントとパート コンプライアンス イベントに基づいて管理されます。</span><span class="sxs-lookup"><span data-stu-id="edd57-118">It is maintained based on join and part compliance events received from the Persistent Chat service.</span></span>  <br/> |
|[<span data-ttu-id="edd57-119">tblComplianceState</span><span class="sxs-lookup"><span data-stu-id="edd57-119">tblComplianceState</span></span>](tblcompliancestate.md) <br/> |<span data-ttu-id="edd57-120">プール全体のコンプライアンス状態情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="edd57-120">Contains pool-wide compliance state information.</span></span>  <br/> |
   

