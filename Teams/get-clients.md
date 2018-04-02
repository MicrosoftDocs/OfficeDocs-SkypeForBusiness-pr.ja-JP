---
title: Microsoft Teams のクライアントを取得する
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/27/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: ninadara
localization_priority: Normal
description: Microsoft Teams で利用できる、Web、デスクトップ (Windows および Mac)、およびモバイル (Android、iOS、Windows Phone) などのさまざまなクライアントを使用する方法について説明します。
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 61bfc43321433a06eba8196b732f8f12dded0d8d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
<a name="get-clients-for-microsoft-teams"></a>Microsoft Teams のクライアントを取得する 
===========================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

Microsoft Teams には、Web、デスクトップ (Windows および Mac)、およびモバイル (Android、iOS、Windows Phone) で利用できるクライアントがあります。これらのクライアントはすべてアクティブなインターネット接続が必要で、オフライン モードをサポートしていません。

<a name="web-client"></a>Web クライアント 
----------

Web クライアント ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) は、完全な機能のクライアントで、さまざまなブラウザーから使用することができます。 Web クライアントでは、プラグインがあるため、webRTC または web ブラウザーでのチームを実行するために必要なダウンロードを使用して通話や会議をサポートします。 ブラウザーを構成して、サード パーティの cookie を許可する必要があります。 

[!INCLUDE [browser-support](includes/browser-support.md)]

Web クライアントへの接続時にブラウザーのバージョンの検出を実行する[https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)、サポートされていないブラウザーのバージョンが検出された場合、web インターフェイスへのアクセスをブロックし、ユーザーがデスクトップ クライアントまたはモバイル アプリケーションをダウンロードすることをお勧めしています。

<a name="desktop-client"></a>デスクトップ クライアント
--------------

マイクロソフト チームのデスクトップ クライアントは、スタンドアロン アプリケーションと現在の Office Pro との一部ではありません。 チームは、Windows (7 +)、32 ビットと 64 ビットの両方のバージョンと MacOS (10.10 +) の両方に使用できます。 Windows では、.NET framework 4.5 以降のチームする必要があります。チームのインストーラーは、インストールすることがない場合に提供されます。 

デスクトップのクライアントでは、チーム ミーティング、グループの呼び出し、およびプライベート 1 対 1 の呼び出しのリアルタイム通信のサポート (オーディオ、ビデオ、およびコンテンツの共有) を提供します。

デスクトップ クライアントをダウンロードしてから直接のエンド ・ ユーザーによってインストールされている[https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754)、適切なローカルのアクセス許可 (管理者権限は、PC 上でチームのクライアントをインストールする必要はありませんが、Mac のために必要な) があります。

IT 管理者は好みの方法で、System Center Configuration Manager (Windows)、Casper Suite (MacOS) のような組織内のコンピューターにインストール ファイルを配布できます。 Windows 用の MSI パッケージの配布を取得するには、[マイクロソフト チームのインストールは、MSI を使用して](msi-deployment.md)参照してください。

> [!NOTE]
> これらのメカニズムによるクライアントの配布は、Microsoft Teams クライアントの初回インストール時にのみ利用でき、それ以降の更新では利用できません。


#### <a name="windows"></a>Windows

Windows 用のMicrosoft Teams インストールでは、32 ビットおよび 64 ビット アーキテクチャでダウンロード可能なインストーラーを提供しています。そのアーキテクチャは、オンライン ダウンロードで既定として提示される OS のアーキテクチャと一致する必要があります。



> [!NOTE]
> Microsoft Teams のアーキテクチャ (32 ビットと 64 ビット) はインストールされている Office のアーキテクチャに依存しません。

Windows クライアントは、ユーザーのプロファイルにある AppData フォルダーに展開されます。ユーザーのローカル プロファイルに展開すると、クライアントは管理者特権を必要とせずにインストール可能になります。Windows クライアントは次の場所にインストールされます。

-   %appdata%\\local\\Microsoft\\Teams

-   %appdata%\\roaming\\Microsoft\\Teams

ユーザーが Microsoft Teams クライアントを使用して初めて通話を開始すると、ユーザーに通信の許可を求める Windows ファイアウォール設定に関する警告が通知される場合があります。警告を受け入れなくても通話は機能するため、このメッセージを無視するように指示される場合があります。

![[Windows セキュリティの重要な警告] ダイアログのスクリーンショット。](media/Get_clients_for_Microsoft_Teams_image3.png)


> [!NOTE]
> Windows ファイアウォール設定は、[キャンセル] の選択によりプロンプトが受け入れられなかった場合でも変更されます。TCP および UDP プロトコルの両方に関するブロック アクションで、teams.exe に関する2 つの着信ルールが作成されます。

#### <a name="mac"></a>Mac

Microsoft は Mac OSX コンピュータ用の DMG インストール ファイルも提供しています。 Mac クライアントをインストールするには管理アクセスが必要です。 Mac OSX クライアントは /Applications フォルダーにインストールされます。


<a name="mobile-clients"></a>モバイル クライアント
--------------

Microsoft Teams のモバイル アプリは Android、iOS、および Windows Phone で利用でき、チャットベースの会話に参加している外出中のユーザーを対象としており、ピアツーピアの音声通話が使用できます。モバイル アプリについては、Google Play、Apple App Store、および Microsoft Store の関連するモバイル ストアにアクセスしてください。

Microsoft Teams モバイル アプリのサポートされるモバイル プラットフォームは次のとおりです。

-   **Android**: 4.4 以降

-   **iOS**: 10.0 以降

-   **Windows Phone**: Windows 10 Mobile

モバイル アプリはそれぞれのモバイル プラットフォームのアプリ ストアからのみ配布および更新され、MDM (モバイル デバイス管理) ソリューションまたはサイド ロードからは配布することはできません。


| | | |
|---------|---------|---------|
|![判断ポイント アイコン。](media/Get_clients_for_Microsoft_Teams_image4.png)      |判断ポイント         |ユーザーが適切な Microsoft Teams クライアントをデバイスにインストールすることを妨げる制限事項はありますか?         |
|![次のステップ アイコン。](media/Get_clients_for_Microsoft_Teams_image5.png)     |次のステップ         |組織によってソフトウェアのインストールが制限されている場合、処理が Microsoft Teams に対応していることを確認してください。注意: 管理者権限は、PC クライアント インストールでは必要ありませんが、Mac へのインストールでは必要になります。         |


  <span id="_Hlk477176062" class="anchor"></span>  判断ポイント   ユーザーが適切な Microsoft Teams クライアントをデバイスにインストールすることを妨げる制限事項はありますか?

<a name="client-update-management"></a>クライアントの更新管理
------------------------

クライアントは現在、IT 管理者の介入を必要とせずに Microsoft Teams サービスによって自動的に更新されています。利用可能な更新がある場合、クライアントは自動的にその更新をダウンロードします。アプリが一定時間アイドル状態となった場合には更新処理が開始されます。

<a name="client-side-configurations"></a>クライアント側の設定
---------------------------

現在、テナント管理者、PowerShell、グループ ポリシー オブジェクトまたはレジストリのいずれかを介してクライアントを設定するオプションはサポートされていません。

<a name="notification-settings"></a>通知設定
----------------------------

現在、IT 管理者がクライアント側の通知設定を設定するオプションはありません。通知オプションはすべてユーザーによって設定されます。次の図に、既定のクライアント設定の概要を示します。

![通知設定のスクリーンショット。](media/Get_clients_for_Microsoft_Teams_image6.png)
