---
title: Skype for Business Server との相互運用用に CUCM を構成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: eab3d9f6-ec40-49bf-9162-1a7f5a59451f
description: '概要: Skype for Business Server で動作するように CUCM を構成します。'
ms.openlocfilehash: 8324e146147480bb682c2cc18c62a96e95a130e3
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36235653"
---
# <a name="configure-cucm-for-interoperation-with-skype-for-business-server"></a>Skype for Business Server との相互運用用に CUCM を構成する
 
**概要:** Skype for Business Server で動作するように CUCM を構成します。
  
> [!CAUTION]
> この機能は、TCP 経由の Trunks セットアップを使って、Cisco ユニファイドコミュニケーションマネージャー (CallManager、または CUCM) バージョン10.5 でテストされています。 作業を続行する前に、CUCM 環境がこれらの条件を満たしていることを確認してください。 
  
ここで説明する設定は、VIS と連携するように CUCM を設定する方法の例としてのみ使用されています。 CUCM の別の機能を他の方法で設定/使用して同じ結果を実現することもできます。 特定のシナリオ向けの最適な構成に関する推奨事項は示されていません。
  
VIS との相互運用を実現するには、多くの CUCM の設定を確認または変更する必要があります。必要な設定を確実に実行するには、以下の手順に従います。
  
### <a name="configure-the-cucm"></a>CUCM を構成する

1. CUCM にログインして、「Cisco ユニファイ CM 管理-\>通話ルーティング-\>制御\>パーティションのクラス」に移動します。
    
2. [Partition Configuration] 画面で、パーティションの名前と説明を入力し、[**Add New**] をクリックします。
    
3. 「Cisco ユニファイド CM の管理\>」に移動\>します。コントロール\>呼び出しの検索スペースのクラスを指定します。
    
4. [Calling Search Space Configuration] 画面で、Calling Search Space (コーリング サーチ スペース) の名前を入力し、[Selected Partitions] には直前に作成したパーティーションの名前を入力します。完了したら、[**Save**] をクリックします。
    
5. 「Cisco ユニファイド CM 管理-\>システム-\>セキュリティ-\>SIP トランクセキュリティプロファイル」に移動します。
    
6. [SIP Trunk Security Profile Configuration] 画面で、図のように [SIP Trunk Security Profile Information] のオプションを設定し、[**Add New**] をクリックします。
    
   |**パラメーター**|**推奨設定**|
   |:-----|:-----|
   |名前  <br/> |SfBVideoInterop_SecurityProfile  <br/> |
   |Device Security Mode  <br/> |Non Secure  <br/> |
   |Incoming Transport Type  <br/> |TCP + UDP  <br/> |
   |Outgoing Transport Type  <br/> |TCP  <br/> |
   |Incoming Port  <br/> |5060  <br/> |
   
7. 「Cisco ユニファイド CM の管理\>-デバイス\>の設定-\>SIP プロフィール」に移動します。
    
8. [SIP Profile Configuration] 画面で、図のように [SIP Profile Information] のオプションを設定します。 
    
   |**パラメーター**|**推奨設定**|
   |:-----|:-----|
   |Name  <br/> |SfBVideoInterop_SIPProfile  <br/> |
   |説明  <br/> |SfBVideoInterop_SIPProfile  <br/> |
   
9. 同じ画面で、[SDP プロファイル情報] セクションまで下にスクロールします。 [**SDP Session-level Bandwidth Modifier for Early Offer and Re-invites**] オプションは、既定では [TIAS and AS] に設定されています。 このオプションを [TIAS only] に変更します。 このオプションを既定の設定のままにした場合、Skype for Business Server は SIP メッセージの帯域幅の補助情報を認識しません。 TIAS は Transport Independent Application Specific (トランスポート非依存アプリケーション固有) の意味で、AS は Application Specific (アプリケーション固有) の意味です。 これらは、RFC3890 で規定されている SIP のオプションです。
    
10. 同じ画面で、さらに下にスクロールします。 SIP プロフィールのトランク固有の構成で、「**音声通話とビデオ通話の早期サポート**」を選択して、「**必須 (必要に応じて MTP を挿入)** 」オプションを設定します。 この設定を行うと、CUCM で、Early Offer (アーリー オファー) を使用して発信 SIP 通話を設定できるようになります。 CUCM 8.5 以降の新機能の 1 つとして、メディア終端ポイント (MTP) が必要でない、Early Offer を使用した発信通話の設定をサポートしています。
    
11. [SIP Options ping] セクションで、[Enable OPTIONS Ping to monitor destination status for Trunks with Service Type 'None (Default)'] の横にあるボックスがオンになっていることを確認します。
    
12. 終了したら、[**Add New**] をクリックします。
    
13. 「Cisco 統合 CM 管理-\>デバイス-\>トランク」に移動します。 
    
14. [Device Protocol] を [SIP] に設定し、[**Next**] をクリックします。
    
15. [Device Information] で、[Device Name] と [Description] (通常は "SfBVideoInterop_SIPTrunk" の形式) の設定を行い、[Media Resource Group List] を、適切なメディア リソースが含まれる MRGL に設定します。 
    
