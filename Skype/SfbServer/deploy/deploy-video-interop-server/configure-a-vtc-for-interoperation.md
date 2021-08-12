---
title: VTC for Interoperation for Interoperation with Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1016aed6-99fe-452e-8b20-81c814808c3d
description: '概要: VTC デバイスを構成して、デバイスをSkype for Business Server。'
ms.openlocfilehash: 0c96766daf67ff3c8f7872a75423f64f64acba8e51d3fbc4c0edef841cc529e6
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54307778"
---
# <a name="configure-a-vtc-for-interoperation-with-skype-for-business-server"></a>VTC for Interoperation for Interoperation with Skype for Business Server
 
**概要:** VTC デバイスを構成して、デバイスをSkype for Business Server。
  
SIP トランクと Cisco Unified Communications Manager (CallManager,または CUCM) ビデオ ゲートウェイを介して Skype for Business VIS サーバーに接続する各 VTC に対して、次の構成カスタマイズ手順を実行する必要があります。
  
ここで説明する設定は、CUCM を VIS で動作するように構成する方法の例としてのみ使用されます。 他の設定や代替 CUCM 機能の使用法も、同じ結果を得る目的で使用できます。 特定のシナリオに最適な構成に関する推奨事項は示されていません。
  
### <a name="configure-a-vtc-registered-with-cucm"></a>CUCM に登録されている VTC を構成する

1. Cisco VTC デバイスにログインし、[Configuration- \> System Configuration- \> Provisioning] に移動します。
    
2. 次の設定を確認し、必要に応じて修正します。 
    
   |**パラメーター**|**推奨される設定値**|
   |:-----|:-----|
   |プロビジョニング モード  <br/> | CUCM <br/> |
   |ExternalManager アドレス  <br/> | CUCM の FQDN <br/> |
   | ExternalManager ドメイン <br/> |CUCM のドメイン  <br/> |
   
3. [構成- システム構成- \> ネットワーク] \> に移動します。
    
4. 次の設定を確認し、必要に応じて修正します。 
    
   |**パラメーター**|**推奨される設定値**|
   |:-----|:-----|
   |DNS ドメイン名  <br/> | CUCM のドメイン名 <br/> |
   |DNS Server 1 アドレス  <br/> | 目的の DNS サーバー アドレス <br/> |
   
5. [構成- システム構成- \> ネットワーク サービス] \> に移動します。 H.323 モードがオフになっていて、SIP モードがオンになっていることを確認します。 
    
6. これらのオプションは、エンドポイントが CUCM に登録されている場合に自動的に設定されます。 次の設定を確認し、必要に応じて修正します。 
    
   |**パラメーター**|**推奨される設定値**|
   |:-----|:-----|
   |H.323 モード  <br/> | Off <br/> |
   |HTTP モード  <br/> | オン <br/> |
   | SIP モード <br/> | オン <br/> |
   |Telnet モード  <br/> | オン <br/> |
   |WelcomeText  <br/> | オン <br/> |
   |XMLAPI モード  <br/> | オン <br/> |
   
7. [構成- システム構成- \> \> SIP] に移動します。
    
8. 次の設定を確認し、必要に応じて修正します。 
    
   |**パラメーター**|**推奨される設定値**|
   |:-----|:-----|
   |プロファイル 1 - DefaultTransport  <br/> | TCP <br/> |
   |プロファイル 1 - 送信  <br/> | Off <br/> |
   |プロファイル 1 - TlsVerify  <br/> | オン <br/> |
   |プロファイル 1 - 種類  <br/> | Cisco <br/> |
   |プロファイル 1 - URI  <br/> | CUCM 登録時に自動的に割り当てられる <br/> |
   |プロキシ 1 - アドレス  <br/> |CUCM のホスト名  <br/> |
   
VTC は相互運用用に構成されています。 サービスを開始する前に、CUCM 側で実行する最後の手順があります。
### <a name="configure-vtc-devices-on-cucm"></a>CUCM で VTC デバイスを構成する

1. CUCM にログインし、[Cisco Unified CM \> Administration- Device- \> 電話- 検索] に \> 移動します。 
    
2. 構成する VTC デバイスを選択します。 [構成] 画面で次の電話を確認し、必要に応じて修正します。 これらの設定が変更または確認された後、[保存] を **クリックします**。
    
   |**パラメーター**|**推奨される設定値**|
   |:-----|:-----|
   |デバイス情報 - 電話 ボタン テンプレート  <br/> | 標準の Cisco Telepresence Codec C40 <br/> |
   |デバイス情報 - 一般的な電話プロファイル  <br/> | Standard Common 電話 プロファイル <br/> |
   |デバイス情報 - コーリング サーチ スペース  <br/> | CSS_SfBVideoInterop <br/> |
   |デバイス情報 - AAR コーリング サーチ スペース  <br/> | CSS_SfBVideoInterop <br/> |
   |デバイス情報 - メディア リソース グループの一覧  <br/> | MRGL_SfBVideoInterop <br/> |
   |プロトコル固有の情報 - デバイス セキュリティ プロファイル  <br/> | Cisco Telepresence Codec C40 <br/> |
   |プロトコル固有の情報 - コーリング サーチ スペースの再ルーティング  <br/> | CSS_SfBVideoInterop <br/> |
   |プロトコル固有の情報 - SUBSCRIBE コーリング サーチ スペース  <br/> | CSS_SfBVideoInterop <br/> |
   |プロトコル固有の情報 -SIP プロファイル  <br/> | Telepresence エンドポイントの標準 SIP プロファイル <br/> |
   
3. VTC 構成が保存された後、デバイスの [電話構成] 画面に再び移動します。 [関連付け] グループの画面の上部で、[ビデオ相互運用] の関連付けをクリックします。 これにより、[電話番号の構成] 画面が表示されます。 
    
4. 次の設定を確認し、必要に応じて修正します。 
    
    [電話番号情報] および [電話番号] ページに示すように、適切な設定。
    
   |**パラメーター**|**推奨される設定値**|
   |:-----|:-----|
   | 電話番号情報 - ルート パーティション <br/> | SfBVideoInterop_RoutePartition <br/> |
   |電話番号 設定 - コーリング サーチ スペース  <br/> | CSS_SfBVideoInterop <br/> |
   |MLPP 代替パーティおよび機密アクセス レベル 設定 - MLPP コーリング サーチ スペース  <br/> | CSS_SfBVideoInterop <br/> |
   |デバイスの行 1 - 表示 (発信者 ID)  <br/> | 必要に応じて <br/> |
   |デバイスの行 1 - ASCII 表示 (発信者 ID)  <br/> | 必要に応じて <br/> |
   
5. 完了したら、画面の上部までスクロールし、[保存] を **押します**。 
    
これで、この VTC デバイスの構成が完了しました。 このプロセスは、企業内の他の VTC デバイスに対して繰り返す必要があります。

