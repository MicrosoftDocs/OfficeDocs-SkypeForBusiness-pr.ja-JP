---
title: Skype for Business Server との相互運用のための CUCM の構成
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
ms.assetid: eab3d9f6-ec40-49bf-9162-1a7f5a59451f
description: '概要: Skype for Business Server と動作する CUCM を構成します。'
ms.openlocfilehash: 82fa48a185b22973d35bc19484e733e6436ba43e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49837117"
---
# <a name="configure-cucm-for-interoperation-with-skype-for-business-server"></a>Skype for Business Server との相互運用のための CUCM の構成
 
**概要:** Skype for Business Server と動作する CUCM を構成します。
  
> [!CAUTION]
> この機能は、TCP を使用したトランクセットアップのみを使用して、Cisco Unified Communications Manager (CallManager または CUCM) バージョン 10.5 でテストされます。 次に進む前に、CUCM 環境がこれらの条件を満たしていることを確認します。 
  
ここで説明する設定は、VIS を使用するように CUCM を構成する方法の例としてのみ使用されます。 代替 CUCM 機能のその他の設定や使用法も、同じ結果を得る目的で使用できます。 特定のシナリオに最適な構成に関する推奨事項は示されていません。
  
VIS と相互運用するには、多くの CUCM 設定を確認または変更する必要があります。 必要な設定が見つからないのを避けるため、以下の手順に従ってください。
  
### <a name="configure-the-cucm"></a>CUCM を構成する

1. CUCM にログインし、[Cisco Unified CM Administration- \> Call Routing- \> Class of Control- Partition] に移動 \> します。
    
2. [パーティション構成] 画面で、パーティション名と説明を入力し、[新規追加] を **クリックします**。
    
3. [Cisco Unified CM Administration- \> Call Routing- \> Class of Control- Calling Search \> Space] に移動します。
    
4. [Calling Search Space Configuration] 画面で、呼び出し元の検索スペースの名前を入力し、[Selected Partitions] に作成したパーティションの名前を入力します。 完了したら **、[保存** ] をクリックします。
    
5. [Cisco Unified CM Administration- \> System- \> Security- \> SIP Trunk Security Profile] に移動します。
    
6. [SIP トランク セキュリティ プロファイルの構成] 画面で、[SIP トランク セキュリティ プロファイル情報] オプションを次のように設定し、[新規追加] を **クリックします**。
    
   |**パラメーター**|**推奨される設定値**|
   |:-----|:-----|
   |名前  <br/> |SfBVideoInterop_SecurityProfile  <br/> |
   |デバイス セキュリティ モード  <br/> |セキュリティで保護されていない  <br/> |
   |受信トランスポートの種類  <br/> |TCP + UDP  <br/> |
   |送信トランスポートの種類  <br/> |TCP  <br/> |
   |受信ポート  <br/> |5060  <br/> |
   
7. [Cisco Unified CM Administration- \> Device- \> Device Settings- \> SIP Profile] に移動します。
    
8. [SIP プロファイル構成] 画面で、[SIP プロファイル情報] オプションを次のように設定します。 
    
   |**パラメーター**|**推奨される設定値**|
   |:-----|:-----|
   |名前  <br/> |SfBVideoInterop_SIPProfile  <br/> |
   |説明  <br/> |SfBVideoInterop_SIPProfile  <br/> |
   
9. 同じ画面で、[SDP プロファイル情報] セクションまで下にスクロールします。 [ **早期提供と** 再招待] オプションの SDP セッション レベルの帯域幅修飾子は、既定で TIAS と AS に設定されています。 このオプションを TIAS にのみ変更します。 このオプションを既定の設定のままにした場合、Skype for Business Server は SIP メッセージの帯域幅修飾子情報を理解しません。 TIAS は Transport Independent Application Specific を意味し、AS はアプリケーション固有を意味します。 これらは RFC3890 で指定されている SIP オプションです。
    
10. 同じ画面で、さらに下にスクロールします。 SIP プロファイルのトランク固有の構成で、音声通話とビデオ通話の早期提供サポートを選択し、必須 (必要に応じて **MTP** を挿入) オプションに設定します。 これにより、CUCM で早期オファーを使用して発信 SIP 通話を設定できます。 CUCM 8.5 以降の新機能の 1 つは、メディア終端ポイント (MTP) を必要とせず、早期オファーによる発信通話セットアップをサポートする点です。
    
11. [SIP オプション ping] セクションで、[OPTIONS Ping を有効にして、サービスの種類が 'なし (既定)' のトランクの宛先の状態を監視する] チェック ボックスがオンになっています。
    
12. 完了したら、[新規追加] を **クリックします**。
    
13. [Cisco Unified CM Administration- \> Device- Trunk] に移動 \> します。 
    
14. デバイス プロトコルを SIP に設定し、[次へ] を **押します**。
    
15. [デバイス情報] で、デバイス名と説明 (おそらく SfBVideoInterop_SIPTrunk など) を設定し、メディア リソース グループの一覧を、適切なメディア リソースを含む MRGL に設定します。 
    
16. さらに下にスクロールします。 ビデオ通話にメディア終端ポイント (MTP) は必要ありません 。まだオフにされていない場合は、オフにします。 アクティブなすべての **Unified CM ノードで実行するオプションをオンにします**。 すべての CUCM ノードを Skype for Business Server 構成に追加する必要があります。
    
