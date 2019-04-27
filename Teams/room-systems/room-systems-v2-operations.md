---
title: マイクロソフト チームの会議室のメンテナンスと運用
ms.author: jambirk
author: jambirk
ms.reviewer: davgroom
manager: serdars
ms.date: 5/10/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
ms.collection: M365-voice
localization_priority: Normal
description: Skype ルーム システムの次世代をマイクロソフト チームの会議室の管理の詳細については、このトピックを参照してください。
ms.openlocfilehash: efaf2a1bae7980855501b826d6a2ee902f0f56b2
ms.sourcegitcommit: 79ec789a22acf1686c33a5cc8ba3bd50049f94b8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2019
ms.locfileid: "33362919"
---
# <a name="microsoft-teams-rooms-maintenance-and-operations"></a>マイクロソフト チームの会議室のメンテナンスと運用 
 
Skype ルーム システムの次世代をマイクロソフト チームの会議室の管理の詳細については、このトピックを参照してください。
  
マイクロソフト チームの会議室は、会議室をリッチな共同作業の経験に変換するように設計された、マイクロソフトの最新の会議ソリューションです。 ユーザーは、使い慣れたマイクロソフトのチームを利用または Skype ビジネス インタ フェースと IT 管理者の Windows 10 Skype 会議アプリケーション展開と管理が容易に喜ばれるでしょう。 マイクロソフト チームの会議室は、マイクロソフトのチームまたは Skype をビジネスの会議室に表示するインストールの容易さの LCD パネルと同様に既存の機器を活用して設計されています。
  
リモート管理は、 [Azure のモニターを使用して Microsoft チームの部屋の計画の管理](azure-monitor-plan.md)、 [Azure のモニターを使用してマイクロソフト チーム ルームの展開の管理](azure-monitor-deploy.md)、[管理の説明に従って、Microsoft Azure のモニターを使用して、追加の構成Azure のモニターを使用して Microsoft チーム室デバイス](azure-monitor-deploy.md)。 また、[マイクロソフト チームのルームの管理コンソールの XML 構成ファイルでリモートでの設定](xml-config-file.md)、ユーザー設定の表示テーマを適用する必要がある場合があります。 
  
## <a name="collecting-logs-on-microsoft-teams-rooms"></a>マイクロソフト チームの会議室のログの収集
<a name="Logs"> </a>

ログを収集するには、マイクロソフト チームの会議室のアプリケーションに付属しているログ収集スクリプトを呼び出す必要があります。 管理者モードで、管理者特権のコマンド プロンプトを開始して、次のコマンドを発行します。
  
```
powershell -ExecutionPolicy unrestricted c:\rigel\x64\scripts\provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
```

ログは ZIP ファイルとして c:\rigel に出力されます。
  
## <a name="front-of-room-display-settings"></a>前面の会議室ディスプレイの設定
<a name="Display"> </a>

前面の会議室ディスプレイを拡張モードに構成します。 これが必ず、コンソールを表示するには、ディスプレイの電源を入れ直すと、UI は複製されません。
  
> [!NOTE]
> 屋内ディスプレイの前面として使用される消費者向け TV では、スタンバイ モードからアクティブなビデオ ソースに自動的に切り替わるように、HDMI の CEC (Consumer Electronics Control) 機能をサポート/有効にする必要があります。 この機能はすべての TV でサポートされるものではありません。 
  
## <a name="microsoft-teams-rooms-reset-factory-restore"></a>マイクロソフト チームの会議室のリセット (工場出荷時復元)
<a name="Reset"> </a>

マイクロソフト チームの会議室がうまく実行されていない、工場出荷時リセットを実行することが役立ちます。 これで**この PC をリセット**するの下にある [**回復**] タブの [アプリケーションの設定を行うを選択**を開始**し、**すべて削除します。** デバイスをリセットするのには、画面の指示に従います。
  
> [!NOTE]
> 場所マイクロソフト チームの会議室が使用できなくなる場合 Windows のリセット処理中に、**アプリの削除と設定のファイルを保存、個人用ファイルを保持**] オプションが選択されている既知の問題があります。 操作を行います_しない_このオプションを使用します。
  
## <a name="supported-remote-options"></a>サポートされるリモート オプション
<a name="RemoteOptions"> </a>

