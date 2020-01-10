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
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: efbe25f2-faf5-41c7-8c95-dbc4a835a4a8
description: 既存の Cloud Connector Edition 展開をアップグレードする方法について説明します。
ms.openlocfilehash: c340b7325c95d25212c9c1f77f9379a25708cea8
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002047"
---
# <a name="upgrade-to-a-new-version-of-cloud-connector"></a>Upgrade to a new version of Cloud Connector
 
既存の Cloud Connector Edition 展開をアップグレードする方法について説明します。
  
オンライン管理テナントのアカウントを設定しており、自動更新を有効にしている場合は、自動更新の時間枠の設定に応じて、Skype for Business Cloud Connector エディションの既存の展開がより新しいバージョンに自動でアップグレードされます。手動でアップグレードを実行することもできます。 
  
Cloud Connector Edition バージョン1.4.1 以降では、既定で自動更新が実行されます。 最新バージョン (2.1) に手動でアップグレードする場合は、このトピックで後述する「 [1 つのサイトを新しいバージョンにアップグレード](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade)する」を参照してください。
  
自動更新を有効にするには、クラウドコネクタサービスが実行されている必要があります。 次の手順で、自動更新のプロセスを説明します。
  
- 自動更新プロセスは、自動更新について構成したスケジュールに従って実行します。
    
- オペレーティング システムがタスクを更新する
    
  - すべてのクラウドコネクタ Vm のオペレーティングシステム更新プログラムを確認してダウンロードします。 
    
  - すべてのクラウドコネクタ Vm を1つずつインストールして更新し、再起動します。
    
  - クラウドコネクタ Vm を再起動した後で、別の再起動が必要かどうかを確認します。
    
  - クラウドコネクタの Vm を正常に修正したら、クラウドコネクタホストコンピューターのプロセスを繰り返します。
    
  - クラウドコネクタホストマシンが正常に起動すると、すべての未解決のオペレーティングシステム更新タスクが完了します。
    
- クラウドコネクタの更新タスク
    
  - ダウンロード サイトからバージョン ファイルをダウンロードして確認します。
    
  - 新しいバージョンの .msi ファイルをダウンロードします。 
    
  - 古い msi ファイルをアンインストールします。新しい msi ファイルをインストールします。
    
  - Skype for Business bits の新しいバージョンをダウンロードします。
    
  - Register-CcAppliance を呼び出してアプライアンスを登録します。
    
  - 新しいクラウドコネクタバージョンをインストールします。
    
  - 古いアプライアンスをドレインして、ネットワーク接続を新しいアプライアンスに切り替えます。
    
> [!NOTE]
>  Cloud Connector が新しいビルドに更新されると、クラウドコネクタコマンドレットが更新されないことがあります。 これは、たとえば、自動更新が行われているときに PowerShell ウィンドウを開いたままにした場合に発生する可能性があります。 更新されたコマンドレットを読み込むには、次のいずれかの手順を実行します。クラウドコネクタアプライアンスで PowerShell を > し、PowerShell をもう一度起動します。 > または、インポート-モジュール CloudConnector-Force を実行できます。
  
## <a name="upgrade-a-single-site-to-a-new-version"></a>単一サイトの新バージョンへのアップグレード
<a name="BKMK_Upgrade"> </a>

アップグレードするサイトにアプライアンスが 1 台のみある場合は、次を行います。
  
1. コントロールパネルの [プログラム**と機能] \> \> **で既存のクラウドコネクタのバージョンをアンインストールします。
    
2. 新しいバージョンの CloudConnector の .msi をから[https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller)インストールします。
    
3. CloudConnector.ini ファイルがインストールするバージョンに該当するファイルで、環境に必要な値をすべて更新したことを確認します。 以前のリリースからの .ini ファイルを使うことはできませんCloudConnector_shortest をアップグレードする場合は「Prepare your environment for Cloud Connector」トピックをご覧ください。 クラウドコネクタをアップグレードする場合は、「[クラウドコネクタの製品を準備](prepare-your-cloud-connector-appliance.md)する」のトピックを参照して、[SiteName] と [EnableReferSupport] が cloudconnector の .ini ファイルで適切な値に設定されていることを確認してください。
    
4. 管理者として PowerShell コンソールを起動し、次のコマンドレットを実行して現在のアプライアンスを登録します。
    
   ```powershell
   Register-CcAppliance
   ```

5. 次のコマンドレットを実行して最新のバージョンをダウンロードします。
    
   ```powershell
   Start-CcDownload
   ```

6. 次のコマンドレットを実行してインストールを開始します。 
    
   ```powershell
   Install-CcAppliance -Upgrade
   ```

7. 次のコマンドレットを実行して、新しい展開をアクティブ化し、以前のバージョンをオフにします。
    
   ```powershell
   Switch-CcVersion
   ```

サイトに複数のアプライアンスがある場合は、前の手順に従い各アプライアンスを一度に 1 台ずつアップグレードしてください。
  
ドメイン管理者、仮想マシン管理者、セーフモード管理者、テナント管理者の資格情報を更新する場合は、 _Updateallcredentials_パラメーターを指定してコマンドレットを実行して、すべての資格情報をリセットすることができます。
  
```powershell
Install-CcAppliance -UpdateAllCredentials
```

次に、新しいバージョンへのアップグレードを開始すると、新しい資格情報を入力するように指示されます。 
  
テナント管理者の資格情報のみをリセットする場合は、次のコマンドレットを実行します。
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="upgrade-multiple-sites-to-a-new-version"></a>マルチサイトの新バージョンへのアップグレード
<a name="BKMK_Upgrade"> </a>

単一サイトのアップグレードの手順に従い、展開でサイトごとに一度に 1 つのサイトずつアップグレードします。各サイトをアップグレードしたら、必ず[Validate your Cloud Connector deployment](validate-your-cloud-connector-deployment.md)を行ってください。
  

