---
title: Lync Server 2010 エッジ サーバー FQDN 設定の展開
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeFqdnsSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eb57268c-2419-4655-ace1-91cf871f25c7
description: '[外部設定] でプロパティを定義するには、次のように構成します。'
ms.openlocfilehash: 2954c9add818e67f471cfb97893fef42e862bea3
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="edge-server-fqdn-settings-expander-for-lync-server-2010"></a><span data-ttu-id="26910-103">Lync Server 2010 エッジ サーバー FQDN 設定の展開</span><span class="sxs-lookup"><span data-stu-id="26910-103">Edge Server FQDN Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="26910-104">[**外部設定**] でプロパティを定義するには、次のように構成します。</span><span class="sxs-lookup"><span data-stu-id="26910-104">To define the properties under **External settings**, configure the following:</span></span>
  
<span data-ttu-id="26910-105">選択、**を有効にする別の FQDN と IP アドレスの web 会議および A/V** web 会議、オーディオとビデオのアドレスを個別のプールの FQDN と IP を定義したい場合はチェック ボックスです。</span><span class="sxs-lookup"><span data-stu-id="26910-105">Select the **Enable separate FQDN and IP address for web conferencing and A/V** check box if you want to define distinct Pool FQDN and IP addresses for web conferencing and audio/video.</span></span>
  
> [!NOTE]
> <span data-ttu-id="26910-106">別の FQDN と IP アドレスのチェック ボックスをオンにする場合は、エッジ サーバーによって提供される 3 つのサービスごとに個別のポートを入力します。</span><span class="sxs-lookup"><span data-stu-id="26910-106">If you choose to not select the check box for separate FQDN and IP addresses, you must provide distinct ports for each of the three services provided by the Edge Server.</span></span> <span data-ttu-id="26910-107">設定する必要がある唯一の完全修飾ドメイン名は、アクセス エッジ サービスに関連付けられた FQDN です。</span><span class="sxs-lookup"><span data-stu-id="26910-107">The only fully qualified domain name that is to configure is the FQDN associated with the Access Edge service.</span></span> 
  
<span data-ttu-id="26910-108">選択、 **A/V エッジ サービスは、NAT が有効な**チェック ボックスをオンする場合は、A/ネットワークを使用する音声ビデオ エッジ サービスはアドレス変換 (NAT) IP アドレスと構成。</span><span class="sxs-lookup"><span data-stu-id="26910-108">Select the **A/V Edge service is NAT enabled** check box if you want the A/V Edge service to use a network address translation (NAT) IP address and configuration.</span></span>
  
<span data-ttu-id="26910-109">**プールの FQDN**および**ポート**] の下のポートを入力する有効なエッジ サービスは、</span><span class="sxs-lookup"><span data-stu-id="26910-109">For the enabled Edge services, you type a **Pool FQDN** and a port under **Ports**</span></span>
  
- <span data-ttu-id="26910-110">**アクセス エッジ サービス**のプールの FQDN と、サービスを一意に識別するポートを定義します。</span><span class="sxs-lookup"><span data-stu-id="26910-110">Define the **Access Edge service** Pool FQDN and a port that uniquely identifies the service.</span></span>
    
- <span data-ttu-id="26910-111">**Web 会議エッジ サービス**プールの FQDN を定義する (web 会議および A の FQDN と IP アドレスを分割する場合に有効にする V が選択されていないと) と、サービスを一意に識別するポート。</span><span class="sxs-lookup"><span data-stu-id="26910-111">Define the **Web Conferencing Edge service** Pool FQDN (If Enable separate FQDN and IP address for web conferencing and A/V is not selected) and a port that uniquely identifies the service.</span></span>
    
- <span data-ttu-id="26910-112">定義、 **A/音声ビデオ エッジ サービス**プールの FQDN (web 会議および A の FQDN と IP アドレスを分割する場合に有効にする V が選択されていないと) と、サービスを一意に識別するポート。</span><span class="sxs-lookup"><span data-stu-id="26910-112">Define the **A/V Edge service** Pool FQDN (If Enable separate FQDN and IP address for web conferencing and A/V is not selected) and a port that uniquely identifies the service.</span></span>
    
 <span data-ttu-id="26910-113">[**OK**]: ダイアログでの変更を受け入れて確定します。</span><span class="sxs-lookup"><span data-stu-id="26910-113">**OK** Accepts and commits changes to the dialog.</span></span>
  
 <span data-ttu-id="26910-114">[**キャンセル**]: 変更を破棄してダイアログを閉じます。</span><span class="sxs-lookup"><span data-stu-id="26910-114">**Cancel** Discards changes and closes the dialog.</span></span>
  
 <span data-ttu-id="26910-115">[**ヘルプ**]: このヘルプ画面を表示します。</span><span class="sxs-lookup"><span data-stu-id="26910-115">**Help** Displays this help screen.</span></span>
  

