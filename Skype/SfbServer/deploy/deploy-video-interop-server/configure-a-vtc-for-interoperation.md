---
title: Skype for Business Server との相互運用のための VTC の構成
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
description: '概要: Skype for Business Server で動作する VTC デバイスを構成します。'
ms.openlocfilehash: 7697fd9f33a4fece4871b056a05264ece888d357
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802077"
---
# <a name="configure-a-vtc-for-interoperation-with-skype-for-business-server"></a>Skype for Business Server との相互運用のための VTC の構成
 
**概要:** Skype for Business Server で動作する VTC デバイスを構成します。
  
SIP トランクと Cisco Unified Communications Manager (CallManager または CUCM) ビデオ ゲートウェイを介して Skype for Business VIS サーバーに接続する各 VTC に対して、次の構成カスタマイズ手順を実行する必要があります。
  
ここで説明する設定は、VIS で動作するように CUCM を構成する方法の例としてのみ使用されます。 代替 CUCM 機能のその他の設定や使用法も、同じ結果を得る目的で使用できます。 特定のシナリオに最適な構成に関する推奨事項は示されていません。
  
### <a name="configure-a-vtc-registered-with-cucm"></a>CUCM に登録された VTC を構成する

1. Cisco VTC デバイスにログインし、[Configuration- \> System Configuration- \> Provisioning] に移動します。
    
2. 次の設定を確認し、必要に応じて修正します。 
    
   |**パラメーター**|**推奨される設定値**|
   |:-----|:-----|
   |プロビジョニング モード  <br/> | CUCM <br/> |
   |ExternalManager アドレス  <br/> | CUCM の FQDN <br/> |
   | ExternalManager ドメイン <br/> |CUCM のドメイン  <br/> |
   
3. [構成- システム構成 \> - ネットワーク] \> に移動します。
    
4. 次の設定を確認し、必要に応じて修正します。 
    
   |**パラメーター**|**推奨される設定値**|
   |:-----|:-----|
   |DNS ドメイン名  <br/> | CUCM のドメイン名 <br/> |
   |DNS サーバー 1 のアドレス  <br/> | 目的の DNS サーバー アドレス <br/> |
   
5. [構成- システム構成 \> - ネットワーク \> サービス] に移動します。 H.323 モードがオフで、SIP モードがオンになっていることを確認します。 
    
6. これらのオプションは、エンドポイントが CUCM に登録されている場合に自動的に設定されます。 次の設定を確認し、必要に応じて修正します。 
    
   |**パラメーター**|**推奨される設定値**|
   |:-----|:-----|
   |H.323 モード  <br/> | オフ <br/> |
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
   |プロファイル 1 - 送信  <br/> | オフ <br/> |
   |プロファイル 1 - TlsVerify  <br/> | オン <br/> |
   |プロファイル 1 - 種類  <br/> | Cisco <br/> |
   |プロファイル 1 - URI  <br/> | CUCM 登録時に自動的に割り当てられる <br/> |
   |プロキシ 1 - アドレス  <br/> |CUCM のホスト名  <br/> |
   
これで、VTC が相互運用用に構成されます。 サービスを開始する前に、CUCM 側で実行する最後の手順があります。
### <a name="configure-vtc-devices-on-cucm"></a>CUCM で VTC デバイスを構成する

1. CUCM にログインし、[Cisco Unified CM Administration- \> Device- \> Phone- \> Find] に移動します。 
    
2. 構成する VTC デバイスを選択します。 [電話の構成] 画面で次の設定を確認し、必要に応じて修正します。 これらの設定を変更または確認したら、[保存] をクリック **します**。
    
   |**パラメーター**|**推奨される設定値**|
   |:-----|:-----|
   |デバイス情報 - 電話ボタン テンプレート  <br/> | 標準 Cisco Telepresence Codec C40 <br/> |
   |デバイス情報 - 共通電話プロファイル  <br/> | Standard Common Phone Profile <br/> |
   |デバイス情報 - 通話検索スペース  <br/> | CSS_SfBVideoInterop <br/> |
   |デバイス情報 - AAR 通話検索スペース  <br/> | CSS_SfBVideoInterop <br/> |
   |デバイス情報 - メディア リソース グループの一覧  <br/> | MRGL_SfBVideoInterop <br/> |
   |プロトコル固有の情報 - デバイス セキュリティ プロファイル  <br/> | Cisco Telepresence Codec C40 <br/> |
   |プロトコル固有の情報 - 呼び出し元の検索スペースの再ルーティング  <br/> | CSS_SfBVideoInterop <br/> |
   |プロトコル固有の情報 - SUBSCRIBE Calling Search Space  <br/> | CSS_SfBVideoInterop <br/> |
   |プロトコル固有の情報 -SIP プロファイル  <br/> | Telepresence エンドポイントの標準 SIP プロファイル <br/> |
   
3. VTC 構成を保存したら、デバイスの [電話の構成] 画面に再び移動します。 関連付けグループの画面の上部で、ビデオ相互運用機能の関連付けをクリックします。 これにより、[ディレクトリ番号の構成] 画面が表示されます。 
    
4. 次の設定を確認し、必要に応じて修正します。 
    
    [ディレクトリ番号情報] および [ディレクトリ番号の設定] に示すように、適切な変更を行います。
    
   |**パラメーター**|**推奨される設定値**|
   |:-----|:-----|
   | ディレクトリ番号情報 - ルート パーティション <br/> | SfBVideoInterop_RoutePartition <br/> |
   |ディレクトリ番号の設定 - 通話検索スペース  <br/> | CSS_SfBVideoInterop <br/> |
   |MLPP 代替パーティーと機密アクセス レベルの設定 - MLPP 通話検索スペース  <br/> | CSS_SfBVideoInterop <br/> |
   |デバイスの 1 行目 - 表示 (発信者番号)  <br/> | 必要に応じて <br/> |
   |デバイスの行 1 - ASCII 表示 (発信者番号)  <br/> | 必要に応じて <br/> |
   
5. 完了したら、画面の上部までスクロールし、[保存] を **押します**。 
    
これで、この VTC デバイスの構成が完了しました。 企業内の他の VTC デバイスに対してこのプロセスを繰り返す必要があります。

