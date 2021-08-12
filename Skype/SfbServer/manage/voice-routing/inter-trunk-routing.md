---
title: 'Skype for Business Server: トランク間ルーティング'
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Skype for Business Serverは、侵入ルーティングのサポートを通じて基本的なセッション管理を提供します。 '
ms.openlocfilehash: 917f6bb1eb114202f06e1f1d2be0c7c126f42d8cf1614c2a05dcce0dde6bb9a6
ms.sourcegitcommit: 2a76435beaac1e5daa647e93f693ea8672ec0135
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/11/2021
ms.locfileid: "57850172"
---
# <a name="skype-for-business-server-inter-trunk-routing"></a>Skype for Business Server: トランク間ルーティング

Skype for Business Serverは、侵入ルーティングのサポートを通じて基本的なセッション管理を提供します。 この機能により、Skype for Business Serverシステムに通話制御機能を提供できます。 トランク間ルーティングは IP-PBX と公衆交換電話網 (PSTN) ゲートウェイを相互に接続でき、それによって、構内交換機 (PBX) 電話機からの通話を PSTN にルーティングしたり、着信した PSTN の通話を PBX 電話機にルーティングしたりできます。 同様にSkype for Business Server複数の IP-PBX システムを相互接続して、異なる IP-PBX システムからの PBX 電話間で通話を行い、受信することができます。 


次の図は、PSTN ゲートウェイSkype for Business Server IP-PBX 間の相互接続を提供する方法を示しています。

![PSTN ゲートウェイと IP-PBX 間の相互接続](../../media/pstn-gateway-ip-pbx.jpg)

次の図は、2 Skype for Business Server IP-PBX システムを接続する方法を示しています。

![Skype for Business Server IP-PGX システムを接続する方法](../../media/two-ip-pbx-systems.jpg)

