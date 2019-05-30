---
title: Skype for Business Server のビデオベースの画面共有
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 2/20/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 50755399-2228-4324-81db-c2bfc824c299
description: Skype for Business Server の計画およびビデオベースの画面共有の構成情報 (VbSS)
ms.openlocfilehash: ae2cc683148fdb2a2cb80e3fe3cf25a698a56c00
ms.sourcegitcommit: b5949233f8080a6cf0edb4b5e27272214feb1c22
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "34548996"
---
# <a name="video-based-screen-sharing-for-skype-for-business-server"></a>Skype for Business Server のビデオベースの画面共有 
 
Skype for Business Server 2015 でビデオベースの画面共有 (VbSS) をダウンロードできるようになりました。 [skype for Business server 2015 累積更新 KB3061064](https://www.microsoft.com/en-us/download/details.aspx?id=47690)。 VbSS は、Skype for Business Server 2019 に含まれています。
  
ビデオベースの画面共有または VbSS は、Lync 画面共有を拡大しています。 VbSS と従来の画面共有との違いは、使用している基本プロトコルと、それぞれの長所が関係しています。 画面共有ではリモート デスクトップ プロトコル (RDP) を使用していますが、このプロトコルはコンピューター間での数千もの 1 対 1 セッションを生成する点で優れています。 一方 VbSS は新しい技術で、ユーザー データグラム プロトコル (UDP) を使用します。
  
Skype for Business Server では、ユーザーの1対1、および1対多 (マルチパーティ) の会話と会議のエクスペリエンスを向上させる必要がありました。 VbSS ではメディア プラットフォーム (基本プロトコルとして UDP に依存) を使用して、ビデオの開始時刻、表示の質 (特に高速移動対象)、および全体的信頼性の向上を目標としています。
  
画面共有を改善する目標には、VbSS と RDP 間での移行が生じる場合に、できるだけシームレスに行うことも含まれています。 VbSS は、Skype for Business Server の画面共有に使用されている基盤技術の更新プログラムであるため、ネットワークトラフィックの SIP の詳細を表示しているか、共有しているコンテンツを共有している場合を除き、どのテクノロジを利用しているかを検出することは困難な場合があります。は、高速移動でも3-d もできます。 たとえば、職場に多くのレガシクライアントがある場合、RDP は、会議や会話へのフェイルセーフとして提供されたままになります。 Skype for Business Server は内部ロジックを使って、クライアントが接続するときに適用する2つの方法 (VbSS または従来の画面共有) を決定します。 必要とされる状況では、VbSS に代えて RDP を使用することができ、実際にそうすることで、表示エクスペリエンスが中断されなくなります。
  
## <a name="planning"></a>計画

### <a name="vbss-pros-and-cons"></a>VbSS の長所と短所

VbSS に切り替える目的は、次の 3 つの重要な改善を行うことにあります。
  
1. RDP だけのときよりも画面共有 (最大 5%) の信頼性を向上させる。

2. RDP だけのときよりもセッション セットアップとビデオ エクスペリエンスを速くする (セットアップ時間を半分に、フレーム/秒を 6:1 に改善)。

3. 低帯域幅条件下で 3-D グラフィックなどの高速運動コンテンツを共有する場合でも、RDP よりも動作を向上させる。
    
3 つの改善点は、ネットワークの良好で適正なパフォーマンス調整に依存することに留意してください。クライアントがモバイル デバイスを使用している場合には、外部のネットワークも関係してきます。
  
また共有コンテンツの忠実で生き生きとした再現性の一部は、信頼性、速度、および効率の犠牲になることにも留意してください。多くの場合これは、容易にユーザーの目に付くようなものではありません。
  
### <a name="ports-and-protocols"></a>ポートとプロトコル

**必要なサーバーポート**

|**サーバーの役割**|**サービス名**|**ポートまたはポート範囲**|**プロトコル**|**メモ**|
|:-----|:-----|:-----|:-----|:-----|
|フロントエンド サーバー  <br/> |Skype for Business Server アプリケーション共有サービス  <br/> |5065  <br/> |TCP  <br/> |アプリケーション共有の SIP リッスン要求を受信するために使用。  <br/> |
|フロントエンド サーバー  <br/> |Skype for Business Server アプリケーション共有サービス  <br/> |49152-65535  <br/> |TCP/UDP  <br/> |アプリケーション共有で使用するメディア ポート範囲。  <br/> |
   
**必要なクライアントポート**

|**コンポーネント**|**ポートの範囲**|**プロトコル**|**メモ**|
|:-----|:-----|:-----|:-----|
|クライアント  <br/> |1024-65535  <br/> |TCP/UDP  <br/> |アプリケーション共有。  <br/> |
   
次のメディアポートと VbSS の QoS が有効になっている場合は、デスクトップ共有を含む会議中に、画面共有トラフィックについて太字で示されているビデオポート設定が使用されます。 
  
> [!IMPORTANT]
> これらの設定は特殊なケースであり、これらの機能を両方とも実装する場合は、これらの厳密な設定を使用する必要があります。 これは、 [QoS のドキュメント](https://technet.microsoft.com/en-us/library/gg405409%28v=ocs.15%29.aspx)で他の推奨設定よりも優先されます。 アプリケーション共有の場合は、これらのポート値を定義するだけでなく、QoS GPO に ASMCUSVC を指定する必要もあります。 
  
**Application Server の QoS/VbSS required 設定**

|**プロパティ**|**ポートの値**|**プロトコル**|
|:-----|:-----|:-----|
|AudioPortStart  <br/> |49152  <br/> |UDP  <br/> |
|AudioPortCount  <br/> |8348  <br/> |UDP  <br/> |
|**VideoPortStart** <br/> |**57501** <br/> |UDP  <br/> |
|**VideoPortCount** <br/> |**8034** <br/> |UDP  <br/> |
|AppSharingPortStart  <br/> |40803  <br/> |TCP  <br/> |
|AppSharingPortCount  <br/> |8348  <br/> |TCP  <br/> |
   
### <a name="capacity-planning"></a>処理能力の計画

Skype for Business Server 2015 累積更新プログラム 2 (CU2) 以降を実行している各フロントエンドサーバーでは、RDP を使用して画面共有を行うための最大375の参加者がサポートされます (ただし、会議あたりの250のみ)。 この数は、VbSS が導入された後も、ポスト CU-3 で変わりません。
  
それはそれとして、当社ラボではパフォーマンスおよびストレス試験が行われ、展開に関して次の測定内容も考慮される予定です (当然ながら用途による)。
  
前提事項:
  
- 展開で Skype for Business Server 2015 CU2 以降を使用している。
    
- Skype for Business Server 環境内のすべてのユーザーには、1920 x 1080 よりも高い画面解像度が設定されています。
    
(上で説明したように) フルキャパシティでは、フロントエンドサーバーあたりの375画面共有の参加者は250合計でで、1 gb のネットワークカードの 89% を利用している可能性があります。 これは、Skype for Business Server CU2 (RDP) の既存のスクリーン共有テクノロジによって、画面上のコンテンツが発表者の PC のネイティブ解像度で伝送されるためです。 そのため、画面の解像度を高く考慮すると、Skype for Business Server 2015 CU2 での画面共有のネットワークボトルネックが既に発生している可能性があります。
  
これを緩和するには、次のオプションを 1 つまたは複数採用すると効果的です。
  
- フロントエンドサーバーを1ギガビットネットワークカードから10ギガビットイーサネットカードにアップグレードします。

- 負荷分散トラフィックのフロントエンドサーバーの数を増やします。

- VbSS と RDP の両チャンネルで使用する最大帯域幅に上限を設け、それぞれの帯域幅 (ビットレート) を制限する。
    
この表の数字は、個々のネットワークや共有されるコンテンツに影響されます。テストして、使用するネットワークのベースラインを確立してください。
  
|**1080p コンテンツ **|**RDP の平均**|**RDP のピーク**|**VbSS の平均**|**VbSS のピーク**|
|:-----|:-----|:-----|:-----|:-----|
|PPT  <br/> |200kbps  <br/> |12mbps  <br/> |100kbps  <br/> |3mbps  <br/> |
|CAD  <br/> |3mbps  <br/> |7mbps  <br/> |1mbps  <br/> |3mbps  <br/> |
|ビデオ  <br/> |5mbps  <br/> |7mbps  <br/> |1.3mbps  <br/> |2.2mbps  <br/> |
   
### <a name="network-bandwidth-requirements-for-media-traffic"></a>メディア トラフィックのネットワーク帯域幅の要件

VbSS の帯域幅:
  
|**ビデオ コーデック**|**解像度と縦横比**|**最大ビデオ ペイロード ビット レート (Kbps)**|**最小ビデオ ペイロード ビット レート (Kbps)**|
|:-----|:-----|:-----|:-----|
|H.264  <br/> |1920x1080 (16:9)  <br/> (縦横比は共有者のモニター解像度に応じて異なり、必ずしも 16:9 ではない。)  <br/> |4000  <br/> |1500  <br/> |
   
## <a name="clients-and-servers-support"></a>クライアントおよびサーバーのサポート

ビデオベースの画面共有には、Skype for business Server 2015 CU3 以降で以降が必要です。 [skype For business と会議のサポートのモバイルクライアントの機能比較](../plan-your-deployment/clients-and-devices/mobile-feature-comparison.md)で一覧[](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md#BKMK_Conferencing)表示されているサポートクライアントの最新バージョンです。 
  
画面の共有が RDP に移行されるのは、次のような場合です。
  
- ASMCU が VbSS をサポートできる最低限のビルドに満たない環境でアカウントがホストされている。
- 以前のバージョンの Skype for Business クライアントを使用しているユーザーが、16.0.6330.1000、Skype for Business Room System デバイス、Skype for Business モバイルアプリなど、Windows クライアントバージョンを使用しているユーザーがいる場合。 
- ユーザーが Skype for Business Web App から共有している場合。
- 他のユーザーが Skype for Business for Mac を使用していて、2018年7月の累積更新プログラム (以降) で skype for Business Online または Skype for business Server 2015 を使っていない場合。
- 他のユーザーがプログラム/Windows 共有を開始した場合。
- 他のユーザーがセッションの記録を開始した場合。
- セッション中に誰かがリモート画面コントロールを起動した場合。 
- 250 人を超える参加者による会議 (VbSS がサポートされていない場合)。

セッションが RDP に移行すると、VbSS には戻らないことに留意してください。VbSS からの移行はシームレスに行われるようになっているため、多くの場合気づきません。
    
> [!NOTE]
> これは、Skype for Business の画面共有の VbSS から RDP への切り替え、またはブロックすることをサポートしていません。 
  
## <a name="enabling-disabling-and-configuring-vbss"></a>VbSS の有効化、無効化、および構成

最適な方法は、Skype for Business Server 2015 累積更新プログラム 3 (CU3 以降で) 以降をインストールすると、すべてのユーザーが既定で1対1およびマルチパーティの VbSS を使用できるようになります。 そのためこの機能を有効にしたくないユーザーがいる場合には問題となります。 その場合、次の手順に従って、ユーザーを無効化します (その後で有効化します)。
  
### <a name="how-to-disable-users-from-using-vbss"></a>ユーザーが VbSS を使用できないようにする方法

- Skype for Business 管理コンソールでこのコマンドレットを実行することにより、vbss を使用していないユーザーに対して VbSS を許可しないユーザーポリシーを割り当てることができます (これを実行しているポリシーで [PolicyName] と置き換えます)。
    
  ```
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode RDP
  ```

- またグローバル会議ポリシーを更新することもでき、そうすれば割り当てられたポリシーのないすべてのユーザーに影響が及びます。
    
  ```
  Set-CsConferencingPolicy -ApplicationSharingMode RDP
  ```

    このコマンドの詳細については、「 [Set-set-csconferencingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)」を参照してください。
    
- VbSS を完全にオフにしたい場合は、このコマンドを実行します。
    
  ```
  Set-CsMediaConfiguration -EnableVideoBasedSharing $false
  ```

    このコマンドの詳細については、「 [Set-CsMediaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmediaconfiguration?view=skype-ps)」を参照してください。
    
> [!NOTE]
> マルチパーティの Skype for Business 会議では、すべてのクライアントエンドポイントに、会議の開催者のポリシー設定が尊重されます。 
  
### <a name="how-to-enable-users-to-use-vbss"></a>ユーザーが VbSS を使用できるようにする方法

- Skype for Business 管理コンソールでこのコマンドレットを実行することにより、VbSS を使用する必要がある特定のユーザーポリシーを割り当てることができます (これを行うには、[PolicyName] をポリシーで置き換えます)。
    
  ```
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode VideoWithFallback
  ```

- またグローバル会議ポリシーを更新することもでき、そうすれば割り当てられたポリシーのないすべてのユーザーに影響が及びます。
    
  ```
  Set-CsConferencingPolicy -ApplicationSharingMode VideoWithFallback
  ```

    このコマンドの詳細については、「 [Set-set-csconferencingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)」を参照してください。
    
- VbSS をオフにした後でオンに戻したい場合は、このコマンドを実行します。
    
  ```
  Set-CsMediaConfiguration -EnableVideoBasedSharing $true
  ```

    このコマンドの詳細については、「 [Set-CsMediaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmediaconfiguration?view=skype-ps)」を参照してください。
    
> [!NOTE]
> マルチパーティの Skype for Business 会議では、すべてのクライアントエンドポイントに、会議の開催者のポリシー設定が尊重されます。 
  
## <a name="see-also"></a>関連項目

[Skype for Business Server 2015 累積更新 KB3061064](https://www.microsoft.com/en-us/download/details.aspx?id=47690)
  
[ビデオベースの画面共有 (VBSS) は、Skype for Business Server 2015 で利用できます。](https://support.microsoft.com/en-us/kb/3170163)
