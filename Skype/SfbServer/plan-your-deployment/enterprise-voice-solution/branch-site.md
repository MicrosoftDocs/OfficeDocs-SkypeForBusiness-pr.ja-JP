---
title: Skype for Business Server のブランチ サイト SIP トランキング
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c4d9dfcd-8baa-41ea-9677-48b0e429429d
description: Skype for Business Server のブランチ サイトでの SIP トランキングについてエンタープライズ VoIP。
ms.openlocfilehash: f8b875fca8adc1ac78c0b24cf3e53fab2ec2cd89
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813717"
---
# <a name="branch-site-sip-trunking-in-skype-for-business-server"></a>Skype for Business Server のブランチ サイト SIP トランキング
 
Skype for Business Server のブランチ サイトでの SIP トランキングについてエンタープライズ VoIP。
  
場合によっては、選択したブランチ サイトで分散型 SIP トランキングの実装が必要な場合があります。 ブランチ サイトに SIP トランクが必要かどうかを判断し、ブランチ サイトに SIP トランクを展開するためにサポートされるトポロジ オプションの詳細については [、「Skype for Business Server](sip-trunking.md)での SIP トランキング」を参照してください。
  
## <a name="example-branch-site-sip-trunk-requirements-analysis"></a>ブランチ サイト SIP トランク要件例の分析

ブランチ サイトの SIP トランクを展開する場合は、サイト固有のコスト分析を実行する必要があります。 たとえば、ワシントン州レドモンドに中央サイトを持ち、ニューヨークのブランチ サイトを持つ企業は分析を行い、ニューヨーク サイトからローカル サービス プロバイダーに SIP トランクを実装するかどうかを決定する必要があります。
  
ニューヨークでの分散型 SIP トランクの費用対効果が高いかどうかを判断するには、SIP トランクを使用する Direct Inward Dialing (DID) 番号を識別し、レドモンド (425) 以外の地域にニューヨークからかける電話の回数を分析します。 中央サイトのブランチ サイトに対して DID ターミネーションを設定できます。 たとえば、Redmond 中央サイトはニューヨークのブランチ サイトの DID 番号をホストできます。 分散型 SIP トランクの実装コストがそれらの通話のコストより低い場合は、ニューヨークブランチ サイトで SIP トランクを実装する方法を検討してください。 
  
## <a name="other-branch-site-sip-trunk-requirements"></a>その他のブランチ サイト SIP トランク要件

ゲートウェイではなく SIP トランクを展開する方法の選択は、各オプションの公衆交換電話網 (PSTN) 長距離有料料金の違いに基づいて行います。 ブランチ サイトの SIP トランクを展開する場合は、回復性と帯域幅の要件も決定する必要があります。 ブランチ サイトと中央サイトの間のリンクが回復力があり、十分な帯域幅を持つ場合は、SIP トランクまたはゲートウェイを展開できます。 ブランチ サイトに存続可能ブランチ アプライアンスを展開する必要はない。 ブランチ サイトと中央サイトの間のリンクが回復力を持たない場合は、存続可能ブランチ アプライアンスを展開するか、ブランチ サイトでゲートウェイまたは SIP トランクを使用して存続可能ブランチ サーバーを展開します。 
  