16. さらに下にスクロールします。 ビデオ通話には [Media Termination Point (MTP)] は不要であり、まだオフにされていない場合はオフにします。 [**Run on all active Unified CM Nodes**] のオプションをオンにします。 Skype for Business Server の設定には、すべての CUCM ノードを追加する必要があることに注意してください。
    
17. さらに下にスクロールします。 以下に示すように、[Inbound Calls and Connected Party Settings] のオプションを設定します。
    
    |**パラメーター**|**推奨設定**|
    |:-----|:-----|
    |Calling Search Space  <br/> |CSS_SfBVideoInterop  <br/> |
    |AAR Calling Search Space  <br/> |CSS_SfBVideoInterop  <br/> |
    |Connected Party Transformation CSS  <br/> |CSS_SfBVideoInterop  <br/> |
   
18. さらに下にスクロールします。 SIP トランク構成の「SIP 情報の送信先」セクションで、VIS Pool の FQDN またはプール内の個々の VIS サーバーの IP アドレスを指定します (複数のエントリを追加する)。 [Destination Port] で、VIS が CUCM からの接続をリッスンするポートを指定します (既定値は 6001)。 また以下のように、以前に作成した SIP トランクのセキュリティ プロファイルと SIP プロファイルも指定します。
    
    |**パラメーター**|**推奨設定**|
    |:-----|:-----|
    |SIP Trunk Security Profile  <br/> |SfBVideoInterop_SecurityProfile  <br/> |
    |Rerouting Calling Search Space  <br/> |CSS_SfBVideoInterop  <br/> |
    |Out-of-Dialog Refer Calling Search Space  <br/> |CSS_SfBVideoInterop  <br/> |
    |Subscribe Calling Search Space  <br/> |CSS_SfBVideoInterop  <br/> |
    |SIP Profile  <br/> |SfBVideoInterop_SIPProfile  <br/> |
    |DTMF Signaling Method  <br/> |RFC 2833  <br/> |
   
19.  さらに下にスクロールします。 システムに適した [Recording Information] の設定を行います。 **[なし**] に設定したままにしておくこともできます。 
    
20. 終了したら、[**Add New**] をクリックします。
    
21. 「Cisco ユニファイド CM の管理\>」に移動\>します。通話\>ルーティング-ルート/ハント-ルートパターン。
    
22. [Route Pattern Configuration] 画面で、以下に示すようにパターン定義のパラメーターを入力します。[Called Party Transformations] セクションまで下にスクロールし、以下に示すようにマスクを設定して、完了したら [**Add New**] をクリックします。
    
    |**パラメーター**|**推奨設定**|
    |:-----|:-----|
    |Route Pattern  <br/> |7779999  <br/> |
    |Route Partition  <br/> |SfBVideoInterop_RoutePartition  <br/> |
    |Description  <br/> |Partition for SfBVideoInterop  <br/> |
    |Gateway/Route List  <br/> |SfBVideoInterop_SIPTrunk  <br/> |
    |Called Party Transform Mask  <br/> |+14257779999  <br/> |
   
23. 「Cisco ユニファイド CM 管理-\>通話ルーティング-\>SIP ルートパターン」に移動します。
    
24. [SIP Route Pattern Configuration] 画面で、以下に示すように [Pattern Definition] のオプションを設定し、[**Add New**] をクリックします。
    
    |**パラメーター**|**推奨設定**|
    |:-----|:-----|
    | Pattern Usage <br/> |Domain Routing  <br/> |
    |IPv4 Pattern  <br/> |contoso.com (IPv6 を使用する場合は空白のまま)  <br/> |
    |IPv6 Pattern  <br/> |contoso.com (IPv4 を使用する場合は空白のまま)  <br/> |
    |Description  <br/> |SIPRoute Pattern to mediarv  <br/> |
    |Route Partition  <br/> |SfBVideoInterop_RoutePartition  <br/> |
    |SIP Trunk/Route List  <br/> |SfBVideoInterop_SIPTrunk  <br/> |
    |[Block Pattern] チェック ボックス  <br/> |オフのまま  <br/> |
   
25. 音声またはビデオのビット レートを既定の設定から変更した場合は、それらを既定に戻す必要があります。 音声/ビデオ通話のビットレートを設定するには、「Cisco 統合 CM 管理\>\>\>」に移動します。 参照用に既定値を以下に示します。
    
    |**パラメーター**|**推奨設定**|
    |:-----|:-----|
    |Region  <br/> |既定  <br/> |
    |オーディオコーデックの基本設定リスト  <br/> |システムの既定値  <br/> |
    |オーディオビットレートの最大値  <br/> |64 kbps (722, G)  <br/> |
    |ビデオ通話の最大セッションビットレート  <br/> |20万 kbps  <br/> |
    |セッションの最大ビットレート  <br/> |20億 kbps  <br/> |
   
この時点で、CUCM ビデオゲートウェイは、VIS と連携するように構成されています。 対応する構成は、統合する各 VTC に対して行う必要があります。
> [!NOTE]
> 回復性を向上させるために、2つ目のビデオ相互運用サーバーまたは VIS プールで動作するように、この CUCM ゲートウェイを構成することができます。 詳細については、「[Resiliency mechanisms](../../plan-your-deployment/video-interop-server.md#resiliency)」を参照してください。
  
## <a name="see-also"></a>関連項目

[Skype for Business Server との相互運用用に VTC を構成する](configure-a-vtc-for-interoperation.md)
