---
title: Microsoft Teams Rooms のメンテナンスと運用
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: このトピックでは、会議室の管理についてMicrosoft Teamsしてください。
ms.openlocfilehash: 3717c140501cbfc7650daafd14a6daa47a4febd3
ms.sourcegitcommit: 7eb66cb2955b17e89e1c162b6ca1b9bdb18189b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/04/2021
ms.locfileid: "61306162"
---
# <a name="microsoft-teams-rooms-maintenance-and-operations"></a>Microsoft Teams Rooms のメンテナンスと運用 
 
このトピックでは、会議室の管理についてMicrosoft Teamsしてください。
  
Microsoft Teams会議室は、会議室をリッチで共同作業的なエクスペリエンスに変換するように設計された Microsoft の会議ソリューションです。 ユーザーは使い慣れたMicrosoft TeamsまたはSkype for Businessインターフェイスを利用できます。IT 管理者は、簡単に展開および管理できる Windows 10 Teams Rooms アプリを利用できます。 Microsoft Teams会議室は、既存の機器を活用して、インストールを容易にし、会議室にMicrosoft TeamsまたはSkype for Businessを取り込む設計です。
    
## <a name="collecting-logs-on-microsoft-teams-rooms"></a>Microsoft Teams Roomsでログを収集する
<a name="Logs"> </a>

管理センターからログをTeamsできます。 管理Teamsで、[デバイス]\[会議室] のTeamsに移動Windows。 このページで、ログをダウンロードする表示名をクリックします。 上部のパネルで、[デバイス ログのダウンロード] をクリックします。 通知を求めるメッセージが表示されます。 [Got it]をクリックします。 数分後、[履歴] タブでログをダウンロードする準備が整います。

PowerShell を使用してログを収集することもできます。 Microsoft Teams Rooms アプリに含むログ収集スクリプトを呼び出す必要があります。 管理者モードで、管理者特権のコマンド プロンプトを開始して、次のコマンドを発行します。
  
```PowerShell
powershell -ExecutionPolicy unrestricted c:\rigel\x64\scripts\provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
```

ログは ZIP ファイルとして c:\rigel に出力されます。
  
## <a name="front-of-room-display-settings"></a>前面の会議室ディスプレイの設定
<a name="Display"> </a>

Consumer Electronics Control (CEC) をサポートするか PC モードを有効にするか、ルーム前面ディスプレイの設定を構成します。
  
