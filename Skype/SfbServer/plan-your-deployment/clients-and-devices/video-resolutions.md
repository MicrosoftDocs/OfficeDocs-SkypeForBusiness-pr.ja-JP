---
title: Skype for Business クライアントのビデオ解像度
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 8f68f4c2-3194-487c-bd2f-fbe71ba8ad70
description: '概要: Skype for Business Server の計画中にクライアントのビデオ要件を確認します。'
ms.openlocfilehash: 15fd424f7ad2e11d473e49e271c7fbf1db83b45c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277280"
---
# <a name="skype-for-business-client-video-resolutions"></a>Skype for Business クライアントのビデオ解像度
 
**概要:** Skype for Business Server を計画しているときに、クライアントのビデオ要件を確認します。
  
この記事では、Skype for Business ビデオ通話に関するビデオハードウェアのサポートについて説明し、さまざまなコンピューター、タブレット、モバイルデバイスの構成について予想されるビデオ品質を決定する方法について説明します。 
  
IT 担当者は、組織内で既に使用されているノート pc の適合性の評価、または使用の検討で、この情報を見つけることができます。 また、特定のデバイスに関する情報については、 [Solutions Catalog](https://partnersolutions.skypeforbusiness.com/solutionscatalog)で検索することもできます。
  
## <a name="windows-desktop-mac-and-tablet-video-requirements-and-capabilities"></a>Windows デスクトップ、Mac、タブレットのビデオ要件と機能

Skype for Business では、ハードウェアアクセラレータを使って、ビデオのエンコードとデコードについて詳しくは、「264/MPEG-2 パート10の高度なビデオコーディング規格」を使用しています。 これにより、CPU クロック速度の低いコンピュータが高解像度のビデオのエンコードとデコードを行うことができます。 ビデオ ハードウェア要件は、コンピューター構成と必要なビデオ解像度によって異なります。
  
「 [Windows と Mac のハードウェア要件](https://products.office.com/en-us/office-system-requirements)」もご覧ください。
  
### <a name="video-hardware-requirements"></a>ビデオ ハードウェア要件

|**機能**|**要件**|
|:-----|:-----|
|DirectX Video Acceleration (DXVA) を使用したハードウェア アクセラレータ H.264 デコード  <br/> |•グラフィックスカードは DirectX 9.0 をサポートしており、DXVA2_ModeH264_VLD_NoFGT デコードモードと DirectX 9 API を公開している必要があります。  <br/> •最新のグラフィックスカードドライバーがインストールされている必要があります。  <br/> |
|ハードウェア アクセラレータ H.264 エンコード: チップセット要件  <br/> |次の Intel ハードウェア アクセラレータ ビデオ エンコード ソリューションがサポートされます。  <br/> •ハードウェアビデオエンコーダー内蔵の第2世代および第3世代の Intel HD グラフィックス2000、2500、3000、4000チップセット (以降のバージョン)。 Intel HD Graphics ドライバー 15.28.9.2884 または以下を含む最新ドライバーが必要です。  <br/> •ディスプレイドライバー9.17.10.2884 または最新のドライバを表示  <br/> •ハードウェアメディアファンデーション変換 (HMFT) バージョン3.12.10.31 または最新の HMFT  <br/> 次の AMD ハードウェア アクセラレータ ビデオ エンコード ソリューションがサポートされます。  <br/> • AMD ビデオコーデックエンジン。複数の独立したグラフィックスカードで使用できます。また、AMD A シリーズの高速プロセッサで、統合された高速処理ユニットを利用できます。 AMD Video Codec Engine ドライバー 9.12.0.0 またはそれ以上がインストールされている必要があります。  <br/> |
|ハードウェア アクセラレータ H.264 エンコード: カメラ要件  <br/> |USB ビデオ クラス (UVC) 仕様バージョン 1.5 に準拠する統合 H.264 ハードウェア エンコーダーを搭載した USB ビデオ カメラ。  <br/> **注:** Skype for Business は、Windows 8 または Windows 8.1 で UVC 1.5 カメラをサポートしています。 UVC 1.5 はサポートされています。 Windows 7 には UVC 1.5 のサポートが含まれていないため、Skype for Business は UVC 1.5 のカメラを通常のカメラとして扱うため、ハードウェアエンコードはサポートされていません。 <br/> |
   
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

次の表では、サポートされているモバイルデバイスで利用可能なビデオの最大解像度について説明します。 モバイルデバイスのサポートの詳細については、「 [Skype For business のモバイルクライアント機能の比較](mobile-feature-comparison.md)」を参照してください。
  
|**機能**|**Windows Phone**|**iPhone**|**iPad**|**Android**|
|:-----|:-----|:-----|:-----|:-----|
|H.264 エンコードの最大解像度  <br/> |VGA  <br/> |QVGA: iPhone 4S  <br/> VGA: iPhone 5  <br/> 720p: iPhone 5S 以降  <br/> |VGA: iPad 2 以降/iPad mini 1 以降  <br/> 720p: iPad Air/iPad mini 2/iPad Pro 以降  <br/> |デバイスのモデルに応じて VGA を最大にする  <br/> |
|H.264 デコードの最大解像度  <br/> |VGA  <br/> |QVGA: iPhone 4S  <br/> VGA: iPhone 5  <br/> 720p: iPhone 5S 以降  <br/> |VGA: iPad 2 以降/iPad mini 1 以降  <br/> 720p: iPad Air/iPad mini 2/iPad Pro 以降  <br/> |デバイスのモデルに応じて VGA を最大にする  <br/> |
   

