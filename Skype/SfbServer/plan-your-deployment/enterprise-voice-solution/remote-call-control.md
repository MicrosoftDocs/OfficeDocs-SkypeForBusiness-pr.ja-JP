---
title: リモート通話制御の計画を立Skype for Business
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
ms.assetid: 688a0328-1aa7-449f-b5f7-98c876112ed2
description: リモート通話制御は、以前のバージョンの Lync Server の機能で、ユーザーは Lync Server で PBX 電話を制御できます。 このSkype for Business Serverは、Call Via Work に置き換えされています。 Skype for Business Server 2015 および今後のクライアント バージョンでは、リモート通話制御はクライアントで構成できなくなったので、使用するために削除されています。
ms.openlocfilehash: de06005cb26e163a6f7f26c64e6863b6e6f4acbb
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/30/2021
ms.locfileid: "60015291"
---
# <a name="plan-for-remote-call-control-in-skype-for-business"></a>リモート通話制御の計画を立Skype for Business
 
リモート通話制御は、以前のバージョンの Lync Server の機能で、ユーザーは Lync Server で PBX 電話を制御できます。 このSkype for Business Serverは、Call Via Work に置き換えされています。  *Skype for Business Server 2015 および今後のクライアント バージョンでは、リモート通話制御はクライアントで構成できなくなったので、使用するために削除されています。* 
  
 Lync Server を実行しているフロント エンド サーバーに所属する組織内のリモート通話制御ユーザーは、引き続きリモート 通話制御を使用できます (クライアントを使用している場合でもSkype for Businessできます。 ただし、リモート 通話を使用しているユーザー Skype for Business Server、リモート通話制御はサポートされていません。 サーバーとクライアントの組み合わせ、およびリモート通話制御または仕事による通話をサポートできるかどうかについては、次の表を参照してください。
  
|&nbsp;|Skype for Businessクライアント UI がSkypeクライアント|Skype for BusinessLync UI が有効なクライアント|Skype for Business 2016 クライアント|Lync 2013 クライアント|Lync 2010 クライアント|
|:-----|:-----|:-----|:-----|:-----|:-----|
| Skype for Business Server  |仕事で通話する   |1  |仕事で通話する   |1  |1  |
| Lync Server 2013  |リモート通話制御   |リモート通話制御   |1  |リモート通話制御   |リモート通話制御   |
| Lync Server 2010  |リモート通話制御   |リモート通話制御   |1  |リモート通話制御   |リモート通話制御   |
   
1. どちらの機能もサポートされていません。
  
詳細については、「Lync [](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-remote-call-control) Server 2013」のドキュメントの「リモート通話制御」を参照してください。
  
## <a name="see-also"></a>関連項目

[[通話の計画] 作業時間内の作業Skype for Business Server](call-via-work.md)
  
[Skype for Business のデスクトップ クライアント機能の比較](../../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)

[電話をSkype for Business、PBX のデスクフォンを使用してオーディオを呼び出す](https://support.office.com/article/Make-a-Skype-for-Business-call-but-use-your-PBX-desk-phone-for-audio-6a316c11-a05e-460c-b969-32ff0ad848e6)