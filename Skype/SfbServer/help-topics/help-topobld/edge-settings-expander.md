---
title: エッジ設定エキスパンダー
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.EdgeSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c73780cd-0033-4287-9ecd-ecf65ca61e62
description: 既存の単一サーバー エッジ プールまたは複数サーバー エッジ プールの設定を編集するために、次のセクションが表示されます。
ms.openlocfilehash: cdc197bb5e6255a9ad0ff69110435908bf6156d5
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2020
ms.locfileid: "41684740"
---
# <a name="edge-settings-expander"></a><span data-ttu-id="1116d-103">エッジ設定エキスパンダー</span><span class="sxs-lookup"><span data-stu-id="1116d-103">Edge Settings Expander</span></span>

<span data-ttu-id="1116d-104">既存の単一サーバー エッジ プールまたは複数サーバー エッジ プールの設定を編集するために、次のセクションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1116d-104">To edit the settings for an existing single or multiple server Edge pool, you are presented with the following sections:</span></span>

- <span data-ttu-id="1116d-105">全般設定</span><span class="sxs-lookup"><span data-stu-id="1116d-105">General settings</span></span>

- <span data-ttu-id="1116d-106">次ホップ選択設定</span><span class="sxs-lookup"><span data-stu-id="1116d-106">Next hop selection settings</span></span>

- <span data-ttu-id="1116d-107">エッジ サーバー構成</span><span class="sxs-lookup"><span data-stu-id="1116d-107">Edge Server configuration</span></span>



## <a name="general-settings"></a><span data-ttu-id="1116d-108">全般設定</span><span class="sxs-lookup"><span data-stu-id="1116d-108">General settings</span></span>

<span data-ttu-id="1116d-p101">エッジ サーバー プールの内部プールの完全修飾ドメイン名 (FQDN)。この設定を変更するには、プールの FQDN を編集します。</span><span class="sxs-lookup"><span data-stu-id="1116d-p101">Internal pool fully qualified domain name (FQDN) of the Edge Server pool. Edit the FQDN of the pool to change this setting.</span></span>

<span data-ttu-id="1116d-111">Lync Server 2013、Microsoft Lync Server 2010、または Microsoft Office Communications Server 2007 R2 trusted partner とのフェデレーションを設定する場合は、チェックボックスをオンにして、**このエッジプール (ポート 5061) との**フェデレーションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="1116d-111">Select the check box **Enable federation for this Edge pool (Port 5061)** if you will set up federation with a Lync Server 2013, Microsoft Lync Server 2010 or Microsoft Office Communications Server 2007 R2 trusted partner.</span></span>

<span data-ttu-id="1116d-112">[**このエッジ プールの XMPP フェデレーションを有効化 (ポート 5269)**] を選択して、XMPP フェデレーションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="1116d-112">Select **Enable XMPP federation for this Edge pool** to enable XMPP federation.</span></span>

<span data-ttu-id="1116d-113">[**内部構成レプリケーション ポート (HTTPS)**] に対してポート番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="1116d-113">Specify the port number for **Internal Configuration Replication Port (HTTPS)**.</span></span>

## <a name="next-hop-selection-settings"></a><span data-ttu-id="1116d-114">次ホップ選択設定</span><span class="sxs-lookup"><span data-stu-id="1116d-114">Next hop selection settings</span></span>

<span data-ttu-id="1116d-115">エッジ サーバーが内部インフラストラクチャと通信するために使用する [**次ホップ プール**] を設定または変更するには、ドロップダウン リスト ボックスからディレクター、ディレクター プール、フロントエンド サーバー、またはフロントエンド サーバーのプールを選択します。</span><span class="sxs-lookup"><span data-stu-id="1116d-115">To set or modify the **Next hop pool** that the Edge Servers will use to communicate to the internal infrastructure, select a Director, Director pool, Front End Server, or Front End Server pool from the drop-down list box.</span></span> <span data-ttu-id="1116d-116">選択できるように、トポロジビルダーで構成されているディレクターまたはフロントエンドのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1116d-116">Only Directors or Front Ends that have been configured in Topology Builder will appear for selection.</span></span>

