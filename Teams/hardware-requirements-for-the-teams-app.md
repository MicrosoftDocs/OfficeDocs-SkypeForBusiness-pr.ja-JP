---
title: Microsoft Teams アプリのハードウェア要件
ms.reviewer: ''
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 06/04/2019
audience: Admin
ms.topic: reference
ms.service: msteams
ms.collection:
- M365-collaboration
localization_priority: Normal
search.appverid: MET150
description: Microsoft Teams をインストールして実行するために必要なハードウェア要件について説明します。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 64fc1698b4eda804825342708d430bd4b9dbcff9
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41833167"
---
# <a name="hardware-requirements-for-the-microsoft-teams-app"></a>Microsoft Teams アプリのハードウェア要件

以下のセクションに記載されているすべての要件は、Teams デスクトップアプリと Teams Web アプリの両方に適用されます。

## <a name="hardware-requirements-for-the-teams-desktop-app-on-a-windows-pc"></a>Windows PC の Teams デスクトップアプリのハードウェア要件

|**コンポーネント**|**要件**  |
|---------|---------|
|コンピューターとプロセッサ    | 最小の 1.6 GHz (またはそれ以上) (32 ビットまたは64ビット)。        |
|メモリ     |    2.0 GB の RAM     |
|ハードディスク    | 3.0 GB の空きディスク領域        |
|Display    |   1024 x 768 画面の解像度 |
|グラフィックスハードウェア |  最小 128 MB のグラフィックスメモリ
|オペレーティング システム  |    Windows Server 2012 R2 +、Windows 10、Windows 8.1、または Windows 7 Service Pack 1 (32 ビットと64ビット)。 最適なエクスペリエンスを実現するには、オペレーティングシステムの最新バージョンを使用します。|
|.NET バージョン    |  .NET 4.5 CLR 以降が必要       |
|ビデオ    |  USB 2.0 ビデオカメラ       |
|デバイス    |   標準のラップトップカメラ、マイク、スピーカー    | 
|ビデオ通話と会議 | <ul><li>ビデオ通話とオンライン会議の操作性を向上させるには、2.0 GHz プロセッサと 4.0 GB の RAM (以上) を搭載したコンピューターを使うことをお勧めします。 </li><li>オプションの [背景ビデオの**ぼかし**] では、高度なベクトル拡張機能 2 (AVX2) がサポートされているプロセッサが必要になります。 サポートされていないデコーダーとエンコーダーの一覧については、「[ハードウェアデコーダーとエンコーダードライバーの推奨事項](hardware-decoders-and-encoders.md)」を参照してください。</li><li>Microsoft Teams Room の類似性検出を使用して会議に参加するには、Bluetooth LE が必要です。これには、クライアントデバイスで Bluetooth を有効にする必要があります。また、Windows クライアントでは64ビットチームクライアントが必要です。 32ビット版の Teams クライアントでは使用できません。</li></ul> |
|Teams のライブ イベント | Teams live のイベントを生成する場合は、コア i5 Kaby Lake processor、4.0 GB RAM (以上)、ハードウェアエンコーダーを搭載したコンピューターを使うことをお勧めします。 サポートされていないデコーダーとエンコーダーの一覧については、「[ハードウェアデコーダーとエンコーダードライバーの推奨事項](hardware-decoders-and-encoders.md)」を参照してください。 |

## <a name="hardware-requirements-for-the-teams-desktop-app-on-a-mac"></a>Mac での Teams デスクトップアプリのハードウェア要件

|**コンポーネント**|**要件**  |
|---------|---------|
|プロセッサ    | 最小の Intel プロセッサ、Core 2 Duo 以上 |
|メモリ     |   2.0 GB の RAM      |
|ハードディスク    |   1.5 GB の空きディスク領域      |
|Display    | 1280 x 800 または高解像度    |
|オペレーティング システム  |    Mac OS X 10.11 El Capitan 以降     |
|ビデオ  |    互換性のある web カメラ     |
|音声    |  互換性のあるマイクとスピーカー、マイク付きヘッドセット、または同等のデバイス       |
|ビデオ通話と会議 | ビデオ通話とオンライン会議の操作性を向上させるには、2.0 GHz プロセッサと 4.0 GB の RAM (以上) を搭載したコンピューターを使うことをお勧めします。  <ul><li>オプションの [背景ビデオの**ぼかし**] では、高度なベクトル拡張機能 2 (AVX2) がサポートされていて、最も遅い 2013 Mac デバイス以降でサポートされています。 サポートされていないデコーダーとエンコーダーの一覧については、「[ハードウェアデコーダーとエンコーダードライバーの推奨事項](hardware-decoders-and-encoders.md)」を参照してください。</li><li>Microsoft Teams のルームでの類似性検出を使用した会議への参加は、Mac OS では使用できません。</li></ul> |

