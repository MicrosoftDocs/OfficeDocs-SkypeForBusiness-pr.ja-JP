---
title: エッジ サーバーのオプションの追加
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeServerOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2405f227-4297-40d0-a117-55427a9e4052
ROBOTS: NOINDEX, NOFOLLOW
description: エッジ プールで有効にする各機能を選択します。既定では、エッジ プールは、仮想プライベート ネットワーク (VPN) を使用してファイアウォールの外側からサインインする、組織のリモート ユーザーをサポートします。以下のエッジ プール機能オプションも使用できます。
ms.openlocfilehash: ece46e3bfc3b399939197ac22429574a739d9761
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/28/2018
ms.locfileid: "23256386"
---
# <a name="add-edge-server-options"></a><span data-ttu-id="260d6-105">エッジ サーバーのオプションの追加</span><span class="sxs-lookup"><span data-stu-id="260d6-105">Add Edge Server Options</span></span>

<span data-ttu-id="260d6-p102">エッジ プールで有効にする各機能を選択します。既定では、エッジ プールは、仮想プライベート ネットワーク (VPN) を使用してファイアウォールの外側からサインインする、組織のリモート ユーザーをサポートします。以下のエッジ プール機能オプションも使用できます。</span><span class="sxs-lookup"><span data-stu-id="260d6-p102">Select each feature that you want to enable for the Edge pool. By default, the Edge pool supports remote users in your organization who sign in to from outside the firewall by using a virtual private network (VPN). You also have the following Edge pool feature options:</span></span>

