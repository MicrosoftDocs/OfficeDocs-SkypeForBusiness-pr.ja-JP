---
title: 常設チャット プールのプロパティとオプションの定義
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
- ms.lync.tb.AddPersistentChatOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f4914a44-2113-48f1-8299-4645fc7011b6
description: 常設チャット サーバーまたは常設チャット サーバー プールのオプションを構成するには、次のプロパティを定義します。
ms.openlocfilehash: acc80c76e79364be730ec56a2b64e5dcd001f661
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49818427"
---
# <a name="define-properties-and-options-for-persistent-chat-pool"></a><span data-ttu-id="d1fa8-103">常設チャット プールのプロパティとオプションの定義</span><span class="sxs-lookup"><span data-stu-id="d1fa8-103">Define Properties and Options for Persistent Chat Pool</span></span>
 
<span data-ttu-id="d1fa8-104">常設チャット サーバーまたは常設チャット サーバー プールのオプションを構成するには、次のプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="d1fa8-104">You configure options for your Persistent Chat Server or Persistent Chat Server pool by defining the following properties:</span></span>
  
 <span data-ttu-id="d1fa8-105">**常設チャット プールの** 表示名 : この常設チャット サーバーまたは常設チャット サーバー プールに対して表示されるユーザー フレンドリーな名前を定義する必須のプロパティ。</span><span class="sxs-lookup"><span data-stu-id="d1fa8-105">**Display name of the Persistent Chat pool**: A required property that defines a user friendly name that will be displayed for this Persistent Chat Server or Persistent Chat Server pool.</span></span>
  
 <span data-ttu-id="d1fa8-106">**常設チャット ポート**: この常設チャット サーバーまたは常設チャット サーバー プールがリッスンするポート番号を定義する必須のプロパティです。</span><span class="sxs-lookup"><span data-stu-id="d1fa8-106">**Persistent Chat port**: A required property that will define the port number that this Persistent Chat Server or Persistent Chat Server pool will listen on.</span></span>
  
 <span data-ttu-id="d1fa8-107">**コンプライアンスの有効化**: オプションの常設チャット コンプライアンス機能とデータベースを展開して実装する場合は、このチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="d1fa8-107">**Enable compliance**: Select the check box if you plan to deploy and implement the optional Persistent Chat compliance feature and database.</span></span>
  
 <span data-ttu-id="d1fa8-108">**障害復旧を有効にするには**、バックアップ SQL Server ストアを使用します。別の SQL Server 上の構成済みのストア セットから常設チャット SQL Server ストアの障害復旧を展開および実装する場合は、このチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="d1fa8-108">**Use backup SQL Server stores to enable disaster recovery**: Select this check box if you plan to deploy and implement disaster recovery of the Persistent Chat SQL Server stores from a configured backup set of stores on another SQL Server.</span></span> <span data-ttu-id="d1fa8-109">詳細については [、「Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015」を参照](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)してください。</span><span class="sxs-lookup"><span data-stu-id="d1fa8-109">For details, see [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="d1fa8-110">このオプションは、複数のサーバーを持つプールでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="d1fa8-110">This option is available only for pools with multiple servers.</span></span> 
  
 <span data-ttu-id="d1fa8-111">**サイトの既定として \<site that this server or pool is being configured in\>** このプールを使用する: これがサイトの既定の常設チャット サーバーまたは常設チャット サーバー プールになる場合は、このチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="d1fa8-111">**Use this pool as default for the site \<site that this server or pool is being configured in\>**: Select this check box if this will be the default Persistent Chat Server or Persistent Chat Server pool for the site.</span></span> <span data-ttu-id="d1fa8-112">サイトごとに既定の常設チャット サーバーまたはプールが 1 つ必要です。</span><span class="sxs-lookup"><span data-stu-id="d1fa8-112">You must have one default Persistent Chat server or pol per site.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d1fa8-113">トポロジに複数のサイトが含まれる場合は、[このプールをすべてのサイトの既定として使用する] チェック ボックス **も** 表示されます。</span><span class="sxs-lookup"><span data-stu-id="d1fa8-113">If your topology includes multiple sites, a checkbox for **Use this pool as default for all sites** is also displayed.</span></span>
  
<span data-ttu-id="d1fa8-114">前のプール定義ダイアログに戻るには、[**戻る**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d1fa8-114">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="d1fa8-115">この **プール** のオプションの入力が完了したら、[次へ] をクリックして、常設チャット サーバー プールの定義を続行します。</span><span class="sxs-lookup"><span data-stu-id="d1fa8-115">Click **Next** after you have finished entering the options for this pool to proceed with the Persistent Chat Server pool definition.</span></span>
  
<span data-ttu-id="d1fa8-116">すべての変更を破棄して **新しい常設チャット プールの定義** ウィザードを終了するには、[**キャンセル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d1fa8-116">Click **Cancel** to discard all changes and end the **Define New Persistent Chat Pool** wizard.</span></span>
  
<span data-ttu-id="d1fa8-117">このページのような状況依存のヘルプにアクセスするには、[**ヘルプ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d1fa8-117">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d1fa8-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="d1fa8-118">See also</span></span>

[<span data-ttu-id="d1fa8-119">Skype for Business Server 2015 での常設チャット サーバーの計画</span><span class="sxs-lookup"><span data-stu-id="d1fa8-119">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="d1fa8-120">Skype for Business Server 2015 トポロジへの常設チャット サーバーの追加</span><span class="sxs-lookup"><span data-stu-id="d1fa8-120">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
