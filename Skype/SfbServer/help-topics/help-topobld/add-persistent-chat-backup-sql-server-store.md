---
title: 常設チャット バックアップ SQL Server ストアを追加する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddPersistentChatBackupSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 106698e4-ce73-4a34-8fc7-e9d3208a17dc
description: 常設チャットサーバーまたは常設チャットサーバープールのバックアップデータベースを提供するバックアップ SQL Server ストアを構成します。
ms.openlocfilehash: 70eec229c567120d0669979f688c152e1b1e3d79
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218708"
---
# <a name="add-persistent-chat-backup-sql-server-store"></a><span data-ttu-id="1ce23-103">常設チャット バックアップ SQL Server ストアを追加する</span><span class="sxs-lookup"><span data-stu-id="1ce23-103">Add Persistent Chat Backup SQL Server Store</span></span>
 
<span data-ttu-id="1ce23-104">常設チャットサーバーまたは常設チャットサーバープールのバックアップデータベースを提供するバックアップ SQL Server ストアを構成します。</span><span class="sxs-lookup"><span data-stu-id="1ce23-104">You configure the Backup SQL Server stores that will provide backup databases for the Persistent Chat Server or Persistent Chat Server pool.</span></span>
  
 <span data-ttu-id="1ce23-105">[ **Sql server ストア**]: 既存の sql server と、必要に応じて常設チャットのインスタンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="1ce23-105">**SQL Server store**: Select an existing SQL Server and optionally an instance for Persistent Chat.</span></span>
  
<span data-ttu-id="1ce23-106">[ **新規** ] をクリックして、新しい SQL Server と、必要に応じて常設チャットのバックアップデータの新しいインスタンスを定義します。</span><span class="sxs-lookup"><span data-stu-id="1ce23-106">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat backup data.</span></span>
  
<span data-ttu-id="1ce23-107">[ **Sql server ストアミラーリングの有効化** ] チェックボックスをオンにして、永続的なチャットバックアップデータのミラーリングされたデータベースを提供する sql server データベースとオプションのインスタンスを構成します。</span><span class="sxs-lookup"><span data-stu-id="1ce23-107">Select the **Enable SQL Server store mirroring** checkbox to configure a SQL Server database and optional instance that will provide a mirrored database for the Persistent Chat backup data.</span></span>
  
<span data-ttu-id="1ce23-108">[ **ミラーリング Sql server ストア** ] の一覧から、常設チャットバックアップ sql SERVER の sql server ミラーとして動作する sql server およびオプションのインスタンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="1ce23-108">Select from the list **Mirroring SQL Server store** a SQL Server and optional instance to act as the SQL Server mirror for the Persistent Chat backup SQL Server.</span></span>
  
<span data-ttu-id="1ce23-109">[ **新規** ] をクリックして、新しい sql server を定義し、オプションで常設チャットの sql server ミラーリング用の新しいインスタンスを定義します。</span><span class="sxs-lookup"><span data-stu-id="1ce23-109">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat SQL Server mirroring.</span></span>
  
<span data-ttu-id="1ce23-110">[**SQL Server ミラーリング監視を自動フェールオーバーの有効化のために使用**] の一覧で、フェールオーバーのシナリオにおいて監視サーバーとして機能する SQL Server を選択します。</span><span class="sxs-lookup"><span data-stu-id="1ce23-110">Select the list **Use SQL Server mirroring witness to enable automatic failover** a SQL Server that will act as the witness server in failover scenarios.</span></span> <span data-ttu-id="1ce23-111">ミラーリング監視サーバーは、常設チャットサーバーのデータをミラーリングまたはホストしませんが、ミラーリング構成の SQL サーバーが常にアクティブな SQL Server であることを保証します。</span><span class="sxs-lookup"><span data-stu-id="1ce23-111">The witness server does not mirror or host data for the Persistent Chat servers, but ensures that only one SQL Server in a mirrored configuration is the active SQL Server at any time.</span></span>
  
<span data-ttu-id="1ce23-112">[ **新規** ] をクリックして、新しい sql server 監視を定義します。オプションで、常設チャットバックアップ sql server ミラーリング監視のインスタンスを定義します。</span><span class="sxs-lookup"><span data-stu-id="1ce23-112">Click **New** to define a new SQL Server witness optionally an instance for the Persistent Chat backup SQL Server mirroring witness.</span></span>
  
<span data-ttu-id="1ce23-113">前のプール定義ダイアログに戻るには、[**戻る**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1ce23-113">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="1ce23-114">このプールのバックアップ SQL Server ストア構成のオプションの入力が終了したら、[ **次へ** ] をクリックして、常設チャットサーバープールの定義を続行します。</span><span class="sxs-lookup"><span data-stu-id="1ce23-114">Click **Next** after you have finished entering the options for this pool's backup SQL Server store configuration and to proceed with the Persistent Chat Server pool definition.</span></span>
  
<span data-ttu-id="1ce23-115">すべての変更を破棄して**新しい常設チャット プールの定義**ウィザードを終了するには、[**キャンセル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1ce23-115">Click **Cancel** to discard all changes and end the **Define New Persistent Chat Pool** wizard.</span></span>
  
<span data-ttu-id="1ce23-116">このページのような状況依存のヘルプにアクセスするには、[**ヘルプ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1ce23-116">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1ce23-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="1ce23-117">See also</span></span>

[<span data-ttu-id="1ce23-118">Skype for Business Server 2015 での常設チャットサーバーの計画</span><span class="sxs-lookup"><span data-stu-id="1ce23-118">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="1ce23-119">Skype for Business Server 2015 のサーバー要件</span><span class="sxs-lookup"><span data-stu-id="1ce23-119">Server requirements for Skype for Business Server 2015</span></span>](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[<span data-ttu-id="1ce23-120">Skype for Business Server 2015 の常設チャットサーバーのハードウェアおよびソフトウェア要件</span><span class="sxs-lookup"><span data-stu-id="1ce23-120">Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[<span data-ttu-id="1ce23-121">Skype for Business Server 2015 での常設チャットサーバーの高可用性および障害復旧の構成</span><span class="sxs-lookup"><span data-stu-id="1ce23-121">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
