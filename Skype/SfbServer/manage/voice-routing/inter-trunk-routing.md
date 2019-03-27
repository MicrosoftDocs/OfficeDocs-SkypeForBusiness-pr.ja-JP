---
title: ビジネス サーバーの間のトランクが Skype でルーティング
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'ビジネス サーバーの Skype では、intertrunk ルーティングのサポートを通じて、基本的なセッション管理を提供します。 '
ms.openlocfilehash: 9f73899d59e79d8fc93e768f0e870449baaeb7fb
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884600"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a>ビジネス サーバーの間のトランクが Skype でルーティング

ビジネス サーバーの Skype では、intertrunk ルーティングのサポートを通じて、基本的なセッション管理を提供します。 この機能により、ダウン ストリームのテレフォニー システムへの呼び出しコントロール機能を提供するビジネス サーバーの Skype です。 トランク間ルーティングは IP-PBX と公衆交換電話網 (PSTN) ゲートウェイを相互に接続でき、それによって、構内交換機 (PBX) 電話機からの通話を PSTN にルーティングしたり、着信した PSTN の通話を PBX 電話機にルーティングしたりできます。 同様に、Skype のビジネス サーバーは、呼び出しを配置し、PBX の電話別の IP PBX システムからとの間に受信するように、2 つ以上の IP PBX システムを相互接続できます。 


次の図では、PSTN ゲートウェイと IP PBX との間の相互接続性を提供するビジネスのサーバーの Skype を示しています。

![PSTN ゲートウェイと IP PBX との間の相互接続](../../media/pstn-gateway-ip-pbx.jpg)

次の図は、ビジネス サーバーの 2 つの IP PBX システムに接続するため、Skype を示しています。

![Skype ビジネス サーバーの 2 つの IP PGX システムに接続します。](../../media/two-ip-pbx-systems.jpg)

