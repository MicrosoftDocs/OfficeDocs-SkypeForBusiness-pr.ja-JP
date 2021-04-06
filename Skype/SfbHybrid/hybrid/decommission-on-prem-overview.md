---
title: オンプレミスの Skype for Business 環境を使用停止する
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
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
description: オンプレミスの Skype for Business 環境を使用停止する方法について説明します。
ms.openlocfilehash: 7f5109661fc7d29d83172489dd987b96cb7e87fd
ms.sourcegitcommit: f223b5f3735f165d46bb611a52fcdfb0f4b88f66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/06/2021
ms.locfileid: "51593900"
---
# <a name="decommission-your-on-premises-skype-for-business-environment"></a>オンプレミスの Skype for Business 環境を使用停止する

組織で Skype for Business Server のオンプレミス展開で Teams または Skype for Business Online を使用している場合は、これらの環境をクラウドに完全に移行し、Skype for Business Server のオンプレミス展開を廃止できます。 

> [!NOTE]
> オンプレミス環境を使用停止する前に、オンプレミス展開と[](configure-hybrid-connectivity.md)Microsoft 365 の間のハイブリッド接続を構成する必要があります。 ハイブリッド接続を構成した後、ユーザーをクラウドに移行しながら、会議をオンプレミスから移行し、Skype for Business Server から Teams に連絡先を移行できます。 ハイブリッド接続の構成は、ユーザーをオンプレミスからクラウドに移行し、Teams の完全な機能を確保するために必要な手順です。

オンプレミスからクラウドへの移行を完了し、オンプレミスの Skype for Business Server 環境を使用停止するには、次の順序で次の手順を実行する必要があります。

- **手順 1.** [必要なすべてのユーザーとアプリケーション エンドポイントをオンプレミスからオンラインに移動します](decommission-move-on-prem-users.md)。

- **手順 2.** [ハイブリッド構成を無効にします](cloud-consolidation-disabling-hybrid.md)。

- **手順 3.** [オンプレミスの Skype for Business 展開を削除します](decommission-remove-on-prem.md)。

