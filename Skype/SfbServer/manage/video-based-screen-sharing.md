---
title: Skype for Business Server のビデオベースの画面共有
ms.reviewer: ''
ms.author: v-cichur
author: cichur
ms.date: 2/20/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 50755399-2228-4324-81db-c2bfc824c299
description: ビデオ ベースの画面共有 (VbSS) の Skype for Business Server の計画と構成情報
ms.openlocfilehash: 9d2466a314876a4ce576727c7673474003994365
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103063"
---
# <a name="video-based-screen-sharing-for-skype-for-business-server"></a>Skype for Business Server のビデオベースの画面共有 
 
Skype For Business Server 2015 のビデオ ベースの画面共有 (VbSS) がダウンロード可能になります [。Skype for Business Server 2015 累積的な更新プログラム KB3061064](https://www.microsoft.com/download/details.aspx?id=47690)です。 VbSS は Skype for Business Server 2019 に含まれています。
  
ビデオ ベースのスクリーン共有 (VbSS) は、Lync の画面共有から成長しました。 VbSS と従来の画面共有の違いは、使用される基になるプロトコルと、そのプロトコルの優良な機能と関係があります。 画面共有はリモート デスクトップ プロトコル (RDP) を使用します。これは、ユーザーのコンピューター間で何千もの 1 対 1 セッションを作成する場合に最適です。 新しいテクノロジ VbSS は、ユーザー データグラム プロトコル (UDP) を利用します。
  
Skype for Business Server は、ユーザーの 1 対 1、および 1 対多 (マルチパーティ) の会話と会議のエクスペリエンスを改善したいと考えています。 VbSS では、メディア プラットフォーム (UDP を基になるプロトコルに依存) を利用し、ビデオの開始時間、視聴している視聴の品質 (特に、視聴中の動きが速い場合)、および全体的な信頼性を向上させる目的で使用されます。
  
画面共有を改善する目的の一部は、VbSS と RDP の間の移行が可能な限りシームレスに行われる点です。 VbSS は、Skype for Business Server の画面共有で使用される基になるテクノロジの更新プログラムです。 たとえば、職場に多くのレガシ クライアントがある場合、RDP は会議や会話のフェールセーフとして利用できます。 Skype for Business Server では、内部ロジックを使用して、クライアントの接続時に適用する 2 つのメソッド (VbSS または従来の画面共有) を決定します。 状況で VbSS が呼び出された場合、RDP は VbSS に置き換わる可能性があります。また、表示エクスペリエンスが中断される可能性があります。
  
## <a name="planning"></a>計画

### <a name="vbss-pros-and-cons"></a>VbSS の長所と短所

VbSS への切り替えは、次の 3 つの重要な改善を目的とします。
  
1. 画面共有を行う (最大 5%)RDP に比べて信頼性が高い。

2. セッションのセットアップとビデオ エクスペリエンスを RDP 単独と比較して高速化します (半分の時間でセットアップし、1 秒あたりのフレーム数が 6:1 向上しました)。

3. 3-D グラフィックスなどの高モーション コンテンツを共有する場合でも、低帯域幅の状況では RDP よりもはるかに優れた機能を実現します。
    
これらの数値は、ネットワークの正常性と適切なパフォーマンス調整に依存し、クライアントがモバイル デバイス上にある場合は、独自の外部ネットワークに関係する場合があります。
  
また、共有コンテンツのいくつかの忠実度/鮮明さは、信頼性、速度、および効率のために取引されている点にも注意してください。 ほとんどの場合、これはユーザーに容易に表示されません。
  
### <a name="ports-and-protocols"></a>ポートとプロトコル

**必要なサーバー ポート**

|**サーバーの役割**|**サービス名**|**ポートまたはポートの範囲**|**プロトコル**|**注**|
|:-----|:-----|:-----|:-----|:-----|
|フロント エンド サーバー  <br/> |Skype for Business Server アプリケーション共有サービス  <br/> |5065  <br/> |TCP  <br/> |アプリケーション共有の SIP リッスン要求を受信するために使用。  <br/> |
|フロント エンド サーバー  <br/> |Skype for Business Server アプリケーション共有サービス  <br/> |49152-65535  <br/> |TCP/UDP  <br/> |アプリケーション共有で使用するメディア ポート範囲。  <br/> |
   
**必要なクライアント ポート**

|**コンポーネント**|**ポート範囲**|**プロトコル**|**注**|
|:-----|:-----|:-----|:-----|
|クライアント  <br/> |1024-65535  <br/> |TCP/UDP  <br/> |アプリケーション共有。  <br/> |
   
次のメディア ポートで QoS が有効で VbSS も有効になっている場合、デスクトップ共有を含む会議中に、AS MCU は画面共有トラフィックに次の太字で示すビデオ ポート設定を使用します。 
  
> [!IMPORTANT]
> これらの設定は特別なケースであり、これらの両方の機能を実装する場合は、これらの正確な設定を使用する必要があります。 これにより、QoS に関するドキュメントの他の [推奨設定が上書きされます](/previous-versions/office/lync-server-2013/lync-server-2013-managing-quality-of-service-qos)。 アプリケーション共有では、これらのポート値の定義に加ASMCUSVC.exe QoS GPO でアプリケーションを指定する必要があります。 
  
**Application Server QoS/VbSS 必須設定**

|**プロパティ**|**ポート値**|**プロトコル**|
|:-----|:-----|:-----|
|AudioPortStart  <br/> |49152  <br/> |UDP  <br/> |
|AudioPortCount  <br/> |8348  <br/> |UDP  <br/> |
|**VideoPortStart** <br/> |**57501** <br/> |UDP  <br/> |
|**VideoPortCount** <br/> |**8034** <br/> |UDP  <br/> |
|AppSharingPortStart  <br/> |40803  <br/> |TCP  <br/> |
|AppSharingPortCount  <br/> |8348  <br/> |TCP  <br/> |
   
### <a name="capacity-planning"></a>キャパシティ プランニング

Skype for Business Server 2015 累積更新プログラム 2 (CU2) 以降を実行している各フロント エンド サーバーは、RDP を使用した画面共有に最大 375 人の参加者をサポートします (会議ごとに 250 人のみ)。 VbSS が導入され使用される場合、この容量は CU3 の後に変更されません。
  
つまり、ラボでパフォーマンスとストレステストを行いましたが、次の測定値は、(もちろん使用状況に応じて) 独自の展開に関して考慮する必要があります。
  
次の場合と仮定します。
  
- 展開で Skype for Business Server 2015 CU2 以降を使用しています。
    
- Skype for Business Server 環境のすべてのユーザーの画面解像度は 1920x1080 より高くなります。
    
フル容量 (上記のように、フロント エンド サーバーあたり合計で 375 の画面共有参加者ですが、会議ごとに 250 人のみ) では、フロントエンド サーバーが 1 ギガビット のネットワーク カードの約 89% を利用している可能性があります。 これは、Skype for Business Server CU2 (RDP) の既存の画面共有テクノロジが、発表者の PC のネイティブ解像度で画面コンテンツを送信する理由です。 そのため、画面解像度が高いほど、Skype for Business Server 2015 CU2 との画面共有のネットワークボトルネックが既に発生している可能性があります。
  
これを軽減するには、次の 1 つ以上のオプションが役立つ場合があります。
  
- フロント エンド サーバーを 1 ギガビット ネットワーク カードから 10 ギガビット イーサネット カードにアップグレードします。

- トラフィックの負荷分散を行うフロントエンド サーバーの数を増やします。

- VbSS と RDP で使用される帯域幅 (ビットレート) を制限するには、いずれかのチャネルで使用される最大帯域幅に上限を設定します。
    
この表の数値は、個々のネットワークと共有されるコンテンツの影響を受ける。 ネットワークまたはネットワークのベースラインを確立するためにテストしてください。
  
|**1080p コンテンツ**|**RDP の平均**|**RDP ピーク**|**VbSS の平均**|**VbSS Peak**|
|:-----|:-----|:-----|:-----|:-----|
|PPT  <br/> |200kbps  <br/> |12 mbps  <br/> |100kbps  <br/> |3mbps  <br/> |
|CAD  <br/> |3mbps  <br/> |7mbps  <br/> |1mbps  <br/> |3mbps  <br/> |
|ビデオ  <br/> |5 mbps  <br/> |7mbps  <br/> |1.3mbps  <br/> |2.2mbps  <br/> |
   
### <a name="network-bandwidth-requirements-for-media-traffic"></a>メディア トラフィックのネットワーク帯域幅要件

VbSS 帯域幅は次の値です。
  
|**ビデオ コーデック**|**解像度と縦横比**|**最大ビデオ ペイロード ビット レート (Kbps)**|**最小ビデオ ペイロード ビット レート (Kbps)**|
|:-----|:-----|:-----|:-----|
|H.264  <br/> |1920x1080 (16:9)  <br/> (縦横比は、共有者のモニター解像度によって異なりますが、必ずしも 16:9 とは限りではありません)  <br/> |4000  <br/> |1500  <br/> |
   
## <a name="clients-and-servers-support"></a>クライアントとサーバーのサポート

ビデオ ベースの画面共有には、Skype for Business Server 2015 CU3 以降、および Skype [for Business](../plan-your-deployment/clients-and-devices/mobile-feature-comparison.md)および Meetings サポート[](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md#BKMK_Conferencing)のモバイル クライアント機能比較に記載されているサポート クライアントの現在のバージョンが必要です。 
  
画面共有が RDP に移行する状況は次のとおりです。
  
- アカウントが、ASMCU が VbSS をサポートする最小ビルドを満たしない環境でホストされている場合。
- 以前のバージョンの Skype for Business クライアントを使用しているユーザーがセッションに参加する場合 (たとえば、16.0.6330.1000 未満の Windows クライアント バージョンを使用しているユーザー、Skype for Business Room System Devices、Skype for Business Mobile Apps など)。 
- ユーザーが Skype for Business Web App から共有している場合。
- Mac で Skype for Business を使用しているユーザーが、Skype for Business Online または Skype for Business Server 2015 に 2018 年 7 月の累積的な更新プログラム (以降) が含まれている場合。
- 他のユーザーがプログラム/Windows 共有を開始した場合。
- ユーザーがセッションの記録を開始した場合。
- セッション中にリモート スクリーン コントロールを呼び出した場合。 
- 250 人を超える参加者との会議 (VbSS は現在サポートされていません)。

セッションが RDP に移行すると、VbSS に戻らなく点に注意してください。 繰り返しますが、VbSS からの移行はシームレスであり、希望を持ってほとんどの状況で簡単に検出できません。
    
> [!NOTE]
> Skype for Business の画面共有で VbSS から RDP への移行をブロックまたはブロックしようとはサポートされていません。 
  
## <a name="enabling-disabling-and-configuring-vbss"></a>VbSS の有効化、無効化、および構成

素晴らしい点は、Skype for Business Server 2015 累積的な更新プログラム 3 (CU3) 以降をインストールすると、すべてのユーザーが既定で 1 対 1 およびマルチパーティ VbSS に対して有効になります。 すべてのユーザーに対してこの機能を有効にしない理由がある場合、これは問題になる可能性があります。 その場合は、次の手順を使用してユーザーを無効にできます (ユーザーを有効にする手順は次のとおりです)。
  
### <a name="how-to-disable-users-from-using-vbss"></a>VbSS を使用してユーザーを無効にする方法

- Skype for Business 管理コンソールでこのコマンドレットを実行することで、VbSS を使用しないユーザーに VbSS を許可しないユーザー ポリシーを割り当てできます ([PolicyName] を、これを実行しているポリシーに置き換えてください)。
    
  ```PowerShell
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode RDP
  ```

- また、グローバル会議ポリシーを更新して、割り当てられたポリシーのないすべてのユーザーに影響を与える可能性があります。
    
  ```PowerShell
  Set-CsConferencingPolicy -ApplicationSharingMode RDP
  ```

    このコマンドの詳細については [、「Set-CsConferencingPolicy」を参照してください](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)。
    
- VbSS を完全にオフにする必要がある場合は、次のコマンドを実行できます。
    
  ```PowerShell
  Set-CsMediaConfiguration -EnableVideoBasedSharing $false
  ```

    このコマンドの詳細については [、「Set-CsMediaConfiguration」を参照してください](/powershell/module/skype/set-csmediaconfiguration?view=skype-ps)。
    
> [!NOTE]
> 複数パーティの Skype for Business 会議では、すべてのクライアント エンドポイントが会議開催者のポリシー設定を尊重します。 
  
### <a name="how-to-enable-users-to-use-vbss"></a>ユーザーが VbSS を使用する方法

- Skype for Business 管理コンソールでこのコマンドレットを実行することで、VbSS を使用する必要があるすべてのユーザーに VbSS を許可する特定のユーザー ポリシーを割り当てできます ([PolicyName] をこれを実行しているポリシーに置き換えてください)。
    
  ```PowerShell
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode VideoWithFallback
  ```

- また、グローバル会議ポリシーを更新して、割り当てられたポリシーのないすべてのユーザーに影響を与える可能性があります。
    
  ```PowerShell
  Set-CsConferencingPolicy -ApplicationSharingMode VideoWithFallback
  ```

    このコマンドの詳細については [、「Set-CsConferencingPolicy」を参照してください](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)。
    
- VbSS をオフにした後で (既定ではオンになっています) 必要がある場合は、次のコマンドを実行できます。
    
  ```PowerShell
  Set-CsMediaConfiguration -EnableVideoBasedSharing $true
  ```

    このコマンドの詳細については [、「Set-CsMediaConfiguration」を参照してください](/powershell/module/skype/set-csmediaconfiguration?view=skype-ps)。
    
> [!NOTE]
> 複数パーティの Skype for Business 会議では、すべてのクライアント エンドポイントが会議開催者のポリシー設定を尊重します。 
  
## <a name="see-also"></a>関連項目

[Skype for Business Server 2015 累積的な更新プログラム KB3061064](https://www.microsoft.com/download/details.aspx?id=47690)
  
[ビデオ ベースの画面共有 (VBSS) は、Skype for Business Server 2015 で利用できます。](https://support.microsoft.com/kb/3170163)