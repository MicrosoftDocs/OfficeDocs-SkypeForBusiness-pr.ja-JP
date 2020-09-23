---
title: Lync Server 2010 用の仲介サーバー全般設定の展開
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.MediationServerGeneralSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 48e434c1-0c3c-4502-9441-c0a3c340f51f
description: このダイアログでは、仲介サーバーのプロパティを編集します。 左側にクイック リンクのセットがあり、これらにより、[全般] 設定、[次ホップ] 設定、および [PSTN ゲートウェイ] 設定の設定に移動できます。 各セクションには次の設定があります。
ms.openlocfilehash: 19687f8d6a97a9174782c094f80c5b52d6973caf
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "48215158"
---
# <a name="mediation-server-general-settings-expander-for-lync-server-2010"></a><span data-ttu-id="2f3ad-105">Lync Server 2010 用の仲介サーバー全般設定の展開</span><span class="sxs-lookup"><span data-stu-id="2f3ad-105">Mediation Server General Settings Expander for Lync Server 2010</span></span>

<span data-ttu-id="2f3ad-106">このダイアログでは、仲介サーバーのプロパティを編集します。</span><span class="sxs-lookup"><span data-stu-id="2f3ad-106">You edit the properties of the Mediation Servers in this dialog.</span></span> <span data-ttu-id="2f3ad-107">左側にクイック リンクのセットがあり、これらにより、[全般] 設定、[次ホップ] 設定、および [PSTN ゲートウェイ] 設定の設定に移動できます。</span><span class="sxs-lookup"><span data-stu-id="2f3ad-107">Along the left side is a set of quick links to take you to settings for General settings, Next hop settings, and PSTN gateway settings.</span></span> <span data-ttu-id="2f3ad-108">各セクションには次の設定があります。</span><span class="sxs-lookup"><span data-stu-id="2f3ad-108">In each section are the following settings:</span></span>

 <span data-ttu-id="2f3ad-109">**全般**:</span><span class="sxs-lookup"><span data-stu-id="2f3ad-109">**General**:</span></span>

- <span data-ttu-id="2f3ad-110">**FQDN**: 仲介サーバーの完全修飾ドメイン名を編集します。</span><span class="sxs-lookup"><span data-stu-id="2f3ad-110">**FQDN**: You edit the fully qualified domain name of the Mediation Server</span></span>

- <span data-ttu-id="2f3ad-111">[**関連付け**]: [**エッジプールの関連付け (メディアコンポーネント用)** ] チェックボックスをオンにし、仲介サーバーが外部アクセスのメディアパスとして使用するエッジサーバーまたはエッジプールを選択します。</span><span class="sxs-lookup"><span data-stu-id="2f3ad-111">**Associations**: Select the **Associate Edge pool (for media components)** check box and select an Edge Server or Edge pool for the Mediation Server to use as the media path for external access.</span></span>

  <span data-ttu-id="2f3ad-112">[**次ホップ**]:</span><span class="sxs-lookup"><span data-stu-id="2f3ad-112">**Next hop**:</span></span>

- <span data-ttu-id="2f3ad-113">**[次ホップの選択**]: 展開との通信に使用する仲介サーバーのパスとして使用するフロントエンドサーバーまたはフロントエンドプールをリストから選択します。</span><span class="sxs-lookup"><span data-stu-id="2f3ad-113">**Next hop selection**: Select from a list the Front End Server or Front End pool to use as the path for the Mediation Server to use for communicating with your deployment.</span></span>

  <span data-ttu-id="2f3ad-114">[**PSTN ゲートウェイ**]:</span><span class="sxs-lookup"><span data-stu-id="2f3ad-114">**PSTN gateway**:</span></span>

  <span data-ttu-id="2f3ad-115">[**仲介サーバーの PSTN ゲートウェイ**]:</span><span class="sxs-lookup"><span data-stu-id="2f3ad-115">**Mediation Server PSTN gateway**:</span></span>

- <span data-ttu-id="2f3ad-116">**リスニングポート**: 仲介サーバーがリッスンするポートを定義します。</span><span class="sxs-lookup"><span data-stu-id="2f3ad-116">**Listening ports**: Define the ports that the Mediation Server will listen on.</span></span> <span data-ttu-id="2f3ad-117">**TLS** (トランスポート層セキュリティ) または **TCP** (伝送制御プロトコル) 用のポートを定義できます。</span><span class="sxs-lookup"><span data-stu-id="2f3ad-117">You can define a port for **TLS** or transport layer security, or **TCP**, or transport control protocol.</span></span> <span data-ttu-id="2f3ad-118">TCP 用のポート エントリを利用できるようにするには、[**TCP ポートを有効にする**] チェック ボックスをオンにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f3ad-118">For the port entry for TCP to be available, you must select the check box for **Enable TCP port**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="2f3ad-119">ご使用の公衆交換電話網 (PSTN) ゲートウェイのドキュメントおよび構成設定を参照し、ポート値 TLS、TCP、またはその両方の有効化および定義が必要かどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="2f3ad-119">Refer to the documentation and configuration settings for your public switched telephone network (PSTN) gateway to determine if you need to enable and define port values TLS, TCP or both.</span></span> <span data-ttu-id="2f3ad-120">TLS は、証明書を使用して仲介サーバーと PSTN ゲートウェイ間のトラフィックを暗号化する、より安全なプロトコルです。</span><span class="sxs-lookup"><span data-stu-id="2f3ad-120">TLS is a more secure protocol, using certificates to encrypt the traffic between the Mediation Server and the PSTN gateway.</span></span> <span data-ttu-id="2f3ad-121">すべての PSTN ゲートウェイが TLS をサポートするわけではありません。</span><span class="sxs-lookup"><span data-stu-id="2f3ad-121">Not all PSTN gateways support TLS.</span></span>

- <span data-ttu-id="2f3ad-122">展開で定義および構成されている SIP トランクおよびゲートウェイのリストが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="2f3ad-122">A listing of SIP trunks and the gateways that are defined and configured for your deployment is listed.</span></span> <span data-ttu-id="2f3ad-123">エントリが存在しない場合、ご使用の展開で構成されている SIP トランクまたは PSTN ゲートウェイはありません。</span><span class="sxs-lookup"><span data-stu-id="2f3ad-123">If no entries are present, there are no SIP trunks or PSTN gateways configured for your deployment.</span></span> <span data-ttu-id="2f3ad-124">トポロジビルダーの [ **共有コンポーネント** ] で、トランクとゲートウェイを定義して構成します。</span><span class="sxs-lookup"><span data-stu-id="2f3ad-124">You define and configure trunks and gateways under **Shared Components** in Topology Builder.</span></span>

## <a name="see-also"></a><span data-ttu-id="2f3ad-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="2f3ad-125">See also</span></span>

[<span data-ttu-id="2f3ad-126">SIP トランキングの概要</span><span class="sxs-lookup"><span data-stu-id="2f3ad-126">Overview of SIP Trunking</span></span>](https://technet.microsoft.com/library/204f2c21-436f-4b2d-93ea-d6db98fa2952.aspx)

[<span data-ttu-id="2f3ad-127">PSTN ゲートウェイの展開オプション</span><span class="sxs-lookup"><span data-stu-id="2f3ad-127">PSTN Gateway Deployment Options</span></span>](https://technet.microsoft.com/library/d1ab4f74-18aa-40c7-a8cf-ec806cf6e28a.aspx)
