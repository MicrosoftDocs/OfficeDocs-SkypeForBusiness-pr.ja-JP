---
title: デバイスとの相互運用用に CUCM をSkype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: eab3d9f6-ec40-49bf-9162-1a7f5a59451f
description: '概要: CUCM を構成して、デバイスをSkype for Business Server。'
ms.openlocfilehash: 809ad19e89f398c507673ec677b4ce882d341327
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60741323"
---
# <a name="configure-cucm-for-interoperation-with-skype-for-business-server"></a>デバイスとの相互運用用に CUCM をSkype for Business Server
 
**概要:** CUCM を構成して、デバイスをSkype for Business Server。
  
> [!CAUTION]
> この機能は、TCP のみを使用したトランクのセットアップを使用して、Cisco Unified Communications Manager (CallManager、または CUCM) バージョン 10.5 でテストされます。 次に進む前に、CUCM 環境がこれらの条件を満たしていることを確認します。 
  
ここで説明する設定は、CUCM を VIS で動作するように構成する方法の例としてのみ使用されます。 他の設定や代替 CUCM 機能の使用法も、同じ結果を得る目的で使用できます。 特定のシナリオに最適な構成に関する推奨事項は示されていません。
  
VIS との相互運用のために、多数の CUCM 設定を確認または変更する必要があります。 必要な設定が見つからないのを避けるために、以下の手順に従います。
  
### <a name="configure-the-cucm"></a>CUCM を構成する

1. CUCM にログインし、Cisco Unified CM Administration- \> Call Routing- \> Class of Control- Partition に移動 \> します。
    
2. [パーティション構成] 画面で、パーティション名と説明を入力し、[新規追加] を **クリックします**。
    
3. [Cisco Unified CM Administration- \> Call Routing- \> Class of Control- Calling Search \> Space] に移動します。
    
4. [コーリング サーチ スペースの構成] 画面で、コーリング サーチ スペースの名前を入力し、[選択したパーティション] に、作成したパーティションの名前を入力します。 [完了 **したら保存]** をクリックします。
    
5. [Cisco Unified CM Administration- \> System- \> Security- \> SIP トランク セキュリティ プロファイル] に移動します。
    
6. [SIP トランク セキュリティ プロファイルの構成] 画面で、表示されている SIP トランク セキュリティ プロファイル情報オプションを設定し、[新規追加] を **クリックします**。
    
   |**パラメーター**|**推奨される設定値**|
   |:-----|:-----|
   |名前  <br/> |SfBVideoInterop_SecurityProfile  <br/> |
   |デバイス セキュリティ モード  <br/> |セキュリティで保護されていない  <br/> |
   |受信トランスポートの種類  <br/> |TCP + UDP  <br/> |
   |送信トランスポートの種類  <br/> |TCP  <br/> |
   |受信ポート  <br/> |5060  <br/> |
   
7. [Cisco Unified CM Administration- \> Device- \> Device 設定- \> SIP プロファイル] に移動します。
    
8. [SIP プロファイル構成] 画面で、次に示すように SIP プロファイル情報オプションを設定します。 
    
   |**パラメーター**|**推奨される設定値**|
   |:-----|:-----|
   |名前  <br/> |SfBVideoInterop_SIPProfile  <br/> |
   |説明  <br/> |SfBVideoInterop_SIPProfile  <br/> |
   
9. 同じ画面で、[SDP プロファイル情報] セクションまで下にスクロールします。 [ **早期オファーと** 再招待の SDP セッション レベルの帯域幅修飾子] オプションは、既定では TIAS と AS に設定されています。 このオプションを TIAS にのみ変更します。 このオプションを既定の設定のままにした場合Skype for Business Server SIP メッセージの帯域幅修飾子情報が理解されません。 TIAS はトランスポート独立アプリケーション固有を意味し、AS はアプリケーション固有を意味します。 これらは RFC3890 で指定された SIP オプションです。
    
10. 同じ画面で、さらに下にスクロールします。 [SIP プロファイルのトランク固有の構成]で、[音声通話とビデオ通話の早期提供サポート] を選択し、必須 (必要に応じて MTP を挿入 **する)** オプションに設定します。 これにより、CUCM は早期オファーを使用して発信 SIP 通話を設定できます。 CUCM 8.5 以降の新機能の 1 つは、メディアターミネーション ポイント (MTP) を必要とせずに、早期オファーによる発信通話セットアップをサポートする点です。
    
11. [SIP オプション ping] セクションで、[Enable OPTIONS Ping] の横にあるチェック ボックスがオンにされ、サービスの種類が [なし (既定)] のトランクの宛先状態を監視します。
    
12. 完了したら、[新規追加] を **クリックします**。
    
13. [Cisco Unified CM Administration- \> Device- \> Trunk] に移動します。 
    
14. デバイス プロトコルを SIP に設定し、[次へ] を **押します**。
    
15. [デバイス情報] で、[デバイス名] と [説明] (おそらく SfBVideoInterop_SIPTrunk など) を設定し、メディア リソース グループリストに適切なメディア リソースを含む MRGL を設定します。 
    
16. さらに下にスクロールします。 ビデオ通話にメディアターミネーション ポイント (MTP) は必要ありません。まだオフにされていない場合は、オフにします。 [すべてのアクティブな **Unified CM ノードで実行する] オプションをオンにします**。 すべての CUCM ノードを新しい構成に追加するSkype for Business Server注意してください。
    
