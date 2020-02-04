---
title: エッジ コンピューター設定エキスパンダー
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.EdgeMachineSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 747456dd-d237-44e6-9e64-63b0e7212a08
ROBOTS: NOINDEX, NOFOLLOW
description: エッジサーバーのプールにあるサーバーのプロパティを編集するには、次の操作を行います。
ms.openlocfilehash: 22f1e46481ce2392a806eadd6029ab51292d5585
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2020
ms.locfileid: "41702292"
---
# <a name="edge-machine-settings-expander"></a><span data-ttu-id="bd370-103">エッジ コンピューター設定エキスパンダー</span><span class="sxs-lookup"><span data-stu-id="bd370-103">Edge Machine Settings Expander</span></span>
 
<span data-ttu-id="bd370-104">エッジサーバーのプールにあるサーバーのプロパティを編集するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="bd370-104">To edit the properties for a server in a pool of Edge Servers, do the following:</span></span>
  
<span data-ttu-id="bd370-105">**内部名または fqdn**は、完全修飾ドメイン名 (fqdn) を編集することで変更できます。</span><span class="sxs-lookup"><span data-stu-id="bd370-105">The **Internal name or FQDN** can be changed by editing the fully qualified domain name (FQDN).</span></span> <span data-ttu-id="bd370-106">FQDN は、ドメインネームシステム (DNS) host (A) レコードと、内部エッジネットワークインターフェイスに対してサーバーに割り当てられている証明書のサブジェクト名と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd370-106">The FQDN must match the Domain Name System (DNS) host (A) record, and the subject name of the certificate assigned to the server for the internal Edge network interface.</span></span> <span data-ttu-id="bd370-107">[**内部 ip アドレス**] の値は、境界ネットワーク設計を基準とした内部ネットワークとして定義されるネットワークインターフェイスに割り当てられている ip アドレスを定義します。</span><span class="sxs-lookup"><span data-stu-id="bd370-107">The value of **Internal IP address** defines the IP address that is assigned the network interface that is defined as an internal network, relative to the perimeter network design.</span></span>
  
<span data-ttu-id="bd370-108">ダイアログの次の3つのセクションでは、このエッジサーバーの外部構成の IP アドレスを定義しています。</span><span class="sxs-lookup"><span data-stu-id="bd370-108">The next three sections of the dialog define the IP addresses for the external configuration of this Edge Server.</span></span> <span data-ttu-id="bd370-109">IP アドレスを変更できるかどうかは、この設定によって、エッジサーバープールレベルのプロパティ設定で、[ **web 会議に個別の FQDN と IP アドレスを有効にする] と [A/V** ] を設定することによって変わります。</span><span class="sxs-lookup"><span data-stu-id="bd370-109">The ability to change the IP addresses is affected by the setting **Enable separate FQDN and IP address for web conferencing and A/V** on the Properties settings at the Edge Server pool level.</span></span>
  
## <a name="sip-access"></a><span data-ttu-id="bd370-110">SIP アクセス</span><span class="sxs-lookup"><span data-stu-id="bd370-110">SIP Access</span></span>

<span data-ttu-id="bd370-111">ネットワークインターフェイスに割り当てられている外部 IP アドレスをセッション開始プロトコル (SIP) アクセス用に編集します。</span><span class="sxs-lookup"><span data-stu-id="bd370-111">Edit the external IP address that is assigned to the network interface for Session Initiation Protocol (SIP) access.</span></span> <span data-ttu-id="bd370-112">この IP アドレスは、パブリック IP アドレスまたはプライベート IP アドレス範囲内のアドレスのいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="bd370-112">This IP address can either be a public IP address or an address in the private IP address range.</span></span>
  
> [!NOTE]
> <span data-ttu-id="bd370-113">[ **Web 会議のために個別の FQDN と ip アドレスを有効にする] と**[プール設定] ページで [A/V] を有効にした場合、SIP アクセスの ip アドレスのみが編集可能になります。</span><span class="sxs-lookup"><span data-stu-id="bd370-113">If the setting **Enable separate FQDN and IP address for web conferencing and A/V** on the pool settings page is enabled, only the IP address for SIP access will be available for editing.</span></span>
  
## <a name="web-conferencing"></a><span data-ttu-id="bd370-114">Web 会議</span><span class="sxs-lookup"><span data-stu-id="bd370-114">Web Conferencing</span></span>

<span data-ttu-id="bd370-115">Web 会議用のネットワークインターフェイスに割り当てられている外部 IP アドレスを編集します。</span><span class="sxs-lookup"><span data-stu-id="bd370-115">Edit the external IP address that is assigned to the network interface for web conferencing.</span></span> <span data-ttu-id="bd370-116">この IP アドレスには、パブリック IP アドレス、またはプライベート IP アドレス範囲内のアドレスのいずれかを使うことができます。</span><span class="sxs-lookup"><span data-stu-id="bd370-116">This IP address can be either a public IP address or an address in the private IP address range.</span></span>
  
## <a name="audiovideo"></a><span data-ttu-id="bd370-117">音声/ビデオ</span><span class="sxs-lookup"><span data-stu-id="bd370-117">Audio/Video</span></span>

<span data-ttu-id="bd370-118">音声/ビデオ用のネットワークインターフェイス (A/V) に割り当てられている外部 IP アドレスを編集します。</span><span class="sxs-lookup"><span data-stu-id="bd370-118">Edit the external IP address that is assigned to the network interface for audio/video (A/V).</span></span> <span data-ttu-id="bd370-119">この IP アドレスには、パブリック IP アドレス、またはプライベート IP アドレス範囲内のアドレスのいずれかを使うことができます。</span><span class="sxs-lookup"><span data-stu-id="bd370-119">This IP address can be either a public IP address or an address in the private IP address range.</span></span>
  
<span data-ttu-id="bd370-120">[NAT を**有効にするパブリック IP アドレス**] の設定は、一般に、A/V ネットワークインターフェイスまたはエッジサーバーの外部インターフェイスで使用されるパブリックアドレスです。</span><span class="sxs-lookup"><span data-stu-id="bd370-120">The setting for **NAT enabled public IP address used** is the public address used by the external interface for either the A/V network interface or the Edge Server in general.</span></span> <span data-ttu-id="bd370-121">この設定で**web 会議で個別の FQDN と IP アドレスを有効にし、A/V**を有効にした場合、このパブリック IP アドレスがすべての3つの外部インターフェイスで使用されます。</span><span class="sxs-lookup"><span data-stu-id="bd370-121">If the setting **Enable separate FQDN and IP address for web conferencing and A/V** is enabled, this public IP address is used for all three external interfaces.</span></span>
  

