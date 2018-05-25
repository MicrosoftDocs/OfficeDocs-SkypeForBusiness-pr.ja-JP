---
title: Lync Server 2010 のフロント エンド仲介サービスの設定の拡張
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.FeMediationServiceSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 37166b87-8a43-42a6-a2aa-5a45bed8a6f3
description: このダイアログ ボックスで、仲介サーバー PSTN ゲートウェイの設定のプロパティを編集するとします。 次の設定を定義します。
ms.openlocfilehash: e3ec392aac08121296769a9d5170886c61c7511b
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/24/2018
---
# <a name="front-end-mediation-service-settings-expander-for-lync-server-2010"></a><span data-ttu-id="46258-104">Lync Server 2010 のフロント エンド仲介サービスの設定の拡張</span><span class="sxs-lookup"><span data-stu-id="46258-104">Front End Mediation Service Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="46258-105">このダイアログ ボックスで **、仲介サーバー PSTN ゲートウェイ**の設定のプロパティを編集するとします。</span><span class="sxs-lookup"><span data-stu-id="46258-105">You edit the properties of the **Mediation Server PSTN gateway** settings in this dialog.</span></span> <span data-ttu-id="46258-106">次の設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="46258-106">You define the following settings:</span></span>
  
- <span data-ttu-id="46258-107">このフロント エンド サーバーまたはフロント エンド プールに仲介サーバーを連結する場合は、**仲介サーバーを 1 か所に配置を有効に**するを選択します。</span><span class="sxs-lookup"><span data-stu-id="46258-107">Select the **Collocated Mediation Server enabled** if you want to collocate the Mediation Server with this Front End Server or Front End pools.</span></span>
    
- <span data-ttu-id="46258-108">**リッスンするポート**: 仲介サーバーがリッスンするポートを定義します。</span><span class="sxs-lookup"><span data-stu-id="46258-108">**Listening ports**: Define the ports that the Mediation Server will listen on.</span></span> <span data-ttu-id="46258-109">**TLS**またはトランスポート層セキュリティ、または**TCP**のポートを定義することができますまたはトランス ポート プロトコルを制御します。</span><span class="sxs-lookup"><span data-stu-id="46258-109">You can define a port for **TLS** or transport layer security, or **TCP**, or transport control protocol.</span></span> <span data-ttu-id="46258-110">使用する TCP のポートのエントリを**有効にする TCP ポート**のチェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="46258-110">For the port entry for TCP to be available, you must select the check box for **Enable TCP port**.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="46258-111">TLS と TCP のどちらか一方または両方のポートの値を有効にして、定義する必要がある場合を判断するのには公衆交換電話網 (PSTN) ゲートウェイのドキュメントおよび構成の設定] を参照してください。</span><span class="sxs-lookup"><span data-stu-id="46258-111">Refer to the documentation and configuration settings for your public switched telephone network (PSTN) gateway to determine if you need to enable and define port values TLS, TCP or both.</span></span> <span data-ttu-id="46258-112">TLS は、仲介サーバーと PSTN ゲートウェイ間のトラフィックを暗号化する証明書を使用して、安全なプロトコルです。</span><span class="sxs-lookup"><span data-stu-id="46258-112">TLS is a more secure protocol, using certificates to encrypt the traffic between the Mediation Server and the PSTN gateway.</span></span> <span data-ttu-id="46258-113">すべての PSTN ゲートウェイが TLS をサポートします。</span><span class="sxs-lookup"><span data-stu-id="46258-113">Not all PSTN gateways support TLS.</span></span> 
  
- <span data-ttu-id="46258-114">現在関連付けられている既存の [**トランク**] (セッション開始プロトコル (SIP) トランク)、[**ゲートウェイ**] (PSTN ゲートウェイまたは IP-PBX)、および [**サイト**] (トランクおよびゲートウェイの構成済みサイト) の一覧。</span><span class="sxs-lookup"><span data-stu-id="46258-114">A listing of currently associated and existing **Trunk** (that is, Session Initiation Protocol (SIP) Trunks), **Gateway** (PSTN gateway or IP-PBX) and **Site** (configured site for the trunk and gateway).</span></span>
    
- <span data-ttu-id="46258-p105">トランク、ゲートウェイ、およびサイトを選択し、[**既定値にする**] をクリックして、選択したものをこの仲介サービス用の既定値に設定します。現在の既定値を選択し、[**既定値の解除**] をクリックして、現在の既定値として選択している設定を削除します。その後、新しい既定値を選択して、[**既定値にする**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="46258-p105">You select a Trunk, Gateway and Site and click **Make Default** to set the selection as the default for this Mediation service. You select the current default and click **Unmake Default** to remove the selection as the current default. You then select a new default and click **Make Default**.</span></span>
    
 <span data-ttu-id="46258-118">[**OK**]: ダイアログでの変更を受け入れて確定します。</span><span class="sxs-lookup"><span data-stu-id="46258-118">**OK** Accepts and commits changes to the dialog.</span></span>
  
 <span data-ttu-id="46258-119">[**キャンセル**]: 変更を破棄してダイアログを閉じます。</span><span class="sxs-lookup"><span data-stu-id="46258-119">**Cancel** Discards changes and closes the dialog.</span></span>
  
 <span data-ttu-id="46258-120">[**ヘルプ**]: このヘルプ画面を表示します。</span><span class="sxs-lookup"><span data-stu-id="46258-120">**Help** Displays this help screen.</span></span>
  