次の表に、可能なリモート操作とそれを実行するために使用できる方法を示します。
  

|**ワークグループ **|**ドメインに参加していない場合**|**ドメインに参加している場合**|
|:-----|:-----|:-----|
|再起動  <br/> |リモート デスクトップ  <br/> リモート Powershell  <br/> |(さらに設定する必要があります)、リモート デスクトップ  <br/> リモート Powershell を (さらに設定する必要があります)  <br/> SCCM  <br/> |
|OS の更新  <br/> |Windows Update  <br/> |Windows Update  <br/> WSUS  <br/> |
|アプリの更新  <br/> |	Windows ストア  <br/> |Windows ストア  <br/> SCCM  <br/> |
|Skype アカウントの構成  <br/> |現在サポートされていません  <br/> |	現在サポートされていません  <br/> |
|ログへのアクセス  <br/> |	現在サポートされていません  <br/> |	現在サポートされていません  <br/> |
   
## <a name="configuring-group-policy-for-microsoft-teams-rooms"></a>マイクロソフト チームの会議室のグループ ポリシーを構成します。
<a name="GroupPolicy"> </a>

このセクションでは、マイクロソフト チームの会議室が正しく機能するために依存しているシステムの設定について説明します。 マイクロソフト チームの会議室をドメインに参加させるときは、グループ ポリシーが次の表の設定を上書きしないことを確認します。
  

|**設定**|**により、**|
|:-----|:-----|
|HKLM\SOFTWARE\Microsoft\Windows 探して AutoAdminLogon = (REG_SZ) 1  <br/> |起動するように、マイクロソフト チームの会議室を使用します。  <br/> |
|電源管理 -\> AC、画面をオフに 10 分後  <br/> 電源管理 -\> Ac システムをスリープ状態を配置しません。  <br/> |マイクロソフト チームの部屋に接続されている表示をオフにして、自動的にスリープを有効に  <br/> |
|net accounts /maxpwage:unlimited  <br/> またはローカル アカウントのパスワードの有効期限を無効にするのと同等のことを意味します。 これを行うには、障害が発生する Skype アカウントの期限切れのパスワードについて苦情を言ってログオンが失敗すると、最終的に。 したがってこれを設定して必要があります管理者アカウント、最終的にも期限切れにする] ボックスに、コンピューター上のすべてのローカル アカウントに影響を与えるこのこと注意してください。  <br/> |常にログインするように Skype アカウントを有効にする  <br/> |
   
グループ ポリシーを使用してファイルを転送するは、[構成ファイルの項目](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx)で説明します。
  
## <a name="remote-management-using-powershell"></a>PowerShell を使用したリモート管理
<a name="RemotePS"> </a>

PowerShell を使用して、次の管理操作をリモートで実行することができます (スクリプトのサンプルについては、次の表を参照してください)。
  
- 接続されているデバイスの取得
    
- アプリの状態の取得
    
- システム情報の取得
    
- システムの再起動
    
- ログの取得
    
- ファイルを転送する (ドメインに参加している Microsoft チーム ルームが必要です)
    