## <a name="edge-server-configuration"></a><span data-ttu-id="1116d-117">エッジ サーバー構成</span><span class="sxs-lookup"><span data-stu-id="1116d-117">Edge Server configuration</span></span>

<span data-ttu-id="1116d-118">エッジ サーバーの [**外部設定**] の設定を編集または指定するには、まず SIP アクセス、Web 会議、および音声ビデオ サービスに個別の IP アドレスを使用するかどうかを判断する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1116d-118">To edit or specify settings for the **External Settings** for the Edge Servers, you first must determine if you will use separate IP addresses for SIP access, web conferencing, and the Audio/Video service.</span></span>

<span data-ttu-id="1116d-p103">各サービスで別々の IP アドレスを使用する場合は、[**Web 会議と音声ビデオで別々の FQDN と IP アドレスを有効にする**] チェック ボックスをオンにします。各サービスに、それぞれに作成された対応する DNS ホスト (A) レコードが存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="1116d-p103">If you intend to use separate IP addresses for each, select the check box **Enable separate FQDN and IP address for Web conferencing and A/V**. Each service must have a corresponding DNS host (A) record created for it.</span></span>

<span data-ttu-id="1116d-p104">各外部サービスについて、FQDN および関連付けられたポートを指定します。たとえば、[**SIP アクセス**] に sip.contoso.com および関連付けられたポート 5061 を使用します。</span><span class="sxs-lookup"><span data-stu-id="1116d-p104">For each of the external-facing services, you specify a FQDN and an associated port. For example, the **SIP Access** would use sip.contoso.com with an associated port of 5061.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1116d-p105">外部に提供される各サービスで別々の FQDN を使用する場合は、各サービスに固有のポート値を関連付ける必要があります。既定では、SIP はポート 5061/TLS で、Web 会議エッジ サービスはポート 444/TLS で、音声ビデオ会議サーバーはポート 443/TLS です。別々の FQDN と IP アドレス、またはポートを使用することを含め、これらの設定に変更を加える場合は、最初に構成された値に依存する他のすべてのサービスを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1116d-p105">If you select separate FQDNs for each of the external-facing services, each service must have a unique port value associated with it. By default, the SIP is on port 5061/TLS, the web conferencing edge service is on port 444/TLS, and the A/V Conferencing Server is on port 443/TLS. If you make changes to any of these settings, including using separate FQDN and IP addresses or ports, you must update all the other services that will rely on the initially configured values.</span></span>

<span data-ttu-id="1116d-p106">外部に提供されるサービスのために、組織では 1 つの FQDN と IP アドレスを使用することを決定した場合は、[**Web 会議と音声ビデオで別々の FQDN と IP アドレスを有効にする**] チェック ボックスをオフにします。必要に応じて、[**SIP アクセス**] のプールの FQDN とポート値を編集できます。</span><span class="sxs-lookup"><span data-stu-id="1116d-p106">If you determine that your organization will use a single FQDN and IP address for the external-facing services, clear the **Enable separate FQDN and IP address for Web conferencing and A/V** check box. You can then edit the **SIP Access** pool FQDN and port values, if necessary.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1116d-128">別々の FQDN および IP アドレスまたはポートを使用することを含め、これらの設定のいずれかに変更を加える場合は、最初に構成された値に依存する他のすべてのサービスを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1116d-128">If you make changes to any of these settings, including using separate FQDN and IP addresses or ports, you must update all other services that will rely on the initially configured values.</span></span>

## <a name="see-also"></a><span data-ttu-id="1116d-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="1116d-129">See also</span></span>

<span data-ttu-id="1116d-130">エッジ サービスの設定の定義および構成の詳細については、「[Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1116d-130">For details about defining and configuring the settings for the Edge Services, see [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx).</span></span>


