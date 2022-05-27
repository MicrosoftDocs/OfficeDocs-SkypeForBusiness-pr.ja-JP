---
title: Teams Room デバイスをマネージド サービスに登録する
author: donnah007
ms.author: v-donnahill
manager: serdars
ms.reviewer: ''
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Teams Rooms デバイスをマネージド サービスにオンボードする
f1keywords: ''
ms.openlocfilehash: d40daed54a04ca7d9949ecc63f57c379aee6b666
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675789"
---
# <a name="enroll-device-into-managed-service"></a>デバイスをマネージド サービスに登録する

展開では、Microsoft Teams Roomsマネージド サービスにMicrosoft Teams Roomsデバイスをオンボードする必要があります。 監視サービス エージェントは、認定された Microsoft Teams Room (MRT) システムおよび周辺機器で使用します。

## <a name="prerequisites"></a>前提条件

登録プロセスを試行する前に、次の手順に従ってハードウェアを設定します。

### <a name="adding-proxy-settings-optional"></a>プロキシ設定の追加 (省略可能)

1. 管理者としてログインするには、[次の操作を実行して、MRT デバイスの管理 ユーザーとして実行します](#performing-operations-as-the-admin-user-of-the-mtr-device)。
1. Windows ***Search** _ フィールド (画面の左下セクション) に「_ *cmd**」と入力します (画面を長押しするか、右クリックして管理者 **_として実行_** を選択します)。
1. 次のコマンドを実行します (コマンドの最後の二重引用符は重要です)。

   - 単一 ***プロキシ サーバー*** を使用している場合: `bitsadmin /Util /SetIEProxy LOCALSYSTEM MANUAL_PROXY <proxyserver>:<port> ""`

     *例：*

     ```DOS
     bitsadmin /Util /SetIEProxy LOCALSYSTEM MANUAL_PROXY contosoproxy.corp.net:8080 ""
     ```

   - ***pac*** ファイルを使用している場合:`bitsadmin /Util /SetIEProxy LOCALSYSTEM AUTOSCRIPT <pac file url>`

     *例：*

     ```DOS
     bitsadmin /Util /SetIEProxy LOCALSYSTEM AUTOSCRIPT `http://contosoproxy.corp.net/proxy.pac`
     ```

### <a name="enabling-tpm-settings"></a>TPM 設定を有効にする

> [!NOTE]
> マネージド サービスに登録するには、TPM を有効にする必要があります。

Intel NUC デバイスの TPM が無効になっている場合は、次のようにこれらのデバイスで TPM を有効にします。

1. キーボードを NUC デバイスに接続します。
1. デバイスを再起動します。
1. BIOS 画面を表示するには、 **F2** キーを素早く押します。
1. [ **詳細設定] を選択します**。
1. [ **セキュリティ**] を選択します。
1. [セキュリティ機能] の右側で、 **Intel Platform Trust Technology** を有効にします。
1. 設定を保存するには、 **F10** キーを押します。
1. 確認ボックスで、[ **はい**] を選択します。

## <a name="performing-operations-as-the-admin-user-of-the-mtr-device"></a>MRT デバイスの管理 ユーザーとして操作を実行する

一部の構成/インストール手順では、管理者としてデバイスにログインする必要があります。

デバイスに管理者 (ローカル管理者) としてログインするには:

1. 進行中の通話をハングアップし、ホーム画面に戻っていることを確認します。
1. Microsoft Teams Room ユーザー インターフェイスで **[その他**] を選択し、**設定** を選択します。ここで、デバイスのローカル管理者パスワード (既定のパスワードは **_sfb_**) の入力を求められます。
1. **設定** を選択し、**Windows 設定** を選択してローカル管理者としてWindowsにアクセスします。

1. Windowsログイン画面に表示されるユーザーの一覧から、[**管理者**] (またはデバイスのそれぞれのローカル管理者) を選択します。

> [!NOTE]
> コンピューターが *ドメインに参加している* 場合は、[ **その他のユーザー**] を選択し、 **.\admin**、またはデバイスで構成されているローカル管理者のユーザー名をユーザー名として使用します。

必要な管理タスクを実行した後、Microsoft Teams Room アプリに戻るには:

1. Windows ***スタート メニュー*** から、管理 アカウントからサインアウトします。
1. 画面の左端にあるユーザー アカウント アイコンを選択し、**Skype** を選択して、Microsoft Teams Room に戻ります。

> [!NOTE]
> Skype ユーザーが一覧にない場合は、[その他のユーザー] を選択し、ユーザー名として ***「.\skype***」と入力してサインインします。

## <a name="urls-required-for-communication"></a>通信に必要な URL

 > [!NOTE]
 > MRT デバイス エージェントと Microsoft Teams Rooms - マネージド サービス サービス ポータル間のすべてのネットワーク トラフィックは、ポート 443 経由の SSL です *。*  [OFFICE 365 URL と IP アドレス範囲 - Microsoft 365 Enterprise |Microsoft Docs](/microsoft-365/enterprise/urls-and-ip-address-ranges?view=o365-worldwide&preserve-view=true)。

エンタープライズ環境内で **トラフィック 許可リスト** が有効になっている場合は、次のホストを許可する必要があります。

agent.rooms.microsoft.com<br>
global.azure-devices-provisioning.net<br>
gj3ftstorage.blob.core.windows.net<br>
mmrstgnoamiot.azure-devices.net<br>
mmrstgnoamstor.blob.core.windows.net<br>
mmrprodapaciot.azure-devices.net<br>
mmrprodapacstor.blob.core.windows.net<br>
mmrprodemeaiot.azure-devices.net<br>
mmrprodemeastor.blob.core.windows.net<br>
mmrprodnoamiot.azure-devices.net<br>
mmrprodnoamstor.blob.core.windows.net

## <a name="enrollment-process"></a>登録プロセス

登録プロセスには、次の手順が含まれます。

1. Microsoft Teams Rooms – Managed Services ポータル [http://portal.rooms.microsoft.com](https://portal.rooms.microsoft.com/)の左側のナビゲーション バーで **、設定** 展開して [**全般**] を選択します。
1. [ *ルームの登録] で* [ **インストーラーのダウンロード**  ] を選択し、監視エージェント ソフトウェアをダウンロードします。
1. **オプション：** エージェントのプロキシ設定を設定します。 [プロキシ設定の追加 (省略可能)に関する](#adding-proxy-settings-optional)セクションを参照してください。
1. (手順 2 でダウンロードした) エージェント インストーラーを、MRT デバイス上で MSI をローカルで実行するか、通常の方法で MSI アプリケーションを環境内のデバイスに大量に発行することによって (グループ ポリシーなど)
1. ポータルに 5 分から 10 分以内に部屋が表示されます。 そうでない場合は、managedroomsupport@microsoft.com にお問い合わせください。

   ![設定と自己登録キーのスクリーンショット。](../media/software-installation-005new.png)

> [!NOTE]
> TEAMS アプリなしでエージェントをインストールして、TEAMSにログインできる場合は、オプションのプロセスとして登録キーを使用できます。 [?] に移動します。 (ヘルプ) ポータルの右上隅にある [ダウンロード キー (省略可能)] を選択します。 エージェントをインストールするときは、デバイスの **C:\Rigel** ディレクトリに "自己登録キー" (以前にポータルからダウンロードした) を配置します。

## <a name="installation"></a>インストール

Microsoft からインストーラーを (ポータルから、または上記の AKA.ms URL を使用して) ダウンロードした後、その内容を解凍してファイル **ManagedRoomsInstaller.msi** にアクセスします。

インストールには、1) 個々のローカル コンピューターのインストールと 2) 一括展開モード (通常は同様の方法のグループ ポリシーを使用) の 2 つのモードがあります。 ドメインに参加していないマシンや、MSI インストーラーをリモートで実行できないマシンには個別にインストールすることをお勧めします。

このドキュメントでは、お客様が一括展開モードで MSI アプリケーションを実行できるさまざまな方法があるため、個々のモードでのインストールのみを説明します。

## <a name="individual-devicemdashdomain-joined-walkthrough"></a>個々のデバイス&mdash;ドメインに参加しているチュートリアル

1. 管理者としてデバイスにログインします。 デバイスの手順の *管理ユーザーとして実行操作が* 実行されていることを確認します。

1. ファイル **ManagedRoomsInstaller.msi** を MRT デバイスにコピーします。

   ***ManagedRoomsInstaller.msi*** を実行すると、[使用許諾契約書] 画面が表示されます。

1. 契約を読んだ後、*[使用許諾契約書] **の条項に同意** し、_*Install** キーを押します。

    これにより、マネージド サービス監視ソフトウェアのインストールMicrosoft Teams Roomsが開始されます。 昇格のプロンプト (管理者として実行) が表示されます。

1. **[はい**] を選択します。

    インストールは続行されます。 インストール手順中に、コンソール ウィンドウが開き、Microsoft Teams Roomsの最終段階である Managed Services 監視ソフトウェアのインストールが開始されます。

    > [!NOTE]
    > ウィンドウを閉じないでください。 インストールが完了すると、ウィザードに [完了] ボタンが表示されます。

## <a name="completing-enrollment"></a>登録の完了

インストールが完了したら、5 ~ 10 分待ってポータルを更新すると、デバイスが一覧表示され、 *オンボード* 状態として報告されます。

*オンボーディング* 状態では、会議室の状態が表示および更新されますが、アラートが発生したり、調査チケットが作成されたりすることはありません。

ルームを選択し、[ **登録]**  を選択してインシデント アラートの取得、調査チケットの取得、またはインシデントの報告を開始します。

質問や問題については、ポータルで顧客から報告されたインシデントを開くか、managedroomsupport@microsoft.com にお問い合わせください。

### <a name="unenrolling-and-uninstalling-monitoring-software"></a>監視ソフトウェアの登録解除とアンインストール

デバイスの登録を解除するには、次のように監視エージェントを MRT デバイスから削除します。

1. 監視対象のデバイスで、管理者としてデバイスにログインします。 *デバイスの管理ユーザーとして操作を実行する* 手順に従ってください。
1. aka.ms/MTRPDeviceOffBoarding からリセット スクリプト [をダウンロードします](https://aka.ms/MTRPDeviceOffBoarding)。
1. デバイス上のどこかにスクリプトを抽出し、パスをコピーします。
1. PowerShell を管理者として開く: Windows ***Search** _ フィールド (画面の左下セクション) で、「Powershell」と入力し、_*_[Windows PowerShell_**] を右クリックします。
1. *[管理者として実行]* を選択し、UAC プロンプトに同意します。
1. *Set-ExecutionPolicy –ExecutionPolicy RemoteSigned* と入力し、次のプロンプトで **Y** キーを押します。
1. 解凍したオフボード スクリプトの完全なパスを PowerShell ウィンドウに貼り付けるか入力し、Enter キーを押 **します**。

   例: 

   ```powershell
   C:\Users\admin\Downloads\MTRP\_Device\_Offboarding\MTRP\_Device\_Offboarding.ps1
   ```

   このコマンドは、デバイスをユーザー標準の MRT 更新プログラムにリセットし、MRTP 監視エージェントとファイルを削除します。

1. Microsoft Teams Rooms – マネージド サービス ポータルの左側のメニューで、[会議室] を選択 **します**。
1. 指定された会議室の一覧で、登録を解除するルームを選択し、[ **登録解除** ] を選択してインシデント アラートや調査チケットの取得を停止するか、ルームのインシデントを報告します。

## <a name="troubleshooting-table"></a>トラブルシューティング の表

> [!NOTE]
> すべてのMicrosoft Teams Rooms – マネージド サービス監視エラーは、**Microsoft Managed Rooms** という名前の特定のイベント ログ ファイルに記録されます。

***アプリケーション ランタイム ログ ファイルの場所*** =

C:\Windows\ServiceProfiles\LocalService\AppData\Local\ServicePortalAgent\ app-x.x.x\ServicePortalAgent\ServicePortal\_Verbose\_ **LogFile.log(x.x.x** はアプリ のバージョン番号です)。

|症状|推奨される手順|
|---|---|
|次のようなエラー メッセージが表示されます。 </p><p> ***エラー: このアプリケーションを_ で実行してください** <br> _ *_管理者特権_**|エスカレーションされた特権でアプリケーションを実行し、もう一度やり直してください。|
|||
|次のようなエラー メッセージが表示されます。 </p><p> ***TPM データが見つかりません***|デバイスの BIOS で TPM (トラステッド プラットフォーム モジュール) がオンになっていることを確認します。 これは通常、デバイス BIOS のセキュリティ設定にあります。|
|||
|エラー メッセージが表示されます。 </p><p> ***エラー: '管理' または 'Skype' という名前のローカル ユーザー アカウントが見つかりません***|認定された Microsoft Teams Room システム デバイスにユーザー アカウントが存在することを確認します。|
|||
|上記で説明していないエラー状態メッセージが表示されます。|インストール ログのコピーをMicrosoft Teamsシステム サポート エージェントに提供してください。|
