---
title: Skype for Business でのリモート通話コントロールの計画
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
ms.assetid: 688a0328-1aa7-449f-b5f7-98c876112ed2
description: リモート通話コントロールは、ユーザーが Lync Server を使用して PBX 電話を制御できるようにする、以前のバージョンの Lync Server の機能でした。 Skype for Business Server では、この機能は [勤務先から通話] に置き換えられました。 Skype for Business Server 2015 のクライアントバージョンでは、リモート通話コントロールはクライアントでの構成に使用できなくなり、使用するために削除されました。
ms.openlocfilehash: 788939c392b1d86d14590232c19979e664fa0c09
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "41982802"
---
# <a name="plan-for-remote-call-control-in-skype-for-business"></a>Skype for Business でのリモート通話コントロールの計画
 
リモート通話コントロールは、ユーザーが Lync Server を使用して PBX 電話を制御できるようにする、以前のバージョンの Lync Server の機能でした。 Skype for Business Server では、この機能は [勤務先から通話] に置き換えられました。  *Skype for Business Server 2015 のクライアントバージョンでは、リモート通話コントロールはクライアントでの構成に使用できなくなり、使用するために削除されました。* 
  
 リモート通話コントロール Lync Server を実行しているフロントエンドサーバーに所属している組織内のユーザーは、Skype for Business クライアントを使用している場合でも、リモート通話コントロールを引き続き使用できます。 ただし、Skype for Business Server を使用しているユーザーの場合、リモート通話コントロールはサポートされていません。 サーバーとクライアントの組み合わせについては、次の表を参照してください。また、リモート通話コントロールをサポートするか、勤務先から通話することもできます。
  
||**Skype UI 対応の skype for Business クライアント**|**Lync UI が有効な Skype for Business クライアント**|**Skype for Business 2016 クライアント**|**Lync 2013 クライアント**|**Lync 2010 クライアント**|
|:-----|:-----|:-----|:-----|:-----|:-----|
| Skype for Business Server <br/> |勤務先から通話  <br/> |1  <br/> |勤務先から通話  <br/> |1  <br/> |1  <br/> |
| Lync Server 2013 <br/> |リモート通話コントロール  <br/> |リモート通話コントロール  <br/> |1  <br/> |リモート通話コントロール  <br/> |リモート通話コントロール  <br/> |
| Lync Server 2010 <br/> |リモート通話コントロール  <br/> |リモート通話コントロール  <br/> |1  <br/> |リモート通話コントロール  <br/> |リモート通話コントロール  <br/> |
   
1. どちらの機能もサポートされていません。
  
詳細については、Lync Server 2013 のドキュメントの「[リモート通話コントロール](https://go.microsoft.com/fwlink/p/?LinkId=530208)」を参照してください。
  
## <a name="see-also"></a>関連項目

[Skype for Business Server での作業による通話の計画](call-via-work.md)
  
[Skype for Business のデスクトップクライアント機能の比較](../../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)

[Skype for Business 通話を行うが、PBX 電話を使用してオーディオを使用する](https://support.office.com/article/Make-a-Skype-for-Business-call-but-use-your-PBX-desk-phone-for-audio-6a316c11-a05e-460c-b969-32ff0ad848e6)

