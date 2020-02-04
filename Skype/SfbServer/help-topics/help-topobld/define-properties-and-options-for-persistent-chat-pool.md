---
title: 常設チャット プールのプロパティとオプションの定義
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddPersistentChatOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f4914a44-2113-48f1-8299-4645fc7011b6
description: 常設チャットサーバープールまたは常設チャットサーバープールのオプションを構成するには、次のプロパティを定義します。
ms.openlocfilehash: 458e50ecc3ddd389a8e413e8f2dd368fc0f15369
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2020
ms.locfileid: "41697552"
---
# <a name="define-properties-and-options-for-persistent-chat-pool"></a><span data-ttu-id="d4d36-103">常設チャット プールのプロパティとオプションの定義</span><span class="sxs-lookup"><span data-stu-id="d4d36-103">Define Properties and Options for Persistent Chat Pool</span></span>
 
<span data-ttu-id="d4d36-104">常設チャットサーバープールまたは常設チャットサーバープールのオプションを構成するには、次のプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="d4d36-104">You configure options for your Persistent Chat Server or Persistent Chat Server pool by defining the following properties:</span></span>
  
 <span data-ttu-id="d4d36-105">**常設チャットプールの表示名**: この常設チャットサーバーまたは常設チャットサーバープールに表示されるユーザーフレンドリ名を定義する必須プロパティ。</span><span class="sxs-lookup"><span data-stu-id="d4d36-105">**Display name of the Persistent Chat pool**: A required property that defines a user friendly name that will be displayed for this Persistent Chat Server or Persistent Chat Server pool.</span></span>
  
 <span data-ttu-id="d4d36-106">[**常設チャットポート**: 常設チャットサーバーまたは常設チャットサーバープールがリッスンするポート番号を定義する必須プロパティ。</span><span class="sxs-lookup"><span data-stu-id="d4d36-106">**Persistent Chat port**: A required property that will define the port number that this Persistent Chat Server or Persistent Chat Server pool will listen on.</span></span>
  
 <span data-ttu-id="d4d36-107">**コンプライアンスを有効**にする: オプションの常設チャットのコンプライアンス機能とデータベースを展開して実装する場合は、このチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="d4d36-107">**Enable compliance**: Select the check box if you plan to deploy and implement the optional Persistent Chat compliance feature and database.</span></span>
  
 <span data-ttu-id="d4d36-108">[ **Sql Server ストアのバックアップ] を使って、障害回復を有効**にする: 別の sql server 上に構成されているストアのバックアップセットから、常設チャットの SQL Server ストアの障害回復を展開して実装する場合は、このチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="d4d36-108">**Use backup SQL Server stores to enable disaster recovery**: Select this check box if you plan to deploy and implement disaster recovery of the Persistent Chat SQL Server stores from a configured backup set of stores on another SQL Server.</span></span> <span data-ttu-id="d4d36-109">詳細については、「 [Skype For Business server 2015 の常設チャットサーバー用に高可用性と障害回復を構成する](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d4d36-109">For details, see [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="d4d36-110">このオプションは、複数のサーバーで構成されたプールに対してのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="d4d36-110">This option is available only for pools with multiple servers.</span></span> 
  
 <span data-ttu-id="d4d36-111">この**プールは、このサーバーまたは\<プールを構成\>するサイトサイトの既定のプールとして使用**します。これが、サイトの既定の常設チャットサーバーまたは常設チャットサーバープールになる場合は、このチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="d4d36-111">**Use this pool as default for the site \<site that this server or pool is being configured in\>**: Select this check box if this will be the default Persistent Chat Server or Persistent Chat Server pool for the site.</span></span> <span data-ttu-id="d4d36-112">既定の常設チャットサーバーまたは、サイトごとに1つの既定の常設が必要です。</span><span class="sxs-lookup"><span data-stu-id="d4d36-112">You must have one default Persistent Chat server or pol per site.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d4d36-113">トポロジに複数のサイトが含まれる場合は、[**このプールをすべてのサイトの既定プールとして使う**] チェック ボックスも表示されます。</span><span class="sxs-lookup"><span data-stu-id="d4d36-113">If your topology includes multiple sites, a checkbox for **Use this pool as default for all sites** is also displayed.</span></span>
  
<span data-ttu-id="d4d36-114">前のプール定義ダイアログに戻るには、[**戻る**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d4d36-114">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="d4d36-115">このプールのオプションの入力が完了したら、[**次へ**] をクリックして、常設チャットサーバープールの定義を続行します。</span><span class="sxs-lookup"><span data-stu-id="d4d36-115">Click **Next** after you have finished entering the options for this pool to proceed with the Persistent Chat Server pool definition.</span></span>
  
<span data-ttu-id="d4d36-116">すべての変更を破棄して**新しい常設チャット プールの定義**ウィザードを終了するには、[**キャンセル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d4d36-116">Click **Cancel** to discard all changes and end the **Define New Persistent Chat Pool** wizard.</span></span>
  
<span data-ttu-id="d4d36-117">このページのような状況依存のヘルプにアクセスするには、[**ヘルプ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d4d36-117">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d4d36-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="d4d36-118">See also</span></span>

[<span data-ttu-id="d4d36-119">Skype for Business Server 2015 の常設チャット サーバーの計画</span><span class="sxs-lookup"><span data-stu-id="d4d36-119">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="d4d36-120">Skype for Business Server 2015 トポロジに常設チャットサーバーを追加する</span><span class="sxs-lookup"><span data-stu-id="d4d36-120">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
