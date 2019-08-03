---
title: ハイブリッド展開で電話会議プロバイダーのフェデレーションを構成する
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
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
description: '概要: Skype for Business Online で電話会議プロバイダーのフェデレーションを構成する方法について説明します。'
ms.openlocfilehash: faeae07c0662bc252e07bbf66ec463355e439461
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "36160638"
---
# <a name="configure-federation-for-an-audio-conferencing-provider-in-your-hybrid-deployment"></a>ハイブリッド展開で電話会議プロバイダーのフェデレーションを構成する

**概要:** Skype for Business Online で電話会議プロバイダーのフェデレーションを構成する方法について説明します。

ハイブリッド展開 (オンラインでオンプレミス) で電話会議プロバイダー (ACP) を使用する場合は、オンプレミス展開と ACP パートナーとの間のフェデレーションを許可されたパートナーサーバーとして構成する必要があります。 フェデレーションを構成するには、オンプレミス展開のために、ACP パートナードメインとエッジサーバー (アクセスプロキシとも呼ばれることもあります) をフェデレーションドメインリストに追加します。 その後、ACP パートナーは、オンプレミスのエッジサーバープールの FQDN を、許可されたフェデレーションドメインリストに追加する必要があります。 その他の詳細については、ACP プロバイダーに問い合わせてください。 その後、ACP パートナーは、オンプレミスのエッジサーバープールの FQDN を、許可されたフェデレーションドメインリストに追加する必要があります。

- **許可されたフェデレーションドメインとしての ACP ドメインおよびエッジサーバーの追加**

    許可されたパートナーサーバー (許可されたフェデレーションドメイン) として ACP ドメインを追加するには、「 [Configure Support For Allowed External Domains](https://technet.microsoft.com/library/3ee6e175-986d-4c33-b03a-b9f93083dca6.aspx)」の手順を実行します。 エッジサーバーには、ACP パートナーのエッジサーバーの FQDN を追加します。 エッジサーバーの FQDN を取得するには、ACP パートナーに連絡する必要がある場合があります。これは、アクセスプロキシとして ACP によって参照されることもあります。

- **ACP パートナーへのエッジサーバープールの FQDN の指定**

    ACP パートナーは、許可されるフェデレーションドメインとしてエッジサーバープールの FQDN を追加することによって、オンプレミスのドメインを許可されたパートナーサーバーとして追加するようにフェデレーションを構成する必要があります。


