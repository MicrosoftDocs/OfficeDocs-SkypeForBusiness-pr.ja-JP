---
title: Microsoft Teams の会議室のメンテナンスと操作
ms.author: v-lanac
author: lanachin
ms.reviewer: davgroom
manager: serdars
ms.date: 5/10/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
ms.collection: M365-voice
localization_priority: Normal
description: このトピックでは、次世代の Skype Room Systems である Microsoft Teams のルームの管理について説明します。
ms.openlocfilehash: b32ac786c7c039bd1eaab060e12b7141a8d8cf72
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34288564"
---
# <a name="microsoft-teams-rooms-maintenance-and-operations"></a>Microsoft Teams の会議室のメンテナンスと操作 
 
このトピックでは、次世代の Skype Room Systems である Microsoft Teams のルームの管理について説明します。
  
Microsoft Teams room は、Microsoft の最新の会議ソリューションであり、会議室を豊かな共同作業環境に変革することを目的としています。 ユーザーには、使い慣れた Microsoft Teams または Skype for Business インターフェイスが採用され、IT 管理者は、Windows 10 の Skype 会議アプリの展開と管理が簡単になります。 Microsoft Teams room は、インストールを容易にするために LCD パネルなどの既存の機器を活用して、Microsoft Teams または Skype for Business を会議室に持ち込むことを目的としています。
  
追加の構成では、「 [Microsoft teams のルーム管理を Azure monitor で計画](azure-monitor-plan.md)する」および「azure モニターを使用して[Microsoft teams のルーム管理を展開](azure-monitor-deploy.md)する」の説明に従って、microsoft azure モニターを使用してリモート管理を行うことができます。 [Microsoft Teams は、Azure モニターを使用して](azure-monitor-deploy.md)います。 また、 [Microsoft Teams 会議コンソールの設定を XML 構成ファイルを使ってリモートで管理](xml-config-file.md)することもできます。これには、カスタム表示テーマの適用が含まれます。 
  
## <a name="collecting-logs-on-microsoft-teams-rooms"></a>Microsoft Teams ルームでのログの収集
<a name="Logs"> </a>

ログを収集するには、Microsoft Teams のルームアプリに付属しているログ収集スクリプトを呼び出す必要があります。 管理者モードで、管理者特権のコマンド プロンプトを開始して、次のコマンドを発行します。
  
```
powershell -ExecutionPolicy unrestricted c:\rigel\x64\scripts\provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
```

ログは ZIP ファイルとして c:\rigel に出力されます。
  
## <a name="front-of-room-display-settings"></a>前面の会議室ディスプレイの設定
<a name="Display"> </a>

前面の会議室ディスプレイを拡張モードに構成します。 この操作を行うと、ディスプレイの電源を入れたときに、そのディスプレイに本体の UI が複製されることがなくなります。
  
> [!NOTE]
> 屋内ディスプレイの前面として使用される消費者向け TV では、スタンバイ モードからアクティブなビデオ ソースに自動的に切り替わるように、HDMI の CEC (Consumer Electronics Control) 機能をサポート/有効にする必要があります。 この機能はすべての TV でサポートされるものではありません。 
  
## <a name="microsoft-teams-rooms-reset-factory-restore"></a>Microsoft Teams の会議室のリセット (工場出荷時の復元)
<a name="Reset"> </a>

Microsoft Teams の会議室が正常に動作していない場合は、出荷時のリセットを実行してください。 この操作は、[**回復**] タブの [設定] アプリで行うことができます。 [**この PC のリセット**] で、[**作業の開始**] を選び、[**すべて削除**] を選びます。 残りの指示に従って、デバイスをリセットします。
  
> [!NOTE]
> **[自分のファイルを保持する] でアプリと設定を削除**した場合、Microsoft Teams の会議室が使用できなくなるという既知の問題がありますが、Windows のリセットプロセス中に個人用ファイルオプションが選択されたままになります。 この__ オプションは使用しないでください。
  
## <a name="supported-remote-options"></a>サポートされるリモート オプション
<a name="RemoteOptions"> </a>

次の表に、可能なリモート操作とそれを実行するために使用できる方法を示します。
  

|**ワークグループ **|**ドメインに参加していない場合**|**ドメインに参加している場合**|
|:-----|:-----|:-----|
|再起動  <br/> |リモート デスクトップ  <br/> リモート Powershell  <br/> |リモートデスクトップ (さらに構成が必要)  <br/> リモート Powershell (さらに構成が必要)  <br/> SCCM  <br/> |
|OS の更新  <br/> |Windows Update  <br/> |Windows Update  <br/> WSUS  <br/> |
|アプリの更新  <br/> |	Windows ストア  <br/> |Windows ストア  <br/> SCCM  <br/> |
|Skype アカウントの構成  <br/> |現在サポートされていません  <br/> |	現在サポートされていません  <br/> |
|ログへのアクセス  <br/> |	現在サポートされていません  <br/> |	現在サポートされていません  <br/> |
   
