---
title: Lync Server 2010 用のエッジ コンピューター設定エキスパンダー
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
- ms.lync.tb.EdgeMachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fb72a5b5-70f4-44af-8dfd-c5d32e563882
description: エッジ サーバー コンピューターのプロパティを単一のエッジ サーバーまたはエッジ プールのメンバー コンピューターとして編集するには、サーバー名と IP アドレス構成設定を構成します。
ms.openlocfilehash: e25f68ec510cf15cd58872a8c584dc71aa939f48
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49807137"
---
# <a name="edge-machine-settings-expander-for-lync-server-2010"></a><span data-ttu-id="da881-103">Lync Server 2010 用のエッジ コンピューター設定エキスパンダー</span><span class="sxs-lookup"><span data-stu-id="da881-103">Edge Machine Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="da881-104">エッジ サーバー コンピューターのプロパティを単一のエッジ サーバーまたはエッジ プールのメンバー コンピューターとして編集するには、サーバー名と IP アドレス構成設定 **を構成** します。</span><span class="sxs-lookup"><span data-stu-id="da881-104">To edit the properties for Edge Server computers as an single Edge Server or as member computers in an Edge pool, you configure **Server name and IP address configuration** settings:</span></span>
  
- <span data-ttu-id="da881-105">**内部名または FQDN**: ドメイン ネーム システム (DNS) で参照されているコンピューターの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="da881-105">**Internal name or FQDN**: Type the name of the computer as it is referenced in the domain name system (DNS).</span></span> 
    
- <span data-ttu-id="da881-106">**内部 IPv4 アドレス**: このコンピューターの内部ネットワーク インターフェイス カード (NIC) の IPv4 アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="da881-106">**Internal IPv4 address**: Type the IPv4 address of the internal network interface card (NIC) for this computer.</span></span>
    
- <span data-ttu-id="da881-107">このコンピューターに関連 **付けられているアクセス エッジ サービス** の外部 **IPv4** アドレスを構成する</span><span class="sxs-lookup"><span data-stu-id="da881-107">You configure the **Access Edge service** **External IPv4 address** associated with this computer</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="da881-108">エッジ サーバー構成に単一の IP アドレスを使用する場合は、アクセス エッジ サービスの外部 IPv4 アドレスのみを編集できます。</span><span class="sxs-lookup"><span data-stu-id="da881-108">If you selected to use a single IP address for the Edge Server configuration, you will only be able to edit the external IPv4 address for the Access Edge service.</span></span> <span data-ttu-id="da881-109">他のエッジ サービスは、アクセス エッジ サービスと同じ IPv4 アドレスを共有します。</span><span class="sxs-lookup"><span data-stu-id="da881-109">The other Edge services will share the same IPv4 address as the Access Edge service.</span></span> 
  
- <span data-ttu-id="da881-110">編集可能な場合は、このコンピューターに関連付けられている **Web 会議** サービスの外部 **IPv4** アドレスを構成します。</span><span class="sxs-lookup"><span data-stu-id="da881-110">If available to edit, you configure the **Web Conferencing service** **External IPv4 address** associated with this computer</span></span>
    
- <span data-ttu-id="da881-111">編集可能な場合は、このコンピューターに関連付けられている外部 **IPv4** アドレスを **A/V** エッジ サービスで構成します。</span><span class="sxs-lookup"><span data-stu-id="da881-111">If available to edit, you configure the **A/V Edge service** **External IPv4 address** associated with this computer</span></span>
    
- <span data-ttu-id="da881-112">編集可能な場合は、このコンピューターに関連付けられている NAT 対応パブリック **IPv4 アドレス** を構成します。</span><span class="sxs-lookup"><span data-stu-id="da881-112">If available to edit, you configure the **NAT-enabled public IPv4 address** associated with this computer.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="da881-113">NAT が有効なパブリック **IPv4** アドレスの構成プロパティは、A/V エッジ サービスにネットワーク アドレス変換 (NAT) を提供することを選択した場合にのみ編集できます。</span><span class="sxs-lookup"><span data-stu-id="da881-113">The configuration property for **NAT-enabled public IPv4 address** will only be available to edit if you chose to provide network address translation (NAT) for the A/V Edge service</span></span>
  
  <span data-ttu-id="da881-114">[**OK**]: ダイアログでの変更を受け入れて確定します。</span><span class="sxs-lookup"><span data-stu-id="da881-114">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="da881-115">[**キャンセル**]: 変更を破棄してダイアログを閉じます。</span><span class="sxs-lookup"><span data-stu-id="da881-115">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="da881-116">[**ヘルプ**]: このヘルプ画面を表示します。</span><span class="sxs-lookup"><span data-stu-id="da881-116">**Help** Displays this help screen.</span></span>
  

