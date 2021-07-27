---
title: ハイブリッド展開で電話会議プロバイダーのフェデレーションを構成する
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: '概要: オンラインで電話会議プロバイダーのフェデレーションを構成するSkype for Businessします。'
ms.openlocfilehash: 4c2f0b9163202ff8469f2a2223c88ba10db193c3
ms.sourcegitcommit: 9879bc587382755d9a5cd63a75b0e7dc4e15574c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2021
ms.locfileid: "53510568"
---
# <a name="configure-federation-for-an-audio-conferencing-provider-in-your-hybrid-deployment"></a>ハイブリッド展開で電話会議プロバイダーのフェデレーションを構成する

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]


**概要:** オンラインで電話会議プロバイダーのフェデレーションを構成するSkype for Businessします。

ハイブリッド展開 (オンプレミスとオンライン) で電話会議プロバイダー (ACP) を使用する場合は、オンプレミス展開と ACP パートナー間のフェデレーションを許可パートナー サーバーとして構成する必要があります。 フェデレーションを構成するには、ACP パートナー ドメインとエッジ サーバー (アクセス プロキシとも呼ばれる場合があります) をオンプレミス展開のフェデレーション ドメイン リストに追加します。 その後、ACP パートナーは、オンプレミスエッジ サーバー プールの FQDN を許可されたフェデレーション ドメイン リストに追加する必要があります。 詳細については、ACP プロバイダーにお問い合わせください。 その後、ACP パートナーは、オンプレミスエッジ サーバー プールの FQDN を許可されたフェデレーション ドメイン リストに追加する必要があります。

- **ACP ドメインとエッジ サーバーを許可されたフェデレーション ドメインとして追加する**

    ACP ドメインを許可パートナー サーバー (許可されたフェデレーション ドメイン) として追加するには、「許可された外部ドメインのサポートを構成する」 [の手順に従います](/previous-versions/office/lync-server-2013/lync-server-2013-configure-support-for-allowed-external-domains)。 エッジ サーバーの場合は、ACP パートナーのエッジ サーバーの FQDN を追加します。 エッジ サーバーの FQDN を取得するには、ACP パートナーに問い合わせが必要な場合があります。これは、ACP がアクセス プロキシと呼ばれる場合があります。

- **エッジ サーバー プールの FQDN を ACP パートナーに提供する**

    ACP パートナーは、許可されたフェデレーション ドメインとしてエッジ サーバー プールの FQDN を追加して、オンプレミス ドメインを許可パートナー サーバーとして追加するフェデレーションを構成する必要があります。