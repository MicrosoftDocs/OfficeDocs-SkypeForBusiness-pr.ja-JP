---
title: Skype for Business クライアントのビデオ解像度
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 8f68f4c2-3194-487c-bd2f-fbe71ba8ad70
description: '概要: Skype for Business Server の計画時に、クライアントのビデオ要件を確認します。'
ms.openlocfilehash: 9be23512462781c55ef94b72b4dbbba60e15e5ba
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816057"
---
# <a name="skype-for-business-client-video-resolutions"></a>Skype for Business クライアントのビデオ解像度
 
**概要:** Skype for Business Server の計画時に、クライアントのビデオ要件を確認します。
  
この記事では、Skype for Business ビデオ通話のビデオ ハードウェア サポートについて説明し、さまざまなコンピューター、タブレット、およびモバイル デバイス構成で予想されるビデオ品質を決定する方法について説明します。 
  
IT 担当者は、この情報は、組織で既に使用されているノート PC の適合性を評価したり、使用を検討している場合に役立ちます。 また、ソリューション カタログで [特定のデバイスに](https://partnersolutions.skypeforbusiness.com/solutionscatalog) 関する情報を検索することもできます。
  
## <a name="windows-desktop-mac-and-tablet-video-requirements-and-capabilities"></a>Windows デスクトップ、Mac、タブレットのビデオの要件と機能

Skype for Business は、H.264/MPEG-4 Part 10 Advanced Video Coding 標準に基づくビデオ エンコードとデコードにハードウェア アクセラレータを使用します。 これにより、CPU クロック速度が低いコンピューターでは、より高い解像度のビデオをエンコードおよびデコードできます。 ビデオ ハードウェア要件は、コンピューター構成と必要なビデオ解像度によって異なります。
  
Windows および [Mac のハードウェア要件も参照してください](https://products.office.com/office-system-requirements)。
  
### <a name="video-hardware-requirements"></a>ビデオ のハードウェア要件

|**機能**|**要件**|
|:-----|:-----|
|DirectX Video Acceleration (DXVA) を使用したハードウェア アクセラレータ H.264 デコード  <br/> |• グラフィックス カードは DirectX 9.0 をサポートする必要があります。また、DXVA2_ModeH264_VLD_NoFGT デコード モードと DirectX 9 API を公開する必要があります。  <br/> • 最新のグラフィックス カード ドライバーがインストールされている必要があります。  <br/> |
|ハードウェア アクセラレータ H.264 エンコード: チップセット要件  <br/> |次の Intel ハードウェア アクセラレータ ビデオ エンコード ソリューションがサポートされています。  <br/> • 統合ハードウェア ビデオ エンコーダーを備えた第 2 世代および第 3 世代の Intel HD Graphics 2000、2500、3000、4000 チップセット (以降のバージョン)。 Intel HD Graphics ドライバー 15.28.9.2884 または次を含む最新のドライバーのインストールが必要です。  <br/> • ディスプレイ ドライバー 9.17.10.2884 または最新のドライバー  <br/> • ハードウェア メディア ファンデーション変換 (HMFT) バージョン 3.12.10.31 または最新の HMFT  <br/> 次の AMD ハードウェア アクセラレータ ビデオ エンコード ソリューションがサポートされています。  <br/> • AMD ビデオ コーデック エンジン。いくつかの個別のグラフィックス カードと、AMD A シリーズ アクセラレータ プロセッサの統合アクセラレータ処理ユニットで利用できます。 AMD Video Codec Engine ドライバー 9.12.0.0 以上がインストールされている必要があります。  <br/> |
|ハードウェア アクセラレータ H.264 エンコード: カメラ要件  <br/> |USB ビデオ クラス (UVC) 仕様バージョン 1.5 に準拠する統合 H.264 ハードウェア エンコーダーを搭載した USB ビデオ カメラ。  <br/> **注:** Skype for Business は、UVC 1.5 のサポートを含む Windows 8 または Windows 8.1 の UVC 1.5 カメラをサポートします。 Windows 7 には UVC 1.5 のサポートが含まれるので、Skype for Business は UVC 1.5 カメラをハードウェア エンコード サポートがない通常のカメラとして扱います。 <br/> |
   
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
|1920x1080  <br/> |1920x1080  <br/> |N/A  <br/> |
   
**DXVA があり、ハードウェア アクセラレータ エンコーダーのないコンピューター**

|**可能なエンコーダー解像度**|**可能なデコーダー解像度**|**要件**|
|:-----|:-----|:-----|
|424x240  <br/> |1920x1080  <br/> |1 コアと and VideoEncodeScore ≥ 3.0  <br/> |
|640x360  <br/> |1920x1080  <br/> |2 コアと VideoEncodeScore ≥ 4.5  <br/> |
|960x540  <br/> |1920x1080  <br/> |2 コアと VideoEncodeScore ≥ 6.0  <br/> |
|1280x720  <br/> |1920x1080  <br/> |4 コアと VideoEncodeScore ≥ 6.7  <br/> |
|1920x1080  <br/> |1920x1080  <br/> |4 コアと VideoEncodeScore ≥ 8.2  <br/> |
   
> [!NOTE]
> Windows 7 での WinSAT スコアは最大 7.9 に制限されます。 したがって、ハードウェア アクセラレータ エンコーダーのないコンピューターのエンコード機能は、最大 WinSAT スコアが 9.9 の Windows 8 または Windows 8.1 でのみ実現できます。 
  
**DXVA と Intel HD グラフィック ハードウェア アクセラレータ エンコーダーがあるコンピューター**

|**可能なエンコーダー解像度**|**可能なデコーダー解像度**|**要件**|
|:-----|:-----|:-----|
|1280x720  <br/> |1920x1080  <br/> |すべての第 2 および第 3 世代 Intel HD Graphics  <br/> |
|1920x1080  <br/> |1920x1080  <br/> |第 2 および第 3 世代 Intel HD Graphics と GraphicsScore ≥ 5.0  <br/> |
   
## <a name="mobile-device-video-capabilities"></a>モバイル デバイスのビデオ機能

次の表に、サポートされているモバイル デバイスで使用可能な最大ビデオ解像度を示します。 For more information about mobile device support, [Mobile client feature comparison for Skype for Business](mobile-feature-comparison.md).
  
|**機能**|**Windows Phone**|**iPhone**|**iPad**|**Android**|
|:-----|:-----|:-----|:-----|:-----|
|H.264 エンコードの最大解像度  <br/> |VGA  <br/> |QVGA: iPhone 4S  <br/> VGA: iPhone 5  <br/> 720p: iPhone 5S 以降  <br/> |VGA: iPad 2 以降/iPad mini 1 以降  <br/> 720p: iPad Air/iPad mini 2/iPad Pro 以降  <br/> |デバイス モデルに応じて VGA まで  <br/> |
|H.264 デコードの最大解像度  <br/> |VGA  <br/> |QVGA: iPhone 4S  <br/> VGA: iPhone 5  <br/> 720p: iPhone 5S 以降  <br/> |VGA: iPad 2 以降/iPad mini 1 以降  <br/> 720p: iPad Air/iPad mini 2/iPad Pro 以降  <br/> |デバイス モデルに応じて VGA まで  <br/> |
   

