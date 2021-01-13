---
title: エッジ コンピューター設定エキスパンダー
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
- ms.lync.tb.EdgeMachineSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 747456dd-d237-44e6-9e64-63b0e7212a08
description: エッジ サーバーのプール内にあるサーバーのプロパティを編集するには、次の操作を行います。
ms.openlocfilehash: 7c3b3d45617d8feeee062bb16e1c7222b71118d8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49807127"
---
# <a name="edge-machine-settings-expander"></a><span data-ttu-id="20898-103">エッジ コンピューター設定エキスパンダー</span><span class="sxs-lookup"><span data-stu-id="20898-103">Edge Machine Settings Expander</span></span>
 
<span data-ttu-id="20898-104">エッジ サーバーのプール内にあるサーバーのプロパティを編集するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="20898-104">To edit the properties for a server in a pool of Edge Servers, do the following:</span></span>
  
<span data-ttu-id="20898-p101">[**内部名または FQDN**] を変更するには、完全修飾ドメイン名 (FQDN) を編集します。FQDN が、ドメイン ネーム システム (DNS) ホスト (A) レコード、および内部エッジ ネットワーク インターフェイスのサーバーに割り当てられている証明書のサブジェクト名と一致している必要があります。[**内部 IP アドレス**] の値で、境界ネットワーク設定に関連して、内部ネットワークとして定義されたネットワーク インターフェイスに割り当てられる IP アドレスを定義します。</span><span class="sxs-lookup"><span data-stu-id="20898-p101">The **Internal name or FQDN** can be changed by editing the fully qualified domain name (FQDN). The FQDN must match the Domain Name System (DNS) host (A) record, and the subject name of the certificate assigned to the server for the internal Edge network interface. The value of **Internal IP address** defines the IP address that is assigned the network interface that is defined as an internal network, relative to the perimeter network design.</span></span>
  
<span data-ttu-id="20898-p102">ダイアログの次の 3 つのセクションで、このエッジ サーバーの外部構成の IP アドレスを定義します。IP アドレスを変更できるかどうかは、エッジ サーバーのプール レベルでの [プロパティ] 設定の [**Web 会議と音声ビデオに対する別々の FQDN および IP アドレス設定の有効化**] の設定の影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="20898-p102">The next three sections of the dialog define the IP addresses for the external configuration of this Edge Server. The ability to change the IP addresses is affected by the setting **Enable separate FQDN and IP address for web conferencing and A/V** on the Properties settings at the Edge Server pool level.</span></span>
  
## <a name="sip-access"></a><span data-ttu-id="20898-110">SIP アクセス</span><span class="sxs-lookup"><span data-stu-id="20898-110">SIP Access</span></span>

<span data-ttu-id="20898-p103">セッション開始プロトコル (SIP) アクセスのネットワーク インターフェイスに割り当てられている外部 IP アドレスを編集します。この IP アドレスは、パブリック IP アドレスまたはプライベート IP アドレス範囲内のアドレスのどちらにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="20898-p103">Edit the external IP address that is assigned to the network interface for Session Initiation Protocol (SIP) access. This IP address can either be a public IP address or an address in the private IP address range.</span></span>
  
> [!NOTE]
> <span data-ttu-id="20898-113">プール設定ページの [**Web 会議と音声ビデオに個別の FQDN と IP アドレスを有効にする**] が有効になっている場合、SIP アクセスの IP アドレスのみ編集できます。</span><span class="sxs-lookup"><span data-stu-id="20898-113">If the setting **Enable separate FQDN and IP address for web conferencing and A/V** on the pool settings page is enabled, only the IP address for SIP access will be available for editing.</span></span>
  
## <a name="web-conferencing"></a><span data-ttu-id="20898-114">Web 会議</span><span class="sxs-lookup"><span data-stu-id="20898-114">Web Conferencing</span></span>

<span data-ttu-id="20898-p104">Web 会議のネットワーク インターフェイスに割り当てられている外部 IP アドレスを編集します。この IP アドレスは、パブリック IP アドレスまたはプライベート IP アドレス範囲内のアドレスのどちらにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="20898-p104">Edit the external IP address that is assigned to the network interface for web conferencing. This IP address can be either a public IP address or an address in the private IP address range.</span></span>
  
## <a name="audiovideo"></a><span data-ttu-id="20898-117">オーディオ/ビデオ</span><span class="sxs-lookup"><span data-stu-id="20898-117">Audio/Video</span></span>

<span data-ttu-id="20898-p105">音声ビデオ (A/V) のネットワーク インターフェイスに割り当てられている外部 IP アドレスを編集します。この IP アドレスは、パブリック IP アドレスまたはプライベート IP アドレス範囲内のアドレスのどちらにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="20898-p105">Edit the external IP address that is assigned to the network interface for audio/video (A/V). This IP address can be either a public IP address or an address in the private IP address range.</span></span>
  
<span data-ttu-id="20898-p106">通常、[**NAT が有効な使用中のパブリック IP アドレス**] の設定は、音声ビデオ ネットワーク インターフェイスまたはエッジ サーバーの外部インターフェイスで使用されるパブリック アドレスです。[**Web 会議と音声ビデオに個別の FQDN と IP アドレスを有効にする**] が有効になっている場合、このパブリック IP アドレスが 3 つのすべての外部インターフェイスに使用されます。</span><span class="sxs-lookup"><span data-stu-id="20898-p106">The setting for **NAT enabled public IP address used** is the public address used by the external interface for either the A/V network interface or the Edge Server in general. If the setting **Enable separate FQDN and IP address for web conferencing and A/V** is enabled, this public IP address is used for all three external interfaces.</span></span>
  

