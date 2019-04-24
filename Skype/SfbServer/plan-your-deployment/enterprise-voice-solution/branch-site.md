---
title: Skype ビジネス サーバー用のブランチ サイトの SIP トランク
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c4d9dfcd-8baa-41ea-9677-48b0e429429d
description: ビジネス サーバーのエンタープライズ VoIP は、Skype でのブランチ サイトに SIP トランクについて説明します。
ms.openlocfilehash: 333cb5f150efb431d4c7c43a0d78b601cb8ff268
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32207084"
---
# <a name="branch-site-sip-trunking-in-skype-for-business-server"></a>Skype ビジネス サーバー用のブランチ サイトの SIP トランク
 
ビジネス サーバーのエンタープライズ VoIP は、Skype でのブランチ サイトに SIP トランクについて説明します。
  
場合によっては、選択したブランチ サイトでの分散型 SIP トランクを実装する必要があります。 ブランチ サイトとブランチ サイトの SIP トランクを展開するためのサポートされているトポロジ オプションの詳細について、SIP かどうかを判断するのにはトランクが必要な[Skype ビジネス サーバー用のトランクの SIP](sip-trunking.md)を参照してください。
  
## <a name="example-branch-site-sip-trunk-requirements-analysis"></a>ブランチ サイト SIP トランク要件例の分析

ブランチ サイトの SIP トランクを展開することを決定する際は、サイト固有のコスト分析を実行する必要があります。 たとえば、ワシントン州レドモンドの中央サイトと、ニューヨークにブランチ サイトを持つ企業では、ニューヨーク サイトからローカル サービス プロバイダーへの SIP トランクを実装するかどうかを決定する分析を行ってください。
  
ニューヨークでの分散型 SIP トランクの費用対効果が高いかどうかを判断するには、SIP トランクを使用する Direct Inward Dialing (DID) 番号を識別し、レドモンド (425) 以外の地域にニューヨークからかける電話の回数を分析します。 セントラル サイトでは、ブランチ サイトの DID 終了をことができます。 たとえば、レドモンドの中央サイトでは、ニューヨークのブランチ サイトの DID 番号をホストできます。 分散型 SIP トランクを実装するためのコストがこれらの呼び出しのコストよりも小さい場合は、ニューヨークのブランチ サイトに SIP トランクを実装することを検討してください。 
  
## <a name="other-branch-site-sip-trunk-requirements"></a>その他のブランチ サイト SIP トランク要件

ゲートウェイではなく、SIP トランクを展開する場合の選択肢は、各オプションの公衆交換電話網 (PSTN) の市外通話の通話料の差に基づいています。 ブランチ サイト SIP トランクを展開する場合は、復元性と帯域幅要件を決定する必要があります。 ブランチ サイトと中央サイト間のリンクは、耐障害性、十分な帯域幅を持つ場合は、SIP トランクまたはゲートウェイを展開できます。 ブランチ サイトでのリカバリ性に優れたブランチ アプライアンスを展開する必要はありません。 ブランチ サイトと中央サイト間のリンクは、耐障害性は、か、リカバリ性に優れたブランチ アプライアンスを展開するブランチ サイトで SIP トランクまたはゲートウェイとの存続可能ブランチ サーバーを展開します。 
  

