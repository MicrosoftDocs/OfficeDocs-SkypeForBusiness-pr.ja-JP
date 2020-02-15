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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 50755399-2228-4324-81db-c2bfc824c299
description: Skype for Business Server の計画およびビデオベースの画面共有の構成情報 (VbSS)
ms.openlocfilehash: d6b66da2994db892bc193103bca75e844c62197f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42009570"
---
# <a name="video-based-screen-sharing-for-skype-for-business-server"></a>Skype for Business Server のビデオベースの画面共有 
 
Skype For business Server 2015 のビデオベースの画面共有 (VbSS) をダウンロードできるようになりました: [skype For Business server 2015 の累積更新プログラム KB3061064](https://www.microsoft.com/download/details.aspx?id=47690)。 VbSS は、Skype for Business Server 2019 に含まれています。
  
ビデオベースの画面共有または VbSS が Lync 画面共有から成長しています。 VbSS と従来の画面共有の違いは、使用されている基になるプロトコルと、それらがどのようなものであるかによって決まります。 画面共有は、リモートデスクトッププロトコル (RDP) を使用します。これは、ユーザーのコンピューター間で数千の1対1セッションを作成するのに適しています。 新しいテクノロジである VbSS は、ユーザーデータグラムプロトコル (UDP) を使用します。
  
Skype for Business Server では、ユーザーの1対1、および1対多 (複数者) の会話と会議のエクスペリエンスを改善する必要がありました。 VbSS は、ビデオの開始時間を短縮することを目標として、ビデオの開始時間を短縮することを目標としたメディアプラットフォーム (特に、監視しているものが速い場合)、および全体的な信頼性を利用することになります。
  
画面共有を改善する目的の一部は、VbSS と RDP 間の移行が、発生時に可能な限りシームレスになることです。 VbSS は、Skype for Business Server の画面共有に使用される基盤テクノロジへの更新プログラムであるため、ネットワークトラフィックの SIP 詳細を確認したり、コンテンツを共有したりしていない限り、使用しているテクノロジを検出するのは困難な場合があります。は、高速移動または3-d です。 たとえば、職場に多数のレガシクライアントがある場合でも、会議や会話へのフェイルセーフとして RDP を使用できるようになります。 Skype for Business Server は内部ロジックを使用して、クライアントの接続時に適用する2つの方法 (VbSS または従来の画面共有) を決定します。 RDP は、状況に応じて VbSS に置き換えられ、表示が中断されないようにすることができます。
  
## <a name="planning"></a>計画

### <a name="vbss-pros-and-cons"></a>VbSS の長所と短所

VbSS を目的として、3つの重要な改善を行います。
  
1. 画面共有を作成する (最大5%)RDP のみに比べて信頼性が向上しています。

2. セッションのセットアップとビデオエクスペリエンスを RDP だけに比べて高速化します (時間が半分で、フレームごとに6:1 が向上します)。

3. 低帯域幅条件では、3-d グラフィックスなどの高モーションコンテンツを共有する場合でも、RDP よりもはるかに優れた機能を発揮します。
    
これらの数字は、ネットワークの正常性とパフォーマンスの調整に依存しており、クライアントがモバイルデバイス上にある場合は、自分の外部のネットワークが関係する可能性があることに注意してください。
  
また、信頼性、速度、効率のために、共有コンテンツの忠実性/犠牲が利用されていることにも注意する必要があります。 ほとんどの場合、これはユーザーにはすぐに表示されません。
  
### <a name="ports-and-protocols"></a>ポートとプロトコル

**必要なサーバーポート**

|サーバーの役割は、新しいファームを作成するとき、またはサーバーを既存のファームに参加させるときに指定します。|**サービス名**|**ポートまたはポート範囲**|**Protocol**|**メモ**|
|:-----|:-----|:-----|:-----|:-----|
|フロント エンド サーバー  <br/> |Skype for Business Server アプリケーション共有サービス  <br/> |5065  <br/> |TCP  <br/> |アプリケーション共有の SIP リッスン要求を受信するために使用。  <br/> |
|フロント エンド サーバー  <br/> |Skype for Business Server アプリケーション共有サービス  <br/> |49152-65535  <br/> |TCP/UDP  <br/> |アプリケーション共有で使用するメディア ポート範囲。  <br/> |
   
**必要なクライアントポート**

|**コンポーネント**|**ポート範囲**|**Protocol**|**メモ**|
|:-----|:-----|:-----|:-----|
|クライアント  <br/> |1024-65535  <br/> |TCP/UDP  <br/> |アプリケーション共有。  <br/> |
   
次のメディアポートで QoS が有効になっていて、VbSS も有効になっている場合、では、デスクトップ共有を含む電話会議中に、MCU としての画面共有トラフィックについて、次に太字で示されているビデオポート設定を使用します。 
  
> [!IMPORTANT]
> これらの設定は特別なケースなので、これらの機能の両方を実装する場合は、これらの設定を使用する必要があります。 これは、 [QoS のドキュメント](https://technet.microsoft.com/library/gg405409%28v=ocs.15%29.aspx)で推奨されるその他の設定よりも優先されます。 アプリケーション共有の場合は、これらのポート値を定義するだけでなく、QoS GPO で ASMCUSVC を指定する必要もあります。 
  
**アプリケーションサーバーの QoS/VbSS 必要な設定**

|**Property**|**ポート値**|**Protocol**|
|:-----|:-----|:-----|
|AudioPortStart  <br/> |49152  <br/> |受信  <br/> |
|AudioPortCount  <br/> |8348  <br/> |受信  <br/> |
|**VideoPortStart** <br/> |**57501** <br/> |受信  <br/> |
|**VideoPortCount** <br/> |**8034** <br/> |受信  <br/> |
|AppSharingPortStart  <br/> |40803  <br/> |TCP  <br/> |
|AppSharingPortCount  <br/> |8348  <br/> |TCP  <br/> |
   
### <a name="capacity-planning"></a>容量計画

Skype for Business Server 2015 の累積的な更新プログラム 2 (CU2) 以降を実行している各フロントエンドサーバーは、RDP を使用して画面を共有するために最大375の参加者をサポートします (ただし、会議ごとに250のみ)。 この容量は、VbSS が導入されて使用されると、CU3 は変更されません。
  
このラボでは、パフォーマンスとストレステストを行ってきましたが、(使用状況に応じて) 独自の展開に関して、以下の測定も考慮する必要があります。
  
場合
  
- 展開で Skype for Business Server 2015 CU2 以降を使用している。
    
- Skype for Business Server 環境内のすべてのユーザーの画面解像度は1920x1080 を超えています。
    
全容量 (上記のとおり) では、フロントエンドサーバーごとに375画面共有参加者が合計で、1ギガビットのネットワークカードの使用率は89最大で250の場合があります。 これは、Skype for Business Server CU2 (RDP) の既存のスクリーン共有テクノロジによって、画面上のコンテンツが発表者の PC のネイティブの解像度で送信されるためです。 そのため、を使用すると、より高い画面解像度が考慮されていますが、既に Skype for Business Server 2015 CU2 での画面共有のネットワークボトルネックが発生している可能性があります。
  
これを緩和するには、次のオプションのうちの1つまたは複数が役に立つことがあります。
  
- フロントエンドサーバーを1ギガビットのネットワークカードから10ギガビットのイーサネットカードにアップグレードします。

- 負荷分散トラフィックのためのフロントエンドサーバーの数を増やします。

- いずれかのチャネルで使用される最大帯域幅に cap を入れることにより、VbSS および RDP に使用される帯域幅 (ビットレート) を制限します。
    
この表の番号は、個別のネットワークおよび共有されるコンテンツによって影響を受けます。 テストして、ネットワークまたはネットワークのベースラインを確立してください。
  
|**1080p コンテンツ**|**RDP の平均**|**RDP ピーク**|**VbSS Average**|**VbSS のピーク**|
|:-----|:-----|:-----|:-----|:-----|
|PPT  <br/> |200 kbps  <br/> |12mbps  <br/> |100kbps  <br/> |3mbps  <br/> |
|CAD  <br/> |3mbps  <br/> |7mbps  <br/> |1mbps  <br/> |3mbps  <br/> |
|ビデオ  <br/> |5mbps  <br/> |7mbps  <br/> |1.3 mbps  <br/> |2.2 mbps  <br/> |
   
### <a name="network-bandwidth-requirements-for-media-traffic"></a>メディアトラフィックのネットワーク帯域幅の要件

VbSS 帯域幅は次のとおりです。
  
|**ビデオ コーデック**|**解像度と縦横比**|**最大ビデオペイロードビットレート (Kbps)**|**最小ビデオペイロードビットレート (Kbps)**|
|:-----|:-----|:-----|:-----|
|.H  <br/> |1920x1080 (16:9)  <br/> (縦横比は、共有先のモニターの解像度に依存し、必ずしも16:9 になることはありません)。  <br/> |4000  <br/> |1500  <br/> |
   
## <a name="clients-and-servers-support"></a>クライアントとサーバーのサポート

ビデオベースの画面共有には、Skype for Business Server 2015 CU3 以降が必要です。また、「Skype for Business および[会議のサポート](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md#BKMK_Conferencing)」[の「モバイルクライアント機能の比較](../plan-your-deployment/clients-and-devices/mobile-feature-comparison.md)」に記載されているサポート対象クライアントの現在のバージョンが必要です。 
  
画面共有が RDP に移行される状況としては、次のようなものがあります。
  
- ASMCU が VbSS をサポートする最小ビルドを満たさない環境でアカウントがホストされている場合。
- 以前のバージョンの Skype for Business クライアントを使用しているユーザーがセッションに参加している場合は、たとえば、16.0.6330.1000、Skype for Business Room System デバイス、または Skype for Business モバイルアプリよりも低い Windows クライアントバージョンを使用しているユーザーがいます。 
- ユーザーが Skype for Business Web App から共有している場合。
- 他のユーザーが Mac で Skype for Business を使用していて、7月、2018累積的な更新プログラム (またはそれ以降) を使用している Skype for Business Online または Skype for Business Server 2015 に所属していない場合。
- 誰かがプログラム/Windows 共有を開始した場合。
- 誰かがセッションの記録を開始した場合。
- セッション中に誰かがリモート画面コントロールを呼び出した場合。 
- 参加者が250人を超える会議 (VbSS は現時点ではサポートされていません)。

セッションが RDP に移行されると、VbSS には戻らないことに注意してください。 ここでも、VbSS からの移行はシームレスであることを意図しているため、ほとんどの状況では簡単に検出できません。
    
> [!NOTE]
> Skype for Business の画面共有では、VbSS から RDP への移行をブロックまたはブロックしようとすることはサポートされていません。 
  
## <a name="enabling-disabling-and-configuring-vbss"></a>VbSS の有効化、無効化、および構成

すばらしいことですが、Skype for Business Server 2015 の累積的な更新プログラム 3 (CU3) 以降をインストールすると、すべてのユーザーが既定で1対1およびマルチパーティの VbSS に対して有効になります。 この機能をすべてのユーザーに対して有効にしない理由がある場合は、この問題が発生する可能性があります。 その場合は、次の手順を使用してユーザーを無効にすることができます ([ユーザーを有効にする] 手順は次のようになっています)。
  
### <a name="how-to-disable-users-from-using-vbss"></a>ユーザーが VbSS を使用できないようにする方法

- Skype for Business 管理コンソールでこのコマンドレットを実行することによって、vbss を使用しないユーザーに VbSS を許可しないユーザーポリシーを割り当てることができます ([PolicyName] を、これを実行しているポリシーに置き換えます)。
    
  ```PowerShell
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode RDP
  ```

- また、グローバル会議ポリシーを更新して、ポリシーが割り当てられていないすべてのユーザーに影響を与えることもできます。
    
  ```PowerShell
  Set-CsConferencingPolicy -ApplicationSharingMode RDP
  ```

    このコマンドの詳細については、「 [get-csconferencingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)」を参照してください。
    
- VbSS を完全にオフにする必要がある場合は、次のコマンドを実行します。
    
  ```PowerShell
  Set-CsMediaConfiguration -EnableVideoBasedSharing $false
  ```

    このコマンドの詳細については、「 [get-csmediaconfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmediaconfiguration?view=skype-ps)」を参照してください。
    
> [!NOTE]
> マルチパーティの Skype for Business 会議では、すべてのクライアントエンドポイントが会議開催者のポリシー設定を尊重します。 
  
### <a name="how-to-enable-users-to-use-vbss"></a>ユーザーが VbSS を使用できるようにする方法

- Skype for Business 管理コンソールで次のコマンドレットを実行することによって、vbss を使用する必要があるユーザーに対して、VbSS を許可する特定のユーザーポリシーを割り当てることができます ([PolicyName] を、これを実行しているポリシーに置き換えます)。
    
  ```PowerShell
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode VideoWithFallback
  ```

- また、グローバル会議ポリシーを更新して、ポリシーが割り当てられていないすべてのユーザーに影響を与えることもできます。
    
  ```PowerShell
  Set-CsConferencingPolicy -ApplicationSharingMode VideoWithFallback
  ```

    このコマンドの詳細については、「 [get-csconferencingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)」を参照してください。
    
- VbSS をオフにした後で有効にする必要がある場合 (既定でオンになっている場合) は、次のコマンドを実行できます。
    
  ```PowerShell
  Set-CsMediaConfiguration -EnableVideoBasedSharing $true
  ```

    このコマンドの詳細については、「 [get-csmediaconfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmediaconfiguration?view=skype-ps)」を参照してください。
    
> [!NOTE]
> マルチパーティの Skype for Business 会議では、すべてのクライアントエンドポイントが会議開催者のポリシー設定を尊重します。 
  
## <a name="see-also"></a>関連項目

[Skype for Business Server 2015 の累積的な更新プログラムの KB3061064](https://www.microsoft.com/download/details.aspx?id=47690)
  
[ビデオベースの画面共有 (VBSS) は Skype for Business Server 2015 で利用できます。](https://support.microsoft.com/kb/3170163)
