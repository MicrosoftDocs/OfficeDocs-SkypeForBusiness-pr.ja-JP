---
title: 仲介サーバーの全般設定エキスパンダー
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 4/14/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.MediationServerGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0e0ad9f0-27d5-4975-ae88-0b8ff8a4c514
ms.openlocfilehash: 51e00323c3c0d5df3915b2652b273f1fa189143e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="mediation-server-general-settings-expander"></a><span data-ttu-id="4bace-102">仲介サーバーの全般設定エキスパンダー</span><span class="sxs-lookup"><span data-stu-id="4bace-102">Mediation Server General Settings Expander</span></span>
 
## 

### <a name="general-settings"></a><span data-ttu-id="4bace-103">全般設定</span><span class="sxs-lookup"><span data-stu-id="4bace-103">General settings</span></span>

<span data-ttu-id="4bace-104">仲介サーバーまたは仲介サーバー プールの完全修飾ドメイン名 (FQDN) です。</span><span class="sxs-lookup"><span data-stu-id="4bace-104">Fully qualified domain name (FQDN) of the Mediation Server pool or Mediation Server.</span></span> <span data-ttu-id="4bace-105">値を変更するには、サーバーの FQDN を編集します。</span><span class="sxs-lookup"><span data-stu-id="4bace-105">Edit the FQDN of the server to change the value.</span></span> <span data-ttu-id="4bace-106">新しい値と一致しているドメイン ネーム システム (DNS) ホスト (A) レコードがある必要があります。</span><span class="sxs-lookup"><span data-stu-id="4bace-106">You must have a Domain Name System (DNS) host (A) record that coincides with the new value.</span></span>
  
<span data-ttu-id="4bace-107">[**関連付け**] セクションでは、仲介サーバー プールまたは仲介サーバーに関連付けるには、エッジ サーバーまたはエッジ サーバー プールを選択します。</span><span class="sxs-lookup"><span data-stu-id="4bace-107">In the **Associations** section, you select an Edge Server or Edge Server pool to associate with the Mediation Server pool or Mediation Server.</span></span> <span data-ttu-id="4bace-108">外部ユーザーのエンタープライズ VoIP の仲介サーバーのメディア コンポーネントを使用するエッジを選択します。</span><span class="sxs-lookup"><span data-stu-id="4bace-108">You select the Edge that the Mediation Server's media components will use for External user Enterprise Voice.</span></span>
  
<span data-ttu-id="4bace-109">必要はありません、エッジ サーバーが、現在定義され、仲介サーバーをエッジ サーバーに関連付ける、[**新規**] をクリックし、新しいエッジ サーバーまたはエッジ サーバー プールを定義する新しいエッジ プールの作成ウィザードで定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4bace-109">If you do not have an Edge Server currently defined and need to associate the Mediation Server with an Edge Server, click **New** and define the new Edge Server or Edge Server pool in the Define the New Edge pool wizard.</span></span>
  
### <a name="next-hop-settings"></a><span data-ttu-id="4bace-110">次ホップ設定</span><span class="sxs-lookup"><span data-stu-id="4bace-110">Next hop settings</span></span>

<span data-ttu-id="4bace-111">プールの仲介サーバーまたは仲介サーバーの次のホップを指定するには、ドロップ ダウン リストから定義済みのエンタープライズ エディションのフロント エンド プールまたは標準的なフロント エンド サーバーのエディションを選択します。</span><span class="sxs-lookup"><span data-stu-id="4bace-111">You specify the Mediation Server pool or Mediation Server next hop by selecting the defined Enterprise Edition Front End pool or Standard Edition Front End Server from the drop-down list.</span></span> <span data-ttu-id="4bace-112">ディレクターまたはディレクター プール プールの仲介サーバーまたは仲介サーバーの次ホップの選択が有効ではありませんし、一覧に表示されません。</span><span class="sxs-lookup"><span data-stu-id="4bace-112">A Director or Director pool is not a valid selection for a Mediation Server pool or Mediation Server next hop, and will not appear in the list.</span></span> <span data-ttu-id="4bace-113">受け入れるし、変更内容を保存して**[ok]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4bace-113">Click **OK** to accept and save your changes.</span></span> <span data-ttu-id="4bace-114">変更を破棄してプロパティ ページを終了するには、[**キャンセル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4bace-114">Click **Cancel** to discard your changes and exit the properties page.</span></span>
  
### <a name="pstn-gateway-settings"></a><span data-ttu-id="4bace-115">PSTN ゲートウェイの設定</span><span class="sxs-lookup"><span data-stu-id="4bace-115">PSTN gateway settings</span></span>

1. <span data-ttu-id="4bace-116">プールの仲介サーバーまたは仲介サーバーに関連付けられている PSTN ゲートウェイを定義します。</span><span class="sxs-lookup"><span data-stu-id="4bace-116">You define PSTN gateways that are associated with the Mediation Server pool or Mediation Server.</span></span> <span data-ttu-id="4bace-117">ゲートウェイが定義されている場合は、仲介サーバーに関連付けるに使用されます。</span><span class="sxs-lookup"><span data-stu-id="4bace-117">If you have already defined gateways, they will be available to associate with the Mediation Server.</span></span> <span data-ttu-id="4bace-118">仲介サーバーのコロケーションを有効にした場合リスニング ポート範囲を定義プールのサーバー上のトランスポート層セキュリティ (TLS)。</span><span class="sxs-lookup"><span data-stu-id="4bace-118">If you enable the collocation of the Mediation Server, define the listening port range on the pool servers for Transport Layer Security (TLS).</span></span> <span data-ttu-id="4bace-119">既定では、このポートは 5067 です。</span><span class="sxs-lookup"><span data-stu-id="4bace-119">By default, this port is 5067.</span></span> <span data-ttu-id="4bace-120">**有効にする TCP ポート**を選択する場合は、配置されている仲介サーバーの伝送制御プロトコル (TCP) ポートを定義してください。</span><span class="sxs-lookup"><span data-stu-id="4bace-120">If you select **Enable TCP port**, you must define a Transmission Control Protocol (TCP) port for the collocated Mediation Server.</span></span> <span data-ttu-id="4bace-121">これは、オプションの設定、およびゲートウェイの要件や、これが必要なかどうかを決定するのには、PSTN の要件を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4bace-121">This is an optional setting, and you should refer to the requirements of your gateway or PSTN requirements to determine if you need this.</span></span> <span data-ttu-id="4bace-122">既定では、TCP ポートの値は 5068 がします。</span><span class="sxs-lookup"><span data-stu-id="4bace-122">By default, the TCP port value is 5068.</span></span>
    
2. <span data-ttu-id="4bace-p105">併置された仲介サーバーに関連付けるトランク。トランクを既に定義している場合は、それらを仲介サーバーに関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="4bace-p105">Trunks that are associated with the collocated Mediation Server. If you have already defined trunks, they will be available to associate with the Mediation Server.</span></span> 
    
3. <span data-ttu-id="4bace-125">仲介サーバーに関連付けられている 1 つ以上のトランクの場合は、トランクを選択し、**既定値に設定**をクリックして既定のトランクを指定できます。</span><span class="sxs-lookup"><span data-stu-id="4bace-125">If you have more than one trunk associated with a Mediation Server, you can specify a default trunk by selecting the trunk and then clicking **Make Default**.</span></span> <span data-ttu-id="4bace-126">既定のゲートウェイとしての選択を解除するには、[**既定値の解除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4bace-126">To unselect a gateway as the default, click **Unmake Default**.</span></span> 
    

