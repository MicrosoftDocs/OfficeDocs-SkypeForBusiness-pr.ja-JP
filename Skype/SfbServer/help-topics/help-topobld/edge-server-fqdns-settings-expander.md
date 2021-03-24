---
title: エッジ サーバーの FQDN 設定エキスパンダー
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.EdgeFqdnsSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9e4e9445-0147-4dd6-84f0-b41de142b332
description: エッジ サーバーの外部設定を編集または指定するには、まず、セッション開始プロトコル (SIP) アクセス、Web 会議エッジ サービス、およびオーディオ/ビデオ エッジ サービスに個別の IP アドレスを使用する必要があります。
ms.openlocfilehash: d2589ccd8bcd3d7f7bfccd39e3adf726f8839ad8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095562"
---
# <a name="edge-server-fqdns-settings-expander"></a><span data-ttu-id="26be0-103">エッジ サーバーの FQDN 設定エキスパンダー</span><span class="sxs-lookup"><span data-stu-id="26be0-103">Edge Server FQDNs Settings Expander</span></span>

<span data-ttu-id="26be0-104">エッジ サーバーの **外部** 設定を編集または指定するには、まず、セッション開始プロトコル (SIP) アクセス、Web 会議エッジ サービス、およびオーディオ/ビデオ エッジ サービスに個別の IP アドレスを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="26be0-104">To edit or specify **External Settings** for the Edge Servers, you first must determine if you will use separate IP addresses for Session Initiation Protocol (SIP) access, the Web Conferencing Edge service, and the Audio/Video Edge service.</span></span>

<span data-ttu-id="26be0-p101">各サービスで別々の IP アドレスを使用する場合は、**[Web 会議と音声ビデオで別々の FQDN と IP アドレスを有効にする]** チェック ボックスをオンにします。それぞれのサービスでは、そのサービス用に、対応するドメイン ネーム システム (DNS) ホスト (A) レコードが作成されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="26be0-p101">If you intend to use separate IP addresses for each, select the check box **Enable separate FQDN and IP address for Web conferencing and A/V**. Each service must have a corresponding Domain Name System (DNS) host (A) record created for it.</span></span>

<span data-ttu-id="26be0-p102">外部に提供されるサービスのそれぞれで、完全修飾ドメイン名 (FQDN) と、関連付けられたポートを指定します。たとえば、[**SIP アドレス**] として、関連付けられたポートを 5061 にして sip.contoso.com を使用できます。</span><span class="sxs-lookup"><span data-stu-id="26be0-p102">For each of the external-facing services, specify a fully qualified domain name (FQDN) and an associated port. For example, for **SIP Access**, you might use sip.contoso.com with an associated port of 5061.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="26be0-p103">外部に提供される各サービスで別々の FQDN を使用する場合は、各サービスに固有のポート値を関連付ける必要があります。既定では、SIP がポート 5061/TLS、Web 会議エッジ サービスがポート 444/TLS、および音声ビデオ会議エッジ サービスがポート 443/TLS で提供されます。別々の FQDN と IP アドレス、またはポートを使用することを含め、これらの設定に変更を加える場合は、最初に構成された値に依存する他のすべてのサービスを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="26be0-p103">If you select separate FQDNs for each of the external-facing services, each service must have a unique port value associated with it. By default, SIP is on port 5061/TLS, the Web Conferencing Edge service is on port 444/TLS, and the A/V Conferencing Edge service is on port 443/TLS. If you make changes to any of these settings, including using separate FQDN and IP addresses or ports, you must update all other services that will rely on the initially configured values.</span></span>

<span data-ttu-id="26be0-p104">外部に提供されるサービスのために、組織では 1 つの FQDN と IP アドレスを使用することを決定した場合は、[**Web 会議と音声ビデオで別々の FQDN と IP アドレスを有効にする**] チェック ボックスをオフにします。必要に応じて、[**SIP アクセス**] のプールの FQDN とポート値を編集できます。</span><span class="sxs-lookup"><span data-stu-id="26be0-p104">If you determine that your organization will use a single FQDN and IP address for the external-facing services, clear the **Enable separate FQDN and IP address for Web conferencing and A/V** check box. You can then edit the **SIP Access** pool FQDN and port values, if necessary.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="26be0-114">別々の FQDN および IP アドレスまたはポートを使用することを含め、これらの設定のいずれかに変更を加える場合は、最初に構成された値に依存する他のすべてのサービスを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="26be0-114">If you make changes to any of these settings, including using separate FQDN and IP addresses or ports, you must update all other services that will rely on the initially configured values.</span></span>

<span data-ttu-id="26be0-115">エッジ サービスの設定の定義と構成の詳細については [、「Define Your Edge Topology 」を参照してください](/previous-versions/office/lync-server-2013/lync-server-2013-define-your-edge-topology)。</span><span class="sxs-lookup"><span data-stu-id="26be0-115">For details about defining and configuring the settings for the Edge services, see [Define Your Edge Topology](/previous-versions/office/lync-server-2013/lync-server-2013-define-your-edge-topology).</span></span>