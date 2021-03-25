---
title: クラウド コネクタの新バージョンへのアップグレード
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
description: クラウド コネクタ エディションの展開をアップグレードする方法について説明します。
ms.openlocfilehash: fea78c6b1b6ba3b2e644fef71d78b94aa3a244b7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109133"
---
# <a name="upgrade-to-a-new-version-of-cloud-connector"></a>クラウド コネクタの新バージョンへのアップグレード

> [!Important]
> Cloud Connector Edition は、Skype for Business Online と共に 2021 年 7 月 31 日に廃止されます。 組織が Teams にアップグレードしたら、直接ルーティングを使用してオンプレミスのテレフォニー ネットワークを Teams に接続する方法 [について説明します](/MicrosoftTeams/direct-routing-landing-page)。
 
クラウド コネクタ エディションの展開をアップグレードする方法について説明します。
  
オンライン管理テナント アカウントをセットアップし、自動更新を有効にしている場合、Skype for Business Cloud Connector Edition の既存の展開は、自動更新のタイム ウィンドウ構成に従って、自動的に新しいバージョンにアップグレードされます。 手動アップグレードを実行できます。 
  
Cloud Connector Edition バージョン 1.4.1 以降では、既定で自動更新が実行されます。 最新バージョン (2.1) に手動でアップグレードする場合は、[](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade)後の「単一サイトを新しいバージョンにアップグレードする」を参照してください。
  
自動更新では、クラウド コネクタ サービスが実行されている必要があります。 次の手順では、自動更新のプロセスについて説明します。
  
- 自動更新プロセスは、自動更新用に構成したスケジュールに従って実行されます。
    
- オペレーティング システムの更新タスク
    
  - すべてのクラウド コネクタ VM に対するオペレーティング システムの更新プログラムを確認してダウンロードします。 
    
  - すべてのクラウド コネクタ VM を 1 つ 1 つインストールして更新し、再起動します。
    
  - Cloud Connector VM の再起動後に、別の再起動が必要な場合に確認します。
    
  - Cloud Connector VM のパッチが正常に適用された後、クラウド コネクタ ホスト コンピューターのプロセスを繰り返します。
    
  - クラウド コネクタ ホスト コンピューターが正常に起動すると、未処理のオペレーティング システム更新タスクが完了します。
    
- クラウド コネクタの更新タスク
    
  - ダウンロード サイトからバージョン ファイルをダウンロードして確認します。
    
  - 新しいバージョンの .msi ファイルをダウンロードします。 
    
  - 古い msi ファイルをアンインストールします。新しい msi ファイルをインストールします。
    
  - Skype for Business ビットの新しいバージョンをダウンロードします。
    
  - Register-CcAppliance を呼び出してアプライアンスを登録します。
    
  - 新しいクラウド コネクタ バージョンをインストールします。
    
  - 古いアプライアンスをドレインし、ネットワーク接続を新しいアプライアンスに切り替えます。
    
> [!NOTE]
>  Cloud Connector が新しいビルドに更新される場合、Cloud Connector コマンドレットは更新されない可能性があります。 これは、たとえば、自動更新の実行中に PowerShell ウィンドウが開いた残っている場合に発生する可能性があります。 更新されたコマンドレットを読み込むには、次のいずれかの手順を実行します:> クラウド コネクタ アプライアンスで PowerShell を閉じてから、PowerShell.> を再度開くか、Import-Module CloudConnector -Force を実行できます。
  
## <a name="upgrade-a-single-site-to-a-new-version"></a>1 つのサイトを新しいバージョンにアップグレードする
<a name="BKMK_Upgrade"> </a>

アップグレードするアプライアンスがサイトに 1 つだけある場合は、次の手順を実行します。
  
1. コントロール パネル の [プログラム] で既存のクラウド コネクタのバージョンを **\> \> アンインストールプログラムと機能。**
    
2. から新しいバージョンのCloudConnector.msiインストールします [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) 。
    
3. インストールするバージョンの CloudConnector.ini ファイルを持ち、環境に必要なすべての値を更新したと確認します。 以前のリリースの .ini ファイルは使用できません。 クラウド コネクタをアップグレードする場合は、トピック「クラウド[](prepare-your-cloud-connector-appliance.md)コネクタ アプライアンスの準備」を参照し、SiteName と EnableReferSupport が CloudConnector.ini ファイルの正しい値に設定されていることを確認してください。
    
4. PowerShell コンソールを管理者として起動し、次のコマンドレットを実行して現在のアプライアンスを登録します。
    
   ```powershell
   Register-CcAppliance
   ```

5. 次のコマンドレットを実行して、最新バージョンをダウンロードします。
    
   ```powershell
   Start-CcDownload
   ```

6. 次のコマンドレットを実行してインストールを開始します。 
    
   ```powershell
   Install-CcAppliance -Upgrade
   ```

7. 次のコマンドレットを実行して新しい展開をアクティブ化し、以前のバージョンをオフにします。
    
   ```powershell
   Switch-CcVersion
   ```

サイトに複数のアプライアンスがある場合は、前の手順に従って各アプライアンスを 1 つ 1 つアップグレードしてください。
  
ドメイン管理者、仮想マシン管理者、セーフ モード管理者、テナント管理者の資格情報を更新する場合は  _、UpdateAllCredentials_ パラメーターを使用してコマンドレットを実行して、すべての資格情報をリセットできます。
  
```powershell
Install-CcAppliance -UpdateAllCredentials
```

次に、新しいバージョンへのアップグレードを開始すると、新しい資格情報の入力が昇格されます。 
  
テナント管理者の資格情報のみをリセットする場合は、次のコマンドレットを実行します。
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="upgrade-multiple-sites-to-a-new-version"></a>複数のサイトを新しいバージョンにアップグレードする
<a name="BKMK_Upgrade"> </a>

1 つのサイトをアップグレードし、展開内の各サイトに対して一度に 1 つのサイトをアップグレードする手順に従います。 各サイトをアップグレード [した後で、クラウド コネクタの展開](validate-your-cloud-connector-deployment.md) を確認して検証します。
