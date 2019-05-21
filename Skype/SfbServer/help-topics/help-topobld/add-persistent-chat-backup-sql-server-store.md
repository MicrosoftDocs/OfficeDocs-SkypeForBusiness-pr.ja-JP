---
title: 常設チャット バックアップ SQL Server ストアの追加
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatBackupSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 106698e4-ce73-4a34-8fc7-e9d3208a17dc
description: 常設チャットサーバーまたは常設チャットサーバープールのバックアップデータベースを提供するバックアップ SQL Server ストアを構成します。
ms.openlocfilehash: 39e5e1ead6ed3cb089545406852de16170d782dc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34304654"
---
# <a name="add-persistent-chat-backup-sql-server-store"></a><span data-ttu-id="50133-103">常設チャット バックアップ SQL Server ストアの追加</span><span class="sxs-lookup"><span data-stu-id="50133-103">Add Persistent Chat Backup SQL Server Store</span></span>
 
<span data-ttu-id="50133-104">常設チャットサーバーまたは常設チャットサーバープールのバックアップデータベースを提供するバックアップ SQL Server ストアを構成します。</span><span class="sxs-lookup"><span data-stu-id="50133-104">You configure the Backup SQL Server stores that will provide backup databases for the Persistent Chat Server or Persistent Chat Server pool.</span></span>
  
 <span data-ttu-id="50133-105">**Sql server ストア**: 既存の sql server を選択し、必要に応じて常設チャットのインスタンスも選択します。</span><span class="sxs-lookup"><span data-stu-id="50133-105">**SQL Server store**: Select an existing SQL Server and optionally an instance for Persistent Chat.</span></span>
  
<span data-ttu-id="50133-106">[**新規**] をクリックして、新しい SQL Server を定義し、必要に応じて永続的なチャットバックアップデータの新しいインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="50133-106">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat backup data.</span></span>
  
<span data-ttu-id="50133-107">[ **Sql server ストアのミラーリングを有効**にする] チェックボックスをオンにして、sql server データベースと永続的なチャットバックアップデータのミラーリングされたデータベースを提供するオプションのインスタンスを構成します。</span><span class="sxs-lookup"><span data-stu-id="50133-107">Select the **Enable SQL Server store mirroring** checkbox to configure a SQL Server database and optional instance that will provide a mirrored database for the Persistent Chat backup data.</span></span>
  
<span data-ttu-id="50133-108">リストの**ミラーリング Sql server ストア**から選択します。 sql server とオプションのインスタンスは、常設チャットバックアップの sql SERVER の sql server ミラーとして機能します。</span><span class="sxs-lookup"><span data-stu-id="50133-108">Select from the list **Mirroring SQL Server store** a SQL Server and optional instance to act as the SQL Server mirror for the Persistent Chat backup SQL Server.</span></span>
  
<span data-ttu-id="50133-109">[**新規**] をクリックして、新しい sql server を定義し、必要に応じて、常設チャットの sql server ミラーリング用の新しいインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="50133-109">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat SQL Server mirroring.</span></span>
  
<span data-ttu-id="50133-110">[**SQL Server ミラーリング監視を自動フェールオーバーの有効化のために使用**] の一覧で、フェールオーバーのシナリオにおいて監視サーバーとして機能する SQL Server を選択します。</span><span class="sxs-lookup"><span data-stu-id="50133-110">Select the list **Use SQL Server mirroring witness to enable automatic failover** a SQL Server that will act as the witness server in failover scenarios.</span></span> <span data-ttu-id="50133-111">監視サーバーは、常設チャットサーバーのデータをミラーリングまたはホストしませんが、ミラー化された構成内の1つの SQL Server のみがアクティブな SQL Server であることを常に確認します。</span><span class="sxs-lookup"><span data-stu-id="50133-111">The witness server does not mirror or host data for the Persistent Chat servers, but ensures that only one SQL Server in a mirrored configuration is the active SQL Server at any time.</span></span>
  
<span data-ttu-id="50133-112">[**新規**] をクリックして、新しい sql server 監視を定義します。必要に応じて、永続的なチャットバックアップ SQL server ミラーリング監視のインスタンスを指定します。</span><span class="sxs-lookup"><span data-stu-id="50133-112">Click **New** to define a new SQL Server witness optionally an instance for the Persistent Chat backup SQL Server mirroring witness.</span></span>
  
<span data-ttu-id="50133-113">前のプール定義ダイアログに戻るには、[**戻る**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="50133-113">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="50133-114">このプールの backup SQL Server ストア構成のオプションを入力して、常設チャットサーバープールの定義を続行するには、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="50133-114">Click **Next** after you have finished entering the options for this pool's backup SQL Server store configuration and to proceed with the Persistent Chat Server pool definition.</span></span>
  
<span data-ttu-id="50133-115">すべての変更を破棄して**新しい常設チャット プールの定義**ウィザードを終了するには、[**キャンセル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="50133-115">Click **Cancel** to discard all changes and end the **Define New Persistent Chat Pool** wizard.</span></span>
  
<span data-ttu-id="50133-116">このページのような状況依存のヘルプにアクセスするには、[**ヘルプ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="50133-116">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="50133-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="50133-117">See also</span></span>

[<span data-ttu-id="50133-118">Skype for Business Server 2015 の常設チャット サーバーの計画</span><span class="sxs-lookup"><span data-stu-id="50133-118">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="50133-119">Server requirements for Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="50133-119">Server requirements for Skype for Business Server 2015</span></span>](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[<span data-ttu-id="50133-120">Skype for Business Server 2015 の常設チャット サーバーのハードウェアおよびソフトウェア要件</span><span class="sxs-lookup"><span data-stu-id="50133-120">Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[<span data-ttu-id="50133-121">Skype for Business Server 2015 での常設チャット サーバーの高可用性および障害復旧の構成</span><span class="sxs-lookup"><span data-stu-id="50133-121">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
