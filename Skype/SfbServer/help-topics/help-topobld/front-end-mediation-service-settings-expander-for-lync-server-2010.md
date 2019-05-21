---
title: Lync Server 2010 用のフロントエンド仲介サービス設定の展開
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.FeMediationServiceSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 37166b87-8a43-42a6-a2aa-5a45bed8a6f3
description: このダイアログで、仲介サーバー PSTN ゲートウェイ設定のプロパティを編集します。 次の設定を定義します。
ms.openlocfilehash: b57ca675d3681886ea2a2853aa1357b394fda4c4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34284390"
---
# <a name="front-end-mediation-service-settings-expander-for-lync-server-2010"></a><span data-ttu-id="9bc32-104">Lync Server 2010 用のフロントエンド仲介サービス設定の展開</span><span class="sxs-lookup"><span data-stu-id="9bc32-104">Front End Mediation Service Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="9bc32-105">このダイアログで、**仲介サーバー PSTN ゲートウェイ**設定のプロパティを編集します。</span><span class="sxs-lookup"><span data-stu-id="9bc32-105">You edit the properties of the **Mediation Server PSTN gateway** settings in this dialog.</span></span> <span data-ttu-id="9bc32-106">次の設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="9bc32-106">You define the following settings:</span></span>
  
- <span data-ttu-id="9bc32-107">このフロントエンドサーバーまたはフロントエンドプールで仲介サーバーを検索する場合は、[併置され**ている仲介サーバー** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9bc32-107">Select the **Collocated Mediation Server enabled** if you want to collocate the Mediation Server with this Front End Server or Front End pools.</span></span>
    
- <span data-ttu-id="9bc32-108">**リスニングポート**: 仲介サーバーがリッスンするポートを定義します。</span><span class="sxs-lookup"><span data-stu-id="9bc32-108">**Listening ports**: Define the ports that the Mediation Server will listen on.</span></span> <span data-ttu-id="9bc32-109">**TLS**またはトランスポート層のセキュリティ、 **TCP**、またはトランスポート制御プロトコルのポートを定義できます。</span><span class="sxs-lookup"><span data-stu-id="9bc32-109">You can define a port for **TLS** or transport layer security, or **TCP**, or transport control protocol.</span></span> <span data-ttu-id="9bc32-110">TCP 用のポートエントリを利用できるようにするには、[ **tcp ポートを有効**にする] チェックボックスをオンにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9bc32-110">For the port entry for TCP to be available, you must select the check box for **Enable TCP port**.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="9bc32-111">ポート値 TLS、TCP、またはその両方を有効にする必要があるかどうかを判断するには、公衆交換電話網 (PSTN) ゲートウェイのドキュメントと構成の設定を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9bc32-111">Refer to the documentation and configuration settings for your public switched telephone network (PSTN) gateway to determine if you need to enable and define port values TLS, TCP or both.</span></span> <span data-ttu-id="9bc32-112">TLS はセキュリティで保護されたプロトコルであり、証明書を使って仲介サーバーと PSTN ゲートウェイ間のトラフィックを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="9bc32-112">TLS is a more secure protocol, using certificates to encrypt the traffic between the Mediation Server and the PSTN gateway.</span></span> <span data-ttu-id="9bc32-113">すべての PSTN ゲートウェイで TLS がサポートされるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="9bc32-113">Not all PSTN gateways support TLS.</span></span> 
  
- <span data-ttu-id="9bc32-114">現在関連付けられている既存の [**トランク**] (セッション開始プロトコル (SIP) トランク)、[**ゲートウェイ**] (PSTN ゲートウェイまたは IP-PBX)、および [**サイト**] (トランクおよびゲートウェイの構成済みサイト) の一覧。</span><span class="sxs-lookup"><span data-stu-id="9bc32-114">A listing of currently associated and existing **Trunk** (that is, Session Initiation Protocol (SIP) Trunks), **Gateway** (PSTN gateway or IP-PBX) and **Site** (configured site for the trunk and gateway).</span></span>
    
- <span data-ttu-id="9bc32-p105">トランク、ゲートウェイ、およびサイトを選択し、[**既定値にする**] をクリックして、選択したものをこの仲介サービス用の既定値に設定します。現在の既定値を選択し、[**既定値の解除**] をクリックして、現在の既定値として選択している設定を削除します。その後、新しい既定値を選択して、[**既定値にする**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9bc32-p105">You select a Trunk, Gateway and Site and click **Make Default** to set the selection as the default for this Mediation service. You select the current default and click **Unmake Default** to remove the selection as the current default. You then select a new default and click **Make Default**.</span></span>
    
  <span data-ttu-id="9bc32-118">[**OK**]: ダイアログでの変更を受け入れて確定します。</span><span class="sxs-lookup"><span data-stu-id="9bc32-118">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="9bc32-119">[**キャンセル**]: 変更を破棄してダイアログを閉じます。</span><span class="sxs-lookup"><span data-stu-id="9bc32-119">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="9bc32-120">[**ヘルプ**]: このヘルプ画面を表示します。</span><span class="sxs-lookup"><span data-stu-id="9bc32-120">**Help** Displays this help screen.</span></span>
  

