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
ms.openlocfilehash: 472436eb4dd9f27d6e170ed723c243c002115d9b
ms.sourcegitcommit: d7e0406276def8bc731aa6dcbd49802441ec5138
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2020
ms.locfileid: "48476652"
---
# <a name="hardware-requirements-for-microsoft-teams"></a>Microsoft Teams のハードウェア要件

以下のセクションのすべての要件は、Microsoft Teams デスクトップ アプリと Teams Web アプリの両方に適用されます。

## <a name="hardware-requirements-for-teams-on-a-windows-pc"></a>Windows PC での Teams のハードウェア要件

| コンポーネント | 要件 |
|---------|---------|
|コンピューターとプロセッサ    | 最低 1.6 GHz (またはそれ以降)、2コア        |
|メモリ     |    4.0 GB の RAM     |
|ハード ディスク    | 3.0 GB の空きディスク容量        |
|ディスプレイ    |   1024 x 768 の画面解像度 |
|グラフィックス ハードウェア |  Windows OS: グラフィックスハードウェアアクセラレーションを使うには、DirectX 9 以降が必要です。 Windows 10 では、WDDM 2.0 以上 (Windows 10 の場合は WDDM 1.3 以上) が必要になります。
|オペレーティング システム  |    Windows 10、Windows 10 ARM、Windows 8.1、Windows Server 2019、Windows Server 2016|
|.NET のバージョン    |  NET 4.5 CLR 以降が必要       |
|ビデオ    |  USB 2.0 ビデオ カメラ       |
|デバイス    |   標準ラップトップ カメラ、マイク、スピーカー    |
|ビデオ通話と会議|<ul><li>2コアプロセッサが必要です。 ビデオ/画面共有の解像度とフレームレートを高くするには、4コアプロセッサ以上をお勧めします。</li> <li>背景のビデオ効果には、Windows 10 または AVX2 の命令を設定するプロセッサが必要です。</li> <li>サポートされていないデコーダーとエンコーダーのリストについては、「[ハードウェア デコーダー/エンコーダー ドライバーの推奨事項](hardware-decoders-and-encoders.md)」を参照してください。</li><li>Microsoft Teams Room の類似性検出を使用して会議に参加するには、Bluetooth LE が必要です。これには、クライアントデバイスで Bluetooth を有効にする必要があります。また、Windows クライアントの場合は、64ビットの Teams クライアントも必要です。 この機能は、32ビット版の Teams クライアントでは使用できません。</li></ul> |
|Teams のライブ イベント | Teams live のイベントを生成する場合は、コア i5 Kaby Lake processor、4.0 GB RAM (以上)、ハードウェアエンコーダーが搭載されたコンピューターを使うことをお勧めします。 サポートされて**いない**デコーダーとエンコーダーの一覧については、「[ハードウェアデコーダーとエンコーダードライバーの推奨事項](hardware-decoders-and-encoders.md)」を参照してください。 |

## <a name="hardware-requirements-for-teams-on-a-mac"></a>Mac での Teams のハードウェア要件

| コンポーネント | 要件 |
|---------|---------|
|コンピューターとプロセッサ    | Intel Core Duo プロセッサ |
|メモリ     |   4.0 GB の RAM      |
|ハード ディスク    |   1.5 GB の空きディスク容量      |
|ディスプレイ    | 1280 x 800 以上の解像度のモニター    |
|オペレーティング システム  |    最新バージョンの macOS のうちの1つ。 最新の macOS バージョンについての情報や、macOS のバージョンをアップグレードする方法については、 [こちら](https://support.apple.com/en-us/HT201260)を参照してください。 たとえば、macOS の新しいバージョンがリリースされると、新しいバージョンとその直前の2つがサポートされているバージョンになります。      |
|ビデオ  |    互換性のある Web カメラ     |
|音声    |  互換性のあるマイクとスピーカー、マイク付きヘッドセット、または同等のデバイス       |
|ビデオ通話と会議 | <ul><li>2コアプロセッサが必要です。 ビデオ/画面共有の解像度とフレームレートを高くするには、4コアプロセッサ以上をお勧めします。 </li><li>Microsoft Teams の Room での類似性検出を使用した会議への参加は、macOS では利用できません。</li></ul>
|

## <a name="hardware-requirements-for-teams-on-linux"></a>Linux での Teams のハードウェア要件

| コンポーネント | 要件 |
|---------|---------|
|コンピューターとプロセッサ    | 1.6 GHz (またはそれ以降) (32 ビットまたは64ビット)、2コア        |
|メモリ     |    4.0 GB の RAM     |
|ハード ディスク    | 3.0 GB の空きディスク容量        |
|ディスプレイ    |   1024 x 768 の画面解像度 |
|グラフィックス ハードウェア |  128 MB グラフィックスメモリ
|オペレーティング システム  | DEB または RPM をインストールできる Linux ディストリビューション。 |
|ビデオ    |  USB 2.0 ビデオ カメラ       |
|デバイス    |   標準ラップトップ カメラ、マイク、スピーカー    |
|音声    |  互換性のあるマイクとスピーカー、マイク付きヘッドセット、または同等のデバイス       |
|ビデオ通話と会議 | <ul><li>2コアプロセッサが必要です。 ビデオ/画面共有の解像度とフレームレートを高くするには、4コアプロセッサ以上をお勧めします。</li><li>Microsoft Teams Room の類似性検出を使用して会議に参加する機能は、Linux では利用できません。</li></ul>
|サポートされている Linux ディストリビューション | Ubuntu 16.04 LTS、18.04 LTS、Fedora 30 Workstation、RHEL 8 Workstation、CentOS 8

## <a name="hardware-requirements-for-teams-on-mobile-devices"></a>モバイル デバイスでの Teams のハードウェア要件

Teams は、次のようなモバイル プラットフォームで使用できます。

- Android: Android スマートフォンおよびタブレットと互換性があります。

  サポートは、最新の **4 つ** の主なバージョンの Android に制限されています。 たとえば、新しいメジャーバージョンの Android がリリースされた場合、Android の要件は新しいバージョンであり、それに先行する3つの最新バージョンです。

- iOS: iPhone、iPad、iPod touch と互換性があります。

  サポートされているのは、iOS の最新の **2 つ** のメジャーバージョンに制限されています。 たとえば、新しいメジャーバージョンの iOS がリリースされた場合、iOS の要件は新しいバージョンであり、その前に最新のバージョンです。 IOS の **[背景** ビデオの効果を追加する] 機能を使うには、ios 12 以降のオペレーティングシステムが必要です。 iPhone 7 以降、iPad 2018 (第6世代) 以降、iPod touch 2019 (7 世代目) に対応しています。

> [!Note]
> Teams を最適なパフォーマンスでご利用いただくために、最新バージョンの iOS および Android を使用してください。

## <a name="hardware-requirements-for-teams-in-a-virtual-desktop-infrastructure-vdi-environment"></a>仮想デスクトップ インフラストラクチャ (VDI) 環境の Teams のハードウェア要件

仮想環境で Teams を実行するための要件については、「[仮想デスクトップ インフラストラクチャ用の Teams](teams-for-vdi.md)」を参照してください。

### <a name="related-topics"></a>関連項目

- [Teams アプリの入手](get-clients.md)
- [モバイル デバイスでの Microsoft Teams](https://support.office.com/article/Microsoft-Teams-on-mobile-devices-2ACBCF73-8FD4-4929-9B31-AE403B88C2D3)
- [MSI を使用して Microsoft Teams アプリをインストールする](msi-deployment.md)
- [Microsoft Teams の制限事項と仕様](limits-specifications-teams.md)
