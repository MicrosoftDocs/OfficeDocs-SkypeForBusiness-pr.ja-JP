---
title: 常設チャット SQL Server ストアの追加
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c8e6064a-8127-4c25-8685-06f49d8bbfce
description: 永続的なチャット サーバーまたはプールの永続的なチャット サーバーのデータベースを提供する SQL Server ストアを構成するとします。
ms.openlocfilehash: 062092ff60fa30f7b8ac19725a12a3f62e1b9ec6
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/24/2018
---
# <a name="add-persistent-chat-sql-server-store"></a><span data-ttu-id="af3a1-103">常設チャット SQL Server ストアの追加</span><span class="sxs-lookup"><span data-stu-id="af3a1-103">Add Persistent Chat SQL Server Store</span></span>
 
<span data-ttu-id="af3a1-104">永続的なチャット サーバーまたはプールの永続的なチャット サーバーのデータベースを提供する SQL Server ストアを構成するとします。</span><span class="sxs-lookup"><span data-stu-id="af3a1-104">You configure the SQL Server stores that will provide databases for the Persistent Chat Server or Persistent Chat Server pool.</span></span>
  
 <span data-ttu-id="af3a1-105">**SQL Server に格納**します。 永続的なチャットの既存の SQL Server およびインスタンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="af3a1-105">**SQL Server store**: Select an existing SQL Server and optionally an instance for Persistent Chat.</span></span>
  
<span data-ttu-id="af3a1-106">新しい SQL Server および必要に応じてデータの永続的なチャットの新しいインスタンスを定義するのには**新規**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="af3a1-106">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat data.</span></span>
  
<span data-ttu-id="af3a1-107">SQL Server データベースおよび永続的なチャットのデータのミラー化されたデータベースを提供する省略可能なインスタンスを構成する**SQL Server を有効にするストアがミラー化**のチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="af3a1-107">Select the **Enable SQL Server store mirroring** checkbox to configure a SQL Server database and optional instance that will provide a mirrored database for the Persistent Chat data.</span></span>
  
<span data-ttu-id="af3a1-108">永続的なチャットの SQL Server 用の SQL Server ミラーとして動作するには、SQL Server と省略可能なインスタンスを**SQL Server のミラーを格納**するリストから選択します。</span><span class="sxs-lookup"><span data-stu-id="af3a1-108">Select from the list **Mirroring SQL Server store** a SQL Server and optional instance to act as the SQL Server mirror for the Persistent Chat SQL Server.</span></span>
  
<span data-ttu-id="af3a1-109">新しい SQL Server と、オプションで永続的なチャットの SQL Server のミラーリング用の新しいインスタンスを定義するのには**新規**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="af3a1-109">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat SQL Server mirroring.</span></span>
  
<span data-ttu-id="af3a1-110">[**SQL Server ミラーリング監視を自動フェールオーバーの有効化のために使用**] の一覧で、フェールオーバーのシナリオにおいて監視サーバーとして機能する SQL Server を選択します。</span><span class="sxs-lookup"><span data-stu-id="af3a1-110">Select the list **Use SQL Server mirroring witness to enable automatic failover** a SQL Server that will act as the witness server in failover scenarios.</span></span> <span data-ttu-id="af3a1-111">ミラーリング監視サーバーはミラーまたはホストのデータは、永続的なチャット サーバーですが、により、ミラー化構成で SQL Server を 1 つだけアクティブな SQL Server の任意の時点。</span><span class="sxs-lookup"><span data-stu-id="af3a1-111">The witness server does not mirror or host data for the Persistent Chat servers, but ensures that only one SQL Server in a mirrored configuration is the active SQL Server at any time.</span></span>
  
<span data-ttu-id="af3a1-112">新しい SQL Server のミラーリング監視サーバー インスタンスでは必要に応じて、永続的なチャット SQL Server ミラーリング監視を定義する**新規**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="af3a1-112">Click **New** to define a new SQL Server witness optionally an instance for the Persistent Chat SQL Server mirroring witness.</span></span>
  
<span data-ttu-id="af3a1-113">前のプール定義ダイアログに戻るには、[**戻る**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="af3a1-113">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="af3a1-114">このプールの SQL Server ストア構成の永続的なチャット サーバー プールの定義を続行するオプションの入力が終了したら**次へ**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="af3a1-114">Click **Next** after you have finished entering the options for this pool's SQL Server store configuration and to proceed with the Persistent Chat Server pool definition.</span></span>
  
<span data-ttu-id="af3a1-115">すべての変更を破棄して**新しい常設チャット プールの定義**ウィザードを終了するには、[**キャンセル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="af3a1-115">Click **Cancel** to discard all changes and end the **Define New Persistent Chat Pool** wizard.</span></span>
  
<span data-ttu-id="af3a1-116">このページのような状況依存のヘルプにアクセスするには、[**ヘルプ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="af3a1-116">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="af3a1-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="af3a1-117">See also</span></span>

#### 

[<span data-ttu-id="af3a1-118">ビジネス サーバー 2015 の Skype での永続的なチャット サーバーの計画</span><span class="sxs-lookup"><span data-stu-id="af3a1-118">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="af3a1-119">ビジネス サーバー 2015 トポロジの場合、Skype に永続的なチャット サーバーを追加します。</span><span class="sxs-lookup"><span data-stu-id="af3a1-119">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[<span data-ttu-id="af3a1-120">ビジネス サーバー 2015 の Skype での永続的なチャット サーバーのハードウェアおよびソフトウェアの要件</span><span class="sxs-lookup"><span data-stu-id="af3a1-120">Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[<span data-ttu-id="af3a1-121">ビジネス サーバー 2015 の Skype のサーバーの要件</span><span class="sxs-lookup"><span data-stu-id="af3a1-121">Server requirements for Skype for Business Server 2015</span></span>](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[<span data-ttu-id="af3a1-122">ビジネス サーバー 2015 の Skype のトポロジーの基本事項</span><span class="sxs-lookup"><span data-stu-id="af3a1-122">Topology Basics for Skype for Business Server 2015</span></span>](../../plan-your-deployment/topology-basics/topology-basics.md)
  
[<span data-ttu-id="af3a1-123">ビジネス サーバー 2015 の Skype での永続的なチャット サーバーの高可用性と障害回復を構成します。</span><span class="sxs-lookup"><span data-stu-id="af3a1-123">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)

