---
title: Lync Server 2010 用の仲介サービス設定エキスパンダー
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/26/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.MediationServiceSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 230e0a08-9e16-4bbd-b550-1f04bad8ddbc
description: 次のプロパティを定義して、仲介サービスのプロパティを編集します。
ms.openlocfilehash: d8529a97459de70270fbe709d06c92e5a1b37af3
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/24/2018
---
# <a name="mediation-service-settings-expander-for-lync-server-2010"></a><span data-ttu-id="5c7e0-103">Lync Server 2010 用の仲介サービス設定エキスパンダー</span><span class="sxs-lookup"><span data-stu-id="5c7e0-103">Mediation Service Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="5c7e0-104">次のプロパティを定義して、仲介サービスのプロパティを編集します。</span><span class="sxs-lookup"><span data-stu-id="5c7e0-104">You edit the properties of the Mediation service by defining the following properties:</span></span>
  
- <span data-ttu-id="5c7e0-p101">[**リッスン ポート**]: 仲介サービスがリッスンする **TLS** ポートを定義します。既定では、ポート値はトランスポート層セキュリティ (TLS) 経由の TCP 5067 です。</span><span class="sxs-lookup"><span data-stu-id="5c7e0-p101">**Listening ports**: Define the **TLS** port that the Mediation service will listen on. By default, the port value is TCP 5067 over transport layer security (TLS)</span></span>
    
    <span data-ttu-id="5c7e0-p102">必要に応じて、**TCP** ポート値を定義します。既定では、この値は TCP 5068 です。</span><span class="sxs-lookup"><span data-stu-id="5c7e0-p102">Optionally, you define a **TCP** port value. By default, the value is TCP 5068.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5c7e0-p103">TCP ポート値の設定を有効にするには、[**TCP ポートを有効にする**] を選択します。仲介サービスとの通信に必要なポート設定の要件については、公衆交換電話網 (PSTN) ゲートウェイまたはインターネット プロトコル構内交換機 (IP-PBX) のドキュメントを参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5c7e0-p103">The TCP port value setting is enabled by selecting **Enable TCP port**. You should refer to the documentation for your Public Switched Telephone Network (PSTN) Gateway or Internet Protocol Private Branch Exchange (IP-PBX) for the requirements for the port settings required to communicate with the Mediation service.</span></span> 
  
- <span data-ttu-id="5c7e0-111">[**TCP ポートを有効にする**] を選択して、PSTN ゲートウェイまたは IP-PBX からの TCP 通信のポート値を定義します。</span><span class="sxs-lookup"><span data-stu-id="5c7e0-111">You **Enable TCP port** to define the port value for TCP communications from your PSTN gateway or IP-PBX.</span></span>
    
- <span data-ttu-id="5c7e0-112">現在関連付けられている既存の [**トランク**] (セッション開始プロトコル (SIP) トランク)、[**ゲートウェイ**] (PSTN ゲートウェイまたは IP-PBX)、および [**サイト**] (トランクおよびゲートウェイの構成済みサイト) の一覧。</span><span class="sxs-lookup"><span data-stu-id="5c7e0-112">A listing of currently associated and existing **Trunk** (that is, Session Initiation Protocol (SIP) Trunks), **Gateway** (PSTN gateway or IP-PBX) and **Site** (configured site for the trunk and gateway).</span></span>
    
- <span data-ttu-id="5c7e0-p104">トランク、ゲートウェイ、およびサイトを選択し、[**既定値にする**] をクリックして、選択したものをこの仲介サービス用の既定値に設定します。現在の既定値を選択し、[**既定値の解除**] をクリックして、現在の既定値として選択している設定を削除します。その後、新しい既定値を選択して、[**既定値にする**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5c7e0-p104">You select a Trunk, Gateway and Site and click **Make Default** to set the selection as the default for this Mediation service. You select the current default and click **Unmake Default** to remove the selection as the current default. You then select a new default and click **Make Default**.</span></span>
    
 <span data-ttu-id="5c7e0-116">[**OK**]: ダイアログでの変更を受け入れて確定します。</span><span class="sxs-lookup"><span data-stu-id="5c7e0-116">**OK** Accepts and commits changes to the dialog.</span></span>
  
 <span data-ttu-id="5c7e0-117">[**キャンセル**]: 変更を破棄してダイアログを閉じます。</span><span class="sxs-lookup"><span data-stu-id="5c7e0-117">**Cancel** Discards changes and closes the dialog.</span></span>
  
 <span data-ttu-id="5c7e0-118">[**ヘルプ**]: このヘルプ画面を表示します。</span><span class="sxs-lookup"><span data-stu-id="5c7e0-118">**Help** Displays this help screen.</span></span>
  

