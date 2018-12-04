---
title: サーフェスのハブのマイクロソフトのチームを配置します。
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 12/04/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: jatpatel
description: サーフェスのハブのマイクロソフトのチームの管理の設定を構成します。
localization_priority: Normal
search.appverid: MET150
ms.custom:
- Devices
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 485e4063c523608421955b86e0be680d5dc10b9a
ms.sourcegitcommit: 5742301cdd28e5e26107920f18e70f41b0f67cfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/03/2018
ms.locfileid: "27132004"
---
<a name="deploy-microsoft-teams-for-surface-hub"></a>サーフェスのハブのマイクロソフトのチームを配置します。
======================================

Microsoft Surface のハブのマイクロソフトのチームを配置する前に、ハードウェア、オペレーティング システム、およびその他の要件を満たしていることを確認してください。 詳細については、 [Microsoft Surface ハブ管理者ガイド](https://docs.microsoft.com/surface-hub/)を参照してください。

> [!NOTE]
> ビジネス オンラインの Skype から移行するが場合、は、マイクロソフトのチームのライセンスがユーザーに割り当てられていることを確認する必要があります。

## <a name="install-teams-for-surface-hub-from-the-microsoft-store"></a>Microsoft ストアからのサーフェスのハブのチームをインストールします。 

これらは、Microsoft ストアからのサーフェスのハブのチームをインストールします。 
 
1. マイクロソフトのストアを開始します。<br>
   a. **スタート**をタップして > **すべてのアプリケーション** > **の設定**です。<br> b. **サーフェス ハブ デバイスのアカウント、管理**をタップします。<br>
   c. 左側の [**アプリケーションと機能**] タブをタップします。<br> d. 、右側には、**ストアを開く**] ボタンをタップします。 
2. マイクロソフト ストアからには、*マイクロソフトのチーム*を検索します。 **サーフェスのハブのマイクロソフトのチーム**が表示されます。 インストールする**アプリケーションを取得する**ボタンをタップします。  
3. インストールが完了すると、サーフェスのハブを再起動します。 

> [!NOTE]
> ページを一覧表示するストアからの**起動**をタップしないようにします。

## <a name="make-teams-the-default-calling-and-meetings-application"></a>デフォルトの通話や会議アプリケーションは、チームを作成します。
 
通話や会議アプリケーションの既定ポリシーを構成するための 2 つのオプションがあります。 

- **オプション 1**: USB キーを使用して構成します。 
- **オプション 2**: Intune などの MDM を使用して構成します。
 
### <a name="option-1-configure-via-usb-key"></a>オプション 1: は、USB キーを使用して構成します。 
 
この[ダウンロード ページ](https://1drv.ms/f/s!ArcnbnREun0Vnp9Wps9MlWB-UJZw3g)で、パッケージをご覧ください。 適切なパッケージをインストールし、USB キーにコピーする予定しているを選択します。 正しい .ppkg ファイルを使用するのには、次のように適用するにはアプリケーションの既定のポリシーによって異なります。 

|数値  |説明  |
|---------|---------|
|0     | [開始] 画面で [チームの会議が利用可能な Skype 優先のアプリケーション        |
|1     | チーム優先のアプリケーション起動画面で、利用可能な Skype の会議        |
|2     | チームの排他的なアプリケーション (Skype アプリが利用できない) の開始画面        |
 
1. サーフェス ハブ デバイスに USB キーを接続します。 
2. サーフェス ハブ デバイスの**設定**アプリを開きます。 
3. **表面ハブ デバイスのアカウントの管理**を開きます。
4. **デバイスの管理**を開きます。 
5. **追加またはプロビジョニング ・ パッケージを削除する**] をクリックします。 
6. **パッケージの追加**] をクリックします。
7. ドロップ ダウン メニューから、[**リムーバブル メディア**] オプションを選択します。 
8. 以前、USB キーにコピーされた適切な<strong>TeamsRTMMode*.ppkg</strong>パッケージを追加します。 
9. サーフェス ハブ デバイスを再起動します。 
10. デバイスを再起動した後は、開始画面から、チームのアプリケーションを起動し、カレンダーから会議に参加することができます。 

### <a name="option-2-configure-via-mdm-such-as-intune"></a>Intune などの MDM を使用してオプション 2: を構成します。 

Intune を使用して既定の通話や会議のアプリケーション ポリシーを構成するのにには、次を使用します。 [展開 Intune を使用してサーフェスのハブのアプリケーションのマイクロソフトのチーム](https://blogs.technet.microsoft.com/y0av/2018/07/16/97/)のブログを参照してください。

|設定   |値    |説明    |
|----------|---------|---------|
| Path      | ./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode        |
|データ型 | 整数 (0-2)   |0 - [開始] 画面で [チームの会議が利用可能な Skype 優先のアプリケーション<br>1 のチーム開始画面で、Skype の会議が利用可能なアプリケーションを優先します。<br>2-チームは、開始画面 (Skype アプリケーションではありません排他的なアプリケーション |
|運用| 取得、設定        |

|設定   |値    |
|----------|---------|
| Path      | ./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId        |
|データ型 | 文字列 - **Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe としてチームのアプリケーション パッケージ ID に文字列を設定します。チーム** |
|運用| 取得、設定        |

サーフェス ハブ デバイスを再起動します。 デバイスを再起動した後は、開始画面から、チームのアプリケーションを起動し、カレンダーから会議に参加することができます。