17. さらに下にスクロールします。 次に示すように、受信通話と接続設定オプションを設定します。
    
    |**パラメーター**|**推奨される設定値**|
    |:-----|:-----|
    |コーリング サーチ スペース  <br/> |CSS_SfBVideoInterop  <br/> |
    |AAR コーリング サーチ スペース  <br/> |CSS_SfBVideoInterop  <br/> |
    |接続されたパーティ変換 CSS  <br/> |CSS_SfBVideoInterop  <br/> |
   
18. さらに下にスクロールします。 SIP トランク構成の [SIP 情報の宛先] セクションで、VIS プールの FQDN またはプール内の個々の VIS サーバーの IP アドレス (複数のエントリの追加) を指定します。 宛先ポートで、VIS が CUCM からの接続をリッスンしているポートを指定します (既定値は 6001 です)。 また、示すように、前に作成した SIP トランク セキュリティ プロファイルと SIP プロファイルも指定します。
    
    |**パラメーター**|**推奨される設定値**|
    |:-----|:-----|
    |SIP トランク セキュリティ プロファイル  <br/> |SfBVideoInterop_SecurityProfile  <br/> |
    |コーリング サーチ スペースの再ルーティング  <br/> |CSS_SfBVideoInterop  <br/> |
    |Out-of-Dialog Refer Calling Search Space  <br/> |CSS_SfBVideoInterop  <br/> |
    |Subscribe Calling Search Space  <br/> |CSS_SfBVideoInterop  <br/> |
    |SIP プロファイル  <br/> |SfBVideoInterop_SIPProfile  <br/> |
    |DTMF Signaling メソッド  <br/> |RFC 2833  <br/> |
   
19.  さらに下にスクロールします。 システムに合ったレコーディング情報を設定します。 [なし] に設定したままにしておいても問題 **ありません**。 
    
20. 完了したら、[新規追加] を **クリックします**。
    
21. [Cisco Unified CM Administration- \> Call Routing- \> Route/Hunt- Route- Route pattern] \> に移動します。
    
22. [ルート パターンの構成] 画面で、次に示すパターン定義パラメーターを入力します。 [通話相手の変換] セクションまで下にスクロールし、マスクを示すように設定し、完了したら [新しい追加] **をクリック** します。
    
    |**パラメーター**|**推奨される設定値**|
    |:-----|:-----|
    |ルート パターン  <br/> |7779999  <br/> |
    |ルート パーティション  <br/> |SfBVideoInterop_RoutePartition  <br/> |
    |説明  <br/> |SfBVideoInterop のパーティション  <br/> |
    |ゲートウェイ/ルート一覧  <br/> |SfBVideoInterop_SIPTrunk  <br/> |
    |呼び出されたパーティ変換マスク  <br/> |+14257779999  <br/> |
   
23. [Cisco Unified CM Administration- \> Call Routing- \> SIP ルート パターン] に移動します。
    
24. [SIP ルート パターン構成] 画面で、図のように [パターン定義] オプションを設定し、[新規追加] を **クリックします**。
    
    |**パラメーター**|**推奨される設定値**|
    |:-----|:-----|
    | パターンの使用法 <br/> |ドメイン ルーティング  <br/> |
    |IPv4 パターン  <br/> |contoso.com (IPv6 を使用する場合は空白のままにする)  <br/> |
    |IPv6 パターン  <br/> |contoso.com (IPv4 を使用する場合は空白のままにする)  <br/> |
    |説明  <br/> |SIPRoute パターンから mediarv へ  <br/> |
    |ルート パーティション  <br/> |SfBVideoInterop_RoutePartition  <br/> |
    |SIP トランク/ルート リスト  <br/> |SfBVideoInterop_SIPTrunk  <br/> |
    |[ブロック パターン] チェック ボックス  <br/> |未チェックのままにする  <br/> |
   
25. オーディオまたはビデオ のビット レートを既定の設定から変更した場合は、既定値に戻す必要があります。 音声/ビデオ通話のビット レートを設定するには、[Cisco Unified CM Administration- \> System- \> Region Information- Region] に移動 \> します。 既定値は、参照用に以下に示されています。
    
    |**パラメーター**|**推奨される設定値**|
    |:-----|:-----|
    |地域  <br/> |既定値  <br/> |
    |オーディオ コーデックの基本設定リスト  <br/> |System Default  <br/> |
    |最大オーディオ ビット レート  <br/> |64 kbps (G.722、G.711)  <br/> |
    |ビデオ通話の最大セッション ビット レート  <br/> |200000 kbps  <br/> |
    |最大セッション ビット レート  <br/> |2000000000 kbps  <br/> |
   
この時点で、CUCM ビデオ ゲートウェイは VIS を使用するように構成されています。 対応する構成は、統合する各 VTC で行う必要があります。
> [!NOTE]
> 復元性を向上させるために、この CUCM ゲートウェイを 2 つ目のビデオ相互運用サーバーまたは VIS プールで動作させる構成が必要な場合があります。 詳細 [については、「復元メカニズム](../../plan-your-deployment/video-interop-server.md#resiliency) 」を参照してください。
  
## <a name="see-also"></a>関連項目

[VTC for Interoperation for Interoperation with Skype for Business Server](configure-a-vtc-for-interoperation.md)
