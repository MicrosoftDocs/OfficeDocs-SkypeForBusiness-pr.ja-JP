---
title: ビジネス用の Skype でのリモート通話コントロールの計画
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 688a0328-1aa7-449f-b5f7-98c876112ed2
description: リモート通話コントロールでは、Lync Server は PBX 電話を制御するユーザーを有効にする Lync Server の以前のバージョンの機能をしました。 ビジネス サーバーの Skype は、この機能は作業時間を使用して呼び出しを交換済み。 Skype ビジネス サーバー 2015 と進行中の転送、リモート呼び出しのクライアント バージョンではコントロールは、クライアントで構成するのには使用できなく、使用するため削除されました
ms.openlocfilehash: 2c17418f765ba7b542f5ce349ba486a4bbe278fe
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23881819"
---
# <a name="plan-for-remote-call-control-in-skype-for-business"></a>ビジネス用の Skype でのリモート通話コントロールの計画
 
リモート通話コントロールでは、Lync Server は PBX 電話を制御するユーザーを有効にする Lync Server の以前のバージョンの機能をしました。 ビジネス サーバーの Skype は、この機能は作業時間を使用して呼び出しを交換済み。  *Skype ビジネス サーバー 2015 と進行中の転送、リモート呼び出しのクライアント バージョンではコントロールは、クライアントで構成するのには使用できなく、使用するため削除されました* 
  
 ビジネス クライアント用の Skype を使用している場合でも、Lync Server を実行して、フロント エンド サーバーに置かれている組織内のリモート呼び出しコントロール ユーザーは、リモート通話コントロールを使用する続行できます。 ただし、すべてのユーザーは、Skype のビジネス サーバーのホームのリモート呼び出しコントロール サポートされていません。 サーバー/クライアントの組み合わせおよびリモート通話コントロールまたは「勤務先から電話」機能に対応しているかどうかについては次の表を参照してください。
  
||**Skype ビジネス クライアント Skype UI を使用して有効になっているため**|**Skype ビジネス クライアント Lync UI を使用して有効になっているため**|**2016 クライアントのビジネス用の Skype**|**Lync 2013 クライアント**|**Lync 2010 クライアント**|
|:-----|:-----|:-----|:-----|:-----|:-----|
| Skype for Business Server <br/> |勤務先から通話  <br/> |1 <br/> |勤務先から通話  <br/> |1 <br/> |1 <br/> |
| Lync Server 2013 <br/> |リモート通話コントロール  <br/> |リモート通話コントロール  <br/> |1 <br/> |リモート通話コントロール  <br/> |リモート通話コントロール  <br/> |
| Lync Server 2010 <br/> |リモート通話コントロール  <br/> |リモート通話コントロール  <br/> |1 <br/> |リモート通話コントロール  <br/> |リモート通話コントロール  <br/> |
   
1. どちらの機能がサポートされています。
  
詳細については、[リモート通話コントロール](https://go.microsoft.com/fwlink/p/?LinkId=530208)Lync Server 2013 のマニュアルを参照してください。
  
## <a name="see-also"></a>関連項目

[Skype ビジネス サーバーの作業時間を使用して呼び出すのための計画](call-via-work.md)
  
[Skype for Business のデスクトップ クライアント機能の比較](../../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)

[Skype のビジネスの呼び出しが PBX 卓上電話を使用して、オーディオの](https://support.office.com/en-us/article/Make-a-Skype-for-Business-call-but-use-your-PBX-desk-phone-for-audio-6a316c11-a05e-460c-b969-32ff0ad848e6)

