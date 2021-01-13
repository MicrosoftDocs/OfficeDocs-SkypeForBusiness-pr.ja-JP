---
title: Lync Server 2010 用のエッジ サーバー FQDN 設定エキスパンダー
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.EdgeFqdnsSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eb57268c-2419-4655-ace1-91cf871f25c7
description: '[外部設定] の下でプロパティを定義するには、次のものを構成します。'
ms.openlocfilehash: 6075fab9dbc820b725beec8be4a674a828b4c7d1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49807097"
---
# <a name="edge-server-fqdn-settings-expander-for-lync-server-2010"></a><span data-ttu-id="30eee-103">Lync Server 2010 用のエッジ サーバー FQDN 設定エキスパンダー</span><span class="sxs-lookup"><span data-stu-id="30eee-103">Edge Server FQDN Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="30eee-104">[**外部設定**] の下でプロパティを定義するには、次のものを構成します。</span><span class="sxs-lookup"><span data-stu-id="30eee-104">To define the properties under **External settings**, configure the following:</span></span>
  
<span data-ttu-id="30eee-105">Web 会議と音声ビデオに対して別々のプールの FQDN と IP アドレスを定義する場合は、[**Web 会議と音声ビデオに対する別々の FQDN および IP アドレス設定の有効化**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="30eee-105">Select the **Enable separate FQDN and IP address for web conferencing and A/V** check box if you want to define distinct Pool FQDN and IP addresses for web conferencing and audio/video.</span></span>
  
> [!NOTE]
> <span data-ttu-id="30eee-106">別々の FQDN と IP アドレスのチェック ボックスをオンにしない場合は、エッジ サーバーによって提供される 3 つのサービスごとに個別のポートを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="30eee-106">If you choose to not select the check box for separate FQDN and IP addresses, you must provide distinct ports for each of the three services provided by the Edge Server.</span></span> <span data-ttu-id="30eee-107">構成する完全修飾ドメイン名は、アクセス エッジ サービスに関連付けられている FQDN のみです。</span><span class="sxs-lookup"><span data-stu-id="30eee-107">The only fully qualified domain name that is to configure is the FQDN associated with the Access Edge service.</span></span> 
  
<span data-ttu-id="30eee-108">ネットワーク アドレス **変換** (NAT) IP アドレスと構成を使用する場合は、A/V エッジ サービスで NAT が有効なチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="30eee-108">Select the **A/V Edge service is NAT enabled** check box if you want the A/V Edge service to use a network address translation (NAT) IP address and configuration.</span></span>
  
<span data-ttu-id="30eee-109">有効なエッジ サービスに対して、**プールの FQDN** とポートを [**ポート**] の下に入力します。</span><span class="sxs-lookup"><span data-stu-id="30eee-109">For the enabled Edge services, you type a **Pool FQDN** and a port under **Ports**</span></span>
  
- <span data-ttu-id="30eee-110">**アクセス エッジ サービス** のプール FQDN とそのサービスを一意に識別するポートを定義します。</span><span class="sxs-lookup"><span data-stu-id="30eee-110">Define the **Access Edge service** Pool FQDN and a port that uniquely identifies the service.</span></span>
    
- <span data-ttu-id="30eee-111">**Web 会議エッジ サービス** のプール FQDN ([Web 会議と音声ビデオに対する別々の FQDN および IP アドレス設定の有効化] を選択していない場合) とそのサービスを一意に識別するポートを定義します。</span><span class="sxs-lookup"><span data-stu-id="30eee-111">Define the **Web Conferencing Edge service** Pool FQDN (If Enable separate FQDN and IP address for web conferencing and A/V is not selected) and a port that uniquely identifies the service.</span></span>
    
- <span data-ttu-id="30eee-112">**音声ビデオ エッジ サービス** のプール FQDN ([Web 会議と音声ビデオに対する別々の FQDN および IP アドレス設定の有効化] を選択していない場合) とそのサービスを一意に識別するポートを定義します。</span><span class="sxs-lookup"><span data-stu-id="30eee-112">Define the **A/V Edge service** Pool FQDN (If Enable separate FQDN and IP address for web conferencing and A/V is not selected) and a port that uniquely identifies the service.</span></span>
    
  <span data-ttu-id="30eee-113">[**OK**]: ダイアログでの変更を受け入れて確定します。</span><span class="sxs-lookup"><span data-stu-id="30eee-113">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="30eee-114">[**キャンセル**]: 変更を破棄してダイアログを閉じます。</span><span class="sxs-lookup"><span data-stu-id="30eee-114">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="30eee-115">[**ヘルプ**]: このヘルプ画面を表示します。</span><span class="sxs-lookup"><span data-stu-id="30eee-115">**Help** Displays this help screen.</span></span>
  

