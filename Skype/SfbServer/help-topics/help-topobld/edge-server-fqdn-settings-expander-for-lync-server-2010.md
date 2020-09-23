---
title: Lync Server 2010 用のエッジ サーバー FQDN 設定エキスパンダー
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: 2de4b562d5b6a8b8ef9707d603fe5f4667893ba4
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218248"
---
# <a name="edge-server-fqdn-settings-expander-for-lync-server-2010"></a><span data-ttu-id="a4de4-103">Lync Server 2010 用のエッジ サーバー FQDN 設定エキスパンダー</span><span class="sxs-lookup"><span data-stu-id="a4de4-103">Edge Server FQDN Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="a4de4-104">[**外部設定**] の下でプロパティを定義するには、次のものを構成します。</span><span class="sxs-lookup"><span data-stu-id="a4de4-104">To define the properties under **External settings**, configure the following:</span></span>
  
<span data-ttu-id="a4de4-105">Web 会議と音声ビデオに対して別々のプールの FQDN と IP アドレスを定義する場合は、[**Web 会議と音声ビデオに対する別々の FQDN および IP アドレス設定の有効化**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a4de4-105">Select the **Enable separate FQDN and IP address for web conferencing and A/V** check box if you want to define distinct Pool FQDN and IP addresses for web conferencing and audio/video.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a4de4-106">別々の FQDN と IP アドレスのチェックボックスをオンにしない場合は、エッジサーバーによって提供される3つのサービスごとに個別のポートを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a4de4-106">If you choose to not select the check box for separate FQDN and IP addresses, you must provide distinct ports for each of the three services provided by the Edge Server.</span></span> <span data-ttu-id="a4de4-107">構成する完全修飾ドメイン名は、アクセスエッジサービスに関連付けられている FQDN です。</span><span class="sxs-lookup"><span data-stu-id="a4de4-107">The only fully qualified domain name that is to configure is the FQDN associated with the Access Edge service.</span></span> 
  
<span data-ttu-id="a4de4-108">音声ビデオエッジサービスでネットワークアドレス変換 (NAT) IP アドレスと構成を使用する場合は、[ **音声ビデオエッジサービスの nat を有効** にする] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="a4de4-108">Select the **A/V Edge service is NAT enabled** check box if you want the A/V Edge service to use a network address translation (NAT) IP address and configuration.</span></span>
  
<span data-ttu-id="a4de4-109">有効なエッジ サービスに対して、**プールの FQDN** とポートを [**ポート**] の下に入力します。</span><span class="sxs-lookup"><span data-stu-id="a4de4-109">For the enabled Edge services, you type a **Pool FQDN** and a port under **Ports**</span></span>
  
- <span data-ttu-id="a4de4-110">**アクセス エッジ サービス**のプール FQDN とそのサービスを一意に識別するポートを定義します。</span><span class="sxs-lookup"><span data-stu-id="a4de4-110">Define the **Access Edge service** Pool FQDN and a port that uniquely identifies the service.</span></span>
    
- <span data-ttu-id="a4de4-111">**Web 会議エッジ サービス**のプール FQDN ([Web 会議と音声ビデオに対する別々の FQDN および IP アドレス設定の有効化] を選択していない場合) とそのサービスを一意に識別するポートを定義します。</span><span class="sxs-lookup"><span data-stu-id="a4de4-111">Define the **Web Conferencing Edge service** Pool FQDN (If Enable separate FQDN and IP address for web conferencing and A/V is not selected) and a port that uniquely identifies the service.</span></span>
    
- <span data-ttu-id="a4de4-112">**音声ビデオ エッジ サービス**のプール FQDN ([Web 会議と音声ビデオに対する別々の FQDN および IP アドレス設定の有効化] を選択していない場合) とそのサービスを一意に識別するポートを定義します。</span><span class="sxs-lookup"><span data-stu-id="a4de4-112">Define the **A/V Edge service** Pool FQDN (If Enable separate FQDN and IP address for web conferencing and A/V is not selected) and a port that uniquely identifies the service.</span></span>
    
  <span data-ttu-id="a4de4-113">[**OK**]: ダイアログでの変更を受け入れて確定します。</span><span class="sxs-lookup"><span data-stu-id="a4de4-113">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="a4de4-114">[**キャンセル**]: 変更を破棄してダイアログを閉じます。</span><span class="sxs-lookup"><span data-stu-id="a4de4-114">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="a4de4-115">[**ヘルプ**]: このヘルプ画面を表示します。</span><span class="sxs-lookup"><span data-stu-id="a4de4-115">**Help** Displays this help screen.</span></span>
  

