---
title: 概要 - デバイスのトランク間ルーティングSkype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.openlocfilehash: 5a44f9e269985312e31d827254dd7bbfae10bcfd
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2021
ms.locfileid: "58731816"
---
# <a name="about-inter-trunk-routing-in-skype-for-business-server"></a>Skype for Business Server でのトランク間ルーティングSkype for Business Server
 
トランク間ルーティングSkype for Business Server エンタープライズ VoIPサポートする方法について説明します。
  
Skype for Business Serverは、侵入ルーティングのサポートを通じて基本的なセッション管理を提供します。 これにより、Skype for Business Serverシステムに通話制御機能を提供できます。 トランク間ルーティングは IP-PBX と公衆交換電話網 (PSTN) ゲートウェイを相互に接続でき、それによって、構内交換機 (PBX) 電話機からの通話を PSTN にルーティングしたり、着信した PSTN の通話を PBX 電話機にルーティングしたりできます。 同様にSkype for Business Server複数の IP-PBX システムを相互接続して、異なる IP-PBX システムからの PBX 電話間で通話を行い、受信することができます。 
  
次の図は、PSTN ゲートウェイSkype for Business Server IP-PBX 間の相互接続を提供する方法を示しています。
  
![PSTN ゲートウェイ/IP-PBX ダイアグラムを接続する Lync Server。](../../media/inter_trunk01.jpg)
  
次の図は、2 Skype for Business Server IP-PBX システムを接続する方法を示しています。
  
![Lync Server 相互接続 IP-PAX システム図。](../../media/inter_trunk02.jpg)
  

