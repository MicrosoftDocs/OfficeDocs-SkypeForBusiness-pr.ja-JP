---
title: Skype for Business クライアントのビデオの解像度
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: '概要: Skype for Business Server を計画しているときに、クライアントのビデオの要件を確認します。'
ms.openlocfilehash: 126c19d817a2cd656b7d581e0d467db80e4969e5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42027978"
---
# <a name="skype-for-business-client-video-resolutions"></a>Skype for Business クライアントのビデオの解像度
 
**概要:** Skype for Business Server を計画しているときに、クライアントのビデオの要件を確認します。
  
この記事では、Skype for Business ビデオ通話のビデオハードウェアサポートについて説明し、さまざまなコンピューター、タブレット、およびモバイルデバイス構成について予想されるビデオ品質を判断する方法について説明します。 
  
IT 担当者は、組織内で既に使用されているラップトップの適合性を評価したり、使用を検討したりするのに役立つ情報を入手できます。 また、[ソリューションカタログ](https://partnersolutions.skypeforbusiness.com/solutionscatalog)を検索して特定のデバイスに関する情報を検索することもできます。
  
## <a name="windows-desktop-mac-and-tablet-video-requirements-and-capabilities"></a>Windows デスクトップ、Mac、タブレットのビデオの要件と機能

Skype for Business では、ハードウェアアクセラレータを使用してビデオのエンコードとデコードを行います。これには、「264/MPEG-2 Part 10 Advanced Video コーディング規格」に基づいています。 これにより、CPU クロック速度の低いコンピューターが高解像度のビデオをエンコードおよびデコードすることができます。 ビデオ ハードウェア要件は、コンピューター構成と必要なビデオ解像度によって異なります。
  
また[、Windows と Mac のハードウェア要件](https://products.office.com/office-system-requirements)も参照してください。
  
### <a name="video-hardware-requirements"></a>ビデオハードウェア要件

|**機能**|**要件**|
|:-----|:-----|
|DirectX Video Acceleration (DXVA) を使用したハードウェア アクセラレータ H.264 デコード  <br/> |• Graphics card は DirectX 9.0 をサポートしている必要があり、DXVA2_ModeH264_VLD_NoFGT デコードモードおよび DirectX 9 API を公開する必要があります。  <br/> •最新のグラフィックスカードドライバーがインストールされている必要があります。  <br/> |
|ハードウェア アクセラレータ H.264 エンコード: チップセット要件  <br/> |次のインテルハードウェアアクセラレータビデオエンコードソリューションがサポートされています。  <br/> •ハードウェアビデオエンコーダーが統合された、2番目および3世代の Intel HD Graphics 2000、2500、3000、および4000チップセット (またはそれ以降のバージョン)。 Intel HD Graphics driver 15.28.9.2884 または次のものを含む最新ドライバーがインストールされている必要があります。  <br/> •ディスプレイドライバー9.17.10.2884 または最新ドライバー  <br/> • Hardware media foundation transform (HMFT) バージョン3.12.10.31 または最新の HMFT  <br/> 次の AMD ハードウェアアクセラレータビデオエンコードソリューションがサポートされています。  <br/> • AMD ビデオコーデックエンジン。これは、いくつかの個別のグラフィックスカードと、AMD A シリーズの高速プロセッサの統合された高速処理ユニットで利用できます。 AMD Video コーデックエンジンドライバー9.12.0.0 以上がインストールされている必要があります。  <br/> |
|ハードウェア アクセラレータ H.264 エンコード: カメラ要件  <br/> |USB ビデオ クラス (UVC) 仕様バージョン 1.5 に準拠する統合 H.264 ハードウェア エンコーダーを搭載した USB ビデオ カメラ。  <br/> **注:** Skype for Business は、Windows 8 または Windows 8.1 で UVC 1.5 カメラをサポートします。これには UVC 1.5 のサポートが含まれています。 Windows 7 には UVC 1.5 のサポートが含まれていないため、Skype for Business は UVC 1.5 カメラを標準のカメラとして扱い、ハードウェアエンコードをサポートしません。 <br/> |
   
### <a name="determining-h264-video-encoding-and-decoding-capabilities"></a>264ビデオエンコードおよびデコード機能を決定する

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
|424x240  <br/> |1920x1080  <br/> |1 コアと and VideoEncodeScore ≥ 3.0  <br/> |
|640x360  <br/> |1920x1080  <br/> |2 コアと VideoEncodeScore ≥ 4.5  <br/> |
|960x540  <br/> |1920x1080  <br/> |2 コアと VideoEncodeScore ≥ 6.0  <br/> |
|1280x720  <br/> |1920x1080  <br/> |4 コアと VideoEncodeScore ≥ 6.7  <br/> |
|1920x1080  <br/> |1920x1080  <br/> |4 コアと VideoEncodeScore ≥ 8.2  <br/> |
   
> [!NOTE]
> Windows 7 での WinSAT スコアは最大 7.9 に制限されます。 そのため、ハードウェアアクセラレータエンコーダーを使用していないコンピューターのエンコード機能は、Windows 8 または Windows 8.1 でのみ実現できます。これは、最大 WinSAT スコアは9.9 です。 
  
**DXVA と Intel HD グラフィック ハードウェア アクセラレータ エンコーダーがあるコンピューター**

|**可能なエンコーダー解像度**|**可能なデコーダー解像度**|**要件**|
|:-----|:-----|:-----|
|1280x720  <br/> |1920x1080  <br/> |すべての第 2 および第 3 世代 Intel HD Graphics  <br/> |
|1920x1080  <br/> |1920x1080  <br/> |第 2 および第 3 世代 Intel HD Graphics と GraphicsScore ≥ 5.0  <br/> |
   
## <a name="mobile-device-video-capabilities"></a>モバイルデバイスのビデオ機能

次の表に、サポートされているモバイルデバイスで使用できる最大ビデオ解像度を示します。 モバイルデバイスのサポートの詳細については、「 [Skype For business のモバイルクライアント機能の比較](mobile-feature-comparison.md)」を参照してください。
  
|**機能**|**Windows Phone**|**iPhone**|**iPad**|**Android**|
|:-----|:-----|:-----|:-----|:-----|
|.H エンコードの最大解像度  <br/> |VGA  <br/> |QVGA: iPhone 4S  <br/> VGA: iPhone 5  <br/> 720p: iPhone 5S 以降  <br/> |VGA: iPad 2 以降/iPad mini 1 以降  <br/> 720p: iPad Air/iPad mini 2/iPad Pro 以降  <br/> |デバイスモデルによっては最大 VGA  <br/> |
|.H デコードの最大解像度  <br/> |VGA  <br/> |QVGA: iPhone 4S  <br/> VGA: iPhone 5  <br/> 720p: iPhone 5S 以降  <br/> |VGA: iPad 2 以降/iPad mini 1 以降  <br/> 720p: iPad Air/iPad mini 2/iPad Pro 以降  <br/> |デバイスモデルによっては最大 VGA  <br/> |
   

