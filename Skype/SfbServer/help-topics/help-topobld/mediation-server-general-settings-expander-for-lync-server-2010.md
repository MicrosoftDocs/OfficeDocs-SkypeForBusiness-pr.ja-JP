---
title: Lync Server 2010 仲介サーバーの全般設定の展開
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.MediationServerGeneralSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 48e434c1-0c3c-4502-9441-c0a3c340f51f
description: このダイアログ ボックス内の仲介サーバーのプロパティを編集するとします。 左側にあるをクリックすると全般的な設定、次のホップの設定、および PSTN ゲートウェイの設定の設定へのクイック リンクのセットです。 各セクションで、次の設定です。
ms.openlocfilehash: bc26a6b92746e2cf1453d9ee789500011469527f
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2018
ms.locfileid: "25375972"
---
# <a name="mediation-server-general-settings-expander-for-lync-server-2010"></a><span data-ttu-id="54fa8-105">Lync Server 2010 仲介サーバーの全般設定の展開</span><span class="sxs-lookup"><span data-stu-id="54fa8-105">Mediation Server General Settings Expander for Lync Server 2010</span></span>

<span data-ttu-id="54fa8-106">このダイアログ ボックス内の仲介サーバーのプロパティを編集するとします。</span><span class="sxs-lookup"><span data-stu-id="54fa8-106">You edit the properties of the Mediation Servers in this dialog.</span></span> <span data-ttu-id="54fa8-107">左側にあるをクリックすると全般的な設定、次のホップの設定、および PSTN ゲートウェイの設定の設定へのクイック リンクのセットです。</span><span class="sxs-lookup"><span data-stu-id="54fa8-107">Along the left side is a set of quick links to take you to settings for General settings, Next hop settings, and PSTN gateway settings.</span></span> <span data-ttu-id="54fa8-108">各セクションで、次の設定です。</span><span class="sxs-lookup"><span data-stu-id="54fa8-108">In each section are the following settings:</span></span>

 <span data-ttu-id="54fa8-109">**全般**。</span><span class="sxs-lookup"><span data-stu-id="54fa8-109">**General**:</span></span>

- <span data-ttu-id="54fa8-110">**FQDN**: 仲介サーバーの完全修飾ドメイン名を編集します。</span><span class="sxs-lookup"><span data-stu-id="54fa8-110">**FQDN**: You edit the fully qualified domain name of the Mediation Server</span></span>

- <span data-ttu-id="54fa8-111">**関連付け**:**関連付けるエッジ プール**を (メディア コンポーネント) のチェック ボックスをオンにし、外部アクセス用のメディアのパスとして使用するには、エッジ サーバーまたは仲介サーバーのエッジ プールを選択します。</span><span class="sxs-lookup"><span data-stu-id="54fa8-111">**Associations**: Select the **Associate Edge pool (for media components)** check box and select an Edge Server or Edge pool for the Mediation Server to use as the media path for external access.</span></span>

  <span data-ttu-id="54fa8-112">**次ホップ**:</span><span class="sxs-lookup"><span data-stu-id="54fa8-112">**Next hop**:</span></span>

- <span data-ttu-id="54fa8-113">**次ホップの選択**: 展開と通信するために使用する仲介サーバーへのパスとして使用するフロント エンド サーバーまたはフロント エンド プールを一覧から選択します。</span><span class="sxs-lookup"><span data-stu-id="54fa8-113">**Next hop selection**: Select from a list the Front End Server or Front End pool to use as the path for the Mediation Server to use for communicating with your deployment.</span></span>

  <span data-ttu-id="54fa8-114">**PSTN ゲートウェイ**:</span><span class="sxs-lookup"><span data-stu-id="54fa8-114">**PSTN gateway**:</span></span>

  <span data-ttu-id="54fa8-115">**仲介サーバー PSTN ゲートウェイ**:</span><span class="sxs-lookup"><span data-stu-id="54fa8-115">**Mediation Server PSTN gateway**:</span></span>

- <span data-ttu-id="54fa8-116">**リッスンするポート**: 仲介サーバーがリッスンするポートを定義します。</span><span class="sxs-lookup"><span data-stu-id="54fa8-116">**Listening ports**: Define the ports that the Mediation Server will listen on.</span></span> <span data-ttu-id="54fa8-117">**TLS**またはトランスポート層セキュリティ、または**TCP**のポートを定義することができますまたはトランス ポート プロトコルを制御します。</span><span class="sxs-lookup"><span data-stu-id="54fa8-117">You can define a port for **TLS** or transport layer security, or **TCP**, or transport control protocol.</span></span> <span data-ttu-id="54fa8-118">使用する TCP のポートのエントリを**有効にする TCP ポート**のチェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="54fa8-118">For the port entry for TCP to be available, you must select the check box for **Enable TCP port**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="54fa8-119">TLS と TCP のどちらか一方または両方のポートの値を有効にして、定義する必要がある場合を判断するのには公衆交換電話網 (PSTN) ゲートウェイのドキュメントおよび構成の設定] を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54fa8-119">Refer to the documentation and configuration settings for your public switched telephone network (PSTN) gateway to determine if you need to enable and define port values TLS, TCP or both.</span></span> <span data-ttu-id="54fa8-120">TLS は、仲介サーバーと PSTN ゲートウェイ間のトラフィックを暗号化する証明書を使用して、安全なプロトコルです。</span><span class="sxs-lookup"><span data-stu-id="54fa8-120">TLS is a more secure protocol, using certificates to encrypt the traffic between the Mediation Server and the PSTN gateway.</span></span> <span data-ttu-id="54fa8-121">すべての PSTN ゲートウェイが TLS をサポートします。</span><span class="sxs-lookup"><span data-stu-id="54fa8-121">Not all PSTN gateways support TLS.</span></span>

- <span data-ttu-id="54fa8-122">SIP トランクと定義して、展開用に構成されているゲートウェイの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="54fa8-122">A listing of SIP trunks and the gateways that are defined and configured for your deployment is listed.</span></span> <span data-ttu-id="54fa8-123">エントリが存在しない場合がない SIP トランクまたは PSTN ゲートウェイの展開用に構成されています。</span><span class="sxs-lookup"><span data-stu-id="54fa8-123">If no entries are present, there are no SIP trunks or PSTN gateways configured for your deployment.</span></span> <span data-ttu-id="54fa8-124">定義し、トポロジ ビルダーでトランクおよび**共有コンポーネント**] の下のゲートウェイを構成します。</span><span class="sxs-lookup"><span data-stu-id="54fa8-124">You define and configure trunks and gateways under **Shared Components** in Topology Builder.</span></span>

## <a name="see-also"></a><span data-ttu-id="54fa8-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="54fa8-125">See also</span></span>

[<span data-ttu-id="54fa8-126">SIP トランクの概要</span><span class="sxs-lookup"><span data-stu-id="54fa8-126">Overview of SIP Trunking</span></span>](https://technet.microsoft.com/library/204f2c21-436f-4b2d-93ea-d6db98fa2952.aspx)

[<span data-ttu-id="54fa8-127">PSTN ゲートウェイの展開オプション</span><span class="sxs-lookup"><span data-stu-id="54fa8-127">PSTN Gateway Deployment Options</span></span>](https://technet.microsoft.com/library/d1ab4f74-18aa-40c7-a8cf-ec806cf6e28a.aspx)