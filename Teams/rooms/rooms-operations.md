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
localization_priority: Normal
description: このトピックでは、Skype Room Systems の後継である Microsoft Teams Roomsの管理について説明します。
ms.openlocfilehash: a6ab68200002035632314ac976cd45a2ee4ff714
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662462"
---
# <a name="microsoft-teams-rooms-maintenance-and-operations"></a>Microsoft Teams Rooms のメンテナンスと運用 
 
このトピックでは、Skype Room Systems の後継である Microsoft Teams Roomsの管理について説明します。
  
Microsoft Teams Roomsは、Microsoft の最新の会議ソリューションで、既存の会議室を機能豊富で共同作業に適したエクスペリエンスに変えられるように設計されています。 ユーザーは慣れ親しんだ Microsoft Teams または Skype for Business のインターフェイスを活用し、IT 管理者は Windows 10 Skype Meeting アプリを簡単に展開および管理することができます。 Microsoft Teams Roomsは、簡単にインストールして Microsoft Teams または Skype for Business を会議室に導入できるように、LCD パネルなどの既存の装置を使用するように設計されています。
  
「[Azure Monitor を使用して Microsoft Teams Roomsの管理を計画する](azure-monitor-plan.md)」、「[Azure Monitor を使用して Microsoft Teams Roomsの管理を展開する](azure-monitor-deploy.md)」、「[Azure Monitor を使用して Microsoft Teams Roomsのデバイスを管理する](azure-monitor-deploy.md)」で説明されているように、追加の構成を行えば Microsoft Azure Monitor を使用してリモート管理を行うことが可能になります。 [XML 構成ファイルを使用して、リモートで Microsoft Teams Roomsのコンソール設定を管理する](xml-config-file.md)こともできます。これには、カスタムの画面テーマの適用が含まれます。 
  
## <a name="collecting-logs-on-microsoft-teams-rooms"></a>Microsoft Teams Roomsでログを収集する
<a name="Logs"> </a>

ログを収集するには、Microsoft Teams Rooms アプリに付属のログ収集スクリプトを呼び出す必要があります。 管理者モードで、管理者特権のコマンド プロンプトを開始して、次のコマンドを発行します。
  
```PowerShell
powershell -ExecutionPolicy unrestricted c:\rigel\x64\scripts\provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
```

ログは ZIP ファイルとして c:\rigel に出力されます。
  
## <a name="front-of-room-display-settings"></a>前面の会議室ディスプレイの設定
<a name="Display"> </a>

会議室ディスプレイのフロントカメラを拡張モードに設定します。 この操作により、ディスプレイの電源を入れ替えたときにディスプレイ上にコンソール UI が重複しません。
  
