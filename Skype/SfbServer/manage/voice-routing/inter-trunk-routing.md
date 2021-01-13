---
title: Skype for Business Server でのトランク間ルーティング
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
description: 'Skype for Business Server は、Trunk ルーティングのサポートを通じて基本的なセッション管理を提供します。 '
ms.openlocfilehash: d509b4f9de489e65ed8443fd1aad92e24363fb55
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814127"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a>Skype for Business Server でのトランク間ルーティング

Skype for Business Server は、Trunk ルーティングのサポートを通じて基本的なセッション管理を提供します。 この機能により、Skype for Business Server はダウンストリームのテレフォニー システムに通話制御機能を提供できます。 トランク間ルーティングは IP-PBX と公衆交換電話網 (PSTN) ゲートウェイを相互に接続でき、それによって、構内交換機 (PBX) 電話機からの通話を PSTN にルーティングしたり、着信した PSTN の通話を PBX 電話機にルーティングしたりできます。 同様に、Skype for Business Server は 2 つ以上の IP-PBX システムを相互接続して、異なる IP-PBX システムからの PBX 電話間で通話を受信できます。 


次の図は、PSTN ゲートウェイと IP-PBX 間の相互接続を提供する Skype for Business Server を示しています。

![PSTN ゲートウェイと IP-PBX 間の相互接続](../../media/pstn-gateway-ip-pbx.jpg)

次の図は、2 つの IP-PBX システムを接続する Skype for Business Server を示しています。

![2 つの IP-PGX システムを接続する Skype for Business Server](../../media/two-ip-pbx-systems.jpg)

