---
title: Microsoft Teams のクライアントを取得する
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 07/05/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: vichau, majafry
localization_priority: Priority
description: Microsoft Teams で利用できる、Web、デスクトップ (Windows および Mac)、およびモバイル (Android、iOS、Windows Phone) などのさまざまなクライアントを使用する方法について説明します。
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 083e45097c7f2495bb73dc51a64d25202fafc13b
ms.sourcegitcommit: 247747ec19c0f5c1d45fea7e5ac5318e4d5127ea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/02/2018
ms.locfileid: "21708361"
---
<a name="get-clients-for-microsoft-teams"></a>Microsoft Teams のクライアントを取得する 
===========================

マイクロソフトのチームには、クライアント デスクトップ (Windows および Mac) は、web、およびモバイル (Android、iOS、および Windows Phone) があります。 これらのクライアントはすべてアクティブなインターネット接続が必要で、オフライン モードをサポートしていません。

<a name="desktop-client"></a>デスクトップ クライアント
--------------

マイクロソフト チームのデスクトップ クライアントは、スタンドアロン アプリケーションと現在の Office 365 用リソースの一部ではありません。 チームは、Windows (7 +)、32 ビットと 64 ビットの両方のバージョンと macOS (10.10 +) の両方に使用できます。 Windows で Teams を使用するには .NET Framework 4.5 以降が必要です。.NET Framework 4.5 以降がない場合は、Teams のインストーラーでインストールすることになります。 

デスクトップ クライアントは、チーム会議、グループ通話、およびプライベートな 1 対 1 での通話に対応するリアルタイム通信のサポート (オーディオ、ビデオ、およびコンテンツ共有) を提供します。

デスクトップ クライアントは、適切なローカルのアクセス許可を持っているエンド ユーザーによって、[https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754) から直接ダウンロードおよびインストールできます (管理者権限は、Teams クライアントを PC にインストールする場合には必要ありませんが、Mac では必要になります) 。

IT 管理者は、システム センター構成マネージャー (Windows) または Jamf Pro (macOS) など、組織内のコンピューターにインストール ファイルを配布するが推奨される方法を選択できます。 Windows ディストリビューションの MSI パッケージを取得するには、[マイクロソフト チームのインストールは、MSI を使用して](msi-deployment.md)参照してください。

> [!NOTE]
> これらのメカニズムによるクライアントの配布は、Microsoft Teams クライアントの初回インストール時にのみ利用でき、それ以降の更新では利用できません。

### <a name="windows"></a>Windows

Windows のマイクロソフトのチームのインストールには、32 ビットおよび 64 ビット アーキテクチャでは、ダウンロード可能なインストーラーが提供されます。

> [!NOTE]
> マイクロソフト チームのアーキテクチャ (32 ビットと 64 ビット) は、Windows とインストールされている Office のアーキテクチャに依存しません。

Windows クライアントは、ユーザーのプロファイルにある AppData フォルダーに展開されます。ユーザーのローカル プロファイルに展開すると、クライアントは管理者特権を必要とせずにインストール可能になります。Windows クライアントは次の場所にインストールされます。

- %appdata%\\local\\Microsoft\\Teams

- %appdata%\\roaming\\Microsoft\\Teams

ユーザーは、最初にマイクロソフトのチームのクライアントを使用して呼び出しを開始するとき、Windows ファイアウォールの設定で通信を許可するユーザーの入力を求める警告がわかります。 呼び出し機能しますが、警告を終了したときにもあるために、このメッセージを無視するようにユーザーを指示することがあります。

![[Windows セキュリティの重要な警告] ダイアログのスクリーンショット。](media/Get_clients_for_Microsoft_Teams_image3.png)

> [!NOTE]
> Windows ファイアウォール設定は、[キャンセル] の選択によりプロンプトが受け入れられなかった場合でも変更されます。TCP および UDP プロトコルの両方に関するブロック アクションで、teams.exe に関する2 つの着信ルールが作成されます。

### <a name="mac"></a>Mac

Mac ユーザーは、macOS のコンピューターでパッケージのインストール ファイルを使用してチームをインストールできます。 Mac クライアントをインストールするには管理アクセスが必要です。 /Applications フォルダーには、macOS クライアントがインストールされています。

#### <a name="install-teams-by-using-the-pkg-file"></a>PKG ファイルを使用してチームをインストールします。

1. [チームがページをダウンロード](https://teams.microsoft.com/downloads)するから**Mac**では、下の [**ダウンロード**] をクリックします。
2. PKG ファイルをダブルクリックします。
3. インストールを完了するのにはインストール ウィザードに従います。
4. チームは、/Applications フォルダーにインストールされます。 コンピューター全体にインストールすることをお勧めします。

> [!NOTE]
> 、インストール中に、PKG は、管理者の資格情報を求められます。 ユーザーは、ユーザーが管理者かどうかに関係なく、管理者の資格情報を入力する必要があります。

ユーザー現在チームの攻撃力のインストールには、パッケージのインストールを交換したい場合、ユーザーする必要があります。

1. チームのアプリケーションを終了します。
2. チームのアプリケーションをアンインストールします。
3. PKG ファイルをインストールします。

IT 管理者は、Jamf Pro など、組織内のすべての Mac にインストール ファイルを配布するのには、チームの管理された展開を使用できます。

> [!NOTE]
> パッケージのインストールで問題が発生する場合お知らせします。 この資料の最後にある [**フィードバック**] セクションでは、**製品に関するフィードバック**をクリックします。

<a name="web-client"></a>Web クライアント 
----------

Web クライアント ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) は、さまざまなブラウザーから使用できる、完全な機能クライアントです。 Web クライアントは WebRTC を使用することによって通話と会議をサポートするため、Web ブラウザーで Teams を実行するためのプラグインやダウンロードの必要がありません。 ブラウザーはサードパーティの Cookie を許可するように設定する必要があります。 

[!INCLUDE [browser-support](includes/browser-support.md)]

Web クライアントへの接続時にブラウザーのバージョンの検出を実行する[https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)。 サポートされていないブラウザーのバージョンが検出された場合、web インタ フェースへのアクセスをブロックし、ユーザーがデスクトップ クライアントまたはモバイル アプリケーションをダウンロードすることをお勧めです。

<a name="mobile-clients"></a>モバイル クライアント
--------------

Microsoft Teams のモバイル アプリは Android、iOS、および Windows Phone で利用でき、チャットベースの会話に参加している外出中のユーザーを対象としており、ピアツーピアの音声通話が使用できます。モバイル アプリについては、Google Play、Apple App Store、および Microsoft Store の関連するモバイル ストアにアクセスしてください。

Microsoft Teams モバイル アプリのサポートされるモバイル プラットフォームは次のとおりです。

-   **Android**: 4.4 以降

-   **iOS**: 10.0 以降

-   **Windows Phone**: Windows 10 Mobile

> [!NOTE]
> モバイル版は、チームが正常に機能するために一般に公開する必要があります。

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
