---
title: Microsoft Teams Rooms ソフトウェアのインストール
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
description: 会議室デバイスTeamsマネージド サービスへのオンボード
f1keywords: ''
ms.openlocfilehash: 70209bcd60740f1d1e19b45b215b921396a6f0fd
ms.sourcegitcommit: a969502c0a5237caf041d7726f4f1edefdd75b44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2022
ms.locfileid: "61767561"
---
# <a name="monitor-device-software-installation"></a>デバイス ソフトウェアのインストールを監視する

デプロイするには、Microsoft Teams Rooms デバイスを Microsoft Teams Rooms で管理されるサービスにオンボードする必要があります。 監視サービス エージェントは、認定ソリューション ルーム (MICROSOFT TEAMS システムと周辺機器) で使用します。

## <a name="performing-operations-as-the-admin-user-of-the-mtr-device"></a>操作を、デバイスの管理者ユーザーとして実行する

一部の構成/インストール手順では、管理者としてデバイスにログインする必要があります。

管理者 (ローカル管理者) としてデバイスにログインするには:

1. 進行中の通話を必ず停止し、ホーム画面に戻ります。
1. Microsoft Teams Room ユーザー インターフェイスで、[詳細] を選択し、[設定] を選択します。ここで、デバイスのローカル管理者パスワード (既定のパスワードは **_sfb)_** を求められます。
1. **[設定] を** 選択し、[Windows 設定] を選択してWindows管理者としてアクセスします。  

1. [ログイン] 画面に表示されるユーザー Windows、[管理者] **(または** デバイスのそれぞれのローカル管理者) を選択します。

> [!NOTE]
> コンピューターが *ドメインに参加* している場合は、[その他の **ユーザー**] を選択し、デバイスで構成されているローカル管理者の **ユーザー** 名をユーザー名として使用します。  

必要な管理タスクをMicrosoft Teamsして、Microsoft Teams Room アプリに戻る場合:

1. [] ***Windowsスタート メニュー*** 管理者アカウントからサインアウトします。
1. 画面のMicrosoft Teamsにあるユーザー アカウント アイコンを選択し、[] を選択して [Skype]**に戻ります**。

> [!NOTE]
> ユーザーがSkype場合は、[その他のユーザー] を選択し、ユーザー名として ***「.\skype」*** と入力してサインインします。

## <a name="prerequisites"></a>前提条件

登録プロセスを試みる前に、次の手順に従ってハードウェアを設定します。

### <a name="adding-proxy-settings-optional"></a>プロキシ設定の追加 (省略可能)