> [!NOTE]
> ルームの前方ディスプレイを、ソースがスタンバイ モードから復帰したときにアクティブなビデオ ソース (MTR コンソールなど) に自動的に切り替える場合は、特定の条件を満たしている必要があります。 この機能はオプションですが、基盤となるハードウェアで機能がサポートされている場合は、Microsoft Teams Rooms ソフトウェアによってサポートされます。 ルームの前方ディスプレイとして使用される一般向けテレビは、HDMI の CEC (Consumer Electronics Control) 機能をサポートしている必要があります。  選択されているドックまたはコンソール (CEC をサポートしていない可能性があるため、製造元のサポート ドキュメントを参照してください) に応じて、適切な動作を実現するには、Crestron 社の [HD-RX-201-C-E](https://www.crestron.com/Products/Video/HDMI-Solutions/HDMI-Extenders/HD-RX-201-C-E) や Extron 社の [Extron HD CTL 100](https://www.extron.com/article/hdctl100ad) などのコントローラーが必要になる場合があります。 
  
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
|再起動  <br/> |リモート デスクトップ  <br/> リモート Powershell  <br/> |リモート デスクトップ (詳細な設定が必要)  <br/> リモート PowerShell (詳細な設定が必要)  <br/> Configuration Manager  <br/> |
|OS の更新  <br/> |Windows Update  <br/> |Windows Update  <br/> WSUS  <br/> |
|アプリの更新  <br/> |Windows ストア  <br/> |Windows ストア  <br/> Configuration Manager  <br/> |
|Skype アカウントの構成  <br/> |現在サポートされていません  <br/> |現在サポートされていません  <br/> |
|ログへのアクセス  <br/> |現在サポートされていません  <br/> |現在サポートされていません  <br/> |
   
## <a name="configuring-group-policy-for-microsoft-teams-rooms"></a>Microsoft Teams Rooms のグループ ポリシーを構成する
<a name="GroupPolicy"> </a>

このセクションでは、Microsoft Teams Rooms が正常に機能するために依存するシステム設定について説明します。 Microsoft Teams Rooms をドメインに加えるときには、グループ ポリシーによって次の表の設定が上書きされないようにしてください。
  

|設定|許可されること|
|:-----|:-----|
|HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (REG_SZ) 1  <br/> |Microsoft Teams Rooms の起動を有効にする  <br/> |
|電源管理 -\> AC で、10 分後に画面をオフにする  <br/> 電源管理 -\> AC で、システムをスリープさせない  <br/> |接続されているディスプレイをオフにし、自動的にウェイク アップさせるように Microsoft Teams Rooms を有効化する  <br/> |
|net accounts /maxpwage:unlimited  <br/> これは、ローカル アカウントでパスワードの有効期限を無効にすることに相当します。 この操作を行わないと、最終的に Skype アカウントがログオンできなくなり、パスワードの有効期限が切れているという通知が発生します。 これは、コンピューター上のすべてのローカル アカウントに影響を与えるため、設定に失敗すると、ボックスの管理者アカウントも最終的に有効期限切れになります。  <br/> |常にログインするように Skype アカウントを有効にする  <br/> |
   
グループ ポリシーを使用してファイルを転送する方法については、「[ファイルの項目を構成する](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx)」で説明しています。

> [!NOTE]
> Microsoft Teams Rooms のデバイスが Windows 10 OS の次回のバージョンと互換性がある場合、Windows Update により、デバイスは次回のバージョンに自動的に更新されます。 Microsoft Teams Rooms のデバイスでは、Windows 10 の次回のリリースに手動でアップグレードしたり、GPO を介して Windows Update for Business (WUFB) グループ ポリシーの [受信する更新プログラムの Windows 準備レベルを選択する] と [プレビュー ビルドと機能更新プログラムを受信するタイミングを選択する] を有効にしたりしないでください。 これらのグループ ポリシーが有効になっているデバイスでは、Microsoft Teams Rooms アプリによる Windows 10 OS 更新プログラムの問題が発生することがわかっています。

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
> この機能は既定でオフになっています。 次に示す操作を実行するには、Microsoft Teams Rooms システムの環境でリモート PowerShell を有効にする必要があります。 リモート PowerShell を有効にする方法の詳細については、**[Enable-PSRemoting](https://technet.microsoft.com/library/hh849694.aspx)** のドキュメントを参照してください。
  
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

既定では、Microsoft Teams Roomsは Windows ストアに接続して、Microsoft Teams Rooms ソフトウェアの最新バージョンを入手しようとするため、デバイスは正常なインターネット アクセスを必要とします。 サポートの問題について Microsoft に問い合わせる前に、Microsoft Teams Rooms のデバイスに最新バージョンのアプリが読み込まれていることを確認してください。
  
既定では、Microsoft Teams Rooms は Windows Update に接続してオペレーティング システムと USB 周辺機器のファームウェアの更新プログラムを取得し、設定された業務時間外にインストールします。 管理者アカウントにサインインし、設定アプリを実行して、業務時間を設定することができます。
  
更新を手動で管理するときに、[オフライン アプリの配布](https://docs.microsoft.com/microsoft-store/distribute-offline-apps)を行うために、[ビジネス向け Microsoft Store](https://businessstore.microsoft.com/store) の通常の手順を実行できない場合は、[デプロイメント キット](https://go.microsoft.com/fwlink/?linkid=851168) ([Microsoft Teams Rooms コンソールの構成](console.md)を行うための操作指示に含まれる) から、Configuration Manager で使用できる適切な APPX ファイルと依存関係を取得できます。 デプロイメント キットのリリースは、ストアのリリースよりも後になるため、最新の入手可能な最新ビルドに必ずしも一致しない可能性があります。
  
### <a name="to-update-using-powershell"></a>PowerShell を使用して更新する場合

1. インストール [MSI](https://go.microsoft.com/fwlink/?linkid=851168) から、デバイスがアクセスできる共有先にパッケージを抽出します。
2. Microsoft Teams Rooms のデバイスを対象に次のスクリプトを実行します \<share\> は、該当するデバイス共有に変更します)。
    
    ```PowerShell
    Add-AppxPackage -Update -ForceApplicationShutdown -Path '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\*.appx' -DependencyPath (Get-ChildItem '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\Dependencies\x64\*.appx' | Foreach-Object {$_.FullName})
    ```

## <a name="admin-mode-and-device-management"></a>管理者モードおよびデバイスの管理
<a name="AdminMode"> </a>

プライベート CA 証明書の手動によるインストールのような一部の管理機能では、Surface Pro デバイスを管理者モードにする必要があります。 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running"></a>管理者モードに切り替え、Microsoft Teams Rooms アプリが実行されたら元に戻す

1. 現在の通話を切って、ホーム画面に戻ります。
2. 歯車アイコンをクリックすると、メニューが表示されます (オプションは、**[設定]**、**[アクセシビリティ]**、**[デバイスを再起動]** です)。
3. **[設定]** を選択します。
4. 管理者パスワードを入力します。 設定画面が表示されます。  デバイスがドメインに参加していない場合、既定によりローカルの管理者アカウント (ユーザー名「Admin」) が使用されます。 このアカウントの既定のパスワードは 'sfb' です。できるだけ早くパスワードを変更してください。 コンピューターがドメインに参加済みの場合、適切な権限のドメイン アカウントでサインインできます。 
5. 左側の列で **[Windows の設定]** を選択します。
6. [**管理サインインに移動**] を選択します。
7. 管理者パスワードを入力します。 これによって、アプリから正常にログオフされ、Windows のログイン画面が表示されます。 
8. 管理者の資格情報でデスクトップにログインします。 デバイスの管理に必要な権限を持つことになります。
9. 必要な管理タスクを実行します。
10. 管理者アカウントからサイン アウトします。
11. 画面の左端にある [ユーザー アカウント] アイコンを選択し、**[Skype]** を選択して、Microsoft Teams Rooms に戻ります。
    
    **[Skype]** ユーザーがリストに表示されていない場合、**[他のユーザー]** を選択してからユーザー名として **.\skype** と入力し、サインインします。
    
コンソールは通常の操作モードに戻ります。次の手順では、デバイスにキーボードが接続されていない場合は接続する必要があります。 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-crashes"></a>管理者モードに切り替え、Microsoft Teams Rooms アプリがクラッシュしたら元に戻す

1. Windows キーを 5 回連続で、素早く押します。 これによって、Windows のログオン画面が開きます。 
2. 管理者の資格情報を使用してデスクトップにログインします。
3. 必要な管理上のタスクを実行します。
4. 終了したら、コンピューターを再起動します。

    > [!NOTE]
    > この方法は、Skype ユーザーをログオフさせたり、アプリを正常終了させることはありませんが、アプリが応答しない場合や、その他の方法が使用できない場合にのみ使用するようにしてください。 

   コンソールは通常の操作モードで再起動され、Microsoft Teams Rooms アプリが実行されます。 この手順を実行するためにキーボードが接続されていた場合は、取り外すことができます。
   ## <a name="troubleshooting-tips"></a>トラブルシューティングのヒント
   <a name="TS"> </a>

- 会議の招待状は、ドメイン境界 (たとえば、2 つの会社間) を越えて送信すると表示されない場合があります。 このような場合、IT 管理者は外部ユーザーに対して会議のスケジュール設定を許可するかどうか決定する必要があります。
- Microsoft Teams Rooms では、Exchange 2010 経由での Exchange 自動検出リダイレクトはサポートされていません。
- 一般に、使用しないオーディオ エンドポイントを無効にするよう IT 管理者にお勧めします。
- ルームのプレビューにミラー イメージが表示される場合、IT 管理者はカメラの電源をいったんオフにして再びオンにするか、カメラのリモート制御を使用してイメージの向きを反転させることでミラー イメージを修正できます。
- コンソールのタッチスクリーンへのアクセスが機能しなくなる問題が発生することが知られています。 このような場合は、Microsoft Teams Rooms システムを再起動することで問題を解決できる場合があります。
- 有線取り込みを介して PC をコンソールに接続すると、ローカルの音声が消失する問題が発生することが知られています。 このような場合は、PC を再起動することでローカルの音声再生の問題を解決できます。
    
