---
title: エッジのマシンの設定の拡張
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeMachineSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 747456dd-d237-44e6-9e64-63b0e7212a08
description: エッジ サーバーのプール内のサーバーのプロパティを編集するには、次の操作を行います。
ms.openlocfilehash: 04b8d8efc455203e49aeb81e533604a405e37cc5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="edge-machine-settings-expander"></a><span data-ttu-id="615fe-103">エッジのマシンの設定の拡張</span><span class="sxs-lookup"><span data-stu-id="615fe-103">Edge Machine Settings Expander</span></span>
 
<span data-ttu-id="615fe-104">エッジ サーバーのプール内のサーバーのプロパティを編集するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="615fe-104">To edit the properties for a server in a pool of Edge Servers, do the following:</span></span>
  
<span data-ttu-id="615fe-105">**内部名または FQDN**は、完全修飾ドメイン名 (FQDN) を編集することによって変更できます。</span><span class="sxs-lookup"><span data-stu-id="615fe-105">The **Internal name or FQDN** can be changed by editing the fully qualified domain name (FQDN).</span></span> <span data-ttu-id="615fe-106">FQDN は、ドメイン ネーム システム (DNS) ホスト (a) レコード、および内部の境界ネットワーク インターフェイスのサーバーに割り当てられている証明書のサブジェクト名と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="615fe-106">The FQDN must match the Domain Name System (DNS) host (A) record, and the subject name of the certificate assigned to the server for the internal Edge network interface.</span></span> <span data-ttu-id="615fe-107">**内部 IP アドレス**の値は、内部ネットワーク、境界ネットワークの設計を基準として定義されているネットワーク ・ インタ フェースに割り当てられている IP アドレスを定義します。</span><span class="sxs-lookup"><span data-stu-id="615fe-107">The value of **Internal IP address** defines the IP address that is assigned the network interface that is defined as an internal network, relative to the perimeter network design.</span></span>
  
<span data-ttu-id="615fe-108">ダイアログ ボックスの次の 3 つのセクションでは、このエッジ サーバーの外部構成の IP アドレスを定義します。</span><span class="sxs-lookup"><span data-stu-id="615fe-108">The next three sections of the dialog define the IP addresses for the external configuration of this Edge Server.</span></span> <span data-ttu-id="615fe-109">設定で IP アドレスを変更する機能が影響を受ける**を有効にする別の FQDN と IP アドレスの web 会議および A/V**プール レベルのエッジ サーバーでプロパティの設定に。</span><span class="sxs-lookup"><span data-stu-id="615fe-109">The ability to change the IP addresses is affected by the setting **Enable separate FQDN and IP address for web conferencing and A/V** on the Properties settings at the Edge Server pool level.</span></span>
  
## <a name="sip-access"></a><span data-ttu-id="615fe-110">SIP アクセス</span><span class="sxs-lookup"><span data-stu-id="615fe-110">SIP Access</span></span>

<span data-ttu-id="615fe-111">セッション開始プロトコル (SIP) アクセス用のネットワーク インターフェイスに割り当てられている外部 IP アドレスを編集します。</span><span class="sxs-lookup"><span data-stu-id="615fe-111">Edit the external IP address that is assigned to the network interface for Session Initiation Protocol (SIP) access.</span></span> <span data-ttu-id="615fe-112">この IP アドレスは IP アドレスをパブリックまたはプライベート IP アドレスの範囲内のアドレスのいずれかできます。</span><span class="sxs-lookup"><span data-stu-id="615fe-112">This IP address can either be a public IP address or an address in the private IP address range.</span></span>
  
> [!NOTE]
> <span data-ttu-id="615fe-113">場合設定**を有効にする別の FQDN と IP アドレスの web 会議および A/V**プールの設定] ページが有効なだけで SIP アクセス用の IP アドレスを編集可能になります。</span><span class="sxs-lookup"><span data-stu-id="615fe-113">If the setting **Enable separate FQDN and IP address for web conferencing and A/V** on the pool settings page is enabled, only the IP address for SIP access will be available for editing.</span></span>
  
## <a name="web-conferencing"></a><span data-ttu-id="615fe-114">Web 会議</span><span class="sxs-lookup"><span data-stu-id="615fe-114">Web Conferencing</span></span>

<span data-ttu-id="615fe-115">Web 会議のネットワーク インターフェイスに割り当てられている外部 IP アドレスを編集します。</span><span class="sxs-lookup"><span data-stu-id="615fe-115">Edit the external IP address that is assigned to the network interface for web conferencing.</span></span> <span data-ttu-id="615fe-116">この IP アドレスには、パブリック IP アドレスまたはプライベート IP アドレスの範囲内のアドレスのいずれかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="615fe-116">This IP address can be either a public IP address or an address in the private IP address range.</span></span>
  
## <a name="audiovideo"></a><span data-ttu-id="615fe-117">オーディオ/ビデオ</span><span class="sxs-lookup"><span data-stu-id="615fe-117">Audio/Video</span></span>

<span data-ttu-id="615fe-118">オーディオとビデオのネットワーク インターフェイスに割り当てられている外部 IP アドレスの編集 (A/V)。</span><span class="sxs-lookup"><span data-stu-id="615fe-118">Edit the external IP address that is assigned to the network interface for audio/video (A/V).</span></span> <span data-ttu-id="615fe-119">この IP アドレスには、パブリック IP アドレスまたはプライベート IP アドレスの範囲内のアドレスのいずれかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="615fe-119">This IP address can be either a public IP address or an address in the private IP address range.</span></span>
  
<span data-ttu-id="615fe-120">**NAT には、使用するパブリック IP アドレスが有効になっている**は、どちらか A の外部インターフェイスで使用されるパブリック アドレス V インターフェイスまたはエッジ サーバーの一般的なネットワークです。</span><span class="sxs-lookup"><span data-stu-id="615fe-120">The setting for **NAT enabled public IP address used** is the public address used by the external interface for either the A/V network interface or the Edge Server in general.</span></span> <span data-ttu-id="615fe-121">場合設定**を有効にする別の FQDN と IP アドレスの web 会議および A/V**が有効にすると、このパブリック IP アドレスがすべての 3 つの外部インターフェイスの使用します。</span><span class="sxs-lookup"><span data-stu-id="615fe-121">If the setting **Enable separate FQDN and IP address for web conferencing and A/V** is enabled, this public IP address is used for all three external interfaces.</span></span>
  

