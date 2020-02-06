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
- NOCSH
ms.custom:
- ms.lync.tb.MediationServerGeneralSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 48e434c1-0c3c-4502-9441-c0a3c340f51f
description: このダイアログボックスで、仲介サーバーのプロパティを編集します。 左側には、[全般設定]、[次ホップの設定]、[PSTN ゲートウェイ] の設定の設定に移動するためのクイックリンクがあります。 各セクションには、次の設定があります。
ms.openlocfilehash: 3f7dad61778f54fee7a9be984191bc21f5029502
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41819619"
---
# <a name="mediation-server-general-settings-expander-for-lync-server-2010"></a><span data-ttu-id="fa972-105">Lync Server 2010 用の仲介サーバー全般設定の展開</span><span class="sxs-lookup"><span data-stu-id="fa972-105">Mediation Server General Settings Expander for Lync Server 2010</span></span>

<span data-ttu-id="fa972-106">このダイアログボックスで、仲介サーバーのプロパティを編集します。</span><span class="sxs-lookup"><span data-stu-id="fa972-106">You edit the properties of the Mediation Servers in this dialog.</span></span> <span data-ttu-id="fa972-107">左側には、[全般設定]、[次ホップの設定]、[PSTN ゲートウェイ] の設定の設定に移動するためのクイックリンクがあります。</span><span class="sxs-lookup"><span data-stu-id="fa972-107">Along the left side is a set of quick links to take you to settings for General settings, Next hop settings, and PSTN gateway settings.</span></span> <span data-ttu-id="fa972-108">各セクションには、次の設定があります。</span><span class="sxs-lookup"><span data-stu-id="fa972-108">In each section are the following settings:</span></span>

 <span data-ttu-id="fa972-109">**一般的な**方法:</span><span class="sxs-lookup"><span data-stu-id="fa972-109">**General**:</span></span>

- <span data-ttu-id="fa972-110">[ **FQDN**: 仲介サーバーの完全修飾ドメイン名を編集します。</span><span class="sxs-lookup"><span data-stu-id="fa972-110">**FQDN**: You edit the fully qualified domain name of the Mediation Server</span></span>

- <span data-ttu-id="fa972-111">[**関連付け**]: [ **Edge プールを関連付ける (メディアコンポーネント用)** ] チェックボックスをオンにし、仲介サーバーが外部アクセスのメディアパスとして使用するエッジサーバーまたはエッジプールを選択します。</span><span class="sxs-lookup"><span data-stu-id="fa972-111">**Associations**: Select the **Associate Edge pool (for media components)** check box and select an Edge Server or Edge pool for the Mediation Server to use as the media path for external access.</span></span>

  <span data-ttu-id="fa972-112">**次のホップ**:</span><span class="sxs-lookup"><span data-stu-id="fa972-112">**Next hop**:</span></span>

- <span data-ttu-id="fa972-113">**[次のホップの選択**]: 展開との通信に使用する仲介サーバーのパスとして使用するフロントエンドサーバーまたはフロントエンドプールの一覧から選択します。</span><span class="sxs-lookup"><span data-stu-id="fa972-113">**Next hop selection**: Select from a list the Front End Server or Front End pool to use as the path for the Mediation Server to use for communicating with your deployment.</span></span>

  <span data-ttu-id="fa972-114">**PSTN ゲートウェイ**:</span><span class="sxs-lookup"><span data-stu-id="fa972-114">**PSTN gateway**:</span></span>

  <span data-ttu-id="fa972-115">**仲介サーバー PSTN ゲートウェイ**:</span><span class="sxs-lookup"><span data-stu-id="fa972-115">**Mediation Server PSTN gateway**:</span></span>

- <span data-ttu-id="fa972-116">**リスニングポート**: 仲介サーバーがリッスンするポートを定義します。</span><span class="sxs-lookup"><span data-stu-id="fa972-116">**Listening ports**: Define the ports that the Mediation Server will listen on.</span></span> <span data-ttu-id="fa972-117">**TLS**またはトランスポート層のセキュリティ、 **TCP**、またはトランスポート制御プロトコルのポートを定義できます。</span><span class="sxs-lookup"><span data-stu-id="fa972-117">You can define a port for **TLS** or transport layer security, or **TCP**, or transport control protocol.</span></span> <span data-ttu-id="fa972-118">TCP 用のポートエントリを利用できるようにするには、[ **tcp ポートを有効**にする] チェックボックスをオンにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa972-118">For the port entry for TCP to be available, you must select the check box for **Enable TCP port**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="fa972-119">ポート値 TLS、TCP、またはその両方を有効にする必要があるかどうかを判断するには、公衆交換電話網 (PSTN) ゲートウェイのドキュメントと構成の設定を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fa972-119">Refer to the documentation and configuration settings for your public switched telephone network (PSTN) gateway to determine if you need to enable and define port values TLS, TCP or both.</span></span> <span data-ttu-id="fa972-120">TLS はセキュリティで保護されたプロトコルであり、証明書を使って仲介サーバーと PSTN ゲートウェイ間のトラフィックを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="fa972-120">TLS is a more secure protocol, using certificates to encrypt the traffic between the Mediation Server and the PSTN gateway.</span></span> <span data-ttu-id="fa972-121">すべての PSTN ゲートウェイで TLS がサポートされるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="fa972-121">Not all PSTN gateways support TLS.</span></span>

- <span data-ttu-id="fa972-122">展開用に定義および構成されている SIP trunks とゲートウェイの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="fa972-122">A listing of SIP trunks and the gateways that are defined and configured for your deployment is listed.</span></span> <span data-ttu-id="fa972-123">エントリが存在しない場合は、展開用に構成された SIP trunks または PSTN ゲートウェイがありません。</span><span class="sxs-lookup"><span data-stu-id="fa972-123">If no entries are present, there are no SIP trunks or PSTN gateways configured for your deployment.</span></span> <span data-ttu-id="fa972-124">Trunks とゲートウェイは、「トポロジビルダーの**共有コンポーネント**」で定義して構成します。</span><span class="sxs-lookup"><span data-stu-id="fa972-124">You define and configure trunks and gateways under **Shared Components** in Topology Builder.</span></span>

## <a name="see-also"></a><span data-ttu-id="fa972-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="fa972-125">See also</span></span>

[<span data-ttu-id="fa972-126">SIP トランクの概要</span><span class="sxs-lookup"><span data-stu-id="fa972-126">Overview of SIP Trunking</span></span>](https://technet.microsoft.com/library/204f2c21-436f-4b2d-93ea-d6db98fa2952.aspx)

[<span data-ttu-id="fa972-127">PSTN ゲートウェイの展開オプション</span><span class="sxs-lookup"><span data-stu-id="fa972-127">PSTN Gateway Deployment Options</span></span>](https://technet.microsoft.com/library/d1ab4f74-18aa-40c7-a8cf-ec806cf6e28a.aspx)
