---
title: Skype for Business クライアントのビデオ解像度
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 8f68f4c2-3194-487c-bd2f-fbe71ba8ad70
description: '概要: クライアントビデオの要件を確認し、クライアントビデオのSkype for Business Server。'
ms.openlocfilehash: 6a483a67b298f2d1ce9a32fbcd7e89882c0598aa
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60745883"
---
# <a name="skype-for-business-client-video-resolutions"></a>Skype for Business クライアントのビデオ解像度
 
**概要:** クライアントビデオの要件を確認し、クライアントビデオのSkype for Business Server。
  
この記事では、Skype for Business ビデオ通話に対するビデオ ハードウェアのサポートについて説明し、さまざまなコンピューター、タブレット、およびモバイル デバイス構成で期待されるビデオ品質を判断する方法について説明します。 
  
IT 担当者は、この情報を組織内で既に使用しているラップトップの適合性を評価したり、使用を検討したりする際に役立ちます。 また、特定のデバイスに[関Microsoft Teamsデバイス](https://www.microsoft.com/microsoft-teams/across-devices/device)で検索することもできます。
  
## <a name="windows-desktop-mac-and-tablet-video-requirements-and-capabilities"></a>Windows、Mac、タブレットのビデオ要件と機能

Skype for Businessは、H.264/MPEG-4 Part 10 Advanced Video Coding standard に基づくビデオ エンコードとデコードにハードウェア アクセラレータを使用します。 これにより、CPU クロック速度が低いコンピューターは、高解像度ビデオをエンコードおよびデコードできます。 ビデオ ハードウェア要件は、コンピューター構成と必要なビデオ解像度によって異なります。
  
「ハードウェア要件[Windows Mac ハードウェア要件」も参照してください](https://products.office.com/office-system-requirements)。
  
### <a name="video-hardware-requirements"></a>ビデオ ハードウェアの要件

|**機能**|**要件**|
|:-----|:-----|
|DirectX Video Acceleration (DXVA) を使用したハードウェア アクセラレータ H.264 デコード  <br/> |• グラフィックス カードは DirectX 9.0 をサポートする必要があります。また、デコード モードと DirectX 9 API DXVA2_ModeH264_VLD_NoFGTを公開する必要があります。  <br/> • 最新のグラフィックス カード ドライバーをインストールする必要があります。  <br/> |
|ハードウェア アクセラレータ H.264 エンコード: チップセット要件  <br/> |次の Intel ハードウェア アクセラレータビデオ エンコード ソリューションがサポートされています。  <br/> • 第 2 世代および第 3 世代の Intel HD Graphics 2000、2500、3000、および 4000 チップセット (以降のバージョン) と統合ハードウェア ビデオ エンコーダー。 Intel HD Graphics ドライバー 15.28.9.2884 または以下を含む最新のドライバーのインストールが必要です。  <br/> • ディスプレイ ドライバー 9.17.10.2884 または最新のドライバー  <br/> • ハードウェア メディアファンデーション変換 (HMFT) バージョン 3.12.10.31 または最新の HMFT  <br/> 次の AMD ハードウェア アクセラレータビデオ エンコード ソリューションがサポートされています。  <br/> • AMD ビデオ コーデック エンジン。これは、複数のディスクリート グラフィックス カードと、AMD A シリーズ アクセラレータプロセッサの統合された高速処理ユニットで利用できます。 AMD ビデオ コーデック エンジン ドライバー 9.12.0.0 以上をインストールする必要があります。  <br/> |
|ハードウェア アクセラレータ H.264 エンコード: カメラ要件  <br/> |USB ビデオ クラス (UVC) 仕様バージョン 1.5 に準拠する統合 H.264 ハードウェア エンコーダーを搭載した USB ビデオ カメラ。  <br/> **注:** Skype for Businessは、UVC 1.5 のサポートをWindows 8またはWindows 8.1 UVC 1.5 カメラをサポートします。 Windows 7 には UVC 1.5 のサポートが含まれるため、Skype for Business では UVC 1.5 カメラをハードウェア エンコードのサポートがない通常のカメラとして扱います。 <br/> |
   
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
|424x240  <br/> |1920x1080  <br/> |1 コアと and VideoEncodeScore ≥ 3.0  <br/> |
|640x360  <br/> |1920x1080  <br/> |2 コアと VideoEncodeScore ≥ 4.5  <br/> |
|960x540  <br/> |1920x1080  <br/> |2 コアと VideoEncodeScore ≥ 6.0  <br/> |
|1280x720  <br/> |1920x1080  <br/> |4 コアと VideoEncodeScore ≥ 6.7  <br/> |
|1920x1080  <br/> |1920x1080  <br/> |4 コアと VideoEncodeScore ≥ 8.2  <br/> |
   
> [!NOTE]
> Windows 7 での WinSAT スコアは最大 7.9 に制限されます。 したがって、ハードウェア アクセラレータエンコーダーのないコンピューターのエンコード機能は、最大 WinSAT スコアが 9.9 の Windows 8 または Windows 8.1 でのみ実現できます。 
  
**DXVA と Intel HD グラフィック ハードウェア アクセラレータ エンコーダーがあるコンピューター**

|**可能なエンコーダー解像度**|**可能なデコーダー解像度**|**要件**|
|:-----|:-----|:-----|
|1280x720  <br/> |1920x1080  <br/> |すべての第 2 および第 3 世代 Intel HD Graphics  <br/> |
|1920x1080  <br/> |1920x1080  <br/> |第 2 および第 3 世代 Intel HD Graphics と GraphicsScore ≥ 5.0  <br/> |
   
## <a name="mobile-device-video-capabilities"></a>モバイル デバイスのビデオ機能

次の表では、サポートされているモバイル デバイスで使用可能な最大ビデオ解像度について説明します。 モバイル デバイスのサポートの詳細については、「[モバイル クライアント](mobile-feature-comparison.md)機能の比較」を参照Skype for Business。
  
|**機能**|**Windows Phone**|**iPhone**|**iPad**|**Android**|
|:-----|:-----|:-----|:-----|:-----|
|H.264 エンコードの最大解像度  <br/> |VGA  <br/> |QVGA: iPhone 4S  <br/> VGA: iPhone 5  <br/> 720p: iPhone 5S 以降  <br/> |VGA: iPad 2 以降/iPadミニ 1 以降  <br/> 720p: iPad/iPad ミニ 2/iPad Pro以降  <br/> |デバイス モデルに応じて最大 VGA  <br/> |
|H.264 デコードの最大解像度  <br/> |VGA  <br/> |QVGA: iPhone 4S  <br/> VGA: iPhone 5  <br/> 720p: iPhone 5S 以降  <br/> |VGA: iPad 2 以降/iPadミニ 1 以降  <br/> 720p: iPad/iPad ミニ 2/iPad Pro以降  <br/> |デバイス モデルに応じて最大 VGA  <br/> |
   

