---
title: ビデオ ベースの画面共有 Skype のビジネス サーバー
ms.author: heidip
author: microsoftheidi
ms.date: 2/20/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 50755399-2228-4324-81db-c2bfc824c299
description: Skype 画面ビデオ ・ ベース (VbSS) を共有するためのビジネス サーバーの計画と構成について
ms.openlocfilehash: a658453af5f71d7bb8103411ed16c534e3004a03
ms.sourcegitcommit: aa3258aeb5aa1296c4bb251a9d258b8896457b7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/11/2018
ms.locfileid: "23935476"
---
# <a name="video-based-screen-sharing-for-skype-for-business-server"></a>ビデオ ベースの画面共有 Skype のビジネス サーバー 
 
ベースのビデオ画面の共有 (VbSS) ビジネス サーバー 2015 の Skype がダウンロードできないようになりました。[ビジネス サーバー 2015 累積的な更新プログラム KB3061064 の Skype](https://www.microsoft.com/en-us/download/details.aspx?id=47690)です。 VbSS は、Skype のビジネス サーバー 2019 で含まれています。
  
ビデオ ベースの画面を共有、または VbSS、画面の共有 Lync から生まれました。 VbSS と従来の画面共有との違いは、使用している基本プロトコルと、それぞれの長所が関係しています。 画面共有ではリモート デスクトップ プロトコル (RDP) を使用していますが、このプロトコルはコンピューター間での数千もの 1 対 1 セッションを生成する点で優れています。 一方 VbSS は新しい技術で、ユーザー データグラム プロトコル (UDP) を使用します。
  
ビジネス サーバーの人の 1 対 1、および 1 対多 (複数の相手) の会話の向上を必要とし、会議の経験の Skype です。 VbSS ではメディア プラットフォーム (基本プロトコルとして UDP に依存) を使用して、ビデオの開始時刻、表示の質 (特に高速移動対象)、および全体的信頼性の向上を目標としています。
  
画面共有を改善する目標には、VbSS と RDP 間での移行が生じる場合に、できるだけシームレスに行うことも含まれています。 VbSS が Skype のビジネス サーバーの共有] 画面で使用される基盤となるテクノロジーの更新のため、ある可能性があります、ネットワーク トラフィック内の SIP の詳細を見ているかを共有している場合を除きを強化するテクノロジーの内容を検出することが困難高速移動] または [3-D です。 たとえば、職場は多くのレガシ クライアントは場合、RDP は念のため、会議や会話を利用できます。 Skype ビジネス サーバーのでは、内部ロジックを使用して、(VbSS または従来の画面共有) クライアントが接続するときに適用する 2 つの方法を決定します。 必要とされる状況では、VbSS に代えて RDP を使用することができ、実際にそうすることで、表示エクスペリエンスが中断されなくなります。
  
## <a name="planning"></a>計画

### <a name="vbss-pros-and-cons"></a>VbSS の長所と短所

VbSS に切り替える目的は、次の 3 つの重要な改善を行うことにあります。
  
1. RDP だけのときよりも画面共有 (最大 5%) の信頼性を向上させる。

2. RDP だけのときよりもセッション セットアップとビデオ エクスペリエンスを速くする (セットアップ時間を半分に、フレーム/秒を 6:1 に改善)。

3. 低帯域幅条件下で 3-D グラフィックなどの高速運動コンテンツを共有する場合でも、RDP よりも動作を向上させる。
    
3 つの改善点は、ネットワークの良好で適正なパフォーマンス調整に依存することに留意してください。クライアントがモバイル デバイスを使用している場合には、外部のネットワークも関係してきます。
  
また共有コンテンツの忠実で生き生きとした再現性の一部は、信頼性、速度、および効率の犠牲になることにも留意してください。多くの場合これは、容易にユーザーの目に付くようなものではありません。
  
### <a name="ports-and-protocols"></a>ポートとプロトコル

**必要なサーバー ポート**

|**サーバーの役割**|**サービス名**|**ポートまたはポート範囲**|**プロトコル**|**メモ**|
|:-----|:-----|:-----|:-----|:-----|
|フロントエンド サーバー  <br/> |ビジネス サーバー アプリケーションの共有サービスの Skype  <br/> |5065  <br/> |TCP  <br/> |アプリケーション共有の SIP リッスン要求を受信するために使用。  <br/> |
|フロントエンド サーバー  <br/> |ビジネス サーバー アプリケーションの共有サービスの Skype  <br/> |49152-65535  <br/> |TCP/UDP  <br/> |アプリケーション共有で使用するメディア ポート範囲。  <br/> |
   
**必要なクライアント ポート**

|**コンポーネント**|**ポートの範囲**|**プロトコル**|**メモ**|
|:-----|:-----|:-----|:-----|
|クライアント  <br/> |1024-65535  <br/> |TCP/UDP  <br/> |アプリケーション共有。  <br/> |
   
次のメディア ポート QoS が有効になっているし、VbSS が有効になりますと MCU に示すようにビデオのポートの設定を使用して、デスクトップの共有を含む会議中に太字の下の共有のトラフィックを選別します。 
  
> [!IMPORTANT]
> これらの設定は、特殊なケース、およびこれらの機能の両方を実装する場合、これらの正確な設定を使用する必要があります。 これには、 [QoS のマニュアル](https://technet.microsoft.com/en-us/library/gg405409%28v=ocs.15%29.aspx)で推奨されるその他の設定がオーバーライドされます。 /Fo オプション アプリケーションを共有するこれらのポートの値を定義するだけでなく、QoS の GPO で ASMCUSVC.exe を指定する必要があります。 
  
**サーバーの QoS と VbSS のアプリケーションに必要な設定**

|**プロパティ**|**ポート値**|**プロトコル**|
|:-----|:-----|:-----|
|AudioPortStart  <br/> |49152  <br/> |UDP  <br/> |
|AudioPortCount  <br/> |8348  <br/> |UDP  <br/> |
|**VideoPortStart** <br/> |**57501** <br/> |UDP  <br/> |
|**VideoPortCount** <br/> |**8034** <br/> |UDP  <br/> |
|AppSharingPortStart  <br/> |40803  <br/> |UDP  <br/> |
|AppSharingPortCount  <br/> |8348  <br/> |UDP  <br/> |
   
### <a name="capacity-planning"></a>処理能力の計画

Skype ビジネス サーバー 2015 累積的な更新プログラム 2 (CU2) またはそれ以降を実行する各フロント エンド サーバーでは、RDP (会議ごとだけが 250) を使用して共有画面の最大 375 の参加者をサポートしています。 この数は、VbSS が導入された後も、ポスト CU-3 で変わりません。
  
それはそれとして、当社ラボではパフォーマンスおよびストレス試験が行われ、展開に関して次の測定内容も考慮される予定です (当然ながら用途による)。
  
前提事項:
  
- サーバー 2015 CU2 のビジネスや、展開の後では、Skype を使用しています。
    
- ビジネス サーバー環境に、Skype のすべてのユーザーには、画面の解像度が 1920 x 1080 よりも高いがあります。
    
完全に (上記で説明したようにフロント エンド サーバーごとの 375 の画面共有参加者にある会議ごとの合計のみが 250)、ネットワーク カードの 1 ギガビットの ~ 89%、フロント エンド サーバーを利用する場合があります。 ビジネス サーバー CU2 (RDP) 用の Skype の技術を共有する既存の画面が発表者の PC のネイティブ解像度で画面に表示されるコンテンツに転送するためです。 これより高い画面解像度考慮すると発生する可能性既に Skype ビジネス サーバー 2015 CU2 の共有] 画面で、ネットワークのボトルネック。
  
これを緩和するには、次のオプションを 1 つまたは複数採用すると効果的です。
  
- 10 ギガビットのイーサネット カードに、1 ギガビット ネットワーク カードから、フロント エンド サーバーをアップグレードします。

- トラフィックを負荷分散するフロント エンド サーバーの数を増やします。

- VbSS と RDP の両チャンネルで使用する最大帯域幅に上限を設け、それぞれの帯域幅 (ビットレート) を制限する。
    
この表の数字は、個々のネットワークや共有されるコンテンツに影響されます。テストして、使用するネットワークのベースラインを確立してください。
  
|**1080p コンテンツ **|**RDP の平均値**|**RDP のピーク**|**VbSS の平均**|**VbSS のピーク**|
|:-----|:-----|:-----|:-----|:-----|
|PPT  <br/> |200 kbps  <br/> |12mbps  <br/> |100 kbps  <br/> |3mbps  <br/> |
|CAD  <br/> |3mbps  <br/> |7mbps  <br/> |1mbps  <br/> |3mbps  <br/> |
|ビデオ  <br/> |5mbps  <br/> |7mbps  <br/> |1.3mbps  <br/> |2.2mbps  <br/> |
   
### <a name="network-bandwidth-requirements-for-media-traffic"></a>メディア トラフィックのネットワーク帯域幅の要件

VbSS の帯域幅:
  
|**ビデオ コーデック**|**解像度と縦横比**|**最大ビデオ ペイロード ビット レート (Kbps)**|**最小ビデオ ペイロード ビット レート (Kbps)**|
|:-----|:-----|:-----|:-----|
|H.264  <br/> |1920x1080 (16:9)  <br/> (縦横比は共有者のモニター解像度に応じて異なり、必ずしも 16:9 ではない。)  <br/> |4000  <br/> |1500  <br/> |
   
## <a name="clients-and-servers-support"></a>クライアントおよびサーバーのサポート

ベースのビデオ画面の共有には、Skype ビジネス サーバー 2015 CU3 またはそれ以降、および[ビジネスの Skype のモバイル クライアントの機能の比較](../plan-your-deployment/clients-and-devices/mobile-feature-comparison.md)と[会議のサポート](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md#BKMK_Conferencing)に記載されているサポートのクライアントの現在のバージョンが必要です。 
  
画面共有に移行 RDP では、上記のような状況があります。
  
- ASMCU が VbSS をサポートできる最低限のビルドに満たない環境でアカウントがホストされている。
- ビジネス クライアントで、Skype の古いバージョンを使用している他のユーザーのセッションに参加する場合などのすべてのユーザーを使用して 16.0.6330.1000、ビジネス ルーム システム デバイスでは、Skype または Skype のビジネス ・ モバイル ・ アプリケーションよりも下位にある任意の Windows クライアント バージョンです。 
- 場合は、Skype からは、ビジネスの Web アプリケーションのユーザーを共有しています。
- Mac でのビジネスの Skype を使用している他のユーザーが置かれて Skype のオンライン ビジネスの場合です。
- 場合は他のユーザーは、任意のプログラムまたは Windows の共有を開始します。
- 場合は他のユーザーは、セッションの記録を開始します。
- セッション中に誰かがリモート画面コントロールを起動した場合。

    セッションが RDP に移行すると、VbSS には戻らないことに留意してください。VbSS からの移行はシームレスに行われるようになっているため、多くの場合気づきません。
  
- 250 人を超える参加者による会議 (VbSS がサポートされていない場合)。
    
> [!NOTE]
> ブロックをサポートしていないか、ビジネスの画面共有するため、VbSS から Skype での RDP への移行をブロックしようとしています。 
  
## <a name="enabling-disabling-and-configuring-vbss"></a>VbSS の有効化、無効化、および構成

最も優れている点は、ビジネス サーバー 2015 累積的な更新プログラム 3 (CU3) は、Skype をインストールしたか、後で、すべてのユーザーを有効化する 1 対 1 および複数相手の VbSS 既定です。 そのためこの機能を有効にしたくないユーザーがいる場合には問題となります。 その場合、次の手順に従って、ユーザーを無効化します (その後で有効化します)。
  
### <a name="how-to-disable-users-from-using-vbss"></a>ユーザーが VbSS を使用できないようにする方法

- VbSS をビジネスの管理コンソール (こうためのポリシーを使用して置換 [グループ]) の Skype でこのコマンドレットを実行することによって VbSS を使用するべきではないすべてのユーザーに使用できないユーザーのポリシーを割り当てることができます。
    
  ```
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode RDP
  ```

- またグローバル会議ポリシーを更新することもでき、そうすれば割り当てられたポリシーのないすべてのユーザーに影響が及びます。
    
  ```
  Set-CsConferencingPolicy -ApplicationSharingMode RDP
  ```

    このコマンドの詳細については、[セット CsConferencingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)を参照してください。
    
- VbSS を完全にオフにしたい場合は、このコマンドを実行します。
    
  ```
  Set-CsMediaConfiguration -EnableVideoBasedSharing $false
  ```

    このコマンドの詳細については、[一連の CsMediaConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/set-csmediaconfiguration?view=skype-ps)を参照してください。
    
> [!NOTE]
> ビジネス会議のための複数の Skype ですべてのクライアント エンドポイントは、会議の開催者のポリシーの設定を尊重します。 
  
### <a name="how-to-enable-users-to-use-vbss"></a>ユーザーが VbSS を使用できるようにする方法

- VbSS をビジネスの管理コンソール (こうためのポリシーを使用して置換 [グループ]) の Skype でこのコマンドレットを実行することによって VbSS を使用する必要があるすべてのユーザーに許可する特定のユーザー ポリシーを割り当てることができます。
    
  ```
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode VideoWithFallback
  ```

- またグローバル会議ポリシーを更新することもでき、そうすれば割り当てられたポリシーのないすべてのユーザーに影響が及びます。
    
  ```
  Set-CsConferencingPolicy -ApplicationSharingMode VideoWithFallback
  ```

    このコマンドの詳細については、[セット CsConferencingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)を参照してください。
    
- VbSS をオフにした後でオンに戻したい場合は、このコマンドを実行します。
    
  ```
  Set-CsMediaConfiguration -EnableVideoBasedSharing $true
  ```

    このコマンドの詳細については、[一連の CsMediaConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/set-csmediaconfiguration?view=skype-ps)を参照してください。
    
> [!NOTE]
> ビジネス会議のための複数相手の Skype ですべてのクライアント エンドポイントは、会議の開催者のポリシーの設定を尊重します。 
  
## <a name="see-also"></a>関連項目

[Skype ビジネス サーバー 2015年の累積的な更新プログラム KB3061064 の](https://www.microsoft.com/en-us/download/details.aspx?id=47690)
  
[ビジネス サーバー 2015 の Skype では、ベースのビデオ画面の共有 (VBSS)](https://support.microsoft.com/en-us/kb/3170163)