1. 「PERFORMING Operations as [the Admin user of the(操作の実行)」に従って管理者としてログインします](#performing-operations-as-the-admin-user-of-the-mtr-device)。
1. [Windows ***Search** _ フィールド (画面の左下のセクション) に *「_cmd** 」と入力します (画面を長押しするか右選択し、[管理者として実行] を選択 **_します_**)。  
1. 次のコマンドを実行します (コマンドの最後の二重引用符が重要です)。
   - 単一の ***プロキシ サーバー*** を使用している場合: bitsadmin /Util /SetIEProxy LOCALSYSTEM MANUAL \_ PROXY : <proxyserver> <port> ""

      *例:* bitsadmin /Util /SetIEProxy LOCALSYSTEM MANUAL \_ PROXY contosoproxy.corp.net:8080 ""
      

   - pac ファイルを ***使用している*** 場合: bitsadmin /Util /SetIEProxy LOCALSYSTEM AUTOSCRIPT <pac file url> ""

      
      *例:* bitsadmin /Util /SetIEProxy LOCALSYSTEM AUTOSCRIPT `http://contosoproxy.corp.net/proxy.pac` ""
      

### <a name="enabling-tpm-settings"></a>TPM 設定の有効化

Intel NUC デバイスの TPM が無効になっている場合は、次のようにこれらのデバイスで TPM を有効にします。  

1. NUC デバイスにキーボードを接続します。  
1. デバイスを再起動します。  
1. BIOS 画面を表示するには、F2 キーを速 **く押します**。  
1. [詳細設定] **を選択します**。  
1. [セキュリティ] **を選択します**。  
1. 右側の [セキュリティ機能] の下で **、Intel Platform Trust Technology を有効にしてください**。  
1. 設定を保存するには **、F10 キーを押します**。  
1. 確認ボックスで、[はい] を **選択します**。  

## <a name="urls-required-for-communication"></a>通信に必要な URL

 > [!NOTE]
 > ポート 443 を使用して、すべてのネットワーク トラフィックMicrosoft Teams MTR デバイス エージェントと MICROSOFT TEAMS Rooms – Managed Services サービス ポータルの間の SSL です *。*  「Office 365 [URL と IP アドレス範囲 - Microsoft 365 Enterprise |Microsoft Docs](/microsoft-365/enterprise/urls-and-ip-address-ranges?view=o365-worldwide&preserve-view=true)。

エンタープライズ環境内でトラフィック許可リストが有効になっている場合は、 **次のホスト** を許可する必要があります。

agent.rooms.microsoft.com<br>
global.azure-devices-provisioning.net<br>
gj3ftstorage.blob.core.windows.net<br>
iothubsgagwt5wgvwg6.azure-devices.net<br>
blobssgagwt5wgvwg6.blob.core.windows.net<br>
mmrstgnoamiot.azure-devices.net<br>
mmrstgnoamstor.blob.core.windows.net<br>
mmrprodapaciot.azure-devices.net<br>
mmrprodapacstor.blob.core.windows.net<br>
mmrprodemeaiot.azure-devices.net<br>
mmrprodemeastor.blob.core.windows.net<br>
mmrprodnoamiot.azure-devices.net<br>
mmrprodnoamstor.blob.core.windows.net

## <a name="process"></a>手順

登録プロセスには、いくつかの手順が含まれます。  

1. [会議室 - Managed Services] ポータルのMicrosoft Teamsバーで、[設定] を展開し、[全般] [http://portal.rooms.microsoft.com](https://portal.rooms.microsoft.com/) **を****選択します**。  
1. [ *自己登録キー] の [* インストーラーのダウンロード] ハイパーリンク **を** 選択 https://aka.ms/serviceportalagentmsi して、監視エージェント ソフトウェアをダウンロードします。
1. [キー **のダウンロード] を選択します**。 登録する各デバイスの **C:\Rigel** フォルダーの下にキー ファイルを配置します。  
1. **省略可能:** エージェントのプロキシ設定を設定します。「 [プロキシ設定の追加 (省略可能)」を参照してください](#adding-proxy-settings-optional)。
1. (手順 2 でダウンロードした) エージェント インストーラーを、MSI をローカルの MSI デバイスで実行するか、環境内のデバイス (グループ ポリシーなど) に MSI アプリケーションを発行する通常の手段を使用して、(手順 2 でダウンロードした) インストールします。  
1. 5 ~ 10 分以内にポータルにルームが表示されます。 表示されない場合は、managedroomsupport@microsoft.com に問い合 managedroomsupport@microsoft.com。  

![図 5](../media/software-installation-005.jpg)

## <a name="installation"></a>インストール

(ポータルから、または上記の AKA.ms URL を使用して) Microsoft からインストーラーをダウンロードした後、その内容を解凍して ファイル にアクセス **ManagedRoomsInstaller.msi。**

インストールには 2 つのモードがあります。個々のローカル マシンのインストールモードと一括デプロイ モード (通常は同様の方法のグループ ポリシーを使用)。 ドメインに参加しないマシン、または MSI インストーラーをリモートで実行する方法がないマシンには、個別インストールすることをお勧めします。  

お客様が MSI アプリケーションを一括デプロイ モードで実行できるさまざまな方法のため、このドキュメントでは、個々のモードでのインストールについてのみ説明します。  

 > [!NOTE]
 > 実行されているモードに関係なく、インストーラー プログラムのフローは同じです。 唯一のわずかな違いは、一括展開モードで次のボタンと閉じるボタンを押すようユーザーに要求しない点です。  

## <a name="individual-devicemdashdomain-joined-walkthrough"></a>個々のデバイス &mdash; ドメイン参加チュートリアル

1. 管理者としてデバイスにログインします。デバイスの *管理者ユーザーとして* 操作を実行する手順に従ってください。

1. 次のファイルを、このデバイスにコピーします。

   - デバイスの **C:\Rigel** ディレクトリに 、(以前にポータルからダウンロードした) "自己登録キー" を配置します。
   - (以前 **ManagedRoomsInstaller.msi** ポータルまたはポータルからダウンロードしたファイル) をデバイス AKA.MS コピーします。

1. *ManagedRoomsInstaller.msiを **実行** すると、[ライセンス契約] 画面が表示されます。 契約を読んだ後、[ _*_使用許諾契約書の条項_*_ に同意する] チェック ボックスをオンにし、_ *[インストール*] * ボタンを押します。  

    これにより、Microsoft Teams Rooms – Managed Services 監視ソフトウェアのインストールが開始されます。 昇格のプロンプト (管理者として実行) が表示されます。
 1. [ ***はい] を選択します***。

    インストールは続行されます。 インストール手順の間に、コンソール ウィンドウが開き、Microsoft Teams Rooms – Managed Services 監視ソフトウェアのインストールの最終段階が開始されます。  

    > [!NOTE]
    > ウィンドウを閉じない。 インストールが完了すると、ウィザードに [完了] ボタンが表示されます。

## <a name="completing-enrollment"></a>登録の完了

インストールが完了したら、5 ~ 10 分待ってポータルを更新すると、デバイスが一覧表示され、オンボード状態 *として報告* されます。

オンボード *状態では* 、ルームの状態が表示および更新されますが、アラートが発生したり、調査チケットを作成したりはされません。

ルームを選択し、[ **登録] を**  選択してインシデント アラートの取得、調査チケットの取得、またはインシデントの報告を開始します。

ご質問や問題がある場合は、ポータルで顧客から報告されたインシデントを開くか、お問い合 managedroomsupport@microsoft.com。

### <a name="unenrolling-and-uninstalling-monitoring-software"></a>監視ソフトウェアの登録解除とアンインストール

デバイスの登録を解除するには、次のように、監視エージェントを次のように、監視エージェントを ()

1. 監視対象のデバイスで、デバイスに管理者としてログインします。 デバイスの管理者ユーザーとしての操作 *の実行に関するページの手順に従ってください*。
1. からリセット スクリプトを[ダウンロード aka.ms/MTRPDeviceOffBoarding。](https://aka.ms/MTRPDeviceOffBoarding)
1. デバイス上のどこかにスクリプトを抽出し、パスをコピーします。
1. 管理者として PowerShell を開きます。Windows ***検索** _ フィールド (画面の左下のセクション) で、「Powershell」と入力し、_* Windows PowerShell ** を _右クリック_ します。
1. [管理者 *として実行] を選択し、UAC* プロンプトに同意します。
1. *「Set-ExecutionPolicy –ExecutionPolicy RemoteSigned」* と入力し、次のプロンプトで **Y** キーを押します。  
1. PowerShell ウィンドウに、未接続のオフボード スクリプトへの完全パスを貼り付けるか入力し、Enter キーを **押します**。

   次に例を示します。

   *C:\Users\admin\Downloads\MTRP \_ Device \_ Offboarding\MTRP \_ Device \_Offboarding.ps1*  

   これにより、デバイスがユーザー標準のTRM 更新プログラムにリセットされ、監視エージェントとファイルが削除されます。

1. [会議室 - Managed Services] ポータルのMicrosoft Teamsメニューで、[会議室] を **選択します**。  
1. 指定されたルームの一覧で、登録を解除するルームを選択し、[登録解除] を選択してインシデント アラートや調査チケットの取得を停止するか、ルームのインシデントを報告します。

## <a name="troubleshooting-table"></a>テーブルのトラブルシューティング

> [!NOTE]
> すべての Microsoft Teams - Managed Services の監視エラーは、Microsoft Managed Rooms という名前の特定のイベント ログ **ファイルに記録されます**。 

### <a name="application-runtime-log-file-location-"></a>***アプリケーション ランタイム ログ ファイルの場所*** =  

C:\Windows\ServiceProfiles\LocalService\AppData\Local\ServicePortalAgent\ app-x.x.x\ServicePortalAgent\ServicePortal \_ Verbose \_ LogFile.log(x.x.xはアプリのバージョン番号です)。

|**現象**  |**推奨される手順**  |
| :- | :- |
|<p>というエラー メッセージが表示されます。   </p><p>***エラー: _ でこのアプリケーションを実行** してください </p><p>_ *_昇格された特権_**  </p>|昇格された特権でアプリケーションを実行し、もう一度やり直す  |
|  |  |
|<p>というエラー メッセージが表示されます。   </p><p>***TPM データが見つからない***  </p>|デバイスの BIOS で TPM (トラステッド プラットフォーム モジュール) が有効になっていることを確認します。 これは通常、デバイスの BIOS のセキュリティ設定で確認できます。  |
|  |  |
|<p>エラー メッセージが表示される  </p><p>` `***エラー: "Admin" または 'Skype' という名前のローカル ユーザー アカウントが見つかりません***  </p>|認証済みの Room システム デバイスにユーザー アカウントMicrosoft Teams確認します。  |
|  |  |
|上記で説明していないエラー状態メッセージが表示される  |インストール ログのコピーをシステム サポート エージェントにMicrosoft Teamsしてください。 |
