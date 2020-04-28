---
title: Microsoft Teams のハードウェア要件
ms.reviewer: ''
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: Admin
ms.topic: reference
ms.service: msteams
ms.collection:
- M365-collaboration
localization_priority: Normal
search.appverid: MET150
description: この記事では、Microsoft Teams をインストールして実行するために必要なハードウェア要件について説明します。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: b85df2a7a5cf341c61d86baef89b0df8a3c4f439
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "43902532"
---
# <a name="hardware-requirements-for-microsoft-teams"></a>Microsoft Teams のハードウェア要件

以下のセクションのすべての要件は、Microsoft Teams デスクトップ アプリと Teams Web アプリの両方に適用されます。

## <a name="hardware-requirements-for-teams-on-a-windows-pc"></a>Windows PC での Teams のハードウェア要件

|**コンポーネント**|**要件**  |
|---------|---------|
|コンピューターとプロセッサ    | 最小 1.6 GHz (またはそれ以上) (32 ビットまたは 64 ビット)。        |
|メモリ     |    2.0 GB RAM     |
|ハード ディスク    | 3.0 GB の空きディスク容量        |
|ディスプレイ    |   1024 x 768 の画面解像度 |
|グラフィックス ハードウェア |  128 MB 以上のグラフィックス メモリ
|オペレーティング システム  |    Windows Server 2012 R2+、Windows 10、Windows 8.1 (32 ビットおよび 64 ビット)。 最適なパフォーマンスでご利用いただくために、最新バージョンのオペレーティング システムを使用してください。|
|.NET のバージョン    |  NET 4.5 CLR 以降が必要       |
|ビデオ    |  USB 2.0 ビデオ カメラ       |
|デバイス    |   標準ラップトップ カメラ、マイク、スピーカー    | 
|ビデオ通話と会議 | <ul><li>ビデオ通話やオンライン会議のエクスペリエンス向上のために、2.0 GHz のプロセッサと 4.0 GB 以上の RAM を搭載したコンピューターの使用をお勧めします。 </li><li>オプションのビデオ効果 **[背景をぼかす]** には、Advanced Vector Extension 2 (AVX2) サポートを備えたプロセッサが必要です。 サポートされていないデコーダーとエンコーダーのリストについては、「[ハードウェア デコーダー/エンコーダー ドライバーの推奨事項](hardware-decoders-and-encoders.md)」を参照してください。</li><li>Microsoft Teams ミーティングで近接性検出を使用して会議に参加するには Bluetooth LE が必要です。これにはクライアント デバイスで Bluetooth を有効にする必要があり、Windows クライアントの場合は 64 ビットの Teams クライアントが必要です。 この機能は、32 ビットの Teams クライアントでは利用できません。</li></ul> |
|Teams のライブ イベント | Teams ライブ イベントを作成する場合は、Core i5 Kaby Lake プロセッサ、4.0 GB RAM (またはそれ以上) とハードウェア エンコーダーを搭載したコンピューターの使用をお勧めします。 サポートされていないデコーダーとエンコーダーのリストについては、「[ハードウェア デコーダー/エンコーダー ドライバーの推奨事項](hardware-decoders-and-encoders.md)」を参照してください。 |

## <a name="hardware-requirements-for-teams-on-a-mac"></a>Mac での Teams のハードウェア要件

|**コンポーネント**|**要件**  |
|---------|---------|
|プロセッサ    | 最小 Intel プロセッサ (Core 2 Duo 以降) |
|メモリ     |   2.0 GB RAM      |
|ハード ディスク    |   1.5 GB の空きディスク容量      |
|ディスプレイ    | 1280 x 800 以上の解像度のモニター    |
|オペレーティング システム  |    Mac OS X 10.11 El Capitan 以降     |
|ビデオ  |    互換性のある Web カメラ     |
|音声    |  互換性のあるマイクとスピーカー、マイク付きヘッドセット、または同等のデバイス       |
|ビデオ通話と会議 | ビデオ通話やオンライン会議のエクスペリエンス向上のために、2.0 GHz のプロセッサと 4.0 GB 以上の RAM を搭載したコンピューターの使用をお勧めします。  <ul><li>オプションのビデオ効果 **[背景をぼかす]** には、Advanced Vector Extension 2 (AVX2) サポート (大半の 2013 年後半の Mac デバイス以降でサポートされています) を備えたプロセッサが必要です。 サポートされていないデコーダーとエンコーダーのリストについては、「[ハードウェア デコーダー/エンコーダー ドライバーの推奨事項](hardware-decoders-and-encoders.md)」を参照してください。</li><li>Microsoft Teams ミーティングの類似性検出を使用して会議に参加する機能は、Mac OS では利用できません。</li></ul> |

