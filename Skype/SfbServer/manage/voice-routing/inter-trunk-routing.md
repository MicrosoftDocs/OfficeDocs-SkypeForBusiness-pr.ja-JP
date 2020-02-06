---
title: Skype for Business Server でのインタートランクルーティング
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Skype for Business Server は、intertrunk ルーティングのサポートを通じて、基本的なセッション管理を提供します。 '
ms.openlocfilehash: c3381c6ae6bd86c416e6bd3349cf54d6fb530a08
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816967"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a>Skype for Business Server でのインタートランクルーティング

Skype for Business Server は、intertrunk ルーティングのサポートを通じて、基本的なセッション管理を提供します。 この機能により、Skype for Business Server は、下流のテレフォニーシステムへの通話コントロール機能を提供できます。 トランク間ルーティングは IP-PBX と公衆交換電話網 (PSTN) ゲートウェイを相互に接続でき、それによって、構内交換機 (PBX) 電話機からの通話を PSTN にルーティングしたり、着信した PSTN の通話を PBX 電話機にルーティングしたりできます。 同様に、Skype for Business Server は2つ以上の IP PBX システムを相互に接続して、さまざまな IP PBX システムから PBX 電話間で通話を発信および受信することができます。 


次の図は、PSTN ゲートウェイと ip-pbx の間の相互活用を実現する Skype for Business Server を示しています。

![PSTN ゲートウェイと ip-pbx の相互通信](../../media/pstn-gateway-ip-pbx.jpg)

次の図は、2つの IP PBX システムを接続する Skype for Business Server を示しています。

![2つの TCP/IP を接続する Skype for Business Server-PGX システム](../../media/two-ip-pbx-systems.jpg)

