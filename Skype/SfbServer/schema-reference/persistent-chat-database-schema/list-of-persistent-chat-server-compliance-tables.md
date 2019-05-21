---
title: Skype for Business Server の常設チャットサーバーのコンプライアンステーブルの一覧
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8563446e-90cc-47cc-8a8e-4883decfe195
description: 常設チャットのコンプライアンスデータベーススキーマは、次の表で構成されています。
ms.openlocfilehash: 92c87ee2783eb8ec064e017b5c3c5b0f6cb893a5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295658"
---
# <a name="list-of-persistent-chat-server-compliance-tables-in-skype-for-business-server"></a><span data-ttu-id="e5214-103">Skype for Business Server の常設チャットサーバーのコンプライアンステーブルの一覧</span><span class="sxs-lookup"><span data-stu-id="e5214-103">List of Persistent Chat Server compliance tables in Skype for Business Server</span></span>
 
<span data-ttu-id="e5214-104">常設チャットのコンプライアンスデータベーススキーマは、次の表で構成されています。</span><span class="sxs-lookup"><span data-stu-id="e5214-104">The Persistent Chat compliance database schema consists of the following tables.</span></span>
  
## <a name="list-of-persistent-chat-server-compliance-tables"></a><span data-ttu-id="e5214-105">常設チャットサーバーのコンプライアンステーブルの一覧</span><span class="sxs-lookup"><span data-stu-id="e5214-105">List of Persistent Chat Server Compliance Tables</span></span>

|<span data-ttu-id="e5214-106">**テーブル**</span><span class="sxs-lookup"><span data-stu-id="e5214-106">**Table**</span></span>|<span data-ttu-id="e5214-107">**説明**</span><span class="sxs-lookup"><span data-stu-id="e5214-107">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="e5214-108">tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="e5214-108">tblComplianceData</span></span>](tblcompliancedata.md) <br/> |<span data-ttu-id="e5214-109">構成済みのアダプターによってまだ処理されていないコンプライアンスイベントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e5214-109">Contains the compliance events that have not yet been processed by the configured adapter.</span></span>  <br/> <span data-ttu-id="e5214-110">この表には、チャットメッセージやファイルのダウンロードなどの常設チャット関連イベントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e5214-110">This table includes Persistent Chat-related events, such as chat messages and file downloads.</span></span> <span data-ttu-id="e5214-111">(参加者のイベントは、tblComplianceParticipant テーブルによって追跡されます)。</span><span class="sxs-lookup"><span data-stu-id="e5214-111">(Participant events are tracked by the tblComplianceParticipant table.)</span></span>  <br/> <span data-ttu-id="e5214-112">(この表のイベントを処理したサーバーは、tblComplianceFanout テーブルに一覧表示されます)。</span><span class="sxs-lookup"><span data-stu-id="e5214-112">(The servers that processed the events in this table are listed in the tblComplianceFanout table.)</span></span>  <br/> |
|[<span data-ttu-id="e5214-113">tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="e5214-113">tblComplianceFanout</span></span>](tblcompliancefanout.md) <br/> |<span data-ttu-id="e5214-114">コンプライアンスイベントを処理したサーバーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e5214-114">Contains the servers that processed a compliance event.</span></span> <span data-ttu-id="e5214-115">この表は、tblComplianceData テーブルと密接に結び付いています。</span><span class="sxs-lookup"><span data-stu-id="e5214-115">This table is tightly coupled with the tblComplianceData table.</span></span>  <br/> |
|[<span data-ttu-id="e5214-116">tblComplianceParticipant</span><span class="sxs-lookup"><span data-stu-id="e5214-116">tblComplianceParticipant</span></span>](tblcomplianceparticipant.md) <br/> |<span data-ttu-id="e5214-117">チャットサービスとサーバーごとに現在の参加者が含まれます。</span><span class="sxs-lookup"><span data-stu-id="e5214-117">Contains current participants per chat service and per server.</span></span> <span data-ttu-id="e5214-118">これは、常設チャットサービスから受信した参加イベントとパートコンプライアンスイベントに基づいて維持されます。</span><span class="sxs-lookup"><span data-stu-id="e5214-118">It is maintained based on join and part compliance events received from the Persistent Chat service.</span></span>  <br/> |
|[<span data-ttu-id="e5214-119">tblComplianceState</span><span class="sxs-lookup"><span data-stu-id="e5214-119">tblComplianceState</span></span>](tblcompliancestate.md) <br/> |<span data-ttu-id="e5214-120">プール全体のコンプライアンスの状態に関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e5214-120">Contains pool-wide compliance state information.</span></span>  <br/> |
   

