---
title: Microsoft Teams のハードウェア要件
ms.reviewer: microthk, sthurlow
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: Admin
ms.topic: reference
ms.service: msteams
ms.collection:
- M365-collaboration
- m365initiative-deployteams
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
ms.openlocfilehash: 90d59bb7753cfd26cf6d0b90835cf8cf27661641
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/13/2020
ms.locfileid: "49030273"
---
# <a name="hardware-requirements-for-microsoft-teams"></a>Microsoft Teams のハードウェア要件

以下のセクションのすべての要件は、Microsoft Teams デスクトップ アプリと Teams Web アプリの両方に適用されます。

## <a name="hardware-requirements-for-teams-on-a-windows-pc"></a>Windows PC での Teams のハードウェア要件

| コンポーネント | 要件 |
|---------|---------|
|コンピューターとプロセッサ    | 最小 1.6 GHz 以上、2コア        |
|メモリ     |    4.0 GB RAM     |
|ハード ディスク    | 3.0 GB の空きディスク容量        |
|ディスプレイ    |   1024 x 768 の画面解像度 |
|グラフィックス ハードウェア |  Windows OS: グラフィック ハードウェア アクセラレータを使用するには、Windows 10 用の WDDM 2.0以降 (または Windows 10 Fall Creators Update 用の WDDM 1.3 以降) と共にDirectX 9 以降をインストールする必要があります。
|オペレーティング システム  |    Windows 10, ARM 上の Windows 10, Windows 8.1, Windows Server 2019, Windows Server 2016|
|.NET のバージョン    |  NET 4.5 CLR 以降が必要       |
|ビデオ    |  USB 2.0 ビデオ カメラ       |
|デバイス    |   標準ラップトップ カメラ、マイク、スピーカー    |
|ビデオ通話と会議|<ul><li>これには、2 コア プロセッサが必要です。 ビデオ/画面共有の解像度とフレーム レートを高くするには、4 コア プロセッサまたはそれ以上のものをお勧めします。</li> <li>背景ビデオの効果には、Windows 10 または、AVX2 命令セット付プロセッサが必要です。</li> <li>サポートされていないデコーダーとエンコーダーのリストについては、「[ハードウェア デコーダーとエンコーダー ドライバーの推奨事項](hardware-decoders-and-encoders.md)」を参照してください。</li><li>Microsoft Teams Room で類似性検出を使用して会議に参加するには Bluetooth LE が必要です。これにはクライアント デバイスで Bluetooth を有効にする必要があり、Windows クライアントの場合は 64 ビットの Teams クライアントが必要です。 この機能は、32 ビットの Teams クライアントでは利用できません。</li></ul> |
|Teams のライブ イベント | Teams ライブ イベントを作成する場合は、Core i5 Kaby Lake プロセッサ、4.0 GB RAM (またはそれ以上) とハードウェア エンコーダーを搭載したコンピューターの使用をお勧めします。 **サポートされていない** デコーダーとエンコーダーのリストについては、「[ハードウェア デコーダーとエンコーダー ドライバーの推奨事項](hardware-decoders-and-encoders.md)」を参照してください。 |

## <a name="hardware-requirements-for-teams-on-a-mac"></a>Mac での Teams のハードウェア要件