会議室の前面ディスプレイがスタンバイ モードからTeamsに自動的に切り替える場合は、特定の条件を満たしている必要があります。 この機能はオプションですが、基盤となるハードウェアで機能がサポートされている場合は、Microsoft Teams Rooms ソフトウェアによってサポートされます。 ルームの前方ディスプレイとして使用される一般向けテレビは、HDMI の CEC (Consumer Electronics Control) 機能をサポートしている必要があります。  選択されているドックまたはコンソール (CEC をサポートしていない可能性があるため、製造元のサポート ドキュメントを参照してください) に応じて、適切な動作を実現するには、Crestron 社の [HD-RX-201-C-E](https://www.crestron.com/Products/Video/HDMI-Solutions/HDMI-Extenders/HD-RX-201-C-E) や Extron 社の [Extron HD CTL 100](https://www.extron.com/article/hdctl100ad) などのコントローラーが必要になる場合があります。 
  
## <a name="microsoft-teams-rooms-reset-factory-restore"></a>Microsoft Teams Rooms のリセット (工場出荷時の復元)
<a name="Reset"> </a>

Microsoft Teams Roomsが正常に動作していない場合は、出荷時の設定にリセットしてみてください。 これを行うには、[Microsoft Teams Room 回復ツール](recovery-tool.md)を使用して、工場出荷時復元の手順に従います。

> [!NOTE]
> Windows を初期状態に戻すプロセス中に、**[個人用ファイルを保持する - アプリと設定を削除しますが、個人用ファイルは保持します]** オプションが選択されている場合、Microsoft Teams Roomsが使用できなくなる可能性があるという既知の問題があります。 このオプションは使用 *しない* でください。
  
## <a name="supported-remote-options"></a>サポートされているリモート オプション
<a name="RemoteOptions"> </a>

次の表に、可能なリモート操作とそれを実行するために使用できる方法を示します。
  

|ワークグループ|ドメインに参加していない場合|ドメインに参加している場合|
|:-----|:-----|:-----|
|再起動  <br/> |Teams管理センター  <br/> リモート デスクトップ  <br/> リモート Powershell  <br/> | <br/>リモート デスクトップ (詳細な設定が必要)  <br/> リモート PowerShell (詳細な設定が必要)  <br/> Configuration Manager  <br/> |
|OS の更新  <br/> |Windows Update  <br/> |Windows Update  <br/> WSUS  <br/> |
|アプリの更新  <br/> |Windows ストア  <br/> |Windows ストア  <br/> Configuration Manager  <br/> |
|アカウント構成  <br/> |Teams管理センター  <br/> |Teams管理センター  <br/> |
|ログへのアクセス  <br/> |Teams管理センター  <br/> PowerShell  <br/> |Teams管理センター <br/> PowerShell  <br/>  |
   
## <a name="configuring-group-policy-for-microsoft-teams-rooms"></a>Microsoft Teams Rooms のグループ ポリシーを構成する
<a name="GroupPolicy"> </a>

このセクションでは、Microsoft Teams Rooms が正常に機能するために依存するシステム設定について説明します。 

会議室Teams Active Directory ドメインに参加すると、次の利点があります。

- 会議室へのドメインTeamsを使用すると、ドメイン ユーザーとグループの管理者権限を付与できます。 これにより、ローカル コンピューター レベルの管理者アカウントのパスワードを記憶する必要がなくなります。

- サービス品質のWindowsを会議室にTeamsできます。

- Skype for Businessを使用している場合は、Teams Rooms へのドメイン参加により、組織のプライベート ルート証明書チェーンを自動的にインポートできます。

Teams Rooms をドメインに参加する場合は、グループ ポリシー オブジェクト (GPO) の除外をすべての Teams Rooms オブジェクトが存在する OU に提供できるよう、別の組織単位 (OU) を作成する必要があります。 すべての GPO の継承を無効にして、サポートされていないグループ ポリシー設定が会議室に適用Teamsします。 既定のコンピューター OU に適用されたグループ ポリシーが確実に適用Teamsに参加する前に、OU にマシン オブジェクトを作成します。

> [!NOTE]
> 別の OU を作成し、継承をブロックする場合でも、グループ ポリシーによっては、[オーバーライドなし] が設定されている場合に問題が発生する可能性があります。 オーバーライドが設定されたグループ ポリシーは、ブロック ポリシー継承が設定された OU を打ち負かします。

多くの組織には、会議室の機能に影響する次Teamsがあります。 以下の継承をオーバーライドまたはブロックしてください。

  - ログオン セッションのタイムアウト (自動ロックアウト)
  - 電源管理関連のポリシー
  - 追加の認証手順が必要
  - ローカル ドライブへのアクセスを拒否
  - ユーザーに低速のネットワーク接続を推奨する
  - ログオン時に特定のプログラムを起動する
  - ドメインに参加するすべてのマシンで別のドメイン ユーザー アカウントを作成する。
  - 更新WindowsをルームにTeamsする

会議室をMicrosoft Teamsに参加する場合は、グループ ポリシーによって次の表の設定が上書きされていないことを確認してください。

|Setting|許可されること|
|:-----|:-----|
|HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (REG_SZ) 1  <br/> |Microsoft Teams Rooms の起動を有効にする  <br/> |
|電源管理 -\> AC で、10 分後に画面をオフにする  <br/> 電源管理 -\> AC で、システムをスリープさせない  <br/> |接続されているディスプレイをオフにし、自動的にウェイク アップさせるように Microsoft Teams Rooms を有効化する  <br/> |
|net accounts /maxpwage:unlimited  <br/> または、ローカル アカウントでパスワードの期限切れを無効にする同等の手段。この設定に失敗すると、パスワードの期限が切れていることが通知され、Skype アカウントのログオンが失敗する原因になります。この影響はマシン上のすべてのローカル アカウントに及びます。したがって、この設定に失敗すると、ボックスの管理アカウントも最終的には期限切れになります。  <br/> |常にログインするように Skype アカウントを有効にする  <br/> |

> [!NOTE]
> Microsoft Teams Rooms が次のバージョンの Windows 10 OS と互換性がある場合、Teams Rooms は、Windows Update を通じて次のバージョンに自動的に更新されます。 Microsoft Teams 会議室は、Windows 10 の次のリリースに手動でアップグレードしたり、GPO を使用して Windows Update for Business (WUFB) グループ ポリシーを有効にしたり 、"受信する更新プログラムの Windows 準備レベルを選択する" および "プレビュー ビルドと機能更新プログラムを受信するときに選択する" を有効にしたりすることはできません。 Teamsポリシーが有効になっている会議室は、OS の更新プログラムに関するWindows 10発生することが知られています。

## <a name="remote-management-using-powershell"></a>PowerShell を使ったリモート管理
<a name="RemotePS"> </a>

PowerShell を使用して、次の管理操作をリモートで実行できます (スクリプトのサンプルについては下記の表を参照してください)。
  
- 接続されているデバイスの取得
- アプリの状態の取得
- システム情報の取得
- システムの再起動
- ログの取得
- ファイルの転送 (ドメインに参加済み Microsoft Teams Rooms が必要)
    
> [!NOTE]
> この機能は既定でオフになっています。 次に示す操作を実行するには、Microsoft Teams Rooms システムの環境でリモート PowerShell を有効にする必要があります。 リモート PowerShell を有効にする方法の詳細については、**[Enable-PSRemoting](/powershell/module/microsoft.powershell.core/enable-psremoting)** のドキュメントを参照してください。
  
たとえば、次のようにしてリモート PowerShell を有効にすることができます。
  
1. Microsoft Teams Rooms のデバイスで、管理者としてサインインします。
2. 管理者特権で PowerShell コマンド プロンプトを開きます。
3. 次のコマンドを入力します: `Enable-PSRemoting -SkipNetworkProfileCheck -Force`
4. ローカル セキュリティ ポリシーを開き、*[管理者]* セキュリティ グループを **[セキュリティの設定]** > **[ローカル ポリシー]** > **[ユーザー権利の割り当て]** > **[ネットワーク経由でコンピューターへアクセス]** に追加します。

管理操作を実行するには、次のようにします。
  
1. Microsoft Teams Rooms のデバイスで PowerShell コマンドを実行する権限を持つアカウントの資格情報を使用して PC にサインインします。
2. PC で通常の PowerShell コマンド プロンプトを開きます。
3. 次の表からコマンド テキストをコピーして、プロンプトに貼り付けます。
4. お使いの環境に応じた適切な FQDN 値で `<Device fqdn>` フィールドを置換します。
5. *\<path\>* をマスター SkypeSettings.xml 構成ファイル (またはテーマの画像) のファイル名とローカル パスで置き換えます。
    
接続されているデバイスを取得する場合
  
```PowerShell
invoke-command {Write-Host "VIDEO DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Image"} | Format-Table Name,Status,Present; Write-Host "AUDIO DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Media"} | Format-Table Name,Status,Present; Write-Host "DISPLAY DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Monitor"} | Format-Table Name,Status,Present} -ComputerName <Device fqdn>
```

アプリの状態の取得
  
```PowerShell
invoke-command { $package = get-appxpackage -User Skype -Name Microsoft.SkypeRoomSystem; if ($package -eq $null) {Write-host "SkypeRoomSystems not installed."} else {write-host "SkypeRoomSystem Version : " $package.Version}; $process = Get-Process -Name "Microsoft.SkypeRoomSystem" -ErrorAction SilentlyContinue; if ($process -eq $null) {write-host "App not running."} else {$process | format-list StartTime,Responding}}  -ComputerName <Device fqdn>
```

システム情報の取得
  
```PowerShell
invoke-command {gwmi -Class Win32_ComputerSystem | Format-List PartOfDomain,Domain,Workgroup,Manufacturer,Model
gwmi -Class Win32_Bios | Format-List SerialNumber,SMBIOSBIOSVersion} -ComputerName <Device fqdn>
```

システムの再起動
  
```PowerShell
invoke-command { Shutdown /r /t 0 } -ComputerName <Device fqdn>
```

ログの取得
  
```PowerShell
$targetDevice = "<Device fqdn> "
$logFile = invoke-command {$output = Powershell.exe -ExecutionPolicy Bypass -File C:\Rigel\x64\Scripts\Provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
Get-ChildItem -Path C:\Rigel\*.zip | Sort-Object -Descending -Property LastWriteTime | Select-Object -First 1} -ComputerName $targetDevice
$session = new-pssession -ComputerName $targetDevice
Copy-Item -Path $logFile.FullName -Destination .\ -FromSession $session; invoke-command {remove-item -force C:\Rigel\*.zip} -ComputerName $targetDevice
```

XML 構成ファイル (またはテーマのグラフィック) をプッシュする
  
```XML
$movefile = "<path>";
$targetDevice = "\\<Device fqdn> \Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState\SkypeSettings.xml"; 
Copy-Item $movefile $targetDevice 
```

## <a name="software-updates"></a>ソフトウェアの更新
<a name="SWupdate"> </a>

既定では、Microsoft Teams Rooms は最新バージョンの Windows Rooms ソフトウェアを取得するために、Microsoft Teams Store への接続を試行します。 そのため、会議室Teamsインターネットに定期的にアクセスする必要があります。 サポートの問題について Microsoft に連絡する前に、Microsoft Teams最新バージョンのアプリが読み込まれているか確認してください。
  
Microsoft Teams Rooms は、オペレーティング システムとWindowsファームウェアの更新プログラムを取得するために、更新プログラムに接続します。 Teamsは、ローカル時刻の午前 2 時 00 分からインストールするように構成されています。
  
Windows ストアへのアクセスの制限により更新プログラムを手動で管理する必要があり、ビジネス向け Microsoft Store から[オフライン](https://businessstore.microsoft.com/store)アプリの配布に関する通常の手順に従う[](/microsoft-store/distribute-offline-apps)必要がある場合は、デプロイ キットから適切な APPX ファイルと依存関係を取得できます[(「](https://go.microsoft.com/fwlink/?linkid=851168) [Microsoft Teams ルーム コンソール](console.md))構成マネージャーで使用できます。 デプロイメント キットのリリースは、ストアのリリースよりも後になるため、最新の入手可能な最新ビルドに必ずしも一致しない可能性があります。
  
### <a name="to-update-using-powershell"></a>PowerShell を使用して更新する場合

1. インストール [MSI](https://go.microsoft.com/fwlink/?linkid=851168) から、デバイスがアクセスできる共有先にパッケージを抽出します。
2. Microsoft Teams Rooms のデバイスを対象に次のスクリプトを実行します \<share\> は、該当するデバイス共有に変更します)。
    
    ```PowerShell
    Add-AppxPackage -Update -ForceApplicationShutdown -Path '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\*.appx' -DependencyPath (Get-ChildItem '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\Dependencies\x64\*.appx' | Foreach-Object {$_.FullName})
    ```

## <a name="admin-mode-and-device-management"></a>管理者モードおよびデバイスの管理
<a name="AdminMode"> </a>

プライベート CA 証明書を手動でインストールする場合など、一部の管理機能では、Teamsを管理モードにする必要があります。 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running"></a>管理者モードに切り替えて、会議室アプリMicrosoft Teamsに戻る

1. 現在の通話を切って、ホーム画面に戻ります。
2. 歯車アイコンをクリックすると、メニューが表示されます (オプションは、**[設定]**、**[アクセシビリティ]**、**[デバイスを再起動]** です)。
3. **[設定]** を選択します。
4. 管理者パスワードを入力します。 設定画面が表示されます。  デバイスがドメインに参加していない場合、既定によりローカルの管理者アカウント (ユーザー名「Admin」) が使用されます。 このアカウントの既定のパスワードは "sfb" です。 できるだけ早くこのパスワードを変更してください。 コンピューターがドメインに参加済みの場合、適切な権限のドメイン アカウントでサインインできます。
5. 左側の列で **[Windows の設定]** を選択します。
6. 管理者の資格情報を使用してデスクトップにログインします。 デバイスの管理に必要な権限を持つことになります。
7. 必要な管理タスクを実行します。
8.  終了したら、コンピューターを再起動します。
    
コンソールは通常の操作モードに戻ります。次の手順では、デバイスにキーボードが接続されていない場合は接続する必要があります。 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-crashes"></a>管理者モードに切り替え、Microsoft Teams Rooms アプリがクラッシュしたら元に戻す

1. Windows キーを 5 回連続で、素早く押します。これによって、Windows のログオン画面が開きます。 
2. 管理者の資格情報を使用してデスクトップにログインします。
3. 必要な管理上のタスクを実行します。
4. 終了したら、コンピューターを再起動します。

    > [!NOTE]
    > この方法は、Skype ユーザーをログオフさせたり、アプリを正常終了させることはありませんが、アプリが応答しない場合や、その他の方法が使用できない場合にのみ使用するようにしてください。 

   コンソールは通常の操作モードで再起動され、Microsoft Teams Rooms アプリが実行されます。 この手順を完了するためにキーボードを取り付ける場合は、キーボードを取り外します。
   ## <a name="troubleshooting-tips"></a>トラブルシューティングのヒント
   <a name="TS"> </a>

- 会議の招待状は、ドメイン境界 (たとえば、2 つの会社間) を越えて送信すると表示されない場合があります。 このような場合、IT 管理者は外部ユーザーに対して会議のスケジュール設定を許可するかどうか決定する必要があります。 PowerShell コマンドレット[Set-CalendarProcessing](/powershell/module/exchange/set-calendarprocessing)Exchange、具体的には 'ProcessExternalMeetingMessages' パラメーターに関する記事を参照してください。
- Microsoft Teams Rooms では、Exchange 2010 経由での Exchange 自動検出リダイレクトはサポートされていません。
- 一般に、使用しないオーディオ エンドポイントを無効にするよう IT 管理者にお勧めします。
- ルーム プレビューでミラー イメージが表示された場合、IT 管理者はカメラの電源を入れ、カメラ設定を使用して画像の向きを反転することで修正できます。
- コンソールのタッチスクリーンへのアクセスが機能しなくなる問題が発生することが知られています。 このような場合は、会議室を再起動することで問題がTeams場合があります。
- 有線取り込みを介して PC をコンソールに接続すると、ローカルの音声が消失する問題が発生することが知られています。 このような場合は、PC を再起動することでローカルの音声再生の問題を解決できます。
