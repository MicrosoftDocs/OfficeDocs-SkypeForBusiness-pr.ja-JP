---
title: Teams Room デバイスを Pro Management に登録する
author: altsou
ms.author: altsou
manager: serdars
ms.date: 09/28/2022
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_MTRP
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Pro Management ポータルへのデバイスTeams Roomsオンボード
f1keywords: ''
ms.openlocfilehash: f5994c5ced6097104ee74044ee2441bc8388f5c3
ms.sourcegitcommit: aa398950cc2f10b268c72a2b25caa0cf893e8230
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/08/2022
ms.locfileid: "69307962"
---
# <a name="enroll-device-into-pro-management"></a>Pro Management にデバイスを登録する

デプロイでは、Microsoft Teams Rooms Pro管理ポータルにデバイスMicrosoft Teams Roomsオンボードする必要があります。 監視サービス エージェントは、認定されたMicrosoft Teams Room (MTR) システムと周辺機器で使用します。

## <a name="prerequisites"></a>前提条件

登録プロセスを試みる前に、次の手順に従ってハードウェアを設定します。

### <a name="adding-proxy-settings-optional"></a>プロキシ設定の追加 (省略可能)

1. [MTR デバイスの管理 ユーザーとして操作を実行するに](#performing-operations-as-the-admin-user-of-the-mtr-device)従って、管理者としてログインします。
1. Windows ***Search** _ フィールド (画面の左下セクション) に「_ *cmd** 」と入力します (画面を長押しするか右選択し、[ **_管理者として実行_**] を選択します)。
1. 次のコマンドを実行します (コマンドの最後に二重引用符が重要です)。

   - 単一 ***プロキシ サーバー*** を使用している場合: `bitsadmin /Util /SetIEProxy LOCALSYSTEM MANUAL_PROXY <proxyserver>:<port> ""`

     *例：*

     ```DOS
     bitsadmin /Util /SetIEProxy LOCALSYSTEM MANUAL_PROXY contosoproxy.corp.net:8080 ""
     ```

   - ***pac*** ファイルを使用している場合:`bitsadmin /Util /SetIEProxy LOCALSYSTEM AUTOSCRIPT <pac file url>`

     *例：*

     ```DOS
     bitsadmin /Util /SetIEProxy LOCALSYSTEM AUTOSCRIPT http://contosoproxy.corp.net/proxy.pac
     ```

### <a name="enabling-tpm-settings"></a>TPM 設定の有効化

> [!NOTE]
> Pro Management に登録するには、TPM を有効にする必要があります。

Intel NUC デバイスの TPM が無効になっている場合は、次のようにこれらのデバイスで TPM を有効にします。

1. キーボードを NUC デバイスに接続します。
1. デバイスを再起動します。
1. BIOS 画面を表示するには、 **F2** キーを押します。
1. [ **詳細設定] を選択します**。
1. [ **セキュリティ**] を選択します。
1. [セキュリティ機能] の右側で、 **Intel Platform Trust Technology** を有効にします。
1. 設定を保存するには、 **F10** キーを押します。
1. 確認ボックスで、[ **はい**] を選択します。

## <a name="performing-operations-as-the-admin-user-of-the-mtr-device"></a>MTR デバイスの管理 ユーザーとしての操作の実行

一部の構成/インストール手順では、管理者としてデバイスにログインする必要があります。

管理者 (ローカル管理者) としてデバイスにログインするには:

1. 進行中の通話をハングアップし、ホーム画面に戻ります。
1. Microsoft Teams Room ユーザー インターフェイスで、[**その他**] を選択し、[**設定]** を選択します。ここで、デバイスのローカル管理者パスワード (既定のパスワードは **_sfb_**) の入力を求められます。
1. [ **設定]** を選択し、[  **Windows の設定]**  を選択して、ローカル管理者として Windows にアクセスします。

1. Windows ログイン画面に表示されるユーザーの一覧から、[  **管理者** ] (またはデバイスのそれぞれのローカル管理者) を選択します。

> [!NOTE]
> コンピューターが *ドメインに参加している* 場合は、[ **その他のユーザー**] を選択し、 **.\admin**、またはデバイスで構成されているローカル管理者のユーザー名をユーザー名として使用します。

必要な管理タスクを実行した後、Microsoft Teams Rooms アプリに戻すには:

1. Windows ***の [スタート] メニュー*** から、管理 アカウントからサインアウトします。
1. 画面の左端にある [ユーザー アカウント] アイコンを選択し、**[Skype]** を選択して、Microsoft Teams Rooms に戻ります。

> [!NOTE]
> Skype ユーザーが一覧にない場合は、[その他のユーザー] を選択し、ユーザー名として ***「.\skype」*** と入力してサインインします。

## <a name="urls-required-for-communication"></a>通信に必要な URL

 > [!NOTE]
 > MTR デバイス エージェントと Microsoft Teams Rooms Pro 管理ポータル間のすべてのネットワーク トラフィックは、ポート 443 経由で SSL になります *。*  [OFFICE 365 URL と IP アドレス範囲 - Microsoft 365 Enterprise |Microsoft Docs](/microsoft-365/enterprise/urls-and-ip-address-ranges?view=o365-worldwide&preserve-view=true)。

エンタープライズ環境内で **トラフィック許可リスト** が有効になっている場合は、次のホストを許可する必要があります。

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

1. Microsoft Teams Rooms Pro管理ポータル [http://portal.rooms.microsoft.com](https://portal.rooms.microsoft.com/)の左側のナビゲーション バーで、[**設定]** を展開し、[全般] を選択 **します**。
1. [ *ルームの登録] で*、[ **インストーラーのダウンロード**  ] を選択して監視エージェント ソフトウェアをダウンロードします。
1. **オプション：** エージェントのプロキシ設定を設定します。 [「プロキシ設定の追加 (省略可能)」を](#adding-proxy-settings-optional)参照してください。
1. エージェント インストーラー (手順 2 でダウンロード) を、MRT デバイスでローカルに MSI を実行するか、環境内のデバイス (グループ ポリシーなど) に MSI アプリケーションを大量に発行する通常の方法で、MTR ユニットにインストールします。
1. 5~ 10 分以内にポータルに表示されます。

   ![設定と自己登録キーのスクリーンショット。](../media/software-installation-005new.png)

> [!NOTE]
> MTR で Teams アプリを使用せずにエージェントをインストールして Teams にログインできるようにする必要がある場合は、オプションのプロセスとして登録キーを使用できます。 '?' に移動します。 (ヘルプ) をクリックし、[キーのダウンロード (省略可能)] を選択します。 エージェントをインストールするときは、デバイスの **C:\Rigel** ディレクトリに "自己登録キー" (以前にポータルからダウンロードしたキー) を配置します。

## <a name="installation"></a>インストール

インストーラーをMicrosoftからダウンロードした後 (ポータルから、または上記の AKA.ms URL を使用して) その内容を解凍し **、ManagedRoomsInstaller.msi** ファイルにアクセスします。

インストールには 2 つのモードがあります。1) 個々のローカル マシンのインストールと 2) 大量展開モード (通常は同様の方法のIntune)。 ドメインに参加していないマシン、または MSI インストーラーをリモートで実行する方法がないマシンの場合は、個別にインストールすることをお勧めします。

お客様が一括展開モードで MSI アプリケーションを実行できるさまざまな方法があるため、このドキュメントでは、個々のモードでのインストールと、Intune登録されたデバイスでの一括インストールについてのみ説明します。

### <a name="individual-device-installation"></a>個々のデバイスのインストール

1. 管理者としてデバイスにログインします。 デバイスの *管理 ユーザーとして操作を実行* する手順に従っていることを確認します。

1. **ファイルManagedRoomsInstaller.msi** を MTR デバイスにコピーします。

   ***ManagedRoomsInstaller.msi*** を実行すると、使用許諾契約画面が表示されます。

1. 契約を読んだ後、***ライセンス契約の条項に同意** する_ を確認し、_*Install**キーを押します。

    これにより、Microsoft Teams Rooms Pro監視ソフトウェアのインストールが開始されます。 昇格のプロンプト (管理者として実行) が表示されます。

1. [ **はい] を選択します**。

    インストールは続行されます。 インストール手順中に、コンソール ウィンドウが開き、Microsoft Teams Rooms Pro監視ソフトウェアのインストールの最終段階が開始されます。

    > [!NOTE]
    > ウィンドウを閉じないでください。 インストールが完了すると、ウィザードに [完了] ボタンが表示されます。

### <a name="intune-enrolled-device-bulk-deployment"></a>Intune登録されたデバイスの一括展開

次のコンポーネントは、インストールを成功させるための前提条件です。 

- **Intune登録**: Windows デバイス上のTeams Roomsは、Intuneに既に登録されている必要があります。
  Intuneで Windows デバイスにTeams Roomsを登録する方法の詳細については、「[Microsoft エンドポイント マネージャーを使用した Windows デバイスへのMicrosoft Teams Roomsの登録 - Microsoft Tech Community](https://techcommunity.microsoft.com/t5/intune-customer-success/enrolling-microsoft-teams-rooms-on-windows-devices-with/ba-p/3246986)
- **Windows デバイス上のすべてのTeams Roomsをメンバーとして含む Azure AD グループ** - Microsoft Teams Rooms Premium サービスの一部である必要がある Windows デバイス上のすべてのTeams Roomsを含む Azure AD で作成されたグループ。 このグループは、MTR Pro エージェントの展開をターゲットにするために使用されます。
  
> [!NOTE]
> この目的のために Azure AD で動的グループを使用することを検討できます。詳細については、「[Microsoft Endpoint Manager を使用した Windows デバイスへのMicrosoft Teams Roomsの登録 - Microsoft Tech Community](https://techcommunity.microsoft.com/t5/intune-customer-success/enrolling-microsoft-teams-rooms-on-windows-devices-with/ba-p/3246986)
- **MTR Pro エージェント** **インストーラー** のダウンロード - エージェントの zip ファイルを から <https://aka.ms/serviceportalagentmsi> ダウンロードし、zip (ManagedRoomsInstaller.msi) の内容をローカルの一時フォルダーに抽出します。

**Intuneを使用してインストールするには**

1. [Microsoft エンドポイント マネージャー管理センター](https://go.microsoft.com/fwlink/?linkid=2109431)にサインインします。
1. [**アプリ** > **] [すべてのアプリ****] [追加] の順に** > 選択します。
1. [ **アプリの種類の選択** ] ウィンドウの [ **その他の** アプリの種類] で、[ **基幹業務アプリ**] を選択します。
1. [ **選択] をクリックします**。 [ **アプリの追加]** ステップが表示されます。 
1. [ **アプリの追加** ] ウィンドウで、[ **アプリ パッケージ ファイルの選択**] をクリックします。
   1. [ **アプリ パッケージ ファイル** ] ウィンドウで、[  **参照**] を選択します。 次に、以前にダウンロードした **ManagedRoomsInstaller.msi** ファイルを選択します (前提条件のセクションを参照してください)。
   1. 完了したら、[**アプリ パッケージ ファイル**] ウィンドウで **[OK] を** 選択してアプリを追加します。
1. [ **アプリ情報** ] ページで、次の変更を実行します。
   1. 発行元: **「Microsoft Corporation」** と入力します。
   1. アプリのバージョンを無視する: **[はい**] を選択します。

      > [!NOTE]
      > MTR Pro エージェントは自己更新中です。そのため、アプリのバージョンは明示的に無視する必要があります (ベースライン バージョンは自動的に更新できます)。

   1. (省略可能)カテゴリ: **[コンピューターの管理]** を選択します。
   
1. [ **次へ** ] をクリックして、[ **割り当て] ページを** 表示します。
   1. [ **必須** ] セクションで、[ **+ グループの追加** ] をクリックして、エージェントのインストール用にデバイスのグループをターゲットにします。
   1. [ **グループの選択** ] ウィンドウで、[検索] ボックスにグループ名を入力し (上記の前提条件を参照してください)、目的の **グループ** をクリックし、[ **選択**] をクリックします。
      詳細については、「[グループを追加してユーザーとデバイスを整理する」および](https://go.microsoft.com/fwlink/?linkid=2202166)「[Microsoft Intuneを使用してグループにアプリを割り当てる](https://go.microsoft.com/fwlink/?linkid=2202270)」を参照してください。
1. [ **次へ** ] をクリックして、[ **確認と作成** ] ページを表示します。
1. アプリに対して入力した値と設定を確認します。 完了したら、[**作成**] をクリックしてアプリをIntuneに追加します。

プロセスが完了すると、数分後にデバイスがMTR Proエージェントのインストールを開始します。

> [!NOTE]
> インストール後、MTR Pro エージェントが最新バージョンへの自己更新を実行し、MTR Pro ポータルに一覧表示されるまでに最大 8 時間かかる場合があります。
MTR Pro ポータルでの自動登録を迅速化するには、エージェントの展開後に MTR デバイスを再起動することを検討してください。

## <a name="completing-enrollment"></a>登録の完了

インストールが完了したら、5 分から 10 分待ってから、ポータルを更新して、 *オンボード* 状態として報告されたデバイスを一覧に表示します。

*オンボーディング* 状態では、ルームの状態が表示され、更新されますが、アラートが発生したり、調査チケットが作成されたりすることはありません。

ルームを選択し、[ **登録**  ] を選択してインシデント アラートの受信を開始します。

### <a name="unenrolling-and-uninstalling-monitoring-software"></a>監視ソフトウェアの登録解除とアンインストール

デバイスの登録を解除するには、次のように監視エージェントを MTR デバイスから削除します。

1. 監視対象のデバイスで、管理者としてデバイスにログインします。 デバイスの *管理ユーザーとしての操作の実行に関するページの手順に* 従ってください。
1. [aka.ms/MTRPDeviceOffBoarding](https://aka.ms/MTRPDeviceOffBoarding) からリセット スクリプトをダウンロードします。
1. デバイス上のどこかにスクリプトを抽出し、パスをコピーします。
1. 管理者として PowerShell を開く: Windows ***Search** _ フィールド (画面の左下セクション) に「Powershell」と入力し、_*_Windows PowerShell_** を右クリックします。
1. *[管理者として実行] を* 選択し、UAC プロンプトを受け入れます。
1. *「Set-ExecutionPolicy –ExecutionPolicy RemoteSigned*」と入力し、次のプロンプトで **Y** キーを押します。
1. 解凍したオフボード スクリプトの完全パスを PowerShell ウィンドウに貼り付けるか入力し、 **Enter** キーを押します。

   例: 

   ```powershell
   C:\Users\admin\Downloads\MTRP\_Device\_Offboarding\MTRP\_Device\_Offboarding.ps1
   ```

   このコマンドは、デバイスをユーザー標準の MTR 更新プログラムにリセットし、MTR Pro 監視エージェントとファイルを削除します。

1. Microsoft Teams Rooms Pro管理ポータルの左側のメニューで、[会議室] を選択 **します**。
1. 提供されている会議室の一覧で、登録を解除するルームを選択し、[ **登録解除** ] を選択してインシデント アラートまたは調査チケットの取得を停止するか、ルームのインシデントを報告します。

## <a name="troubleshooting-table"></a>トラブルシューティング テーブル

> [!NOTE]
> すべてのMicrosoft Teams Rooms Pro監視エラーは、**managed Rooms** という名前の特定のイベント ログ ファイルMicrosoft記録されます。

***アプリケーション ランタイム ログ ファイルの場所*** =

C:\Windows\ServiceProfiles\LocalService\AppData\Local\ServicePortalAgent\ app-x.x\ServicePortalAgent\ServicePortal\_Verbose\_LogFile.log( **x.x.x** はアプリのバージョン番号) です。

|症状|推奨される手順|
|---|---|
|次のようなエラー メッセージが表示されます。 </p><p> ***エラー: このアプリケーションは、 を使用して実行してください**。 <br> _ *_elevated 特権_**|エスカレートされた特権でアプリケーションを実行し、もう一度やり直してください。|
|||
|次のようなエラー メッセージが表示されます。 </p><p> ***TPM データが見つかりません***|デバイスの BIOS で TPM (トラステッド プラットフォーム モジュール) がオンになっていることを確認します。 これは通常、デバイス BIOS のセキュリティ設定にあります。|
|||
|次のエラー メッセージが表示されます。 </p><p> ***エラー: '管理' または 'Skype' という名前のローカル ユーザー アカウントが見つかりません***|認定されたMicrosoft Teams Room システム デバイスにユーザー アカウントが存在することを確認します。|
|||
|上記で説明していないエラー状態メッセージが表示されます。|インストール ログのコピーを、Microsoft Teams システム サポート エージェントに提供してください。|