## <a name="configuring-group-policy-for-microsoft-teams-rooms"></a>Microsoft Teams ルームのグループポリシーを構成する
<a name="GroupPolicy"> </a>

このセクションでは、Microsoft Teams のルームが適切に機能するために依存するシステム設定について説明します。 Microsoft Teams のルームをドメインに参加させる場合は、次の表の設定を上書きしないようにグループポリシーを設定します。
  

|**]**|**よう**|
|:-----|:-----|
|HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (REG_SZ) 1  <br/> |Microsoft Teams のルームを起動できるようにします。  <br/> |
|電源管理-\> AC 電源、10分後に画面をオフにする  <br/> 電源管理-\> AC で、システムをスリープ状態にしない  <br/> |Microsoft Teams の会議機能を有効にして、添付されたディスプレイをオフにし、自動的にスリープ状態を解除する  <br/> |
|net accounts /maxpwage:unlimited  <br/> または、ローカルアカウントのパスワードの有効期限を無効にすることもできます。 そうしないと、有効期限が切れたパスワードについて、Skype アカウントがログオンに失敗することになります。 これは、マシン上のすべてのローカルアカウントに影響を与えるため、これを設定しないと、そのボックスの管理者アカウントも最終的に有効期限切れになります。  <br/> |常にログインするように Skype アカウントを有効にする  <br/> |
   
グループポリシーを使用してファイルを転送する方法については[、「ファイルを構成](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx)する」をお勧めします。
  
## <a name="remote-management-using-powershell"></a>PowerShell を使用したリモート管理
<a name="RemotePS"> </a>

PowerShell を使用して、次の管理操作をリモートで実行できます (スクリプトサンプルについては、以下の表を参照してください)。
  
- 接続されているデバイスの取得
    
- アプリの状態の取得
    
- システム情報の取得
    
- システムの再起動
    
- ログの取得
    
- ファイルを転送する (ドメインに参加している Microsoft Teams ルームが必要)
    
