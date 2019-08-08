---
title: Skype for Business Server との相互運用用に VTC を構成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1016aed6-99fe-452e-8b20-81c814808c3d
description: '概要: Skype for Business Server で動作するように VTC デバイスを構成します。'
ms.openlocfilehash: 8c5310479aea38f5623f8ac2e10ef64978aa4aee
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36235673"
---
# <a name="configure-a-vtc-for-interoperation-with-skype-for-business-server"></a>Skype for Business Server との相互運用用に VTC を構成する
 
**概要:** Skype for Business Server で動作するように VTC デバイスを構成します。
  
SIP トランクと Cisco ユニファイドコミュニケーションマネージャー (CallManager または CUCM) のビデオゲートウェイを介して、Skype for Business VIS サーバーに接続する各 VTC について、次の構成のカスタマイズ手順を実行する必要があります。
  
ここで説明する設定は、VIS と連携するように CUCM を設定する方法の例としてのみ使用されています。 CUCM の別の機能を他の方法で設定/使用して同じ結果を実現することもできます。 特定のシナリオに最適な構成について推奨するものではありません。
  
### <a name="configure-a-vtc-registered-with-cucm"></a>CUCM を使用して登録された VTC を構成する

1. Cisco VTC デバイスにログインして、構成-\>システム構成の\>プロビジョニングに移動します。
    
2. 次の設定を確認し、必要に応じて修正します。 
    
   |**パラメーター**|**推奨設定**|
   |:-----|:-----|
   |Provisioning Mode  <br/> | CUCM <br/> |
   |ExternalManager Address  <br/> | CUCM の FQDN <br/> |
   | ExternalManager ドメイン <br/> |CUCM のドメイン  <br/> |
   
3. 構成-\>システム構成-\>ネットワークに移動します。
    
4. 次の設定を確認し、必要に応じて修正します。 
    
   |**パラメーター**|**推奨設定**|
   |:-----|:-----|
   |DNS Domain Name  <br/> | CUCM のドメイン名 <br/> |
   |DNS Server 1 Address  <br/> | 目的の DNS サーバー アドレス <br/> |
   
5. "構成-\>システム構成-\>ネットワークサービス" に移動します。 H.323 モードがオフで、SIP モードがオンになっていることを確認します。 
    
6. これらのオプションは、CUCM を使用してエンドポイントを登録すると、自動的に設定されます。次の設定を確認し、必要に応じて修正します。 
    
   |**パラメーター**|**推奨設定**|
   |:-----|:-----|
   |H.323 Mode  <br/> | オフ <br/> |
   |HTTP Mode  <br/> | オン <br/> |
   | SIP Mode <br/> | オン <br/> |
   |Telnet Mode  <br/> | オン <br/> |
   |WelcomeText  <br/> | オン <br/> |
   |XMLAPI Mode  <br/> | オン <br/> |
   
7. 「構成-\>システム構成-\>SIP」に移動します。
    
8. 次の設定を確認し、必要に応じて修正します。 
    
   |**パラメーター**|**推奨設定**|
   |:-----|:-----|
   |Profile 1 - DefaultTransport  <br/> | TCP <br/> |
   |Profile 1 - Outbound  <br/> | オフ <br/> |
   |プロファイル 1-TlsVerify  <br/> | オン <br/> |
   |Profile 1 - Type  <br/> | Cisco <br/> |
   |Profile 1 - URI  <br/> | CUCM 登録時に自動割り当て <br/> |
   |Proxy 1 - Address  <br/> |CUCM のホスト名  <br/> |
   
これで、VTC が相互運用するように構成されました。サービスを開始する前に、CUCM 側で最後の手順を実行します。
### <a name="configure-vtc-devices-on-cucm"></a>CUCM で VTC デバイスを構成する

1. CUCM にログインして、「Cisco ユニファイ CM 管理-\>デバイス-\>電話-\>検索」に移動します。 
    
2. 構成する VTC デバイスを選択します。[Phone Configuration] 画面で以下の設定を確認し、必要に応じて修正します。これらの設定の変更または確認が完了したら、[**Save**] をクリックします。
    
   |**パラメーター**|**推奨設定**|
   |:-----|:-----|
   |Device Information - Phone Button Template  <br/> | 標準の Cisco テレプレゼンスコーデック C40 <br/> |
   |Device Information - Common Phone Profile  <br/> | Standard Common Phone Profile <br/> |
   |Device Information - Calling Search Space  <br/> | CSS_SfBVideoInterop <br/> |
   |Device Information - AAR Calling Search Space  <br/> | CSS_SfBVideoInterop <br/> |
   |Device Information - Media Resource Group List  <br/> | MRGL_SfBVideoInterop <br/> |
   |Protocol Specific Information - Device Security Profile  <br/> | Cisco テレプレゼンスコーデック C40 <br/> |
   |Protocol Specific Information - Rerouting Calling Search Space  <br/> | CSS_SfBVideoInterop <br/> |
   |プロトコル固有の情報-購読通話の検索スペース  <br/> | CSS_SfBVideoInterop <br/> |
   |Protocol Specific Information - SIP Profile  <br/> | Standard SIP Profile for Telepresence Endpoint <br/> |
   
3. VTC 構成を保存したら、デバイスの [Phone Configuration] 画面にもう一度移動します。 Association グループの画面の上部で、ビデオ相互運用の関連付けをクリックします。 この操作を行うと、[Directory Number Configuration] 画面が表示されます。 
    
4. 次の設定を確認し、必要に応じて修正します。 
    
    次に示すように、[Directory Number Information] と [Directory Number Settings] を適切に変更します。
    
   |**パラメーター**|**推奨設定**|
   |:-----|:-----|
   | Directory Number Information - Route Partition <br/> | SfBVideoInterop_RoutePartition <br/> |
   |Directory Number Settings - Calling Search Space  <br/> | CSS_SfBVideoInterop <br/> |
   |MLPP Alternate Party and Confidential Access Level Settings - MLPP Calling Search Space  <br/> | CSS_SfBVideoInterop <br/> |
   |デバイスに表示される1行目 (発信者番号)  <br/> | 自由に設定 <br/> |
   |デバイス上の1行目 (発信者番号)  <br/> | 自由に設定 <br/> |
   
5. 変更が完了したら、画面の上部までスクロールし、[**Save**] をクリックします。 
    
これで、この VTC デバイスの構成が完了しました。社内の他の VTC デバイスに対して、このプロセスを繰り返してください。

