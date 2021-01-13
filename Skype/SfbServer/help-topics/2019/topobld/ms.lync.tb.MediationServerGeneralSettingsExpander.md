---
title: 仲介サーバーの全般設定の展開
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.MediationServerGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0e0ad9f0-27d5-4975-ae88-0b8ff8a4c514
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: a78fa8c12f2eb0db4cedd97a765e6445788c3382
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804267"
---
# <a name="mediation-server-general-settings-expander"></a><span data-ttu-id="69916-102">仲介サーバー全般設定エキスパンダー</span><span class="sxs-lookup"><span data-stu-id="69916-102">Mediation Server General Settings Expander</span></span>
 


## <a name="general-settings"></a><span data-ttu-id="69916-103">全般設定</span><span class="sxs-lookup"><span data-stu-id="69916-103">General settings</span></span>

<span data-ttu-id="69916-p101">仲介サーバー プールまたは仲介サーバーの完全修飾ドメイン名 (FQDN)。値を変更するには、サーバーの FQDN を編集します。新しい値と一致しているドメイン ネーム システム (DNS) ホスト (A) レコードがある必要があります。</span><span class="sxs-lookup"><span data-stu-id="69916-p101">Fully qualified domain name (FQDN) of the Mediation Server pool or Mediation Server. Edit the FQDN of the server to change the value. You must have a Domain Name System (DNS) host (A) record that coincides with the new value.</span></span>
  
<span data-ttu-id="69916-107">**[関連付け]** で、仲介サーバー プールまたは仲介サーバーに関連付けるエッジ サーバーまたはエッジ サーバー プールを選択します。</span><span class="sxs-lookup"><span data-stu-id="69916-107">In the **Associations** section, you select an Edge Server or Edge Server pool to associate with the Mediation Server pool or Mediation Server.</span></span> <span data-ttu-id="69916-108">仲介サーバーのメディア コンポーネントが外部ユーザー インターフェイスに使用するエッジを選択エンタープライズ VoIP。</span><span class="sxs-lookup"><span data-stu-id="69916-108">You select the Edge that the Mediation Server's media components will use for External user Enterprise Voice.</span></span>
  
<span data-ttu-id="69916-109">現在エッジ サーバーを定義しておらず、仲介サーバーをエッジ サーバーに関連付ける必要がある場合、**[新規]** をクリックし、新しいエッジ プールの定義ウィザードで新しいエッジ サーバーまたはエッジ サーバー プールを定義します。</span><span class="sxs-lookup"><span data-stu-id="69916-109">If you do not have an Edge Server currently defined and need to associate the Mediation Server with an Edge Server, click **New** and define the new Edge Server or Edge Server pool in the Define the New Edge pool wizard.</span></span>
  
## <a name="next-hop-settings"></a><span data-ttu-id="69916-110">次ホップ設定</span><span class="sxs-lookup"><span data-stu-id="69916-110">Next hop settings</span></span>

<span data-ttu-id="69916-111">ドロップダウン リストから定義済みの Enterprise Edition フロント エンド プールまたは Standard Edition フロント エンド サーバーを選択して、仲介サーバー プールまたは仲介サーバーの次ホップを指定します。</span><span class="sxs-lookup"><span data-stu-id="69916-111">You specify the Mediation Server pool or Mediation Server next hop by selecting the defined Enterprise Edition Front End pool or Standard Edition Front End Server from the drop-down list.</span></span> <span data-ttu-id="69916-112">ディレクターまたはディレクター プールは仲介サーバー プールまたは仲介サーバー次ホップの有効な選択肢ではないため、一覧には表示されません。</span><span class="sxs-lookup"><span data-stu-id="69916-112">A Director or Director pool is not a valid selection for a Mediation Server pool or Mediation Server next hop, and will not appear in the list.</span></span> <span data-ttu-id="69916-113">**[OK] を** クリックして変更を受け入れて保存します。</span><span class="sxs-lookup"><span data-stu-id="69916-113">Click **OK** to accept and save your changes.</span></span> <span data-ttu-id="69916-114">変更を破棄してプロパティ ページを終了するには、**[キャンセル]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="69916-114">Click **Cancel** to discard your changes and exit the properties page.</span></span>
  
## <a name="pstn-gateway-settings"></a><span data-ttu-id="69916-115">PSTN ゲートウェイの設定</span><span class="sxs-lookup"><span data-stu-id="69916-115">PSTN gateway settings</span></span>

1. <span data-ttu-id="69916-p104">仲介サーバー プールまたは仲介サーバーに関連付ける PSTN ゲートウェイを定義します。ゲートウェイを既に定義している場合は、それらのゲートウェイを仲介サーバーに関連付けることができます。仲介サーバーの併置を有効にする場合は、プール サーバーでのトランスポート層セキュリティ (TLS) のリッスン ポートの範囲を定義します。既定のポートは 5067 です。[**TCP ポートの有効化**] を選択する場合は、併置する仲介サーバーの伝送制御プロトコル (TCP) ポートを定義する必要があります。これは省略可能な設定です。この設定が必要かどうかは、ゲートウェイまたは PSTN の要件を参照して判断してください。既定では、TCP ポートの値は 5068 です。</span><span class="sxs-lookup"><span data-stu-id="69916-p104">You define PSTN gateways that are associated with the Mediation Server pool or Mediation Server. If you have already defined gateways, they will be available to associate with the Mediation Server. If you enable the collocation of the Mediation Server, define the listening port range on the pool servers for Transport Layer Security (TLS). By default, this port is 5067. If you select **Enable TCP port**, you must define a Transmission Control Protocol (TCP) port for the collocated Mediation Server. This is an optional setting, and you should refer to the requirements of your gateway or PSTN requirements to determine if you need this. By default, the TCP port value is 5068.</span></span>
    
2. <span data-ttu-id="69916-p105">併置された仲介サーバーに関連付けるトランク。トランクを既に定義している場合は、それらのトランクを仲介サーバーに関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="69916-p105">Trunks that are associated with the collocated Mediation Server. If you have already defined trunks, they will be available to associate with the Mediation Server.</span></span> 
    
3. <span data-ttu-id="69916-p106">複数のトランクを仲介サーバーに関連付けている場合は、トランクを選択して [**既定値にする**] をクリックすることで、既定のトランクを指定できます。既定のゲートウェイとしての選択を解除するには、[**既定値の解除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="69916-p106">If you have more than one trunk associated with a Mediation Server, you can specify a default trunk by selecting the trunk and then clicking **Make Default**. To unselect a gateway as the default, click **Unmake Default**.</span></span> 
    

