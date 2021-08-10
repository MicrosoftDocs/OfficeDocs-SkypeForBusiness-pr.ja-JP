---
title: ブランチ サイトの SIP トランキング (Skype for Business Server
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
description: SIP トランキングの詳細については、Skype for Business Server エンタープライズ VoIP。
ms.openlocfilehash: 3a009e7e2a94cd9c172adb4cfb0496efc9a44a03749f6c40c6ee63fb321b7f62
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54306958"
---
# <a name="branch-site-sip-trunking-in-skype-for-business-server"></a>ブランチ サイトの SIP トランキング (Skype for Business Server
 
SIP トランキングの詳細については、Skype for Business Server エンタープライズ VoIP。
  
場合によっては、選択したブランチ サイトで分散 SIP トランキングを実装する必要がある場合があります。 ブランチ サイトに SIP トランクが必要かどうか、およびブランチ サイトに SIP トランクを展開するためのサポートされているトポロジ オプションの詳細については、「Skype for Business Server での SIP トランキング」[を参照してください](sip-trunking.md)。
  
## <a name="example-branch-site-sip-trunk-requirements-analysis"></a>ブランチ サイト SIP トランク要件例の分析

ブランチ サイト SIP トランクを展開する場合は、サイト固有のコスト分析を実行する必要があります。 たとえば、Redmond、Washington、およびニューヨークのブランチ サイトに中央サイトを持つ企業は、ニューヨーク サイトからローカル サービス プロバイダーに SIP トランクを実装するかどうかを決定する分析を行う必要があります。
  
ニューヨークでの分散型 SIP トランクの費用対効果が高いかどうかを判断するには、SIP トランクを使用する Direct Inward Dialing (DID) 番号を識別し、レドモンド (425) 以外の地域にニューヨークからかける電話の回数を分析します。 ブランチ サイトの DID 終了は、中央サイトで実行できます。 たとえば、Redmond セントラル サイトは、ニューヨークのブランチ サイトの DID 番号をホストできます。 分散 SIP トランクを実装するコストがこれらの呼び出しのコストよりも低い場合は、ニューヨークブランチ サイトでの SIP トランクの実装を検討してください。 
  
## <a name="other-branch-site-sip-trunk-requirements"></a>その他のブランチ サイト SIP トランク要件

ゲートウェイの代わりに SIP トランクを展開する方法の選択は、各オプションの公衆交換電話網 (PSTN) 長距離有料料金の違いに基づいて行います。 ブランチ サイトの SIP トランクを展開する場合は、回復性と帯域幅の要件も決定する必要があります。 ブランチ サイトとセントラル サイトの間のリンクが回復力があり、十分な帯域幅を持つ場合は、SIP トランクまたはゲートウェイを展開できます。 ブランチ サイトに存続可能ブランチ アプライアンスを展開する必要はない。 ブランチ サイトとセントラル サイト間のリンクが回復力を持たない場合は、存続可能ブランチ アプライアンスを展開するか、ブランチ サイトにゲートウェイまたは SIP トランクを持つ存続可能ブランチ サーバーを展開します。 
  

