---
title: "Microsoft Teams のクライアントを取得する | Microsoft サポート"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Microsoft Teams で利用できる、Web、デスクトップ (Windows および Mac)、およびモバイル (Android、iOS、Windows Phone) などのさまざまなクライアントを使用する方法について説明します。"
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: f555208aba849b77d648e5e9561d0daf3ba199b3
ms.sourcegitcommit: e8b96ddf6a6eaea4598b116f1e33c71911b337bb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/08/2017
---
<a name="get-clients-for-microsoft-teams"></a>Microsoft Teams のクライアントを取得する 
===========================

Microsoft Teams には、Web、デスクトップ (Windows および Mac)、およびモバイル (Android、iOS、Windows Phone) で利用できるクライアントがあります。これらのクライアントはすべてアクティブなインターネット接続が必要で、オフライン モードをサポートしていません。

<a name="web-client"></a>Web クライアント 
----------------

Web クライアント ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) は、さまざまなブラウザーから使用できる、完全な機能クライアントです。 現時点では、リアルタイム通信 (会議への参加、1 対 1 の通話) をサポートしている Web クライアントは Microsoft Edge のみです。 また、ブラウザーはサードパーティの Cookie を許可するように設定する必要があります。

Web ブラウザーで Microsoft Teams を利用するために必要となるプラグインやダウンロードはありません。

Web クライアントは、[https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753) への接続時にブラウザー バージョンの検出を実行します。サポートされていないブラウザー バージョンを検出した場合、Web インターフェイスへのアクセスをブロックし、ユーザーによるデスクトップ クライアントまたはモバイル アプリのダウンロードを推奨します。

Microsoft Teams は、次のブラウザーおよびバージョンをサポートしています。

-   **Microsoft Edge**: 12 以上

-   **Internet Explorer:** 11 以上

-   **Chrome**: 51.0 以上

-   **Firefox**: 47.0 以上


| | |
|---------|---------|
|![重要アイコン。](media/Get_clients_for_Microsoft_Teams_image1.png)<br></br>重要     |Safari はまだサポートされていませんが、まもなく対応します。         |

<a name="desktop-clients"></a>デスクトップ クライアント
------------------------

Microsoft Teams デスクトップ クライアントはスタンドアロン アプリケーションであり、現在は Office Pro Plus の一部ではありません。Microsoft Teams は、32 ビットおよび 64 ビット バージョンの Windows (7 以上)、および MacOS (10.10 以上) で利用できます。

デスクトップ クライアントは、チーム会議、グループ通話、およびプライベートな 1 対 1 での通話に対応するリアルタイム通信のサポート (オーディオ、ビデオ、およびコンテンツ共有) を提供します。

デスクトップ クライアントは、適切なローカルのアクセス許可を持っているエンド ユーザーによって、[https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754) から直接ダウンロードおよびインストールできます (管理者権限は、Teams クライアントを PC にインストールする場合には必要ありませんが、Mac では必要になります) 。

IT 管理者は好みの方法で、System Center Configuration Manager (Windows)、Casper Suite (MacOS) のような組織内のコンピューターにインストール ファイルを配布できます。


| | |
|---------|---------|
|![注意アイコン。](media/Get_clients_for_Microsoft_Teams_image2.png)<br></br>注意    |これらのメカニズムによるクライアントの配布は、Microsoft Teams クライアントの初回インストール時にのみ利用でき、それ以降の更新では利用できません。         |

#### <a name="windows"></a>Windows

Windows 用のMicrosoft Teams インストールでは、32 ビットおよび 64 ビット アーキテクチャでダウンロード可能なインストーラーを提供しています。そのアーキテクチャは、オンライン ダウンロードで既定として提示される OS のアーキテクチャと一致する必要があります。

| | |
|---------|---------|
|![注意アイコン。](media/Get_clients_for_Microsoft_Teams_image2.png)<br></br>注意    |Microsoft Teams のアーキテクチャ (32 ビットと 64 ビット) はインストールされている Office のアーキテクチャに依存しません。        |

Windows クライアントは、ユーザーのプロファイルにある AppData フォルダーに展開されます。ユーザーのローカル プロファイルに展開すると、クライアントは管理者特権を必要とせずにインストール可能になります。Windows クライアントは次の場所にインストールされます。

-   %appdata%\\local\\Microsoft\\Teams

-   %appdata%\\roaming\\Microsoft\\Teams

ユーザーが Microsoft Teams クライアントを使用して初めて通話を開始すると、ユーザーに通信の許可を求める Windows ファイアウォール設定に関する警告が通知される場合があります。警告を受け入れなくても通話は機能するため、このメッセージを無視するように指示される場合があります。

![[Windows セキュリティの重要な警告] ダイアログのスクリーンショット。](media/Get_clients_for_Microsoft_Teams_image3.png)

| | |
|---------|---------|
|![注意アイコン。](media/Get_clients_for_Microsoft_Teams_image2.png)<br></br>注意    |Windows ファイアウォール設定は、[キャンセル] の選択によりプロンプトが受け入れられなかった場合でも変更されます。TCP および UDP プロトコルの両方に関するブロック アクションで、teams.exe に関する2 つの着信ルールが作成されます。        |

#### <a name="mac"></a>Mac

Microsoft は Mac OSX コンピューター用の DMG インストール ファイルも提供しています。Mac クライアントのインストールには管理アクセスが必要です。Mac OSX クライアントは次の場所にインストールされます。

\~/Library/Application Support/Microsoft/Teams

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
