---
title: Microsoft Teams for Surface Hub を展開する
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 12/04/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: jatpatel
description: Microsoft Teams for Surface Hub の管理者設定を構成します。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Devices
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5634c4ac5e5955d099555cce4f74b57a527662e9
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836937"
---
<a name="deploy-microsoft-teams-for-surface-hub"></a>Microsoft Teams for Surface Hub を展開する
======================================

Teams for Surface Hub をインストールする前に、次の操作を行います。

 □ ハードウェア、オペレーティング システム、その他の要件を満たしていることを確認する。 詳細については、[Microsoft Surface Hub の管理者ガイド](https://docs.microsoft.com/surface-hub/)を参照してください。<br>
 □ Teams に必要な最小オペレーティング システムの更新プログラムがインストールされていることを確認する - [KB4343889](https://support.microsoft.com/help/4343889)。<br>
 □ Teams ライセンスを Hub デバイス アカウントに割り当てる。<br>
 □ Skype for Business Online から移行している場合は、Teams ライセンスがユーザーに割り当てられていることを確認する。

## <a name="install-teams-for-surface-hub-from-the-microsoft-store"></a>Microsoft Store から Teams for Surface Hub をインストールする 

Microsoft Store から Teams for Surface Hub をインストールする手順を以下に示します。 
 
1. Microsoft Store を開始します。<br>
   a. **[スタート]** > **[すべてのアプリ]** > **[設定]** をタップします。<br> b. **[Surface Hub Device account, management]** (Surface Hub デバイス アカウント、管理) をタップします。<br>
   c. 左側にある **[アプリと機能]** タブをタップします。<br> d. 右側にある **[ストアを開く]** ボタンをタップします。 
2. Microsoft Store で、*[Microsoft Teams]* を検索します。 **[Microsoft Teams for Surface Hub]** が表示されます。 **[アプリを入手]** ボタンをタップしてインストールします。  
3. インストールが完了したら、Surface Hub を再起動します。 

> [!NOTE]
> Store 登録情報ページからは **[起動]** をタップしないでください。

## <a name="make-teams-the-default-calling-and-meetings-application"></a>Teams を既定の通話と会議のアプリケーションにする
 
既定の通話と会議のアプリケーション ポリシーを構成するには、次の 2 つのオプションがあります。 

- **オプション 1**: USB キーを使用して構成する。 
- **オプション 2**: MDM (Intune など) を使用して構成する。
 
### <a name="option-1-configure-via-usb-key"></a>オプション 1: USB キーを使用して構成する 
 
パッケージは、この[ダウンロード ページ](https://1drv.ms/f/s!ArcnbnREun0Vnp9Wps9MlWB-UJZw3g)にあります。 インストールを計画しているパッケージに適したものを選択し、USB キーにコピーします。 使用できる正しい .ppkg ファイルは、次に示すとおり、適用する既定のアプリケーション ポリシーによって異なります。 

|数値  |説明  |
|---------|---------|
|0     | スタート画面で Skype が優先アプリ、Teams 会議が利用可能        |
|1     | スタート画面で Teams が優先アプリ、Skype 会議が利用可能        |
|2     | スタート画面で Teams が独占的アプリ (Skype アプリは利用不可)        |
 
1. Surface Hub デバイスに USB キーを接続します。 
2. Surface Hub デバイスで **[設定] **アプリを開きます。 
3. **[Surface Hub Device Account Management]** (Surface Hub デバイス アカウントの管理) を開きます。
4. **[デバイスの管理]** を開きます。 
5. **[プロビジョニング パッケージを追加または削除する]** をクリックします。 
6. **[パッケージの追加]** をクリックします。
7. ドロップダウン メニューから **[リムーバブル メディア]** オプションを選択します。 
8. 既に USB キーにコピーした適切な <strong>TeamsRTMMode*.ppkg</strong> パッケージを追加します。 
9. Surface Hub デバイスを再起動します。 
10. デバイスが再起動したら、スタート画面から Teams アプリを起動し、予定表から会議に参加できます。 

### <a name="option-2-configure-via-mdm-such-as-intune"></a>オプション 2: MDM (Intune など) を使用して構成する 

以下の情報を使用し、Intune を介して既定の通話と会議のアプリケーション ポリシーを構成します。 ブログ「[Intune を使用して Microsoft Teams for Surface Hub アプリを展開する](https://y0av.me/2018/07/16/deploy-the-microsoft-teams-for-surface-hub-app-using-intune/)」も参照してください。

|設定   |値    |説明    |
|----------|---------|---------|
|パス      | ./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode        |
|データ型 | 整数 (0 ～ 2)   |0 - スタート画面で Skype が優先アプリ、Teams 会議が利用可能<br>1 - スタート画面で Teams が優先アプリ、Skype 会議が利用可能<br>2 - スタート画面で Teams が独占的アプリ (Skype アプリは利用不可) |
|操作| Get、Set        |

|設定   |値    |
|----------|---------|
|パス      | ./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId        |
|データ型 | 文字列 - 文字列を **Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe!Teams** として Teams アプリケーション パッケージ ID に設定します |
|操作| Get、Set        |

Surface Hub デバイスを再起動します。 デバイスが再起動したら、スタート画面から Teams アプリを起動し、予定表から会議に参加できます。

