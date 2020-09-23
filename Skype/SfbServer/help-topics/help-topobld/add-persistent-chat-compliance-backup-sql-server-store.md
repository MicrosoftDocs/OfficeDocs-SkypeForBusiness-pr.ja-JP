---
title: 常設チャット コンプライアンス バックアップ SQL Server ストアの追加
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
- ms.lync.tb.AddPersistentChatBackupComplianceStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 358b74bd-a97d-4f28-9bed-af633ea0099e
description: 常設チャットサーバーまたは常設チャットサーバーコンプライアンス SQL Server ストアのバックアップデータベースを提供するバックアップコンプライアンス SQL Server ストアを構成します。
ms.openlocfilehash: 9251c322560d06652c4eefe80b6c05a51aa9f922
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218698"
---
# <a name="add-persistent-chat-compliance-backup-sql-server-store"></a><span data-ttu-id="3f926-103">常設チャット コンプライアンス バックアップ SQL Server ストアの追加</span><span class="sxs-lookup"><span data-stu-id="3f926-103">Add Persistent Chat Compliance Backup SQL Server Store</span></span>
 
<span data-ttu-id="3f926-104">常設チャットサーバーまたは常設チャットサーバーコンプライアンス SQL Server ストアのバックアップデータベースを提供するバックアップコンプライアンス SQL Server ストアを構成します。</span><span class="sxs-lookup"><span data-stu-id="3f926-104">You configure the Backup compliance SQL Server stores that will provide backup databases for the Persistent Chat Server or Persistent Chat Server compliance SQL Server stores.</span></span>
  
 <span data-ttu-id="3f926-105">[ **Sql server ストア**]: 既存の sql server と、必要に応じて常設チャットのインスタンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="3f926-105">**SQL Server store**: Select an existing SQL Server and optionally an instance for Persistent Chat.</span></span>
  
<span data-ttu-id="3f926-106">[ **新規** ] をクリックして、新しい SQL Server を定義し、オプションで常設チャットバックアップコンプライアンスデータの新しいインスタンスを定義します。</span><span class="sxs-lookup"><span data-stu-id="3f926-106">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat backup compliance data.</span></span>
  
<span data-ttu-id="3f926-107">[ **Sql server ストアミラーリングの有効化** ] チェックボックスをオンにして、永続的なチャットバックアップコンプライアンスデータのミラーリングされたデータベースを提供する sql server データベースとオプションのインスタンスを構成します。</span><span class="sxs-lookup"><span data-stu-id="3f926-107">Select the **Enable SQL Server store mirroring** checkbox to configure a SQL Server database and optional instance that will provide a mirrored database for the Persistent Chat backup compliance data.</span></span>
  
<span data-ttu-id="3f926-108">[ **ミラーリング Sql server ストア** ] の一覧から、常設チャットバックアップコンプライアンス sql SERVER の sql server ミラーとして機能する sql server およびオプションのインスタンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="3f926-108">Select from the list **Mirroring SQL Server store** a SQL Server and optional instance to act as the SQL Server mirror for the Persistent Chat backup compliance SQL Server.</span></span>
  
<span data-ttu-id="3f926-109">[ **新規** ] をクリックして、新しい sql server を定義し、オプションで常設チャットの sql server ミラーリング用の新しいインスタンスを定義します。</span><span class="sxs-lookup"><span data-stu-id="3f926-109">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat SQL Server mirroring.</span></span>
  
<span data-ttu-id="3f926-110">[**SQL Server ミラーリング監視を自動フェールオーバーの有効化のために使用**] の一覧で、フェールオーバーのシナリオにおいて監視サーバーとして機能する SQL Server を選択します。</span><span class="sxs-lookup"><span data-stu-id="3f926-110">Select the list **Use SQL Server mirroring witness to enable automatic failover** a SQL Server that will act as the witness server in failover scenarios.</span></span> <span data-ttu-id="3f926-111">ミラーリング監視サーバーは、常設チャットサーバーのデータをミラーリングまたはホストしませんが、ミラーリング構成の SQL サーバーが常にアクティブな SQL Server であることを保証します。</span><span class="sxs-lookup"><span data-stu-id="3f926-111">The witness server does not mirror or host data for the Persistent Chat servers, but ensures that only one SQL Server in a mirrored configuration is the active SQL Server at any time.</span></span>
  
<span data-ttu-id="3f926-112">[ **新規** ] をクリックして、新しい sql server 監視を定義します。オプションで、永続的なチャットバックアップコンプライアンス SQL server ミラーリング監視のインスタンスを定義します。</span><span class="sxs-lookup"><span data-stu-id="3f926-112">Click **New** to define a new SQL Server witness optionally an instance for the Persistent Chat backup compliance SQL Server mirroring witness.</span></span>
  
<span data-ttu-id="3f926-113">前のプール定義ダイアログに戻るには、[**戻る**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f926-113">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="3f926-114">このプールのバックアップ SQL Server ストア構成のオプションの入力が終了したら、[ **次へ** ] をクリックして、常設チャットサーバープールの定義を続行します。</span><span class="sxs-lookup"><span data-stu-id="3f926-114">Click **Next** after you have finished entering the options for this pool's backup SQL Server store configuration and to proceed with the Persistent Chat Server pool definition.</span></span>
  
<span data-ttu-id="3f926-115">すべての変更を破棄して**新しい常設チャット プールの定義**ウィザードを終了するには、[**キャンセル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f926-115">Click **Cancel** to discard all changes and end the **Define New Persistent Chat Pool** wizard.</span></span>
  
<span data-ttu-id="3f926-116">このページのような状況依存のヘルプにアクセスするには、[**ヘルプ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f926-116">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3f926-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="3f926-117">See also</span></span>

[<span data-ttu-id="3f926-118">Skype for Business Server 2015 での常設チャットサーバーの計画</span><span class="sxs-lookup"><span data-stu-id="3f926-118">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="3f926-119">Skype for Business Server 2015 のサーバー要件</span><span class="sxs-lookup"><span data-stu-id="3f926-119">Server requirements for Skype for Business Server 2015</span></span>](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[<span data-ttu-id="3f926-120">Skype for Business Server 2015 の常設チャットサーバーのハードウェアおよびソフトウェア要件</span><span class="sxs-lookup"><span data-stu-id="3f926-120">Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[<span data-ttu-id="3f926-121">Skype for Business Server 2015 で常設チャットサーバーのコンプライアンスサービスを構成する</span><span class="sxs-lookup"><span data-stu-id="3f926-121">Configure the Compliance service for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../manage/persistent-chat/configure-compliance.md)
  
[<span data-ttu-id="3f926-122">Skype for Business Server 2015 での常設チャットサーバーの高可用性および障害復旧の構成</span><span class="sxs-lookup"><span data-stu-id="3f926-122">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
