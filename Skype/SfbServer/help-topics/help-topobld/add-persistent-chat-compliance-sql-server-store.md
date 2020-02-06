---
title: 常設チャット コンプライアンス SQL Server ストアの追加
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.AddPersistentChatComplianceStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b9771b53-e19a-4a12-bf01-24bae6f7e482
description: 常設チャットサーバーまたは常設チャットサーバーのコンプライアンス機能のデータベースを提供するコンプライアンス SQL Server ストアを構成します。
ms.openlocfilehash: fd51b3d582c915d02799f2f633869e84f3659c4f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820689"
---
# <a name="add-persistent-chat-compliance-sql-server-store"></a><span data-ttu-id="ac576-103">常設チャット コンプライアンス SQL Server ストアの追加</span><span class="sxs-lookup"><span data-stu-id="ac576-103">Add Persistent Chat Compliance SQL Server Store</span></span>
 
<span data-ttu-id="ac576-104">常設チャットサーバーまたは常設チャットサーバーのコンプライアンス機能のデータベースを提供するコンプライアンス SQL Server ストアを構成します。</span><span class="sxs-lookup"><span data-stu-id="ac576-104">You configure the compliance SQL Server stores that will provide databases for the Persistent Chat Server or Persistent Chat Server compliance feature.</span></span>
  
 <span data-ttu-id="ac576-105">**Sql server ストア**: 既存の sql server を選択し、必要に応じて常設チャットのインスタンスも選択します。</span><span class="sxs-lookup"><span data-stu-id="ac576-105">**SQL Server store**: Select an existing SQL Server and optionally an instance for Persistent Chat.</span></span>
  
<span data-ttu-id="ac576-106">[**新規**] をクリックして、新しい SQL Server を定義し、必要に応じて、常設チャットのコンプライアンスデータ用の新しいインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="ac576-106">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat compliance data.</span></span>
  
<span data-ttu-id="ac576-107">[ **Sql server ストアのミラーリングを有効**にする] チェックボックスをオンにして、sql server データベースと、常設チャットのコンプライアンスデータのミラーリングされたデータベースを提供するオプションのインスタンスを構成します。</span><span class="sxs-lookup"><span data-stu-id="ac576-107">Select the **Enable SQL Server store mirroring** checkbox to configure a SQL Server database and optional instance that will provide a mirrored database for the Persistent Chat compliance data.</span></span>
  
<span data-ttu-id="ac576-108">リストの**ミラーリング Sql server ストア**から選択します。 sql server とオプションのインスタンスは、常設チャットのコンプライアンス sql SERVER の sql server ミラーとして機能します。</span><span class="sxs-lookup"><span data-stu-id="ac576-108">Select from the list **Mirroring SQL Server store** a SQL Server and optional instance to act as the SQL Server mirror for the Persistent Chat compliance SQL Server.</span></span>
  
<span data-ttu-id="ac576-109">[**新規**] をクリックして、新しい sql server を定義し、必要に応じて、常設チャットの sql server ミラーリング用の新しいインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="ac576-109">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat SQL Server mirroring.</span></span>
  
<span data-ttu-id="ac576-110">[**SQL Server ミラーリング監視を自動フェールオーバーの有効化のために使用**] の一覧で、フェールオーバーのシナリオにおいて監視サーバーとして機能する SQL Server を選択します。</span><span class="sxs-lookup"><span data-stu-id="ac576-110">Select the list **Use SQL Server mirroring witness to enable automatic failover** a SQL Server that will act as the witness server in failover scenarios.</span></span> <span data-ttu-id="ac576-111">監視サーバーは、常設チャットサーバーのデータをミラーリングまたはホストしませんが、ミラー化された構成内の1つの SQL Server のみがアクティブな SQL Server であることを常に確認します。</span><span class="sxs-lookup"><span data-stu-id="ac576-111">The witness server does not mirror or host data for the Persistent Chat servers, but ensures that only one SQL Server in a mirrored configuration is the active SQL Server at any time.</span></span>
  
<span data-ttu-id="ac576-112">[**新規**] をクリックして、新しい sql server の監視を定義します。必要に応じて、永続的なチャット準拠の SQL server ミラーリング監視用のインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="ac576-112">Click **New** to define a new SQL Server witness optionally an instance for the Persistent Chat compliance SQL Server mirroring witness.</span></span>
  
<span data-ttu-id="ac576-113">前のプール定義ダイアログに戻るには、[**戻る**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac576-113">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="ac576-114">このプールの backup SQL Server ストア構成のオプションを入力して、常設チャットサーバープールの定義を続行するには、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac576-114">Click **Next** after you have finished entering the options for this pool's backup SQL Server store configuration and to proceed with the Persistent Chat Server pool definition.</span></span>
  
<span data-ttu-id="ac576-115">すべての変更を破棄して**新しい常設チャット プールの定義**ウィザードを終了するには、[**キャンセル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac576-115">Click **Cancel** to discard all changes and end the **Define New Persistent Chat Pool** wizard.</span></span>
  
<span data-ttu-id="ac576-116">このページのような状況依存のヘルプにアクセスするには、[**ヘルプ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac576-116">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ac576-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="ac576-117">See also</span></span>

[<span data-ttu-id="ac576-118">Skype for Business Server 2015 の常設チャット サーバーの計画</span><span class="sxs-lookup"><span data-stu-id="ac576-118">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="ac576-119">Server requirements for Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="ac576-119">Server requirements for Skype for Business Server 2015</span></span>](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[<span data-ttu-id="ac576-120">Skype for Business Server 2015 の常設チャット サーバーのハードウェアおよびソフトウェア要件</span><span class="sxs-lookup"><span data-stu-id="ac576-120">Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[<span data-ttu-id="ac576-121">Skype for Business Server 2015 での常設チャット サーバーのコンプライアンス サービスの構成</span><span class="sxs-lookup"><span data-stu-id="ac576-121">Configure the Compliance service for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../manage/persistent-chat/configure-compliance.md)
