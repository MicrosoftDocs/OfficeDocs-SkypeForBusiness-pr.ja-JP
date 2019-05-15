---
title: ビジネス サーバーの Skype での永続的なチャット サーバー コンプライアンス テーブルの一覧
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8563446e-90cc-47cc-8a8e-4883decfe195
description: 永続的なチャット コンプライアンス データベース スキーマは、次の表で構成されます。
ms.openlocfilehash: e17b2e52bdeb65ff4c77377cb913da212f20ecf0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929890"
---
# <a name="list-of-persistent-chat-server-compliance-tables-in-skype-for-business-server"></a><span data-ttu-id="1fc5d-103">ビジネス サーバーの Skype での永続的なチャット サーバー コンプライアンス テーブルの一覧</span><span class="sxs-lookup"><span data-stu-id="1fc5d-103">List of Persistent Chat Server compliance tables in Skype for Business Server</span></span>
 
<span data-ttu-id="1fc5d-104">永続的なチャット コンプライアンス データベース スキーマは、次の表で構成されます。</span><span class="sxs-lookup"><span data-stu-id="1fc5d-104">The Persistent Chat compliance database schema consists of the following tables.</span></span>
  
## <a name="list-of-persistent-chat-server-compliance-tables"></a><span data-ttu-id="1fc5d-105">永続的なチャット サーバー コンプライアンス テーブルの一覧</span><span class="sxs-lookup"><span data-stu-id="1fc5d-105">List of Persistent Chat Server Compliance Tables</span></span>

|<span data-ttu-id="1fc5d-106">**テーブル**</span><span class="sxs-lookup"><span data-stu-id="1fc5d-106">**Table**</span></span>|<span data-ttu-id="1fc5d-107">**説明**</span><span class="sxs-lookup"><span data-stu-id="1fc5d-107">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="1fc5d-108">tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="1fc5d-108">tblComplianceData</span></span>](tblcompliancedata.md) <br/> |<span data-ttu-id="1fc5d-109">構成されているアダプターによってまだ処理されていないコンプライアンス イベントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="1fc5d-109">Contains the compliance events that have not yet been processed by the configured adapter.</span></span>  <br/> <span data-ttu-id="1fc5d-110">このテーブルには、チャット メッセージやファイルのダウンロードなどの永続的なチャットに関連するイベントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="1fc5d-110">This table includes Persistent Chat-related events, such as chat messages and file downloads.</span></span> <span data-ttu-id="1fc5d-111">(イベントの参加者は、tblComplianceParticipant テーブルで追跡されます)。</span><span class="sxs-lookup"><span data-stu-id="1fc5d-111">(Participant events are tracked by the tblComplianceParticipant table.)</span></span>  <br/> <span data-ttu-id="1fc5d-112">(この表に示すイベントを処理するサーバーは、tblComplianceFanout の表に一覧表示されます)。</span><span class="sxs-lookup"><span data-stu-id="1fc5d-112">(The servers that processed the events in this table are listed in the tblComplianceFanout table.)</span></span>  <br/> |
|[<span data-ttu-id="1fc5d-113">tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="1fc5d-113">tblComplianceFanout</span></span>](tblcompliancefanout.md) <br/> |<span data-ttu-id="1fc5d-114">コンプライアンス イベントを処理するサーバーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="1fc5d-114">Contains the servers that processed a compliance event.</span></span> <span data-ttu-id="1fc5d-115">次の表は、tblComplianceData テーブルと密接に関連します。</span><span class="sxs-lookup"><span data-stu-id="1fc5d-115">This table is tightly coupled with the tblComplianceData table.</span></span>  <br/> |
|[<span data-ttu-id="1fc5d-116">tblComplianceParticipant</span><span class="sxs-lookup"><span data-stu-id="1fc5d-116">tblComplianceParticipant</span></span>](tblcomplianceparticipant.md) <br/> |<span data-ttu-id="1fc5d-117">チャット サービスおよびサーバーごとの現在の参加者が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1fc5d-117">Contains current participants per chat service and per server.</span></span> <span data-ttu-id="1fc5d-118">永続的なチャット サービスから受信した結合し、一部のコンプライアンス イベントに基づいて保持されます。</span><span class="sxs-lookup"><span data-stu-id="1fc5d-118">It is maintained based on join and part compliance events received from the Persistent Chat service.</span></span>  <br/> |
|[<span data-ttu-id="1fc5d-119">tblComplianceState</span><span class="sxs-lookup"><span data-stu-id="1fc5d-119">tblComplianceState</span></span>](tblcompliancestate.md) <br/> |<span data-ttu-id="1fc5d-120">プール全体にわたるコンプライアンスの状態情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1fc5d-120">Contains pool-wide compliance state information.</span></span>  <br/> |
   

