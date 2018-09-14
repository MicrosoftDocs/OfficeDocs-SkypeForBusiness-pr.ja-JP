---
title: Skype ルーム システム v2 のメンテナンスと運用
ms.author: jambirk
author: jambirk
ms.reviewer: davgroom
manager: serdars
ms.date: 5/10/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype ルーム システムの次世代を Skype ルーム システム v2 では、管理の詳細については、このトピックを参照してください。
ms.openlocfilehash: 52e02ff1f87d06088636b2f44706ec03c62675f3
ms.sourcegitcommit: b265545216ff36772d5dc2df381a9046bc71098e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/13/2018
ms.locfileid: "23965892"
---
# <a name="skype-room-systems-v2-maintenance-and-operations"></a>Skype ルーム システム v2 のメンテナンスと運用 
 
Skype ルーム システムの次世代を Skype ルーム システム v2 では、管理の詳細については、このトピックを参照してください。
  
Skype ルーム システム v2 は、ビジネス経験の豊富な共同の Skype 会議室に変換するように設計された、マイクロソフトの最新の会議ソリューションです。 ユーザーは慣れ親しんだ Skype for Business インターフェイスを活用し、IT 管理者は Windows 10 Skype Meeting アプリを簡単に展開および管理することができます。 Skype ルーム システム v2 は、Skype をビジネスの会議室に移動するのにはインストールの容易さの LCD パネルと同様に既存の機器を活用するよう設計されています。
  
リモート管理は、 [Skype ルーム システムの計画 v2 管理 OMS を使用して](../../plan-your-deployment/clients-and-devices/oms-management.md)、 [OMS を使用して Skype ルーム システムの展開 v2 の管理](../../deploy/deploy-clients/with-oms.md)、および管理の[で説明したように運用管理スイート (OMS) を使用して、追加の構成OMS を使用して Skype ルーム システム v2 のデバイス](oms.md)。 [Skype ルーム システム v2 の管理コンソールの設定を XML 構成ファイルでリモートから](xml-config-file.md)、カスタムの表示テーマを適用する必要があるかもしれません。 
  
## <a name="collecting-logs-on-skype-room-systems-v2"></a>Skype Room Systems バージョン 2 でのログの収集
<a name="Logs"> </a>

ログを収集するには、Skype ルーム システム v2 のアプリケーションに付属しているログ収集スクリプトを呼び出す必要があります。 管理者モードで、管理者特権のコマンド プロンプトを開始して、次のコマンドを発行します。
  
```
powershell -ExecutionPolicy unrestricted c:\rigel\x64\scripts\provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
```

ログは ZIP ファイルとして c:\rigel に出力されます。
  
## <a name="front-of-room-display-settings"></a>前面の会議室ディスプレイの設定
<a name="Display"> </a>

前面の会議室ディスプレイを拡張モードに構成します。 これが必ず、コンソールを表示するには、ディスプレイの電源を入れ直すと、UI は複製されません。
  
> [!NOTE]
> 屋内ディスプレイの前面として使用される消費者向け TV では、スタンバイ モードからアクティブなビデオ ソースに自動的に切り替わるように、HDMI の CEC (Consumer Electronics Control) 機能をサポート/有効にする必要があります。 この機能はすべての TV でサポートされるものではありません。 
  
## <a name="skype-room-systems-v2-reset-factory-restore"></a>Skype Room Systems バージョン 2 のリセット (工場出荷時状態への復元)
<a name="Reset"> </a>

Skype ルーム システム v2 がうまく実行されていない、工場出荷時リセットを実行することが役立ちます。 これで**この PC をリセット**するの下にある [**回復**] タブの [アプリケーションの設定を行うを選択**を開始**し、**すべて削除します。** デバイスをリセットするのには、画面の指示に従います。
  
> [!NOTE]
> Skype ルーム システム v2 が Windows のリセット処理中に、**アプリの削除と設定のファイルを保存、個人用ファイルを保持**] オプションが選択されている場合に使用できなくなる、既知の問題があります。 操作を行います_しない_このオプションを使用します。
  
## <a name="supported-remote-options"></a>サポートされるリモート オプション
<a name="RemoteOptions"> </a>

次の表に、可能なリモート操作とそれを実行するために使用できる方法を示します。
  

