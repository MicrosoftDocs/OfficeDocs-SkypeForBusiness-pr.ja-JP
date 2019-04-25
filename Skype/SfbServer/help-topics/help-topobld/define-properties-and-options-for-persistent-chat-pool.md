---
title: 常設チャット プールのプロパティとオプションの定義
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f4914a44-2113-48f1-8299-4645fc7011b6
description: 永続的なチャット サーバーまたは永続的なチャット サーバー プールのオプションを構成するには、次のプロパティを定義します。
ms.openlocfilehash: 380a1e34e041368d4520cd5c8ecea5b18284ef51
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32226922"
---
# <a name="define-properties-and-options-for-persistent-chat-pool"></a><span data-ttu-id="b77a5-103">常設チャット プールのプロパティとオプションの定義</span><span class="sxs-lookup"><span data-stu-id="b77a5-103">Define Properties and Options for Persistent Chat Pool</span></span>
 
<span data-ttu-id="b77a5-104">永続的なチャット サーバーまたは永続的なチャット サーバー プールのオプションを構成するには、次のプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="b77a5-104">You configure options for your Persistent Chat Server or Persistent Chat Server pool by defining the following properties:</span></span>
  
 <span data-ttu-id="b77a5-105">**永続的なチャット プールの表示名**: この永続的なチャット サーバーまたは永続的なチャット サーバー プールに表示されるユーザー フレンドリ名を定義する必要なプロパティです。</span><span class="sxs-lookup"><span data-stu-id="b77a5-105">**Display name of the Persistent Chat pool**: A required property that defines a user friendly name that will be displayed for this Persistent Chat Server or Persistent Chat Server pool.</span></span>
  
 <span data-ttu-id="b77a5-106">**永続的なチャットのポート**: ポートを定義する必要なプロパティ番号を永続的なチャット サーバーまたはプールの永続的なチャット サーバー上でリッスンします。</span><span class="sxs-lookup"><span data-stu-id="b77a5-106">**Persistent Chat port**: A required property that will define the port number that this Persistent Chat Server or Persistent Chat Server pool will listen on.</span></span>
  
 <span data-ttu-id="b77a5-107">**コンプライアンスを有効にする**: の導入し、省略可能な永続的なチャットのコンプライアンス機能とデータベースを実装する場合はチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="b77a5-107">**Enable compliance**: Select the check box if you plan to deploy and implement the optional Persistent Chat compliance feature and database.</span></span>
  
 <span data-ttu-id="b77a5-108">**災害復旧を有効にする SQL Server のバックアップの使用を格納**します。 から別の SQL Server 上のストアの構成のバックアップ セットを展開し、永続的なチャットの SQL Server の災害復旧を実装する場合、このチェック ボックスを保存] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b77a5-108">**Use backup SQL Server stores to enable disaster recovery**: Select this check box if you plan to deploy and implement disaster recovery of the Persistent Chat SQL Server stores from a configured backup set of stores on another SQL Server.</span></span> <span data-ttu-id="b77a5-109">詳細については、[構成の高可用性とビジネス サーバー 2015 の Skype での永続的なチャット サーバーの障害回復](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b77a5-109">For details, see [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="b77a5-110">このオプションは、複数のサーバーで構成されたプールに対してのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="b77a5-110">This option is available only for pools with multiple servers.</span></span> 
  
 <span data-ttu-id="b77a5-111">**サイトの既定値としてこのプールを使用して\<では、このサーバーまたはプールを構成しているサイト\>**: このチェック ボックスをオンに、既定の永続的なチャット サーバーまたはサイトの永続的なチャット サーバー プールになります。</span><span class="sxs-lookup"><span data-stu-id="b77a5-111">**Use this pool as default for the site \<site that this server or pool is being configured in\>**: Select this check box if this will be the default Persistent Chat Server or Persistent Chat Server pool for the site.</span></span> <span data-ttu-id="b77a5-112">サイトごと、1 つの既定の永続的なチャット サーバーまたは pol をすることが必要です。</span><span class="sxs-lookup"><span data-stu-id="b77a5-112">You must have one default Persistent Chat server or pol per site.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b77a5-113">トポロジに複数のサイトが含まれる場合は、[**このプールをすべてのサイトの既定プールとして使う**] チェック ボックスも表示されます。</span><span class="sxs-lookup"><span data-stu-id="b77a5-113">If your topology includes multiple sites, a checkbox for **Use this pool as default for all sites** is also displayed.</span></span>
  
<span data-ttu-id="b77a5-114">前のプール定義ダイアログに戻るには、[**戻る**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b77a5-114">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="b77a5-115">永続的なチャット サーバー プールの定義を続行するには、このプールのオプションの入力が終了したら**次へ**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b77a5-115">Click **Next** after you have finished entering the options for this pool to proceed with the Persistent Chat Server pool definition.</span></span>
  
<span data-ttu-id="b77a5-116">すべての変更を破棄して**新しい常設チャット プールの定義**ウィザードを終了するには、[**キャンセル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b77a5-116">Click **Cancel** to discard all changes and end the **Define New Persistent Chat Pool** wizard.</span></span>
  
<span data-ttu-id="b77a5-117">このページのような状況依存のヘルプにアクセスするには、[**ヘルプ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b77a5-117">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b77a5-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="b77a5-118">See also</span></span>

[<span data-ttu-id="b77a5-119">Skype for Business Server 2015 の常設チャット サーバーの計画</span><span class="sxs-lookup"><span data-stu-id="b77a5-119">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="b77a5-120">ビジネス サーバー 2015 トポロジの場合、Skype に永続的なチャット サーバーを追加します。</span><span class="sxs-lookup"><span data-stu-id="b77a5-120">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