> [!NOTE]
> 既定では、この機能はオフです。 以下の操作を実行するのには、マイクロソフト チームの会議室のシステム環境のリモート PowerShell を有効にする必要があります。 リモート PowerShell を有効にする方法についての情報を**[有効にする PSRemoting](https://technet.microsoft.com/library/hh849694.aspx)** のマニュアルを参照してください。
  
たとえば、次のようにリモート PowerShell を有効にできます。
  
1. マイクロソフト チームの会議室のデバイスに管理者としてサインインします。
    
2. 管理者特権の PowerShell コマンド プロンプトを開きます。
    
3. 次のコマンドを入力します。Enable-PSRemoting -force
    
管理操作を実行するには、次の操作を実行します。
  
1. マイクロソフト チームの会議室のデバイスでの PowerShell コマンドを実行する権限を持つアカウントの資格情報で PC にサインインします。
    
2. PC の通常の PowerShell コマンド プロンプトを開きます。
    
3. コマンド テキストを次の表からコピーし、プロンプトに貼り付けます。
    
4. 交換`<Device fqdn>`FQDN の値を持つフィールドが、環境に対応します。
    
5. 交換*\<のパス\>* SkypeSettings.xml 構成ファイルのマスター (またはテーマのイメージ) のローカル パスとファイル名とします。
    
接続されているデバイスを取得するには
  
```
invoke-command {Write-Host "VIDEO DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Image"} | Format-Table Name,Status,Present; Write-Host "AUDIO DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Media"} | Format-Table Name,Status,Present; Write-Host "DISPLAY DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Monitor"} | Format-Table Name,Status,Present} -ComputerName <Device fqdn>
```

アプリの状態の取得
  
```
invoke-command { $package = get-appxpackage -User Skype -Name Microsoft.SkypeRoomSystem; if ($package -eq $null) {Write-host "SkypeRoomSystems not installed."} else {write-host "SkypeRoomSystem Version : " $package.Version}; $process = Get-Process -Name "Microsoft.SkypeRoomSystem" -ErrorAction SilentlyContinue; if ($process -eq $null) {write-host "App not running."} else {$process | format-list StartTime,Responding}}  -ComputerName <Device fqdn>
```

システム情報の取得
  
```
invoke-command {gwmi -Class Win32_ComputerSystem | Format-List PartOfDomain,Domain,Workgroup,Manufacturer,Model
gwmi -Class Win32_Bios | Format-List SerialNumber,SMBIOSBIOSVersion} -ComputerName <Device fqdn>
```

システムの再起動
  
```
invoke-command { Shutdown /r /t 0 } -ComputerName <Device fqdn>
```

ログの取得
  
```
$targetDevice = "<Device fqdn> "
$logFile = invoke-command {$output = Powershell.exe -ExecutionPolicy Bypass -File C:\Rigel\x64\Scripts\Provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
Get-ChildItem -Path C:\Rigel\*.zip | Sort-Object -Descending -Property LastWriteTime | Select-Object -First 1} -ComputerName $targetDevice
$session = new-pssession -ComputerName $targetDevice
Copy-Item -Path $logFile.FullName -Destination .\ -FromSession $session; invoke-command {remove-item -force C:\Rigel\*.zip} -ComputerName $targetDevice
```

XML 構成ファイル (またはテーマのグラフィック) をプッシュします。
  
```
$movefile = "<path>";
$targetDevice = "\\<Device fqdn> \Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState\SkypeSettings.xml"; 
Copy-Item $movefile $targetDevice 
```

## <a name="software-updates"></a>ソフトウェアの更新
<a name="SWupdate"> </a>

既定では、マイクロソフト チームの会議室は、デバイスの通常のインターネット アクセスが必要なので、チームの会議室を Microsoft のソフトウェアの最新バージョンを取得する Windows ストアに接続しようとします。 必ずサポートの問題に関して、マイクロソフトに連絡する前にマイクロソフト チームの会議室のデバイス アプリケーションの最新バージョンがロードされます。
  
既定は、マイクロソフト チームの会議室は、オペレーティング システムを取得するために Windows の更新プログラムと USB 周辺機器のファームウェアの更新に接続し、構成済みの業務時間外をインストールします。 営業時間を設定するには、管理者アカウントでサインインし、設定アプリを実行します。
  
APPX の適切なファイルとの[『 導入ガイド 』](https://go.microsoft.com/fwlink/?linkid=851168) (からの依存関係を取得することをした場合、手動で更新プログラムを管理する通常の手順に従って、[ビジネス向けのマイクロソフト ストア](https://businessstore.microsoft.com/store)の[オフライン アプリケーションを配布](https://docs.microsoft.com/microsoft-store/distribute-offline-apps)することはできません。[マイクロソフト チームの会議室のコンソールを構成](console.md)する方法) と SCCM を使用できます。 展開キットのリリースも遅れて、ストアのリリースでは、最新の利用可能なビルドを常に一致可能性がありますように。
  
### <a name="to-update-using-powershell"></a>Powershell を使用して更新するのには

1. 共有デバイスには、 [MSI](https://go.microsoft.com/fwlink/?linkid=851168)にアクセスできるインストール パッケージを展開します。
    
2. デバイスの Microsoft チームの会議室の変更を対象とする次のスクリプトを実行\<共有\>デバイスには、必要に応じて共有します。
    
```
Add-AppxPackage -Update -ForceApplicationShutdown -Path '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\*.appx' -DependencyPath (Get-ChildItem '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\Dependencies\x64\*.appx' | Foreach-Object {$_.FullName})
```

## <a name="admin-mode-and-device-management"></a>管理者モードとデバイス管理
<a name="AdminMode"> </a>

プライベート CA 証明書を手動でインストールするように、一部の管理機能は、管理者モードで Surface Pro デバイスを配置する必要があります。 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running"></a>管理者モードとマイクロソフト チームの会議室のアプリケーションを実行しているときの切り替え

1. 進行中の呼び出しを切断し、ホーム画面に戻ります。
    
2. 歯車のアイコンを選択し、メニューを表示 (オプションは、**設定**、**ユーザー補助の設定**、および**デバイスの再起動**) します。
    
3. [**設定**] を選択します。
    
4. 管理者パスワードを入力します。 セットアップ画面が表示されます。
    
    > [!NOTE]
    > 場合は、デバイスでは、ドメインに参加していない場合は、ローカルの管理者アカウント (ユーザー名"Admin") は、既定で使用されます。 このアカウントの既定のパスワードは「sfb」ですが、セキュリティ上の理由により所属する組織によってできるだけ早く変更されることが推奨されます。 コンピューターがドメインに参加している場合は、適切な特権を持つドメイン アカウントを使用して署名できます。 
  
5. 左の列には、 **Windows の設定**を選択します。
    
6. [**管理サインインに移動**] を選択します。
    
7. 管理者パスワードを入力します。 これによって、アプリから正常にログオフされ、Windows のログイン画面が表示されます。 
    
8. 管理者の資格情報でデスクトップにログインします。 デバイスを管理するために必要な特権があります。
    
9. 必要な管理タスクを実行します。
    
10. 管理者アカウントからサイン アウトします。
    
11. 画面の左端にある [ユーザー アカウントのアイコンを選択し、 **Skype**では、マイクロソフト チームの会議室に戻ります。
    
    **Skype**ユーザーが一覧にない場合は**他のユーザー**を選択し、入力をする必要があります**です。 \skype**として、ユーザー名、およびサインインします。
    
コンソールは、その通常の操作モードに戻るようになりました。次の手順では、1 つは既に接続されていない場合、デバイスにキーボードを接続する必要があります。 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-crashes"></a>管理者モードとマイクロソフト チーム ルーム アプリケーションがクラッシュしたときの切り替え

1. Windows キーを 5 回連続で、素早く押します。 これによって、Windows のログオン画面が開きます。 
    
2. 管理者の資格情報でデスクトップにログインします。
    
    > [!NOTE]
    > このメソッドは、Skype ユーザーをログオフまたは、アプリケーションを正常に終了しませんが、場合を使用してアプリケーションが応答していませんでしたし、使用可能なその他の方法がありませんでした。 
  
3. 必要な管理タスクを実行します。
    
4. 完了したら、コンピューターを再起動します。
    
   コンソールは、マイクロソフト チームの会議室のアプリケーションを実行して、通常の操作モードに再起動します。 キーボードを削除するには、この手順を実行するために割り当てられる場合。
   ## <a name="troubleshooting-tips"></a>トラブルシューティングのヒント
   <a name="TS"> </a>

- 会議出席依頼があります (たとえば、2 つの企業では)、ドメインの境界を越えて送信される場合は表示されません。 このような場合、IT 管理者は、会議をスケジュールするのには外部のユーザーを許可するかどうかを決める必要があります。
    
- マイクロソフト チームの会議室には、Exchange 2010 を使用して Exchange の自動検出リダイレクトをサポートしていません。
    
- 一般は、オーディオ エンドポイントを使用しないことを無効にする IT 管理者のことをお勧めします。
    
- ルームのプレビューにミラー イメージが表示される場合、IT 管理者はカメラの電源をいったんオフにして再びオンにするか、カメラのリモート制御を使用してイメージの向きを反転させることでミラー イメージを修正できます。
    
- コンソールのタッチスクリーンへのアクセスが機能しなくなる問題が発生することが知られています。 このような場合は、マイクロソフト チームの会議室のシステムを再起動することによって問題が解決場合があります。
    
- 有線取り込みを介して PC をコンソールに接続すると、ローカルの音声が消失する問題が発生することが知られています。 このような場合は、PC を再起動することでローカルの音声再生の問題を解決できます。
    
