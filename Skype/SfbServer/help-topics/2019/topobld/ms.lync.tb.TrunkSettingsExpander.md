---
title: トランク設定エキスパンダー
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.TrunkSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3d00e8f4-e599-4094-a4a1-34fd6e8a5580
ROBOTS: NOINDEX, NOFOLLOW
description: SIP トランクの設定を編集または変更するには、次の操作を行います。
ms.openlocfilehash: 6206a52930251681b197dbeea4e882a59da68787
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33921056"
---
# <a name="trunk-settings-expander"></a><span data-ttu-id="d770d-103">トランク設定エキスパンダー</span><span class="sxs-lookup"><span data-stu-id="d770d-103">Trunk Settings Expander</span></span>

<span data-ttu-id="d770d-104">SIP トランクの設定を編集または変更するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="d770d-104">To edit or modify the settings for a SIP trunk, you do the following:</span></span>

 <span data-ttu-id="d770d-105">[**トランク名**] は必須のエントリで、展開の中の SIP トランクを一意に特定します。</span><span class="sxs-lookup"><span data-stu-id="d770d-105">**Trunk name** is a required entry and uniquely identifies the SIP trunk in the deployment.</span></span>

 <span data-ttu-id="d770d-106">[**PSTN ゲートウェイの関連付け**]: 展開で定義された既存の PSTN ゲートウェイを選択します。</span><span class="sxs-lookup"><span data-stu-id="d770d-106">**Associated PSTN gateway**: Select an existing PSTN gateway that has been defined in the deployment.</span></span>

 <span data-ttu-id="d770d-p101">[**IP/PSTN ゲートウェイのリッスン ポート**]: ゲートウェイが要求をリッスンする TCP/IP ポートを示します。必要な値はゲートウェイのベンダーによって異なる場合がありますが、既定はポート 5067 です。</span><span class="sxs-lookup"><span data-stu-id="d770d-p101">**Listening port for IP/PSTN gateway**: Indicates what TCP/IP port the gateway will be listening for requests on. The required value may differ, based on the vendor of the gateway, but the default is port 5067.</span></span>

 <span data-ttu-id="d770d-p102">[**SIP 転送プロトコル**]: 使用されるプロトコルは TCP または TLS です。TLS が既定です。ゲートウェイでサポートされるプロトコルについては、ゲートウェイ ベンダーのドキュメントを参照してください。既定は TLS で、ゲートウェイが TLS をサポートしている場合、既定がより安全性の高い選択肢と考えられます。</span><span class="sxs-lookup"><span data-stu-id="d770d-p102">**SIP Transport Protocol**: The protocol used is either TCP or TLS. TLS is the default. Refer to the gateway vendor documentation for what you gateway supports. The default is TLS, and should be considered the more secure selection, if the gateway supports TLS.</span></span>

 <span data-ttu-id="d770d-113">**仲介サーバーの関連付けられている**: SIP トランクに関連付ける展開から既存の仲介サーバーを選択します。</span><span class="sxs-lookup"><span data-stu-id="d770d-113">**Associated Mediation Server**: Select an existing Mediation Server from the deployment to associate with the SIP trunk.</span></span>

> [!NOTE]
> <span data-ttu-id="d770d-114">ルート トランクだけは、仲介サーバーを関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="d770d-114">Only the root trunk can be associated with a Mediation Server.</span></span>

 <span data-ttu-id="d770d-115">**仲介サーバーの関連付けられているポート**: 必要な値では、仲介サーバーが構成されている値に設定これは上でリッスンします。</span><span class="sxs-lookup"><span data-stu-id="d770d-115">**Associated Mediation Server port**: A required value, this is set to the value that the Mediation Server is configured to listen on.</span></span>

![トランク設定エキスパンダー](../../../media/Trunk_Settings_Expander.jpg)

## <a name="see-also"></a><span data-ttu-id="d770d-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="d770d-117">See also</span></span>

[<span data-ttu-id="d770d-118">SIP トランクの展開のチェックリスト</span><span class="sxs-lookup"><span data-stu-id="d770d-118">SIP Trunking Deployment Checklist</span></span>](https://technet.microsoft.com/library/94f4f03e-19d5-4198-92be-e4076dbb959a.aspx)

[<span data-ttu-id="d770d-119">コンポーネントおよび SIP トランキングのトポロジ</span><span class="sxs-lookup"><span data-stu-id="d770d-119">Components and Topologies for SIP Trunking</span></span>](https://technet.microsoft.com/library/8ed9a9d0-517e-4f36-a131-22cdafa257fa.aspx)
