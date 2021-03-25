---
title: Skype for Business でリモート通話制御を計画する
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
ms.assetid: 688a0328-1aa7-449f-b5f7-98c876112ed2
description: リモート通話制御は、以前のバージョンの Lync Server の機能で、ユーザーは Lync Server で PBX 電話を制御できます。 Skype for Business Server では、この機能は Call Via Work に置き換えられた。 Skype for Business Server 2015 および今後のクライアント バージョンでは、リモート通話制御はクライアントで構成できなくなったので、使用するために削除されています。
ms.openlocfilehash: 1ec6bb59b34505f17451be72baa44cdcc466c0d3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51114613"
---
# <a name="plan-for-remote-call-control-in-skype-for-business"></a>Skype for Business でリモート通話制御を計画する
 
リモート通話制御は、以前のバージョンの Lync Server の機能で、ユーザーは Lync Server で PBX 電話を制御できます。 Skype for Business Server では、この機能は Call Via Work に置き換えられた。  *Skype for Business Server 2015 および今後のクライアント バージョンでは、リモート通話制御はクライアントで構成できなくなったので、使用するために削除されています。* 
  
 Lync Server を実行しているフロントエンド サーバーに所属する組織内のリモート通話制御ユーザーは、Skype for Business クライアントを使用している場合でも、リモート通話制御を引き続き使用できます。 ただし、Skype for Business Server に接続しているユーザーの場合、リモート通話制御はサポートされていません。 サーバーとクライアントの組み合わせ、およびリモート通話制御または仕事による通話をサポートできるかどうかについては、次の表を参照してください。
  
||**Skype の UI が有効になっている Skype for Business クライアント**|**Lync UI を有効にした Skype for Business クライアント**|**Skype for Business 2016 クライアント**|**Lync 2013 クライアント**|**Lync 2010 クライアント**|
|:-----|:-----|:-----|:-----|:-----|:-----|
| Skype for Business Server <br/> |仕事で通話する  <br/> |1 <br/> |仕事で通話する  <br/> |1 <br/> |1 <br/> |
| Lync Server 2013 <br/> |リモート通話制御  <br/> |リモート通話制御  <br/> |1 <br/> |リモート通話制御  <br/> |リモート通話制御  <br/> |
| Lync Server 2010 <br/> |リモート通話制御  <br/> |リモート通話制御  <br/> |1 <br/> |リモート通話制御  <br/> |リモート通話制御  <br/> |
   
1. どちらの機能もサポートされていません。
  
詳細については、「Lync [](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-remote-call-control) Server 2013」のドキュメントの「リモート通話制御」を参照してください。
  
## <a name="see-also"></a>関連項目

[Skype for Business Server での作業による通話の計画](call-via-work.md)
  
[Skype for Business のデスクトップ クライアント機能の比較](../../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)

[Skype for Business 呼び出しを行うが、PBX デスクフォンをオーディオに使用する](https://support.office.com/article/Make-a-Skype-for-Business-call-but-use-your-PBX-desk-phone-for-audio-6a316c11-a05e-460c-b969-32ff0ad848e6)