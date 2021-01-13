---
title: 常設チャット バックアップ SQL Server ストアを追加する
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
- ms.lync.tb.AddPersistentChatBackupSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 106698e4-ce73-4a34-8fc7-e9d3208a17dc
description: 常設チャット サーバー SQL Serverバックアップ データベースを提供するバックアップ サーバー ストアを構成します。
ms.openlocfilehash: c21cd099372bb49b621447697320df2785a0c9dc
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49818737"
---
# <a name="add-persistent-chat-backup-sql-server-store"></a><span data-ttu-id="3b8dd-103">常設チャット バックアップ SQL Server ストアの追加</span><span class="sxs-lookup"><span data-stu-id="3b8dd-103">Add Persistent Chat Backup SQL Server Store</span></span>
 
<span data-ttu-id="3b8dd-104">常設チャット サーバー SQL Serverバックアップ データベースを提供するバックアップ サーバー ストアを構成します。</span><span class="sxs-lookup"><span data-stu-id="3b8dd-104">You configure the Backup SQL Server stores that will provide backup databases for the Persistent Chat Server or Persistent Chat Server pool.</span></span>
  
 <span data-ttu-id="3b8dd-105">**SQL Serverストア**: 既存のチャット を選択SQL Server、必要に応じて常設チャットのインスタンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="3b8dd-105">**SQL Server store**: Select an existing SQL Server and optionally an instance for Persistent Chat.</span></span>
  
<span data-ttu-id="3b8dd-106">[ **新規]** をクリックして、新しいSQL Serverし、必要に応じて常設チャットのバックアップ データの新しいインスタンスを定義します。</span><span class="sxs-lookup"><span data-stu-id="3b8dd-106">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat backup data.</span></span>
  
<span data-ttu-id="3b8dd-107">常設チャット **の** SQL Serverデータベースを提供する SQL Server データベースとオプションのインスタンスを構成するには、[ストア ミラーリングの有効化] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="3b8dd-107">Select the **Enable SQL Server store mirroring** checkbox to configure a SQL Server database and optional instance that will provide a mirrored database for the Persistent Chat backup data.</span></span>
  
<span data-ttu-id="3b8dd-108">リストから **選択しSQL Server** 常設チャット のバックアップ SQL Serverミラーとして機能する SQL Server およびオプションのインスタンスを格納SQL Server。</span><span class="sxs-lookup"><span data-stu-id="3b8dd-108">Select from the list **Mirroring SQL Server store** a SQL Server and optional instance to act as the SQL Server mirror for the Persistent Chat backup SQL Server.</span></span>
  
<span data-ttu-id="3b8dd-109">[ **新規]** をクリックして新しいSQL Serverし、必要に応じて常設チャット の新しいインスタンスをSQL Serverします。</span><span class="sxs-lookup"><span data-stu-id="3b8dd-109">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat SQL Server mirroring.</span></span>
  
<span data-ttu-id="3b8dd-110">[**SQL Server ミラーリング監視を自動フェールオーバーの有効化のために使用**] の一覧で、フェールオーバーのシナリオにおいて監視サーバーとして機能する SQL Server を選択します。</span><span class="sxs-lookup"><span data-stu-id="3b8dd-110">Select the list **Use SQL Server mirroring witness to enable automatic failover** a SQL Server that will act as the witness server in failover scenarios.</span></span> <span data-ttu-id="3b8dd-111">ミラーリング監視サーバーは、常設チャット サーバーのデータをミラー化またはホストしませんが、ミラー化された構成の 1 つの SQL Server だけがアクティブなチャット サーバー SQL Server保証します。</span><span class="sxs-lookup"><span data-stu-id="3b8dd-111">The witness server does not mirror or host data for the Persistent Chat servers, but ensures that only one SQL Server in a mirrored configuration is the active SQL Server at any time.</span></span>
  
<span data-ttu-id="3b8dd-112">[ **新規]** をクリックして、ミラーリング監視SQL Server常設チャット バックアップ監視のインスタンスを定義SQL Server定義します。</span><span class="sxs-lookup"><span data-stu-id="3b8dd-112">Click **New** to define a new SQL Server witness optionally an instance for the Persistent Chat backup SQL Server mirroring witness.</span></span>
  
<span data-ttu-id="3b8dd-113">前のプール定義ダイアログに戻るには、[**戻る**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3b8dd-113">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="3b8dd-114">この **プール** のバックアップ サーバー構成のオプションの入力が完了したら、[次へ] SQL Serverをクリックし、常設チャット サーバー プールの定義に進みます。</span><span class="sxs-lookup"><span data-stu-id="3b8dd-114">Click **Next** after you have finished entering the options for this pool's backup SQL Server store configuration and to proceed with the Persistent Chat Server pool definition.</span></span>
  
<span data-ttu-id="3b8dd-115">すべての変更を破棄して **新しい常設チャット プールの定義** ウィザードを終了するには、[**キャンセル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3b8dd-115">Click **Cancel** to discard all changes and end the **Define New Persistent Chat Pool** wizard.</span></span>
  
<span data-ttu-id="3b8dd-116">このページのような状況依存のヘルプにアクセスするには、[**ヘルプ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3b8dd-116">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3b8dd-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="3b8dd-117">See also</span></span>

[<span data-ttu-id="3b8dd-118">Skype for Business Server 2015 での常設チャット サーバーの計画</span><span class="sxs-lookup"><span data-stu-id="3b8dd-118">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="3b8dd-119">Skype for Business Server 2015 のサーバー要件</span><span class="sxs-lookup"><span data-stu-id="3b8dd-119">Server requirements for Skype for Business Server 2015</span></span>](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[<span data-ttu-id="3b8dd-120">Skype for Business Server 2015 の常設チャット サーバーのハードウェア要件およびソフトウェア要件</span><span class="sxs-lookup"><span data-stu-id="3b8dd-120">Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[<span data-ttu-id="3b8dd-121">Skype for Business Server 2015 での常設チャット サーバーの高可用性と障害復旧の構成</span><span class="sxs-lookup"><span data-stu-id="3b8dd-121">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
