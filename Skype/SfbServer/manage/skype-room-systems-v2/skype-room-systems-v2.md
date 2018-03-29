---
title: Skype Room Systems バージョン 2 を管理する
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 39d7dc65-22c3-400f-91f1-87ed2fd792b6
description: Skype ルーム システムの次世代を Skype ルーム システム v2 では、管理の詳細については、このトピックを参照してください。
ms.openlocfilehash: 5ef699bed1a77fc48f59ba4c5f8eb78ccc286ef7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="manage-skype-room-systems-v2"></a>Skype Room Systems バージョン 2 を管理する
 
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

前面の会議室ディスプレイを拡張モードに構成します。 この操作により、ディスプレイの電源サイクル時にディスプレイ上にコンソール UI が重複しません。
  
> [!NOTE]
> 屋内ディスプレイの前面として使用される消費者向け TV では、スタンバイ モードからアクティブなビデオ ソースに自動的に切り替わるように、HDMI の CEC (Consumer Electronics Control) 機能をサポート/有効にする必要があります。 この機能はすべての TV でサポートされるものではありません。 
  
## <a name="skype-room-systems-v2-reset-factory-restore"></a>Skype Room Systems バージョン 2 のリセット (工場出荷時状態への復元)
<a name="Reset"> </a>

Skype ルーム システム v2 がうまく実行されていない、工場出荷時リセットを実行することができます。 これの設定のアプリケーションで、[このコンピューターのリセット」ヘッダーの下に「回復」タブから、選択"開始"の後に「"すべて削除するです。 残りのプロンプトの求めに従って、デバイスをリセットします。
  
> [!NOTE]
> Skype ルーム システム v2 が Windows のリセット処理中に「ファイルを保存 - アプリケーションと設定が削除が、個人用ファイルを保持」オプションが選択されている場合に使用できなくなる既知問題があります。 このオプションは使用**しない**でください。
  
## <a name="supported-remote-options"></a>サポートされるリモート オプション
<a name="RemoteOptions"> </a>

次の表に、可能なリモート操作とそれを実行するために使用できる方法を示します。
  

|**ワークグループ**|**ドメインに参加していません。**|**ドメインに参加して**|
|:-----|:-----|:-----|
|再起動  <br/> |リモート デスクトップ  <br/> リモート Powershell  <br/> |(さらに設定する必要があります)、リモート デスクトップ  <br/> リモート Powershell を (さらに設定する必要があります)  <br/> SCCM  <br/> |
|OS の更新  <br/> |Windows Update  <br/> |Windows Update  <br/> WSUS  <br/> |
|アプリの更新  <br/> |	Windows ストア  <br/> |Windows ストア  <br/> SCCM  <br/> |
|Skype アカウントの構成  <br/> |	現在サポートされていません  <br/> |	現在サポートされていません  <br/> |
|ログへのアクセス  <br/> |現在サポートされていません  <br/> |	現在サポートされていません  <br/> |
||||
   
## <a name="configuring-group-policy-for-skype-room-systems-v2"></a>Skype Room Systems バージョン 2 のグループ ポリシーの構成
<a name="GroupPolicy"> </a>

このセクションでは、Skype ルーム システム v2 が正しく機能するために依存しているシステムの設定について説明します。 Skype ルーム システム v2 をドメインに参加させるときに、グループ ポリシーが次の設定をオーバーライドしないことを確認してください。
  

|**設定**|**により、**|
|:-----|:-----|
|HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AdminAutoLogon = (dword) 1  <br/> |起動するように Skype ルーム システム v2 を有効に  <br/> |
|電源管理 -\> AC、画面をオフに 10 分後  <br/> 電源管理 -\> Ac システムをスリープ状態を配置しません。  <br/> |により、接続されている表示をオフにして、自動的に復帰する Skype ルーム システム v2  <br/> |
|net accounts /maxpwage:unlimited  <br/> またはローカル アカウントのパスワードの有効期限を無効にするのと同等のことを意味します。 これを行うには、障害が発生する Skype アカウントの期限切れのパスワードについて苦情を言ってログオンが失敗すると、最終的に。 したがってこれを設定して必要があります管理者アカウント、最終的にも期限切れにする] ボックスに、コンピューター上のすべてのローカル アカウントに影響を与えるこのこと注意してください。  <br/> |常にログインするように Skype アカウントを有効にする  <br/> |
   
