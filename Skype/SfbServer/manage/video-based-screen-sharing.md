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
description: ビデオ ベースの画面共有 (VbSS) の Skype for Business Server の計画と構成に関する情報
ms.openlocfilehash: 6c24ad9e2f74495fc616a66472f338f1b0b281d4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832767"
---
# <a name="video-based-screen-sharing-for-skype-for-business-server"></a>Skype for Business Server のビデオベースの画面共有 
 
Skype for Business Server 2015 のビデオ ベースの画面共有 (VbSS) がダウンロード可能に: [Skype for Business Server 2015 の累積的な更新プログラム KB3061064](https://www.microsoft.com/download/details.aspx?id=47690)。 VbSS は Skype for Business Server 2019 に付属しています。
  
ビデオ ベースの画面共有 (VbSS) は、Lync の画面共有から抜け出します。 VbSS と従来の画面共有の違いは、使用される基になるプロトコルと、そのプロトコルが優っているものに関係しています。 画面共有では、リモート デスクトップ プロトコル (RDP) を使用します。これは、ユーザーのコンピューター間で数千の 1 対 1 セッションを作成する点で最適です。 新しいテクノロジである VbSS は、ユーザー データグラム プロトコル (UDP) を利用します。
  
Skype for Business Server は、ユーザーの 1 対 1、および 1 対多 (マルチパーティ) の会話と会議のエクスペリエンスを改善したいと考えています。 VbSS では、メディア プラットフォーム (基になるプロトコルとして UDP に依存) を利用し、ビデオの開始時間、視聴している情報の表示品質 (特に、視聴しているデータが速い場合)、全体的な信頼性を向上させるという目標があります。
  
画面共有を改善する目標の一部は、VbSS と RDP の間の移行は、可能な限りシームレスに行われる点です。 VbSS は、Skype for Business Server の画面共有で使用される基礎技術の更新プログラムです。ネットワーク トラフィックの SIP の詳細を見ている場合や、高速に移動するコンテンツや 3-D コンテンツを共有している場合を使用しない限り、どのテクノロジを利用しているかの検出が困難な場合があります。 たとえば、職場に多くのレガシ クライアントがある場合、RDP は会議や会話のフェールセーフとして引き続き利用できます。 Skype for Business Server は内部ロジックを使用して、クライアントが接続するときに適用する 2 つの方法 (VbSS または従来の画面共有) を決定します。 状況が VbSS を呼び出す場合、RDP は VbSS に代わるものになります。そのため、表示エクスペリエンスが中断されません。
  
## <a name="planning"></a>計画

### <a name="vbss-pros-and-cons"></a>VbSS の長所と短所

VbSS への切り替えは、次の 3 つの重要な改善を目的とします。
  
1. 画面共有を行う (最大 5%)RDP 単独よりも信頼性が高い。

2. RDP 単独と比較して、セッションのセットアップとビデオのエクスペリエンスを速くします (1 秒あたりのフレーム数が 6:1 向上し、半分の時間でセットアップされます)。

3. 3-D グラフィックスなどの高モーション コンテンツを共有する場合でも、低帯域幅の条件で RDP よりもはるかに優れた動作をします。
    
これらの数値は、ネットワークの正常性と適切なパフォーマンスのチューニングに依存し、クライアントがモバイル デバイスを使用している場合は、外部のネットワークが関係する可能性があります。
  
また、共有コンテンツの忠実性/鮮明度は、信頼性、速度、および効率性とトレードされている点にも注意する必要があります。 ほとんどの場合、これはユーザーに簡単には表示されません。
  
### <a name="ports-and-protocols"></a>ポートとプロトコル

**必要なサーバー ポート**

|**サーバーの役割**|**サービス名**|**ポートまたはポート範囲**|**プロトコル**|**注**|
|:-----|:-----|:-----|:-----|:-----|
|フロント エンド サーバー  <br/> |Skype for Business Server アプリケーション共有サービス  <br/> |5065  <br/> |TCP  <br/> |アプリケーション共有の SIP リッスン要求を受信するために使用。  <br/> |
|フロント エンド サーバー  <br/> |Skype for Business Server アプリケーション共有サービス  <br/> |49152-65535  <br/> |TCP/UDP  <br/> |アプリケーション共有で使用するメディア ポート範囲。  <br/> |
   
**必要なクライアント ポート**

|**コンポーネント**|**ポート範囲**|**プロトコル**|**注**|
|:-----|:-----|:-----|:-----|
|クライアント  <br/> |1024-65535  <br/> |TCP/UDP  <br/> |アプリケーション共有。  <br/> |
   
QoS が次のメディア ポートに対して有効で、VbSS も有効になっている場合は、AS MCU を共有するデスクトップを含む会議中に、画面共有トラフィックに次に示すビデオ ポート設定が太字で使用されます。 
  
> [!IMPORTANT]
> これらの設定は特殊なケースであり、これらの両方の機能を実装する場合は、これらの正確な設定を使用する必要があります。 これは、QoS に関するドキュメントの他の [推奨設定より優先されます](https://technet.microsoft.com/library/gg405409%28v=ocs.15%29.aspx)。 アプリケーション共有の場合は、これらのポート値を定義ASMCUSVC.exe QoS GPO でアプリケーションを指定する必要があります。 
  
**アプリケーション サーバー QoS/VbSS に必要な設定**

|**プロパティ**|**ポート値**|**プロトコル**|
|:-----|:-----|:-----|
|AudioPortStart  <br/> |49152  <br/> |UDP  <br/> |
|AudioPortCount  <br/> |8348  <br/> |UDP  <br/> |
|**VideoPortStart** <br/> |**57501** <br/> |UDP  <br/> |
|**VideoPortCount** <br/> |**8034** <br/> |UDP  <br/> |
|AppSharingPortStart  <br/> |40803  <br/> |TCP  <br/> |
|AppSharingPortCount  <br/> |8348  <br/> |TCP  <br/> |
   
### <a name="capacity-planning"></a>キャパシティ プランニング

Skype for Business Server 2015 累積更新プログラム 2 (CU2) 以降を実行している各フロントエンド サーバーは、RDP を使用した画面共有に最大 375 人の参加者をサポートします (会議ごとに 250 人のみ)。 VbSS が導入され使用される場合、この容量は CU3 後に変更されません。
  
とは言え、ラボではパフォーマンスとストレスのテストが行われ、次の測定値も (もちろん使用法に応じて) 独自の展開に関して考慮する必要があります。
  
次の条件を前提とします。
  
- 展開で Skype for Business Server 2015 CU2 以降を使用している。
    
- Skype for Business Server 環境のすべてのユーザーの画面解像度は 1920x1080 より高くなります。
    
フル容量 (上記のように、フロント エンド サーバーあたり合計 375 人の画面共有参加者ですが、会議あたり 250 人)、フロント エンド サーバーは 1 ギガビットのネットワーク カードの最大 89% を利用している可能性があります。 これは、Skype for Business Server CU2 (RDP) の既存の画面共有テクノロジが、発表者の PC のネイティブ解像度で画面コンテンツを送信する理由です。 そのため、画面解像度が高くなると、Skype for Business Server 2015 CU2 での画面共有のネットワーク ボトルネックが既に発生している可能性があります。
  
これを軽減するには、次の 1 つ以上のオプションが役立つ場合があります。
  
- フロント エンド サーバーを 1 ギガビット ネットワーク カードから 10 ギガビット イーサネット カードにアップグレードします。

- トラフィックの負荷分散を行うフロントエンド サーバーの数を増やします。

- VbSS と RDP で使用される帯域幅 (ビットレート) を制限するには、いずれかのチャネルで使用される最大帯域幅に上限を設定します。
    
この表の数値は、個々のネットワークおよび共有されるコンテンツによって影響されます。 ネットワークまたはネットワークのベースラインを確立するためにテストしてください。
  
|**1080p コンテンツ**|**RDP の平均**|**RDP ピーク**|**VbSS Average**|**VbSS ピーク**|
|:-----|:-----|:-----|:-----|:-----|
|PPT  <br/> |200 kbps  <br/> |12mbps  <br/> |100 kbps  <br/> |3mbps  <br/> |
|CAD  <br/> |3mbps  <br/> |7mbps  <br/> |1mbps  <br/> |3mbps  <br/> |
|ビデオ  <br/> |5mbps  <br/> |7mbps  <br/> |1.3mbps  <br/> |2.2mbps  <br/> |
   
### <a name="network-bandwidth-requirements-for-media-traffic"></a>メディア トラフィックのネットワーク帯域幅要件

VbSS の帯域幅は次の値です。
  
|**ビデオ コーデック**|**解像度と縦横比**|**最大ビデオ ペイロード ビット レート (Kbps)**|**最小ビデオ ペイロード ビット レート (Kbps)**|
|:-----|:-----|:-----|:-----|
|H.264  <br/> |1920x1080 (16:9)  <br/> (縦横比は共有者のモニター解像度によって異なりますが、常に 16:9 になるとは限りではありません)。  <br/> |4000  <br/> |1500  <br/> |
   
## <a name="clients-and-servers-support"></a>クライアントとサーバーのサポート

ビデオ ベースの画面共有には、Skype for Business Server 2015 CU3 以降と [、Skype for Business](../plan-your-deployment/clients-and-devices/mobile-feature-comparison.md) と会議のサポートに関するモバイル クライアント機能の比較に記載されているサポート クライアントの現在の [バージョンが必要](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md#BKMK_Conferencing)です。 
  
画面共有が RDP に移行する状況は次のとおりです。
  
- アカウントが、VBSS をサポートする最小ビルドを ASMCU が満たしない環境でホストされている場合。
- 以前のバージョンの Skype for Business クライアントを使用しているユーザーがセッションに参加する場合 (たとえば、16.0.6330.1000 より低い Windows クライアント バージョン、Skype for Business Room System Devices、Skype for Business Mobile Apps を使用しているユーザーなど)。 
- ユーザーが Skype for Business Web App から共有している場合。
- If someone is using Skype for Business on Mac and not is homed on Skype for Business Online or Skype for Business Server 2015 with the July, 2018 cumulative update (or later).
- プログラムや Windows の共有を開始した場合。
- 誰かがセッションのレコーディングを開始した場合。
- セッション中に誰かがリモート スクリーン コントロールを呼び出した場合。 
- 参加者が 250 人を超える会議 (VbSS は現在サポートされていません)。

セッションが RDP に移行すると、VbSS に戻らなく点に注意してください。 繰り返しますが、VbSS からの移行はシームレスに行う必要があります。多くの場合、それを検出するのは容易ではありません。
    
> [!NOTE]
> Skype for Business の画面共有で VbSS から RDP への移行をブロックまたはブロックしようとはサポートされていません。 
  
## <a name="enabling-disabling-and-configuring-vbss"></a>VbSS の有効化、無効化、および構成

大きな点は、Skype for Business Server 2015 の累積的な更新プログラム 3 (CU3) 以降をインストールすると、すべてのユーザーが既定で 1 対 1 およびマルチパーティ VbSS に対して有効になります。 すべてのユーザーに対してこの機能を有効にしない理由がある場合は、この問題が発生する可能性があります。 その場合、次の手順を使用してユーザーを無効にできます (ユーザーを有効にする手順に従います)。
  
### <a name="how-to-disable-users-from-using-vbss"></a>ユーザーによる VbSS の使用を無効にする方法

- Skype for Business 管理コンソールでこのコマンドレットを実行することで、VbSS を使用しないユーザーに VbSS を許可しないユーザー ポリシーを割り当てできます ([PolicyName] を、この処理を行っているポリシーに置き換えてください)。
    
  ```PowerShell
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode RDP
  ```

- また、グローバル会議ポリシーを更新して、割り当てられたポリシーを持たなくてもすべてのユーザーに影響を与える可能性があります。
    
  ```PowerShell
  Set-CsConferencingPolicy -ApplicationSharingMode RDP
  ```

    このコマンドの詳細については [、「Set-CsConferencingPolicy」を参照してください](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)。
    
- VbSS を完全にオフにする必要がある場合は、次のコマンドを実行できます。
    
  ```PowerShell
  Set-CsMediaConfiguration -EnableVideoBasedSharing $false
  ```

    このコマンドの詳細については [、「Set-CsMediaConfiguration」を参照してください](https://docs.microsoft.com/powershell/module/skype/set-csmediaconfiguration?view=skype-ps)。
    
> [!NOTE]
> マルチパーティの Skype for Business 会議では、すべてのクライアント エンドポイントが会議開催者のポリシー設定を尊重します。 
  
### <a name="how-to-enable-users-to-use-vbss"></a>ユーザーが VbSS を使用できる方法

- Skype for Business 管理コンソールでこのコマンドレットを実行することで、VbSS を使用する必要があるすべてのユーザーに VbSS を許可する特定のユーザー ポリシーを割り当てできます ([PolicyName] を、これを行うポリシーに置き換えてください)。
    
  ```PowerShell
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode VideoWithFallback
  ```

- また、グローバル会議ポリシーを更新して、割り当てられたポリシーを持たなくてもすべてのユーザーに影響を与える可能性があります。
    
  ```PowerShell
  Set-CsConferencingPolicy -ApplicationSharingMode VideoWithFallback
  ```

    このコマンドの詳細については [、「Set-CsConferencingPolicy」を参照してください](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)。
    
- オフにした後で VbSS をオンに戻す必要がある場合 (既定ではオンになっています)、次のコマンドを実行できます。
    
  ```PowerShell
  Set-CsMediaConfiguration -EnableVideoBasedSharing $true
  ```

    このコマンドの詳細については [、「Set-CsMediaConfiguration」を参照してください](https://docs.microsoft.com/powershell/module/skype/set-csmediaconfiguration?view=skype-ps)。
    
> [!NOTE]
> 複数パーティの Skype for Business 会議では、すべてのクライアント エンドポイントが会議開催者のポリシー設定を尊重します。 
  
## <a name="see-also"></a>関連項目

[Skype for Business Server 2015 の累積的な更新プログラム KB3061064](https://www.microsoft.com/download/details.aspx?id=47690)
  
[ビデオ ベースの画面共有 (VBSS) は Skype for Business Server 2015 で利用できます。](https://support.microsoft.com/kb/3170163)