|**ワークグループ **|**ドメインに参加していない場合**|**ドメインに参加している場合**|
|:-----|:-----|:-----|
|再起動  <br/> |リモート デスクトップ  <br/> リモート Powershell  <br/> |(さらに設定する必要があります)、リモート デスクトップ  <br/> リモート Powershell を (さらに設定する必要があります)  <br/> SCCM  <br/> |
|OS の更新  <br/> |Windows Update  <br/> |Windows Update  <br/> WSUS  <br/> |
|アプリの更新  <br/> |	Windows ストア  <br/> |Windows ストア  <br/> SCCM  <br/> |
|Skype アカウントの構成  <br/> |	現在サポートされていません  <br/> |	現在サポートされていません  <br/> |
|ログへのアクセス  <br/> |現在サポートされていません  <br/> |	現在サポートされていません  <br/> |
   
## <a name="configuring-group-policy-for-skype-room-systems-v2"></a>Skype Room Systems バージョン 2 のグループ ポリシーの構成
<a name="GroupPolicy"> </a>

このセクションでは、Skype ルーム システム v2 が正しく機能するために依存しているシステムの設定について説明します。 Skype ルーム システム v2 をドメインに参加させるときは、グループ ポリシーが次の表の設定を上書きしないことを確認します。
  

|**設定**|**により、**|
|:-----|:-----|
|HKLM\SOFTWARE\Microsoft\Windows 指定できます AdminAutoLogon = (REG_SZ) 1  <br/> |起動するように Skype ルーム システム v2 を有効に  <br/> |
|電源管理 -\> AC、画面をオフに 10 分後  <br/> 電源管理 -\> Ac システムをスリープ状態を配置しません。  <br/> |により、接続されている表示をオフにして、自動的に復帰する Skype ルーム システム v2  <br/> |
|net accounts /maxpwage:unlimited  <br/> または、ローカル アカウントでパスワードの期限切れを無効にする同等の手段。この設定に失敗すると、パスワードの期限が切れていることが通知され、Skype アカウントのログオンが失敗する原因になります。この影響はマシン上のすべてのローカル アカウントに及びます。したがって、この設定に失敗すると、ボックスの管理アカウントも最終的には期限切れになります。  <br/> |常にログインするように Skype アカウントを有効にする  <br/> |
   
グループ ポリシーを使用してファイルを転送するは、[構成ファイルの項目](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx)で説明します。
  
## <a name="remote-management-using-powershell"></a>PowerShell を使用したリモート管理
<a name="RemotePS"> </a>

PowerShell を使用して、次の管理操作をリモートで実行することができます (スクリプトのサンプルについては、次の表を参照してください)。
  
- 接続されているデバイスの取得
    
- アプリの状態の取得
    
- システム情報の取得
    
- システムの再起動
    
- ログの取得
    
- ファイルを転送する (ドメインに参加している Skype ルーム システム バージョン 2 が必要です)
    