グループ ポリシーを使用してファイルを転送するは、[構成ファイルの項目](https://technet.microsoft.com/en-us/library/cc772536%28v=ws.11%29.aspx)で説明します。
  
## <a name="remote-management-using-powershell"></a>PowerShell を使用したリモート管理
<a name="RemotePS"> </a>

PowerShell を使用して次の管理操作をリモートで実行できます (スクリプトのサンプルについては下記の表を参照してください)。
  
- 接続されているデバイスの取得
    
- アプリの状態の取得
    
- システム情報の取得
    
- システムの再起動
    
- ログの取得
    
- ファイル転送 (Skype ルーム システム v2 がドメインに参加している必要があります)
    
> [!NOTE]
> 既定では、この機能はオフです。 Skype ルーム システム v2 システムの環境に次の操作を実行するリモートの PowerShell を有効にする必要があります。 リモート PowerShell を有効にする方法については**[有効にする PSRemoting](https://technet.microsoft.com/en-us/library/hh849694.aspx)**のマニュアルを参照してください。
  
たとえば、次のようにリモート PowerShell を有効にできます。
  
1. Skype ルーム システム v2 デバイスの管理者のユーザーとしてサインインします。
    
2. 管理者特権で PowerShell コマンド プロンプトを起動します。
    
3. 次のコマンドを入力してください: 有効にする-PSRemoting - 強制
    
管理操作を実行するには、次の操作を実行します。
  
1. Skype ルーム システム v2 のデバイスでの PowerShell コマンドを実行する権限を持つアカウントの資格情報を持つ PC にサインインします。
    
2. PC で通常の PowerShell コマンド プロンプトを起動します。
    
3. 次の表からコマンド テキストをコピーして、プロンプトに貼り付けます。
    
4. 交換`<Device fqdn>`FQDN の値を持つフィールドが、環境に対応します。
    
5. 交換*\<のパス\>*SkypeSettings.xml 構成ファイルのマスター (またはテーマのイメージ) のローカル パスとファイル名とします。
    
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

XML 構成ファイルまたはテーマのグラフィックをプッシュします)
  
```
$movefile = "<path>";
$targetDevice = "\\<Device fqdn> \Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState\SkypeSettings.xml"; 
Copy-Item $movefile $targetDevice 
```

## <a name="software-updates"></a>ソフトウェアの更新
<a name="SWupdate"> </a>

既定では、Skype ルーム システム v2 はデバイスの通常のインターネット アクセスが必要なので、Skype ルーム システム v2 のソフトウェアの最新バージョンを取得する Windows ストアへの接続を試みます。 Skype ルーム システム v2 デバイスが読み込まれるアプリケーションの最新バージョンとサポートの問題をマイクロソフトに連絡する前に必ずしてください。
  
既定では、Skype ルーム システム v2 は OS の取得と USB 周辺機器のファームウェアの更新プログラム Windows Update に接続し、構成済みの業務時間外にインストールします。 営業時間を設定するには、管理者アカウントでサインインし、設定アプリを実行します。
  
APPX の適切なファイルとの[『 導入ガイド 』](https://go.microsoft.com/fwlink/?linkid=851168) (からの依存関係を取得することをした場合、手動で更新プログラムを管理する通常の手順に従って、[ビジネス向けのマイクロソフト ストア](https://businessstore.microsoft.com/en-us/store)の[オフライン アプリケーションを配布](https://docs.microsoft.com/en-us/microsoft-store/distribute-offline-apps)することはできません。[Skype ルーム システム v2 のコンソールを構成](../../deploy/deploy-clients/console.md)する方法) と SCCM を使用できます。 デプロイメント キットのリリースは、ストアのリリースよりも後になるため、最新の入手可能な最新ビルドに必ずしも一致しない可能性があります。
  
### <a name="to-update-using-powershell"></a>Powershell を使用して更新するのには

1. [MSI](https://go.microsoft.com/fwlink/?linkid=851168)のインストールとデバイスのアクセス可能な共有にパッケージを抽出します。
    
2. Skype ルーム システム v2 ・ デバイスを使用し、変更することを対象とする次のスクリプトを実行\<共有\>デバイスには、必要に応じて共有します。
    
  ```
  Add-AppxPackage -Update -ForceApplicationShutdown -Path \\<share>\Rigel\x64\Ship\AppPackages\*\*.appx -DependencyPath (Get-ChildItem \\<share>\Rigel\x64\Ship\AppPackages\*\Dependencies\x64\*.appx | Foreach-Object {$_.FullName}) 

  ```

## <a name="admin-mode-and-device-management"></a>管理者モードとデバイス管理
<a name="AdminMode"> </a>

プライベート CA 証明書の手動によるインストールのような一部の管理機能では、Surface 4 デバイスを管理者モードにする必要があります。 
  
### <a name="switching-to-admin-mode-and-back-when-the-skype-room-systems-v2-app-is-running"></a>管理者モードと Skype ルーム システム v2 のアプリケーションを実行しているときの切り替え

1. 現在の通話を切って、ホーム画面に戻ります。
    
2. 歯車のアイコンをクリックし、メニューを表示 (オプションは、**設定**、**ユーザー補助の設定**、および**デバイスの再起動**) します。
    
3. [**設定**] を選択します。
    
4. 管理者パスワードを入力します。 セットアップ画面が表示されます。
    
    > [!NOTE]
    > デバイスがドメインに参加していない場合、既定によりローカルの管理アカウント (ユーザー名「Admin」) が使用されます。このアカウントの既定のパスワードは「sfb」ですが、セキュリティ上の理由により所属する組織によってできるだけ早く変更されることが推奨されます。コンピューターがドメインに参加している場合、適切な権限のドメイン アカウントでサインインできます。 
  
5. 左列にある [**Windows の設定**] をクリックします。
    
6. [**管理サインインに移動**] を選択します。
    
7. 管理者パスワードを入力します。 これによって、アプリから正常にログオフされ、Windows のログイン画面が表示されます。 
    
8. 管理者の資格情報でデスクトップにログインします。デバイスの管理に必要な権限を持つことになります。
    
9. 必要な管理タスクを実行します。
    
10. 管理者アカウントからサイン アウトします。
    
11. 画面の一番左上のユーザー アカウントのアイコンを選択して Skype ルーム システム v2 に戻るし、 **Skype**を選択します。
    
    **Skype**ユーザーが一覧にない場合は**他のユーザー**を選択し、入力をする必要があります**です。 \skype**として、ユーザー名、およびサインインします。
    
 コンソールは、その通常の操作モードに戻るようになりました。次の手順では、1 つは既に接続されていない場合、デバイスにキーボードを接続する必要があります。 
  
### <a name="switching-to-admin-mode-and-back-when-the-skype-room-systems-v2-app-crashes"></a>管理者モードと Skype ルーム システム v2 のアプリケーションがクラッシュしたときの切り替え

1. Windows キーを 5 回連続で、素早く押します。これによって、Windows のログオン画面が開きます。 
    
2. 管理者の資格情報でデスクトップにログインします。
    
    > [!NOTE]
    > この方法は、Skype ユーザーをログオフさせたりアプリを正常終了させることはありませんが、アプリが応答しない場合やその他の方法が使用できない場合にのみ使用するようにしてください。 
  
3. 必要な管理タスクを実行します。
    
4. 終了したら、コンピューターを再起動します。
    
 Skype ルーム システム v2 のアプリケーションを実行して、通常の操作モードに、コンソールを再起動します。 キーボードが接続されている場合は、取り外してこの手順を実行することができます。
## <a name="troubleshooting-tips"></a>トラブルシューティングのヒント
<a name="TS"> </a>

- 会議の招待状は、ドメイン境界 (たとえば、2 つの会社間) を越えて送信すると表示されない場合があります。 このような場合、IT 管理者は外部ユーザーに対して会議のスケジュール設定を許可するかどうかを決定する必要があります。
    
- Skype ルーム システム v2 では、Exchange 2010 を使用して Exchange の自動検出リダイレクトをサポートしていません。
    
- 通常、IT 管理者は使用する予定のないオーディオ エンドポイントをすべて無効にすることをお勧めします。
    
- ルームのプレビューにミラー イメージが表示される場合、IT 管理者はカメラの電源をいったんオフにして再びオンにするか、カメラのリモート制御を使用してイメージの向きを反転させることでミラー イメージを修正できます。
    
- コンソールのタッチスクリーンへのアクセスが機能しなくなる問題が発生することが知られています。 このような場合は、Skype ルーム システム v2 のシステムを再起動することによって問題が解決場合があります。
    
- 有線取り込みを介して PC をコンソールに接続すると、ローカルの音声が消失する問題が発生することが知られています。 このような場合は、PC を再起動することでローカルの音声再生の問題を解決できます。
    
## <a name="see-also"></a>この手順は役に立ちましたか? 役に立った場合は、この記事の下でお知らせください。役に立たなかった場合は、わかりにくかった部分をお知らせください。いただいたフィードバックを元に手順を再確認します。
<a name="TS"> </a>

#### 

[Skype ルームの計画システム v2](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[Skype の部屋を配置するシステム v2](../../deploy/deploy-clients/room-systems-v2.md)
  
[Skype ルーム システム v2 のコンソールを構成します。](../../deploy/deploy-clients/console.md)
  
[Skype ルーム システム v2 のコンソールの設定を XML 構成ファイルを使用してリモートで管理します。](xml-config-file.md)

