---
title: オンプレミスの Skype for Business 環境を廃止する
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: オンプレミスの環境を使用停止する方法Skype for Business説明します。
ms.openlocfilehash: 53ed840c89ab02eff87607f0bdffebcef94fd4e2
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58583391"
---
# <a name="decommission-your-on-premises-skype-for-business-environment"></a>オンプレミスの Skype for Business 環境を廃止する

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

組織が Skype for Business Server のオンプレミス展開で Teams を使用している場合は、これらの環境を完全にクラウドに移行してから、Skype for Business Server のオンプレミス展開を廃止できます。 

> [!NOTE]
> オンプレミス環境の使用を停止する前に、オンプレミス展開と[](configure-hybrid-connectivity.md)オンプレミスの間のハイブリッド接続を構成するMicrosoft 365。 ハイブリッド接続を構成した後、ユーザーをクラウドに移行しながら、会議をオンプレミスから移行し、連絡先を Skype for Business Server から Teams に移行できます。 ハイブリッド接続の構成は、ユーザーをオンプレミスからクラウドに移行し、完全な機能を確実にTeamsです。

オンプレミスからクラウドへの移行を完了し、オンプレミス Skype for Business Server 環境を使用停止するには、次の手順を実行する必要があります。

- **手順 1.** [必要なすべてのユーザーをオンプレミスからオンラインに移動します](decommission-move-on-prem-users.md)。

- **手順 2.** [ハイブリッド構成を無効にします](cloud-consolidation-disabling-hybrid.md)。

- **手順 3.** [ハイブリッド アプリケーション エンドポイントをオンプレミスからオンラインに移動します](decommission-move-on-prem-endpoints.md)。

- **手順 4.** [オンプレミスの展開を削除Skype for Businessします](decommission-remove-on-prem.md)。

