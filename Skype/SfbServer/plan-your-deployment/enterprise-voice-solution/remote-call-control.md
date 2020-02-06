---
title: Skype for Business のリモート通話コントロールを計画する
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
description: リモート通話コントロールは、ユーザーが Lync Server で PBX 電話を制御できるようにする以前のバージョンの Lync Server の機能です。 Skype for Business Server では、この機能は勤務先からの通話に置き換えられました。 Skype for Business Server 2015 のクライアントバージョンでは、リモート通話コントロールはクライアントでの構成に使用できなくなり、使用するために削除されました。
ms.openlocfilehash: 67010a0bc74ef46dcf204e3b2a905be87c182daf
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802507"
---
# <a name="plan-for-remote-call-control-in-skype-for-business"></a>Skype for Business のリモート通話コントロールを計画する
 
リモート通話コントロールは、ユーザーが Lync Server で PBX 電話を制御できるようにする以前のバージョンの Lync Server の機能です。 Skype for Business Server では、この機能は勤務先からの通話に置き換えられました。  *Skype for Business Server 2015 のクライアントバージョンでは、リモート通話コントロールはクライアントでの構成に使用できなくなり、使用するために削除されました。* 
  
 リモート通話コントロール Lync Server を実行しているフロントエンドサーバーを使っている組織内のユーザーは、Skype for Business クライアントを使用している場合でも、引き続きリモート通話コントロールを使用できます。 ただし、Skype for Business Server を使用しているすべてのユーザーは、リモート通話コントロールはサポートされません。 サーバー/クライアントの組み合わせおよびリモート通話コントロールまたは「勤務先から電話」機能に対応しているかどうかについては次の表を参照してください。
  
||**Skype UI を有効にした skype for Business クライアント**|**Lync UI を有効にした Skype for Business クライアント**|**Skype for Business 2016 クライアント**|**Lync 2013 クライアント**|**Lync 2010 クライアント**|
|:-----|:-----|:-----|:-----|:-----|:-----|
| Skype for Business Server <br/> |勤務先から通話  <br/> |1 <br/> |勤務先から通話  <br/> |1 <br/> |1 <br/> |
| Lync Server 2013 <br/> |リモート通話コントロール  <br/> |リモート通話コントロール  <br/> |件 <br/> |リモート通話コントロール  <br/> |リモート通話コントロール  <br/> |
| Lync Server 2010 <br/> |リモート通話コントロール  <br/> |リモート通話コントロール  <br/> |件 <br/> |リモート通話コントロール  <br/> |リモート通話コントロール  <br/> |
   
1. どちらの機能もサポートされていません。
  
詳細については、「Lync Server 2013 ドキュメントの[リモート通話コントロール](https://go.microsoft.com/fwlink/p/?LinkId=530208)」を参照してください。
  
## <a name="see-also"></a>関連項目

[Skype for Business Server での勤務先での通話の計画](call-via-work.md)
  
[Skype for Business のデスクトップ クライアント機能の比較](../../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)

[Skype for Business 通話を発信するが、PBX デスクフォンを使ってオーディオを作成する](https://support.office.com/en-us/article/Make-a-Skype-for-Business-call-but-use-your-PBX-desk-phone-for-audio-6a316c11-a05e-460c-b969-32ff0ad848e6)