> [!NOTE]
> 既定では、この機能はオフです。 以下の操作を実行するには、Microsoft Teams のルームシステムの環境に対してリモート PowerShell を有効にする必要があります。 リモート PowerShell を有効にする方法については、「 **[enable-PSRemoting](https://technet.microsoft.com/library/hh849694.aspx)** のドキュメントを参照してください。
  
たとえば、次のようにリモート PowerShell を有効にできます。
  
1. Microsoft Teams の会議室のデバイスで、管理者としてサインインします。
    
2. 管理者特権の PowerShell コマンドプロンプトを開きます。
    
3. 次のコマンドを入力します。Enable-PSRemoting -force
    
管理操作を実行するには、次の操作を実行します。
  
1. Microsoft Teams 室のデバイスで PowerShell コマンドを実行する権限を持つ、アカウントの資格情報を使って PC にサインインします。
    
2. PC で通常の PowerShell コマンドプロンプトを開きます。
    
3. 次の表からコマンドテキストをコピーし、メッセージに貼り付けます。
    
4. 使用`<Device fqdn>`している環境に適した FQDN 値をフィールドに置き換えます。
    
5. * \<Path\> *を、マスター skypesettings (またはテーマの画像) のファイル名とローカルパスに置き換えます。
    
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

XML 構成ファイル (またはテーマグラフィック) をプッシュする
  
```
$movefile = "<path>";
$targetDevice = "\\<Device fqdn> \Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState\SkypeSettings.xml"; 
Copy-Item $movefile $targetDevice 
```

## <a name="software-updates"></a>ソフトウェアの更新
<a name="SWupdate"> </a>

既定では、Microsoft Teams の会議は、Microsoft Teams ルームソフトウェアの最新バージョンを取得するために Windows ストアに接続しようとします。そのため、デバイスでは、通常のインターネットアクセスが必要になります。 サポートの問題が発生した場合は、Microsoft Teams の会議室のデバイスが最新バージョンのアプリと共に読み込まれていることを確認してください。
  
既定では、Microsoft Teams のルームは Windows Update に接続して、オペレーティングシステムと USB 周辺機器のファームウェア更新プログラムを取得し、構成された勤務時間外にインストールします。 営業時間を設定するには、管理者アカウントでサインインし、設定アプリを実行します。
  
更新プログラムを手動で管理する必要があるが、一般[法人向け Microsoft Store](https://businessstore.microsoft.com/store)の通常の手順に従って[オフラインアプリの配布](https://docs.microsoft.com/microsoft-store/distribute-offline-apps)を行うことができない場合は、適切な APPX ファイルと依存関係を[展開キット](https://go.microsoft.com/fwlink/?linkid=851168)から入手できます (fromSCCM で使用できる[Microsoft Teams のルーム本体を構成](console.md)する手順)。 展開キットのリリースがストアのリリースよりも遅れているため、常に最新のビルドと一致しない可能性があります。
  
### <a name="to-update-using-powershell"></a>Powershell を使用して更新するには

1. インストール[MSI](https://go.microsoft.com/fwlink/?linkid=851168)からデバイスがアクセスできる共有にパッケージを抽出します。
    
2. 次のスクリプトを実行して、Microsoft Teams の会議\<室\>のデバイスをターゲットにし、必要に応じて共有をデバイス共有に変更します。
    
```
Add-AppxPackage -Update -ForceApplicationShutdown -Path '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\*.appx' -DependencyPath (Get-ChildItem '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\Dependencies\x64\*.appx' | Foreach-Object {$_.FullName})
```

## <a name="admin-mode-and-device-management"></a>管理者モードとデバイス管理
<a name="AdminMode"> </a>

プライベート CA 証明書を手動でインストールするなどの一部の管理機能には、Surface Pro デバイスを管理モードで配置する必要があります。 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running"></a>Microsoft Teams のルームアプリが実行されているときに、管理モードに切り替えて戻る

1. 進行中の通話を切断して、ホーム画面に戻ります。
    
2. 歯車アイコンを選択し、メニューを開きます (オプションは [**設定**]、[**アクセシビリティ**]、[**デバイスの再起動**])。
    
3. [**設定**] を選択します。
    
4. 管理者パスワードを入力します。 セットアップ画面が表示されます。
    
    > [!NOTE]
    > デバイスがドメインに参加していない場合は、ローカルの管理者アカウント (ユーザー名 "管理者") が既定で使用されます。 このアカウントの既定のパスワードは「sfb」ですが、セキュリティ上の理由により所属する組織によってできるだけ早く変更されることが推奨されます。 コンピューターがドメインに参加している場合は、適切な権限を持つドメインアカウントでサインインできます。 
  
5. 左側の列で、[ **Windows の設定**] を選択します。
    
6. [**管理サインインに移動**] を選択します。
    
7. 管理者パスワードを入力します。 これによって、アプリから正常にログオフされ、Windows のログイン画面が表示されます。 
    
8. 管理者の資格情報でデスクトップにログインします。 デバイスを管理するために必要な権限が与えられます。
    
9. 必要な管理タスクを実行します。
    
10. 管理者アカウントからサイン アウトします。
    
11. 画面左側のユーザーアカウントアイコンを選択し、[ **Skype**] を選択して、Microsoft Teams のルームに戻ります。
    
    **Skype**ユーザーが表示されていない場合は、[**他のユーザー** ] を選択し、ユーザー名として「 **.\skype** 」と入力して、サインインしなければならない場合があります。
    
これで本体が通常の操作モードに戻ります。次の手順では、デバイスがまだ接続されていない場合は、そのデバイスにキーボードをアタッチする必要があります。 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-crashes"></a>Microsoft Teams の会議アプリがクラッシュしたときに、管理モードに切り替えて戻る

1. Windows キーを 5 回連続で、素早く押します。 これによって、Windows のログオン画面が開きます。 
    
2. 管理者の資格情報でデスクトップにログインします。
    
    > [!NOTE]
    > この方法では、Skype ユーザをログオフしたり、アプリを正常に終了したりすることはありませんが、アプリが応答しなくなった場合や、その他の方法が利用できない場合に使用します。 
  
3. 必要な管理タスクを実行します。
    
4. 完了したら、コンピューターを再起動します。
    
   本体は、Microsoft Teams のルームアプリを実行して、通常の操作モードで再起動します。 この手順を実行できるように設定されている場合は、キーボードを削除することができます。
   ## <a name="troubleshooting-tips"></a>トラブルシューティングのヒント
   <a name="TS"> </a>

- 会議の出席依頼は、(2 つの会社間など) ドメインの境界を越えて送信された場合には表示されない場合があります。 このような場合、IT 管理者は、外部ユーザーによる会議のスケジュールを許可するかどうかを決定する必要があります。
    
- Microsoft Teams のルームは、Exchange 2010 経由の Exchange 自動検出リダイレクトをサポートしていません。
    
- 一般的に、IT 管理者が使用する必要のないオーディオエンドポイントを無効にすることをお勧めします。
    
- ルームのプレビューにミラー イメージが表示される場合、IT 管理者はカメラの電源をいったんオフにして再びオンにするか、カメラのリモート制御を使用してイメージの向きを反転させることでミラー イメージを修正できます。
    
- コンソールのタッチスクリーンへのアクセスが機能しなくなる問題が発生することが知られています。 このような場合、Microsoft Teams のルームシステムを再起動すると、問題が解決されることがあります。
    
- 有線取り込みを介して PC をコンソールに接続すると、ローカルの音声が消失する問題が発生することが知られています。 このような場合は、PC を再起動することでローカルの音声再生の問題を解決できます。
    