## <a name="hardware-requirements-for-teams-on-linux"></a>Linux での Teams のハードウェア要件

|**コンポーネント**|**要件**  |
|---------|---------|
|コンピューターとプロセッサ    | 最小 1.6 GHz (またはそれ以上) (32 ビットまたは 64 ビット)。        |
|メモリ     |    2.0 GB RAM     |
|ハード ディスク    | 3.0 GB の空きディスク容量        |
|ディスプレイ    |   1024 x 768 の画面解像度 |
|グラフィックス ハードウェア |  128 MB 以上のグラフィックス メモリ
|オペレーティング システム  | DEB または RPM をインストールできる Linux ディストリビューション。 |
|ビデオ    |  USB 2.0 ビデオ カメラ       |
|デバイス    |   標準ラップトップ カメラ、マイク、スピーカー    | 
|音声    |  互換性のあるマイクとスピーカー、マイク付きヘッドセット、または同等のデバイス       |
|ビデオ通話と会議 | <ul><li>ビデオ通話やオンライン会議のエクスペリエンス向上のために、2.0 GHz のプロセッサと 4.0 GB 以上の RAM を搭載したコンピューターの使用をお勧めします。 </li><li>オプションのビデオ効果 [背景をぼかす] には、Advanced Vector Extension 2 (AVX2) サポート (大半の 2013 年後半の Mac デバイス以降でサポートされています) を備えたプロセッサが必要です。 サポートされていないデコーダーとエンコーダーのリストについては、「[ハードウェア デコーダー/エンコーダー ドライバーの推奨事項](hardware-decoders-and-encoders.md)」を参照してください。</li><li>Microsoft Teams ミーティングの類似性検出を使用して会議に参加する機能は、Linux では利用できません。</li></ul>
|サポートされている Linux ディストリビューション | Ubuntu 16.04 LTS、18.04 LTS、Fedora 30 Workstation、RHEL 8 Workstation、CentOS 8

## <a name="hardware-requirements-for-teams-on-mobile-devices"></a>モバイル デバイスでの Teams のハードウェア要件

Teams は、次のようなモバイル プラットフォームで使用できます。

- Android: Android スマートフォンおよびタブレットと互換性があります。

  サポート対象は、最新の 4 つのメジャー バージョンの Android に限られています。 新しいメジャー バージョンの Android がリリースされると、その新しいバージョンと、その前の 3 つのバージョンが正式にサポートされます。

- iOS: iPhone、iPad、iPod touch と互換性があります。

  サポート対象は、最新の 2 つのメジャー バージョンの iOS に限られています。 新しいメジャー バージョンの iOS がリリースされると、その新しいバージョンの iOS と、その 1 つ前のバージョンが正式にサポートされます。

Teams を最適なパフォーマンスでご利用いただくために、最新バージョンの iOS および Android を使用してください。

## <a name="hardware-requirements-for-teams-in-a-virtual-desktop-infrastructure-vdi-environment"></a>仮想デスクトップ インフラストラクチャ (VDI) 環境の Teams のハードウェア要件

仮想環境で Teams を実行するための要件については、「[仮想デスクトップ インフラストラクチャ用の Teams](teams-for-vdi.md)」を参照してください。

### <a name="related-topics"></a>関連項目
- [Teams アプリの入手](get-clients.md)
- [モバイル デバイスでの Microsoft Teams](https://support.office.com/article/Microsoft-Teams-on-mobile-devices-2ACBCF73-8FD4-4929-9B31-AE403B88C2D3)
- [MSI を使用して Microsoft Teams アプリをインストールする](msi-deployment.md)
- [Microsoft Teams の制限事項と仕様](limits-specifications-teams.md)
