---
title: 仲介サーバーの全般設定エキスパンダー
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.MediationServerGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0e0ad9f0-27d5-4975-ae88-0b8ff8a4c514
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 364e76befd6d259428ea2ae8d580c774e06d210a
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2020
ms.locfileid: "41701912"
---
# <a name="mediation-server-general-settings-expander"></a><span data-ttu-id="6fdc4-102">仲介サーバーの全般設定エキスパンダー</span><span class="sxs-lookup"><span data-stu-id="6fdc4-102">Mediation Server General Settings Expander</span></span>
 


## <a name="general-settings"></a><span data-ttu-id="6fdc4-103">全般設定</span><span class="sxs-lookup"><span data-stu-id="6fdc4-103">General settings</span></span>

<span data-ttu-id="6fdc4-104">仲介サーバープールまたは仲介サーバーの完全修飾ドメイン名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="6fdc4-104">Fully qualified domain name (FQDN) of the Mediation Server pool or Mediation Server.</span></span> <span data-ttu-id="6fdc4-105">値を変更するには、サーバーの FQDN を編集します。</span><span class="sxs-lookup"><span data-stu-id="6fdc4-105">Edit the FQDN of the server to change the value.</span></span> <span data-ttu-id="6fdc4-106">新しい値と一致しているドメイン ネーム システム (DNS) ホスト (A) レコードがある必要があります。</span><span class="sxs-lookup"><span data-stu-id="6fdc4-106">You must have a Domain Name System (DNS) host (A) record that coincides with the new value.</span></span>
  
<span data-ttu-id="6fdc4-107">[**関連付け**] セクションで、仲介サーバープールまたは仲介サーバーに関連付けるエッジサーバーまたはエッジサーバープールを選択します。</span><span class="sxs-lookup"><span data-stu-id="6fdc4-107">In the **Associations** section, you select an Edge Server or Edge Server pool to associate with the Mediation Server pool or Mediation Server.</span></span> <span data-ttu-id="6fdc4-108">仲介サーバーのメディアコンポーネントで外部ユーザーのエンタープライズ Voip に使用されるエッジを選択します。</span><span class="sxs-lookup"><span data-stu-id="6fdc4-108">You select the Edge that the Mediation Server's media components will use for External user Enterprise Voice.</span></span>
  
<span data-ttu-id="6fdc4-109">現在定義されている Edge サーバーがなく、仲介サーバーとエッジサーバーを関連付ける必要がある場合は、[**新規**作成] をクリックし、[新しいエッジプールの定義] ウィザードで新しいエッジサーバーまたはエッジサーバープールを定義します。</span><span class="sxs-lookup"><span data-stu-id="6fdc4-109">If you do not have an Edge Server currently defined and need to associate the Mediation Server with an Edge Server, click **New** and define the new Edge Server or Edge Server pool in the Define the New Edge pool wizard.</span></span>
  
## <a name="next-hop-settings"></a><span data-ttu-id="6fdc4-110">次ホップ設定</span><span class="sxs-lookup"><span data-stu-id="6fdc4-110">Next hop settings</span></span>

<span data-ttu-id="6fdc4-111">定義済みの Enterprise Edition のフロントエンドプールまたは標準エディションのフロントエンドサーバーをドロップダウンリストから選ぶことにより、仲介サーバープールまたは仲介サーバーの次ホップを指定します。</span><span class="sxs-lookup"><span data-stu-id="6fdc4-111">You specify the Mediation Server pool or Mediation Server next hop by selecting the defined Enterprise Edition Front End pool or Standard Edition Front End Server from the drop-down list.</span></span> <span data-ttu-id="6fdc4-112">ディレクターまたはディレクタープールが、仲介サーバープールまたは仲介サーバーの次ホップの有効な選択ではないため、一覧に表示されません。</span><span class="sxs-lookup"><span data-stu-id="6fdc4-112">A Director or Director pool is not a valid selection for a Mediation Server pool or Mediation Server next hop, and will not appear in the list.</span></span> <span data-ttu-id="6fdc4-113">[ **OK]** をクリックして、変更を承諾して保存します。</span><span class="sxs-lookup"><span data-stu-id="6fdc4-113">Click **OK** to accept and save your changes.</span></span> <span data-ttu-id="6fdc4-114">変更を破棄してプロパティ ページを終了するには、[**キャンセル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6fdc4-114">Click **Cancel** to discard your changes and exit the properties page.</span></span>
  
## <a name="pstn-gateway-settings"></a><span data-ttu-id="6fdc4-115">PSTN ゲートウェイの設定</span><span class="sxs-lookup"><span data-stu-id="6fdc4-115">PSTN gateway settings</span></span>

1. <span data-ttu-id="6fdc4-116">仲介サーバープールまたは仲介サーバーに関連付けられている PSTN ゲートウェイを定義します。</span><span class="sxs-lookup"><span data-stu-id="6fdc4-116">You define PSTN gateways that are associated with the Mediation Server pool or Mediation Server.</span></span> <span data-ttu-id="6fdc4-117">既にゲートウェイが定義されている場合は、それらを仲介サーバーと関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="6fdc4-117">If you have already defined gateways, they will be available to associate with the Mediation Server.</span></span> <span data-ttu-id="6fdc4-118">仲介サーバーの collocation を有効にした場合、トランスポート層セキュリティ (TLS) のプールサーバーでリッスンポートの範囲を定義します。</span><span class="sxs-lookup"><span data-stu-id="6fdc4-118">If you enable the collocation of the Mediation Server, define the listening port range on the pool servers for Transport Layer Security (TLS).</span></span> <span data-ttu-id="6fdc4-119">既定では、このポートは5067です。</span><span class="sxs-lookup"><span data-stu-id="6fdc4-119">By default, this port is 5067.</span></span> <span data-ttu-id="6fdc4-120">[ **Tcp ポートを有効に**する] を選択した場合、併置された仲介サーバーに対して伝送制御プロトコル (TCP) ポートを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6fdc4-120">If you select **Enable TCP port**, you must define a Transmission Control Protocol (TCP) port for the collocated Mediation Server.</span></span> <span data-ttu-id="6fdc4-121">これはオプションの設定であり、必要に応じてゲートウェイまたは PSTN の要件を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6fdc4-121">This is an optional setting, and you should refer to the requirements of your gateway or PSTN requirements to determine if you need this.</span></span> <span data-ttu-id="6fdc4-122">既定では、[TCP ポート] の値は5068です。</span><span class="sxs-lookup"><span data-stu-id="6fdc4-122">By default, the TCP port value is 5068.</span></span>
    
2. <span data-ttu-id="6fdc4-p105">併置された仲介サーバーに関連付けるトランク。トランクを既に定義している場合は、それらを仲介サーバーに関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="6fdc4-p105">Trunks that are associated with the collocated Mediation Server. If you have already defined trunks, they will be available to associate with the Mediation Server.</span></span> 
    
3. <span data-ttu-id="6fdc4-125">仲介サーバーと関連付けられているトランクが複数ある場合は、トランクを選択して「**デフォルト**に設定」をクリックすると、デフォルトのトランクを指定できます。</span><span class="sxs-lookup"><span data-stu-id="6fdc4-125">If you have more than one trunk associated with a Mediation Server, you can specify a default trunk by selecting the trunk and then clicking **Make Default**.</span></span> <span data-ttu-id="6fdc4-126">既定のゲートウェイとしての選択を解除するには、[**既定値の解除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6fdc4-126">To unselect a gateway as the default, click **Unmake Default**.</span></span> 
    