| コンポーネント | 要件 |
|---------|---------|
|コンピューターとプロセッサ    | インテル® Core Duo プロセッサー |
|メモリ     |   4.0 GB RAM      |
|ハード ディスク    |   1.5 GB の空きディスク容量      |
|ディスプレイ    | 1280 x 800 以上の解像度のモニター    |
|オペレーティング システム  |    MacOS の 3 つの最新バージョンのいずれか。 最新の MacOS バージョンについての詳細とMacOS バージョンをアップグレードする方法については、[こちら](https://support.apple.com/ja-JP/HT201260)を参照 してください。 たとえば、新しいバージョンの MacOS がリリースされたときに、新しいバージョンとそのすぐ前にある 2つのバージョンがサポートされています。      |
|ビデオ  |    互換性のある Web カメラ     |
|音声    |  互換性のあるマイクとスピーカー、マイク付きヘッドセット、または同等のデバイス       |
|ビデオ通話と会議 | <ul><li>これには、2 コア プロセッサが必要です。 ビデオ/画面共有の解像度とフレーム レートを高くするには、4 コア プロセッサまたはそれ以上のものをお勧めします。 </li><li>Microsoft Teams Room の類似性検出を使用して会議に参加する機能は、MacOS では利用できません。</li></ul>
|

## <a name="hardware-requirements-for-teams-on-linux"></a>Linux での Teams のハードウェア要件

| コンポーネント | 要件 |
|---------|---------|
|コンピューターとプロセッサ    | 1.6 GHz (またはそれ以上) (32 ビットまたは 64 ビット)、2 コア        |
|メモリ     |    4.0 GB RAM     |
|ハード ディスク    | 3.0 GB の空きディスク容量        |
|ディスプレイ    |   1024 x 768 の画面解像度 |
|グラフィックス ハードウェア |  128 MB 以上のグラフィックス メモリ
|オペレーティング システム  | DEB または RPM をインストールできる Linux ディストリビューション。 |
|ビデオ    |  USB 2.0 ビデオ カメラ       |
|デバイス    |   標準ラップトップ カメラ、マイク、スピーカー    |
|音声    |  互換性のあるマイクとスピーカー、マイク付きヘッドセット、または同等のデバイス       |
|ビデオ通話と会議 | <ul><li>これには、2 コア プロセッサが必要です。 ビデオ/画面共有の解像度とフレーム レートを高くするには、4 コア プロセッサまたはそれ以上のものをお勧めします。</li><li>Microsoft Teams Room の類似性検出を使用して会議に参加する機能は、Linux では利用できません。</li></ul>
|サポートされている Linux ディストリビューション | Ubuntu 18.04 LTS, 20.04 LTS, Fedora 30 Workstation, RHEL 8 Workstation, CentOS 8       |
|サポートされているデスクトップ環境 | GNOME、KDE       |
|サポートされるディスプレイ サーバー | X11       |

## <a name="hardware-requirements-for-teams-on-mobile-devices"></a>モバイル デバイスでの Teams のハードウェア要件

Teams は、次のようなモバイル プラットフォームで使用できます。

- Android: Android スマートフォンおよびタブレットと互換性があります。

  サポート対象は、Android の **最新の 4 つ** のメジャー バージョンに限られています。 たとえば、Android の新しいメジャー バージョンがリリースされたときに、Android の要件は新しいバージョンと、その直前の 3 つの最新バージョンです。 

- iOS: iPhone、iPad、iPod touch と互換性があります。

  サポート対象は、最新の **2 つ** のメジャー バージョンの iOS に限られています。 たとえば、iOS の新しいメジャー バージョンがリリースされた場合、iOS の要件は新しいバージョンと、その前の最新のバージョンです。 iOS のオプションの **背景をぼかす** ビデオ効果には、iOS 12 以降のオペレーティング システムが必要であり、次のデバイスと互換性があります: iPhone 7 以降、iPad 2018 (第 6 世代) 以降、および iPod touch 2019 (第 7 世代)。

> [!Note]
> Teams を最適なパフォーマンスでご利用いただくために、最新バージョンの iOS および Android を使用してください。

## <a name="hardware-requirements-for-teams-in-a-virtual-desktop-infrastructure-vdi-environment"></a>仮想デスクトップ インフラストラクチャ (VDI) 環境の Teams のハードウェア要件

仮想環境で Teams を実行するための要件については、「[仮想デスクトップ インフラストラクチャ用の Teams](teams-for-vdi.md)」を参照してください。

### <a name="related-topics"></a>関連項目

- [Teams アプリの入手](get-clients.md)
- [モバイル デバイスでの Microsoft Teams](https://support.office.com/article/Microsoft-Teams-on-mobile-devices-2ACBCF73-8FD4-4929-9B31-AE403B88C2D3)
- [MSI を使用して Microsoft Teams アプリをインストールする](msi-deployment.md)
- [Microsoft Teams の制限事項と仕様](limits-specifications-teams.md)
