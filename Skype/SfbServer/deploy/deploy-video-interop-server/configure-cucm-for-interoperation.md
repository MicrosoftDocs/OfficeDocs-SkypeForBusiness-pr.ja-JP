---
title: Skype for Business Server 2015 と相互運用するための CUCM の構成
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: eab3d9f6-ec40-49bf-9162-1a7f5a59451f
description: '概要: ビジネス サーバー 2015 の Skype 上で動作する CUCM を構成します。'
ms.openlocfilehash: f05b55b875cb344da369f5fd74f16a73faf43907
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="configure-cucm-for-interoperation-with-skype-for-business-server-2015"></a>Skype for Business Server 2015 と相互運用するための CUCM の構成
 
**の概要:**CUCM ビジネス サーバー 2015 の Skype を使用するを構成します。
  
> [!CAUTION]
> この機能は、TCP 経由のみで設定されたトランクを使用する CUCM バージョン 10.5 でテストされています。作業を続行する前に、CUCM 環境がこれらの条件を満たしていることを確認してください。 
  
ここで説明する設定は、CUCM を構成する方法の例として、VIS. を操作するには CUCM の別の機能を他の方法で設定/使用して同じ結果を実現することもできます。 特定のシナリオ向けの最適な構成に関する推奨事項は示されていません。
  
VIS との相互運用を実現するには、多くの CUCM の設定を確認または変更する必要があります。必要な設定を確実に実行するには、以下の手順に従います。
  
### <a name="configure-the-cucm"></a>CUCM を構成する

1. CUCM にログインし、移動する Cisco ユニファイド CM 管理 -\>の呼び出しのルーティング ・\>クラスのコントロールの\>パーティションです。
    
2. [Partition Configuration] 画面で、パーティションの名前と説明を入力し、[**Add New**] をクリックします。
    
3. 移動 Cisco の統合管理 - CM\>呼び出しルーティング -\>のコントロールのクラス\>検索の領域を呼び出すことです。
    
4. [Calling Search Space Configuration] 画面で、Calling Search Space (コーリング サーチ スペース) の名前を入力し、[Selected Partitions] には直前に作成したパーティーションの名前を入力します。完了したら、[**Save**] をクリックします。
    
5. 移動 Cisco の統合管理 - CM\>システム -\>セキュリティ ・\>SIP トランクのセキュリティ プロファイルです。
    
6. [SIP Trunk Security Profile Configuration] 画面で、図のように [SIP Trunk Security Profile Information] のオプションを設定し、[**Add New**] をクリックします。
    
   |**パラメーター**|**推奨設定**|
   |:-----|:-----|
   |Name  <br/> |SfBVideoInterop_SecurityProfile  <br/> |
   |Device Security Mode  <br/> |Non Secure  <br/> |
   |Incoming Transport Type  <br/> |TCP + UDP  <br/> |
   |Outgoing Transport Type  <br/> |TCP  <br/> |
   |Incoming Port  <br/> |5060  <br/> |
   
7. 移動 Cisco の統合管理 - CM\>デバイス ・\>デバイスの設定 -\>SIP プロファイルです。
    
8. [SIP Profile Configuration] 画面で、図のように [SIP Profile Information] のオプションを設定します。 
    
   |**パラメーター**|**推奨設定**|
   |:-----|:-----|
   |Name  <br/> |SfBVideoInterop_SIPProfile  <br/> |
   |Description  <br/> |SfBVideoInterop_SIPProfile  <br/> |
   
9. 同じ画面上には、SDP のプロファイル情報] セクションまでスクロールします。 [**SDP Session-level Bandwidth Modifier for Early Offer and Re-invites**] オプションは、既定では [TIAS and AS] に設定されています。 このオプションを [TIAS only] に変更します。 このオプションを既定の設定のままにする Skype のビジネス サーバーは帯域幅修飾子については、SIP メッセージでを理解できません。 TIAS は Transport Independent Application Specific (トランスポート非依存アプリケーション固有) の意味で、AS は Application Specific (アプリケーション固有) の意味です。 これらは、RFC3890 で規定されている SIP のオプションです。
    
10. 同じ画面で、さらに下にスクロールします。 [SIP プロファイルのトランクの特定の構成を選択 * * 初期サポートの音声とビデオ通話 * * では、**必須 (必要な場合は、MTP を挿入する)** ] オプションを設定します。 この設定を行うと、CUCM で、Early Offer (アーリー オファー) を使用して発信 SIP 通話を設定できるようになります。 CUCM 8.5 以降の新機能の 1 つとして、メディア終端ポイント (MTP) が必要でない、Early Offer を使用した発信通話の設定をサポートしています。
    
11. [SIP Options ping] セクションで、[Enable OPTIONS Ping to monitor destination status for Trunks with Service Type 'None (Default)'] の横にあるボックスがオンになっていることを確認します。
    
12. 終了したら、[**Add New**] をクリックします。
    
13. 移動 Cisco の統合管理 - CM\>デバイス ・\>トランク。 
    
