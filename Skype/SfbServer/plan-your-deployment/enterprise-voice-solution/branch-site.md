---
title: Skype for Business Server のブランチサイト SIP トランク
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Skype for Business Server Enterprise Voice のブランチサイトでの SIP トランクについて説明します。
ms.openlocfilehash: 158c1cff28ba0c21f5c995a1fe5b7dfdf2f9f150
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803257"
---
# <a name="branch-site-sip-trunking-in-skype-for-business-server"></a>Skype for Business Server のブランチサイト SIP トランク
 
Skype for Business Server Enterprise Voice のブランチサイトでの SIP トランクについて説明します。
  
場合によっては、選択したブランチサイトに配布 SIP トランキングを実装する必要があります。 ブランチサイトに SIP トランクが必要かどうかを判断し、ブランチサイトで SIP trunks を展開するためにサポートされているトポロジーオプションの詳細については、「 [Skype For Business Server の sip トランク](sip-trunking.md)」を参照してください。
  
## <a name="example-branch-site-sip-trunk-requirements-analysis"></a>ブランチ サイト SIP トランク要件例の分析

ブランチサイト SIP トランクの展開を決定する際には、サイト固有のコスト分析を実行する必要があります。 たとえば、ニューヨークのレドモンド、ワシントン、支店にセントラルサイトがある企業では、ニューヨークサイトの SIP トランクをローカルサービスプロバイダに実装するかどうかを判断する分析を行う必要があります。
  
ニューヨークでの分散型 SIP トランクの費用対効果が高いかどうかを判断するには、SIP トランクを使用する Direct Inward Dialing (DID) 番号を識別し、レドモンド (425) 以外の地域にニューヨークからかける電話の回数を分析します。 セントラルサイトでブランチサイトの終了ができました。 たとえば、Redmond のセントラルサイトでは、ニューヨーク支社のサイトの番号をホストできます。 分散 SIP トランクの実装のコストがこれらの通話のコストよりも少ない場合は、ニューヨーク支店のサイトで SIP トランクを実装することを検討してください。 
  
## <a name="other-branch-site-sip-trunk-requirements"></a>その他のブランチ サイト SIP トランク要件

ゲートウェイの代わりに SIP トランクを展開するには、各オプションの PSTN (公衆交換電話網) の長距離電話料金の差に基づいて選択することができます。 ブランチサイト SIP トランクを展開する場合は、回復性と帯域幅の要件を特定する必要もあります。 ブランチサイトとセントラルサイト間のリンクが回復可能であり、十分な帯域幅がある場合は、SIP トランクまたはゲートウェイを展開できます。 ブランチサイトに Survivable Branch Appliance を展開する必要はありません。 ブランチサイトとセントラルサイト間のリンクが復元できない場合は、Survivable Branch Appliance を展開するか、ゲートウェイまたは SIP トランクのいずれかでブランチサイトに Survivable ブランチサーバーを展開してください。 
  

