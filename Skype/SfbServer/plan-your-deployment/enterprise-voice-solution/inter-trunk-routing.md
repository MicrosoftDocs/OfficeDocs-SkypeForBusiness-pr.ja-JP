---
title: ビジネス サーバーの間のトランクが Skype でルーティング
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f687a548-1f2e-48ed-9745-a13dc1f3698f
description: ビジネス サーバーのエンタープライズ VoIP の Skype がトランクの間のルーティングをサポートする方法について説明します。
ms.openlocfilehash: a019e0340d9077874b35af0a116731f0ede97d67
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "20965402"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a>ビジネス サーバーの間のトランクが Skype でルーティング
 
ビジネス サーバーのエンタープライズ VoIP の Skype がトランクの間のルーティングをサポートする方法について説明します。
  
ビジネス サーバーの Skype では、intertrunk ルーティングのサポートを通じて、基本的なセッション管理を提供します。 これにより、ダウン ストリームのテレフォニー システムへの呼び出しコントロール機能を提供するビジネス サーバーの Skype です。 トランク間ルーティングは IP-PBX と公衆交換電話網 (PSTN) ゲートウェイを相互に接続でき、それによって、構内交換機 (PBX) 電話機からの通話を PSTN にルーティングしたり、着信した PSTN の通話を PBX 電話機にルーティングしたりできます。 同様に、Skype のビジネス サーバーは、呼び出しを配置し、PBX の電話別の IP PBX システムからとの間に受信するように、2 つ以上の IP PBX システムを相互接続できます。 
  
次の図では、PSTN ゲートウェイと IP PBX との間の相互接続性を提供するビジネスのサーバーの Skype を示しています。
  
![Lync Server、PSTN ゲートウェイ/IP-PBX の接続図](../../media/inter_trunk01.jpg)
  
次の図は、ビジネス サーバーの 2 つの IP PBX システムに接続するため、Skype を示しています。
  
![Lync Server、IP-PAX システムの相互接続図](../../media/inter_trunk02.jpg)
  