14. [Device Protocol] を [SIP] に設定し、[**Next**] をクリックします。
    
15. [Device Information] で、[Device Name] と [Description] (通常は "SfBVideoInterop_SIPTrunk" の形式) の設定を行い、[Media Resource Group List] を、適切なメディア リソースが含まれる MRGL に設定します。 
    
16. さらに下にスクロールします。 ビデオ通話には [Media Termination Point (MTP)] は不要であり、まだオフにされていない場合はオフにします。 [**Run on all active Unified CM Nodes**] のオプションをオンにします。 ビジネス サーバー構成の Skype に CUCM のすべてのノードを追加する必要があることに注意してください。
    
17. さらに下にスクロールします。以下に示すように、[Inbound Calls and Connected Party Settings] のオプションを設定します。
    
    |**パラメーター**|**推奨設定**|
    |:-----|:-----|
    |Calling Search Space  <br/> |CSS_SfBVideoInterop  <br/> |
    |AAR Calling Search Space  <br/> |CSS_SfBVideoInterop  <br/> |
    |Connected Party Transformation CSS  <br/> |CSS_SfBVideoInterop  <br/> |
   
18. さらに下へスクロールします。 [情報の送信先の SIP SIP トランクの構成のセクションで、(複数のエントリを追加すること) のプールに VIS プールの FQDN または VIS の個々 のサーバーの IP アドレスを指定します。 [Destination Port] で、VIS が CUCM からの接続をリッスンするポートを指定します (既定値は 6001)。 また以下のように、以前に作成した SIP トランクのセキュリティ プロファイルと SIP プロファイルも指定します。
    
    |**パラメーター**|**推奨設定**|
    |:-----|:-----|
    |SIP Trunk Security Profile  <br/> |SfBVideoInterop_SecurityProfile  <br/> |
    |Rerouting Calling Search Space  <br/> |CSS_SfBVideoInterop  <br/> |
    |Out-of-Dialog Refer Calling Search Space  <br/> |CSS_SfBVideoInterop  <br/> |
    |Subscribe Calling Search Space  <br/> |CSS_SfBVideoInterop  <br/> |
    |SIP Profile  <br/> |SfBVideoInterop_SIPProfile  <br/> |
    |DTMF Signaling Method  <br/> |RFC 2833  <br/> |
   
19.  さらに下にスクロールします。 システムに適した [Recording Information] の設定を行います。 [**なし]**のままにしても問題があります。 
    
20. 終了したら、[**Add New**] をクリックします。
    
21. 移動する Cisco ユニファイド CM 管理 -\>呼び出しのルーティング ・\>ルート/ハント ・\>ルート パターンです。
    
22. [Route Pattern Configuration] 画面で、以下に示すようにパターン定義のパラメーターを入力します。[Called Party Transformations] セクションまで下にスクロールし、以下に示すようにマスクを設定して、完了したら [**Add New**] をクリックします。
    
    |**パラメーター**|**推奨設定**|
    |:-----|:-----|
    |Route Pattern  <br/> |7779999  <br/> |
    |Route Partition  <br/> |SfBVideoInterop_RoutePartition  <br/> |
    |Description  <br/> |Partition for SfBVideoInterop  <br/> |
    |Gateway/Route List  <br/> |SfBVideoInterop_SIPTrunk  <br/> |
    |Called Party Transform Mask  <br/> |+14257779999  <br/> |
   
23. 移動 Cisco の統合管理 - CM\>呼び出しルーティング -\>SIP ルート パターンです。
    
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
   
25. 音声またはビデオのビット レートを既定の設定から変更した場合は、それらを既定に戻す必要があります。 呼び出しのオーディオ/ビデオのビット レートを設定するのには次のように移動する Cisco ユニファイド CM 管理 -\>システム -\>地域情報 -\>地域。 参照用に既定値を以下に示します。
    
    |**パラメーター**|**推奨設定**|
    |:-----|:-----|
    |Region  <br/> |Default  <br/> |
    |Audio Codec Preference List  <br/> |System Default  <br/> |
    |Maximum Audio Bit Rate  <br/> |64 kbps (G.722, G.711)  <br/> |
    |Maximum Session Bit Rate for Video Calls  <br/> |200000 kbps  <br/> |
    |Maximum Session Bit Rate  <br/> |2000000000 kbps  <br/> |
   
この時点で、CUCM ビデオ ゲートウェイは VIS と連携するように構成されています。 統合する必要がある各 VTC 上で、対応する構成を行う必要があります。
> [!NOTE]
> 弾力性を高めるためには、2 番目のビデオの相互運用機能のサーバーまたは VIS プールを操作するには、この CUCM ゲートウェイを構成する場合があります。 詳細については、「[Resiliency mechanisms](../../plan-your-deployment/video-interop-server.md#resiliency)」を参照してください。
  
## <a name="see-also"></a>関連項目

#### 

[ビジネス サーバー 2015 の Skype での相互運用のため、VTC を構成します。](configure-a-vtc-for-interoperation.md)

