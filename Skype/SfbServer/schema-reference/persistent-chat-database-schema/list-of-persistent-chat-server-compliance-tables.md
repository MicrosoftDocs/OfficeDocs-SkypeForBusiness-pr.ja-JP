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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8563446e-90cc-47cc-8a8e-4883decfe195
description: 常設チャットのコンプライアンスデータベーススキーマは、次の表で構成されています。
ms.openlocfilehash: a992f00718d831af1b5a30f08baaf779ea3ee2c1
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814765"
---
# <a name="list-of-persistent-chat-server-compliance-tables-in-skype-for-business-server"></a><span data-ttu-id="cf83d-103">Skype for Business Server の常設チャットサーバーのコンプライアンステーブルの一覧</span><span class="sxs-lookup"><span data-stu-id="cf83d-103">List of Persistent Chat Server compliance tables in Skype for Business Server</span></span>
 
<span data-ttu-id="cf83d-104">常設チャットのコンプライアンスデータベーススキーマは、次の表で構成されています。</span><span class="sxs-lookup"><span data-stu-id="cf83d-104">The Persistent Chat compliance database schema consists of the following tables.</span></span>
  
## <a name="list-of-persistent-chat-server-compliance-tables"></a><span data-ttu-id="cf83d-105">常設チャットサーバーのコンプライアンステーブルの一覧</span><span class="sxs-lookup"><span data-stu-id="cf83d-105">List of Persistent Chat Server Compliance Tables</span></span>

|<span data-ttu-id="cf83d-106">**テーブル**</span><span class="sxs-lookup"><span data-stu-id="cf83d-106">**Table**</span></span>|<span data-ttu-id="cf83d-107">**説明**</span><span class="sxs-lookup"><span data-stu-id="cf83d-107">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="cf83d-108">tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="cf83d-108">tblComplianceData</span></span>](tblcompliancedata.md) <br/> |<span data-ttu-id="cf83d-109">構成済みのアダプターによってまだ処理されていないコンプライアンスイベントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="cf83d-109">Contains the compliance events that have not yet been processed by the configured adapter.</span></span>  <br/> <span data-ttu-id="cf83d-110">この表には、チャットメッセージやファイルのダウンロードなどの常設チャット関連イベントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="cf83d-110">This table includes Persistent Chat-related events, such as chat messages and file downloads.</span></span> <span data-ttu-id="cf83d-111">(参加者のイベントは、tblComplianceParticipant テーブルによって追跡されます)。</span><span class="sxs-lookup"><span data-stu-id="cf83d-111">(Participant events are tracked by the tblComplianceParticipant table.)</span></span>  <br/> <span data-ttu-id="cf83d-112">(この表のイベントを処理したサーバーは、tblComplianceFanout テーブルに一覧表示されます)。</span><span class="sxs-lookup"><span data-stu-id="cf83d-112">(The servers that processed the events in this table are listed in the tblComplianceFanout table.)</span></span>  <br/> |
|[<span data-ttu-id="cf83d-113">tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="cf83d-113">tblComplianceFanout</span></span>](tblcompliancefanout.md) <br/> |<span data-ttu-id="cf83d-114">コンプライアンスイベントを処理したサーバーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="cf83d-114">Contains the servers that processed a compliance event.</span></span> <span data-ttu-id="cf83d-115">この表は、tblComplianceData テーブルと密接に結び付いています。</span><span class="sxs-lookup"><span data-stu-id="cf83d-115">This table is tightly coupled with the tblComplianceData table.</span></span>  <br/> |
|[<span data-ttu-id="cf83d-116">tblComplianceParticipant</span><span class="sxs-lookup"><span data-stu-id="cf83d-116">tblComplianceParticipant</span></span>](tblcomplianceparticipant.md) <br/> |<span data-ttu-id="cf83d-117">チャットサービスとサーバーごとに現在の参加者が含まれます。</span><span class="sxs-lookup"><span data-stu-id="cf83d-117">Contains current participants per chat service and per server.</span></span> <span data-ttu-id="cf83d-118">これは、常設チャットサービスから受信した参加イベントとパートコンプライアンスイベントに基づいて維持されます。</span><span class="sxs-lookup"><span data-stu-id="cf83d-118">It is maintained based on join and part compliance events received from the Persistent Chat service.</span></span>  <br/> |
|[<span data-ttu-id="cf83d-119">tblComplianceState</span><span class="sxs-lookup"><span data-stu-id="cf83d-119">tblComplianceState</span></span>](tblcompliancestate.md) <br/> |<span data-ttu-id="cf83d-120">プール全体のコンプライアンスの状態に関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="cf83d-120">Contains pool-wide compliance state information.</span></span>  <br/> |
   

