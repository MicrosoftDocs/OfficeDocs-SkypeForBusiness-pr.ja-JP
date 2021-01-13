---
title: Skype for Business でのリモート通話コントロールの計画
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
description: リモート通話コントロールは、以前のバージョンの Lync Server の機能で、ユーザーは Lync Server を使用して PBX 電話を制御できます。 Skype for Business Server では、この機能は [Call Via Work] に置き換えられた機能です。 Skype for Business Server 2015 および今後のクライアント バージョンでは、リモート通話コントロールはクライアントで構成できなくなったので、使用するために削除されています。
ms.openlocfilehash: b48eeed656f5889d08fe892da7d7a6896f8a11c3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813517"
---
# <a name="plan-for-remote-call-control-in-skype-for-business"></a>Skype for Business でのリモート通話コントロールの計画
 
リモート通話コントロールは、以前のバージョンの Lync Server の機能で、ユーザーは Lync Server を使用して PBX 電話を制御できます。 Skype for Business Server では、この機能は [Call Via Work] に置き換えられた機能です。  *Skype for Business Server 2015 および今後のクライアント バージョンでは、リモート通話コントロールはクライアントで構成できなくなったので、使用するために削除されています。* 
  
 Lync Server を実行しているフロントエンド サーバーに所属する組織内のリモート通話コントロール ユーザーは、Skype for Business クライアントを使用している場合でも、リモート通話コントロールを引き続き使用できます。 ただし、Skype for Business Server にホームを持つユーザーの場合、リモート通話コントロールはサポートされません。 サーバーとクライアントの組み合わせ、およびリモート通話コントロールまたは [作業から通話] をサポートできるかどうかについては、次の表を参照してください。
  
||**Skype UI が有効な Skype for Business クライアント**|**Lync UI が有効な Skype for Business クライアント**|**Skype for Business 2016 クライアント**|**Lync 2013 クライアント**|**Lync 2010 クライアント**|
|:-----|:-----|:-----|:-----|:-----|:-----|
| Skype for Business Server <br/> |[Call via Work] (仕事から通話)  <br/> |1  <br/> |[Call via Work] (仕事から通話)  <br/> |1  <br/> |1  <br/> |
| Lync Server 2013 <br/> |リモート通話コントロール  <br/> |リモート通話コントロール  <br/> |1  <br/> |リモート通話コントロール  <br/> |リモート通話コントロール  <br/> |
| Lync Server 2010 <br/> |リモート通話コントロール  <br/> |リモート通話コントロール  <br/> |1  <br/> |リモート通話コントロール  <br/> |リモート通話コントロール  <br/> |
   
1. どちらの機能もサポートされていません。
  
詳細については、Lync [](https://go.microsoft.com/fwlink/p/?LinkId=530208) Server 2013 のドキュメントの「リモート通話コントロール」を参照してください。
  
## <a name="see-also"></a>関連項目

[Plan for Call Via Work in Skype for Business Server](call-via-work.md)
  
[Skype for Business のデスクトップ クライアント機能の比較](../../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)

[Skype for Business 通話を行うが、音声には PBX 電話を使用する](https://support.office.com/article/Make-a-Skype-for-Business-call-but-use-your-PBX-desk-phone-for-audio-6a316c11-a05e-460c-b969-32ff0ad848e6)