> [!NOTE]
> 既定では、この機能はオフです。 Skype ルーム システム v2 システムの環境に次の操作を実行するリモートの PowerShell を有効にする必要があります。 リモート PowerShell を有効にする方法についての情報を**[有効にする PSRemoting](https://technet.microsoft.com/library/hh849694.aspx)** のマニュアルを参照してください。
  
たとえば、次のようにリモート PowerShell を有効にできます。
  
1. Skype ルーム システム v2 デバイスの管理者のユーザーとしてサインインします。
    
2. 管理者特権の PowerShell コマンド プロンプトを開きます。
    
3. 次のコマンドを入力してください: 有効にする-PSRemoting - 強制
    
管理操作を実行するには、次の操作を実行します。
  
1. Skype ルーム システム v2 のデバイスでの PowerShell コマンドを実行する権限を持つアカウントの資格情報で PC にサインインします。
    
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

既定では、Skype ルーム システム v2 は、デバイスの通常のインターネット アクセスが必要なので、Skype ルーム システム v2 のソフトウェアの最新バージョンを取得する Windows ストアに接続しようとします。 必ずサポートの問題に関して、マイクロソフトに連絡する前にアプリケーションの最新バージョンの Skype ルーム システムのバージョン 2 のデバイスが読み込まれます。
  
既定は、Skype ルーム システム v2 は、オペレーティング システムを取得するために Windows の更新プログラムと USB 周辺機器のファームウェアの更新に接続し、構成済みの業務時間外をインストールします。 営業時間を設定するには、管理者アカウントでサインインし、設定アプリを実行します。
  
APPX の適切なファイルとの[『 導入ガイド 』](https://go.microsoft.com/fwlink/?linkid=851168) (からの依存関係を取得することをした場合、手動で更新プログラムを管理する通常の手順に従って、[ビジネス向けのマイクロソフト ストア](https://businessstore.microsoft.com/store)の[オフライン アプリケーションを配布](https://docs.microsoft.com/microsoft-store/distribute-offline-apps)することはできません。[Skype ルーム システム v2 のコンソールを構成](../../deploy/deploy-clients/console.md)する方法) と SCCM を使用できます。 展開キットのリリースも遅れて、ストアのリリースでは、最新の利用可能なビルドを常に一致可能性がありますように。
  
### <a name="to-update-using-powershell"></a>Powershell を使用して更新するのには

1. 共有デバイスには、 [MSI](https://go.microsoft.com/fwlink/?linkid=851168)にアクセスできるインストール パッケージを展開します。
    
2. Skype ルーム システム v2 ・ デバイスを使用し、変更することを対象とする次のスクリプトを実行\<共有\>デバイスには、必要に応じて共有します。
    
```
Add-AppxPackage -Update -ForceApplicationShutdown -Path '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\*.appx' -DependencyPath (Get-ChildItem '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\Dependencies\x64\*.appx' | Foreach-Object {$_.FullName})
```

## <a name="admin-mode-and-device-management"></a>管理者モードとデバイス管理
<a name="AdminMode"> </a>

プライベート CA 証明書を手動でインストールするように、一部の管理機能は、管理者モードで Surface Pro デバイスを配置する必要があります。 
  
### <a name="switching-to-admin-mode-and-back-when-the-skype-room-systems-v2-app-is-running"></a>管理者モードと Skype ルーム システム v2 のアプリケーションを実行しているときの切り替え

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
    
11. 画面の左端にある [ユーザー アカウントのアイコンを選択し、 **Skype**Skype ルーム システム v2 に戻ります。
    
    **Skype**ユーザーが一覧にない場合は**他のユーザー**を選択し、入力をする必要があります**です。 \skype**として、ユーザー名、およびサインインします。
    
コンソールは、その通常の操作モードに戻るようになりました。次の手順では、1 つは既に接続されていない場合、デバイスにキーボードを接続する必要があります。 
  
### <a name="switching-to-admin-mode-and-back-when-the-skype-room-systems-v2-app-crashes"></a>管理者モードと Skype ルーム システム v2 のアプリケーションがクラッシュしたときの切り替え

1. Windows キーを 5 回連続で、素早く押します。これによって、Windows のログオン画面が開きます。 
    
2. 管理者の資格情報でデスクトップにログインします。
    
    > [!NOTE]
    > このメソッドは、Skype ユーザーをログオフまたは、アプリケーションを正常に終了しませんが、場合を使用してアプリケーションが応答していませんでしたし、使用可能なその他の方法がありませんでした。 
  
3. 必要な管理タスクを実行します。
    
4. 完了したら、コンピューターを再起動します。
    
 Skype ルーム システム v2 のアプリケーションを実行して、通常の操作モードに、コンソールを再起動します。 キーボードを削除するには、この手順を実行するために割り当てられる場合。
## <a name="troubleshooting-tips"></a>トラブルシューティングのヒント
<a name="TS"> </a>

- 会議出席依頼があります (たとえば、2 つの企業では)、ドメインの境界を越えて送信される場合は表示されません。 このような場合、IT 管理者は、会議をスケジュールするのには外部のユーザーを許可するかどうかを決める必要があります。
    
- Skype ルーム システム v2 では、Exchange 2010 を使用して Exchange の自動検出リダイレクトをサポートしていません。
    
- 一般は、オーディオ エンドポイントを使用しないことを無効にする IT 管理者のことをお勧めします。
    
- ルームのプレビューにミラー イメージが表示される場合、IT 管理者はカメラの電源をいったんオフにして再びオンにするか、カメラのリモート制御を使用してイメージの向きを反転させることでミラー イメージを修正できます。
    
- コンソールのタッチスクリーンへのアクセスが機能しなくなる問題が発生することが知られています。 このような場合は、Skype ルーム システム v2 のシステムを再起動することによって問題が解決場合があります。
    
- 有線取り込みを介して PC をコンソールに接続すると、ローカルの音声が消失する問題が発生することが知られています。 このような場合は、PC を再起動することでローカルの音声再生の問題を解決できます。
    