- <span data-ttu-id="260d6-109">アクセス エッジ サービス、Web 会議エッジ サービス、音声ビデオ エッジ サービスなど、すべてのエッジ サービスに 1 つの完全修飾ドメイン名 (FQDN) と IP アドレスを使用する。</span><span class="sxs-lookup"><span data-stu-id="260d6-109">Use of a single fully qualified domain name (FQDN) and IP address for all edge services, including the Access Edge service, Web Conferencing Edge service, and A/V Edge service.</span></span> <span data-ttu-id="260d6-110">1 つの FQDN と IP アドレスを使用するオプションを選択しない場合、展開プロセスの一貫として、これらの 3 つの各エッジ サービスに個別の FQDN と IP アドレスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="260d6-110">If you do not select the option to use a single FQDN and IP address, you will need to specify a separate FQDN and IP address for each of these three Edge services as part of the deployment process.</span></span> <span data-ttu-id="260d6-111">エッジ サービスについての詳細は、計画のドキュメントで[外部ユーザー アクセスに必要なコンポーネント](https://technet.microsoft.com/library/2d0f9817-14e7-4109-95dc-62420e3c29e2.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="260d6-111">For details about the Edge services, see [Components Required for External User Access](https://technet.microsoft.com/library/2d0f9817-14e7-4109-95dc-62420e3c29e2.aspx) in the Planning documentation.</span></span>

    > [!NOTE]
    > <span data-ttu-id="260d6-p104">このオプションを選択する場合、各エッジ サービスに異なるポート番号を指定する必要があります (推奨される既定のポート設定:アクセス エッジ サービスに 444、Web 会議エッジ サービスに 8057、音声ビデオ エッジ サービスに 443)。このオプションを選択すると、潜在的な接続の問題を防ぐとともに、3 つのすべてのサービスに 1 つの FQDN を入力できるため、構成を簡素化することができます。</span><span class="sxs-lookup"><span data-stu-id="260d6-p104">If you select this option, you must specify a different port number for each of the Edge services (recommended default port settings: 444 for Access Edge service, 8057 for Web Conferencing Edge service, and 443 for A/V Edge service). Selecting this option can help prevent potential connectivity issues, and simplify the configuration because you can then enter one FQDN that is used for all three services.</span></span>

- <span data-ttu-id="260d6-114">フェデレーションのサポート。</span><span class="sxs-lookup"><span data-stu-id="260d6-114">Support for federation.</span></span> <span data-ttu-id="260d6-115">内部ユーザーと組織外部の信頼されるドメインのユーザー (サポートされるパブリック インスタント メッセージング (IM) プロバイダーのユーザーなど) との間の通信をサポートする必要がある場合は、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="260d6-115">Select this option if you want to support communication between internal users and users in trusted domains outside your organization, including any users of a supported public instant messaging (IM) provider.</span></span> <span data-ttu-id="260d6-116">このオプションを選択する場合、サポートする必要がある特定のフェデレーション ドメインとパブリック IM 接続サービス プロバイダーのサポートを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="260d6-116">If you select this option, you will need to configure support for the specific federated domains and public IM connectivity service providers that you want to support.</span></span> <span data-ttu-id="260d6-117">フェデレーションと外部ユーザー アクセスの他の種類のサポートを構成する方法の詳細は、エッジ サーバーの展開に関するドキュメントの[外部ユーザー アクセスのサポートを構成する](https://technet.microsoft.com/library/f8424f8c-f965-4414-8485-30f07e10214a.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="260d6-117">For details about configuring support for federation and other types of external user access, see [Configuring Support for External User Access](https://technet.microsoft.com/library/f8424f8c-f965-4414-8485-30f07e10214a.aspx) in the Edge Server Deployment documentation.</span></span>

    > [!NOTE]
    > <span data-ttu-id="260d6-p106">組織内の 1 つのフロントエンド プールまたは Standard エッジ サーバーのみ、フェデレーション用に外部に公開できます。パブリック IM ユーザーを含め、フェデレーション ユーザーによるすべてのアクセスが同じエッジ プールまたは単一エッジ サーバーを通過します。たとえば、ニューヨークとロンドンにそれぞれ展開されているエッジ プールまたは単一エッジ サーバーが展開に含まれている場合、ニューヨークのエッジ プールまたは単一エッジ サーバーでフェデレーション サポートを有効にすると、フェデレーション ユーザーの信号トラフィックはニューヨークのエッジ プールまたは単一エッジ サーバーを通過します。これは、ロンドンのユーザーとの通信の場合でも同じです。ただし、ロンドンの内部ユーザーがロンドンのフェデレーション ユーザーを呼び出す場合は、音声ビデオ トラフィックにロンドンのプールまたはエッジ サーバーを使用します。</span><span class="sxs-lookup"><span data-stu-id="260d6-p106">Only one Front End pool or Standard Edge Server in your organization may be published externally for federation. All access by federated users, including public IM users, go through the same Edge pool or single Edge Server. For instance, if your deployment includes an Edge pool or single Edge Server deployed in New York and one deployed in London and you enable federation support on the New York Edge pool or single Edge Server, signal traffic for federated users will go through the New York Edge pool or single Edge Server. This is true even for communications with London users, although a London internal user calling a London federated user uses the London pool or Edge Server for A/V traffic.</span></span>

- <span data-ttu-id="260d6-p107">XMPP フェデレーションを有効にします。内部ユーザーと信頼された XMPP パートナーとの間の通信をサポートする場合は、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="260d6-p107">Enable XMPP federation. Select this option if you want to support communication between internal users and trusted XMPP partners.</span></span>

<span data-ttu-id="260d6-124">最初のトポロジの展開時やその後に、外部ユーザー アクセスのサポートを追加できます。</span><span class="sxs-lookup"><span data-stu-id="260d6-124">You can add support for external user access when you deploy your initial topology or afterward.</span></span> <span data-ttu-id="260d6-125">既存のトポロジにエッジ サーバーを追加する方法の詳細は、エッジ サーバーの展開に関するドキュメントの「[エッジ トポロジ定義](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="260d6-125">For details about adding Edge Servers to an existing topology, see [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx) in the Edge Server Deployment documentation.</span></span>


