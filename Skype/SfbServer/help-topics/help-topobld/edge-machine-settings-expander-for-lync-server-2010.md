---
title: Lync Server 2010 用のエッジ コンピューター設定エキスパンダー
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeMachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fb72a5b5-70f4-44af-8dfd-c5d32e563882
description: 単一のエッジ サーバーまたはエッジ プール内のメンバー コンピューターとは、エッジ サーバーのコンピューターのプロパティを編集するには、サーバー名と IP アドレスの構成の設定を構成します。
ms.openlocfilehash: f0125ba8d9c7ff181aff0a29f69a5077b1ad0818
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30891541"
---
# <a name="edge-machine-settings-expander-for-lync-server-2010"></a><span data-ttu-id="1a1ee-103">Lync Server 2010 用のエッジ コンピューター設定エキスパンダー</span><span class="sxs-lookup"><span data-stu-id="1a1ee-103">Edge Machine Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="1a1ee-104">単一のエッジ サーバーまたはエッジ プール内のメンバー コンピューターとは、エッジ サーバーのコンピューターのプロパティを編集するには、**サーバー名と IP アドレスの構成**の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="1a1ee-104">To edit the properties for Edge Server computers as an single Edge Server or as member computers in an Edge pool, you configure **Server name and IP address configuration** settings:</span></span>
  
- <span data-ttu-id="1a1ee-105">**内部名または FQDN**: ドメイン ネーム システム (DNS) で参照されているコンピューターの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="1a1ee-105">**Internal name or FQDN**: Type the name of the computer as it is referenced in the domain name system (DNS).</span></span> 
    
- <span data-ttu-id="1a1ee-106">**内部の IPv4 アドレス**: このコンピューターの内部ネットワーク インターフェイス カード (NIC) の IPv4 アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="1a1ee-106">**Internal IPv4 address**: Type the IPv4 address of the internal network interface card (NIC) for this computer.</span></span>
    
- <span data-ttu-id="1a1ee-107">このコンピューターに関連付けられている**アクセス エッジ サービス**の**外部 IPv4 アドレス**を構成します。</span><span class="sxs-lookup"><span data-stu-id="1a1ee-107">You configure the **Access Edge service** **External IPv4 address** associated with this computer</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="1a1ee-108">エッジ サーバーの構成の 1 つの IP アドレスを使用することを選択した場合は、アクセス エッジ サービスの外部 IPv4 アドレスを編集することは必ず。</span><span class="sxs-lookup"><span data-stu-id="1a1ee-108">If you selected to use a single IP address for the Edge Server configuration, you will only be able to edit the external IPv4 address for the Access Edge service.</span></span> <span data-ttu-id="1a1ee-109">他のエッジ サービスは、アクセス エッジ サービスと同じ IPv4 アドレスを共有します。</span><span class="sxs-lookup"><span data-stu-id="1a1ee-109">The other Edge services will share the same IPv4 address as the Access Edge service.</span></span> 
  
- <span data-ttu-id="1a1ee-110">このコンピューターに関連付けられている**Web 会議サービス**の**外部 IPv4 アドレス**を構成する場合は編集するのには、</span><span class="sxs-lookup"><span data-stu-id="1a1ee-110">If available to edit, you configure the **Web Conferencing service** **External IPv4 address** associated with this computer</span></span>
    
- <span data-ttu-id="1a1ee-111">かどうかは編集に使用可能な構成する、 **A/V エッジ サービス\*\*\*\*外部 IPv4 アドレス**がこのコンピューターに関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="1a1ee-111">If available to edit, you configure the **A/V Edge service** **External IPv4 address** associated with this computer</span></span>
    
- <span data-ttu-id="1a1ee-112">編集可能であれば、このコンピューターに関連付けられている**パブリック IPv4 アドレスの NAT が有効な**を構成します。</span><span class="sxs-lookup"><span data-stu-id="1a1ee-112">If available to edit, you configure the **NAT-enabled public IPv4 address** associated with this computer.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="1a1ee-113">**NAT が有効なパブリックな IPv4 アドレス**の構成のプロパティのみを使用できます、A のネットワーク アドレス変換 (NAT) を提供するよう選択した場合は、編集すると音声ビデオ エッジ サービス</span><span class="sxs-lookup"><span data-stu-id="1a1ee-113">The configuration property for **NAT-enabled public IPv4 address** will only be available to edit if you chose to provide network address translation (NAT) for the A/V Edge service</span></span>
  
  <span data-ttu-id="1a1ee-114">[**OK**]: ダイアログでの変更を受け入れて確定します。</span><span class="sxs-lookup"><span data-stu-id="1a1ee-114">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="1a1ee-115">[**キャンセル**]: 変更を破棄してダイアログを閉じます。</span><span class="sxs-lookup"><span data-stu-id="1a1ee-115">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="1a1ee-116">[**ヘルプ**]: このヘルプ画面を表示します。</span><span class="sxs-lookup"><span data-stu-id="1a1ee-116">**Help** Displays this help screen.</span></span>
  