17. さらに下にスクロールします。 次に示すように、[着信呼び出しと接続済みパーティの設定] オプションを設定します。
    
    |**パラメーター**|**推奨される設定値**|
    |:-----|:-----|
    |Calling Search Space  <br/> |CSS_SfBVideoInterop  <br/> |
    |AAR Calling Search Space  <br/> |CSS_SfBVideoInterop  <br/> |
    |接続されたパーティー変換 CSS  <br/> |CSS_SfBVideoInterop  <br/> |
   
18. さらに下にスクロールします。 SIP トランク構成の [SIP 情報の宛先] セクションで、VIS プールの FQDN またはプール内の個々の VIS サーバーの IP アドレスを指定します (複数のエントリを追加)。 [Destination Port] で、VIS が CUCM からの接続をリッスンしているポートを指定します (既定値は 6001 です)。 また、次に示すように、前に作成した SIP トランク セキュリティ プロファイルと SIP プロファイルも指定します。
    
    |**パラメーター**|**推奨される設定値**|
    |:-----|:-----|
    |SIP トランク セキュリティ プロファイル  <br/> |SfBVideoInterop_SecurityProfile  <br/> |
    |呼び出し元の検索スペースの再ルーティング  <br/> |CSS_SfBVideoInterop  <br/> |
    |Out-of-Dialog Refer Calling Search Space  <br/> |CSS_SfBVideoInterop  <br/> |
    |Subscribe Calling Search Space  <br/> |CSS_SfBVideoInterop  <br/> |
    |SIP プロファイル  <br/> |SfBVideoInterop_SIPProfile  <br/> |
    |DTMF Signaling Method  <br/> |RFC 2833  <br/> |
   
19.  さらに下にスクロールします。 システムに応じてレコーディング情報を設定します。 [なし] に設定したままで **問題ありません**。 
    
20. 完了したら、[新規追加] を **クリックします**。
    
21. [Cisco Unified CM Administration- \> Call Routing- \> Route/Hunt- \> Route Pattern] に移動します。
    
22. [ルート パターン構成] 画面で、以下に示すパターン定義パラメーターを入力します。 [呼び出し済みパーティ変換] セクションまで下にスクロールし、次に示すようにマスクを設定し、完了したら [新規追加] **をクリック** します。
    
    |**パラメーター**|**推奨される設定値**|
    |:-----|:-----|
    |ルート パターン  <br/> |7779999  <br/> |
    |ルート パーティション  <br/> |SfBVideoInterop_RoutePartition  <br/> |
    |説明  <br/> |SfBVideoInterop のパーティション  <br/> |
    |ゲートウェイ/ルート一覧  <br/> |SfBVideoInterop_SIPTrunk  <br/> |
    |呼び出されたパーティー変換マスク  <br/> |+14257779999  <br/> |
   
23. [Cisco Unified CM Administration- \> Call Routing- \> SIP Route Pattern] に移動します。
    
24. [SIP ルート パターン構成] 画面で、パターン定義オプションを次のように設定し、[新規追加] **をクリックします**。
    
    |**パラメーター**|**推奨される設定値**|
    |:-----|:-----|
    | パターンの使用 <br/> |ドメイン ルーティング  <br/> |
    |IPv4 パターン  <br/> |contoso.com (IPv6 を使用する場合は空白のままにします)  <br/> |
    |IPv6 パターン  <br/> |contoso.com (IPv4 を使用する場合は空白のままにします)  <br/> |
    |説明  <br/> |MEDIARV への SIPRoute パターン  <br/> |
    |ルート パーティション  <br/> |SfBVideoInterop_RoutePartition  <br/> |
    |SIP トランク/ルート一覧  <br/> |SfBVideoInterop_SIPTrunk  <br/> |
    |[ブロック パターン] チェック ボックス  <br/> |オフのままにする  <br/> |
   
25. オーディオまたはビデオのビット レートを既定の設定から変更した場合は、既定値に戻す必要があります。 音声ビデオ通話のビット レートを設定するには、[Cisco Unified CM Administration- \> System- \> Region Information- Region] に移動 \> します。 参照用の既定値を以下に示します。
    
    |**パラメーター**|**推奨される設定値**|
    |:-----|:-----|
    |Region  <br/> |既定値  <br/> |
    |オーディオ コーデックの基本設定の一覧  <br/> |システムの既定値  <br/> |
    |最大オーディオ ビット レート  <br/> |64 kbps (G.722、G.711)  <br/> |
    |ビデオ通話の最大セッション ビット レート  <br/> |200000 kbps  <br/> |
    |最大セッション ビット レート  <br/> |2000000000 kbps  <br/> |
   
この時点で、CUCM ビデオ ゲートウェイは VIS を使用するように構成されています。 対応する構成は、統合する各 VTC で行う必要があります。
> [!NOTE]
> 回復性を向上させるために、この CUCM ゲートウェイが 2 つ目のビデオ相互運用サーバーまたは VIS プールで動作する構成が必要になる場合があります。 詳細 [については、「復元メカニズム」](../../plan-your-deployment/video-interop-server.md#resiliency) を参照してください。
  
## <a name="see-also"></a>関連項目

[Skype for Business Server との相互運用のための VTC の構成](configure-a-vtc-for-interoperation.md)
