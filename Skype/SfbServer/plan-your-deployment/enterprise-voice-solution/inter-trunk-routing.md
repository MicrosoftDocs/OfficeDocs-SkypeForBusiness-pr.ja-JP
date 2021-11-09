---
title: 概要 - デバイスのトランク間ルーティングSkype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f687a548-1f2e-48ed-9745-a13dc1f3698f
description: トランク間ルーティングSkype for Business Server エンタープライズ VoIPサポートする方法について説明します。
ms.openlocfilehash: 16a67af73db89f884f797c24123b984d3eb87789
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60855414"
---
# <a name="about-inter-trunk-routing-in-skype-for-business-server"></a>Skype for Business Server でのトランク間ルーティングSkype for Business Server
 
トランク間ルーティングSkype for Business Server エンタープライズ VoIPサポートする方法について説明します。
  
Skype for Business Serverは、侵入ルーティングのサポートを通じて基本的なセッション管理を提供します。 これにより、Skype for Business Serverシステムに通話制御機能を提供できます。 トランク間ルーティングは IP-PBX と公衆交換電話網 (PSTN) ゲートウェイを相互に接続でき、それによって、構内交換機 (PBX) 電話機からの通話を PSTN にルーティングしたり、着信した PSTN の通話を PBX 電話機にルーティングしたりできます。 同様にSkype for Business Server複数の IP-PBX システムを相互接続して、異なる IP-PBX システムからの PBX 電話間で通話を行い、受信することができます。 
  
次の図は、PSTN ゲートウェイSkype for Business Server IP-PBX 間の相互接続を提供する方法を示しています。
  
![PSTN ゲートウェイ/IP-PBX ダイアグラムを接続する Lync Server。](../../media/inter_trunk01.jpg)
  
次の図は、2 Skype for Business Server IP-PBX システムを接続する方法を示しています。
  
![Lync Server 相互接続 IP-PAX システム図。](../../media/inter_trunk02.jpg)
  

