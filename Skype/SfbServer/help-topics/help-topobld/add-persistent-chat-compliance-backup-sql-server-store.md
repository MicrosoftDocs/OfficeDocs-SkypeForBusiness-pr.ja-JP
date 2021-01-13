---
title: 常設チャット コンプライアンス バックアップ SQL Server ストアの追加
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
- ms.lync.tb.AddPersistentChatBackupComplianceStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 358b74bd-a97d-4f28-9bed-af633ea0099e
description: 常設チャット サーバーまたは常設SQL Serverサーバー コンプライアンス データベースのバックアップ データベースを提供するバックアップ コンプライアンス サーバーストアを構成SQL Serverします。
ms.openlocfilehash: 9b380091978d62294c6ea16ffa8586b9f8d9d322
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49818717"
---
# <a name="add-persistent-chat-compliance-backup-sql-server-store"></a><span data-ttu-id="3a521-103">常設チャット コンプライアンス バックアップ SQL Server ストアの追加</span><span class="sxs-lookup"><span data-stu-id="3a521-103">Add Persistent Chat Compliance Backup SQL Server Store</span></span>
 
<span data-ttu-id="3a521-104">常設チャット サーバーまたは常設SQL Serverサーバー コンプライアンス データベースのバックアップ データベースを提供するバックアップ コンプライアンス サーバーストアを構成SQL Serverします。</span><span class="sxs-lookup"><span data-stu-id="3a521-104">You configure the Backup compliance SQL Server stores that will provide backup databases for the Persistent Chat Server or Persistent Chat Server compliance SQL Server stores.</span></span>
  
 <span data-ttu-id="3a521-105">**SQL Serverストア**: 既存のチャット をSQL Server、必要に応じて常設チャットのインスタンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="3a521-105">**SQL Server store**: Select an existing SQL Server and optionally an instance for Persistent Chat.</span></span>
  
<span data-ttu-id="3a521-106">[ **新規]** をクリックして、新しいSQL Serverし、必要に応じて常設チャット のバックアップ コンプライアンス データの新しいインスタンスを定義します。</span><span class="sxs-lookup"><span data-stu-id="3a521-106">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat backup compliance data.</span></span>
  
<span data-ttu-id="3a521-107">常設チャット の **バックアップ SQL Server** コンプライアンス データ用にミラー化されたデータベースを提供する SQL Server データベースとオプションのインスタンスを構成するには、[ストア ミラーリングストアのミラーリングを有効にする] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="3a521-107">Select the **Enable SQL Server store mirroring** checkbox to configure a SQL Server database and optional instance that will provide a mirrored database for the Persistent Chat backup compliance data.</span></span>
  
<span data-ttu-id="3a521-108">リストから選択し **、SQL Server** 常設チャット のSQL Serverコンプライアンス ポリシーのミラーとして機能する SQL Server およびオプションのインスタンスを格納SQL Server。</span><span class="sxs-lookup"><span data-stu-id="3a521-108">Select from the list **Mirroring SQL Server store** a SQL Server and optional instance to act as the SQL Server mirror for the Persistent Chat backup compliance SQL Server.</span></span>
  
<span data-ttu-id="3a521-109">[ **新規]** をクリックして新しいSQL Serverし、必要に応じて常設チャット の新しいインスタンスをSQL Serverします。</span><span class="sxs-lookup"><span data-stu-id="3a521-109">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat SQL Server mirroring.</span></span>
  
<span data-ttu-id="3a521-110">[**SQL Server ミラーリング監視を自動フェールオーバーの有効化のために使用**] の一覧で、フェールオーバーのシナリオにおいて監視サーバーとして機能する SQL Server を選択します。</span><span class="sxs-lookup"><span data-stu-id="3a521-110">Select the list **Use SQL Server mirroring witness to enable automatic failover** a SQL Server that will act as the witness server in failover scenarios.</span></span> <span data-ttu-id="3a521-111">ミラーリング監視サーバーは、常設チャット サーバーのデータをミラー化またはホストしませんが、ミラー化された構成の 1 つの SQL Server だけがアクティブなチャット サーバー SQL Server保証します。</span><span class="sxs-lookup"><span data-stu-id="3a521-111">The witness server does not mirror or host data for the Persistent Chat servers, but ensures that only one SQL Server in a mirrored configuration is the active SQL Server at any time.</span></span>
  
<span data-ttu-id="3a521-112">[ **新規]** をクリックして、ミラーリング監視SQL Server常設チャット バックアップ コンプライアンス監視のインスタンスを定義SQL Server定義します。</span><span class="sxs-lookup"><span data-stu-id="3a521-112">Click **New** to define a new SQL Server witness optionally an instance for the Persistent Chat backup compliance SQL Server mirroring witness.</span></span>
  
<span data-ttu-id="3a521-113">前のプール定義ダイアログに戻るには、[**戻る**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3a521-113">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="3a521-114">この **プール** のバックアップ サーバー構成のオプションの入力が完了したら、[次へ] SQL Serverをクリックし、常設チャット サーバー プールの定義に進みます。</span><span class="sxs-lookup"><span data-stu-id="3a521-114">Click **Next** after you have finished entering the options for this pool's backup SQL Server store configuration and to proceed with the Persistent Chat Server pool definition.</span></span>
  
<span data-ttu-id="3a521-115">すべての変更を破棄して **新しい常設チャット プールの定義** ウィザードを終了するには、[**キャンセル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3a521-115">Click **Cancel** to discard all changes and end the **Define New Persistent Chat Pool** wizard.</span></span>
  
<span data-ttu-id="3a521-116">このページのような状況依存のヘルプにアクセスするには、[**ヘルプ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3a521-116">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3a521-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="3a521-117">See also</span></span>

[<span data-ttu-id="3a521-118">Skype for Business Server 2015 での常設チャット サーバーの計画</span><span class="sxs-lookup"><span data-stu-id="3a521-118">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="3a521-119">Skype for Business Server 2015 のサーバー要件</span><span class="sxs-lookup"><span data-stu-id="3a521-119">Server requirements for Skype for Business Server 2015</span></span>](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[<span data-ttu-id="3a521-120">Skype for Business Server 2015 の常設チャット サーバーのハードウェア要件およびソフトウェア要件</span><span class="sxs-lookup"><span data-stu-id="3a521-120">Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[<span data-ttu-id="3a521-121">Skype for Business Server 2015 での常設チャット サーバーのコンプライアンス サービスの構成</span><span class="sxs-lookup"><span data-stu-id="3a521-121">Configure the Compliance service for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../manage/persistent-chat/configure-compliance.md)
  
[<span data-ttu-id="3a521-122">Skype for Business Server 2015 での常設チャット サーバーの高可用性と障害復旧の構成</span><span class="sxs-lookup"><span data-stu-id="3a521-122">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
