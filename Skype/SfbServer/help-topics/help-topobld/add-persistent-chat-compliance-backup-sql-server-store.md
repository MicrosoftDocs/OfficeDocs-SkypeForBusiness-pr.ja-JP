---
title: 常設チャット コンプライアンス バックアップ SQL Server ストアの追加
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatBackupComplianceStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 358b74bd-a97d-4f28-9bed-af633ea0099e
description: 永続的なチャット サーバーのデータベースのバックアップを提供するように SQL Server に格納されてバックアップ コンプライアンスまたは SQL Server に格納する永続的なチャット サーバー コンプライアンスを構成するとします。
ms.openlocfilehash: 031a47974624a60f2732df1535d23d392d16b74d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33897633"
---
# <a name="add-persistent-chat-compliance-backup-sql-server-store"></a><span data-ttu-id="03663-103">常設チャット コンプライアンス バックアップ SQL Server ストアの追加</span><span class="sxs-lookup"><span data-stu-id="03663-103">Add Persistent Chat Compliance Backup SQL Server Store</span></span>
 
<span data-ttu-id="03663-104">永続的なチャット サーバーのデータベースのバックアップを提供するように SQL Server に格納されてバックアップ コンプライアンスまたは SQL Server に格納する永続的なチャット サーバー コンプライアンスを構成するとします。</span><span class="sxs-lookup"><span data-stu-id="03663-104">You configure the Backup compliance SQL Server stores that will provide backup databases for the Persistent Chat Server or Persistent Chat Server compliance SQL Server stores.</span></span>
  
 <span data-ttu-id="03663-105">**SQL Server に格納**します。 永続的なチャットの既存の SQL Server およびインスタンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="03663-105">**SQL Server store**: Select an existing SQL Server and optionally an instance for Persistent Chat.</span></span>
  
<span data-ttu-id="03663-106">新しい SQL Server と、オプションで永続的なチャットのコンプライアンスのバックアップ ・ データの新しいインスタンスを定義するのには**新規**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="03663-106">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat backup compliance data.</span></span>
  
<span data-ttu-id="03663-107">SQL Server データベースおよび永続的なチャットのコンプライアンスのバックアップ ・ データのミラー化されたデータベースを提供する省略可能なインスタンスを構成する**SQL Server を有効にするストアがミラー化**のチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="03663-107">Select the **Enable SQL Server store mirroring** checkbox to configure a SQL Server database and optional instance that will provide a mirrored database for the Persistent Chat backup compliance data.</span></span>
  
<span data-ttu-id="03663-108">永続的なチャットのバックアップ コンプライアンス SQL Server の SQL Server ミラーとして動作するには、SQL Server と省略可能なインスタンスを**SQL Server のミラーを格納**するリストから選択します。</span><span class="sxs-lookup"><span data-stu-id="03663-108">Select from the list **Mirroring SQL Server store** a SQL Server and optional instance to act as the SQL Server mirror for the Persistent Chat backup compliance SQL Server.</span></span>
  
<span data-ttu-id="03663-109">新しい SQL Server と、オプションで永続的なチャットの SQL Server のミラーリング用の新しいインスタンスを定義するのには**新規**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="03663-109">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat SQL Server mirroring.</span></span>
  
<span data-ttu-id="03663-110">[**SQL Server ミラーリング監視を自動フェールオーバーの有効化のために使用**] の一覧で、フェールオーバーのシナリオにおいて監視サーバーとして機能する SQL Server を選択します。</span><span class="sxs-lookup"><span data-stu-id="03663-110">Select the list **Use SQL Server mirroring witness to enable automatic failover** a SQL Server that will act as the witness server in failover scenarios.</span></span> <span data-ttu-id="03663-111">ミラーリング監視サーバーはミラーまたはホストのデータは、永続的なチャット サーバーですが、により、ミラー化構成で SQL Server を 1 つだけアクティブな SQL Server の任意の時点。</span><span class="sxs-lookup"><span data-stu-id="03663-111">The witness server does not mirror or host data for the Persistent Chat servers, but ensures that only one SQL Server in a mirrored configuration is the active SQL Server at any time.</span></span>
  
<span data-ttu-id="03663-112">必要に応じて永続的なチャットのバックアップ コンプライアンス ミラーリング監視を SQL Server のインスタンスの新しい SQL Server のミラーリング監視サーバーを定義するのには**新規**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="03663-112">Click **New** to define a new SQL Server witness optionally an instance for the Persistent Chat backup compliance SQL Server mirroring witness.</span></span>
  
<span data-ttu-id="03663-113">前のプール定義ダイアログに戻るには、[**戻る**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="03663-113">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="03663-114">このプールのバックアップ SQL Server ストア構成の永続的なチャット サーバー プールの定義を続行するオプションの入力が終了したら**次へ**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="03663-114">Click **Next** after you have finished entering the options for this pool's backup SQL Server store configuration and to proceed with the Persistent Chat Server pool definition.</span></span>
  
<span data-ttu-id="03663-115">すべての変更を破棄して**新しい常設チャット プールの定義**ウィザードを終了するには、[**キャンセル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="03663-115">Click **Cancel** to discard all changes and end the **Define New Persistent Chat Pool** wizard.</span></span>
  
<span data-ttu-id="03663-116">このページのような状況依存のヘルプにアクセスするには、[**ヘルプ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="03663-116">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="03663-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="03663-117">See also</span></span>

[<span data-ttu-id="03663-118">Skype for Business Server 2015 の常設チャット サーバーの計画</span><span class="sxs-lookup"><span data-stu-id="03663-118">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="03663-119">Server requirements for Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="03663-119">Server requirements for Skype for Business Server 2015</span></span>](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[<span data-ttu-id="03663-120">Skype for Business Server 2015 の常設チャット サーバーのハードウェアおよびソフトウェア要件</span><span class="sxs-lookup"><span data-stu-id="03663-120">Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[<span data-ttu-id="03663-121">Skype for Business Server 2015 での常設チャット サーバーのコンプライアンス サービスの構成</span><span class="sxs-lookup"><span data-stu-id="03663-121">Configure the Compliance service for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../manage/persistent-chat/configure-compliance.md)
  
[<span data-ttu-id="03663-122">Skype for Business Server 2015 での常設チャット サーバーの高可用性および障害復旧の構成</span><span class="sxs-lookup"><span data-stu-id="03663-122">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
