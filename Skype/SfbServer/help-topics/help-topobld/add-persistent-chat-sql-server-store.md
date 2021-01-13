---
title: 常設チャット SQL Server ストアを追加する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddPersistentChatSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c8e6064a-8127-4c25-8685-06f49d8bbfce
description: 常設チャット サーバー SQL Serverデータベースを提供する常設チャット サーバー ストアを構成します。
ms.openlocfilehash: e93705e0646f1115994a61c936a5c0cb16149dfa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49818657"
---
# <a name="add-persistent-chat-sql-server-store"></a><span data-ttu-id="7624f-103">常設チャット SQL Server ストアの追加</span><span class="sxs-lookup"><span data-stu-id="7624f-103">Add Persistent Chat SQL Server Store</span></span>
 
<span data-ttu-id="7624f-104">常設チャット サーバー SQL Serverデータベースを提供する常設チャット サーバー ストアを構成します。</span><span class="sxs-lookup"><span data-stu-id="7624f-104">You configure the SQL Server stores that will provide databases for the Persistent Chat Server or Persistent Chat Server pool.</span></span>
  
 <span data-ttu-id="7624f-105">**SQL Serverストア**: 既存のチャット を選択SQL Server、必要に応じて常設チャットのインスタンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="7624f-105">**SQL Server store**: Select an existing SQL Server and optionally an instance for Persistent Chat.</span></span>
  
<span data-ttu-id="7624f-106">[ **新規]** をクリックして、新SQL Serverし、必要に応じて常設チャット データの新しいインスタンスを定義します。</span><span class="sxs-lookup"><span data-stu-id="7624f-106">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat data.</span></span>
  
<span data-ttu-id="7624f-107">常設チャット **データSQL Server** データベースを提供する SQL Server データベースとオプションのインスタンスを構成するには、[ストア ミラーリングの有効化] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="7624f-107">Select the **Enable SQL Server store mirroring** checkbox to configure a SQL Server database and optional instance that will provide a mirrored database for the Persistent Chat data.</span></span>
  
<span data-ttu-id="7624f-108">[ミラーリング] リストから選択 **SQL Server常設** チャット SQL Serverのミラーとして機能するSQL Serverおよびオプションのインスタンスを格納SQL Server。</span><span class="sxs-lookup"><span data-stu-id="7624f-108">Select from the list **Mirroring SQL Server store** a SQL Server and optional instance to act as the SQL Server mirror for the Persistent Chat SQL Server.</span></span>
  
<span data-ttu-id="7624f-109">[ **新規]** をクリックして新しいSQL Serverし、必要に応じて常設チャット の新しいインスタンスをSQL Serverします。</span><span class="sxs-lookup"><span data-stu-id="7624f-109">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat SQL Server mirroring.</span></span>
  
<span data-ttu-id="7624f-110">[**SQL Server ミラーリング監視を自動フェールオーバーの有効化のために使用**] の一覧で、フェールオーバーのシナリオにおいて監視サーバーとして機能する SQL Server を選択します。</span><span class="sxs-lookup"><span data-stu-id="7624f-110">Select the list **Use SQL Server mirroring witness to enable automatic failover** a SQL Server that will act as the witness server in failover scenarios.</span></span> <span data-ttu-id="7624f-111">ミラーリング監視サーバーは、常設チャット サーバーのデータをミラー化またはホストしませんが、ミラー化された構成の 1 つの SQL Server だけがアクティブなチャット サーバー SQL Server保証します。</span><span class="sxs-lookup"><span data-stu-id="7624f-111">The witness server does not mirror or host data for the Persistent Chat servers, but ensures that only one SQL Server in a mirrored configuration is the active SQL Server at any time.</span></span>
  
<span data-ttu-id="7624f-112">[ **新規]** をクリックして、SQL Serverミラーリング監視のインスタンスを必要に応じて新しいSQL Server定義します。</span><span class="sxs-lookup"><span data-stu-id="7624f-112">Click **New** to define a new SQL Server witness optionally an instance for the Persistent Chat SQL Server mirroring witness.</span></span>
  
<span data-ttu-id="7624f-113">前のプール定義ダイアログに戻るには、[**戻る**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7624f-113">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="7624f-114">この **プール** のストア構成のオプションの入力が完了したら、[次へ] をSQL Serverし、常設チャット サーバー プールの定義に進みます。</span><span class="sxs-lookup"><span data-stu-id="7624f-114">Click **Next** after you have finished entering the options for this pool's SQL Server store configuration and to proceed with the Persistent Chat Server pool definition.</span></span>
  
<span data-ttu-id="7624f-115">すべての変更を破棄して **新しい常設チャット プールの定義** ウィザードを終了するには、[**キャンセル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7624f-115">Click **Cancel** to discard all changes and end the **Define New Persistent Chat Pool** wizard.</span></span>
  
<span data-ttu-id="7624f-116">このページのような状況依存のヘルプにアクセスするには、[**ヘルプ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7624f-116">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7624f-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="7624f-117">See also</span></span>

[<span data-ttu-id="7624f-118">Skype for Business Server 2015 での常設チャット サーバーの計画</span><span class="sxs-lookup"><span data-stu-id="7624f-118">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="7624f-119">Skype for Business Server 2015 トポロジへの常設チャット サーバーの追加</span><span class="sxs-lookup"><span data-stu-id="7624f-119">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[<span data-ttu-id="7624f-120">Skype for Business Server 2015 の常設チャット サーバーのハードウェア要件およびソフトウェア要件</span><span class="sxs-lookup"><span data-stu-id="7624f-120">Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[<span data-ttu-id="7624f-121">Skype for Business Server 2015 のサーバー要件</span><span class="sxs-lookup"><span data-stu-id="7624f-121">Server requirements for Skype for Business Server 2015</span></span>](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[<span data-ttu-id="7624f-122">Skype for Business Server 2015 のトポロジの基本</span><span class="sxs-lookup"><span data-stu-id="7624f-122">Topology Basics for Skype for Business Server 2015</span></span>](../../plan-your-deployment/topology-basics/topology-basics.md)
  
[<span data-ttu-id="7624f-123">Skype for Business Server 2015 での常設チャット サーバーの高可用性と障害復旧の構成</span><span class="sxs-lookup"><span data-stu-id="7624f-123">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
