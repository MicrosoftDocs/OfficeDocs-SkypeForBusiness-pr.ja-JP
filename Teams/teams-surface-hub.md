---
title: Surface Hub の Microsoft Teams を展開する
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 12/04/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: jatpatel
description: Surface Hub 用の Microsoft Teams の管理者設定を構成します。
localization_priority: Normal
search.appverid: MET150
ms.custom:
- Devices
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 70398d6718268742205181db3fd21bfc01886c0e
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36235043"
---
<a name="deploy-microsoft-teams-for-surface-hub"></a>Surface Hub の Microsoft Teams を展開する
======================================

Surface Hub の Teams をインストールする前に、次の操作を行ってください。

 □ハードウェア、オペレーティングシステム、その他の要件が満たされていることを確認します。 詳細については、「 [Microsoft Surface Hub 管理者ガイド](https://docs.microsoft.com/surface-hub/)」を参照してください。<br>
 □ Teams に必要なオペレーティングシステムの最小更新プログラムがインストールされていることを確認します。 [KB4343889](https://support.microsoft.com/help/4343889)。<br>
 □によって、Hub デバイスアカウントに Teams ライセンスが割り当てられます。<br>
 □ Skype for Business Online から移行している場合は、Teams ライセンスがユーザーに割り当てられていることを確認します。

## <a name="install-teams-for-surface-hub-from-the-microsoft-store"></a>Microsoft Store から Surface Hub の Teams をインストールする 

この手順では、Microsoft Store から Surface Hub の Teams をインストールする方法について説明します。 
 
1. Microsoft Store を起動します。<br>
   a. [ **** > **すべてのアプリ** > **設定**を開始] をタップします。<br> b. **[Surface Hub デバイスアカウント] の [管理] を**タップします。<br>
   c. 左側の [**アプリ & 機能**] タブをタップします。<br> d. 右側の [**ストアを開く**] ボタンをタップします。 
2. Microsoft Store で、 *Microsoft Teams*を検索します。 **Surface Hub 用の Microsoft Teams**が表示されます。 インストールするには、[**アプリの取得**] ボタンをタップします。  
3. インストールが完了したら、Surface Hub を再起動します。 

> [!NOTE]
> [ストア登録情報] ページから [**起動**] をタップしないでください。

## <a name="make-teams-the-default-calling-and-meetings-application"></a>チームを既定の通話と会議アプリケーションとして設定する
 
既定の通話と会議のアプリケーションポリシーを構成するには、次の2つのオプションがあります。 

- **オプション 1**: USB キーを使用して構成します。 
- **オプション 2**: Intune などの MDM 経由で構成する。
 
### <a name="option-1-configure-via-usb-key"></a>オプション 1: USB キーを使用して構成する 
 
パッケージはこの[ダウンロードページ](https://1drv.ms/f/s!ArcnbnREun0Vnp9Wps9MlWB-UJZw3g)で確認できます。 インストールを計画しているパッケージに適切なものを選び、USB キーにコピーします。 使用する正しい ppkg ファイルは、次のようにして適用する既定のアプリケーションポリシーによって異なります。 

|数値  |説明  |
|---------|---------|
|0     | スタート画面の Skype 優先アプリ、Teams 会議が利用可能        |
|1     | スタート画面の Teams 優先アプリ、Skype 会議が利用可能        |
|2     | スタート画面の Teams 排他アプリ (Skype アプリは利用できません)        |
 
1. USB キーを Surface Hub デバイスに接続します。 
2. Surface Hub デバイスで [**設定**] アプリを開きます。 
3. **Surface Hub デバイスアカウントの管理**を開きます。
4. [**デバイス管理**] を開きます。 
5. [**プロビジョニングパッケージの追加または削除] を**クリックします。 
6. [**パッケージの追加**] をクリックします。
7. ドロップダウンメニューから [**リムーバブルメディア**] オプションを選択します。 
8. 以前に USB キーにコピーした適切な<strong>Teamsrtmmode *. ppkg</strong>パッケージを追加します。 
9. Surface Hub デバイスを再起動します。 
10. デバイスを再起動すると、スタート画面から Teams アプリを起動して、予定表から会議に参加できるようになります。 

### <a name="option-2-configure-via-mdm-such-as-intune"></a>オプション 2: Intune などの MDM で構成する 

Intune で既定の通話と会議のアプリケーションポリシーを構成するには、次のようにします。 また、ブログをご覧になり、 [Intune を使って Microsoft Teams For Surface Hub アプリを展開](https://y0av.me/2018/07/16/deploy-the-microsoft-teams-for-surface-hub-app-using-intune/)してください。

|設定   |値    |説明    |
|----------|---------|---------|
|Path      | ./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode        |
|データ型 | integer (0-2)   |0-Skype 優先アプリをスタート画面に表示し、Teams 会議を利用できるようにする<br>1-チーム優先アプリスタート画面で Skype 会議が利用可能<br>2-スタート画面の Teams 排他アプリ (Skype アプリは利用できません) |
|操作| Get、Set        |

|設定   |値    |
|----------|---------|
|Path      | ./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId        |
|データ型 | string-MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe として Teams アプリケーションパッケージ ID に文字列を設定し**ます。Teams** |
|操作| Get、Set        |

Surface Hub デバイスを再起動します。 デバイスを再起動すると、スタート画面から Teams アプリを起動して、予定表から会議に参加できるようになります。

