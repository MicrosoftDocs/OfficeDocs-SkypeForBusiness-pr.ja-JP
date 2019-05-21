---
title: Lync Server 2010 用のエッジ コンピューター設定エキスパンダー
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeMachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fb72a5b5-70f4-44af-8dfd-c5d32e563882
description: エッジサーバーコンピューターのプロパティを1つのエッジサーバーまたはエッジプールのメンバーコンピューターとして編集するには、サーバー名と IP アドレス構成設定を構成します。
ms.openlocfilehash: c9201cfde9f19391e1cee351de6d4efac00be9dd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34302337"
---
# <a name="edge-machine-settings-expander-for-lync-server-2010"></a><span data-ttu-id="bd4ba-103">Lync Server 2010 用のエッジ コンピューター設定エキスパンダー</span><span class="sxs-lookup"><span data-stu-id="bd4ba-103">Edge Machine Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="bd4ba-104">エッジサーバーコンピューターのプロパティを1つのエッジサーバーまたはエッジプールのメンバーコンピューターとして編集するには、**サーバー名と IP アドレス構成**設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="bd4ba-104">To edit the properties for Edge Server computers as an single Edge Server or as member computers in an Edge pool, you configure **Server name and IP address configuration** settings:</span></span>
  
- <span data-ttu-id="bd4ba-105">[ **Internal name OR FQDN**]: ドメインネームシステム (DNS) で参照されているコンピューターの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="bd4ba-105">**Internal name or FQDN**: Type the name of the computer as it is referenced in the domain name system (DNS).</span></span> 
    
- <span data-ttu-id="bd4ba-106">[**内部 IPv4 アドレス**]: このコンピューターの内部ネットワークインターフェイスカード (NIC) の IPv4 アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="bd4ba-106">**Internal IPv4 address**: Type the IPv4 address of the internal network interface card (NIC) for this computer.</span></span>
    
- <span data-ttu-id="bd4ba-107">このコンピューターに関連付けられている**アクセスエッジサービス**の**外部 IPv4 アドレス**を構成します</span><span class="sxs-lookup"><span data-stu-id="bd4ba-107">You configure the **Access Edge service** **External IPv4 address** associated with this computer</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="bd4ba-108">エッジサーバー構成に単一の IP アドレスを使用するように選択した場合は、アクセスエッジサービスの外部 IPv4 アドレスのみを編集できます。</span><span class="sxs-lookup"><span data-stu-id="bd4ba-108">If you selected to use a single IP address for the Edge Server configuration, you will only be able to edit the external IPv4 address for the Access Edge service.</span></span> <span data-ttu-id="bd4ba-109">他のエッジサービスは、アクセスエッジサービスと同じ IPv4 アドレスを共有します。</span><span class="sxs-lookup"><span data-stu-id="bd4ba-109">The other Edge services will share the same IPv4 address as the Access Edge service.</span></span> 
  
- <span data-ttu-id="bd4ba-110">編集できる場合は、このコンピューターに関連付けられている**Web 会議サービス**の**外部 IPv4 アドレス**を構成します。</span><span class="sxs-lookup"><span data-stu-id="bd4ba-110">If available to edit, you configure the **Web Conferencing service** **External IPv4 address** associated with this computer</span></span>
    
- <span data-ttu-id="bd4ba-111">編集できる場合は、このコンピューターに関連付けられている**A/V Edge サービス**の**外部 IPv4 アドレス**を構成します。</span><span class="sxs-lookup"><span data-stu-id="bd4ba-111">If available to edit, you configure the **A/V Edge service** **External IPv4 address** associated with this computer</span></span>
    
- <span data-ttu-id="bd4ba-112">編集できる場合は、このコンピューターに関連付けられている**NAT 対応パブリック IPv4 アドレス**を構成します。</span><span class="sxs-lookup"><span data-stu-id="bd4ba-112">If available to edit, you configure the **NAT-enabled public IPv4 address** associated with this computer.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="bd4ba-113">**Nat 対応パブリック IPv4 アドレス**の構成プロパティは、A/V Edge サービスのネットワークアドレス変換 (NAT) を提供するように選択した場合にのみ編集可能になります。</span><span class="sxs-lookup"><span data-stu-id="bd4ba-113">The configuration property for **NAT-enabled public IPv4 address** will only be available to edit if you chose to provide network address translation (NAT) for the A/V Edge service</span></span>
  
  <span data-ttu-id="bd4ba-114">[**OK**]: ダイアログでの変更を受け入れて確定します。</span><span class="sxs-lookup"><span data-stu-id="bd4ba-114">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="bd4ba-115">[**キャンセル**]: 変更を破棄してダイアログを閉じます。</span><span class="sxs-lookup"><span data-stu-id="bd4ba-115">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="bd4ba-116">[**ヘルプ**]: このヘルプ画面を表示します。</span><span class="sxs-lookup"><span data-stu-id="bd4ba-116">**Help** Displays this help screen.</span></span>
  

