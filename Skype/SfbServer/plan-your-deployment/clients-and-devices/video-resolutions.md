---
title: Skype ビジネス クライアントのビデオ解像度について
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 8f68f4c2-3194-487c-bd2f-fbe71ba8ad70
description: '概要: は、Skype ビジネス サーバーの計画中に、クライアントのビデオ要件を確認します。'
ms.openlocfilehash: a17e3e269f24e74c5403c053723d544898560f34
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32207238"
---
# <a name="skype-for-business-client-video-resolutions"></a>Skype ビジネス クライアントのビデオ解像度について
 
**の概要:** Skype ビジネス サーバーの計画中に、クライアントのビデオ要件を確認します。
  
この資料では、Skype のビデオ通話のビジネス用のビデオ ハードウェアのサポートについて説明し、さまざまなコンピューター、タブレット、およびモバイル デバイスの構成に必要なビデオの品質を決定する方法について説明します。 
  
IT プロフェッショナルに役立つ情報、組織内、または使用を検討中の使用中のノート パソコンの適合性を評価する際の。 デバイス固有の情報のために[ソリューションのカタログ](https://partnersolutions.skypeforbusiness.com/solutionscatalog)を検索することもできます。
  
## <a name="windows-desktop-mac-and-tablet-video-requirements-and-capabilities"></a>Windows デスクトップ、Mac とタブレットのビデオの要件および機能

ビジネス用の Skype では、ビデオのエンコードおよびデコードの H.264 と mpeg-4 パート 10 高度なビデオ ・ コーディング標準に準拠のハードウェア アクセラレータの設定を使用します。 これにより、エンコードし、デコードの高解像度ビデオに下位の CPU クロック速度を持つコンピューターです。 ビデオ ハードウェア要件は、コンピューター構成と必要なビデオ解像度によって異なります。
  
[Windows と Mac のハードウェア要件](https://products.office.com/en-us/office-system-requirements)を参照してください。
  
### <a name="video-hardware-requirements"></a>ビデオ ハードウェア要件

|**機能**|**要件**|
|:-----|:-----|
|DirectX Video Acceleration (DXVA) を使用したハードウェア アクセラレータ H.264 デコード  <br/> |• グラフィックス カードは、DirectX 9.0 がサポートする必要があり、DXVA2_ModeH264_VLD_NoFGT デコード モードと DirectX 9 の API を公開する必要があります。  <br/> • 最新のグラフィックス カードのドライバーをインストールする必要があります。  <br/> |
|ハードウェア アクセラレータ H.264 エンコード: チップセット要件  <br/> |次の Intel ハードウェア アクセラレータ ビデオ エンコード ソリューションがサポートされます。  <br/> • 第 2、第 3 世代インテル HD グラフィックス 2000、2500、3000、4000 のチップセット (またはそれ以降) に統合されたハードウェア ビデオ エンコーダー。 Intel HD Graphics ドライバー 15.28.9.2884 または以下を含む最新ドライバーが必要です。  <br/> • ディスプレイ ドライバー 9.17.10.2884 または最新のドライバー  <br/> • ハードウェア メディア ファンデーション (HMFT) のバージョン 3.12.10.31 または最新の HMFT を変換します。  <br/> 次の AMD ハードウェア アクセラレータ ビデオ エンコード ソリューションがサポートされます。  <br/> • AMD ビデオ コーデック エンジンでは、いくつかの個別のグラフィックス カードとの統合には、AMD A シリーズの高速プロセッサの処理装置が高速化。 AMD Video Codec Engine ドライバー 9.12.0.0 またはそれ以上がインストールされている必要があります。  <br/> |
|ハードウェア アクセラレータ H.264 エンコード: カメラ要件  <br/> |USB ビデオ クラス (UVC) 仕様バージョン 1.5 に準拠する統合 H.264 ハードウェア エンコーダーを搭載した USB ビデオ カメラ。  <br/> **注:** ビジネス用の Skype では、Windows 8 と Windows 8.1 は、UVC の 1.5 のサポートが含まれています 1.5 の UVC カメラをサポートします。 Windows 7 に UVC 1.5 のサポートが含まれていないためビジネス用の Skype は、エンコーディングをサポートしないハードウェアを通常のカメラとして 1.5 の UVC カメラを扱います。 <br/> |
   
### <a name="determining-h264-video-encoding-and-decoding-capabilities"></a>H.264 ビデオ エンコードおよびデコード機能の決定

一般に、特定のコンピューター構成の最大エンコードおよびデコード機能を決定する主な要因として、次の 4 つがあります。
  
- DXVA を使用したハードウェア アクセラレータ デコードのサポート
    
- ハードウェア アクセラレータ エンコードのサポート
    
- 物理コアの数
    
- Windows エクスペリエンス インデックス (WEI)
    
Windows システム評価ツール (WinSAT) は、WEI を決定します。WinSAT ツールを実行すると、コンピューターの %windir%\Performance\WinSAT\DataStore ディレクトリに Formal.Assessment XML ドキュメントが生成されます。この XML ファイルには、エンコードおよびデコード機能を決定するために特に重要な次の 2 つのスコアが含まれます。
  
- VideoEncodeScore は、コンピューターのソフトウェア ベースのビデオ エンコード機能を示します。
    
- GraphicsScore 値は、コンピューターのハードウェア アクセラレータ エンコード機能を示します。
    
次の 3 つの表で、サポートされるハードウェア アクセラレータによる、異なる種類の PC の最大エンコードおよびデコード機能を説明します。640x360 以上の解像度では、サポートされる最大フレーム レートは 30 フレーム/秒 (fps) です。640x360 より低い解像度では、サポートされる最大フレーム レートは 15 fps です。
  
**DXVA とハードウェア アクセラレータ エンコーダーのないコンピューター**

|**可能なエンコーダー解像度**|**可能なデコーダー解像度**|**要件**|
|:-----|:-----|:-----|
|424x240  <br/> |424x240 (受信のみのシナリオでは 15fps で 640x360)  <br/> |1 コアと VideoEncodeScore ≥ 4.0  <br/> |
|640x360  <br/> |640x360  <br/> |2 コアと VideoEncodeScore ≥ 4.5  <br/> |
|640x360  <br/> |1280x720  <br/> |2 コアと VideoEncodeScore ≥ 4.5  <br/> |
|640x360  <br/> |1920x1080  <br/> |4 コアと VideoEncodeScore ≥ 4.5  <br/> |
|1280x720  <br/> |1280x720  <br/> |4 コアと VideoEncodeScore ≥ 7.3  <br/> |
|1280x720  <br/> |1920x1080  <br/> |4 コアと VideoEncodeScore ≥ 7.3  <br/> |
|1920x1080  <br/> |1920x1080  <br/> |該当なし  <br/> |
   
**DXVA があり、ハードウェア アクセラレータ エンコーダーのないコンピューター**

|**可能なエンコーダー解像度**|**可能なデコーダー解像度**|**要件**|
|:-----|:-----|:-----|
|424x240  <br/> |1920x1080  <br/> |1 コアと VideoEncodeScore ≥ 3.0  <br/> |
|640x360  <br/> |1920x1080  <br/> |2 コアと VideoEncodeScore ≥ 4.5  <br/> |
|960x540  <br/> |1920x1080  <br/> |2 コアと VideoEncodeScore ≥ 6.0  <br/> |
|1280x720  <br/> |1920x1080  <br/> |4 コアと VideoEncodeScore ≥ 6.7  <br/> |
|1920x1080  <br/> |1920x1080  <br/> |4 コアと VideoEncodeScore ≥ 8.2  <br/> |
   
> [!NOTE]
> Windows 7 での WinSAT スコアは最大 7.9 に制限されます。したがって、ハードウェア アクセラレータ エンコーダーのないコンピューターのエンコード能力は、Windows 8 または Windows 8.1 でのみ実現でき、その場合の最大 WinSAT スコアは 9.9 です。 
  
**DXVA と Intel HD グラフィック ハードウェア アクセラレータ エンコーダーがあるコンピューター**

|**可能なエンコーダー解像度**|**可能なデコーダー解像度**|**要件**|
|:-----|:-----|:-----|
|1280x720  <br/> |1920x1080  <br/> |すべての第 2 世代および第 3 世代の Intel HD Graphics  <br/> |
|1920x1080  <br/> |1920x1080  <br/> |第 2 世代および第 3 世代の Intel HD Graphics と GraphicsScore ≥ 5.0  <br/> |
   
## <a name="mobile-device-video-capabilities"></a>モバイル デバイスのビデオ機能

次の表では、サポートされているモバイル デバイスで使用可能な最大ビデオ解像度について説明します。 モバイル デバイスのサポート、[ビジネスの Skype のモバイル クライアントの機能の比較](mobile-feature-comparison.md)に関する詳細については。
  
|**機能**|**Windows Phone**|**iPhone**|**iPad**|**Android**|
|:-----|:-----|:-----|:-----|:-----|
|H.264 エンコードの最大解像度  <br/> |VGA  <br/> |QVGA: iPhone 4S  <br/> VGA: iPhone 5  <br/> 720p: iPhone 5S 以降  <br/> |VGA: iPad 2 以降/iPad mini 1 以降  <br/> 720p: iPad Air/iPad mini 2/iPad Pro 以降  <br/> |VGA デバイスのモデルによって最大  <br/> |
|H.264 デコードの最大解像度  <br/> |VGA  <br/> |QVGA: iPhone 4S  <br/> VGA: iPhone 5  <br/> 720p: iPhone 5S 以降  <br/> |VGA: iPad 2 以降/iPad mini 1 以降  <br/> 720p: iPad Air/iPad mini 2/iPad Pro 以降  <br/> |VGA デバイスのモデルによって最大  <br/> |
   

