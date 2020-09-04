---
title: Cloud Connector 新バージョンへのアップグレード
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: efbe25f2-faf5-41c7-8c95-dbc4a835a4a8
description: Cloud Connector エディションの展開をアップグレードする方法について説明します。
ms.openlocfilehash: dc9473dbf605f00df76daa1a88a29c7d5ed65fd8
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359293"
---
# <a name="upgrade-to-a-new-version-of-cloud-connector"></a>Cloud Connector 新バージョンへのアップグレード

> [!Important]
> Cloud Connector エディションは、2021年7月31日、Skype for Business Online と共に廃止されます。 組織が Teams にアップグレードされたら、 [直接ルーティング](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)を使用してオンプレミスのテレフォニーネットワークを teams に接続する方法について説明します。
 
Cloud Connector エディションの展開をアップグレードする方法について説明します。
  
オンライン管理テナントアカウントを設定し、自動更新を有効にしている場合、既存の Skype for Business Cloud Connector エディションの展開は、自動更新の時間枠の構成に従って、新しいバージョンに自動的にアップグレードされます。 手動アップグレードを実行することもできます。 
  
Cloud Connector Edition バージョン1.4.1 以降では、既定で自動更新が実行されます。 最新バージョン (2.1) に手動でアップグレードする場合は、このトピックで後述する「 [1 つのサイトを新しいバージョンにアップグレード](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade) する」を参照してください。
  
自動更新では、Cloud Connector service が実行されている必要があります。 次の手順では、自動更新のプロセスについて説明します。
  
- 自動更新プロセスは、自動更新のために構成したスケジュールに従って実行されます。
    
- オペレーティングシステムの更新タスク
    
  - すべての Cloud Connector Vm に対するオペレーティングシステムの更新プログラムを確認してダウンロードします。 
    
  - すべての Cloud Connector Vm を1つずつインストールして更新し、再起動します。
    
  - Cloud Connector Vm が再起動したら、別の再起動が必要かどうかを確認します。
    
  - Cloud Connector Vm が正常にパッチされたら、Cloud Connector ホストコンピューターのプロセスを繰り返します。
    
  - Cloud Connector ホストマシンが正常に起動すると、すべての未解決のオペレーティングシステムの更新タスクが完了します。
    
- Cloud Connector の更新タスク
    
  - ダウンロードサイトからバージョンファイルをダウンロードして確認します。
    
  - 新しいバージョンの .msi ファイルをダウンロードします。 
    
  - 古い msi ファイルをアンインストールします。新しい msi ファイルをインストールします。
    
  - 新しいバージョンの Skype for Business ビットをダウンロードします。
    
  - Register-CcAppliance を呼び出してアプライアンスを登録します。
    
  - 新しい Cloud Connector のバージョンをインストールします。
    
  - 古いアプライアンスをドレインし、ネットワーク接続を新しいアプライアンスに切り替えます。
    
> [!NOTE]
>  Cloud Connector が新しいビルドに更新された場合、Cloud Connector コマンドレットは更新されない可能性があります。 これは、自動更新の実行中に PowerShell ウィンドウを開いたままにした場合などに発生します。 更新されたコマンドレットを読み込むには、次のいずれかの手順を実行します。 Cloud Connector アプライアンスで PowerShell を > てから、PowerShell をもう一度開いてください。または、> を実行することもできます。
  
## <a name="upgrade-a-single-site-to-a-new-version"></a>1つのサイトを新しいバージョンにアップグレードする
<a name="BKMK_Upgrade"> </a>

アップグレードするサイトにアプライアンスが1つだけある場合は、次の手順を実行します。
  
1. **コントロールパネルの \> [プログラム \> と機能]** で既存の Cloud Connector のバージョンをアンインストールします。
    
2. 新しいバージョンの CloudConnector.msi をからインストール [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) します。
    
3. インストールしているバージョンの CloudConnector.ini ファイルがあること、および環境に必要なすべての値が更新されていることを確認します。 以前のリリースから .ini ファイルを使用することはできません。 Cloud Connector をアップグレードする場合は、「 [Cloud connector を準備](prepare-your-cloud-connector-appliance.md) する」および「SiteName と EnableReferSupport が CloudConnector.ini ファイルの正しい値に設定されていることを確認してください」を参照してください。
    
4. 管理者として PowerShell コンソールを起動し、次のコマンドレットを実行して現在のアプライアンスを登録します。
    
   ```powershell
   Register-CcAppliance
   ```

5. 次のコマンドレットを実行して、最新バージョンをダウンロードします。
    
   ```powershell
   Start-CcDownload
   ```

6. 次のコマンドレットを実行して、インストールを開始します。 
    
   ```powershell
   Install-CcAppliance -Upgrade
   ```

7. 次のコマンドレットを実行して、新しい展開をアクティブ化し、以前のバージョンをオフにします。
    
   ```powershell
   Switch-CcVersion
   ```

サイト内に複数のアプライアンスがある場合は、前の手順に従って各アプライアンスを1つずつアップグレードしてください。
  
ドメイン管理者、仮想マシン管理者、セーフモード管理者、テナント管理者の資格情報を更新する場合は、  _Updateallcredentials_ パラメーターを指定してコマンドレットを実行すると、すべての資格情報をリセットできます。
  
```powershell
Install-CcAppliance -UpdateAllCredentials
```

その後、新しいバージョンへのアップグレードを開始すると、新しい資格情報を入力するように求められます。 
  
テナント管理者の資格情報のみをリセットする場合は、次のコマンドレットを実行します。
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="upgrade-multiple-sites-to-a-new-version"></a>複数のサイトを新しいバージョンにアップグレードする
<a name="BKMK_Upgrade"> </a>

1つのサイトをアップグレードする手順を実行し、展開内のサイトごとに1つずつサイトをアップグレードします。 各サイトをアップグレードした後 [に、Cloud Connector の展開](validate-your-cloud-connector-deployment.md) を確認して検証してください。
  