## <a name="hardware-requirements-for-the-teams-desktop-app-on-a-linux"></a>Linux での Teams デスクトップアプリのハードウェア要件

|**コンポーネント**|**要件**  |
|---------|---------|
|コンピューターとプロセッサ    | 最小の 1.6 GHz (またはそれ以上) (32 ビットまたは64ビット)。        |
|メモリ     |    2.0 GB の RAM     |
|ハードディスク    | 3.0 GB の空きディスク領域        |
|Display    |   1024 x 768 画面の解像度 |
|グラフィックスハードウェア |  最小 128 MB のグラフィックスメモリ
|オペレーティング システム  | DEB または RPM をインストールできる Linux ディストリビューション。 |
|ビデオ    |  USB 2.0 ビデオカメラ       |
|デバイス    |   標準のラップトップカメラ、マイク、スピーカー    | 
|音声    |  互換性のあるマイクとスピーカー、マイク付きヘッドセット、または同等のデバイス       |
|ビデオ通話と会議 | <ul><li>ビデオ通話とオンライン会議の操作性を向上させるには、2.0 GHz プロセッサと 4.0 GB の RAM (以上) を搭載したコンピューターを使うことをお勧めします。 </li><li>オプションの [背景ビデオのぼかし] では、高度なベクトル拡張機能 2 (AVX2) がサポートされていて、最も遅い 2013 Mac デバイス以降でサポートされています。 サポートされていないデコーダーとエンコーダーの一覧については、「[ハードウェアデコーダーとエンコーダードライバーの推奨事項](hardware-decoders-and-encoders.md)」を参照してください。</li><li>Microsoft Teams のルームでの類似性検出を使用した会議への参加は、Linux では利用できません。</li></ul>
|サポートされている Linux ディストリビューション | Ubuntu 16.04 LTS、18.04 LTS、Fedora 30 ワークステーション、RHEL 8 Workstation、CentOS 8


## <a name="hardware-requirements-for-the-teams-app-on-mobile-devices"></a>モバイルデバイス上の Teams アプリのハードウェア要件

Teams は以下のモバイルプラットフォームで使用できます。

- Android: Android フォンやタブレットとの互換性があります。

  サポートは、最新の4つの主なバージョンの Android に制限されています。 Android の新しいメジャーバージョンがリリースされると、新しいバージョンと以前の3つのバージョンが正式にサポートされます。

- iOS: iPhone、iPad、iPod touch に対応しています。 

  サポートされているのは、iOS の最新の2つのメジャーバージョンに制限されています。 IOS の新しいメジャーバージョンがリリースされると、iOS の新しいバージョンと以前のバージョンは正式にサポートされます。

Teams で最高のエクスペリエンスを実現するには、iOS と Android の最新バージョンを使用します。

## <a name="hardware-requirements-for-the-teams-app-in-a-virtual-desktop-infrastructure-vdi-environment"></a>仮想デスクトップインフラストラクチャ (VDI) 環境での Teams アプリのハードウェア要件

仮想化された環境で Teams を実行するための要件については、「[仮想デスクトップインフラストラクチャのチーム](teams-for-vdi.md)」をご覧ください。 

### <a name="related-topics"></a>関連トピック
- [チームアプリを入手する](get-clients.md)
- [モバイルデバイス上の Microsoft Teams](https://support.office.com/article/Microsoft-Teams-on-mobile-devices-2ACBCF73-8FD4-4929-9B31-AE403B88C2D3)
- [MSI を使用して Microsoft Teams アプリをインストールする](msi-deployment.md)
